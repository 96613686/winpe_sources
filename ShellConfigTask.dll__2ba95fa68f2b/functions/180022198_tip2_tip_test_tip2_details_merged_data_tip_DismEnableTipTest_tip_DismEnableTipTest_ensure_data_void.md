# tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(void)

- ea: `0x180022198`
- end: `0x180022224`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001448c`
- `0x18001b7fc`

## callees

- `0x180012a4c`
- `0x180013ae0`
- `0x180022198`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022210`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180022198  mov     [rsp+arg_10], rbx
0x18002219d  push    rdi
0x18002219e  sub     rsp, 20h
0x1800221a2  cmp     qword ptr [rcx], 0
0x1800221a6  mov     rdi, rcx
0x1800221a9  jnz     short loc_180022216
0x1800221ab  lea     rcx, [rsp+28h+pv]
0x1800221b0  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>,>(void)
0x1800221b5  mov     rdx, [rax]
0x1800221b8  mov     qword ptr [rax], 0
0x1800221bf  mov     rbx, [rdi]
0x1800221c2  mov     [rdi], rdx
0x1800221c5  test    rbx, rbx
0x1800221c8  jz      short loc_1800221EB
0x1800221ca  or      eax, 0FFFFFFFFh
0x1800221cd  lock xadd [rbx+118h], eax
0x1800221d5  cmp     eax, 1
0x1800221d8  jnz     short loc_1800221EB
0x1800221da  mov     rcx, rbx
0x1800221dd  call    ??1?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(void)
0x1800221e2  mov     rcx, rbx; pv
0x1800221e5  call    cs:__imp_CoTaskMemFree
0x1800221eb  mov     rbx, [rsp+28h+pv]
0x1800221f0  test    rbx, rbx
0x1800221f3  jz      short loc_180022216
0x1800221f5  or      eax, 0FFFFFFFFh
0x1800221f8  lock xadd [rbx+118h], eax
0x180022200  cmp     eax, 1
0x180022203  jnz     short loc_180022216
0x180022205  mov     rcx, rbx
0x180022208  call    ??1?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(void)
0x18002220d  mov     rcx, rbx; pv
0x180022210  call    cs:__imp_CoTaskMemFree
0x180022216  mov     rbx, [rsp+28h+arg_10]
0x18002221b  mov     rax, rdi
0x18002221e  add     rsp, 20h
0x180022222  pop     rdi
0x180022223  retn
```
