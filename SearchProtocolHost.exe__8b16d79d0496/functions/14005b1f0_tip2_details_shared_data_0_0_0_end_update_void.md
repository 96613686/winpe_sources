# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x14005b1f0`
- end: `0x14005b31e`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140058710`
- `0x14005b688`
- `0x14005cbec`
- `0x14005cc24`

## callees

- `0x140005240`
- `0x14000f22c`
- `0x14003a02c`
- `0x14005b1f0`
- `0x14005b8c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005b2f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005b2f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005b2e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005b2e5`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
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
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
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
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v7, 1);
    TestUnlockData(*(_QWORD *)(a1 + 240), v3, v2, &v4);
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( !pv[1] )
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
0x14005b1f0  mov     [rsp-8+arg_8], rbx
0x14005b1f5  push    rbp
0x14005b1f6  lea     rbp, [rsp-790h]
0x14005b1fe  sub     rsp, 890h
0x14005b205  mov     rax, cs:__security_cookie
0x14005b20c  xor     rax, rsp
0x14005b20f  mov     [rbp+790h+var_10], rax
0x14005b216  bts     dword ptr [rcx+40h], 0Bh
0x14005b21b  mov     rbx, rcx
0x14005b21e  cmp     qword ptr [rcx+0F0h], 0
0x14005b226  jz      loc_14005B2EB
0x14005b22c  test    dword ptr [rcx+40h], 100h
0x14005b233  jnz     loc_14005B2EB
0x14005b239  test    dword ptr [rcx+14h], 8000h
0x14005b240  jnz     loc_14005B2EB
0x14005b246  xorps   xmm0, xmm0
0x14005b249  mov     [rsp+890h+var_840], 0
0x14005b252  lea     rax, [rsp+890h+var_837]
0x14005b257  mov     [rsp+890h+var_838], 0
0x14005b25c  mov     [rbp+790h+var_30], rax
0x14005b263  lea     rdx, [rsp+890h+var_840]
0x14005b268  lea     rax, [rbp+790h+var_37]
0x14005b26f  mov     [rsp+890h+var_837], 80408040h
0x14005b277  mov     [rbp+790h+var_20], rax
0x14005b27e  mov     r8d, 1
0x14005b284  lea     rax, [rsp+890h+var_832]
0x14005b289  mov     [rsp+890h+var_833], 0
0x14005b28e  mov     [rbp+790h+var_28], rax
0x14005b295  movups  [rsp+890h+var_870], xmm0
0x14005b29a  movups  xmmword ptr [rsp+890h+pv], xmm0
0x14005b29f  movups  [rsp+890h+var_850], xmm0
0x14005b2a4  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14005b2a9  mov     rcx, [rbx+0F0h]
0x14005b2b0  lea     r9, [rsp+890h+var_870]
0x14005b2b5  mov     r8, rax
0x14005b2b8  call    TestUnlockData
0x14005b2bd  mov     eax, dword ptr [rsp+890h+pv+4]
0x14005b2c1  or      [rbx+40h], eax
0x14005b2c4  cmp     [rsp+890h+pv+8], 0
0x14005b2ca  jnz     short loc_14005B2D6
0x14005b2cc  mov     eax, dword ptr [rsp+890h+pv]
0x14005b2d0  mov     [rbx+0B8h], eax
0x14005b2d6  lea     rcx, [rsp+890h+var_840]
0x14005b2db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005b2e0  mov     rcx, [rsp+890h+pv+8]; pv
0x14005b2e5  call    cs:__imp_CoTaskMemFree
0x14005b2eb  dec     dword ptr [rbx+0E8h]
0x14005b2f1  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x14005b2f8  call    cs:__imp_LeaveCriticalSection
0x14005b2fe  mov     rcx, [rbp+790h+var_10]
0x14005b305  xor     rcx, rsp; StackCookie
0x14005b308  call    __security_check_cookie
0x14005b30d  mov     rbx, [rsp+890h+arg_8]
0x14005b315  add     rsp, 890h
0x14005b31c  pop     rbp
0x14005b31d  retn
```
