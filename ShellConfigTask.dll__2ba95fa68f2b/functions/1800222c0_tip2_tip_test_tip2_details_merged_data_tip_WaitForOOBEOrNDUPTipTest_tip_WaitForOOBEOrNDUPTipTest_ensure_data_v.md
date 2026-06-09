# tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(void)

- ea: `0x1800222c0`
- end: `0x18002234c`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800146c0`
- `0x18001bde0`
- `0x18001f998`

## callees

- `0x180012bd4`
- `0x180013b6c`
- `0x1800222c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002230d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002230d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022338`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800222c0  mov     [rsp+arg_10], rbx
0x1800222c5  push    rdi
0x1800222c6  sub     rsp, 20h
0x1800222ca  cmp     qword ptr [rcx], 0
0x1800222ce  mov     rdi, rcx
0x1800222d1  jnz     short loc_18002233E
0x1800222d3  lea     rcx, [rsp+28h+pv]
0x1800222d8  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>,>(void)
0x1800222dd  mov     rdx, [rax]
0x1800222e0  mov     qword ptr [rax], 0
0x1800222e7  mov     rbx, [rdi]
0x1800222ea  mov     [rdi], rdx
0x1800222ed  test    rbx, rbx
0x1800222f0  jz      short loc_180022313
0x1800222f2  or      eax, 0FFFFFFFFh
0x1800222f5  lock xadd [rbx+118h], eax
0x1800222fd  cmp     eax, 1
0x180022300  jnz     short loc_180022313
0x180022302  mov     rcx, rbx
0x180022305  call    ??1?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(void)
0x18002230a  mov     rcx, rbx; pv
0x18002230d  call    cs:__imp_CoTaskMemFree
0x180022313  mov     rbx, [rsp+28h+pv]
0x180022318  test    rbx, rbx
0x18002231b  jz      short loc_18002233E
0x18002231d  or      eax, 0FFFFFFFFh
0x180022320  lock xadd [rbx+118h], eax
0x180022328  cmp     eax, 1
0x18002232b  jnz     short loc_18002233E
0x18002232d  mov     rcx, rbx
0x180022330  call    ??1?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(void)
0x180022335  mov     rcx, rbx; pv
0x180022338  call    cs:__imp_CoTaskMemFree
0x18002233e  mov     rbx, [rsp+28h+arg_10]
0x180022343  mov     rax, rdi
0x180022346  add     rsp, 20h
0x18002234a  pop     rdi
0x18002234b  retn
```
