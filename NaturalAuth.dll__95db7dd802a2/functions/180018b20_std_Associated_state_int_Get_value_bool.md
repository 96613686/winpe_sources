# std::_Associated_state<int>::_Get_value(bool)

- ea: `0x180018b20`
- end: `0x180018c06`
- name: `?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018c10`

## callees

- `0x180011e50`
- `0x180012aec`
- `0x180018b20`
- `0x180019b2c`
- `0x18001a7fc`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x180018bac`
- `msvcp_win!_Cnd_wait` at `0x180018bac`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180018b8c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180018be9`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180018b8c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180018be9`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180018b61`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180018bbe`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180018b61`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180018bbe`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180018b7a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180018bd7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180018b7a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180018bd7`

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
0x180018b20  push    rbp
0x180018b22  push    rbx
0x180018b23  push    rsi
0x180018b24  push    rdi
0x180018b25  mov     rbp, rsp
0x180018b28  sub     rsp, 48h
0x180018b2c  mov     bl, dl
0x180018b2e  mov     rdi, rcx
0x180018b31  lea     rdx, [rcx+20h]
0x180018b35  lea     rcx, [rbp+var_18]
0x180018b39  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180018b3e  nop
0x180018b3f  lea     rsi, [rdi+0B8h]
0x180018b46  test    bl, bl
0x180018b48  jz      short loc_180018B5A
0x180018b4a  cmp     byte ptr [rsi], 0
0x180018b4d  jz      short loc_180018B5A
0x180018b4f  mov     ecx, 2
0x180018b54  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180018b5a  lea     rbx, [rdi+10h]
0x180018b5e  mov     rcx, rbx
0x180018b61  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180018b67  test    al, al
0x180018b69  jz      short loc_180018B93
0x180018b6b  xorps   xmm0, xmm0
0x180018b6e  movdqu  [rbp+var_28], xmm0
0x180018b73  mov     rdx, rbx
0x180018b76  lea     rcx, [rbp+var_28]
0x180018b7a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180018b80  lea     rax, [rbp+var_28]
0x180018b84  mov     [rbp+arg_0], rax
0x180018b88  lea     rcx, [rbp+var_28]
0x180018b8c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180018b92  nop
0x180018b93  mov     byte ptr [rsi], 1
0x180018b96  lea     rdx, [rbp+var_18]
0x180018b9a  mov     rcx, rdi
0x180018b9d  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x180018ba2  jmp     short loc_180018BB2
0x180018ba4  mov     rdx, [rbp+var_18]; _Mtx_t
0x180018ba8  lea     rcx, [rdi+70h]; _Cnd_t
0x180018bac  call    cs:__imp__Cnd_wait
0x180018bb2  cmp     dword ptr [rdi+0BCh], 0
0x180018bb9  jz      short loc_180018BA4
0x180018bbb  mov     rcx, rbx
0x180018bbe  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180018bc4  test    al, al
0x180018bc6  jz      short loc_180018BF0
0x180018bc8  xorps   xmm0, xmm0
0x180018bcb  movdqu  [rbp+var_28], xmm0
0x180018bd0  mov     rdx, rbx
0x180018bd3  lea     rcx, [rbp+var_28]
0x180018bd7  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180018bdd  lea     rax, [rbp+var_28]
0x180018be1  mov     [rbp+arg_0], rax
0x180018be5  lea     rcx, [rbp+var_28]
0x180018be9  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180018bef  nop
0x180018bf0  lea     rcx, [rbp+var_18]
0x180018bf4  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180018bf9  lea     rax, [rdi+0Ch]
0x180018bfd  add     rsp, 48h
0x180018c01  pop     rdi
0x180018c02  pop     rsi
0x180018c03  pop     rbx
0x180018c04  pop     rbp
0x180018c05  retn
```
