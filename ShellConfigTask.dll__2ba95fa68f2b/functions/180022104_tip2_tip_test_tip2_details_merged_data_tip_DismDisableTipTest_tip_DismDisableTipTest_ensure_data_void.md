# tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(void)

- ea: `0x180022104`
- end: `0x180022190`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f1c4`

## callees

- `0x180012988`
- `0x180013a54`
- `0x180022104`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022151`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002217c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022151`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002217c`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180022104  mov     [rsp+arg_10], rbx
0x180022109  push    rdi
0x18002210a  sub     rsp, 20h
0x18002210e  cmp     qword ptr [rcx], 0
0x180022112  mov     rdi, rcx
0x180022115  jnz     short loc_180022182
0x180022117  lea     rcx, [rsp+28h+pv]
0x18002211c  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>,>(void)
0x180022121  mov     rdx, [rax]
0x180022124  mov     qword ptr [rax], 0
0x18002212b  mov     rbx, [rdi]
0x18002212e  mov     [rdi], rdx
0x180022131  test    rbx, rbx
0x180022134  jz      short loc_180022157
0x180022136  or      eax, 0FFFFFFFFh
0x180022139  lock xadd [rbx+118h], eax
0x180022141  cmp     eax, 1
0x180022144  jnz     short loc_180022157
0x180022146  mov     rcx, rbx
0x180022149  call    ??1?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>(void)
0x18002214e  mov     rcx, rbx; pv
0x180022151  call    cs:__imp_CoTaskMemFree
0x180022157  mov     rbx, [rsp+28h+pv]
0x18002215c  test    rbx, rbx
0x18002215f  jz      short loc_180022182
0x180022161  or      eax, 0FFFFFFFFh
0x180022164  lock xadd [rbx+118h], eax
0x18002216c  cmp     eax, 1
0x18002216f  jnz     short loc_180022182
0x180022171  mov     rcx, rbx
0x180022174  call    ??1?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>(void)
0x180022179  mov     rcx, rbx; pv
0x18002217c  call    cs:__imp_CoTaskMemFree
0x180022182  mov     rbx, [rsp+28h+arg_10]
0x180022187  mov     rax, rdi
0x18002218a  add     rsp, 20h
0x18002218e  pop     rdi
0x18002218f  retn
```
