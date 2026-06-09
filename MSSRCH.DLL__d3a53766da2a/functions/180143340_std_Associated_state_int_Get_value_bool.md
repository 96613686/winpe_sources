# std::_Associated_state<int>::_Get_value(bool)

- ea: `0x180143340`
- end: `0x180143426`
- name: `?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180143430`

## callees

- `0x18014025c`
- `0x1801407b4`
- `0x180143340`
- `0x1801434ac`
- `0x1801438a0`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x1801433cc`
- `msvcp_win!_Cnd_wait` at `0x1801433cc`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18014339a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1801433f7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18014339a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1801433f7`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180143381`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1801433de`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180143381`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1801433de`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1801433ac`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180143409`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1801433ac`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180143409`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<int>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  _Mtx_t v7[3]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, a1 + 32);
  v4 = (_BYTE *)(a1 + 184);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state<int>::_Maybe_run_deferred_function(a1, v7);
  while ( !*(_DWORD *)(a1 + 188) )
    _Cnd_wait((_Cnd_t)(a1 + 112), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 12;
}

```

## disassembly

```asm
0x180143340  push    rbp
0x180143342  push    rbx
0x180143343  push    rsi
0x180143344  push    rdi
0x180143345  mov     rbp, rsp
0x180143348  sub     rsp, 48h
0x18014334c  mov     bl, dl
0x18014334e  mov     rdi, rcx
0x180143351  lea     rdx, [rcx+20h]
0x180143355  lea     rcx, [rbp+var_18]
0x180143359  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18014335e  nop
0x18014335f  lea     rsi, [rdi+0B8h]
0x180143366  test    bl, bl
0x180143368  jz      short loc_18014337A
0x18014336a  cmp     byte ptr [rsi], 0
0x18014336d  jz      short loc_18014337A
0x18014336f  mov     ecx, 2
0x180143374  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18014337a  lea     rbx, [rdi+10h]
0x18014337e  mov     rcx, rbx
0x180143381  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180143387  test    al, al
0x180143389  jz      short loc_1801433B3
0x18014338b  xorps   xmm0, xmm0
0x18014338e  movdqu  [rbp+var_28], xmm0
0x180143393  mov     rdx, rbx
0x180143396  lea     rcx, [rbp+var_28]
0x18014339a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1801433a0  lea     rax, [rbp+var_28]
0x1801433a4  mov     [rbp+arg_0], rax
0x1801433a8  lea     rcx, [rbp+var_28]
0x1801433ac  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1801433b2  nop
0x1801433b3  mov     byte ptr [rsi], 1
0x1801433b6  lea     rdx, [rbp+var_18]
0x1801433ba  mov     rcx, rdi
0x1801433bd  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x1801433c2  jmp     short loc_1801433D2
0x1801433c4  mov     rdx, [rbp+var_18]; _Mtx_t
0x1801433c8  lea     rcx, [rdi+70h]; _Cnd_t
0x1801433cc  call    cs:__imp__Cnd_wait
0x1801433d2  cmp     dword ptr [rdi+0BCh], 0
0x1801433d9  jz      short loc_1801433C4
0x1801433db  mov     rcx, rbx
0x1801433de  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1801433e4  test    al, al
0x1801433e6  jz      short loc_180143410
0x1801433e8  xorps   xmm0, xmm0
0x1801433eb  movdqu  [rbp+var_28], xmm0
0x1801433f0  mov     rdx, rbx
0x1801433f3  lea     rcx, [rbp+var_28]
0x1801433f7  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1801433fd  lea     rax, [rbp+var_28]
0x180143401  mov     [rbp+arg_0], rax
0x180143405  lea     rcx, [rbp+var_28]
0x180143409  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18014340f  nop
0x180143410  lea     rcx, [rbp+var_18]
0x180143414  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180143419  lea     rax, [rdi+0Ch]
0x18014341d  add     rsp, 48h
0x180143421  pop     rdi
0x180143422  pop     rsi
0x180143423  pop     rbx
0x180143424  pop     rbp
0x180143425  retn
```
