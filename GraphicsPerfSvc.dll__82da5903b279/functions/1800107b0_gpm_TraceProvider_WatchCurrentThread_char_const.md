# gpm::TraceProvider::WatchCurrentThread(char const *)

- ea: `0x1800107b0`
- end: `0x180010842`
- name: `?WatchCurrentThread@TraceProvider@gpm@@SA?AVActivityThreadWatcher@wil@@PEBD@Z`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180010070`
- `0x180010880`
- `0x180011630`

## callees

- `0x180006f6c`
- `0x18000d7e0`
- `0x1800107b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001082b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001082b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall gpm::TraceProvider::WatchCurrentThread(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rbx
  _QWORD *Local; // rax

  v4 = wil::details::static_lazy<gpm::TraceProvider>::get(
         a1,
         _lambda_44e411d5a304c89b3d836c501e367609_::_lambda_invoker_cdecl_);
  *(_BYTE *)(a1 + 24) = 0;
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = a2;
  *(_QWORD *)(a1 + 16) = 0;
  v7 = (_QWORD *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = v4;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = a1;
  *(_BYTE *)(a1 + 72) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v5) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        v6,
                        v5);
    *v7 = Local;
    if ( Local )
    {
      *(_QWORD *)(a1 + 48) = *Local;
      *Local = v7;
      *(_DWORD *)(a1 + 56) = GetCurrentThreadId();
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800107b0  mov     [rsp+arg_0], rbx
0x1800107b5  push    rdi
0x1800107b6  sub     rsp, 20h
0x1800107ba  mov     rbx, rdx
0x1800107bd  mov     rdi, rcx
0x1800107c0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_44e411d5a304c89b3d836c501e367609_@@CA@XZ; _lambda_44e411d5a304c89b3d836c501e367609_::_lambda_invoker_cdecl_(void)
0x1800107c7  call    ?get@?$static_lazy@VTraceProvider@gpm@@@details@wil@@QEAAPEAVTraceProvider@gpm@@P6AXXZ@Z; wil::details::static_lazy<gpm::TraceProvider>::get(void (*)(void))
0x1800107cc  mov     byte ptr [rdi+18h], 0
0x1800107d0  mov     dword ptr [rdi], 0
0x1800107d6  mov     [rdi+8], rbx
0x1800107da  mov     qword ptr [rdi+10h], 0
0x1800107e2  lea     rbx, [rdi+20h]
0x1800107e6  mov     qword ptr [rbx], 0
0x1800107ed  mov     [rbx+8], rax
0x1800107f1  mov     qword ptr [rbx+10h], 0
0x1800107f9  mov     dword ptr [rbx+18h], 0
0x180010800  mov     [rbx+20h], rdi
0x180010804  mov     byte ptr [rbx+28h], 0
0x180010808  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180010810  jz      short loc_180010834
0x180010812  mov     dl, 1
0x180010814  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180010819  mov     [rbx], rax
0x18001081c  test    rax, rax
0x18001081f  jz      short loc_180010834
0x180010821  mov     rcx, [rax]
0x180010824  mov     [rbx+10h], rcx
0x180010828  mov     [rax], rbx
0x18001082b  call    cs:__imp_GetCurrentThreadId
0x180010831  mov     [rbx+18h], eax
0x180010834  mov     rax, rdi
0x180010837  mov     rbx, [rsp+28h+arg_0]
0x18001083c  add     rsp, 20h
0x180010840  pop     rdi
0x180010841  retn
```
