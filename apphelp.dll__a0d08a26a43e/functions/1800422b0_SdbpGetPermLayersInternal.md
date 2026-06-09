# SdbpGetPermLayersInternal

- ea: `0x1800422b0`
- end: `0x180042561`
- name: `SdbpGetPermLayersInternal`
- size: `689`
- prototype: `__int64 __fastcall(PCWSTR SourceString, void *, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033f0c`

## callees

- `0x18000f114`
- `0x180016910`
- `0x180018f20`
- `0x1800422b0`
- `0x180059169`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180042309`
- `ntdll!RtlInitUnicodeString` at `0x180042309`
- `ntdll!ZwClose` at `0x1800423a9`
- `ntdll!ZwClose` at `0x1800423a9`
- `ntdll!ZwQueryValueKey` at `0x18004239c`
- `ntdll!ZwQueryValueKey` at `0x180042463`
- `ntdll!ZwQueryValueKey` at `0x18004239c`
- `ntdll!ZwQueryValueKey` at `0x180042463`
- `ntdll!RtlAllocateHeap` at `0x180042417`
- `ntdll!RtlAllocateHeap` at `0x180042417`

## string_xrefs

- `0x18004234e`: `Failed to open key [%x]`
- `0x18004232e`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x1800423db`: `Failed to read value info from key because info size is unreasonably big [%x] [%x]`
- `0x18004247f`: `Failed to read value info from key [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetPermLayersInternal(PCWSTR SourceString, void *a2, unsigned int *a3, unsigned int a4)
{
  size_t v4; // r12
  signed int Key; // eax
  const char *v9; // r9
  __int64 v10; // r8
  NTSTATUS v11; // ebx
  _DWORD *Heap; // rsi
  _DWORD *v13; // rdi
  unsigned int v14; // edx
  __int64 Length; // [rsp+20h] [rbp-E0h]
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-CCh]
  HANDLE KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE KeyValueInformation[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = *a3;
  v18 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  *a3 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( a2 )
    memset_0(a2, 0, (unsigned int)v4);
  Key = AslRegistryGetKey(
          &KeyHandle,
          L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
          2147483904LL,
          a4,
          0);
  if ( Key >= 0 )
  {
    v11 = ZwQueryValueKey(
            KeyHandle,
            &DestinationString,
            KeyValuePartialInformation,
            KeyValueInformation,
            0x400u,
            &ResultLength);
    ZwClose(KeyHandle);
    if ( v11 == -2147483643 || v11 == -1073741789 )
    {
      if ( ResultLength > 0x2800 )
      {
        AslLogCallPrintf(
          1,
          "SdbpGetPermLayersInternal",
          4125,
          "Failed to read value info from key because info size is unreasonably big [%x] [%x]",
          v11,
          ResultLength);
        return v18;
      }
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
      if ( !Heap )
      {
        Key = ResultLength;
        v9 = "Failed to allocate 0x%lx bytes for KeyValue";
        v10 = 4131;
        goto LABEL_6;
      }
      v13 = Heap;
      v11 = ZwQueryValueKey(
              KeyHandle,
              &DestinationString,
              KeyValuePartialInformation,
              Heap,
              ResultLength,
              &ResultLength);
    }
    else
    {
      Heap = 0;
      v13 = KeyValueInformation;
    }
    if ( v11 >= 0 )
    {
      if ( v13[1] == 1 )
      {
        v14 = v13[2];
        *a3 = v14;
        if ( v13[2] < 2u || *(_WORD *)((char *)v13 + (unsigned int)v13[2] + 10) )
        {
          v14 += 2;
          *a3 = v14;
        }
        if ( a2 )
        {
          if ( v14 <= (unsigned int)v4 )
          {
            memset_0(a2, 0, v4);
            memmove_0(a2, v13 + 3, (unsigned int)v13[2]);
            v18 = 1;
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
    else if ( v11 != -1073741772 )
    {
      LODWORD(Length) = v11;
      AslLogCallPrintf(1, "SdbpGetPermLayersInternal", 4146, "Failed to read value info from key [%x]", Length);
    }
    if ( Heap )
      AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  }
  else if ( Key != -1073741772 )
  {
    v9 = "Failed to open key [%x]";
    v10 = 4108;
LABEL_6:
    LODWORD(Length) = Key;
    AslLogCallPrintf(1, "SdbpGetPermLayersInternal", v10, v9, Length);
  }
  return v18;
}

```

## disassembly

```asm
0x1800422b0  push    rbp
0x1800422b2  push    rbx
0x1800422b3  push    rsi
0x1800422b4  push    rdi
0x1800422b5  push    r12
0x1800422b7  push    r13
0x1800422b9  push    r14
0x1800422bb  lea     rbp, [rsp-360h]
0x1800422c3  sub     rsp, 460h
0x1800422ca  mov     rax, cs:__security_cookie
0x1800422d1  xor     rax, rsp
0x1800422d4  mov     [rbp+390h+var_40], rax
0x1800422db  mov     r12d, [r8]
0x1800422de  xor     edi, edi
0x1800422e0  mov     r14, rdx
0x1800422e3  mov     [rsp+490h+var_45C], edi
0x1800422e7  mov     rdx, rcx; SourceString
0x1800422ea  mov     [rsp+490h+KeyHandle], rdi
0x1800422ef  xorps   xmm0, xmm0
0x1800422f2  mov     [rsp+490h+var_460], edi
0x1800422f6  lea     rcx, [rsp+490h+DestinationString]; DestinationString
0x1800422fb  mov     [r8], edi
0x1800422fe  mov     ebx, r9d
0x180042301  mov     r13, r8
0x180042304  movups  xmmword ptr [rsp+490h+DestinationString.Length], xmm0
0x180042309  call    cs:__imp_RtlInitUnicodeString
0x18004230f  test    r14, r14
0x180042312  jz      short loc_180042321
0x180042314  mov     r8d, r12d; Size
0x180042317  xor     edx, edx; Val
0x180042319  mov     rcx, r14; void *
0x18004231c  call    memset_0
0x180042321  mov     r9d, ebx
0x180042324  mov     dword ptr [rsp+490h+Length], edi
0x180042328  mov     r8d, 80000100h
0x18004232e  lea     rdx, aSoftwareMicros_2; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x180042335  lea     rcx, [rsp+490h+KeyHandle]
0x18004233a  call    AslRegistryGetKey
0x18004233f  test    eax, eax
0x180042341  jns     short loc_180042375
0x180042343  cmp     eax, 0C0000034h
0x180042348  jz      loc_18004253C
0x18004234e  lea     r9, aFailedToOpenKe; "Failed to open key [%x]"
0x180042355  mov     r8d, 100Ch
0x18004235b  lea     rdx, aSdbpgetpermlay; "SdbpGetPermLayersInternal"
0x180042362  mov     dword ptr [rsp+490h+Length], eax
0x180042366  mov     ecx, 1
0x18004236b  call    AslLogCallPrintf
0x180042370  jmp     loc_18004253C
0x180042375  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18004237a  lea     rax, [rsp+490h+var_460]
0x18004237f  mov     [rsp+490h+ResultLength], rax; ResultLength
0x180042384  lea     r9, [rsp+490h+KeyValueInformation]; KeyValueInformation
0x180042389  mov     r8d, 2; KeyValueInformationClass
0x18004238f  mov     dword ptr [rsp+490h+Length], 400h; Length
0x180042397  lea     rdx, [rsp+490h+DestinationString]; ValueName
0x18004239c  call    cs:__imp_ZwQueryValueKey
0x1800423a2  mov     rcx, [rsp+490h+KeyHandle]; Handle
0x1800423a7  mov     ebx, eax
0x1800423a9  call    cs:__imp_ZwClose
0x1800423af  cmp     ebx, 80000005h
0x1800423b5  jz      short loc_1800423CC
0x1800423b7  cmp     ebx, 0C0000023h
0x1800423bd  jz      short loc_1800423CC
0x1800423bf  mov     rsi, rdi
0x1800423c2  lea     rdi, [rsp+490h+KeyValueInformation]
0x1800423c7  jmp     loc_18004246B
0x1800423cc  mov     eax, [rsp+490h+var_460]
0x1800423d0  cmp     eax, 2800h
0x1800423d5  jbe     short loc_180042402
0x1800423d7  mov     dword ptr [rsp+490h+ResultLength], eax
0x1800423db  lea     r9, aFailedToReadVa; "Failed to read value info from key beca"...
0x1800423e2  mov     r8d, 101Dh
0x1800423e8  mov     dword ptr [rsp+490h+Length], ebx
0x1800423ec  lea     rdx, aSdbpgetpermlay; "SdbpGetPermLayersInternal"
0x1800423f3  mov     ecx, 1
0x1800423f8  call    AslLogCallPrintf
0x1800423fd  jmp     loc_18004253C
0x180042402  mov     rcx, gs:60h
0x18004240b  mov     r8, rax; Size
0x18004240e  mov     edx, 8; Flags
0x180042413  mov     rcx, [rcx+30h]; HeapHandle
0x180042417  call    cs:__imp_RtlAllocateHeap
0x18004241d  mov     rsi, rax
0x180042420  test    rax, rax
0x180042423  jnz     short loc_18004243B
0x180042425  mov     eax, [rsp+490h+var_460]
0x180042429  lea     r9, aFailedToAlloca_10; "Failed to allocate 0x%lx bytes for KeyV"...
0x180042430  mov     r8d, 1023h
0x180042436  jmp     loc_18004235B
0x18004243b  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x180042440  lea     rax, [rsp+490h+var_460]
0x180042445  mov     [rsp+490h+ResultLength], rax; ResultLength
0x18004244a  lea     rdx, [rsp+490h+DestinationString]; ValueName
0x18004244f  mov     eax, [rsp+490h+var_460]
0x180042453  mov     r9, rsi; KeyValueInformation
0x180042456  mov     r8d, 2; KeyValueInformationClass
0x18004245c  mov     dword ptr [rsp+490h+Length], eax; Length
0x180042460  mov     rdi, rsi
0x180042463  call    cs:__imp_ZwQueryValueKey
0x180042469  mov     ebx, eax
0x18004246b  test    ebx, ebx
0x18004246d  jns     short loc_1800424A2
0x18004246f  cmp     ebx, 0C0000034h
0x180042475  jz      loc_180042522
0x18004247b  mov     dword ptr [rsp+490h+Length], ebx
0x18004247f  lea     r9, aFailedToReadVa_0; "Failed to read value info from key [%x]"
0x180042486  mov     r8d, 1032h
0x18004248c  lea     rdx, aSdbpgetpermlay; "SdbpGetPermLayersInternal"
0x180042493  mov     ecx, 1
0x180042498  call    AslLogCallPrintf
0x18004249d  jmp     loc_180042522
0x1800424a2  mov     eax, [rdi+4]
0x1800424a5  cmp     eax, 1
0x1800424a8  jz      short loc_1800424BD
0x1800424aa  mov     dword ptr [rsp+490h+Length], eax
0x1800424ae  lea     r9, aUnexpectedValu; "Unexpected value type 0x%x for key"
0x1800424b5  mov     r8d, 1040h
0x1800424bb  jmp     short loc_18004248C
0x1800424bd  mov     edx, [rdi+8]
0x1800424c0  mov     [r13+0], edx
0x1800424c4  cmp     dword ptr [rdi+8], 2
0x1800424c8  jb      short loc_1800424D6
0x1800424ca  mov     ecx, [rdi+8]
0x1800424cd  xor     eax, eax
0x1800424cf  cmp     ax, [rcx+rdi+0Ah]
0x1800424d4  jz      short loc_1800424DD
0x1800424d6  add     edx, 2
0x1800424d9  mov     [r13+0], edx
0x1800424dd  test    r14, r14
0x1800424e0  jz      short loc_180042522
0x1800424e2  cmp     edx, r12d
0x1800424e5  jbe     short loc_1800424FD
0x1800424e7  mov     eax, [rdi+8]
0x1800424ea  lea     r9, aValueLengthDTo; "Value length %d too long for key"
0x1800424f1  mov     dword ptr [rsp+490h+Length], eax
0x1800424f5  mov     r8d, 1062h
0x1800424fb  jmp     short loc_18004248C
0x1800424fd  mov     r8, r12; Size
0x180042500  xor     edx, edx; Val
0x180042502  mov     rcx, r14; void *
0x180042505  call    memset_0
0x18004250a  mov     r8d, [rdi+8]; Size
0x18004250e  lea     rdx, [rdi+0Ch]; Src
0x180042512  mov     rcx, r14; void *
0x180042515  call    memmove_0
0x18004251a  mov     [rsp+490h+var_45C], 1
0x180042522  test    rsi, rsi
0x180042525  jz      short loc_18004253C
0x180042527  mov     rcx, gs:60h
0x180042530  mov     rdx, rsi
0x180042533  mov     rcx, [rcx+30h]
0x180042537  call    AslFree
0x18004253c  mov     eax, [rsp+490h+var_45C]
0x180042540  mov     rcx, [rbp+390h+var_40]
0x180042547  xor     rcx, rsp; StackCookie
0x18004254a  call    __security_check_cookie
0x18004254f  add     rsp, 460h
0x180042556  pop     r14
0x180042558  pop     r13
0x18004255a  pop     r12
0x18004255c  pop     rdi
0x18004255d  pop     rsi
0x18004255e  pop     rbx
0x18004255f  pop     rbp
0x180042560  retn
```
