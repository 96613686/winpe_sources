# tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data(void)

- ea: `0x18002222c`
- end: `0x1800222b8`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014760`
- `0x18001be80`
- `0x18001f604`

## callees

- `0x180012b10`
- `0x180013b6c`
- `0x18002222c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222a4`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data(
        __int64 *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
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
0x18002222c  mov     [rsp+arg_10], rbx
0x180022231  push    rdi
0x180022232  sub     rsp, 20h
0x180022236  cmp     qword ptr [rcx], 0
0x18002223a  mov     rdi, rcx
0x18002223d  jnz     short loc_1800222AA
0x18002223f  lea     rcx, [rsp+28h+pv]
0x180022244  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,>(void)
0x180022249  mov     rdx, [rax]
0x18002224c  mov     qword ptr [rax], 0
0x180022253  mov     rbx, [rdi]
0x180022256  mov     [rdi], rdx
0x180022259  test    rbx, rbx
0x18002225c  jz      short loc_18002227F
0x18002225e  or      eax, 0FFFFFFFFh
0x180022261  lock xadd [rbx+118h], eax
0x180022269  cmp     eax, 1
0x18002226c  jnz     short loc_18002227F
0x18002226e  mov     rcx, rbx
0x180022271  call    ??1?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(void)
0x180022276  mov     rcx, rbx; pv
0x180022279  call    cs:__imp_CoTaskMemFree
0x18002227f  mov     rbx, [rsp+28h+pv]
0x180022284  test    rbx, rbx
0x180022287  jz      short loc_1800222AA
0x180022289  or      eax, 0FFFFFFFFh
0x18002228c  lock xadd [rbx+118h], eax
0x180022294  cmp     eax, 1
0x180022297  jnz     short loc_1800222AA
0x180022299  mov     rcx, rbx
0x18002229c  call    ??1?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(void)
0x1800222a1  mov     rcx, rbx; pv
0x1800222a4  call    cs:__imp_CoTaskMemFree
0x1800222aa  mov     rbx, [rsp+28h+arg_10]
0x1800222af  mov     rax, rdi
0x1800222b2  add     rsp, 20h
0x1800222b6  pop     rdi
0x1800222b7  retn
```
