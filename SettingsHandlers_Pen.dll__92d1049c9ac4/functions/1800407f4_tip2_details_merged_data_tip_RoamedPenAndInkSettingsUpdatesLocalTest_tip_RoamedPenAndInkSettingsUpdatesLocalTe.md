# tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>::Release(void)

- ea: `0x1800407f4`
- end: `0x18004082c`
- name: `?Release@?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ec40`
- `0x180042228`
- `0x180042cc4`

## callees

- `0x18003ecbc`
- `0x1800407f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040819`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040819`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 80);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>::~merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x1800407f4  mov     [rsp+arg_0], rbx
0x1800407f9  push    rdi
0x1800407fa  sub     rsp, 20h
0x1800407fe  mov     rdi, rcx
0x180040801  or      ebx, 0FFFFFFFFh
0x180040804  lock xadd [rcx+140h], ebx
0x18004080c  sub     ebx, 1
0x18004080f  jnz     short loc_18004081F
0x180040811  call    ??1?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>::~merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>(void)
0x180040816  mov     rcx, rdi; pv
0x180040819  call    cs:__imp_CoTaskMemFree
0x18004081f  mov     eax, ebx
0x180040821  mov     rbx, [rsp+28h+arg_0]
0x180040826  add     rsp, 20h
0x18004082a  pop     rdi
0x18004082b  retn
```
