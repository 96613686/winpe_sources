# std::_Associated_state<int>::_Get_value(bool)

- ea: `0x180010e30`
- end: `0x180010f16`
- name: `?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000e418`
- `0x18000e700`
- `0x180010e30`
- `0x180010f6c`
- `0x180011130`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180010e9c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180010ef9`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180010e9c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180010ef9`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180010e71`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180010ece`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180010e71`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180010ece`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180010e8a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180010ee7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180010e8a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180010ee7`
- `msvcp_win!_Cnd_wait` at `0x180010ebc`
- `msvcp_win!_Cnd_wait` at `0x180010ebc`

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
0x180010e30  push    rbp
0x180010e32  push    rbx
0x180010e33  push    rsi
0x180010e34  push    rdi
0x180010e35  mov     rbp, rsp
0x180010e38  sub     rsp, 48h
0x180010e3c  mov     bl, dl
0x180010e3e  mov     rdi, rcx
0x180010e41  lea     rdx, [rcx+20h]
0x180010e45  lea     rcx, [rbp+var_18]
0x180010e49  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180010e4e  nop
0x180010e4f  lea     rsi, [rdi+0B8h]
0x180010e56  test    bl, bl
0x180010e58  jz      short loc_180010E6A
0x180010e5a  cmp     byte ptr [rsi], 0
0x180010e5d  jz      short loc_180010E6A
0x180010e5f  mov     ecx, 2
0x180010e64  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180010e6a  lea     rbx, [rdi+10h]
0x180010e6e  mov     rcx, rbx
0x180010e71  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180010e77  test    al, al
0x180010e79  jz      short loc_180010EA3
0x180010e7b  xorps   xmm0, xmm0
0x180010e7e  movdqu  [rbp+var_28], xmm0
0x180010e83  mov     rdx, rbx
0x180010e86  lea     rcx, [rbp+var_28]
0x180010e8a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180010e90  lea     rax, [rbp+var_28]
0x180010e94  mov     [rbp+arg_0], rax
0x180010e98  lea     rcx, [rbp+var_28]
0x180010e9c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180010ea2  nop
0x180010ea3  mov     byte ptr [rsi], 1
0x180010ea6  lea     rdx, [rbp+var_18]
0x180010eaa  mov     rcx, rdi
0x180010ead  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x180010eb2  jmp     short loc_180010EC2
0x180010eb4  mov     rdx, [rbp+var_18]; _Mtx_t
0x180010eb8  lea     rcx, [rdi+70h]; _Cnd_t
0x180010ebc  call    cs:__imp__Cnd_wait
0x180010ec2  cmp     dword ptr [rdi+0BCh], 0
0x180010ec9  jz      short loc_180010EB4
0x180010ecb  mov     rcx, rbx
0x180010ece  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180010ed4  test    al, al
0x180010ed6  jz      short loc_180010F00
0x180010ed8  xorps   xmm0, xmm0
0x180010edb  movdqu  [rbp+var_28], xmm0
0x180010ee0  mov     rdx, rbx
0x180010ee3  lea     rcx, [rbp+var_28]
0x180010ee7  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180010eed  lea     rax, [rbp+var_28]
0x180010ef1  mov     [rbp+arg_0], rax
0x180010ef5  lea     rcx, [rbp+var_28]
0x180010ef9  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180010eff  nop
0x180010f00  lea     rcx, [rbp+var_18]
0x180010f04  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180010f09  lea     rax, [rdi+0Ch]
0x180010f0d  add     rsp, 48h
0x180010f11  pop     rdi
0x180010f12  pop     rsi
0x180010f13  pop     rbx
0x180010f14  pop     rbp
0x180010f15  retn
```
