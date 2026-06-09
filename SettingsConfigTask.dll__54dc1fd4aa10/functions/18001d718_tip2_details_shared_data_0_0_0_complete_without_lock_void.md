# tip2::details::shared_data<0,0,0>::complete_without_lock(void)

- ea: `0x18001d718`
- end: `0x18001d760`
- name: `?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `72`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001871c`
- `0x18001c150`

## callees

- `0x1800045ec`
- `0x180005c0c`
- `0x18001d670`
- `0x18001d718`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<0,0,0>::complete_without_lock(__int64 a1)
{
  char v3; // [rsp+30h] [rbp+8h] BYREF

  wil::EnterCriticalSection(&v3, a1 + 192);
  *(_DWORD *)(a1 + 64) |= 0x300u;
  if ( *(_QWORD *)(a1 + 240) )
    tip2::details::shared_data<0,0,0>::complete_helper(a1, 2);
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v3);
}

```

## disassembly

```asm
0x18001d718  push    rbx
0x18001d71a  sub     rsp, 20h
0x18001d71e  mov     rbx, rcx
0x18001d721  lea     rdx, [rcx+0C0h]
0x18001d728  lea     rcx, [rsp+28h+arg_0]
0x18001d72d  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18001d732  or      dword ptr [rbx+40h], 300h
0x18001d739  cmp     qword ptr [rbx+0F0h], 0
0x18001d741  jz      short loc_18001D750
0x18001d743  mov     edx, 2
0x18001d748  mov     rcx, rbx
0x18001d74b  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001d750  lea     rcx, [rsp+28h+arg_0]
0x18001d755  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001d75a  add     rsp, 20h
0x18001d75e  pop     rbx
0x18001d75f  retn
```
