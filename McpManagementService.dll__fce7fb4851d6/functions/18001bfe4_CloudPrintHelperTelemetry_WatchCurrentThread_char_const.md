# CloudPrintHelperTelemetry::WatchCurrentThread(char const *)

- ea: `0x18001bfe4`
- end: `0x18001c076`
- name: `?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x180014de4`
- `0x1800154fc`
- `0x180016b54`
- `0x180017144`
- `0x1800179e8`
- `0x180017b98`
- `0x180018f08`
- `0x18001bc2c`
- `0x18001ef30`
- `0x18001f118`
- `0x18001f554`
- `0x18001f77c`
- `0x18001f9a4`
- `0x1800203b0`
- `0x180020e9c`

## callees

- `0x18000966c`
- `0x18001bfe4`
- `0x18001e07c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c05f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c05f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudPrintHelperTelemetry::WatchCurrentThread(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rbx
  _QWORD *Local; // rax

  v4 = wil::details::static_lazy<CloudPrintHelperTelemetry>::get(
         a1,
         _lambda_d2014b196dcf28ad8e10995fa2e149c9_::_lambda_invoker_cdecl_);
  *(_BYTE *)(a1 + 24) = 0;
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = a2;
  *(_QWORD *)(a1 + 16) = 0;
  v6 = (_QWORD *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = v4;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = a1;
  *(_BYTE *)(a1 + 72) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(v5, 1);
    *v6 = Local;
    if ( Local )
    {
      *(_QWORD *)(a1 + 48) = *Local;
      *Local = v6;
      *(_DWORD *)(a1 + 56) = GetCurrentThreadId();
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001bfe4  mov     [rsp+arg_0], rbx
0x18001bfe9  push    rdi
0x18001bfea  sub     rsp, 20h
0x18001bfee  mov     rbx, rdx
0x18001bff1  mov     rdi, rcx
0x18001bff4  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d2014b196dcf28ad8e10995fa2e149c9_@@CA@XZ; _lambda_d2014b196dcf28ad8e10995fa2e149c9_::_lambda_invoker_cdecl_(void)
0x18001bffb  call    ?get@?$static_lazy@VCloudPrintHelperTelemetry@@@details@wil@@QEAAPEAVCloudPrintHelperTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CloudPrintHelperTelemetry>::get(void (*)(void))
0x18001c000  mov     byte ptr [rdi+18h], 0
0x18001c004  mov     dword ptr [rdi], 0
0x18001c00a  mov     [rdi+8], rbx
0x18001c00e  mov     qword ptr [rdi+10h], 0
0x18001c016  lea     rbx, [rdi+20h]
0x18001c01a  mov     qword ptr [rbx], 0
0x18001c021  mov     [rbx+8], rax
0x18001c025  mov     qword ptr [rbx+10h], 0
0x18001c02d  mov     dword ptr [rbx+18h], 0
0x18001c034  mov     [rbx+20h], rdi
0x18001c038  mov     byte ptr [rbx+28h], 0
0x18001c03c  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001c044  jz      short loc_18001C068
0x18001c046  mov     dl, 1
0x18001c048  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001c04d  mov     [rbx], rax
0x18001c050  test    rax, rax
0x18001c053  jz      short loc_18001C068
0x18001c055  mov     rcx, [rax]
0x18001c058  mov     [rbx+10h], rcx
0x18001c05c  mov     [rax], rbx
0x18001c05f  call    cs:__imp_GetCurrentThreadId
0x18001c065  mov     [rbx+18h], eax
0x18001c068  mov     rax, rdi
0x18001c06b  mov     rbx, [rsp+28h+arg_0]
0x18001c070  add     rsp, 20h
0x18001c074  pop     rdi
0x18001c075  retn
```
