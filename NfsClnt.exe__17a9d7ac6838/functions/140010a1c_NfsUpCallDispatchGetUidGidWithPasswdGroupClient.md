# NfsUpCallDispatchGetUidGidWithPasswdGroupClient

- ea: `0x140010a1c`
- end: `0x140010bde`
- name: `NfsUpCallDispatchGetUidGidWithPasswdGroupClient`
- size: `450`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1400072b8`

## callees

- `0x140010a1c`
- `0x1400111a0`
- `0x140018350`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x140010b5c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140010b5c`
- `ntdll!RtlAppendUnicodeToString` at `0x140010b4c`
- `ntdll!RtlAppendUnicodeToString` at `0x140010b4c`
- `ntdll!RtlCopyUnicodeString` at `0x140010b3a`
- `ntdll!RtlCopyUnicodeString` at `0x140010b3a`

## pseudocode

```c
__int64 __fastcall NfsUpCallDispatchGetUidGidWithPasswdGroupClient(
        __int64 a1,
        unsigned int *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6)
{
  RTL_SRWLOCK *v6; // rdi
  int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // r11d
  __int64 v12; // r10
  __int64 v13; // r9
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-D8h] BYREF
  UNICODE_STRING Source; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING SourceString; // [rsp+48h] [rbp-B8h] BYREF
  char v17; // [rsp+60h] [rbp-A0h] BYREF

  v6 = g_PasswdGroupContext;
  *(_DWORD *)(&Source.MaximumLength + 1) = 0;
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  if ( !g_PasswdGroupContext )
    return 3221226021LL;
  *(_DWORD *)&DestinationString.Length = 17039360;
  DestinationString.Buffer = (PWSTR)&v17;
  if ( a3 >= 0x20 )
  {
    v10 = a2[5];
    if ( v10 > 0xFFFF
      || (v11 = a2[7], v11 > 0xFFFF)
      || (v12 = a2[4], (unsigned int)(v12 - 32) > 0xFFDF)
      || (v13 = a2[6], (unsigned int)(v13 - 32) > 0xFFDF) )
    {
      v9 = -1073741811;
      goto LABEL_16;
    }
    if ( a3 >= (unsigned int)v12 + v10 && a3 >= (unsigned int)v13 + v11 )
    {
      SourceString.Length = a2[5];
      SourceString.MaximumLength = v10;
      SourceString.Buffer = (PWSTR)((char *)a2 + v12);
      Source.Length = v11;
      Source.MaximumLength = v11;
      Source.Buffer = (PWSTR)((char *)a2 + v13);
      RtlCopyUnicodeString(&DestinationString, &SourceString);
      RtlAppendUnicodeToString(&DestinationString, L"\\");
      RtlAppendUnicodeStringToString(&DestinationString, &Source);
      v9 = NfsUpCallpPasswdGroupLookupUserByName(v6, &DestinationString);
      if ( v9 == -1073741275 )
        v9 = NfsUpCallpPasswdGroupLookupUserByName(v6, &Source);
      if ( v9 >= 0 )
      {
        *(_DWORD *)(a4 + 40) = 0;
        *(_DWORD *)(a4 + 44) = 0;
      }
      goto LABEL_16;
    }
  }
  v9 = -2147483643;
LABEL_16:
  *a6 = 48;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140010a1c  mov     [rsp-8+arg_0], rbx
0x140010a21  push    rbp
0x140010a22  push    rsi
0x140010a23  push    rdi
0x140010a24  lea     rbp, [rsp-180h]
0x140010a2c  sub     rsp, 280h
0x140010a33  mov     rax, cs:__security_cookie
0x140010a3a  xor     rax, rsp
0x140010a3d  mov     [rbp+190h+var_20], rax
0x140010a44  mov     rdi, cs:g_PasswdGroupContext
0x140010a4b  mov     rbx, r9
0x140010a4e  mov     rsi, [rbp+190h+arg_28]
0x140010a55  mov     dword ptr [rsp+290h+Source+4], 0
0x140010a5d  mov     dword ptr [rsp+290h+SourceString+4], 0
0x140010a65  mov     dword ptr [rsp+290h+DestinationString+4], 0
0x140010a6d  mov     [rsp+290h+var_270], 0
0x140010a75  mov     [rsp+290h+var_26C], 0
0x140010a7d  test    rdi, rdi
0x140010a80  jnz     short loc_140010A8C
0x140010a82  mov     eax, 0C0000225h
0x140010a87  jmp     loc_140010BBC
0x140010a8c  mov     dword ptr [rsp+290h+DestinationString.Length], 1040000h
0x140010a94  lea     rax, [rsp+290h+var_230]
0x140010a99  mov     [rsp+290h+DestinationString.Buffer], rax
0x140010a9e  cmp     r8d, 20h ; ' '
0x140010aa2  jnb     short loc_140010AAE
0x140010aa4  mov     ecx, 80000005h
0x140010aa9  jmp     loc_140010BB4
0x140010aae  mov     ecx, [rdx+14h]
0x140010ab1  mov     eax, 0FFFFh
0x140010ab6  cmp     ecx, eax
0x140010ab8  ja      loc_140010BAF
0x140010abe  mov     r11d, [rdx+1Ch]
0x140010ac2  cmp     r11d, eax
0x140010ac5  ja      loc_140010BAF
0x140010acb  mov     r10d, [rdx+10h]
0x140010acf  lea     eax, [r10-20h]
0x140010ad3  cmp     eax, 0FFDFh
0x140010ad8  ja      loc_140010BAF
0x140010ade  mov     r9d, [rdx+18h]
0x140010ae2  lea     eax, [r9-20h]
0x140010ae6  cmp     eax, 0FFDFh
0x140010aeb  ja      loc_140010BAF
0x140010af1  lea     eax, [r10+rcx]
0x140010af5  cmp     r8d, eax
0x140010af8  jb      short loc_140010AA4
0x140010afa  lea     eax, [r9+r11]
0x140010afe  cmp     r8d, eax
0x140010b01  jb      short loc_140010AA4
0x140010b03  movzx   eax, cx
0x140010b06  mov     [rsp+290h+SourceString.Length], cx
0x140010b0b  lea     rax, [rdx+r10]
0x140010b0f  mov     [rsp+290h+SourceString.MaximumLength], cx
0x140010b14  mov     [rsp+290h+SourceString.Buffer], rax
0x140010b19  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x140010b1e  movzx   eax, r11w
0x140010b22  mov     [rsp+290h+Source.Length], ax
0x140010b27  mov     [rsp+290h+Source.MaximumLength], ax
0x140010b2c  lea     rax, [rdx+r9]
0x140010b30  lea     rdx, [rsp+290h+SourceString]; SourceString
0x140010b35  mov     [rsp+290h+Source.Buffer], rax
0x140010b3a  call    cs:__imp_RtlCopyUnicodeString
0x140010b40  lea     rdx, asc_14001B4A0; "\\"
0x140010b47  lea     rcx, [rsp+290h+DestinationString]; Destination
0x140010b4c  call    cs:__imp_RtlAppendUnicodeToString
0x140010b52  lea     rdx, [rsp+290h+Source]; Source
0x140010b57  lea     rcx, [rsp+290h+DestinationString]; Destination
0x140010b5c  call    cs:__imp_RtlAppendUnicodeStringToString
0x140010b62  lea     r9, [rsp+290h+var_26C]
0x140010b67  mov     rcx, rdi; SRWLock
0x140010b6a  lea     r8, [rsp+290h+var_270]
0x140010b6f  lea     rdx, [rsp+290h+DestinationString]; Key
0x140010b74  call    NfsUpCallpPasswdGroupLookupUserByName
0x140010b79  mov     ecx, eax
0x140010b7b  cmp     eax, 0C0000225h
0x140010b80  jnz     short loc_140010B9B
0x140010b82  lea     r9, [rsp+290h+var_26C]
0x140010b87  mov     rcx, rdi; SRWLock
0x140010b8a  lea     r8, [rsp+290h+var_270]
0x140010b8f  lea     rdx, [rsp+290h+Source]; Key
0x140010b94  call    NfsUpCallpPasswdGroupLookupUserByName
0x140010b99  mov     ecx, eax
0x140010b9b  test    ecx, ecx
0x140010b9d  js      short loc_140010BB4
0x140010b9f  mov     eax, [rsp+290h+var_270]
0x140010ba3  mov     [rbx+28h], eax
0x140010ba6  mov     eax, [rsp+290h+var_26C]
0x140010baa  mov     [rbx+2Ch], eax
0x140010bad  jmp     short loc_140010BB4
0x140010baf  mov     ecx, 0C000000Dh
0x140010bb4  mov     dword ptr [rsi], 30h ; '0'
0x140010bba  mov     eax, ecx
0x140010bbc  mov     rcx, [rbp+190h+var_20]
0x140010bc3  xor     rcx, rsp; StackCookie
0x140010bc6  call    __security_check_cookie
0x140010bcb  mov     rbx, [rsp+290h+arg_0]
0x140010bd3  add     rsp, 280h
0x140010bda  pop     rdi
0x140010bdb  pop     rsi
0x140010bdc  pop     rbp
0x140010bdd  retn
```
