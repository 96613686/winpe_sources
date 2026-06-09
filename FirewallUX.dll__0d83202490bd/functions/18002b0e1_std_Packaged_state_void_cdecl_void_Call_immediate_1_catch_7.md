# _std::_Packaged_state_void___cdecl(void)_::_Call_immediate_::_1_::catch$7

- ea: `0x18002b0e1`
- end: `0x18002b1ea`
- name: `_std::_Packaged_state_void___cdecl(void)_::_Call_immediate_::_1_::catch$7`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001a200`
- `0x18002b0e1`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002b136`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002b14e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002b136`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002b14e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002b169`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002b169`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b1b4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b1d0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b1b4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b1d0`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002b193`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002b193`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b0fc`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b0fc`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002b106`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002b106`
- `msvcp_win!_Mtx_unlock` at `0x18002b1c5`
- `msvcp_win!_Mtx_unlock` at `0x18002b1c5`
- `msvcp_win!_Mtx_lock` at `0x18002b127`
- `msvcp_win!_Mtx_lock` at `0x18002b127`

## pseudocode

```c
__int64 __fastcall std::_Packaged_state_void___cdecl_void__::_Call_immediate_::_1_::catch_7(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi

  *(_OWORD *)(a2 + 32) = 0;
  __ExceptionPtrCreate((void *)(a2 + 32));
  __ExceptionPtrCurrentException((void *)(a2 + 32));
  *(_QWORD *)(a2 + 104) = a2 + 32;
  v3 = *(_QWORD *)(a2 + 96);
  *(_QWORD *)(a2 + 64) = v3 + 32;
  *(_BYTE *)(a2 + 72) = 0;
  if ( _Mtx_lock((_Mtx_t)(v3 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v3 + 108) == 0x7FFFFFFF )
  {
    --*(_DWORD *)(v3 + 108);
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  *(_BYTE *)(a2 + 72) = 1;
  *(_OWORD *)(a2 + 48) = 0;
  __ExceptionPtrCopy((void *)(a2 + 48), (const void *)(a2 + 32));
  *(_QWORD *)(a2 + 96) = a2 + 48;
  if ( *(_BYTE *)(v3 + 193) )
    std::_Throw_future_error2(3);
  __ExceptionPtrAssign((void *)(v3 + 16), (const void *)(a2 + 48));
  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v3 + 40LL))(v3, a2 + 64, 0);
  __ExceptionPtrDestroy((void *)(a2 + 48));
  if ( *(_BYTE *)(a2 + 72) )
    _Mtx_unlock(*(_Mtx_t *)(a2 + 64));
  __ExceptionPtrDestroy((void *)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x18002b0e1  mov     [rsp+arg_8], rdx
0x18002b0e6  push    rbx
0x18002b0e7  push    rbp
0x18002b0e8  push    rdi
0x18002b0e9  sub     rsp, 20h
0x18002b0ed  mov     rbp, rdx
0x18002b0f0  xorps   xmm0, xmm0
0x18002b0f3  movdqu  xmmword ptr [rbp+20h], xmm0
0x18002b0f8  lea     rcx, [rbp+20h]
0x18002b0fc  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002b102  lea     rcx, [rbp+20h]
0x18002b106  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18002b10c  lea     rax, [rbp+20h]
0x18002b110  mov     [rbp+68h], rax
0x18002b114  mov     rdi, [rbp+60h]
0x18002b118  lea     rbx, [rdi+20h]
0x18002b11c  mov     [rbp+40h], rbx
0x18002b120  mov     byte ptr [rbp+48h], 0
0x18002b124  mov     rcx, rbx; _Mtx_t
0x18002b127  call    cs:__imp__Mtx_lock
0x18002b12d  test    eax, eax
0x18002b12f  jz      short loc_18002B13D
0x18002b131  mov     ecx, 5
0x18002b136  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002b13c  int     3; Trap to Debugger
0x18002b13d  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18002b144  jnz     short loc_18002B155
0x18002b146  dec     dword ptr [rbx+4Ch]
0x18002b149  mov     ecx, 6
0x18002b14e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002b154  int     3; Trap to Debugger
0x18002b155  mov     byte ptr [rbp+48h], 1
0x18002b159  xorps   xmm0, xmm0
0x18002b15c  movdqu  xmmword ptr [rbp+30h], xmm0
0x18002b161  lea     rdx, [rbp+20h]
0x18002b165  lea     rcx, [rbp+30h]
0x18002b169  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002b16f  lea     rax, [rbp+30h]
0x18002b173  mov     [rbp+60h], rax
0x18002b177  cmp     byte ptr [rdi+0C1h], 0
0x18002b17e  jz      short loc_18002B18B
0x18002b180  mov     ecx, 3
0x18002b185  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18002b18b  lea     rcx, [rdi+10h]
0x18002b18f  lea     rdx, [rbp+30h]
0x18002b193  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18002b199  mov     rax, [rdi]
0x18002b19c  xor     r8d, r8d
0x18002b19f  lea     rdx, [rbp+40h]
0x18002b1a3  mov     rcx, rdi
0x18002b1a6  mov     rax, [rax+28h]
0x18002b1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1af  nop
0x18002b1b0  lea     rcx, [rbp+30h]
0x18002b1b4  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002b1ba  nop
0x18002b1bb  cmp     byte ptr [rbp+48h], 0
0x18002b1bf  jz      short loc_18002B1CC
0x18002b1c1  mov     rcx, [rbp+40h]; _Mtx_t
0x18002b1c5  call    cs:__imp__Mtx_unlock
0x18002b1cb  nop
0x18002b1cc  lea     rcx, [rbp+20h]
0x18002b1d0  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002b1d6  nop
0x18002b1d7  mov     rax, 0
0x18002b1e1  add     rsp, 20h
0x18002b1e5  pop     rdi
0x18002b1e6  pop     rbp
0x18002b1e7  pop     rbx
0x18002b1e8  retn
```
