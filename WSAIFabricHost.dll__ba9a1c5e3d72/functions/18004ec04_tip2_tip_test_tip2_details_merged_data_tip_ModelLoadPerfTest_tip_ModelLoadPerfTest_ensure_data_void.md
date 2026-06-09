# tip2::tip_test<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>::ensure_data(void)

- ea: `0x18004ec04`
- end: `0x18004ec90`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002fb70`
- `0x18003e364`

## callees

- `0x180030188`
- `0x180031a68`
- `0x18004ec04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec7c`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>::~merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>::~merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18004ec04  mov     [rsp+arg_10], rbx
0x18004ec09  push    rdi
0x18004ec0a  sub     rsp, 20h
0x18004ec0e  cmp     qword ptr [rcx], 0
0x18004ec12  mov     rdi, rcx
0x18004ec15  jnz     short loc_18004EC82
0x18004ec17  lea     rcx, [rsp+28h+pv]
0x18004ec1c  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>,>(void)
0x18004ec21  mov     rdx, [rax]
0x18004ec24  mov     qword ptr [rax], 0
0x18004ec2b  mov     rbx, [rdi]
0x18004ec2e  mov     [rdi], rdx
0x18004ec31  test    rbx, rbx
0x18004ec34  jz      short loc_18004EC57
0x18004ec36  or      eax, 0FFFFFFFFh
0x18004ec39  lock xadd [rbx+120h], eax
0x18004ec41  cmp     eax, 1
0x18004ec44  jnz     short loc_18004EC57
0x18004ec46  mov     rcx, rbx
0x18004ec49  call    ??1?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>::~merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>(void)
0x18004ec4e  mov     rcx, rbx; pv
0x18004ec51  call    cs:__imp_CoTaskMemFree
0x18004ec57  mov     rbx, [rsp+28h+pv]
0x18004ec5c  test    rbx, rbx
0x18004ec5f  jz      short loc_18004EC82
0x18004ec61  or      eax, 0FFFFFFFFh
0x18004ec64  lock xadd [rbx+120h], eax
0x18004ec6c  cmp     eax, 1
0x18004ec6f  jnz     short loc_18004EC82
0x18004ec71  mov     rcx, rbx
0x18004ec74  call    ??1?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>::~merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>(void)
0x18004ec79  mov     rcx, rbx; pv
0x18004ec7c  call    cs:__imp_CoTaskMemFree
0x18004ec82  mov     rbx, [rsp+28h+arg_10]
0x18004ec87  mov     rax, rdi
0x18004ec8a  add     rsp, 20h
0x18004ec8e  pop     rdi
0x18004ec8f  retn
```
