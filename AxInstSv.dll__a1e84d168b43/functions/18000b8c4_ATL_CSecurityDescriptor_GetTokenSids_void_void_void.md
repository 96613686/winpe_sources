# ATL::CSecurityDescriptor::GetTokenSids(void *,void * *,void * *)

- ea: `0x18000b8c4`
- end: `0x18000ba6b`
- name: `?GetTokenSids@CSecurityDescriptor@ATL@@SAJPEAXPEAPEAX1@Z`
- size: `423`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c4a8`

## callees

- `0x180009df4`
- `0x180009e18`
- `0x18000a104`
- `0x18000b8c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b973`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ba10`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ba34`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ba49`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b973`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ba10`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ba34`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ba49`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b92d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b9ca`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b92d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b91e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b91e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9bb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b918`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b952`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b9b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b9ef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b918`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b952`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b9b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b9ef`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::GetTokenSids(HANDLE TokenHandle, void **a2, void **a3)
{
  int v3; // ebx
  DWORD LastError; // eax
  void **v8; // r14
  int v9; // eax
  DWORD v10; // eax
  void **v11; // r14
  int v12; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  TokenInformationLength = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 )
    goto LABEL_24;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v8 = (void **)malloc(TokenInformationLength);
    if ( v8 )
    {
      v9 = GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength)
         ? ATL::CSecurityDescriptor::CloneSID(a2, *v8)
         : ATL::AtlHresultFromLastError();
      v3 = v9;
      free(v8);
    }
    else
    {
      v3 = -2147024882;
    }
  }
  else
  {
    v3 = ATL::AtlHresultFromWin32(LastError);
  }
  if ( v3 >= 0 )
  {
LABEL_24:
    if ( !a3 )
      return (unsigned int)v3;
    GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, &TokenInformationLength);
    v10 = GetLastError();
    if ( v10 == 122 )
    {
      v11 = (void **)malloc(TokenInformationLength);
      if ( v11 )
      {
        v12 = GetTokenInformation(TokenHandle, TokenPrimaryGroup, v11, TokenInformationLength, &TokenInformationLength)
            ? ATL::CSecurityDescriptor::CloneSID(a3, *v11)
            : ATL::AtlHresultFromLastError();
        v3 = v12;
        free(v11);
      }
      else
      {
        v3 = -2147024882;
      }
    }
    else
    {
      v3 = ATL::AtlHresultFromWin32(v10);
    }
    if ( v3 >= 0 )
      return (unsigned int)v3;
    if ( !a2 )
    {
LABEL_27:
      free(*a3);
      *a3 = 0;
      return (unsigned int)v3;
    }
  }
  free(*a2);
  *a2 = 0;
  if ( a3 )
    goto LABEL_27;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b8c4  mov     [rsp+arg_0], rbx
0x18000b8c9  mov     [rsp+arg_10], rbp
0x18000b8ce  push    rsi
0x18000b8cf  push    rdi
0x18000b8d0  push    r14
0x18000b8d2  sub     rsp, 30h
0x18000b8d6  xor     ebx, ebx
0x18000b8d8  mov     [rsp+48h+TokenInformationLength], 0
0x18000b8e0  mov     rdi, r8
0x18000b8e3  mov     rsi, rdx
0x18000b8e6  mov     rbp, rcx
0x18000b8e9  test    rdx, rdx
0x18000b8ec  jz      short loc_18000B8F1
0x18000b8ee  mov     [rdx], rbx
0x18000b8f1  test    rdi, rdi
0x18000b8f4  jz      short loc_18000B8F9
0x18000b8f6  mov     [r8], rbx
0x18000b8f9  test    rsi, rsi
0x18000b8fc  jz      loc_18000B993
0x18000b902  xor     r9d, r9d; TokenInformationLength
0x18000b905  lea     rax, [rsp+48h+TokenInformationLength]
0x18000b90a  xor     r8d, r8d; TokenInformation
0x18000b90d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000b912  lea     ebx, [r9+1]
0x18000b916  mov     edx, ebx; TokenInformationClass
0x18000b918  call    cs:__imp_GetTokenInformation
0x18000b91e  call    cs:__imp_GetLastError
0x18000b924  cmp     eax, 7Ah ; 'z'
0x18000b927  jnz     short loc_18000B982
0x18000b929  mov     ecx, [rsp+48h+TokenInformationLength]; Size
0x18000b92d  call    cs:__imp_malloc
0x18000b933  mov     r14, rax
0x18000b936  test    rax, rax
0x18000b939  jz      short loc_18000B97B
0x18000b93b  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000b940  lea     rax, [rsp+48h+TokenInformationLength]
0x18000b945  mov     r8, r14; TokenInformation
0x18000b948  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000b94d  mov     edx, ebx; TokenInformationClass
0x18000b94f  mov     rcx, rbp; TokenHandle
0x18000b952  call    cs:__imp_GetTokenInformation
0x18000b958  test    eax, eax
0x18000b95a  jz      short loc_18000B969
0x18000b95c  mov     rdx, [r14]; void *
0x18000b95f  mov     rcx, rsi; void **
0x18000b962  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x18000b967  jmp     short loc_18000B96E
0x18000b969  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000b96e  mov     rcx, r14; Block
0x18000b971  mov     ebx, eax
0x18000b973  call    cs:__imp_free
0x18000b979  jmp     short loc_18000B98B
0x18000b97b  mov     ebx, 8007000Eh
0x18000b980  jmp     short loc_18000B98B
0x18000b982  mov     ecx, eax; unsigned int
0x18000b984  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000b989  mov     ebx, eax
0x18000b98b  test    ebx, ebx
0x18000b98d  js      loc_18000BA31
0x18000b993  test    rdi, rdi
0x18000b996  jz      loc_18000BA56
0x18000b99c  xor     r9d, r9d; TokenInformationLength
0x18000b99f  lea     rax, [rsp+48h+TokenInformationLength]
0x18000b9a4  xor     r8d, r8d; TokenInformation
0x18000b9a7  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000b9ac  mov     rcx, rbp; TokenHandle
0x18000b9af  lea     ebx, [r9+5]
0x18000b9b3  mov     edx, ebx; TokenInformationClass
0x18000b9b5  call    cs:__imp_GetTokenInformation
0x18000b9bb  call    cs:__imp_GetLastError
0x18000b9c1  cmp     eax, 7Ah ; 'z'
0x18000b9c4  jnz     short loc_18000BA1F
0x18000b9c6  mov     ecx, [rsp+48h+TokenInformationLength]; Size
0x18000b9ca  call    cs:__imp_malloc
0x18000b9d0  mov     r14, rax
0x18000b9d3  test    rax, rax
0x18000b9d6  jz      short loc_18000BA18
0x18000b9d8  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000b9dd  lea     rax, [rsp+48h+TokenInformationLength]
0x18000b9e2  mov     r8, r14; TokenInformation
0x18000b9e5  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000b9ea  mov     edx, ebx; TokenInformationClass
0x18000b9ec  mov     rcx, rbp; TokenHandle
0x18000b9ef  call    cs:__imp_GetTokenInformation
0x18000b9f5  test    eax, eax
0x18000b9f7  jz      short loc_18000BA06
0x18000b9f9  mov     rdx, [r14]; void *
0x18000b9fc  mov     rcx, rdi; void **
0x18000b9ff  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x18000ba04  jmp     short loc_18000BA0B
0x18000ba06  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000ba0b  mov     rcx, r14; Block
0x18000ba0e  mov     ebx, eax
0x18000ba10  call    cs:__imp_free
0x18000ba16  jmp     short loc_18000BA28
0x18000ba18  mov     ebx, 8007000Eh
0x18000ba1d  jmp     short loc_18000BA28
0x18000ba1f  mov     ecx, eax; unsigned int
0x18000ba21  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000ba26  mov     ebx, eax
0x18000ba28  test    ebx, ebx
0x18000ba2a  jns     short loc_18000BA56
0x18000ba2c  test    rsi, rsi
0x18000ba2f  jz      short loc_18000BA46
0x18000ba31  mov     rcx, [rsi]; Block
0x18000ba34  call    cs:__imp_free
0x18000ba3a  mov     qword ptr [rsi], 0
0x18000ba41  test    rdi, rdi
0x18000ba44  jz      short loc_18000BA56
0x18000ba46  mov     rcx, [rdi]; Block
0x18000ba49  call    cs:__imp_free
0x18000ba4f  mov     qword ptr [rdi], 0
0x18000ba56  mov     rbp, [rsp+48h+arg_10]
0x18000ba5b  mov     eax, ebx
0x18000ba5d  mov     rbx, [rsp+48h+arg_0]
0x18000ba62  add     rsp, 30h
0x18000ba66  pop     r14
0x18000ba68  pop     rdi
0x18000ba69  pop     rsi
0x18000ba6a  retn
```
