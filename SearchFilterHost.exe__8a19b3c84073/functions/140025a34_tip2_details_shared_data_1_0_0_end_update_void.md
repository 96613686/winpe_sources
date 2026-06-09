# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x140025a34`
- end: `0x140025b64`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14001bcbc`
- `0x140022180`

## callees

- `0x1400030a0`
- `0x14000e19c`
- `0x14001865c`
- `0x1400256e8`
- `0x140025a34`
- `0x140026edc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025b3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025b3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025b2b`

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
0x140025a34  mov     [rsp-8+arg_8], rbx
0x140025a39  push    rbp
0x140025a3a  lea     rbp, [rsp-790h]
0x140025a42  sub     rsp, 890h
0x140025a49  mov     rax, cs:__security_cookie
0x140025a50  xor     rax, rsp
0x140025a53  mov     [rbp+790h+var_10], rax
0x140025a5a  bts     dword ptr [rcx+40h], 0Bh
0x140025a5f  mov     rbx, rcx
0x140025a62  cmp     qword ptr [rcx+0F0h], 0
0x140025a6a  jz      loc_140025B31
0x140025a70  test    dword ptr [rcx+40h], 100h
0x140025a77  jnz     loc_140025B31
0x140025a7d  xorps   xmm0, xmm0
0x140025a80  mov     [rsp+890h+var_840], 0
0x140025a89  lea     rax, [rsp+890h+var_837]
0x140025a8e  mov     [rsp+890h+var_838], 0
0x140025a93  mov     [rbp+790h+var_30], rax
0x140025a9a  lea     rdx, [rsp+890h+var_840]
0x140025a9f  lea     rax, [rbp+790h+var_37]
0x140025aa6  mov     [rsp+890h+var_837], 80408040h
0x140025aae  mov     [rbp+790h+var_20], rax
0x140025ab5  mov     r8d, 1
0x140025abb  lea     rax, [rsp+890h+var_832]
0x140025ac0  mov     [rsp+890h+var_833], 0
0x140025ac5  mov     [rbp+790h+var_28], rax
0x140025acc  movups  [rsp+890h+var_870], xmm0
0x140025ad1  movups  xmmword ptr [rsp+890h+pv], xmm0
0x140025ad6  movups  [rsp+890h+var_850], xmm0
0x140025adb  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x140025ae0  mov     rcx, [rbx+0F0h]
0x140025ae7  lea     r9, [rsp+890h+var_870]
0x140025aec  mov     r8, rax
0x140025aef  call    TestUnlockData
0x140025af4  mov     eax, dword ptr [rsp+890h+pv+4]
0x140025af8  or      [rbx+40h], eax
0x140025afb  cmp     [rsp+890h+pv+8], 0
0x140025b01  jz      short loc_140025B12
0x140025b03  lea     rdx, [rsp+890h+var_870]
0x140025b08  mov     rcx, rbx
0x140025b0b  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x140025b10  jmp     short loc_140025B1C
0x140025b12  mov     eax, dword ptr [rsp+890h+pv]
0x140025b16  mov     [rbx+0B8h], eax
0x140025b1c  lea     rcx, [rsp+890h+var_840]
0x140025b21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140025b26  mov     rcx, [rsp+890h+pv+8]; pv
0x140025b2b  call    cs:__imp_CoTaskMemFree
0x140025b31  dec     dword ptr [rbx+0E8h]
0x140025b37  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x140025b3e  call    cs:__imp_LeaveCriticalSection
0x140025b44  mov     rcx, [rbp+790h+var_10]
0x140025b4b  xor     rcx, rsp; StackCookie
0x140025b4e  call    __security_check_cookie
0x140025b53  mov     rbx, [rsp+890h+arg_8]
0x140025b5b  add     rsp, 890h
0x140025b62  pop     rbp
0x140025b63  retn
```
