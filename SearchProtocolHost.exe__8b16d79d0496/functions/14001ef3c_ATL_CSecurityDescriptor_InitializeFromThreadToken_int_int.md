# ATL::CSecurityDescriptor::InitializeFromThreadToken(int,int)

- ea: `0x14001ef3c`
- end: `0x14001f07a`
- name: `?InitializeFromThreadToken@CSecurityDescriptor@ATL@@QEAAJHH@Z`
- size: `318`
- prototype: `__int64 __fastcall(ATL::CSecurityDescriptor *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003a8e8`

## callees

- `0x1400124cc`
- `0x14001de48`
- `0x14001ee64`
- `0x14001ef3c`
- `0x1400287f4`
- `0x14002896c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001f04a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001f053`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001f04a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001f053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001efab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001f00e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001efab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001f00e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001efdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001efdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001ef77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001ef77`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001ef8a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001ef8a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001efed`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001efed`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::InitializeFromThreadToken(ATL::CSecurityDescriptor *this)
{
  int TokenSids; // ebx
  void *v3; // rdi
  void *v4; // rsi
  HANDLE CurrentThread; // rax
  int v6; // r8d
  HANDLE CurrentProcess; // rax
  int v8; // r8d
  void *v10; // [rsp+20h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-8h] BYREF
  void *Block; // [rsp+68h] [rbp+38h] BYREF

  TokenSids = ATL::CSecurityDescriptor::Initialize(this);
  if ( TokenSids >= 0 )
  {
    v3 = 0;
    TokenHandle = 0;
    v4 = 0;
    Block = 0;
    v10 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      TokenSids = ATL::CSecurityDescriptor::GetTokenSids(TokenHandle, &Block, &v10);
      CloseHandle(TokenHandle);
      v3 = Block;
      v4 = v10;
    }
    else
    {
      TokenSids = ResultFromLastError();
    }
    if ( (_WORD)TokenSids == 1008 )
    {
      v3 = 0;
      TokenHandle = 0;
      v4 = 0;
      Block = 0;
      v10 = 0;
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        TokenSids = ATL::CSecurityDescriptor::GetTokenSids(TokenHandle, &Block, &v10);
        CloseHandle(TokenHandle);
        v3 = Block;
        v4 = v10;
      }
      else
      {
        TokenSids = ResultFromLastError();
      }
    }
    if ( TokenSids >= 0 )
    {
      TokenSids = ATL::CSecurityDescriptor::SetOwner(this, v3, v6);
      if ( TokenSids >= 0 )
        TokenSids = ATL::CSecurityDescriptor::SetGroup(this, v4, v8);
      free(v3);
      free(v4);
      if ( TokenSids < 0 )
        ATL::CSecurityDescriptor::Initialize(this);
    }
  }
  return (unsigned int)TokenSids;
}

```

## disassembly

```asm
0x14001ef3c  mov     [rsp-18h+arg_0], rbx
0x14001ef41  mov     [rsp-18h+arg_8], rsi
0x14001ef46  push    rbp
0x14001ef47  push    rdi
0x14001ef48  push    r14
0x14001ef4a  mov     rbp, rsp
0x14001ef4d  sub     rsp, 30h
0x14001ef51  mov     r14, rcx
0x14001ef54  call    ?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ; ATL::CSecurityDescriptor::Initialize(void)
0x14001ef59  mov     ebx, eax
0x14001ef5b  test    eax, eax
0x14001ef5d  js      loc_14001F065
0x14001ef63  xor     edi, edi
0x14001ef65  mov     [rbp+TokenHandle], 0
0x14001ef6d  xor     esi, esi
0x14001ef6f  mov     [rbp+Block], rdi
0x14001ef73  mov     [rbp+var_10], rsi
0x14001ef77  call    cs:__imp_GetCurrentThread
0x14001ef7d  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14001ef81  xor     r8d, r8d; OpenAsSelf
0x14001ef84  mov     rcx, rax; ThreadHandle
0x14001ef87  lea     edx, [rdi+8]; DesiredAccess
0x14001ef8a  call    cs:__imp_OpenThreadToken
0x14001ef90  test    eax, eax
0x14001ef92  jz      short loc_14001EFBB
0x14001ef94  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14001ef98  lea     r8, [rbp+var_10]; void **
0x14001ef9c  lea     rdx, [rbp+Block]; void **
0x14001efa0  call    ?GetTokenSids@CSecurityDescriptor@ATL@@SAJPEAXPEAPEAX1@Z; ATL::CSecurityDescriptor::GetTokenSids(void *,void * *,void * *)
0x14001efa5  mov     rcx, [rbp+TokenHandle]; hObject
0x14001efa9  mov     ebx, eax
0x14001efab  call    cs:__imp_CloseHandle
0x14001efb1  mov     rdi, [rbp+Block]
0x14001efb5  mov     rsi, [rbp+var_10]
0x14001efb9  jmp     short loc_14001EFC2
0x14001efbb  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14001efc0  mov     ebx, eax
0x14001efc2  cmp     bx, 3F0h
0x14001efc7  jnz     short loc_14001F025
0x14001efc9  xor     edi, edi
0x14001efcb  mov     [rbp+TokenHandle], 0
0x14001efd3  xor     esi, esi
0x14001efd5  mov     [rbp+Block], rdi
0x14001efd9  mov     [rbp+var_10], rsi
0x14001efdd  call    cs:__imp_GetCurrentProcess
0x14001efe3  mov     rcx, rax; ProcessHandle
0x14001efe6  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14001efea  lea     edx, [rdi+8]; DesiredAccess
0x14001efed  call    cs:__imp_OpenProcessToken
0x14001eff3  test    eax, eax
0x14001eff5  jz      short loc_14001F01E
0x14001eff7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14001effb  lea     r8, [rbp+var_10]; void **
0x14001efff  lea     rdx, [rbp+Block]; void **
0x14001f003  call    ?GetTokenSids@CSecurityDescriptor@ATL@@SAJPEAXPEAPEAX1@Z; ATL::CSecurityDescriptor::GetTokenSids(void *,void * *,void * *)
0x14001f008  mov     rcx, [rbp+TokenHandle]; hObject
0x14001f00c  mov     ebx, eax
0x14001f00e  call    cs:__imp_CloseHandle
0x14001f014  mov     rdi, [rbp+Block]
0x14001f018  mov     rsi, [rbp+var_10]
0x14001f01c  jmp     short loc_14001F025
0x14001f01e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14001f023  mov     ebx, eax
0x14001f025  test    ebx, ebx
0x14001f027  js      short loc_14001F065
0x14001f029  mov     rdx, rdi; void *
0x14001f02c  mov     rcx, r14; this
0x14001f02f  call    ?SetOwner@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z; ATL::CSecurityDescriptor::SetOwner(void *,int)
0x14001f034  mov     ebx, eax
0x14001f036  test    eax, eax
0x14001f038  js      short loc_14001F047
0x14001f03a  mov     rdx, rsi; void *
0x14001f03d  mov     rcx, r14; this
0x14001f040  call    ?SetGroup@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z; ATL::CSecurityDescriptor::SetGroup(void *,int)
0x14001f045  mov     ebx, eax
0x14001f047  mov     rcx, rdi; Block
0x14001f04a  call    cs:__imp_free
0x14001f050  mov     rcx, rsi; Block
0x14001f053  call    cs:__imp_free
0x14001f059  test    ebx, ebx
0x14001f05b  jns     short loc_14001F065
0x14001f05d  mov     rcx, r14; this
0x14001f060  call    ?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ; ATL::CSecurityDescriptor::Initialize(void)
0x14001f065  mov     rsi, [rsp+30h+arg_8]
0x14001f06a  mov     eax, ebx
0x14001f06c  mov     rbx, [rsp+30h+arg_0]
0x14001f071  add     rsp, 30h
0x14001f075  pop     r14
0x14001f077  pop     rdi
0x14001f078  pop     rbp
0x14001f079  retn
```
