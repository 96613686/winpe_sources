# tip2::tip_test<tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>>::ensure_data(void)

- ea: `0x18004ec98`
- end: `0x18004ed24`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_QueryBlocklistedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_QueryBlocklistedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002fc30`
- `0x18003f5d0`

## callees

- `0x180030250`
- `0x180031af4`
- `0x18004ec98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ece5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ed10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ece5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ed10`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>::~merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>::~merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18004ec98  mov     [rsp+arg_10], rbx
0x18004ec9d  push    rdi
0x18004ec9e  sub     rsp, 20h
0x18004eca2  cmp     qword ptr [rcx], 0
0x18004eca6  mov     rdi, rcx
0x18004eca9  jnz     short loc_18004ED16
0x18004ecab  lea     rcx, [rsp+28h+pv]
0x18004ecb0  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_QueryBlocklistedTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_QueryBlocklistedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>,>(void)
0x18004ecb5  mov     rdx, [rax]
0x18004ecb8  mov     qword ptr [rax], 0
0x18004ecbf  mov     rbx, [rdi]
0x18004ecc2  mov     [rdi], rdx
0x18004ecc5  test    rbx, rbx
0x18004ecc8  jz      short loc_18004ECEB
0x18004ecca  or      eax, 0FFFFFFFFh
0x18004eccd  lock xadd [rbx+118h], eax
0x18004ecd5  cmp     eax, 1
0x18004ecd8  jnz     short loc_18004ECEB
0x18004ecda  mov     rcx, rbx
0x18004ecdd  call    ??1?$merged_data@U_tip_QueryBlocklistedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>::~merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>(void)
0x18004ece2  mov     rcx, rbx; pv
0x18004ece5  call    cs:__imp_CoTaskMemFree
0x18004eceb  mov     rbx, [rsp+28h+pv]
0x18004ecf0  test    rbx, rbx
0x18004ecf3  jz      short loc_18004ED16
0x18004ecf5  or      eax, 0FFFFFFFFh
0x18004ecf8  lock xadd [rbx+118h], eax
0x18004ed00  cmp     eax, 1
0x18004ed03  jnz     short loc_18004ED16
0x18004ed05  mov     rcx, rbx
0x18004ed08  call    ??1?$merged_data@U_tip_QueryBlocklistedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>::~merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>(void)
0x18004ed0d  mov     rcx, rbx; pv
0x18004ed10  call    cs:__imp_CoTaskMemFree
0x18004ed16  mov     rbx, [rsp+28h+arg_10]
0x18004ed1b  mov     rax, rdi
0x18004ed1e  add     rsp, 20h
0x18004ed22  pop     rdi
0x18004ed23  retn
```
