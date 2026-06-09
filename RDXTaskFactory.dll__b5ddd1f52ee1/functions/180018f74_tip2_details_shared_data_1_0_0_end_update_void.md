# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x180018f74`
- end: `0x1800190a4`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180016f98`
- `0x180016fd0`
- `0x180019e98`
- `0x180036884`
- `0x1800368bc`
- `0x1800368f4`
- `0x18003692c`

## callees

- `0x180003390`
- `0x18000e3bc`
- `0x180018de0`
- `0x180018f74`
- `0x18001ac8c`
- `0x18001b628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001907e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001907e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001906b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001906b`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int128 v4; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h]
  __int128 v6; // [rsp+40h] [rbp-C0h]
  void *v7; // [rsp+50h] [rbp-B0h] BYREF
  char v8; // [rsp+58h] [rbp-A8h]
  int v9; // [rsp+59h] [rbp-A7h] BYREF
  char v10; // [rsp+5Dh] [rbp-A3h]
  char v11; // [rsp+5Eh] [rbp-A2h] BYREF
  char v12; // [rsp+859h] [rbp+759h] BYREF
  int *v13; // [rsp+860h] [rbp+760h]
  char *v14; // [rsp+868h] [rbp+768h]
  char *v15; // [rsp+870h] [rbp+770h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v7 = 0;
    v8 = 0;
    v13 = &v9;
    v9 = -2143256512;
    v15 = &v12;
    v10 = 0;
    v14 = &v11;
    v4 = 0;
    *(_OWORD *)pv = 0;
    v6 = 0;
    v2 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v7, 1);
    TestUnlockData(*(_QWORD *)(a1 + 240), v3, v2, &v4);
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( pv[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v4);
    else
      *(_DWORD *)(a1 + 184) = pv[0];
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v7);
    CoTaskMemFree(pv[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x180018f74  mov     [rsp-8+arg_8], rbx
0x180018f79  push    rbp
0x180018f7a  lea     rbp, [rsp-790h]
0x180018f82  sub     rsp, 890h
0x180018f89  mov     rax, cs:__security_cookie
0x180018f90  xor     rax, rsp
0x180018f93  mov     [rbp+790h+var_10], rax
0x180018f9a  bts     dword ptr [rcx+40h], 0Bh
0x180018f9f  mov     rbx, rcx
0x180018fa2  cmp     qword ptr [rcx+0F0h], 0
0x180018faa  jz      loc_180019071
0x180018fb0  test    dword ptr [rcx+40h], 100h
0x180018fb7  jnz     loc_180019071
0x180018fbd  xorps   xmm0, xmm0
0x180018fc0  mov     [rsp+890h+var_840], 0
0x180018fc9  lea     rax, [rsp+890h+var_837]
0x180018fce  mov     [rsp+890h+var_838], 0
0x180018fd3  mov     [rbp+790h+var_30], rax
0x180018fda  lea     rdx, [rsp+890h+var_840]
0x180018fdf  lea     rax, [rbp+790h+var_37]
0x180018fe6  mov     [rsp+890h+var_837], 80408040h
0x180018fee  mov     [rbp+790h+var_20], rax
0x180018ff5  mov     r8d, 1
0x180018ffb  lea     rax, [rsp+890h+var_832]
0x180019000  mov     [rsp+890h+var_833], 0
0x180019005  mov     [rbp+790h+var_28], rax
0x18001900c  movups  [rsp+890h+var_870], xmm0
0x180019011  movups  xmmword ptr [rsp+890h+pv], xmm0
0x180019016  movups  [rsp+890h+var_850], xmm0
0x18001901b  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180019020  mov     rcx, [rbx+0F0h]
0x180019027  lea     r9, [rsp+890h+var_870]
0x18001902c  mov     r8, rax
0x18001902f  call    TestUnlockData
0x180019034  mov     eax, dword ptr [rsp+890h+pv+4]
0x180019038  or      [rbx+40h], eax
0x18001903b  cmp     [rsp+890h+pv+8], 0
0x180019041  jz      short loc_180019052
0x180019043  lea     rdx, [rsp+890h+var_870]
0x180019048  mov     rcx, rbx
0x18001904b  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180019050  jmp     short loc_18001905C
0x180019052  mov     eax, dword ptr [rsp+890h+pv]
0x180019056  mov     [rbx+0B8h], eax
0x18001905c  lea     rcx, [rsp+890h+var_840]
0x180019061  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180019066  mov     rcx, [rsp+890h+pv+8]; pv
0x18001906b  call    cs:__imp_CoTaskMemFree
0x180019071  dec     dword ptr [rbx+0E8h]
0x180019077  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18001907e  call    cs:__imp_LeaveCriticalSection
0x180019084  mov     rcx, [rbp+790h+var_10]
0x18001908b  xor     rcx, rsp; StackCookie
0x18001908e  call    __security_check_cookie
0x180019093  mov     rbx, [rsp+890h+arg_8]
0x18001909b  add     rsp, 890h
0x1800190a2  pop     rbp
0x1800190a3  retn
```
