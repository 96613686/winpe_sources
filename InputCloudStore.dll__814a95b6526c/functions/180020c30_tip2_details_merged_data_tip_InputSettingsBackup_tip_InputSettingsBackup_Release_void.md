# tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>::Release(void)

- ea: `0x180020c30`
- end: `0x180020c68`
- name: `?Release@?$merged_data@U_tip_InputSettingsBackup@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b14c`
- `0x180025130`
- `0x180025c8c`

## callees

- `0x18001b188`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c55`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 82);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>::~merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180020c30  mov     [rsp+arg_0], rbx
0x180020c35  push    rdi
0x180020c36  sub     rsp, 20h
0x180020c3a  mov     rdi, rcx
0x180020c3d  or      ebx, 0FFFFFFFFh
0x180020c40  lock xadd [rcx+148h], ebx
0x180020c48  sub     ebx, 1
0x180020c4b  jnz     short loc_180020C5B
0x180020c4d  call    ??1?$merged_data@U_tip_InputSettingsBackup@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>::~merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>(void)
0x180020c52  mov     rcx, rdi; pv
0x180020c55  call    cs:__imp_CoTaskMemFree
0x180020c5b  mov     eax, ebx
0x180020c5d  mov     rbx, [rsp+28h+arg_0]
0x180020c62  add     rsp, 20h
0x180020c66  pop     rdi
0x180020c67  retn
```
