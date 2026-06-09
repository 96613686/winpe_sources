# CTabletEventSink::SetCollector(ATL::CComObject<CInkCollector> *)

- ea: `0x1800ae918`
- end: `0x1800aea58`
- name: `?SetCollector@CTabletEventSink@@QEAAXPEAV?$CComObject@VCInkCollector@@@ATL@@@Z`
- size: `320`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ab9e0`
- `0x1800b3bd0`
- `0x1800da308`
- `0x1800e3354`
- `0x1800e8538`
- `0x1800f4624`

## callees

- `0x180001c20`
- `0x1800ae918`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ae9fd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800aea2a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ae9fd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800aea2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aea51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ae983`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ae983`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ae99f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ae99f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aea33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aea33`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800ae995`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800ae995`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ae9a8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ae9a8`
- `api-ms-win-core-com-l1-1-0!CoGetCancelObject` at `0x1800ae9ce`
- `api-ms-win-core-com-l1-1-0!CoGetCancelObject` at `0x1800ae9ce`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800ae962`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800aea1b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800ae962`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800aea1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall CTabletEventSink::SetCollector(__int64 a1, __int64 a2)
{
  HANDLE *v4; // r14
  HANDLE *v5; // rsi
  HANDLE CurrentThread; // rbx
  DWORD dwindex; // [rsp+60h] [rbp+8h] BYREF
  void *ppUnk; // [rsp+68h] [rbp+10h] BYREF
  __int64 v10; // [rsp+70h] [rbp+18h]

  v10 = (a1 + 72) & -(__int64)(a1 != 0);
  dwindex = 0;
  v4 = (HANDLE *)(v10 + 8);
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)(v10 + 8), &dwindex);
  if ( !a2 )
  {
    v5 = (HANDLE *)(a1 + 120);
    if ( *(_QWORD *)(a1 + 120) )
    {
      dwindex = 0;
      if ( GetCurrentThreadId() == *(_DWORD *)(a1 + 136) )
      {
        SetEvent(*(HANDLE *)(a1 + 152));
      }
      else
      {
        if ( CoImpersonateClient() >= 0 )
        {
          CurrentThread = GetCurrentThread();
          CoRevertToSelf();
          if ( CurrentThread == *(HANDLE *)(a1 + 128) )
          {
            ppUnk = 0;
            if ( CoGetCancelObject(*(_DWORD *)(a1 + 136), &IID_ICancelMethodCalls, &ppUnk) >= 0 )
              (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppUnk + 24LL))(ppUnk, 0);
            ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&ppUnk);
          }
        }
        SetEvent(*(HANDLE *)(a1 + 152));
        CoWaitForMultipleHandles(0, 0xEA60u, 1u, (LPHANDLE)(a1 + 120), &dwindex);
      }
      CloseHandle(*v5);
      *v5 = 0;
    }
  }
  *(_QWORD *)(a1 + 96) = a2;
  return ReleaseMutex(*v4);
}

```

## disassembly

```asm
0x1800ae918  push    rbx
0x1800ae91a  push    rbp
0x1800ae91b  push    rsi
0x1800ae91c  push    rdi
0x1800ae91d  push    r14
0x1800ae91f  sub     rsp, 30h
0x1800ae923  mov     rbp, rdx
0x1800ae926  mov     rdi, rcx
0x1800ae929  mov     rax, rcx
0x1800ae92c  lea     r8, [rcx+48h]
0x1800ae930  neg     rax
0x1800ae933  sbb     r9, r9
0x1800ae936  and     r9, r8
0x1800ae939  mov     [rsp+58h+arg_10], r9
0x1800ae93e  mov     [rsp+58h+dwindex], 0
0x1800ae946  lea     r14, [r9+8]
0x1800ae94a  lea     rax, [rsp+58h+dwindex]
0x1800ae94f  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800ae954  mov     r9, r14; pHandles
0x1800ae957  mov     r8d, 1; cHandles
0x1800ae95d  or      edx, 0FFFFFFFFh; dwTimeout
0x1800ae960  xor     ecx, ecx; dwFlags
0x1800ae962  call    cs:__imp_CoWaitForMultipleHandles
0x1800ae968  nop
0x1800ae969  test    rbp, rbp
0x1800ae96c  jnz     loc_1800AEA40
0x1800ae972  lea     rsi, [rdi+78h]
0x1800ae976  cmp     [rsi], rbp
0x1800ae979  jz      loc_1800AEA40
0x1800ae97f  mov     [rsp+58h+dwindex], ebp
0x1800ae983  call    cs:__imp_GetCurrentThreadId
0x1800ae989  cmp     eax, [rdi+88h]
0x1800ae98f  jz      loc_1800AEA23
0x1800ae995  call    cs:__imp_CoImpersonateClient
0x1800ae99b  test    eax, eax
0x1800ae99d  js      short loc_1800AE9F6
0x1800ae99f  call    cs:__imp_GetCurrentThread
0x1800ae9a5  mov     rbx, rax
0x1800ae9a8  call    cs:__imp_CoRevertToSelf
0x1800ae9ae  cmp     rbx, [rdi+80h]
0x1800ae9b5  jnz     short loc_1800AE9F6
0x1800ae9b7  mov     [rsp+58h+ppUnk], rbp
0x1800ae9bc  lea     r8, [rsp+58h+ppUnk]; ppUnk
0x1800ae9c1  lea     rdx, IID_ICancelMethodCalls; iid
0x1800ae9c8  mov     ecx, [rdi+88h]; dwThreadId
0x1800ae9ce  call    cs:__imp_CoGetCancelObject
0x1800ae9d4  test    eax, eax
0x1800ae9d6  js      short loc_1800AE9EC
0x1800ae9d8  mov     rcx, [rsp+58h+ppUnk]
0x1800ae9dd  mov     rax, [rcx]
0x1800ae9e0  xor     edx, edx
0x1800ae9e2  mov     rax, [rax+18h]
0x1800ae9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae9eb  nop
0x1800ae9ec  lea     rcx, [rsp+58h+ppUnk]; void *
0x1800ae9f1  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800ae9f6  mov     rcx, [rdi+98h]; hEvent
0x1800ae9fd  call    cs:__imp_SetEvent
0x1800aea03  lea     rax, [rsp+58h+dwindex]
0x1800aea08  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800aea0d  mov     r9, rsi; pHandles
0x1800aea10  mov     edx, 0EA60h; dwTimeout
0x1800aea15  xor     ecx, ecx; dwFlags
0x1800aea17  lea     r8d, [rcx+1]; cHandles
0x1800aea1b  call    cs:__imp_CoWaitForMultipleHandles
0x1800aea21  jmp     short loc_1800AEA30
0x1800aea23  mov     rcx, [rdi+98h]; hEvent
0x1800aea2a  call    cs:__imp_SetEvent
0x1800aea30  mov     rcx, [rsi]; hObject
0x1800aea33  call    cs:__imp_CloseHandle
0x1800aea39  mov     qword ptr [rsi], 0
0x1800aea40  mov     [rdi+60h], rbp
0x1800aea44  mov     rcx, [r14]
0x1800aea47  add     rsp, 30h
0x1800aea4b  pop     r14
0x1800aea4d  pop     rdi
0x1800aea4e  pop     rsi
0x1800aea4f  pop     rbp
0x1800aea50  pop     rbx
0x1800aea51  jmp     cs:__imp_ReleaseMutex
```
