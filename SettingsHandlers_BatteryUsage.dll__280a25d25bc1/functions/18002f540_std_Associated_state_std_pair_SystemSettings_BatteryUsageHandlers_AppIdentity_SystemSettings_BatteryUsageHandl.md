# std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::_Get_value(bool)

- ea: `0x18002f540`
- end: `0x18002f62f`
- name: `?_Get_value@?$_Associated_state@U?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@std@@@std@@UEAAAEAU?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@2@_N@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002f640`

## callees

- `0x18002aa2c`
- `0x18002b518`
- `0x18002f540`
- `0x18002fba4`
- `0x180030700`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18002f5d5`
- `msvcp_win!_Cnd_wait` at `0x18002f5d5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002f5a0`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002f600`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002f5a0`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002f600`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002f587`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002f5e7`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002f587`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002f5e7`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002f5b2`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002f612`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002f5b2`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002f612`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::_Get_value(
        __int64 a1,
        char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  _Mtx_t v7[3]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, a1 + 152);
  v4 = (_BYTE *)(a1 + 304);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 136)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 136));
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::_Maybe_run_deferred_function(
    a1,
    v7);
  while ( !*(_DWORD *)(a1 + 308) )
    _Cnd_wait((_Cnd_t)(a1 + 232), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 136)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 136));
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 16;
}

```

## disassembly

```asm
0x18002f540  push    rbp
0x18002f542  push    rbx
0x18002f543  push    rsi
0x18002f544  push    rdi
0x18002f545  mov     rbp, rsp
0x18002f548  sub     rsp, 48h
0x18002f54c  mov     bl, dl
0x18002f54e  mov     rdi, rcx
0x18002f551  lea     rdx, [rcx+98h]
0x18002f558  lea     rcx, [rbp+var_18]
0x18002f55c  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18002f561  nop
0x18002f562  lea     rsi, [rdi+130h]
0x18002f569  test    bl, bl
0x18002f56b  jz      short loc_18002F57D
0x18002f56d  cmp     byte ptr [rsi], 0
0x18002f570  jz      short loc_18002F57D
0x18002f572  mov     ecx, 2
0x18002f577  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18002f57d  lea     rbx, [rdi+88h]
0x18002f584  mov     rcx, rbx
0x18002f587  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18002f58d  test    al, al
0x18002f58f  jz      short loc_18002F5B9
0x18002f591  xorps   xmm0, xmm0
0x18002f594  movdqu  [rbp+var_28], xmm0
0x18002f599  mov     rdx, rbx
0x18002f59c  lea     rcx, [rbp+var_28]
0x18002f5a0  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002f5a6  lea     rax, [rbp+var_28]
0x18002f5aa  mov     [rbp+arg_0], rax
0x18002f5ae  lea     rcx, [rbp+var_28]
0x18002f5b2  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18002f5b8  nop
0x18002f5b9  mov     byte ptr [rsi], 1
0x18002f5bc  lea     rdx, [rbp+var_18]
0x18002f5c0  mov     rcx, rdi
0x18002f5c3  call    ?_Maybe_run_deferred_function@?$_Associated_state@U?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@std@@@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x18002f5c8  jmp     short loc_18002F5DB
0x18002f5ca  mov     rdx, [rbp+var_18]; _Mtx_t
0x18002f5ce  lea     rcx, [rdi+0E8h]; _Cnd_t
0x18002f5d5  call    cs:__imp__Cnd_wait
0x18002f5db  cmp     dword ptr [rdi+134h], 0
0x18002f5e2  jz      short loc_18002F5CA
0x18002f5e4  mov     rcx, rbx
0x18002f5e7  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18002f5ed  test    al, al
0x18002f5ef  jz      short loc_18002F619
0x18002f5f1  xorps   xmm0, xmm0
0x18002f5f4  movdqu  [rbp+var_28], xmm0
0x18002f5f9  mov     rdx, rbx
0x18002f5fc  lea     rcx, [rbp+var_28]
0x18002f600  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002f606  lea     rax, [rbp+var_28]
0x18002f60a  mov     [rbp+arg_0], rax
0x18002f60e  lea     rcx, [rbp+var_28]
0x18002f612  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18002f618  nop
0x18002f619  lea     rcx, [rbp+var_18]
0x18002f61d  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18002f622  lea     rax, [rdi+10h]
0x18002f626  add     rsp, 48h
0x18002f62a  pop     rdi
0x18002f62b  pop     rsi
0x18002f62c  pop     rbx
0x18002f62d  pop     rbp
0x18002f62e  retn
```
