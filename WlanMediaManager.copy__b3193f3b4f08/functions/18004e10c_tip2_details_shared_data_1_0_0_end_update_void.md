# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x18004e10c`
- end: `0x18004e23c`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003a108`
- `0x180062b5c`
- `0x1800631d8`

## callees

- `0x180003ed0`
- `0x18002a40c`
- `0x18004df78`
- `0x18004e10c`
- `0x180051418`
- `0x180051c24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e216`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e216`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e203`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e203`

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
0x18004e10c  mov     [rsp-8+arg_8], rbx
0x18004e111  push    rbp
0x18004e112  lea     rbp, [rsp-790h]
0x18004e11a  sub     rsp, 890h
0x18004e121  mov     rax, cs:__security_cookie
0x18004e128  xor     rax, rsp
0x18004e12b  mov     [rbp+790h+var_10], rax
0x18004e132  bts     dword ptr [rcx+40h], 0Bh
0x18004e137  mov     rbx, rcx
0x18004e13a  cmp     qword ptr [rcx+0F0h], 0
0x18004e142  jz      loc_18004E209
0x18004e148  test    dword ptr [rcx+40h], 100h
0x18004e14f  jnz     loc_18004E209
0x18004e155  xorps   xmm0, xmm0
0x18004e158  mov     [rsp+890h+var_840], 0
0x18004e161  lea     rax, [rsp+890h+var_837]
0x18004e166  mov     [rsp+890h+var_838], 0
0x18004e16b  mov     [rbp+790h+var_30], rax
0x18004e172  lea     rdx, [rsp+890h+var_840]
0x18004e177  lea     rax, [rbp+790h+var_37]
0x18004e17e  mov     [rsp+890h+var_837], 80408040h
0x18004e186  mov     [rbp+790h+var_20], rax
0x18004e18d  mov     r8d, 1
0x18004e193  lea     rax, [rsp+890h+var_832]
0x18004e198  mov     [rsp+890h+var_833], 0
0x18004e19d  mov     [rbp+790h+var_28], rax
0x18004e1a4  movups  [rsp+890h+var_870], xmm0
0x18004e1a9  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18004e1ae  movups  [rsp+890h+var_850], xmm0
0x18004e1b3  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18004e1b8  mov     rcx, [rbx+0F0h]
0x18004e1bf  lea     r9, [rsp+890h+var_870]
0x18004e1c4  mov     r8, rax
0x18004e1c7  call    TestUnlockData
0x18004e1cc  mov     eax, dword ptr [rsp+890h+pv+4]
0x18004e1d0  or      [rbx+40h], eax
0x18004e1d3  cmp     [rsp+890h+pv+8], 0
0x18004e1d9  jz      short loc_18004E1EA
0x18004e1db  lea     rdx, [rsp+890h+var_870]
0x18004e1e0  mov     rcx, rbx
0x18004e1e3  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004e1e8  jmp     short loc_18004E1F4
0x18004e1ea  mov     eax, dword ptr [rsp+890h+pv]
0x18004e1ee  mov     [rbx+0B8h], eax
0x18004e1f4  lea     rcx, [rsp+890h+var_840]
0x18004e1f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004e1fe  mov     rcx, [rsp+890h+pv+8]; pv
0x18004e203  call    cs:__imp_CoTaskMemFree
0x18004e209  dec     dword ptr [rbx+0E8h]
0x18004e20f  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18004e216  call    cs:__imp_LeaveCriticalSection
0x18004e21c  mov     rcx, [rbp+790h+var_10]
0x18004e223  xor     rcx, rsp; StackCookie
0x18004e226  call    __security_check_cookie
0x18004e22b  mov     rbx, [rsp+890h+arg_8]
0x18004e233  add     rsp, 890h
0x18004e23a  pop     rbp
0x18004e23b  retn
```
