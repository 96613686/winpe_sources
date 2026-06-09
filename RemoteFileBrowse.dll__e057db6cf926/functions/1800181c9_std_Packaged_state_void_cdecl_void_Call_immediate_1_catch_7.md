# _std::_Packaged_state_void___cdecl(void)_::_Call_immediate_::_1_::catch$7

- ea: `0x1800181c9`
- end: `0x1800182d2`
- name: `_std::_Packaged_state_void___cdecl(void)_::_Call_immediate_::_1_::catch$7`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180012b24`
- `0x1800181c9`
- `0x180019010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18001827b`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18001827b`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800181e4`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800181e4`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800181ee`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800181ee`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001829c`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800182b8`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001829c`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800182b8`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180018251`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180018251`
- `msvcp_win!_Mtx_unlock` at `0x1800182ad`
- `msvcp_win!_Mtx_unlock` at `0x1800182ad`
- `msvcp_win!_Mtx_lock` at `0x18001820f`
- `msvcp_win!_Mtx_lock` at `0x18001820f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001821e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018236`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001821e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018236`

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
0x1800181c9  mov     [rsp+arg_8], rdx
0x1800181ce  push    rbx
0x1800181cf  push    rbp
0x1800181d0  push    rdi
0x1800181d1  sub     rsp, 20h
0x1800181d5  mov     rbp, rdx
0x1800181d8  xorps   xmm0, xmm0
0x1800181db  movdqu  xmmword ptr [rbp+20h], xmm0
0x1800181e0  lea     rcx, [rbp+20h]
0x1800181e4  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800181ea  lea     rcx, [rbp+20h]
0x1800181ee  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800181f4  lea     rax, [rbp+20h]
0x1800181f8  mov     [rbp+68h], rax
0x1800181fc  mov     rdi, [rbp+60h]
0x180018200  lea     rbx, [rdi+20h]
0x180018204  mov     [rbp+40h], rbx
0x180018208  mov     byte ptr [rbp+48h], 0
0x18001820c  mov     rcx, rbx; _Mtx_t
0x18001820f  call    cs:__imp__Mtx_lock
0x180018215  test    eax, eax
0x180018217  jz      short loc_180018225
0x180018219  mov     ecx, 5
0x18001821e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180018224  int     3; Trap to Debugger
0x180018225  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18001822c  jnz     short loc_18001823D
0x18001822e  dec     dword ptr [rbx+4Ch]
0x180018231  mov     ecx, 6
0x180018236  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001823c  int     3; Trap to Debugger
0x18001823d  mov     byte ptr [rbp+48h], 1
0x180018241  xorps   xmm0, xmm0
0x180018244  movdqu  xmmword ptr [rbp+30h], xmm0
0x180018249  lea     rdx, [rbp+20h]
0x18001824d  lea     rcx, [rbp+30h]
0x180018251  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180018257  lea     rax, [rbp+30h]
0x18001825b  mov     [rbp+60h], rax
0x18001825f  cmp     byte ptr [rdi+0C1h], 0
0x180018266  jz      short loc_180018273
0x180018268  mov     ecx, 3
0x18001826d  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180018273  lea     rcx, [rdi+10h]
0x180018277  lea     rdx, [rbp+30h]
0x18001827b  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180018281  mov     rax, [rdi]
0x180018284  xor     r8d, r8d
0x180018287  lea     rdx, [rbp+40h]
0x18001828b  mov     rcx, rdi
0x18001828e  mov     rax, [rax+28h]
0x180018292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018297  nop
0x180018298  lea     rcx, [rbp+30h]
0x18001829c  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800182a2  nop
0x1800182a3  cmp     byte ptr [rbp+48h], 0
0x1800182a7  jz      short loc_1800182B4
0x1800182a9  mov     rcx, [rbp+40h]; _Mtx_t
0x1800182ad  call    cs:__imp__Mtx_unlock
0x1800182b3  nop
0x1800182b4  lea     rcx, [rbp+20h]
0x1800182b8  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800182be  nop
0x1800182bf  mov     rax, 0
0x1800182c9  add     rsp, 20h
0x1800182cd  pop     rdi
0x1800182ce  pop     rbp
0x1800182cf  pop     rbx
0x1800182d0  retn
```
