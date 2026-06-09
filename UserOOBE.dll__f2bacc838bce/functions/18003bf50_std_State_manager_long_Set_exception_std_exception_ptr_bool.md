# std::_State_manager<long>::_Set_exception(std::exception_ptr,bool)

- ea: `0x18003bf50`
- end: `0x18003bfaf`
- name: `?_Set_exception@?$_State_manager@J@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180036f94`

## callees

- `0x18001cb60`
- `0x18001d2b4`
- `0x18003be9c`
- `0x18003bf50`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003bf9d`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003bf7c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003bf7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_State_manager<long>::_Set_exception(__int64 a1, void *a2)
{
  const void *v3; // rdx
  _BYTE **v4; // rcx
  _BYTE *v5; // rbx
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned __int8)std::_State_manager<long>::valid() )
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
0x18003bf50  mov     [rsp+arg_0], rbx
0x18003bf55  mov     [rsp+arg_8], rdx
0x18003bf5a  push    rdi
0x18003bf5b  sub     rsp, 30h
0x18003bf5f  mov     rdi, rdx
0x18003bf62  call    ?valid@?$_State_manager@J@std@@QEBA_NXZ; std::_State_manager<long>::valid(void)
0x18003bf67  test    al, al
0x18003bf69  jz      short loc_18003BFA4
0x18003bf6b  mov     rbx, [rcx]
0x18003bf6e  xorps   xmm0, xmm0
0x18003bf71  movdqu  [rsp+38h+var_18], xmm0
0x18003bf77  lea     rcx, [rsp+38h+var_18]
0x18003bf7c  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003bf82  lea     rdx, [rsp+38h+var_18]
0x18003bf87  mov     rcx, rbx
0x18003bf8a  call    ?_Set_exception@?$_Associated_state@J@std@@QEAAXVexception_ptr@2@_N@Z; std::_Associated_state<long>::_Set_exception(std::exception_ptr,bool)
0x18003bf8f  nop
0x18003bf90  mov     rcx, rdi
0x18003bf93  mov     rbx, [rsp+38h+arg_0]
0x18003bf98  add     rsp, 30h
0x18003bf9c  pop     rdi
0x18003bf9d  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003bfa4  mov     ecx, 4
0x18003bfa9  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
