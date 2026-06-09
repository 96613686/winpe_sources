# ATL::CSecurityDescriptor::InitializeFromThreadToken(int,int)

- ea: `0x1400218d0`
- end: `0x140021a0e`
- name: `?InitializeFromThreadToken@CSecurityDescriptor@ATL@@QEAAJHH@Z`
- size: `318`
- prototype: `__int64 __fastcall(ATL::CSecurityDescriptor *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002753c`

## callees

- `0x14001d4e8`
- `0x140020ff8`
- `0x1400217f8`
- `0x1400218d0`
- `0x140023e90`
- `0x140023f30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400219de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400219e7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400219de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400219e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14002191e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14002191e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14002190b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14002190b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140021971`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140021971`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140021981`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140021981`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002193f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400219a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002193f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400219a2`

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
0x1400218d0  mov     [rsp-18h+arg_0], rbx
0x1400218d5  mov     [rsp-18h+arg_8], rsi
0x1400218da  push    rbp
0x1400218db  push    rdi
0x1400218dc  push    r14
0x1400218de  mov     rbp, rsp
0x1400218e1  sub     rsp, 30h
0x1400218e5  mov     r14, rcx
0x1400218e8  call    ?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ; ATL::CSecurityDescriptor::Initialize(void)
0x1400218ed  mov     ebx, eax
0x1400218ef  test    eax, eax
0x1400218f1  js      loc_1400219F9
0x1400218f7  xor     edi, edi
0x1400218f9  mov     [rbp+TokenHandle], 0
0x140021901  xor     esi, esi
0x140021903  mov     [rbp+Block], rdi
0x140021907  mov     [rbp+var_10], rsi
0x14002190b  call    cs:__imp_GetCurrentThread
0x140021911  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140021915  xor     r8d, r8d; OpenAsSelf
0x140021918  mov     rcx, rax; ThreadHandle
0x14002191b  lea     edx, [rdi+8]; DesiredAccess
0x14002191e  call    cs:__imp_OpenThreadToken
0x140021924  test    eax, eax
0x140021926  jz      short loc_14002194F
0x140021928  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14002192c  lea     r8, [rbp+var_10]; void **
0x140021930  lea     rdx, [rbp+Block]; void **
0x140021934  call    ?GetTokenSids@CSecurityDescriptor@ATL@@SAJPEAXPEAPEAX1@Z; ATL::CSecurityDescriptor::GetTokenSids(void *,void * *,void * *)
0x140021939  mov     rcx, [rbp+TokenHandle]; hObject
0x14002193d  mov     ebx, eax
0x14002193f  call    cs:__imp_CloseHandle
0x140021945  mov     rdi, [rbp+Block]
0x140021949  mov     rsi, [rbp+var_10]
0x14002194d  jmp     short loc_140021956
0x14002194f  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140021954  mov     ebx, eax
0x140021956  cmp     bx, 3F0h
0x14002195b  jnz     short loc_1400219B9
0x14002195d  xor     edi, edi
0x14002195f  mov     [rbp+TokenHandle], 0
0x140021967  xor     esi, esi
0x140021969  mov     [rbp+Block], rdi
0x14002196d  mov     [rbp+var_10], rsi
0x140021971  call    cs:__imp_GetCurrentProcess
0x140021977  mov     rcx, rax; ProcessHandle
0x14002197a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14002197e  lea     edx, [rdi+8]; DesiredAccess
0x140021981  call    cs:__imp_OpenProcessToken
0x140021987  test    eax, eax
0x140021989  jz      short loc_1400219B2
0x14002198b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14002198f  lea     r8, [rbp+var_10]; void **
0x140021993  lea     rdx, [rbp+Block]; void **
0x140021997  call    ?GetTokenSids@CSecurityDescriptor@ATL@@SAJPEAXPEAPEAX1@Z; ATL::CSecurityDescriptor::GetTokenSids(void *,void * *,void * *)
0x14002199c  mov     rcx, [rbp+TokenHandle]; hObject
0x1400219a0  mov     ebx, eax
0x1400219a2  call    cs:__imp_CloseHandle
0x1400219a8  mov     rdi, [rbp+Block]
0x1400219ac  mov     rsi, [rbp+var_10]
0x1400219b0  jmp     short loc_1400219B9
0x1400219b2  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400219b7  mov     ebx, eax
0x1400219b9  test    ebx, ebx
0x1400219bb  js      short loc_1400219F9
0x1400219bd  mov     rdx, rdi; void *
0x1400219c0  mov     rcx, r14; this
0x1400219c3  call    ?SetOwner@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z; ATL::CSecurityDescriptor::SetOwner(void *,int)
0x1400219c8  mov     ebx, eax
0x1400219ca  test    eax, eax
0x1400219cc  js      short loc_1400219DB
0x1400219ce  mov     rdx, rsi; void *
0x1400219d1  mov     rcx, r14; this
0x1400219d4  call    ?SetGroup@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z; ATL::CSecurityDescriptor::SetGroup(void *,int)
0x1400219d9  mov     ebx, eax
0x1400219db  mov     rcx, rdi; Block
0x1400219de  call    cs:__imp_free
0x1400219e4  mov     rcx, rsi; Block
0x1400219e7  call    cs:__imp_free
0x1400219ed  test    ebx, ebx
0x1400219ef  jns     short loc_1400219F9
0x1400219f1  mov     rcx, r14; this
0x1400219f4  call    ?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ; ATL::CSecurityDescriptor::Initialize(void)
0x1400219f9  mov     rsi, [rsp+30h+arg_8]
0x1400219fe  mov     eax, ebx
0x140021a00  mov     rbx, [rsp+30h+arg_0]
0x140021a05  add     rsp, 30h
0x140021a09  pop     r14
0x140021a0b  pop     rdi
0x140021a0c  pop     rbp
0x140021a0d  retn
```
