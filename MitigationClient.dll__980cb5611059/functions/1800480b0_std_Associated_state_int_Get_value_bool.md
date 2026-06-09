# std::_Associated_state<int>::_Get_value(bool)

- ea: `0x1800480b0`
- end: `0x180048196`
- name: `?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800481a0`

## callees

- `0x1800466bc`
- `0x180046d5c`
- `0x1800480b0`
- `0x18004843c`
- `0x180048b20`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18004813c`
- `msvcp_win!_Cnd_wait` at `0x18004813c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004810a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180048167`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004810a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180048167`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18004811c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180048179`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18004811c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180048179`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800480f1`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18004814e`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800480f1`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18004814e`

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
0x1800480b0  push    rbp
0x1800480b2  push    rbx
0x1800480b3  push    rsi
0x1800480b4  push    rdi
0x1800480b5  mov     rbp, rsp
0x1800480b8  sub     rsp, 48h
0x1800480bc  mov     bl, dl
0x1800480be  mov     rdi, rcx
0x1800480c1  lea     rdx, [rcx+20h]
0x1800480c5  lea     rcx, [rbp+var_18]
0x1800480c9  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x1800480ce  nop
0x1800480cf  lea     rsi, [rdi+0B8h]
0x1800480d6  test    bl, bl
0x1800480d8  jz      short loc_1800480EA
0x1800480da  cmp     byte ptr [rsi], 0
0x1800480dd  jz      short loc_1800480EA
0x1800480df  mov     ecx, 2
0x1800480e4  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800480ea  lea     rbx, [rdi+10h]
0x1800480ee  mov     rcx, rbx
0x1800480f1  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800480f7  test    al, al
0x1800480f9  jz      short loc_180048123
0x1800480fb  xorps   xmm0, xmm0
0x1800480fe  movdqu  [rbp+var_28], xmm0
0x180048103  mov     rdx, rbx
0x180048106  lea     rcx, [rbp+var_28]
0x18004810a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180048110  lea     rax, [rbp+var_28]
0x180048114  mov     [rbp+arg_0], rax
0x180048118  lea     rcx, [rbp+var_28]
0x18004811c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180048122  nop
0x180048123  mov     byte ptr [rsi], 1
0x180048126  lea     rdx, [rbp+var_18]
0x18004812a  mov     rcx, rdi
0x18004812d  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x180048132  jmp     short loc_180048142
0x180048134  mov     rdx, [rbp+var_18]; _Mtx_t
0x180048138  lea     rcx, [rdi+70h]; _Cnd_t
0x18004813c  call    cs:__imp__Cnd_wait
0x180048142  cmp     dword ptr [rdi+0BCh], 0
0x180048149  jz      short loc_180048134
0x18004814b  mov     rcx, rbx
0x18004814e  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180048154  test    al, al
0x180048156  jz      short loc_180048180
0x180048158  xorps   xmm0, xmm0
0x18004815b  movdqu  [rbp+var_28], xmm0
0x180048160  mov     rdx, rbx
0x180048163  lea     rcx, [rbp+var_28]
0x180048167  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18004816d  lea     rax, [rbp+var_28]
0x180048171  mov     [rbp+arg_0], rax
0x180048175  lea     rcx, [rbp+var_28]
0x180048179  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18004817f  nop
0x180048180  lea     rcx, [rbp+var_18]
0x180048184  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180048189  lea     rax, [rdi+0Ch]
0x18004818d  add     rsp, 48h
0x180048191  pop     rdi
0x180048192  pop     rsi
0x180048193  pop     rbx
0x180048194  pop     rbp
0x180048195  retn
```
