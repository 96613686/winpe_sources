# SdbpGetPermLayersInternal

- ea: `0x140024700`
- end: `0x14002498c`
- name: `SdbpGetPermLayersInternal`
- size: `652`
- prototype: `__int64 __fastcall(PCWSTR SourceString, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400547d8`

## callees

- `0x14000440f`
- `0x140004469`
- `0x14000449f`
- `0x1400079f0`
- `0x140007b40`
- `0x140007e40`
- `0x140024700`
- `0x14003e364`
- `0x140045d44`
- `0x140046440`
- `0x14005498c`

## string_xrefs

- `0x140024775`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x14002479b`: `Failed to open key [%x]`
- `0x14002482b`: `Failed to read value info from key because info size is unreasonably big [%x] [%x]`
- `0x1400248bd`: `Failed to read value info from key [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetPermLayersInternal(PCWSTR SourceString, void *a2, unsigned int *a3, int a4)
{
  size_t v4; // r13
  int Key; // eax
  const char *v8; // r9
  __int64 v9; // r8
  NTSTATUS v10; // edi
  __int64 v11; // rcx
  _DWORD *v12; // r14
  _DWORD *v13; // rsi
  unsigned int *v14; // r8
  unsigned int v15; // edx
  unsigned int v16; // eax
  __int64 Length; // [rsp+20h] [rbp-E0h]
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v20; // [rsp+34h] [rbp-CCh]
  HANDLE KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int *v22; // [rsp+40h] [rbp-C0h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE KeyValueInformation[1024]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = *a3;
  v22 = a3;
  v20 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  *a3 = 0;
  DestinationString = 0;
  RtlInitUnicodeString_0(&DestinationString, SourceString);
  if ( a2 )
    memset(a2, 0, (unsigned int)v4);
  Key = AslRegistryGetKey(
          &KeyHandle,
          L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
          0x80000100,
          a4);
  if ( Key >= 0 )
  {
    v10 = ZwQueryValueKey_0(
            KeyHandle,
            &DestinationString,
            KeyValuePartialInformation,
            KeyValueInformation,
            0x400u,
            &ResultLength);
    ZwClose_0(KeyHandle);
    if ( v10 == -2147483643 || v10 == -1073741789 )
    {
      if ( ResultLength > 0x2800 )
      {
        AslLogCallPrintf(
          1,
          "SdbpGetPermLayersInternal",
          4125,
          "Failed to read value info from key because info size is unreasonably big [%x] [%x]",
          v10,
          ResultLength);
        return v20;
      }
      v12 = (_DWORD *)AslAlloc(v11, ResultLength, 1);
      if ( !v12 )
      {
        Key = ResultLength;
        v8 = "Failed to allocate 0x%lx bytes for KeyValue";
        v9 = 4131;
        goto LABEL_6;
      }
      v13 = v12;
      v10 = ZwQueryValueKey_0(
              KeyHandle,
              &DestinationString,
              KeyValuePartialInformation,
              v12,
              ResultLength,
              &ResultLength);
    }
    else
    {
      v12 = 0;
      v13 = KeyValueInformation;
    }
    if ( v10 >= 0 )
    {
      if ( v13[1] == 1 )
      {
        v14 = v22;
        v15 = v13[2];
        *v22 = v15;
        v16 = v13[2];
        if ( v16 < 2 || (v11 = v16, *(_WORD *)((char *)v13 + v16 + 10)) )
        {
          v15 += 2;
          *v14 = v15;
        }
        if ( a2 )
        {
          if ( v15 <= (unsigned int)v4 )
          {
            memset(a2, 0, v4);
            memmove(a2, v13 + 3, (unsigned int)v13[2]);
            v20 = 1;
          }
          else
          {
            LODWORD(Length) = v13[2];
            AslLogCallPrintf(1, "SdbpGetPermLayersInternal", 4194, "Value length %d too long for key", Length);
          }
        }
      }
      else
      {
        LODWORD(Length) = v13[1];
        AslLogCallPrintf(1, "SdbpGetPermLayersInternal", 4160, "Unexpected value type 0x%x for key", Length);
      }
    }
    else if ( v10 != -1073741772 )
    {
      LODWORD(Length) = v10;
      AslLogCallPrintf(1, "SdbpGetPermLayersInternal", 4146, "Failed to read value info from key [%x]", Length);
    }
    if ( v12 )
      AslFree(v11, v12);
  }
  else if ( Key != -1073741772 )
  {
    v8 = "Failed to open key [%x]";
    v9 = 4108;
LABEL_6:
    LODWORD(Length) = Key;
    AslLogCallPrintf(1, "SdbpGetPermLayersInternal", v9, v8, Length);
  }
  return v20;
}

```

## disassembly

```asm
0x140024700  push    rbp
0x140024702  push    rbx
0x140024703  push    rsi
0x140024704  push    rdi
0x140024705  push    r13
0x140024707  push    r14
0x140024709  push    r15
0x14002470b  lea     rbp, [rsp-370h]
0x140024713  sub     rsp, 470h
0x14002471a  mov     rax, cs:__security_cookie
0x140024721  xor     rax, rsp
0x140024724  mov     [rbp+3A0h+var_40], rax
0x14002472b  mov     r13d, [r8]
0x14002472e  xor     esi, esi
0x140024730  mov     r15, rdx
0x140024733  mov     [rsp+4A0h+var_460], r8
0x140024738  mov     rdx, rcx; SourceString
0x14002473b  mov     [rsp+4A0h+var_46C], esi
0x14002473f  xorps   xmm0, xmm0
0x140024742  mov     [rsp+4A0h+KeyHandle], rsi
0x140024747  lea     rcx, [rsp+4A0h+DestinationString]; DestinationString
0x14002474c  mov     [rsp+4A0h+var_470], esi
0x140024750  mov     ebx, r9d
0x140024753  mov     [r8], esi
0x140024756  movups  xmmword ptr [rsp+4A0h+DestinationString.Length], xmm0
0x14002475b  call    RtlInitUnicodeString_0
0x140024760  test    r15, r15
0x140024763  jz      short loc_140024772
0x140024765  mov     r8d, r13d; Size
0x140024768  xor     edx, edx; Val
0x14002476a  mov     rcx, r15; void *
0x14002476d  call    memset
0x140024772  mov     r9d, ebx
0x140024775  lea     rdx, aSoftwareMicros_2; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x14002477c  mov     r8d, 80000100h
0x140024782  lea     rcx, [rsp+4A0h+KeyHandle]
0x140024787  call    AslRegistryGetKey
0x14002478c  test    eax, eax
0x14002478e  jns     short loc_1400247C2
0x140024790  cmp     eax, 0C0000034h
0x140024795  jz      loc_140024966
0x14002479b  lea     r9, aFailedToOpenKe; "Failed to open key [%x]"
0x1400247a2  mov     r8d, 100Ch
0x1400247a8  mov     ecx, 1
0x1400247ad  lea     rdx, aSdbpgetpermlay; "SdbpGetPermLayersInternal"
0x1400247b4  mov     dword ptr [rsp+4A0h+Length], eax
0x1400247b8  call    AslLogCallPrintf
0x1400247bd  jmp     loc_140024966
0x1400247c2  mov     rcx, [rsp+4A0h+KeyHandle]; KeyHandle
0x1400247c7  lea     rax, [rsp+4A0h+var_470]
0x1400247cc  mov     [rsp+4A0h+ResultLength], rax; ResultLength
0x1400247d1  lea     r9, [rsp+4A0h+KeyValueInformation]; KeyValueInformation
0x1400247d6  mov     r8d, 2; KeyValueInformationClass
0x1400247dc  mov     dword ptr [rsp+4A0h+Length], 400h; Length
0x1400247e4  lea     rdx, [rsp+4A0h+DestinationString]; ValueName
0x1400247e9  call    ZwQueryValueKey_0
0x1400247ee  mov     rcx, [rsp+4A0h+KeyHandle]; Handle
0x1400247f3  mov     edi, eax
0x1400247f5  call    ZwClose_0
0x1400247fa  mov     ebx, 1
0x1400247ff  cmp     edi, 80000005h
0x140024805  jz      short loc_14002481C
0x140024807  cmp     edi, 0C0000023h
0x14002480d  jz      short loc_14002481C
0x14002480f  mov     r14, rsi
0x140024812  lea     rsi, [rsp+4A0h+KeyValueInformation]
0x140024817  jmp     loc_1400248A9
0x14002481c  mov     eax, [rsp+4A0h+var_470]
0x140024820  cmp     eax, 2800h
0x140024825  jbe     short loc_14002484F
0x140024827  mov     dword ptr [rsp+4A0h+ResultLength], eax
0x14002482b  lea     r9, aFailedToReadVa; "Failed to read value info from key beca"...
0x140024832  mov     r8d, 101Dh
0x140024838  mov     dword ptr [rsp+4A0h+Length], edi
0x14002483c  lea     rdx, aSdbpgetpermlay; "SdbpGetPermLayersInternal"
0x140024843  mov     ecx, ebx
0x140024845  call    AslLogCallPrintf
0x14002484a  jmp     loc_140024966
0x14002484f  mov     rdx, rax
0x140024852  mov     r8d, ebx
0x140024855  call    AslAlloc
0x14002485a  mov     r14, rax
0x14002485d  test    rax, rax
0x140024860  jnz     short loc_14002487A
0x140024862  mov     eax, [rsp+4A0h+var_470]
0x140024866  lea     r9, aFailedToAlloca_5; "Failed to allocate 0x%lx bytes for KeyV"...
0x14002486d  mov     r8d, 1023h
0x140024873  mov     ecx, ebx
0x140024875  jmp     loc_1400247AD
0x14002487a  mov     rcx, [rsp+4A0h+KeyHandle]; KeyHandle
0x14002487f  lea     rax, [rsp+4A0h+var_470]
0x140024884  mov     [rsp+4A0h+ResultLength], rax; ResultLength
0x140024889  lea     rdx, [rsp+4A0h+DestinationString]; ValueName
0x14002488e  mov     eax, [rsp+4A0h+var_470]
0x140024892  mov     r9, r14; KeyValueInformation
0x140024895  mov     r8d, 2; KeyValueInformationClass
0x14002489b  mov     dword ptr [rsp+4A0h+Length], eax; Length
0x14002489f  mov     rsi, r14
0x1400248a2  call    ZwQueryValueKey_0
0x1400248a7  mov     edi, eax
0x1400248a9  test    edi, edi
0x1400248ab  jns     short loc_1400248DA
0x1400248ad  cmp     edi, 0C0000034h
0x1400248b3  jz      loc_140024959
0x1400248b9  mov     dword ptr [rsp+4A0h+Length], edi
0x1400248bd  lea     r9, aFailedToReadVa_0; "Failed to read value info from key [%x]"
0x1400248c4  mov     r8d, 1032h
0x1400248ca  lea     rdx, aSdbpgetpermlay; "SdbpGetPermLayersInternal"
0x1400248d1  mov     ecx, ebx
0x1400248d3  call    AslLogCallPrintf
0x1400248d8  jmp     short loc_140024959
0x1400248da  mov     eax, [rsi+4]
0x1400248dd  cmp     eax, ebx
0x1400248df  jz      short loc_1400248F4
0x1400248e1  mov     dword ptr [rsp+4A0h+Length], eax
0x1400248e5  lea     r9, aUnexpectedValu; "Unexpected value type 0x%x for key"
0x1400248ec  mov     r8d, 1040h
0x1400248f2  jmp     short loc_1400248CA
0x1400248f4  mov     r8, [rsp+4A0h+var_460]
0x1400248f9  mov     edx, [rsi+8]
0x1400248fc  mov     [r8], edx
0x1400248ff  mov     eax, [rsi+8]
0x140024902  cmp     eax, 2
0x140024905  jb      short loc_140024912
0x140024907  mov     ecx, eax
0x140024909  xor     eax, eax
0x14002490b  cmp     ax, [rcx+rsi+0Ah]
0x140024910  jz      short loc_140024918
0x140024912  add     edx, 2
0x140024915  mov     [r8], edx
0x140024918  test    r15, r15
0x14002491b  jz      short loc_140024959
0x14002491d  cmp     edx, r13d
0x140024920  jbe     short loc_140024938
0x140024922  mov     eax, [rsi+8]
0x140024925  lea     r9, aValueLengthDTo; "Value length %d too long for key"
0x14002492c  mov     dword ptr [rsp+4A0h+Length], eax
0x140024930  mov     r8d, 1062h
0x140024936  jmp     short loc_1400248CA
0x140024938  mov     r8, r13; Size
0x14002493b  xor     edx, edx; Val
0x14002493d  mov     rcx, r15; void *
0x140024940  call    memset
0x140024945  mov     r8d, [rsi+8]; Size
0x140024949  lea     rdx, [rsi+0Ch]; Src
0x14002494d  mov     rcx, r15; void *
0x140024950  call    memmove
0x140024955  mov     [rsp+4A0h+var_46C], ebx
0x140024959  test    r14, r14
0x14002495c  jz      short loc_140024966
0x14002495e  mov     rdx, r14
0x140024961  call    AslFree
0x140024966  mov     eax, [rsp+4A0h+var_46C]
0x14002496a  mov     rcx, [rbp+3A0h+var_40]
0x140024971  xor     rcx, rsp; StackCookie
0x140024974  call    __security_check_cookie
0x140024979  add     rsp, 470h
0x140024980  pop     r15
0x140024982  pop     r14
0x140024984  pop     r13
0x140024986  pop     rdi
0x140024987  pop     rsi
0x140024988  pop     rbx
0x140024989  pop     rbp
0x14002498a  retn
```
