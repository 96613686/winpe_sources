# tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>::Release(void)

- ea: `0x1800490e8`
- end: `0x180049120`
- name: `?Release@?$merged_data@U_tip_DirectLaunchRegistrationTest@details@DirectLaunch@@U123@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003e630`
- `0x18004f1f4`
- `0x18004fbe8`

## callees

- `0x18003e8e8`
- `0x1800490e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004910d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004910d`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>::~merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x1800490e8  mov     [rsp+arg_0], rbx
0x1800490ed  push    rdi
0x1800490ee  sub     rsp, 20h
0x1800490f2  mov     rdi, rcx
0x1800490f5  or      ebx, 0FFFFFFFFh
0x1800490f8  lock xadd [rcx+118h], ebx
0x180049100  sub     ebx, 1
0x180049103  jnz     short loc_180049113
0x180049105  call    ??1?$merged_data@U_tip_DirectLaunchRegistrationTest@details@DirectLaunch@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>::~merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>(void)
0x18004910a  mov     rcx, rdi; pv
0x18004910d  call    cs:__imp_CoTaskMemFree
0x180049113  mov     eax, ebx
0x180049115  mov     rbx, [rsp+28h+arg_0]
0x18004911a  add     rsp, 20h
0x18004911e  pop     rdi
0x18004911f  retn
```
