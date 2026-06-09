# std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::_Set_exception(std::exception_ptr,bool)

- ea: `0x1800302bc`
- end: `0x18003036d`
- name: `?_Set_exception@?$_Associated_state@U?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@std@@@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180057a06`

## callees

- `0x18002aa2c`
- `0x18002b518`
- `0x1800302bc`
- `0x180030700`
- `0x18005a010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800302f4`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800302f4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030347`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003035c`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030347`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003035c`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180030324`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180030324`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::_Set_exception(
        _BYTE *a1,
        void *a2)
{
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v5[24]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v5, a1 + 152);
  v4 = 0;
  __ExceptionPtrCopy(&v4, a2);
  if ( a1[313] )
    std::_Throw_future_error2(3);
  __ExceptionPtrAssign(a1 + 136, &v4);
  (*(void (__fastcall **)(_BYTE *, _BYTE *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v5, 0);
  __ExceptionPtrDestroy(&v4);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v5);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x1800302bc  mov     [rsp+arg_10], rbx
0x1800302c1  mov     [rsp+arg_8], rdx
0x1800302c6  push    rdi
0x1800302c7  sub     rsp, 40h
0x1800302cb  mov     rdi, rdx
0x1800302ce  mov     rbx, rcx
0x1800302d1  lea     rdx, [rcx+98h]
0x1800302d8  lea     rcx, [rsp+48h+var_18]
0x1800302dd  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x1800302e2  nop
0x1800302e3  xorps   xmm0, xmm0
0x1800302e6  movdqu  [rsp+48h+var_28], xmm0
0x1800302ec  mov     rdx, rdi
0x1800302ef  lea     rcx, [rsp+48h+var_28]
0x1800302f4  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800302fa  lea     rax, [rsp+48h+var_28]
0x1800302ff  mov     [rsp+48h+arg_0], rax
0x180030304  cmp     byte ptr [rbx+139h], 0
0x18003030b  jz      short loc_180030318
0x18003030d  mov     ecx, 3
0x180030312  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180030318  lea     rcx, [rbx+88h]
0x18003031f  lea     rdx, [rsp+48h+var_28]
0x180030324  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18003032a  mov     rax, [rbx]
0x18003032d  xor     r8d, r8d
0x180030330  lea     rdx, [rsp+48h+var_18]
0x180030335  mov     rcx, rbx
0x180030338  mov     rax, [rax+28h]
0x18003033c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030341  nop
0x180030342  lea     rcx, [rsp+48h+var_28]
0x180030347  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003034d  nop
0x18003034e  lea     rcx, [rsp+48h+var_18]
0x180030353  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180030358  nop
0x180030359  mov     rcx, rdi
0x18003035c  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180030362  mov     rbx, [rsp+48h+arg_10]
0x180030367  add     rsp, 40h
0x18003036b  pop     rdi
0x18003036c  retn
```
