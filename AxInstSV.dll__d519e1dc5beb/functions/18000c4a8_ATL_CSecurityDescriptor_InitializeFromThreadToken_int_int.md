# ATL::CSecurityDescriptor::InitializeFromThreadToken(int,int)

- ea: `0x18000c4a8`
- end: `0x18000c5e6`
- name: `?InitializeFromThreadToken@CSecurityDescriptor@ATL@@QEAAJHH@Z`
- size: `318`
- prototype: `__int64 __fastcall(ATL::CSecurityDescriptor *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c5ec`

## callees

- `0x180009df4`
- `0x18000b8c4`
- `0x18000c3d8`
- `0x18000c4a8`
- `0x18000f93c`
- `0x18000fab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c5b6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c5bf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c5b6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c5bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c517`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c57a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c517`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c57a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c549`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c549`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c4e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c4e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c4f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c4f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c559`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c559`

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
      TokenSids = ATL::AtlHresultFromLastError();
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
        TokenSids = ATL::AtlHresultFromLastError();
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
0x18000c4a8  mov     [rsp-18h+arg_0], rbx
0x18000c4ad  mov     [rsp-18h+arg_8], rsi
0x18000c4b2  push    rbp
0x18000c4b3  push    rdi
0x18000c4b4  push    r14
0x18000c4b6  mov     rbp, rsp
0x18000c4b9  sub     rsp, 30h
0x18000c4bd  mov     r14, rcx
0x18000c4c0  call    ?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ; ATL::CSecurityDescriptor::Initialize(void)
0x18000c4c5  mov     ebx, eax
0x18000c4c7  test    eax, eax
0x18000c4c9  js      loc_18000C5D1
0x18000c4cf  xor     edi, edi
0x18000c4d1  mov     [rbp+TokenHandle], 0
0x18000c4d9  xor     esi, esi
0x18000c4db  mov     [rbp+Block], rdi
0x18000c4df  mov     [rbp+var_10], rsi
0x18000c4e3  call    cs:__imp_GetCurrentThread
0x18000c4e9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000c4ed  xor     r8d, r8d; OpenAsSelf
0x18000c4f0  mov     rcx, rax; ThreadHandle
0x18000c4f3  lea     edx, [rdi+8]; DesiredAccess
0x18000c4f6  call    cs:__imp_OpenThreadToken
0x18000c4fc  test    eax, eax
0x18000c4fe  jz      short loc_18000C527
0x18000c500  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000c504  lea     r8, [rbp+var_10]; void **
0x18000c508  lea     rdx, [rbp+Block]; void **
0x18000c50c  call    ?GetTokenSids@CSecurityDescriptor@ATL@@SAJPEAXPEAPEAX1@Z; ATL::CSecurityDescriptor::GetTokenSids(void *,void * *,void * *)
0x18000c511  mov     rcx, [rbp+TokenHandle]; hObject
0x18000c515  mov     ebx, eax
0x18000c517  call    cs:__imp_CloseHandle
0x18000c51d  mov     rdi, [rbp+Block]
0x18000c521  mov     rsi, [rbp+var_10]
0x18000c525  jmp     short loc_18000C52E
0x18000c527  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c52c  mov     ebx, eax
0x18000c52e  cmp     bx, 3F0h
0x18000c533  jnz     short loc_18000C591
0x18000c535  xor     edi, edi
0x18000c537  mov     [rbp+TokenHandle], 0
0x18000c53f  xor     esi, esi
0x18000c541  mov     [rbp+Block], rdi
0x18000c545  mov     [rbp+var_10], rsi
0x18000c549  call    cs:__imp_GetCurrentProcess
0x18000c54f  mov     rcx, rax; ProcessHandle
0x18000c552  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000c556  lea     edx, [rdi+8]; DesiredAccess
0x18000c559  call    cs:__imp_OpenProcessToken
0x18000c55f  test    eax, eax
0x18000c561  jz      short loc_18000C58A
0x18000c563  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000c567  lea     r8, [rbp+var_10]; void **
0x18000c56b  lea     rdx, [rbp+Block]; void **
0x18000c56f  call    ?GetTokenSids@CSecurityDescriptor@ATL@@SAJPEAXPEAPEAX1@Z; ATL::CSecurityDescriptor::GetTokenSids(void *,void * *,void * *)
0x18000c574  mov     rcx, [rbp+TokenHandle]; hObject
0x18000c578  mov     ebx, eax
0x18000c57a  call    cs:__imp_CloseHandle
0x18000c580  mov     rdi, [rbp+Block]
0x18000c584  mov     rsi, [rbp+var_10]
0x18000c588  jmp     short loc_18000C591
0x18000c58a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c58f  mov     ebx, eax
0x18000c591  test    ebx, ebx
0x18000c593  js      short loc_18000C5D1
0x18000c595  mov     rdx, rdi; void *
0x18000c598  mov     rcx, r14; this
0x18000c59b  call    ?SetOwner@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z; ATL::CSecurityDescriptor::SetOwner(void *,int)
0x18000c5a0  mov     ebx, eax
0x18000c5a2  test    eax, eax
0x18000c5a4  js      short loc_18000C5B3
0x18000c5a6  mov     rdx, rsi; void *
0x18000c5a9  mov     rcx, r14; this
0x18000c5ac  call    ?SetGroup@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z; ATL::CSecurityDescriptor::SetGroup(void *,int)
0x18000c5b1  mov     ebx, eax
0x18000c5b3  mov     rcx, rdi; Block
0x18000c5b6  call    cs:__imp_free
0x18000c5bc  mov     rcx, rsi; Block
0x18000c5bf  call    cs:__imp_free
0x18000c5c5  test    ebx, ebx
0x18000c5c7  jns     short loc_18000C5D1
0x18000c5c9  mov     rcx, r14; this
0x18000c5cc  call    ?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ; ATL::CSecurityDescriptor::Initialize(void)
0x18000c5d1  mov     rsi, [rsp+30h+arg_8]
0x18000c5d6  mov     eax, ebx
0x18000c5d8  mov     rbx, [rsp+30h+arg_0]
0x18000c5dd  add     rsp, 30h
0x18000c5e1  pop     r14
0x18000c5e3  pop     rdi
0x18000c5e4  pop     rbp
0x18000c5e5  retn
```
