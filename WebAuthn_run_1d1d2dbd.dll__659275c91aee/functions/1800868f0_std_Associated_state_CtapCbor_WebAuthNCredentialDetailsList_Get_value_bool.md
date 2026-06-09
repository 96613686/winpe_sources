# std::_Associated_state<CtapCbor::WebAuthNCredentialDetailsList>::_Get_value(bool)

- ea: `0x1800868f0`
- end: `0x1800869d9`
- name: `?_Get_value@?$_Associated_state@UWebAuthNCredentialDetailsList@CtapCbor@@@std@@UEAAAEAUWebAuthNCredentialDetailsList@CtapCbor@@_N@Z`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180024938`
- `0x1800462b4`
- `0x1800868f0`
- `0x1800872ac`
- `0x1800877b4`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18008697f`
- `msvcp_win!_Cnd_wait` at `0x18008697f`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18008695c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800869bc`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18008695c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800869bc`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180086931`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180086991`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180086931`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180086991`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18008694a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800869aa`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18008694a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800869aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<CtapCbor::WebAuthNCredentialDetailsList>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  _Mtx_t v7[3]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, a1 + 56);
  v4 = (_BYTE *)(a1 + 208);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 40)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 40));
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state<CtapCbor::WebAuthNCredentialDetailsList>::_Maybe_run_deferred_function(a1, v7);
  while ( !*(_DWORD *)(a1 + 212) )
    _Cnd_wait((_Cnd_t)(a1 + 136), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 40)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 40));
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 16;
}

```

## disassembly

```asm
0x1800868f0  push    rbp
0x1800868f2  push    rbx
0x1800868f3  push    rsi
0x1800868f4  push    rdi
0x1800868f5  mov     rbp, rsp
0x1800868f8  sub     rsp, 48h
0x1800868fc  mov     bl, dl
0x1800868fe  mov     rdi, rcx
0x180086901  lea     rdx, [rcx+38h]
0x180086905  lea     rcx, [rbp+var_18]
0x180086909  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18008690e  nop
0x18008690f  lea     rsi, [rdi+0D0h]
0x180086916  test    bl, bl
0x180086918  jz      short loc_18008692A
0x18008691a  cmp     byte ptr [rsi], 0
0x18008691d  jz      short loc_18008692A
0x18008691f  mov     ecx, 2
0x180086924  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18008692a  lea     rbx, [rdi+28h]
0x18008692e  mov     rcx, rbx
0x180086931  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180086937  test    al, al
0x180086939  jz      short loc_180086963
0x18008693b  xorps   xmm0, xmm0
0x18008693e  movdqu  [rbp+var_28], xmm0
0x180086943  mov     rdx, rbx
0x180086946  lea     rcx, [rbp+var_28]
0x18008694a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180086950  lea     rax, [rbp+var_28]
0x180086954  mov     [rbp+arg_0], rax
0x180086958  lea     rcx, [rbp+var_28]
0x18008695c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180086962  nop
0x180086963  mov     byte ptr [rsi], 1
0x180086966  lea     rdx, [rbp+var_18]
0x18008696a  mov     rcx, rdi
0x18008696d  call    ?_Maybe_run_deferred_function@?$_Associated_state@UWebAuthNCredentialDetailsList@CtapCbor@@@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<CtapCbor::WebAuthNCredentialDetailsList>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x180086972  jmp     short loc_180086985
0x180086974  mov     rdx, [rbp+var_18]; _Mtx_t
0x180086978  lea     rcx, [rdi+88h]; _Cnd_t
0x18008697f  call    cs:__imp__Cnd_wait
0x180086985  cmp     dword ptr [rdi+0D4h], 0
0x18008698c  jz      short loc_180086974
0x18008698e  mov     rcx, rbx
0x180086991  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180086997  test    al, al
0x180086999  jz      short loc_1800869C3
0x18008699b  xorps   xmm0, xmm0
0x18008699e  movdqu  [rbp+var_28], xmm0
0x1800869a3  mov     rdx, rbx
0x1800869a6  lea     rcx, [rbp+var_28]
0x1800869aa  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800869b0  lea     rax, [rbp+var_28]
0x1800869b4  mov     [rbp+arg_0], rax
0x1800869b8  lea     rcx, [rbp+var_28]
0x1800869bc  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800869c2  nop
0x1800869c3  lea     rcx, [rbp+var_18]
0x1800869c7  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1800869cc  lea     rax, [rdi+10h]
0x1800869d0  add     rsp, 48h
0x1800869d4  pop     rdi
0x1800869d5  pop     rsi
0x1800869d6  pop     rbx
0x1800869d7  pop     rbp
0x1800869d8  retn
```
