# FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)

- ea: `0x14000f8d0`
- end: `0x14000f962`
- name: `?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `108`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140009520`
- `0x1400095b0`
- `0x140009630`
- `0x1400096c0`
- `0x140009740`
- `0x1400097c0`
- `0x140009880`
- `0x140009900`
- `0x140009ad0`
- `0x140009b50`
- `0x140009bd0`
- `0x140009da0`
- `0x140009e20`
- `0x14000a060`
- `0x14000a0e0`
- `0x14000a180`
- `0x14000a5c0`
- `0x14000a640`
- `0x14000a8d0`
- `0x14000a960`
- `0x14000a9f0`
- `0x14000aaf0`
- `0x14000ab70`
- `0x14000ac20`
- `0x14000acb0`
- `0x14000afc0`
- `0x14000b0f0`
- `0x14000b220`
- `0x14000b350`
- `0x14000b7f0`
- `0x14000b870`
- `0x14000b8f0`
- `0x14000bad0`
- `0x14000bb80`
- `0x14000bea0`
- `0x14000c020`
- `0x14000c190`
- `0x14000c230`
- `0x14000c360`
- `0x14000c630`
- `0x14000c6c0`
- `0x14000c760`
- `0x14000c7f0`
- `0x14000c880`
- `0x14000c8f0`
- `0x14000ca80`
- `0x14000cb70`
- `0x14000cc70`
- `0x14000cd60`
- `0x14000cdd0`

## callees

- `0x140003fec`
- `0x14000742c`
- `0x14000f8d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f94b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f94b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FileDialogBrokerTraceLogging::WatchCurrentThread(__int64 a1, __int64 a2)
{
  __int64 *v4; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rbx
  _QWORD *Local; // rax

  v4 = wil::details::static_lazy<FileDialogBrokerTraceLogging>::get(
         a1,
         (void (__cdecl *)())_lambda_690474f5197746a9e0653436b7d8238b_::_lambda_invoker_cdecl_);
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
0x14000f8d0  mov     [rsp+arg_0], rbx
0x14000f8d5  push    rdi
0x14000f8d6  sub     rsp, 20h
0x14000f8da  mov     rbx, rdx
0x14000f8dd  mov     rdi, rcx
0x14000f8e0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_690474f5197746a9e0653436b7d8238b_@@CA@XZ; _lambda_690474f5197746a9e0653436b7d8238b_::_lambda_invoker_cdecl_(void)
0x14000f8e7  call    ?get@?$static_lazy@VFileDialogBrokerTraceLogging@@@details@wil@@QEAAPEAVFileDialogBrokerTraceLogging@@P6AXXZ@Z; wil::details::static_lazy<FileDialogBrokerTraceLogging>::get(void (*)(void))
0x14000f8ec  mov     byte ptr [rdi+18h], 0
0x14000f8f0  mov     dword ptr [rdi], 0
0x14000f8f6  mov     [rdi+8], rbx
0x14000f8fa  mov     qword ptr [rdi+10h], 0
0x14000f902  lea     rbx, [rdi+20h]
0x14000f906  mov     qword ptr [rbx], 0
0x14000f90d  mov     [rbx+8], rax
0x14000f911  mov     qword ptr [rbx+10h], 0
0x14000f919  mov     dword ptr [rbx+18h], 0
0x14000f920  mov     [rbx+20h], rdi
0x14000f924  mov     byte ptr [rbx+28h], 0
0x14000f928  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000f930  jz      short loc_14000F954
0x14000f932  mov     dl, 1
0x14000f934  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14000f939  mov     [rbx], rax
0x14000f93c  test    rax, rax
0x14000f93f  jz      short loc_14000F954
0x14000f941  mov     rcx, [rax]
0x14000f944  mov     [rbx+10h], rcx
0x14000f948  mov     [rax], rbx
0x14000f94b  call    cs:__imp_GetCurrentThreadId
0x14000f951  mov     [rbx+18h], eax
0x14000f954  mov     rax, rdi
0x14000f957  mov     rbx, [rsp+28h+arg_0]
0x14000f95c  add     rsp, 20h
0x14000f960  pop     rdi
0x14000f961  retn
```
