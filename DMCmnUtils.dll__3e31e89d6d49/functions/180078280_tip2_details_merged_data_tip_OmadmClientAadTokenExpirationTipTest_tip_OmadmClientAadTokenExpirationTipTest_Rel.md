# tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>::Release(void)

- ea: `0x180078280`
- end: `0x1800782bf`
- name: `?Release@?$merged_data@U_tip_OmadmClientAadTokenExpirationTipTest@@U1@@details@tip2@@AEAAKXZ`
- size: `63`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180074994`
- `0x180074cd8`
- `0x1800793fc`

## callees

- `0x1800749b4`
- `0x180078280`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800782a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800782a5`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 72);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>::~merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180078280  mov     [rsp+arg_0], rbx
0x180078285  push    rdi
0x180078286  sub     rsp, 20h
0x18007828a  mov     rdi, rcx
0x18007828d  or      ebx, 0FFFFFFFFh
0x180078290  lock xadd [rcx+120h], ebx
0x180078298  sub     ebx, 1
0x18007829b  jnz     short loc_1800782B1
0x18007829d  call    ??1?$merged_data@U_tip_OmadmClientAadTokenExpirationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>::~merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>(void)
0x1800782a2  mov     rcx, rdi; pv
0x1800782a5  call    cs:__imp_CoTaskMemFree
0x1800782ac  nop     dword ptr [rax+rax+00h]
0x1800782b1  mov     eax, ebx
0x1800782b3  mov     rbx, [rsp+28h+arg_0]
0x1800782b8  add     rsp, 20h
0x1800782bc  pop     rdi
0x1800782bd  retn
```
