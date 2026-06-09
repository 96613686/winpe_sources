# std::_Associated_state<int>::_Get_value(bool)

- ea: `0x18001c5f0`
- end: `0x18001c6d6`
- name: `?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18001862c`
- `0x180018c30`
- `0x18001c5f0`
- `0x18001c938`
- `0x18001cb60`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001c65c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001c6b9`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001c65c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001c6b9`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001c631`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001c68e`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001c631`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001c68e`
- `msvcp_win!_Cnd_wait` at `0x18001c67c`
- `msvcp_win!_Cnd_wait` at `0x18001c67c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001c64a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001c6a7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001c64a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001c6a7`

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
0x18001c5f0  push    rbp
0x18001c5f2  push    rbx
0x18001c5f3  push    rsi
0x18001c5f4  push    rdi
0x18001c5f5  mov     rbp, rsp
0x18001c5f8  sub     rsp, 48h
0x18001c5fc  mov     bl, dl
0x18001c5fe  mov     rdi, rcx
0x18001c601  lea     rdx, [rcx+20h]
0x18001c605  lea     rcx, [rbp+var_18]
0x18001c609  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001c60e  nop
0x18001c60f  lea     rsi, [rdi+0B8h]
0x18001c616  test    bl, bl
0x18001c618  jz      short loc_18001C62A
0x18001c61a  cmp     byte ptr [rsi], 0
0x18001c61d  jz      short loc_18001C62A
0x18001c61f  mov     ecx, 2
0x18001c624  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18001c62a  lea     rbx, [rdi+10h]
0x18001c62e  mov     rcx, rbx
0x18001c631  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18001c637  test    al, al
0x18001c639  jz      short loc_18001C663
0x18001c63b  xorps   xmm0, xmm0
0x18001c63e  movdqu  [rbp+var_28], xmm0
0x18001c643  mov     rdx, rbx
0x18001c646  lea     rcx, [rbp+var_28]
0x18001c64a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001c650  lea     rax, [rbp+var_28]
0x18001c654  mov     [rbp+arg_0], rax
0x18001c658  lea     rcx, [rbp+var_28]
0x18001c65c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18001c662  nop
0x18001c663  mov     byte ptr [rsi], 1
0x18001c666  lea     rdx, [rbp+var_18]
0x18001c66a  mov     rcx, rdi
0x18001c66d  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x18001c672  jmp     short loc_18001C682
0x18001c674  mov     rdx, [rbp+var_18]; _Mtx_t
0x18001c678  lea     rcx, [rdi+70h]; _Cnd_t
0x18001c67c  call    cs:__imp__Cnd_wait
0x18001c682  cmp     dword ptr [rdi+0BCh], 0
0x18001c689  jz      short loc_18001C674
0x18001c68b  mov     rcx, rbx
0x18001c68e  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18001c694  test    al, al
0x18001c696  jz      short loc_18001C6C0
0x18001c698  xorps   xmm0, xmm0
0x18001c69b  movdqu  [rbp+var_28], xmm0
0x18001c6a0  mov     rdx, rbx
0x18001c6a3  lea     rcx, [rbp+var_28]
0x18001c6a7  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001c6ad  lea     rax, [rbp+var_28]
0x18001c6b1  mov     [rbp+arg_0], rax
0x18001c6b5  lea     rcx, [rbp+var_28]
0x18001c6b9  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18001c6bf  nop
0x18001c6c0  lea     rcx, [rbp+var_18]
0x18001c6c4  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001c6c9  lea     rax, [rdi+0Ch]
0x18001c6cd  add     rsp, 48h
0x18001c6d1  pop     rdi
0x18001c6d2  pop     rsi
0x18001c6d3  pop     rbx
0x18001c6d4  pop     rbp
0x18001c6d5  retn
```
