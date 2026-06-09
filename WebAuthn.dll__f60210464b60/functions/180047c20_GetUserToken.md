# GetUserToken

- ea: `0x180047c20`
- end: `0x180047d36`
- name: `GetUserToken`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180047b08`

## callees

- `0x18002bbf4`
- `0x180031708`
- `0x180047c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047ca7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047ca7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047d17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047d17`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047c5c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047cdd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047c5c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047cdd`

## string_xrefs

- `0x180047c8a`: `onecore\ds\security\fido\common\lib\fidosid.cpp`
- `0x180047d00`: `onecore\ds\security\fido\common\lib\fidosid.cpp`

## pseudocode

```c
__int64 __fastcall GetUserToken(__int64 a1, _QWORD *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  HLOCAL v6; // rdi
  int NonzeroLastError; // eax
  int ReturnLength; // [rsp+20h] [rbp-18h]
  int ReturnLengtha; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD uBytes; // [rsp+40h] [rbp+8h] BYREF
  int uBytes_4; // [rsp+44h] [rbp+Ch]

  uBytes_4 = HIDWORD(a1);
  uBytes = 0;
  *a2 = 0;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, &uBytes) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v5 = 35;
      goto LABEL_6;
    }
  }
  v6 = LocalAlloc(0x40u, uBytes);
  if ( !v6 )
  {
    v4 = -2147024882;
    v5 = 40;
LABEL_6:
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\fido\\common\\lib\\fidosid.cpp",
      (const char *)v4,
      ReturnLength);
    return v4;
  }
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, v6, uBytes, &uBytes) )
  {
    v4 = 0;
    *a2 = v6;
  }
  else
  {
    NonzeroLastError = _GetNonzeroLastError();
    v4 = NonzeroLastError;
    if ( NonzeroLastError > 0 )
      v4 = (unsigned __int16)NonzeroLastError | 0x80070000;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\ds\\security\\fido\\common\\lib\\fidosid.cpp",
      (const char *)v4,
      ReturnLengtha);
    LocalFree(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180047c20  mov     rax, rsp
0x180047c23  mov     [rax+10h], rbx
0x180047c27  mov     [rax+18h], rsi
0x180047c2b  mov     [rax+8], rcx
0x180047c2f  push    rdi
0x180047c30  sub     rsp, 30h
0x180047c34  xor     r9d, r9d; TokenInformationLength
0x180047c37  mov     dword ptr [rax+8], 0
0x180047c3e  mov     rsi, rdx
0x180047c41  mov     qword ptr [rdx], 0
0x180047c48  lea     rax, [rax+8]
0x180047c4c  xor     r8d, r8d; TokenInformation
0x180047c4f  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180047c54  lea     edx, [r9+1]; TokenInformationClass
0x180047c58  lea     rcx, [r9-6]; TokenHandle
0x180047c5c  call    cs:__imp_GetTokenInformation
0x180047c62  test    eax, eax
0x180047c64  jnz     short loc_180047C9E
0x180047c66  call    cs:__imp_GetLastError
0x180047c6c  mov     ebx, eax
0x180047c6e  cmp     eax, 7Ah ; 'z'
0x180047c71  jz      short loc_180047C9E
0x180047c73  test    eax, eax
0x180047c75  jle     short loc_180047C80
0x180047c77  movzx   ebx, ax
0x180047c7a  or      ebx, 80070000h
0x180047c80  mov     edx, 23h ; '#'; void *
0x180047c85  mov     rcx, [rsp+38h]; this
0x180047c8a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\fido\\common\\li"...
0x180047c91  mov     r9d, ebx; char *
0x180047c94  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180047c99  jmp     loc_180047D24
0x180047c9e  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x180047ca2  mov     ecx, 40h ; '@'; uFlags
0x180047ca7  call    cs:__imp_LocalAlloc
0x180047cad  mov     rdi, rax
0x180047cb0  test    rax, rax
0x180047cb3  jnz     short loc_180047CBF
0x180047cb5  mov     ebx, 8007000Eh
0x180047cba  lea     edx, [rax+28h]
0x180047cbd  jmp     short loc_180047C85
0x180047cbf  mov     r9d, dword ptr [rsp+38h+uBytes]; TokenInformationLength
0x180047cc4  lea     rax, [rsp+38h+uBytes]
0x180047cc9  mov     r8, rdi; TokenInformation
0x180047ccc  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180047cd1  mov     edx, 1; TokenInformationClass
0x180047cd6  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180047cdd  call    cs:__imp_GetTokenInformation
0x180047ce3  test    eax, eax
0x180047ce5  jnz     short loc_180047D1F
0x180047ce7  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x180047cec  mov     ebx, eax
0x180047cee  test    eax, eax
0x180047cf0  jle     short loc_180047CFB
0x180047cf2  movzx   ebx, ax
0x180047cf5  or      ebx, 80070000h
0x180047cfb  mov     rcx, [rsp+38h]; this
0x180047d00  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\fido\\common\\li"...
0x180047d07  mov     r9d, ebx; char *
0x180047d0a  mov     edx, 2Fh ; '/'; void *
0x180047d0f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180047d14  mov     rcx, rdi; hMem
0x180047d17  call    cs:__imp_LocalFree
0x180047d1d  jmp     short loc_180047D24
0x180047d1f  xor     ebx, ebx
0x180047d21  mov     [rsi], rdi
0x180047d24  mov     rsi, [rsp+38h+arg_10]
0x180047d29  mov     eax, ebx
0x180047d2b  mov     rbx, [rsp+38h+arg_8]
0x180047d30  add     rsp, 30h
0x180047d34  pop     rdi
0x180047d35  retn
```
