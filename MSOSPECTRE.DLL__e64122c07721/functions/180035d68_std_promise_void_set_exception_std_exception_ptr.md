# std::promise<void>::set_exception(std::exception_ptr)

- ea: `0x180035d68`
- end: `0x180035e38`
- name: `?set_exception@?$promise@X@std@@QEAAXVexception_ptr@2@@Z`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180037b58`
- `0x1804fbad5`

## callees

- `0x180035b0c`
- `0x180035d68`
- `0x1800377b0`

## import_xrefs

- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180035df9`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180035e03`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180035df9`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180035e03`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180035dad`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180035de2`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180035dad`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180035de2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::promise<void>::set_exception(_BYTE *a1, _QWORD *a2)
{
  __int64 v4; // rsi
  __int64 result; // rax
  __int128 v6; // [rsp+20h] [rbp-20h] BYREF
  __int128 v7; // [rsp+30h] [rbp-10h] BYREF

  if ( !*(_QWORD *)a1 || a1[8] && *(_BYTE *)(*(_QWORD *)a1 + 184LL) )
    std::_Throw_future_error2(4);
  v6 = 0;
  __ExceptionPtrCopy(&v6, a2);
  v4 = *(_QWORD *)a1;
  if ( !*(_QWORD *)a1 || a1[8] && *(_BYTE *)(v4 + 184) )
    std::_Throw_future_error2(4);
  v7 = 0;
  __ExceptionPtrCopy(&v7, &v6);
  std::_Associated_state<int>::_Set_exception(v4, &v7);
  __ExceptionPtrDestroy(&v6);
  __ExceptionPtrDestroy(a2);
  result = 19937;
  *a2 = 19937;
  a2[1] = 19937;
  return result;
}

```

## disassembly

```asm
0x180035d68  mov     [rsp-18h+arg_18], rbx
0x180035d6d  mov     [rsp-18h+arg_8], rdx
0x180035d72  push    rbp
0x180035d73  push    rsi
0x180035d74  push    rdi
0x180035d75  mov     rbp, rsp
0x180035d78  sub     rsp, 40h
0x180035d7c  mov     rdi, rdx
0x180035d7f  mov     rbx, rcx
0x180035d82  mov     rax, [rcx]
0x180035d85  test    rax, rax
0x180035d88  jz      loc_180035E2D
0x180035d8e  cmp     byte ptr [rcx+8], 0
0x180035d92  jz      short loc_180035DA1
0x180035d94  cmp     byte ptr [rax+0B8h], 0
0x180035d9b  jnz     loc_180035E2D
0x180035da1  xorps   xmm0, xmm0
0x180035da4  movdqu  [rbp+var_20], xmm0
0x180035da9  lea     rcx, [rbp+var_20]
0x180035dad  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180035db3  lea     rax, [rbp+var_20]
0x180035db7  mov     [rbp+arg_0], rax
0x180035dbb  mov     rsi, [rbx]
0x180035dbe  test    rsi, rsi
0x180035dc1  jz      short loc_180035E22
0x180035dc3  cmp     byte ptr [rbx+8], 0
0x180035dc7  jz      short loc_180035DD2
0x180035dc9  cmp     byte ptr [rsi+0B8h], 0
0x180035dd0  jnz     short loc_180035E22
0x180035dd2  xorps   xmm0, xmm0
0x180035dd5  movdqu  [rbp+var_10], xmm0
0x180035dda  lea     rdx, [rbp+var_20]
0x180035dde  lea     rcx, [rbp+var_10]
0x180035de2  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180035de8  lea     rdx, [rbp+var_10]
0x180035dec  mov     rcx, rsi
0x180035def  call    ?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z; std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)
0x180035df4  nop
0x180035df5  lea     rcx, [rbp+var_20]
0x180035df9  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180035dff  nop
0x180035e00  mov     rcx, rdi
0x180035e03  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180035e09  mov     eax, 4DE1h
0x180035e0e  mov     [rdi], rax
0x180035e11  mov     [rdi+8], rax
0x180035e15  mov     rbx, [rsp+40h+arg_18]
0x180035e1a  add     rsp, 40h
0x180035e1e  pop     rdi
0x180035e1f  pop     rsi
0x180035e20  pop     rbp
0x180035e21  retn
0x180035e22  mov     ecx, 4
0x180035e27  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180035e2d  mov     ecx, 4
0x180035e32  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
