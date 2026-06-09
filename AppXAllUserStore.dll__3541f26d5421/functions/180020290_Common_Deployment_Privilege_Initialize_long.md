# Common::Deployment::Privilege::Initialize(long)

- ea: `0x180020290`
- end: `0x1800203d8`
- name: `?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z`
- size: `328`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019b04`
- `0x18001ffd0`
- `0x18004a9a4`

## callees

- `0x180018248`
- `0x18001a604`
- `0x18001ed4c`
- `0x18001ff94`
- `0x180020290`
- `0x180020b04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800202f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800202f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020389`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800202eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002037f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800202eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002037f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800202d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002036a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800202d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002036a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020353`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020353`

## string_xrefs

- `0x18002031e`: `onecore\admin\appmodel\common\privilege.cpp`
- `0x180020398`: `onecore\admin\appmodel\common\privilege.cpp`

## pseudocode

```c
int __fastcall Common::Deployment::Privilege::Initialize(PHANDLE TokenHandle, int a2)
{
  void *v2; // rdi
  void *v4; // rsi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  int v7; // eax
  int v8; // edi
  void *v10; // rdi
  HANDLE v11; // rax
  unsigned int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v14; // [rsp+30h] [rbp+8h] BYREF

  v2 = *TokenHandle;
  v4 = (void *)a2;
  if ( (char *)*TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
    CloseHandle(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
  }
  *TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError == 1008 )
    {
      v7 = Common::ImpersonateSelf::Impersonate((Common::ImpersonateSelf *)(TokenHandle + 3));
      v8 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17,
          (unsigned int)"onecore\\admin\\appmodel\\common\\privilege.cpp",
          (const char *)(unsigned int)v7,
          v12);
        return v8;
      }
      v10 = *TokenHandle;
      if ( (char *)*TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        CloseHandle(v10);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      *TokenHandle = 0;
      v11 = GetCurrentThread();
      if ( OpenThreadToken(v11, 0x28u, 1, TokenHandle) )
        goto LABEL_13;
      LastError = GetLastError();
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1A,
               (unsigned int)"onecore\\admin\\appmodel\\common\\privilege.cpp",
               (const char *)LastError,
               v12);
  }
LABEL_13:
  TokenHandle[1] = v4;
  return 0;
}

```

## disassembly

```asm
0x180020290  mov     [rsp+arg_8], rbx
0x180020295  mov     [rsp+arg_10], rsi
0x18002029a  push    rdi; unsigned int
0x18002029b  sub     rsp, 20h
0x18002029f  mov     rdi, [rcx]
0x1800202a2  mov     rbx, rcx
0x1800202a5  movsxd  rsi, edx
0x1800202a8  lea     rax, [rdi-1]
0x1800202ac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800202b0  ja      short loc_1800202CF
0x1800202b2  lea     rcx, [rsp+28h+arg_0]; this
0x1800202b7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800202bc  mov     rcx, rdi; hObject
0x1800202bf  call    cs:__imp_CloseHandle
0x1800202c5  lea     rcx, [rsp+28h+arg_0]; this
0x1800202ca  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800202cf  mov     qword ptr [rbx], 0
0x1800202d6  call    cs:__imp_GetCurrentThread
0x1800202dc  mov     edx, 28h ; '('; DesiredAccess
0x1800202e1  mov     r9, rbx; TokenHandle
0x1800202e4  mov     rcx, rax; ThreadHandle
0x1800202e7  lea     r8d, [rdx-27h]; OpenAsSelf
0x1800202eb  call    cs:__imp_OpenThreadToken
0x1800202f1  test    eax, eax
0x1800202f3  jnz     loc_1800203AE
0x1800202f9  call    cs:__imp_GetLastError
0x1800202ff  cmp     eax, 3F0h
0x180020304  jnz     loc_18002038F
0x18002030a  lea     rcx, [rbx+18h]; this
0x18002030e  call    ?Impersonate@ImpersonateSelf@Common@@QEAAJXZ; Common::ImpersonateSelf::Impersonate(void)
0x180020313  mov     edi, eax
0x180020315  test    eax, eax
0x180020317  jns     short loc_180020339
0x180020319  mov     rcx, [rsp+28h]; this
0x18002031e  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\common\\privi"...
0x180020325  mov     r9d, eax; char *
0x180020328  mov     edx, 17h; void *
0x18002032d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020332  mov     eax, edi
0x180020334  jmp     loc_1800203C8
0x180020339  mov     rdi, [rbx]
0x18002033c  lea     rax, [rdi-1]
0x180020340  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020344  ja      short loc_180020363
0x180020346  lea     rcx, [rsp+28h+arg_0]; this
0x18002034b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180020350  mov     rcx, rdi; hObject
0x180020353  call    cs:__imp_CloseHandle
0x180020359  lea     rcx, [rsp+28h+arg_0]; this
0x18002035e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180020363  mov     qword ptr [rbx], 0
0x18002036a  call    cs:__imp_GetCurrentThread
0x180020370  mov     edx, 28h ; '('; DesiredAccess
0x180020375  mov     r9, rbx; TokenHandle
0x180020378  mov     rcx, rax; ThreadHandle
0x18002037b  lea     r8d, [rdx-27h]; OpenAsSelf
0x18002037f  call    cs:__imp_OpenThreadToken
0x180020385  test    eax, eax
0x180020387  jnz     short loc_1800203AE
0x180020389  call    cs:__imp_GetLastError
0x18002038f  test    eax, eax
0x180020391  jz      short loc_1800203AE
0x180020393  mov     rcx, [rsp+28h]; this
0x180020398  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\common\\privi"...
0x18002039f  mov     r9d, eax; char *
0x1800203a2  mov     edx, 1Ah; void *
0x1800203a7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800203ac  jmp     short loc_1800203C8
0x1800203ae  mov     rax, rsi
0x1800203b1  mov     dword ptr [rsp+28h+arg_0], eax
0x1800203b5  shr     rax, 20h
0x1800203b9  mov     dword ptr [rsp+28h+arg_0+4], eax
0x1800203bd  mov     rax, [rsp+28h+arg_0]
0x1800203c2  mov     [rbx+8], rax
0x1800203c6  xor     eax, eax
0x1800203c8  mov     rbx, [rsp+28h+arg_8]
0x1800203cd  mov     rsi, [rsp+28h+arg_10]
0x1800203d2  add     rsp, 20h
0x1800203d6  pop     rdi
0x1800203d7  retn
```
