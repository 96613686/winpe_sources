# _std::_Packaged_state_long___cdecl(void)_::_Call_immediate_::_1_::catch$7

- ea: `0x18008721d`
- end: `0x180087326`
- name: `_std::_Packaged_state_long___cdecl(void)_::_Call_immediate_::_1_::catch$7`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180072e40`
- `0x18008721d`
- `0x180089010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180087242`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180087242`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800872a5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800872a5`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800872cf`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800872cf`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800872f0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18008730c`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800872f0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18008730c`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180087238`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180087238`
- `msvcp_win!_Mtx_unlock` at `0x180087301`
- `msvcp_win!_Mtx_unlock` at `0x180087301`
- `msvcp_win!_Mtx_lock` at `0x180087263`
- `msvcp_win!_Mtx_lock` at `0x180087263`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180087272`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008728a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180087272`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008728a`

## pseudocode

```c
__int64 __fastcall std::_Packaged_state_long___cdecl_void__::_Call_immediate_::_1_::catch_7(__int64 a1, __int64 a2)
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
0x18008721d  mov     [rsp+arg_8], rdx
0x180087222  push    rbx
0x180087223  push    rbp
0x180087224  push    rdi
0x180087225  sub     rsp, 20h
0x180087229  mov     rbp, rdx
0x18008722c  xorps   xmm0, xmm0
0x18008722f  movdqu  xmmword ptr [rbp+20h], xmm0
0x180087234  lea     rcx, [rbp+20h]
0x180087238  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18008723e  lea     rcx, [rbp+20h]
0x180087242  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180087248  lea     rax, [rbp+20h]
0x18008724c  mov     [rbp+68h], rax
0x180087250  mov     rdi, [rbp+60h]
0x180087254  lea     rbx, [rdi+20h]
0x180087258  mov     [rbp+40h], rbx
0x18008725c  mov     byte ptr [rbp+48h], 0
0x180087260  mov     rcx, rbx; _Mtx_t
0x180087263  call    cs:__imp__Mtx_lock
0x180087269  test    eax, eax
0x18008726b  jz      short loc_180087279
0x18008726d  mov     ecx, 5
0x180087272  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180087278  int     3; Trap to Debugger
0x180087279  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180087280  jnz     short loc_180087291
0x180087282  dec     dword ptr [rbx+4Ch]
0x180087285  mov     ecx, 6
0x18008728a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180087290  int     3; Trap to Debugger
0x180087291  mov     byte ptr [rbp+48h], 1
0x180087295  xorps   xmm0, xmm0
0x180087298  movdqu  xmmword ptr [rbp+30h], xmm0
0x18008729d  lea     rdx, [rbp+20h]
0x1800872a1  lea     rcx, [rbp+30h]
0x1800872a5  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800872ab  lea     rax, [rbp+30h]
0x1800872af  mov     [rbp+60h], rax
0x1800872b3  cmp     byte ptr [rdi+0C1h], 0
0x1800872ba  jz      short loc_1800872C7
0x1800872bc  mov     ecx, 3
0x1800872c1  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800872c7  lea     rcx, [rdi+10h]
0x1800872cb  lea     rdx, [rbp+30h]
0x1800872cf  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800872d5  mov     rax, [rdi]
0x1800872d8  xor     r8d, r8d
0x1800872db  lea     rdx, [rbp+40h]
0x1800872df  mov     rcx, rdi
0x1800872e2  mov     rax, [rax+28h]
0x1800872e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800872eb  nop
0x1800872ec  lea     rcx, [rbp+30h]
0x1800872f0  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800872f6  nop
0x1800872f7  cmp     byte ptr [rbp+48h], 0
0x1800872fb  jz      short loc_180087308
0x1800872fd  mov     rcx, [rbp+40h]; _Mtx_t
0x180087301  call    cs:__imp__Mtx_unlock
0x180087307  nop
0x180087308  lea     rcx, [rbp+20h]
0x18008730c  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180087312  nop
0x180087313  mov     rax, 0
0x18008731d  add     rsp, 20h
0x180087321  pop     rdi
0x180087322  pop     rbp
0x180087323  pop     rbx
0x180087324  retn
```
