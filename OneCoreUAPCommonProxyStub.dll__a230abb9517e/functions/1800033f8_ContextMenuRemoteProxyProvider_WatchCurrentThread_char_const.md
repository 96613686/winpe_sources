# ContextMenuRemoteProxyProvider::WatchCurrentThread(char const *)

- ea: `0x1800033f8`
- end: `0x180003450`
- name: `?WatchCurrentThread@ContextMenuRemoteProxyProvider@@SA?AVActivityThreadWatcher@wil@@PEBD@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a500`

## callees

- `0x180002a44`
- `0x180003458`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ContextMenuRemoteProxyProvider::WatchCurrentThread(__int64 a1, __int64 a2)
{
  __int64 v4; // rax

  v4 = wil::details::static_lazy<ContextMenuRemoteProxyProvider>::get(
         a1,
         _lambda_30ad8d2020ae8953ad650d3900026770_::_lambda_invoker_cdecl_);
  *(_BYTE *)(a1 + 24) = 0;
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = a2;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = v4;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = a1;
  *(_BYTE *)(a1 + 72) = 0;
  wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 32), 0);
  return a1;
}

```

## disassembly

```asm
0x1800033f8  mov     [rsp+arg_0], rbx
0x1800033fd  push    rdi
0x1800033fe  sub     rsp, 20h
0x180003402  mov     rbx, rdx
0x180003405  mov     rdi, rcx
0x180003408  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_30ad8d2020ae8953ad650d3900026770_@@CA@XZ; _lambda_30ad8d2020ae8953ad650d3900026770_::_lambda_invoker_cdecl_(void)
0x18000340f  call    ?get@?$static_lazy@VContextMenuRemoteProxyProvider@@@details@wil@@QEAAPEAVContextMenuRemoteProxyProvider@@P6AXXZ@Z; wil::details::static_lazy<ContextMenuRemoteProxyProvider>::get(void (*)(void))
0x180003414  xor     edx, edx
0x180003416  mov     [rdi+18h], dl
0x180003419  mov     [rdi], edx
0x18000341b  mov     [rdi+8], rbx
0x18000341f  mov     [rdi+10h], rdx
0x180003423  lea     rcx, [rdi+20h]; this
0x180003427  mov     [rcx], rdx
0x18000342a  mov     [rcx+8], rax
0x18000342e  mov     [rcx+10h], rdx
0x180003432  mov     [rcx+18h], edx
0x180003435  mov     [rcx+20h], rdi
0x180003439  mov     [rcx+28h], dl
0x18000343c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180003441  nop
0x180003442  mov     rax, rdi
0x180003445  mov     rbx, [rsp+28h+arg_0]
0x18000344a  add     rsp, 20h
0x18000344e  pop     rdi
0x18000344f  retn
```
