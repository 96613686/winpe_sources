# ThreadPoolWorkCallback::ThreadPoolWorkCallback(std::function<void (void)> &&,_TP_CALLBACK_ENVIRON_V3 *)

- ea: `0x18005d2e8`
- end: `0x18005d3f1`
- name: `??0ThreadPoolWorkCallback@@QEAA@$$QEAV?$function@$$A6AXXZ@std@@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z`
- size: `265`
- prototype: `_QWORD *__fastcall(_QWORD *pv, __int64, struct _TP_CALLBACK_ENVIRON_V3 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18004fae0`

## callees

- `0x180011318`
- `0x18005cff4`
- `0x18005d2e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d372`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d393`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d393`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005d382`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005d3b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005d382`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005d3b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005d38b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005d3c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005d38b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005d3c2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005d331`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005d331`

## string_xrefs

- `0x18005d3df`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\threadpoolworkcallback.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall ThreadPoolWorkCallback::ThreadPoolWorkCallback(
        _QWORD *pv,
        __int64 a2,
        struct _TP_CALLBACK_ENVIRON_V3 *a3)
{
  struct _TP_WORK **v5; // r14
  struct _TP_WORK *ThreadpoolWork; // rdi
  const char *v7; // r9
  struct _TP_WORK *v8; // rbp
  DWORD LastError; // ebx
  struct _TP_WORK *v11; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *pv = &ThreadPoolWorkCallback::`vftable';
  pv[8] = 0;
  v5 = (struct _TP_WORK **)(pv + 9);
  pv[9] = 0;
  *((_BYTE *)pv + 80) = 0;
  ThreadpoolWork = CreateThreadpoolWork(ThreadPoolWorkCallback::_OnWorkCallback, pv, a3);
  v11 = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\threadpoolworkcallback.cpp",
      v7);
  std::function<void (void)>::operator=(pv + 1, a2);
  if ( v5 != &v11 )
  {
    v8 = *v5;
    if ( *v5 )
    {
      LastError = GetLastError();
      WaitForThreadpoolWorkCallbacks(v8, 1);
      CloseThreadpoolWork(v8);
      SetLastError(LastError);
    }
    *v5 = ThreadpoolWork;
    v11 = 0;
    ThreadpoolWork = 0;
  }
  *((_BYTE *)pv + 80) = 0;
  if ( ThreadpoolWork )
  {
    WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 1);
    CloseThreadpoolWork(ThreadpoolWork);
  }
  return pv;
}

```

## disassembly

```asm
0x18005d2e8  mov     [rsp+arg_8], rbx
0x18005d2ed  mov     [rsp+arg_10], rbp
0x18005d2f2  mov     [rsp+arg_0], rcx
0x18005d2f7  push    rsi
0x18005d2f8  push    rdi
0x18005d2f9  push    r14
0x18005d2fb  sub     rsp, 30h
0x18005d2ff  mov     rbp, rdx
0x18005d302  mov     rsi, rcx
0x18005d305  lea     rax, ??_7ThreadPoolWorkCallback@@6B@; const ThreadPoolWorkCallback::`vftable'
0x18005d30c  mov     [rcx], rax
0x18005d30f  mov     qword ptr [rcx+40h], 0
0x18005d317  lea     r14, [rcx+48h]
0x18005d31b  mov     qword ptr [r14], 0
0x18005d322  xor     eax, eax
0x18005d324  mov     [rcx+50h], al
0x18005d327  mov     rdx, rcx; pv
0x18005d32a  lea     rcx, ?_OnWorkCallback@ThreadPoolWorkCallback@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18005d331  call    cs:__imp_CreateThreadpoolWork
0x18005d337  mov     rdi, rax
0x18005d33a  mov     [rsp+48h+var_28], rax
0x18005d33f  xor     eax, eax
0x18005d341  test    rdi, rdi
0x18005d344  setnz   al
0x18005d347  mov     rcx, [rsp+48h]; this
0x18005d34c  test    eax, eax
0x18005d34e  jz      loc_18005D3DF
0x18005d354  mov     rdx, rbp
0x18005d357  lea     rcx, [rsi+8]
0x18005d35b  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18005d360  lea     rax, [rsp+48h+var_28]
0x18005d365  cmp     r14, rax
0x18005d368  jz      short loc_18005D3A7
0x18005d36a  mov     rbp, [r14]
0x18005d36d  test    rbp, rbp
0x18005d370  jz      short loc_18005D399
0x18005d372  call    cs:__imp_GetLastError
0x18005d378  mov     ebx, eax
0x18005d37a  mov     edx, 1; fCancelPendingCallbacks
0x18005d37f  mov     rcx, rbp; pwk
0x18005d382  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18005d388  mov     rcx, rbp; pwk
0x18005d38b  call    cs:__imp_CloseThreadpoolWork
0x18005d391  mov     ecx, ebx; dwErrCode
0x18005d393  call    cs:__imp_SetLastError
0x18005d399  mov     [r14], rdi
0x18005d39c  mov     [rsp+48h+var_28], 0
0x18005d3a5  xor     edi, edi
0x18005d3a7  xor     eax, eax
0x18005d3a9  xchg    al, [rsi+50h]
0x18005d3ac  test    rdi, rdi
0x18005d3af  jz      short loc_18005D3C9
0x18005d3b1  mov     edx, 1; fCancelPendingCallbacks
0x18005d3b6  mov     rcx, rdi; pwk
0x18005d3b9  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18005d3bf  mov     rcx, rdi; pwk
0x18005d3c2  call    cs:__imp_CloseThreadpoolWork
0x18005d3c8  nop
0x18005d3c9  mov     rax, rsi
0x18005d3cc  mov     rbx, [rsp+48h+arg_8]
0x18005d3d1  mov     rbp, [rsp+48h+arg_10]
0x18005d3d6  add     rsp, 30h
0x18005d3da  pop     r14
0x18005d3dc  pop     rdi
0x18005d3dd  pop     rsi
0x18005d3de  retn
0x18005d3df  lea     r8, aOnecoreBaseLan_25; "onecore\\base\\languageoverlay\\service"...
0x18005d3e6  mov     edx, 39h ; '9'; void *
0x18005d3eb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
