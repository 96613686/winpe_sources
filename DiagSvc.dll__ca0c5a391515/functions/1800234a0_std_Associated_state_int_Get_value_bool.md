# std::_Associated_state<int>::_Get_value(bool)

- ea: `0x1800234a0`
- end: `0x180023586`
- name: `?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180023590`

## callees

- `0x18001d9e0`
- `0x18001e230`
- `0x1800234a0`
- `0x180023a84`
- `0x180024310`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18002352c`
- `msvcp_win!_Cnd_wait` at `0x18002352c`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800234e1`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002353e`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800234e1`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002353e`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002350c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180023569`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002350c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180023569`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800234fa`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180023557`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800234fa`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180023557`

## pseudocode

```c
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
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v7);
  return a1 + 12;
}

```

## disassembly

```asm
0x1800234a0  push    rbp
0x1800234a2  push    rbx
0x1800234a3  push    rsi
0x1800234a4  push    rdi
0x1800234a5  mov     rbp, rsp
0x1800234a8  sub     rsp, 48h
0x1800234ac  mov     bl, dl
0x1800234ae  mov     rdi, rcx
0x1800234b1  lea     rdx, [rcx+20h]
0x1800234b5  lea     rcx, [rbp+var_18]
0x1800234b9  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x1800234be  nop
0x1800234bf  lea     rsi, [rdi+0B8h]
0x1800234c6  test    bl, bl
0x1800234c8  jz      short loc_1800234DA
0x1800234ca  cmp     byte ptr [rsi], 0
0x1800234cd  jz      short loc_1800234DA
0x1800234cf  mov     ecx, 2
0x1800234d4  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800234da  lea     rbx, [rdi+10h]
0x1800234de  mov     rcx, rbx
0x1800234e1  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800234e7  test    al, al
0x1800234e9  jz      short loc_180023513
0x1800234eb  xorps   xmm0, xmm0
0x1800234ee  movdqu  [rbp+var_28], xmm0
0x1800234f3  mov     rdx, rbx
0x1800234f6  lea     rcx, [rbp+var_28]
0x1800234fa  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180023500  lea     rax, [rbp+var_28]
0x180023504  mov     [rbp+arg_0], rax
0x180023508  lea     rcx, [rbp+var_28]
0x18002350c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180023512  nop
0x180023513  mov     byte ptr [rsi], 1
0x180023516  lea     rdx, [rbp+var_18]
0x18002351a  mov     rcx, rdi
0x18002351d  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x180023522  jmp     short loc_180023532
0x180023524  mov     rdx, [rbp+var_18]; _Mtx_t
0x180023528  lea     rcx, [rdi+70h]; _Cnd_t
0x18002352c  call    cs:__imp__Cnd_wait
0x180023532  cmp     dword ptr [rdi+0BCh], 0
0x180023539  jz      short loc_180023524
0x18002353b  mov     rcx, rbx
0x18002353e  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180023544  test    al, al
0x180023546  jz      short loc_180023570
0x180023548  xorps   xmm0, xmm0
0x18002354b  movdqu  [rbp+var_28], xmm0
0x180023550  mov     rdx, rbx
0x180023553  lea     rcx, [rbp+var_28]
0x180023557  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002355d  lea     rax, [rbp+var_28]
0x180023561  mov     [rbp+arg_0], rax
0x180023565  lea     rcx, [rbp+var_28]
0x180023569  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18002356f  nop
0x180023570  lea     rcx, [rbp+var_18]
0x180023574  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180023579  lea     rax, [rdi+0Ch]
0x18002357d  add     rsp, 48h
0x180023581  pop     rdi
0x180023582  pop     rsi
0x180023583  pop     rbx
0x180023584  pop     rbp
0x180023585  retn
```
