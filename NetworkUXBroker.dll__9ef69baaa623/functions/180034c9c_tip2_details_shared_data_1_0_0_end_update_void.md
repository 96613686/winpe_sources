# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x180034c9c`
- end: `0x180034dcc`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003468c`

## callees

- `0x180002520`
- `0x18001b8ac`
- `0x18001d88c`
- `0x180034b08`
- `0x180034c9c`
- `0x180037158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034da6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d93`

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
0x180034c9c  mov     [rsp-8+arg_8], rbx
0x180034ca1  push    rbp
0x180034ca2  lea     rbp, [rsp-790h]
0x180034caa  sub     rsp, 890h
0x180034cb1  mov     rax, cs:__security_cookie
0x180034cb8  xor     rax, rsp
0x180034cbb  mov     [rbp+790h+var_10], rax
0x180034cc2  bts     dword ptr [rcx+40h], 0Bh
0x180034cc7  mov     rbx, rcx
0x180034cca  cmp     qword ptr [rcx+0F0h], 0
0x180034cd2  jz      loc_180034D99
0x180034cd8  test    dword ptr [rcx+40h], 100h
0x180034cdf  jnz     loc_180034D99
0x180034ce5  xorps   xmm0, xmm0
0x180034ce8  mov     [rsp+890h+var_840], 0
0x180034cf1  lea     rax, [rsp+890h+var_837]
0x180034cf6  mov     [rsp+890h+var_838], 0
0x180034cfb  mov     [rbp+790h+var_30], rax
0x180034d02  lea     rdx, [rsp+890h+var_840]
0x180034d07  lea     rax, [rbp+790h+var_37]
0x180034d0e  mov     [rsp+890h+var_837], 80408040h
0x180034d16  mov     [rbp+790h+var_20], rax
0x180034d1d  mov     r8d, 1
0x180034d23  lea     rax, [rsp+890h+var_832]
0x180034d28  mov     [rsp+890h+var_833], 0
0x180034d2d  mov     [rbp+790h+var_28], rax
0x180034d34  movups  [rsp+890h+var_870], xmm0
0x180034d39  movups  xmmword ptr [rsp+890h+pv], xmm0
0x180034d3e  movups  [rsp+890h+var_850], xmm0
0x180034d43  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180034d48  mov     rcx, [rbx+0F0h]
0x180034d4f  lea     r9, [rsp+890h+var_870]
0x180034d54  mov     r8, rax
0x180034d57  call    TestUnlockData
0x180034d5c  mov     eax, dword ptr [rsp+890h+pv+4]
0x180034d60  or      [rbx+40h], eax
0x180034d63  cmp     [rsp+890h+pv+8], 0
0x180034d69  jz      short loc_180034D7A
0x180034d6b  lea     rdx, [rsp+890h+var_870]
0x180034d70  mov     rcx, rbx
0x180034d73  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180034d78  jmp     short loc_180034D84
0x180034d7a  mov     eax, dword ptr [rsp+890h+pv]
0x180034d7e  mov     [rbx+0B8h], eax
0x180034d84  lea     rcx, [rsp+890h+var_840]
0x180034d89  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180034d8e  mov     rcx, [rsp+890h+pv+8]; pv
0x180034d93  call    cs:__imp_CoTaskMemFree
0x180034d99  dec     dword ptr [rbx+0E8h]
0x180034d9f  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180034da6  call    cs:__imp_LeaveCriticalSection
0x180034dac  mov     rcx, [rbp+790h+var_10]
0x180034db3  xor     rcx, rsp; StackCookie
0x180034db6  call    __security_check_cookie
0x180034dbb  mov     rbx, [rsp+890h+arg_8]
0x180034dc3  add     rsp, 890h
0x180034dca  pop     rbp
0x180034dcb  retn
```
