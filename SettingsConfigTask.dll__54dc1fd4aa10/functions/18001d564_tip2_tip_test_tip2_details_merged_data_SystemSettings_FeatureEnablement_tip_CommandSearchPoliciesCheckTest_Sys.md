# tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::complete(void)

- ea: `0x18001d564`
- end: `0x18001d5b2`
- name: `?complete@?$tip_test@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@QEAAXXZ`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018be0`
- `0x180018d58`

## callees

- `0x1800045ec`
- `0x180005c0c`
- `0x18001d564`
- `0x18001d5b8`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::complete(
        __int64 *a1)
{
  __int64 v1; // rbx
  __int64 result; // rax
  char v3; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  if ( *a1 )
  {
    wil::EnterCriticalSection(&v3, v1 + 200);
    *(_DWORD *)(v1 + 72) |= 0x300u;
    if ( *(_QWORD *)(v1 + 248) )
      tip2::details::shared_data<1,0,0>::complete_helper(v1 + 8, 2);
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v3);
  }
  return result;
}

```

## disassembly

```asm
0x18001d564  push    rbx
0x18001d566  sub     rsp, 20h
0x18001d56a  mov     rbx, [rcx]
0x18001d56d  test    rbx, rbx
0x18001d570  jz      short loc_18001D5AC
0x18001d572  lea     rdx, [rbx+0C8h]
0x18001d579  lea     rcx, [rsp+28h+arg_0]
0x18001d57e  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18001d583  or      dword ptr [rbx+48h], 300h
0x18001d58a  cmp     qword ptr [rbx+0F8h], 0
0x18001d592  jz      short loc_18001D5A2
0x18001d594  mov     edx, 2
0x18001d599  lea     rcx, [rbx+8]
0x18001d59d  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18001d5a2  lea     rcx, [rsp+28h+arg_0]
0x18001d5a7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001d5ac  add     rsp, 20h
0x18001d5b0  pop     rbx
0x18001d5b1  retn
```
