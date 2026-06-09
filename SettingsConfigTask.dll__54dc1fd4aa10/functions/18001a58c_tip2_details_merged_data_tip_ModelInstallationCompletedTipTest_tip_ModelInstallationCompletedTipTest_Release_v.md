# tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>::Release(void)

- ea: `0x18001a58c`
- end: `0x18001a5c4`
- name: `?Release@?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800125b0`
- `0x18001e14c`
- `0x18002000c`

## callees

- `0x1800126e8`
- `0x18001a58c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5b1`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>::~merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18001a58c  mov     [rsp+arg_0], rbx
0x18001a591  push    rdi
0x18001a592  sub     rsp, 20h
0x18001a596  mov     rdi, rcx
0x18001a599  or      ebx, 0FFFFFFFFh
0x18001a59c  lock xadd [rcx+118h], ebx
0x18001a5a4  sub     ebx, 1
0x18001a5a7  jnz     short loc_18001A5B7
0x18001a5a9  call    ??1?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>::~merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>(void)
0x18001a5ae  mov     rcx, rdi; pv
0x18001a5b1  call    cs:__imp_CoTaskMemFree
0x18001a5b7  mov     eax, ebx
0x18001a5b9  mov     rbx, [rsp+28h+arg_0]
0x18001a5be  add     rsp, 20h
0x18001a5c2  pop     rdi
0x18001a5c3  retn
```
