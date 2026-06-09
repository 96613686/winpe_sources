# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x18003c8cc`
- end: `0x18003c9fc`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180037090`
- `0x180039ed0`
- `0x18003eed4`

## callees

- `0x1800032b0`
- `0x18000a5c8`
- `0x18003c738`
- `0x18003c8cc`
- `0x18003ed00`
- `0x18003fb6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c9d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c9d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c9c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c9c3`

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
0x18003c8cc  mov     [rsp-8+arg_8], rbx
0x18003c8d1  push    rbp
0x18003c8d2  lea     rbp, [rsp-790h]
0x18003c8da  sub     rsp, 890h
0x18003c8e1  mov     rax, cs:__security_cookie
0x18003c8e8  xor     rax, rsp
0x18003c8eb  mov     [rbp+790h+var_10], rax
0x18003c8f2  bts     dword ptr [rcx+40h], 0Bh
0x18003c8f7  mov     rbx, rcx
0x18003c8fa  cmp     qword ptr [rcx+0F0h], 0
0x18003c902  jz      loc_18003C9C9
0x18003c908  test    dword ptr [rcx+40h], 100h
0x18003c90f  jnz     loc_18003C9C9
0x18003c915  xorps   xmm0, xmm0
0x18003c918  mov     [rsp+890h+var_840], 0
0x18003c921  lea     rax, [rsp+890h+var_837]
0x18003c926  mov     [rsp+890h+var_838], 0
0x18003c92b  mov     [rbp+790h+var_30], rax
0x18003c932  lea     rdx, [rsp+890h+var_840]
0x18003c937  lea     rax, [rbp+790h+var_37]
0x18003c93e  mov     [rsp+890h+var_837], 80408040h
0x18003c946  mov     [rbp+790h+var_20], rax
0x18003c94d  mov     r8d, 1
0x18003c953  lea     rax, [rsp+890h+var_832]
0x18003c958  mov     [rsp+890h+var_833], 0
0x18003c95d  mov     [rbp+790h+var_28], rax
0x18003c964  movups  [rsp+890h+var_870], xmm0
0x18003c969  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18003c96e  movups  [rsp+890h+var_850], xmm0
0x18003c973  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18003c978  mov     rcx, [rbx+0F0h]
0x18003c97f  lea     r9, [rsp+890h+var_870]
0x18003c984  mov     r8, rax
0x18003c987  call    TestUnlockData
0x18003c98c  mov     eax, dword ptr [rsp+890h+pv+4]
0x18003c990  or      [rbx+40h], eax
0x18003c993  cmp     [rsp+890h+pv+8], 0
0x18003c999  jz      short loc_18003C9AA
0x18003c99b  lea     rdx, [rsp+890h+var_870]
0x18003c9a0  mov     rcx, rbx
0x18003c9a3  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18003c9a8  jmp     short loc_18003C9B4
0x18003c9aa  mov     eax, dword ptr [rsp+890h+pv]
0x18003c9ae  mov     [rbx+0B8h], eax
0x18003c9b4  lea     rcx, [rsp+890h+var_840]
0x18003c9b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003c9be  mov     rcx, [rsp+890h+pv+8]; pv
0x18003c9c3  call    cs:__imp_CoTaskMemFree
0x18003c9c9  dec     dword ptr [rbx+0E8h]
0x18003c9cf  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18003c9d6  call    cs:__imp_LeaveCriticalSection
0x18003c9dc  mov     rcx, [rbp+790h+var_10]
0x18003c9e3  xor     rcx, rsp; StackCookie
0x18003c9e6  call    __security_check_cookie
0x18003c9eb  mov     rbx, [rsp+890h+arg_8]
0x18003c9f3  add     rsp, 890h
0x18003c9fa  pop     rbp
0x18003c9fb  retn
```
