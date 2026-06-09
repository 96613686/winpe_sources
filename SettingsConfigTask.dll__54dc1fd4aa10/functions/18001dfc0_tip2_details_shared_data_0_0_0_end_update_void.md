# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x18001dfc0`
- end: `0x18001e0ee`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800127e8`
- `0x180012820`
- `0x1800196e0`

## callees

- `0x1800021d0`
- `0x180012920`
- `0x18001dfc0`
- `0x180020c54`
- `0x180021a64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e0c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e0c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0b5`

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
0x18001dfc0  mov     [rsp-8+arg_8], rbx
0x18001dfc5  push    rbp
0x18001dfc6  lea     rbp, [rsp-790h]
0x18001dfce  sub     rsp, 890h
0x18001dfd5  mov     rax, cs:__security_cookie
0x18001dfdc  xor     rax, rsp
0x18001dfdf  mov     [rbp+790h+var_10], rax
0x18001dfe6  bts     dword ptr [rcx+40h], 0Bh
0x18001dfeb  mov     rbx, rcx
0x18001dfee  cmp     qword ptr [rcx+0F0h], 0
0x18001dff6  jz      loc_18001E0BB
0x18001dffc  test    dword ptr [rcx+40h], 100h
0x18001e003  jnz     loc_18001E0BB
0x18001e009  test    dword ptr [rcx+14h], 8000h
0x18001e010  jnz     loc_18001E0BB
0x18001e016  xorps   xmm0, xmm0
0x18001e019  mov     [rsp+890h+var_840], 0
0x18001e022  lea     rax, [rsp+890h+var_837]
0x18001e027  mov     [rsp+890h+var_838], 0
0x18001e02c  mov     [rbp+790h+var_30], rax
0x18001e033  lea     rdx, [rsp+890h+var_840]
0x18001e038  lea     rax, [rbp+790h+var_37]
0x18001e03f  mov     [rsp+890h+var_837], 80408040h
0x18001e047  mov     [rbp+790h+var_20], rax
0x18001e04e  mov     r8d, 1
0x18001e054  lea     rax, [rsp+890h+var_832]
0x18001e059  mov     [rsp+890h+var_833], 0
0x18001e05e  mov     [rbp+790h+var_28], rax
0x18001e065  movups  [rsp+890h+var_870], xmm0
0x18001e06a  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18001e06f  movups  [rsp+890h+var_850], xmm0
0x18001e074  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18001e079  mov     rcx, [rbx+0F0h]
0x18001e080  lea     r9, [rsp+890h+var_870]
0x18001e085  mov     r8, rax
0x18001e088  call    TestUnlockData
0x18001e08d  mov     eax, dword ptr [rsp+890h+pv+4]
0x18001e091  or      [rbx+40h], eax
0x18001e094  cmp     [rsp+890h+pv+8], 0
0x18001e09a  jnz     short loc_18001E0A6
0x18001e09c  mov     eax, dword ptr [rsp+890h+pv]
0x18001e0a0  mov     [rbx+0B8h], eax
0x18001e0a6  lea     rcx, [rsp+890h+var_840]
0x18001e0ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001e0b0  mov     rcx, [rsp+890h+pv+8]; pv
0x18001e0b5  call    cs:__imp_CoTaskMemFree
0x18001e0bb  dec     dword ptr [rbx+0E8h]
0x18001e0c1  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18001e0c8  call    cs:__imp_LeaveCriticalSection
0x18001e0ce  mov     rcx, [rbp+790h+var_10]
0x18001e0d5  xor     rcx, rsp; StackCookie
0x18001e0d8  call    __security_check_cookie
0x18001e0dd  mov     rbx, [rsp+890h+arg_8]
0x18001e0e5  add     rsp, 890h
0x18001e0ec  pop     rbp
0x18001e0ed  retn
```
