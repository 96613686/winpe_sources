# tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>::Release(void)

- ea: `0x180014c34`
- end: `0x180014c6c`
- name: `?Release@?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000de84`
- `0x18002d0e4`
- `0x18002d45c`
- `0x18004a43c`

## callees

- `0x18000dff0`
- `0x180014c34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014c59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014c59`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 78);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>::~merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180014c34  mov     [rsp+arg_0], rbx
0x180014c39  push    rdi
0x180014c3a  sub     rsp, 20h
0x180014c3e  mov     rdi, rcx
0x180014c41  or      ebx, 0FFFFFFFFh
0x180014c44  lock xadd [rcx+138h], ebx
0x180014c4c  sub     ebx, 1
0x180014c4f  jnz     short loc_180014C5F
0x180014c51  call    ??1?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>::~merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>(void)
0x180014c56  mov     rcx, rdi; pv
0x180014c59  call    cs:__imp_CoTaskMemFree
0x180014c5f  mov     eax, ebx
0x180014c61  mov     rbx, [rsp+28h+arg_0]
0x180014c66  add     rsp, 20h
0x180014c6a  pop     rdi
0x180014c6b  retn
```
