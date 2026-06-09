# tip2::details::shared_data<0,0,0>::complete_without_lock(void)

- ea: `0x18000d280`
- end: `0x18000d2c8`
- name: `?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `72`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b6f0`
- `0x18000b820`

## callees

- `0x18000b3ac`
- `0x18000bc18`
- `0x18000d178`
- `0x18000d280`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<0,0,0>::complete_without_lock(__int64 a1)
{
  char v3; // [rsp+30h] [rbp+8h] BYREF

  wil::EnterCriticalSection(&v3, a1 + 192);
  *(_DWORD *)(a1 + 64) |= 0x300u;
  if ( *(_QWORD *)(a1 + 240) )
    tip2::details::shared_data<0,0,0>::complete_helper(a1, 2u);
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v3);
}

```

## disassembly

```asm
0x18000d280  push    rbx
0x18000d282  sub     rsp, 20h
0x18000d286  mov     rbx, rcx
0x18000d289  lea     rdx, [rcx+0C0h]
0x18000d290  lea     rcx, [rsp+28h+arg_0]
0x18000d295  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18000d29a  or      dword ptr [rbx+40h], 300h
0x18000d2a1  cmp     qword ptr [rbx+0F0h], 0
0x18000d2a9  jz      short loc_18000D2B8
0x18000d2ab  mov     edx, 2
0x18000d2b0  mov     rcx, rbx
0x18000d2b3  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18000d2b8  lea     rcx, [rsp+28h+arg_0]
0x18000d2bd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000d2c2  add     rsp, 20h
0x18000d2c6  pop     rbx
0x18000d2c7  retn
```
