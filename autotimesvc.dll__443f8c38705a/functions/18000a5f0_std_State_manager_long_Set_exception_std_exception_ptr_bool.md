# std::_State_manager<long>::_Set_exception(std::exception_ptr,bool)

- ea: `0x18000a5f0`
- end: `0x18000a64f`
- name: `?_Set_exception@?$_State_manager@J@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `95`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005688`

## callees

- `0x18000a53c`
- `0x18000a5f0`
- `0x18000a6d0`
- `0x18000ab38`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000a627`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000a627`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000a648`

## pseudocode

```c
void __fastcall std::_State_manager<long>::_Set_exception(__int64 a1, void *a2)
{
  const void *v3; // rdx
  _BYTE **v4; // rcx
  _BYTE *v5; // rbx
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned __int8)std::_State_manager<long>::valid(a1) )
    std::_Throw_future_error2(4);
  v5 = *v4;
  v6 = 0;
  __ExceptionPtrCopy(&v6, v3);
  std::_Associated_state<long>::_Set_exception(v5, &v6);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x18000a5f0  mov     [rsp+arg_0], rbx
0x18000a5f5  mov     [rsp+arg_8], rdx
0x18000a5fa  push    rdi
0x18000a5fb  sub     rsp, 30h
0x18000a5ff  mov     rdi, rdx
0x18000a602  call    ?valid@?$_State_manager@J@std@@QEBA_NXZ; std::_State_manager<long>::valid(void)
0x18000a607  test    al, al
0x18000a609  jnz     short loc_18000A616
0x18000a60b  mov     ecx, 4
0x18000a610  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18000a616  mov     rbx, [rcx]
0x18000a619  xorps   xmm0, xmm0
0x18000a61c  movdqu  [rsp+38h+var_18], xmm0
0x18000a622  lea     rcx, [rsp+38h+var_18]
0x18000a627  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18000a62d  lea     rdx, [rsp+38h+var_18]
0x18000a632  mov     rcx, rbx
0x18000a635  call    ?_Set_exception@?$_Associated_state@J@std@@QEAAXVexception_ptr@2@_N@Z; std::_Associated_state<long>::_Set_exception(std::exception_ptr,bool)
0x18000a63a  nop
0x18000a63b  mov     rcx, rdi
0x18000a63e  mov     rbx, [rsp+38h+arg_0]
0x18000a643  add     rsp, 30h
0x18000a647  pop     rdi
0x18000a648  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
