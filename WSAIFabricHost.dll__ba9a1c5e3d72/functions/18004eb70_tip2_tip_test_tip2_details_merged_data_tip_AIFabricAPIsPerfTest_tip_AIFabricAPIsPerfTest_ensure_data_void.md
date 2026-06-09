# tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(void)

- ea: `0x18004eb70`
- end: `0x18004ebfc`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f8ec`
- `0x18002f924`
- `0x180032cec`
- `0x180040a70`
- `0x180054928`
- `0x180075dd0`
- `0x1800765d0`
- `0x180076a40`
- `0x180076ec0`
- `0x180077570`
- `0x180077c10`

## callees

- `0x18002fec4`
- `0x1800318c4`
- `0x18004eb70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ebbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ebe8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ebbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ebe8`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION **v2; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (struct _RTL_CRITICAL_SECTION **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v4);
      CoTaskMemFree(v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18004eb70  mov     [rsp+arg_10], rbx
0x18004eb75  push    rdi
0x18004eb76  sub     rsp, 20h
0x18004eb7a  cmp     qword ptr [rcx], 0
0x18004eb7e  mov     rdi, rcx
0x18004eb81  jnz     short loc_18004EBEE
0x18004eb83  lea     rcx, [rsp+28h+pv]
0x18004eb88  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>,>(void)
0x18004eb8d  mov     rdx, [rax]
0x18004eb90  mov     qword ptr [rax], 0
0x18004eb97  mov     rbx, [rdi]
0x18004eb9a  mov     [rdi], rdx
0x18004eb9d  test    rbx, rbx
0x18004eba0  jz      short loc_18004EBC3
0x18004eba2  or      eax, 0FFFFFFFFh
0x18004eba5  lock xadd [rbx+120h], eax
0x18004ebad  cmp     eax, 1
0x18004ebb0  jnz     short loc_18004EBC3
0x18004ebb2  mov     rcx, rbx
0x18004ebb5  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x18004ebba  mov     rcx, rbx; pv
0x18004ebbd  call    cs:__imp_CoTaskMemFree
0x18004ebc3  mov     rbx, [rsp+28h+pv]
0x18004ebc8  test    rbx, rbx
0x18004ebcb  jz      short loc_18004EBEE
0x18004ebcd  or      eax, 0FFFFFFFFh
0x18004ebd0  lock xadd [rbx+120h], eax
0x18004ebd8  cmp     eax, 1
0x18004ebdb  jnz     short loc_18004EBEE
0x18004ebdd  mov     rcx, rbx
0x18004ebe0  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x18004ebe5  mov     rcx, rbx; pv
0x18004ebe8  call    cs:__imp_CoTaskMemFree
0x18004ebee  mov     rbx, [rsp+28h+arg_10]
0x18004ebf3  mov     rax, rdi
0x18004ebf6  add     rsp, 20h
0x18004ebfa  pop     rdi
0x18004ebfb  retn
```
