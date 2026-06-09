# tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::Release(void)

- ea: `0x18000c8bc`
- end: `0x18000c8f4`
- name: `?Release@?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(volatile signed __int32 *pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b220`
- `0x18000d550`
- `0x18000e2d4`

## callees

- `0x18000b27c`
- `0x18000c8bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c8e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c8e1`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 74);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::~merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>(pv);
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c8bc  mov     [rsp+arg_0], rbx
0x18000c8c1  push    rdi
0x18000c8c2  sub     rsp, 20h
0x18000c8c6  mov     rdi, rcx
0x18000c8c9  or      ebx, 0FFFFFFFFh
0x18000c8cc  lock xadd [rcx+128h], ebx
0x18000c8d4  sub     ebx, 1
0x18000c8d7  jnz     short loc_18000C8E7
0x18000c8d9  call    ??1?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::~merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>(void)
0x18000c8de  mov     rcx, rdi; pv
0x18000c8e1  call    cs:__imp_CoTaskMemFree
0x18000c8e7  mov     eax, ebx
0x18000c8e9  mov     rbx, [rsp+28h+arg_0]
0x18000c8ee  add     rsp, 20h
0x18000c8f2  pop     rdi
0x18000c8f3  retn
```
