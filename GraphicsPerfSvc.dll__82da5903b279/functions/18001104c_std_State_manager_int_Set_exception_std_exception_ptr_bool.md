# std::_State_manager<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x18001104c`
- end: `0x1800110ab`
- name: `?_Set_exception@?$_State_manager@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `95`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e620`

## callees

- `0x180010f98`
- `0x18001104c`
- `0x180011130`
- `0x1800115fc`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180011083`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180011083`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800110a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_State_manager<int>::_Set_exception(__int64 a1, void *a2)
{
  const void *v3; // rdx
  _BYTE **v4; // rcx
  _BYTE *v5; // rbx
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned __int8)std::_State_manager<int>::valid(a1) )
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
0x18001104c  mov     [rsp+arg_0], rbx
0x180011051  mov     [rsp+arg_8], rdx
0x180011056  push    rdi
0x180011057  sub     rsp, 30h
0x18001105b  mov     rdi, rdx
0x18001105e  call    ?valid@?$_State_manager@H@std@@QEBA_NXZ; std::_State_manager<int>::valid(void)
0x180011063  test    al, al
0x180011065  jnz     short loc_180011072
0x180011067  mov     ecx, 4
0x18001106c  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180011072  mov     rbx, [rcx]
0x180011075  xorps   xmm0, xmm0
0x180011078  movdqu  [rsp+38h+var_18], xmm0
0x18001107e  lea     rcx, [rsp+38h+var_18]
0x180011083  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180011089  lea     rdx, [rsp+38h+var_18]
0x18001108e  mov     rcx, rbx
0x180011091  call    ?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z; std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)
0x180011096  nop
0x180011097  mov     rcx, rdi
0x18001109a  mov     rbx, [rsp+38h+arg_0]
0x18001109f  add     rsp, 30h
0x1800110a3  pop     rdi
0x1800110a4  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
