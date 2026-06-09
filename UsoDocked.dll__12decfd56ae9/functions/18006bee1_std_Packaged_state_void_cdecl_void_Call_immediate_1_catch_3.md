# _std::_Packaged_state_void___cdecl(void)_::_Call_immediate_::_1_::catch$3

- ea: `0x18006bee1`
- end: `0x18006bf29`
- name: `_std::_Packaged_state_void___cdecl(void)_::_Call_immediate_::_1_::catch$3`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180039fec`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006befa`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006befa`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006bf04`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006bf04`

## pseudocode

```c
__int64 __fastcall std::_Packaged_state_void___cdecl_void__::_Call_immediate_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_OWORD *)(a2 + 40) = 0;
  __ExceptionPtrCreate((void *)(a2 + 40));
  __ExceptionPtrCurrentException((void *)(a2 + 40));
  std::_Associated_state<int>::_Set_exception(*(_QWORD *)(a2 + 32), (void *)(a2 + 40));
  return 0;
}

```

## disassembly

```asm
0x18006bee1  mov     [rsp+arg_8], rdx
0x18006bee6  push    rbp
0x18006bee7  sub     rsp, 20h
0x18006beeb  mov     rbp, rdx
0x18006beee  xorps   xmm0, xmm0
0x18006bef1  movdqu  xmmword ptr [rbp+28h], xmm0
0x18006bef6  lea     rcx, [rbp+28h]
0x18006befa  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18006bf00  lea     rcx, [rbp+28h]
0x18006bf04  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18006bf0a  lea     rdx, [rbp+28h]
0x18006bf0e  mov     rcx, [rbp+20h]
0x18006bf12  call    ?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z; std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)
0x18006bf17  nop
0x18006bf18  mov     rax, 0
0x18006bf22  add     rsp, 20h
0x18006bf26  pop     rbp
0x18006bf27  retn
```
