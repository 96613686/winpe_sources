# std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>(std::_Deleter_base<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>> *)

- ea: `0x18002a720`
- end: `0x18002a7cd`
- name: `??0?$_Associated_state@U?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@std@@@std@@QEAA@PEAU?$_Deleter_base@U?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@std@@@1@@Z`
- size: `173`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180028094`
- `0x1800317b8`

## callees

- `0x1800033a0`
- `0x180015074`
- `0x18002ac08`
- `0x18002ac2c`
- `0x18002addc`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002a781`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002a781`

## pseudocode

```c
__int64 __fastcall std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  SystemSettings::BatteryUsageHandlers::AppStaticInfo *v4; // rbx
  int v5; // edx
  __int64 result; // rax

  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::`vftable';
  v2 = a1 + 16;
  *(_OWORD *)v2 = 0;
  *(_OWORD *)(v2 + 16) = 0;
  *(_QWORD *)(v2 + 32) = 0;
  std::wstring::wstring();
  v4 = (SystemSettings::BatteryUsageHandlers::AppStaticInfo *)(v3 + 40);
  memset_0((void *)(v3 + 40), 0, 0x50u);
  SystemSettings::BatteryUsageHandlers::AppStaticInfo::AppStaticInfo(v4);
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  __ExceptionPtrCreate((void *)(a1 + 136));
  std::_Mutex_base::_Mutex_base((std::_Mutex_base *)(a1 + 152), v5);
  std::condition_variable::condition_variable((std::condition_variable *)(a1 + 232));
  *(_BYTE *)(a1 + 304) = 0;
  result = a1;
  *(_DWORD *)(a1 + 308) = 0;
  *(_WORD *)(a1 + 312) = 0;
  *(_BYTE *)(a1 + 314) = 0;
  *(_QWORD *)(a1 + 320) = 0;
  return result;
}

```

## disassembly

```asm
0x18002a720  mov     [rsp+arg_0], rbx
0x18002a725  push    rdi
0x18002a726  sub     rsp, 20h
0x18002a72a  mov     dword ptr [rcx+8], 1
0x18002a731  lea     rax, ??_7?$_Associated_state@U?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@std@@@std@@6B@; const std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::`vftable'
0x18002a738  mov     [rcx], rax
0x18002a73b  xorps   xmm0, xmm0
0x18002a73e  xor     eax, eax
0x18002a740  mov     rdi, rcx
0x18002a743  add     rcx, 10h
0x18002a747  movups  xmmword ptr [rcx], xmm0
0x18002a74a  movups  xmmword ptr [rcx+10h], xmm0
0x18002a74e  mov     [rcx+20h], rax
0x18002a752  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002a757  xor     edx, edx; Val
0x18002a759  lea     rbx, [rcx+28h]
0x18002a75d  mov     rcx, rbx; void *
0x18002a760  lea     r8d, [rdx+50h]; Size
0x18002a764  call    memset_0
0x18002a769  mov     rcx, rbx; this
0x18002a76c  call    ??0AppStaticInfo@BatteryUsageHandlers@SystemSettings@@QEAA@XZ; SystemSettings::BatteryUsageHandlers::AppStaticInfo::AppStaticInfo(void)
0x18002a771  lea     rcx, [rdi+88h]
0x18002a778  xor     ebx, ebx
0x18002a77a  mov     [rcx], rbx
0x18002a77d  mov     [rcx+8], rbx
0x18002a781  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002a787  lea     rcx, [rdi+98h]; this
0x18002a78e  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x18002a793  lea     rcx, [rdi+0E8h]; this
0x18002a79a  call    ??0condition_variable@std@@QEAA@XZ; std::condition_variable::condition_variable(void)
0x18002a79f  mov     [rdi+130h], bl
0x18002a7a5  mov     rax, rdi
0x18002a7a8  mov     [rdi+134h], ebx
0x18002a7ae  mov     [rdi+138h], bx
0x18002a7b5  mov     [rdi+13Ah], bl
0x18002a7bb  mov     [rdi+140h], rbx
0x18002a7c2  mov     rbx, [rsp+28h+arg_0]
0x18002a7c7  add     rsp, 20h
0x18002a7cb  pop     rdi
0x18002a7cc  retn
```
