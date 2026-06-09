# Microsoft::CoreUI::Support::EventWaiter::DoWaitWithThread(uint,Microsoft::CoreUI::Support::Win32Handle)

- ea: `0x18008b904`
- end: `0x18008b9fb`
- name: `?DoWaitWithThread@EventWaiter@Support@CoreUI@Microsoft@@CAXIUWin32Handle@234@@Z`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18008b870`

## callees

- `0x1800067f0`
- `0x180007d80`
- `0x180009750`
- `0x18003950c`
- `0x180048a20`
- `0x18008b904`
- `0x1800a236c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18008b99e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18008b99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b933`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18008b920`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18008b920`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008b969`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008b969`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b9e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b9e5`

## pseudocode

```c
BOOL __fastcall Microsoft::CoreUI::Support::EventWaiter::DoWaitWithThread(DWORD a1, void *a2)
{
  HANDLE v3; // rax
  void *v4; // rsi
  signed int LastError; // eax
  _QWORD *Value; // rdi
  __int64 v7; // rdx
  DWORD v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  Cn::Engine::Lock *v11; // rcx
  HANDLE Handles[4]; // [rsp+38h] [rbp-20h] BYREF

  v3 = OpenThread(0x100000u, 0, a1);
  v4 = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CFlat::Abandonment::FailWithHR(LastError, 0, 0);
  }
  Handles[0] = a2;
  Handles[1] = v3;
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  Value[2] = 0;
  CFlat::EntryExit::OnBeginCallToNative(Value);
  v8 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
  v11 = (Cn::Engine::Lock *)Value[11];
  if ( v11 )
  {
    Cn::Engine::Lock::Enter(v11);
    Cn::Context::SetCurrentContext((struct Cn::Context *)Value);
  }
  Value[2] = 0;
  if ( v8 >= 2 )
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
      v11,
      v7,
      v9,
      v10);
  return CloseHandle(v4);
}

```

## disassembly

```asm
0x18008b904  mov     [rsp+arg_0], rbx
0x18008b909  mov     [rsp+arg_8], rsi
0x18008b90e  push    rdi
0x18008b90f  sub     rsp, 50h
0x18008b913  mov     rbx, rdx
0x18008b916  mov     r8d, ecx; dwThreadId
0x18008b919  xor     edx, edx; bInheritHandle
0x18008b91b  mov     ecx, 100000h; dwDesiredAccess
0x18008b920  call    cs:__imp_OpenThread
0x18008b926  mov     rsi, rax
0x18008b929  mov     [rsp+58h+arg_18], rax
0x18008b92e  test    rax, rax
0x18008b931  jnz     short loc_18008B952
0x18008b933  call    cs:__imp_GetLastError
0x18008b939  test    eax, eax
0x18008b93b  jle     short loc_18008B945
0x18008b93d  movzx   eax, ax
0x18008b940  or      eax, 80070000h
0x18008b945  xor     r8d, r8d; int
0x18008b948  xor     edx, edx; void *
0x18008b94a  mov     ecx, eax; int
0x18008b94c  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x18008b952  mov     [rsp+58h+Handles], rbx
0x18008b957  mov     [rsp+58h+var_18], rax
0x18008b95c  or      ebx, 0FFFFFFFFh
0x18008b95f  mov     [rsp+58h+var_28], ebx
0x18008b963  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18008b969  call    cs:__imp_TlsGetValue
0x18008b96f  mov     rdi, rax
0x18008b972  mov     [rsp+58h+arg_10], rax
0x18008b977  mov     qword ptr [rax+10h], 0
0x18008b97f  mov     rcx, rax; void *
0x18008b982  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x18008b987  mov     [rsp+58h+bAlertable], 0; bAlertable
0x18008b98f  mov     r9d, ebx; dwMilliseconds
0x18008b992  xor     r8d, r8d; bWaitAll
0x18008b995  lea     rdx, [rsp+58h+Handles]; lpHandles
0x18008b99a  lea     ecx, [r8+2]; nCount
0x18008b99e  call    cs:__imp_WaitForMultipleObjectsEx
0x18008b9a4  mov     ebx, eax
0x18008b9a6  mov     [rsp+58h+var_28], eax
0x18008b9aa  mov     rcx, [rdi+58h]; this
0x18008b9ae  test    rcx, rcx
0x18008b9b1  jz      short loc_18008B9C0
0x18008b9b3  call    ?Enter@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Enter(void)
0x18008b9b8  mov     rcx, rdi; lpTlsValue
0x18008b9bb  call    ?SetCurrentContext@Context@Cn@@CAXPEAV12@@Z; Cn::Context::SetCurrentContext(Cn::Context *)
0x18008b9c0  mov     qword ptr [rdi+10h], 0
0x18008b9c8  jmp     short loc_18008B9D3
0x18008b9ca  mov     rsi, [rsp+58h+arg_18]
0x18008b9cf  mov     ebx, [rsp+58h+var_28]
0x18008b9d3  test    ebx, ebx
0x18008b9d5  jz      short loc_18008B9E2
0x18008b9d7  cmp     ebx, 1
0x18008b9da  jz      short loc_18008B9E2
0x18008b9dc  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x18008b9e2  mov     rcx, rsi; hObject
0x18008b9e5  call    cs:__imp_CloseHandle
0x18008b9eb  mov     rbx, [rsp+58h+arg_0]
0x18008b9f0  mov     rsi, [rsp+58h+arg_8]
0x18008b9f5  add     rsp, 50h
0x18008b9f9  pop     rdi
0x18008b9fa  retn
0x1800cc2e4  push    rbp
0x1800cc2e6  sub     rsp, 30h
0x1800cc2ea  mov     rbp, rdx
0x1800cc2ed  mov     rdx, [rbp+70h]; this
0x1800cc2f1  call    ?UnexpectedStructuredExceptionFilter@ExceptionHandling@CFlat@@SAHPEAU_EXCEPTION_POINTERS@@PEAX@Z; CFlat::ExceptionHandling::UnexpectedStructuredExceptionFilter(_EXCEPTION_POINTERS *,void *)
0x1800cc2f6  nop
0x1800cc2f7  add     rsp, 30h
0x1800cc2fb  pop     rbp
0x1800cc2fc  retn
```
