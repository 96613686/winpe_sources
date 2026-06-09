# tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>::Release(void)

- ea: `0x1800433ac`
- end: `0x1800433e4`
- name: `?Release@?$merged_data@U_tip_EnergySaverToggleTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800403c4`
- `0x1800450fc`
- `0x180045124`

## callees

- `0x1800403e0`
- `0x1800433ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800433d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800433d1`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>::~merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x1800433ac  mov     [rsp+arg_0], rbx
0x1800433b1  push    rdi
0x1800433b2  sub     rsp, 20h
0x1800433b6  mov     rdi, rcx
0x1800433b9  or      ebx, 0FFFFFFFFh
0x1800433bc  lock xadd [rcx+118h], ebx
0x1800433c4  sub     ebx, 1
0x1800433c7  jnz     short loc_1800433D7
0x1800433c9  call    ??1?$merged_data@U_tip_EnergySaverToggleTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>::~merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>(void)
0x1800433ce  mov     rcx, rdi; pv
0x1800433d1  call    cs:__imp_CoTaskMemFree
0x1800433d7  mov     eax, ebx
0x1800433d9  mov     rbx, [rsp+28h+arg_0]
0x1800433de  add     rsp, 20h
0x1800433e2  pop     rdi
0x1800433e3  retn
```
