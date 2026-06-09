# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x180023708`
- end: `0x180023838`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001b2f4`
- `0x18002468c`
- `0x180026d54`

## callees

- `0x180003560`
- `0x18001b360`
- `0x1800234b8`
- `0x180023708`
- `0x180025900`
- `0x18002652c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023812`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023812`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800237ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800237ff`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int128 v4; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h]
  __int128 v6; // [rsp+40h] [rbp-C0h]
  __int64 v7; // [rsp+50h] [rbp-B0h] BYREF
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
0x180023708  mov     [rsp-8+arg_8], rbx
0x18002370d  push    rbp
0x18002370e  lea     rbp, [rsp-790h]
0x180023716  sub     rsp, 890h
0x18002371d  mov     rax, cs:__security_cookie
0x180023724  xor     rax, rsp
0x180023727  mov     [rbp+790h+var_10], rax
0x18002372e  bts     dword ptr [rcx+40h], 0Bh
0x180023733  mov     rbx, rcx
0x180023736  cmp     qword ptr [rcx+0F0h], 0
0x18002373e  jz      loc_180023805
0x180023744  test    dword ptr [rcx+40h], 100h
0x18002374b  jnz     loc_180023805
0x180023751  xorps   xmm0, xmm0
0x180023754  mov     [rsp+890h+var_840], 0
0x18002375d  lea     rax, [rsp+890h+var_837]
0x180023762  mov     [rsp+890h+var_838], 0
0x180023767  mov     [rbp+790h+var_30], rax
0x18002376e  lea     rdx, [rsp+890h+var_840]
0x180023773  lea     rax, [rbp+790h+var_37]
0x18002377a  mov     [rsp+890h+var_837], 80408040h
0x180023782  mov     [rbp+790h+var_20], rax
0x180023789  mov     r8d, 1
0x18002378f  lea     rax, [rsp+890h+var_832]
0x180023794  mov     [rsp+890h+var_833], 0
0x180023799  mov     [rbp+790h+var_28], rax
0x1800237a0  movups  [rsp+890h+var_870], xmm0
0x1800237a5  movups  xmmword ptr [rsp+890h+pv], xmm0
0x1800237aa  movups  [rsp+890h+var_850], xmm0
0x1800237af  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800237b4  mov     rcx, [rbx+0F0h]
0x1800237bb  lea     r9, [rsp+890h+var_870]
0x1800237c0  mov     r8, rax
0x1800237c3  call    TestUnlockData
0x1800237c8  mov     eax, dword ptr [rsp+890h+pv+4]
0x1800237cc  or      [rbx+40h], eax
0x1800237cf  cmp     [rsp+890h+pv+8], 0
0x1800237d5  jz      short loc_1800237E6
0x1800237d7  lea     rdx, [rsp+890h+var_870]
0x1800237dc  mov     rcx, rbx
0x1800237df  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800237e4  jmp     short loc_1800237F0
0x1800237e6  mov     eax, dword ptr [rsp+890h+pv]
0x1800237ea  mov     [rbx+0B8h], eax
0x1800237f0  lea     rcx, [rsp+890h+var_840]
0x1800237f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800237fa  mov     rcx, [rsp+890h+pv+8]; pv
0x1800237ff  call    cs:__imp_CoTaskMemFree
0x180023805  dec     dword ptr [rbx+0E8h]
0x18002380b  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180023812  call    cs:__imp_LeaveCriticalSection
0x180023818  mov     rcx, [rbp+790h+var_10]
0x18002381f  xor     rcx, rsp; StackCookie
0x180023822  call    __security_check_cookie
0x180023827  mov     rbx, [rsp+890h+arg_8]
0x18002382f  add     rsp, 890h
0x180023836  pop     rbp
0x180023837  retn
```
