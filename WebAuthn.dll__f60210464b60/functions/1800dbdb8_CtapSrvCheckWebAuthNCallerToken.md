# _CtapSrvCheckWebAuthNCallerToken

- ea: `0x1800dbdb8`
- end: `0x1800dbee0`
- name: `_CtapSrvCheckWebAuthNCallerToken`
- size: `296`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001dfb8`

## callees

- `0x18002bbf4`
- `0x1800466ec`
- `0x1800dbdb8`
- `0x18013abf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800dbe83`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800dbe83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbeb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbeb6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800dbdf6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800dbdf6`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800dbe39`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800dbe39`

## string_xrefs

- `0x1800dbebf`: `_CtapSrvCheckWebAuthNCallerToken`
- `0x1800dbe62`: `AppContainerStringSid`

## pseudocode

```c
__int64 __fastcall CtapSrvCheckWebAuthNCallerToken(HANDLE TokenHandle)
{
  unsigned __int64 v1; // rdi
  unsigned int v3; // ebx
  const char *v4; // rsi
  wchar_t *v5; // rdx
  unsigned int NonzeroLastError; // eax
  __int64 i; // r14
  HLOCAL hMem; // [rsp+30h] [rbp-10h] BYREF
  char v10; // [rsp+78h] [rbp+38h] BYREF
  DWORD ReturnLength; // [rsp+80h] [rbp+40h] BYREF
  int TokenInformation; // [rsp+88h] [rbp+48h] BYREF

  v1 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  hMem = 0;
  if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) && ReturnLength == 4 )
  {
    v3 = 0;
    v4 = 0;
    if ( !TokenInformation )
      goto LABEL_19;
    while ( (unsigned int)v1 < 3 )
    {
      v5 = off_18014CE30[v1];
      v10 = 0;
      if ( !(unsigned int)CapabilityCheck(TokenHandle, v5, &v10) && v10 )
        goto LABEL_19;
      v1 = (unsigned int)(v1 + 1);
    }
    if ( (unsigned int)I_CryptGetTokenAppContainerStringSid(TokenHandle, (LPWSTR *)&hMem) )
    {
      v1 = (unsigned __int64)hMem;
      for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
      {
        if ( !(unsigned int)_o__wcsicmp(v1, off_18014CE20[i]) )
          goto LABEL_17;
      }
      v3 = 4252;
      v4 = "NoMatch";
      goto LABEL_17;
    }
    NonzeroLastError = _GetNonzeroLastError();
    v1 = (unsigned __int64)hMem;
    v4 = "AppContainerStringSid";
  }
  else
  {
    NonzeroLastError = _GetNonzeroLastError();
    v4 = "IsAppContainer";
  }
  v3 = NonzeroLastError;
LABEL_17:
  if ( v1 )
    LocalFree((HLOCAL)v1);
LABEL_19:
  CtapSrvLogError(v3, "_CtapSrvCheckWebAuthNCallerToken", v4);
  return v3;
}

```

## disassembly

```asm
0x1800dbdb8  mov     [rsp-28h+arg_0], rbx
0x1800dbdbd  push    rbp
0x1800dbdbe  push    rsi
0x1800dbdbf  push    rdi
0x1800dbdc0  push    r12
0x1800dbdc2  push    r14
0x1800dbdc4  mov     rbp, rsp
0x1800dbdc7  sub     rsp, 40h
0x1800dbdcb  xor     edi, edi
0x1800dbdcd  mov     [rbp+TokenInformation], 0
0x1800dbdd4  lea     rax, [rbp+arg_10]
0x1800dbdd8  mov     [rbp+arg_10], 0
0x1800dbddf  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800dbde3  mov     [rbp+hMem], rdi
0x1800dbde7  mov     r14, rcx
0x1800dbdea  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800dbdef  lea     r9d, [rdi+4]; TokenInformationLength
0x1800dbdf3  lea     edx, [rdi+1Dh]; TokenInformationClass
0x1800dbdf6  call    cs:__imp_GetTokenInformation
0x1800dbdfc  test    eax, eax
0x1800dbdfe  jz      loc_1800DBEA0
0x1800dbe04  cmp     [rbp+arg_10], 4
0x1800dbe08  jnz     loc_1800DBEA0
0x1800dbe0e  xor     ebx, ebx
0x1800dbe10  xor     esi, esi
0x1800dbe12  cmp     [rbp+TokenInformation], ebx
0x1800dbe15  jz      loc_1800DBEBC
0x1800dbe1b  lea     r12, __ImageBase
0x1800dbe22  mov     rcx, r14; TokenHandle
0x1800dbe25  cmp     edi, 3
0x1800dbe28  jnb     short loc_1800DBE4C
0x1800dbe2a  mov     rdx, ds:rva off_18014CE30[r12+rdi*8]; "windowsHelloCredentialAccess" ...
0x1800dbe32  lea     r8, [rbp+arg_8]
0x1800dbe36  mov     [rbp+arg_8], bl
0x1800dbe39  call    cs:__imp_CapabilityCheck
0x1800dbe3f  test    eax, eax
0x1800dbe41  jnz     short loc_1800DBE48
0x1800dbe43  cmp     [rbp+arg_8], bl
0x1800dbe46  jnz     short loc_1800DBEBC
0x1800dbe48  inc     edi
0x1800dbe4a  jmp     short loc_1800DBE22
0x1800dbe4c  lea     rdx, [rbp+hMem]
0x1800dbe50  call    I_CryptGetTokenAppContainerStringSid
0x1800dbe55  test    eax, eax
0x1800dbe57  jnz     short loc_1800DBE6B
0x1800dbe59  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800dbe5e  mov     rdi, [rbp+hMem]
0x1800dbe62  lea     rsi, aAppcontainerst; "AppContainerStringSid"
0x1800dbe69  jmp     short loc_1800DBEAC
0x1800dbe6b  mov     rdi, [rbp+hMem]
0x1800dbe6f  xor     r14d, r14d
0x1800dbe72  cmp     r14d, 2
0x1800dbe76  jnb     short loc_1800DBE92
0x1800dbe78  mov     rdx, ds:rva off_18014CE20[r12+r14*8]; "S-1-15-2-1910091885-1573563583-11049412"... ...
0x1800dbe80  mov     rcx, rdi
0x1800dbe83  call    cs:__imp__o__wcsicmp
0x1800dbe89  test    eax, eax
0x1800dbe8b  jz      short loc_1800DBEAE
0x1800dbe8d  inc     r14d
0x1800dbe90  jmp     short loc_1800DBE72
0x1800dbe92  mov     ebx, 109Ch
0x1800dbe97  lea     rsi, aNomatch; "NoMatch"
0x1800dbe9e  jmp     short loc_1800DBEAE
0x1800dbea0  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800dbea5  lea     rsi, aIsappcontainer; "IsAppContainer"
0x1800dbeac  mov     ebx, eax
0x1800dbeae  test    rdi, rdi
0x1800dbeb1  jz      short loc_1800DBEBC
0x1800dbeb3  mov     rcx, rdi; hMem
0x1800dbeb6  call    cs:__imp_LocalFree
0x1800dbebc  mov     r8, rsi
0x1800dbebf  lea     rdx, aCtapsrvcheckwe_0; "_CtapSrvCheckWebAuthNCallerToken"
0x1800dbec6  mov     ecx, ebx
0x1800dbec8  call    _CtapSrvLogError
0x1800dbecd  mov     eax, ebx
0x1800dbecf  mov     rbx, [rsp+40h+arg_0]
0x1800dbed4  add     rsp, 40h
0x1800dbed8  pop     r14
0x1800dbeda  pop     r12
0x1800dbedc  pop     rdi
0x1800dbedd  pop     rsi
0x1800dbede  pop     rbp
0x1800dbedf  retn
```
