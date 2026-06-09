# std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x1800377b0`
- end: `0x1800378a4`
- name: `?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180035d68`
- `0x1800383d0`

## callees

- `0x180035b0c`
- `0x1800377b0`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003785f`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003787a`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003785f`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003787a`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003781e`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003781e`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003783d`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003783d`
- `MSVCP140!_Mtx_unlock` at `0x180037870`
- `MSVCP140!_Mtx_unlock` at `0x180037870`
- `MSVCP140!_Mtx_lock` at `0x1800377d9`
- `MSVCP140!_Mtx_lock` at `0x1800377d9`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800377e8`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180037804`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800377e8`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180037804`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Associated_state<int>::_Set_exception(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdi
  __int64 result; // rax
  __int128 v6; // [rsp+20h] [rbp-20h] BYREF
  _Mtx_t v7; // [rsp+30h] [rbp-10h] BYREF
  char v8; // [rsp+38h] [rbp-8h]

  v4 = a1 + 32;
  v7 = (_Mtx_t)(a1 + 32);
  v8 = 0;
  if ( _Mtx_lock((_Mtx_t)(a1 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v4 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v4 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v8 = 1;
  v6 = 0;
  __ExceptionPtrCopy(&v6, a2);
  if ( *(_BYTE *)(a1 + 193) )
    std::_Throw_future_error2(3);
  __ExceptionPtrAssign((void *)(a1 + 16), &v6);
  (*(void (__fastcall **)(__int64, _Mtx_t *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, &v7, 0);
  __ExceptionPtrDestroy(&v6);
  if ( v8 )
    _Mtx_unlock(v7);
  __ExceptionPtrDestroy(a2);
  result = 19937;
  *a2 = 19937;
  a2[1] = 19937;
  return result;
}

```

## disassembly

```asm
0x1800377b0  mov     [rsp-18h+arg_10], rbx
0x1800377b5  mov     [rsp-18h+arg_8], rdx
0x1800377ba  push    rbp
0x1800377bb  push    rsi
0x1800377bc  push    rdi
0x1800377bd  mov     rbp, rsp
0x1800377c0  sub     rsp, 40h
0x1800377c4  mov     rbx, rdx
0x1800377c7  mov     rsi, rcx
0x1800377ca  lea     rdi, [rcx+20h]
0x1800377ce  mov     [rbp+var_10], rdi
0x1800377d2  mov     [rbp+var_8], 0
0x1800377d6  mov     rcx, rdi; _Mtx_t
0x1800377d9  call    cs:__imp__Mtx_lock
0x1800377df  test    eax, eax
0x1800377e1  jz      short loc_1800377EF
0x1800377e3  mov     ecx, 5
0x1800377e8  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800377ee  int     3; Trap to Debugger
0x1800377ef  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x1800377f6  jnz     short loc_18003780B
0x1800377f8  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x1800377ff  mov     ecx, 6
0x180037804  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003780a  int     3; Trap to Debugger
0x18003780b  mov     [rbp+var_8], 1
0x18003780f  xorps   xmm0, xmm0
0x180037812  movdqu  [rbp+var_20], xmm0
0x180037817  mov     rdx, rbx
0x18003781a  lea     rcx, [rbp+var_20]
0x18003781e  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180037824  lea     rax, [rbp+var_20]
0x180037828  mov     [rbp+arg_0], rax
0x18003782c  cmp     byte ptr [rsi+0C1h], 0
0x180037833  jnz     short loc_180037899
0x180037835  lea     rcx, [rsi+10h]
0x180037839  lea     rdx, [rbp+var_20]
0x18003783d  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180037843  mov     rax, [rsi]
0x180037846  xor     r8d, r8d
0x180037849  lea     rdx, [rbp+var_10]
0x18003784d  mov     rcx, rsi
0x180037850  mov     rax, [rax+28h]
0x180037854  call    cs:__guard_dispatch_icall_fptr
0x18003785a  nop
0x18003785b  lea     rcx, [rbp+var_20]
0x18003785f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180037865  nop
0x180037866  cmp     [rbp+var_8], 0
0x18003786a  jz      short loc_180037877
0x18003786c  mov     rcx, [rbp+var_10]; _Mtx_t
0x180037870  call    cs:__imp__Mtx_unlock
0x180037876  nop
0x180037877  mov     rcx, rbx
0x18003787a  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180037880  mov     eax, 4DE1h
0x180037885  mov     [rbx], rax
0x180037888  mov     [rbx+8], rax
0x18003788c  mov     rbx, [rsp+40h+arg_10]
0x180037891  add     rsp, 40h
0x180037895  pop     rdi
0x180037896  pop     rsi
0x180037897  pop     rbp
0x180037898  retn
0x180037899  mov     ecx, 3
0x18003789e  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
