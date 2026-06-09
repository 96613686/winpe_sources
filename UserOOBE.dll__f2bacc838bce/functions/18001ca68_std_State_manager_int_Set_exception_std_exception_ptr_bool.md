# std::_State_manager<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x18001ca68`
- end: `0x18001cac7`
- name: `?_Set_exception@?$_State_manager@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018b48`

## callees

- `0x18001c9b4`
- `0x18001ca68`
- `0x18001cb60`
- `0x18001d2b4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001cac0`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001ca9f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001ca9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_State_manager<int>::_Set_exception(__int64 a1, void *a2)
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
  std::_Associated_state<int>::_Set_exception(v5, &v6);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x18001ca68  mov     [rsp+arg_0], rbx
0x18001ca6d  mov     [rsp+arg_8], rdx
0x18001ca72  push    rdi
0x18001ca73  sub     rsp, 30h
0x18001ca77  mov     rdi, rdx
0x18001ca7a  call    ?valid@?$_State_manager@J@std@@QEBA_NXZ; std::_State_manager<long>::valid(void)
0x18001ca7f  test    al, al
0x18001ca81  jnz     short loc_18001CA8E
0x18001ca83  mov     ecx, 4
0x18001ca88  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18001ca8e  mov     rbx, [rcx]
0x18001ca91  xorps   xmm0, xmm0
0x18001ca94  movdqu  [rsp+38h+var_18], xmm0
0x18001ca9a  lea     rcx, [rsp+38h+var_18]
0x18001ca9f  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001caa5  lea     rdx, [rsp+38h+var_18]
0x18001caaa  mov     rcx, rbx
0x18001caad  call    ?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z; std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)
0x18001cab2  nop
0x18001cab3  mov     rcx, rdi
0x18001cab6  mov     rbx, [rsp+38h+arg_0]
0x18001cabb  add     rsp, 30h
0x18001cabf  pop     rdi
0x18001cac0  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
