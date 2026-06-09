# tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::Release(void)

- ea: `0x18001a5cc`
- end: `0x18001a604`
- name: `?Release@?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800125cc`
- `0x18001e1ac`
- `0x180020034`

## callees

- `0x180012718`
- `0x18001a5cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5f1`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::~merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18001a5cc  mov     [rsp+arg_0], rbx
0x18001a5d1  push    rdi
0x18001a5d2  sub     rsp, 20h
0x18001a5d6  mov     rdi, rcx
0x18001a5d9  or      ebx, 0FFFFFFFFh
0x18001a5dc  lock xadd [rcx+118h], ebx
0x18001a5e4  sub     ebx, 1
0x18001a5e7  jnz     short loc_18001A5F7
0x18001a5e9  call    ??1?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::~merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>(void)
0x18001a5ee  mov     rcx, rdi; pv
0x18001a5f1  call    cs:__imp_CoTaskMemFree
0x18001a5f7  mov     eax, ebx
0x18001a5f9  mov     rbx, [rsp+28h+arg_0]
0x18001a5fe  add     rsp, 20h
0x18001a602  pop     rdi
0x18001a603  retn
```
