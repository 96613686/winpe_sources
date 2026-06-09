# tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>::Release(void)

- ea: `0x180028180`
- end: `0x1800281b8`
- name: `?Release@?$merged_data@U_tip_InputSettingsRestore@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026d08`
- `0x180028614`
- `0x1800286b4`

## callees

- `0x180026d24`
- `0x180028180`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800281a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800281a5`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>::~merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180028180  mov     [rsp+arg_0], rbx
0x180028185  push    rdi
0x180028186  sub     rsp, 20h
0x18002818a  mov     rdi, rcx
0x18002818d  or      ebx, 0FFFFFFFFh
0x180028190  lock xadd [rcx+118h], ebx
0x180028198  sub     ebx, 1
0x18002819b  jnz     short loc_1800281AB
0x18002819d  call    ??1?$merged_data@U_tip_InputSettingsRestore@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>::~merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>(void)
0x1800281a2  mov     rcx, rdi; pv
0x1800281a5  call    cs:__imp_CoTaskMemFree
0x1800281ab  mov     eax, ebx
0x1800281ad  mov     rbx, [rsp+28h+arg_0]
0x1800281b2  add     rsp, 20h
0x1800281b6  pop     rdi
0x1800281b7  retn
```
