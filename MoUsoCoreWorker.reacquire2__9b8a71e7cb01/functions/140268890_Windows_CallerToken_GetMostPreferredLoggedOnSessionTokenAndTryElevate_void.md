# Windows::CallerToken::GetMostPreferredLoggedOnSessionTokenAndTryElevate(void)

- ea: `0x140268890`
- end: `0x140268988`
- name: `?GetMostPreferredLoggedOnSessionTokenAndTryElevate@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `248`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1402a3ca0`
- `0x1402a5560`

## callees

- `0x140268574`
- `0x140268890`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14026895a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14026895a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140268947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140268947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140268952`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140268952`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1402688f6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140268925`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1402688f6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140268925`

## pseudocode

```c
WCHAR *__fastcall Windows::CallerToken::GetMostPreferredLoggedOnSessionTokenAndTryElevate(WCHAR *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  WCHAR *v4; // rbp
  void *v5; // rsi
  DWORD LastError; // ebx
  WCHAR *v8; // [rsp+38h] [rbp-20h] BYREF
  int TokenInformation; // [rsp+40h] [rbp-18h] BYREF
  DWORD ReturnLength; // [rsp+44h] [rbp-14h] BYREF

  v8 = a1;
  *(_QWORD *)a1 = 0;
  Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(a1);
  v2 = *(void **)a1;
  if ( (unsigned __int64)(*(_QWORD *)a1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    TokenInformation = 0;
    ReturnLength = 0;
    if ( GetTokenInformation(v2, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
    {
      if ( TokenInformation == 3 )
      {
        v3 = *(void **)a1;
        v8 = 0;
        if ( GetTokenInformation(v3, TokenLinkedToken, &v8, 8u, &ReturnLength) )
        {
          v4 = v8;
          if ( v8 )
          {
            v5 = *(void **)a1;
            if ( *(_QWORD *)a1 && v5 != (void *)-1LL )
            {
              LastError = GetLastError();
              CloseHandle(v5);
              SetLastError(LastError);
            }
            *(_QWORD *)a1 = v4;
          }
        }
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140268890  mov     [rsp+arg_8], rbx
0x140268895  mov     [rsp+arg_10], rbp
0x14026889a  mov     [rsp+arg_18], rsi
0x14026889f  push    rdi
0x1402688a0  sub     rsp, 50h
0x1402688a4  mov     rax, cs:__security_cookie
0x1402688ab  xor     rax, rsp
0x1402688ae  mov     [rsp+58h+var_10], rax
0x1402688b3  xor     eax, eax
0x1402688b5  mov     [rsp+58h+var_20], rcx
0x1402688ba  mov     [rcx], rax
0x1402688bd  mov     rdi, rcx
0x1402688c0  xor     ebx, ebx
0x1402688c2  call    ?GetMostPreferredLoggedOnSessionToken@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(void)
0x1402688c7  mov     rcx, [rdi]; TokenHandle
0x1402688ca  lea     rax, [rcx-1]
0x1402688ce  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1402688d2  ja      loc_140268963
0x1402688d8  lea     rax, [rsp+58h+var_14]
0x1402688dd  mov     [rsp+58h+TokenInformation], ebx
0x1402688e1  lea     r9d, [rbx+4]; TokenInformationLength
0x1402688e5  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1402688ea  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x1402688ef  mov     [rsp+58h+var_14], ebx
0x1402688f3  lea     edx, [rbx+12h]; TokenInformationClass
0x1402688f6  call    cs:__imp_GetTokenInformation
0x1402688fc  test    eax, eax
0x1402688fe  jz      short loc_140268963
0x140268900  cmp     [rsp+58h+TokenInformation], 3
0x140268905  jnz     short loc_140268963
0x140268907  mov     rcx, [rdi]; TokenHandle
0x14026890a  lea     rax, [rsp+58h+var_14]
0x14026890f  lea     r9d, [rbx+8]; TokenInformationLength
0x140268913  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140268918  lea     r8, [rsp+58h+var_20]; TokenInformation
0x14026891d  mov     [rsp+58h+var_20], rbx
0x140268922  lea     edx, [rbx+13h]; TokenInformationClass
0x140268925  call    cs:__imp_GetTokenInformation
0x14026892b  test    eax, eax
0x14026892d  jz      short loc_140268963
0x14026892f  mov     rbp, [rsp+58h+var_20]
0x140268934  test    rbp, rbp
0x140268937  jz      short loc_140268963
0x140268939  mov     rsi, [rdi]
0x14026893c  test    rsi, rsi
0x14026893f  jz      short loc_140268960
0x140268941  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140268945  jz      short loc_140268960
0x140268947  call    cs:__imp_GetLastError
0x14026894d  mov     rcx, rsi; hObject
0x140268950  mov     ebx, eax
0x140268952  call    cs:__imp_CloseHandle
0x140268958  mov     ecx, ebx; dwErrCode
0x14026895a  call    cs:__imp_SetLastError
0x140268960  mov     [rdi], rbp
0x140268963  mov     rax, rdi
0x140268966  mov     rcx, [rsp+58h+var_10]
0x14026896b  xor     rcx, rsp; StackCookie
0x14026896e  call    __security_check_cookie
0x140268973  mov     rbx, [rsp+58h+arg_8]
0x140268978  mov     rbp, [rsp+58h+arg_10]
0x14026897d  mov     rsi, [rsp+58h+arg_18]
0x140268982  add     rsp, 50h
0x140268986  pop     rdi
0x140268987  retn
```
