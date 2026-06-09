# NgcUtils::ProcessPriorityManager::~ProcessPriorityManager(void)

- ea: `0x180019ad4`
- end: `0x180019b23`
- name: `??1ProcessPriorityManager@NgcUtils@@AEAA@XZ`
- size: `79`
- prototype: `void __fastcall(NgcUtils::ProcessPriorityManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180019ac0`

## callees

- `0x180019ad4`
- `0x180028d80`
- `0x18003b80c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019af9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019af9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019ae9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019ae9`

## pseudocode

```c
void __fastcall NgcUtils::ProcessPriorityManager::~ProcessPriorityManager(PTP_TIMER *this)
{
  struct wil::details::wnf_subscription_state_base *v2; // rdx
  wil::details *v3; // rcx

  SetThreadpoolTimer(this[1], 0, 0, 0);
  CloseThreadpoolTimer(this[1]);
  wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(this + 4);
  v3 = this[2];
  if ( v3 )
    wil::details::delete_wnf_subscription_state(v3, v2);
}

```

## disassembly

```asm
0x180019ad4  push    rbx
0x180019ad6  sub     rsp, 20h
0x180019ada  mov     rbx, rcx
0x180019add  xor     r9d, r9d; msWindowLength
0x180019ae0  mov     rcx, [rcx+8]; pti
0x180019ae4  xor     r8d, r8d; msPeriod
0x180019ae7  xor     edx, edx; pftDueTime
0x180019ae9  call    cs:__imp_SetThreadpoolTimer
0x180019af0  nop     dword ptr [rax+rax+00h]
0x180019af5  mov     rcx, [rbx+8]; pti
0x180019af9  call    cs:__imp_CloseThreadpoolTimer
0x180019b00  nop     dword ptr [rax+rax+00h]
0x180019b05  lea     rcx, [rbx+20h]
0x180019b09  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AKPEAX@Z$1?PowerSettingUnregisterNotification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180019b0e  mov     rcx, [rbx+10h]; this
0x180019b12  test    rcx, rcx
0x180019b15  jz      short loc_180019B1C
0x180019b17  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x180019b1c  add     rsp, 20h
0x180019b20  pop     rbx
0x180019b21  retn
```
