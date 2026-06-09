# std::_Associated_state<long>::_Get_value(bool)

- ea: `0x18000a3c0`
- end: `0x18000a4a6`
- name: `?_Get_value@?$_Associated_state@J@std@@UEAAAEAJ_N@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004e9c`
- `0x1800057b4`
- `0x18000a3c0`
- `0x18000a504`
- `0x18000a6d0`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18000a44c`
- `msvcp_win!_Cnd_wait` at `0x18000a44c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18000a42c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18000a489`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18000a42c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18000a489`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000a41a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000a477`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000a41a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000a477`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000a401`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000a45e`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000a401`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000a45e`

## pseudocode

```c
__int64 __fastcall std::_Associated_state<long>::_Get_value(__int64 a1, char a2)
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
  std::_Associated_state<long>::_Maybe_run_deferred_function(a1, v7);
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
0x18000a3c0  push    rbp
0x18000a3c2  push    rbx
0x18000a3c3  push    rsi
0x18000a3c4  push    rdi
0x18000a3c5  mov     rbp, rsp
0x18000a3c8  sub     rsp, 48h
0x18000a3cc  mov     bl, dl
0x18000a3ce  mov     rdi, rcx
0x18000a3d1  lea     rdx, [rcx+20h]
0x18000a3d5  lea     rcx, [rbp+var_18]
0x18000a3d9  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18000a3de  nop
0x18000a3df  lea     rsi, [rdi+0B8h]
0x18000a3e6  test    bl, bl
0x18000a3e8  jz      short loc_18000A3FA
0x18000a3ea  cmp     byte ptr [rsi], 0
0x18000a3ed  jz      short loc_18000A3FA
0x18000a3ef  mov     ecx, 2
0x18000a3f4  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18000a3fa  lea     rbx, [rdi+10h]
0x18000a3fe  mov     rcx, rbx
0x18000a401  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18000a407  test    al, al
0x18000a409  jz      short loc_18000A433
0x18000a40b  xorps   xmm0, xmm0
0x18000a40e  movdqu  [rbp+var_28], xmm0
0x18000a413  mov     rdx, rbx
0x18000a416  lea     rcx, [rbp+var_28]
0x18000a41a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18000a420  lea     rax, [rbp+var_28]
0x18000a424  mov     [rbp+arg_0], rax
0x18000a428  lea     rcx, [rbp+var_28]
0x18000a42c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18000a432  nop
0x18000a433  mov     byte ptr [rsi], 1
0x18000a436  lea     rdx, [rbp+var_18]
0x18000a43a  mov     rcx, rdi
0x18000a43d  call    ?_Maybe_run_deferred_function@?$_Associated_state@J@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<long>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x18000a442  jmp     short loc_18000A452
0x18000a444  mov     rdx, [rbp+var_18]; _Mtx_t
0x18000a448  lea     rcx, [rdi+70h]; _Cnd_t
0x18000a44c  call    cs:__imp__Cnd_wait
0x18000a452  cmp     dword ptr [rdi+0BCh], 0
0x18000a459  jz      short loc_18000A444
0x18000a45b  mov     rcx, rbx
0x18000a45e  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18000a464  test    al, al
0x18000a466  jz      short loc_18000A490
0x18000a468  xorps   xmm0, xmm0
0x18000a46b  movdqu  [rbp+var_28], xmm0
0x18000a470  mov     rdx, rbx
0x18000a473  lea     rcx, [rbp+var_28]
0x18000a477  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18000a47d  lea     rax, [rbp+var_28]
0x18000a481  mov     [rbp+arg_0], rax
0x18000a485  lea     rcx, [rbp+var_28]
0x18000a489  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18000a48f  nop
0x18000a490  lea     rcx, [rbp+var_18]
0x18000a494  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18000a499  lea     rax, [rdi+0Ch]
0x18000a49d  add     rsp, 48h
0x18000a4a1  pop     rdi
0x18000a4a2  pop     rsi
0x18000a4a3  pop     rbx
0x18000a4a4  pop     rbp
0x18000a4a5  retn
```
