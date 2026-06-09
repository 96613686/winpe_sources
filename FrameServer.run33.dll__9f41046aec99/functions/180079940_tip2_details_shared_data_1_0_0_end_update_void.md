# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x180079940`
- end: `0x180079a70`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800763f0`
- `0x1800780e0`

## callees

- `0x180003e20`
- `0x18000a648`
- `0x1800797ac`
- `0x180079940`
- `0x18007b4d4`
- `0x18007bd6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079a4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079a4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079a37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079a37`

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
0x180079940  mov     [rsp-8+arg_8], rbx
0x180079945  push    rbp
0x180079946  lea     rbp, [rsp-790h]
0x18007994e  sub     rsp, 890h
0x180079955  mov     rax, cs:__security_cookie
0x18007995c  xor     rax, rsp
0x18007995f  mov     [rbp+790h+var_10], rax
0x180079966  bts     dword ptr [rcx+40h], 0Bh
0x18007996b  mov     rbx, rcx
0x18007996e  cmp     qword ptr [rcx+0F0h], 0
0x180079976  jz      loc_180079A3D
0x18007997c  test    dword ptr [rcx+40h], 100h
0x180079983  jnz     loc_180079A3D
0x180079989  xorps   xmm0, xmm0
0x18007998c  mov     [rsp+890h+var_840], 0
0x180079995  lea     rax, [rsp+890h+var_837]
0x18007999a  mov     [rsp+890h+var_838], 0
0x18007999f  mov     [rbp+790h+var_30], rax
0x1800799a6  lea     rdx, [rsp+890h+var_840]
0x1800799ab  lea     rax, [rbp+790h+var_37]
0x1800799b2  mov     [rsp+890h+var_837], 80408040h
0x1800799ba  mov     [rbp+790h+var_20], rax
0x1800799c1  mov     r8d, 1
0x1800799c7  lea     rax, [rsp+890h+var_832]
0x1800799cc  mov     [rsp+890h+var_833], 0
0x1800799d1  mov     [rbp+790h+var_28], rax
0x1800799d8  movups  [rsp+890h+var_870], xmm0
0x1800799dd  movups  xmmword ptr [rsp+890h+pv], xmm0
0x1800799e2  movups  [rsp+890h+var_850], xmm0
0x1800799e7  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800799ec  mov     rcx, [rbx+0F0h]
0x1800799f3  lea     r9, [rsp+890h+var_870]
0x1800799f8  mov     r8, rax
0x1800799fb  call    TestUnlockData
0x180079a00  mov     eax, dword ptr [rsp+890h+pv+4]
0x180079a04  or      [rbx+40h], eax
0x180079a07  cmp     [rsp+890h+pv+8], 0
0x180079a0d  jz      short loc_180079A1E
0x180079a0f  lea     rdx, [rsp+890h+var_870]
0x180079a14  mov     rcx, rbx
0x180079a17  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180079a1c  jmp     short loc_180079A28
0x180079a1e  mov     eax, dword ptr [rsp+890h+pv]
0x180079a22  mov     [rbx+0B8h], eax
0x180079a28  lea     rcx, [rsp+890h+var_840]
0x180079a2d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180079a32  mov     rcx, [rsp+890h+pv+8]; pv
0x180079a37  call    cs:__imp_CoTaskMemFree
0x180079a3d  dec     dword ptr [rbx+0E8h]
0x180079a43  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180079a4a  call    cs:__imp_LeaveCriticalSection
0x180079a50  mov     rcx, [rbp+790h+var_10]
0x180079a57  xor     rcx, rsp; StackCookie
0x180079a5a  call    __security_check_cookie
0x180079a5f  mov     rbx, [rsp+890h+arg_8]
0x180079a67  add     rsp, 890h
0x180079a6e  pop     rbp
0x180079a6f  retn
```
