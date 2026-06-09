# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x18000d3ec`
- end: `0x18000d51a`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b314`
- `0x18000d148`

## callees

- `0x180004c70`
- `0x18000a100`
- `0x18000b370`
- `0x18000d3ec`
- `0x18000eb08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4e1`

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
0x18000d3ec  mov     [rsp-8+arg_8], rbx
0x18000d3f1  push    rbp
0x18000d3f2  lea     rbp, [rsp-790h]
0x18000d3fa  sub     rsp, 890h
0x18000d401  mov     rax, cs:__security_cookie
0x18000d408  xor     rax, rsp
0x18000d40b  mov     [rbp+790h+var_10], rax
0x18000d412  bts     dword ptr [rcx+40h], 0Bh
0x18000d417  mov     rbx, rcx
0x18000d41a  cmp     qword ptr [rcx+0F0h], 0
0x18000d422  jz      loc_18000D4E7
0x18000d428  test    dword ptr [rcx+40h], 100h
0x18000d42f  jnz     loc_18000D4E7
0x18000d435  test    dword ptr [rcx+14h], 8000h
0x18000d43c  jnz     loc_18000D4E7
0x18000d442  xorps   xmm0, xmm0
0x18000d445  mov     [rsp+890h+var_840], 0
0x18000d44e  lea     rax, [rsp+890h+var_837]
0x18000d453  mov     [rsp+890h+var_838], 0
0x18000d458  mov     [rbp+790h+var_30], rax
0x18000d45f  lea     rdx, [rsp+890h+var_840]
0x18000d464  lea     rax, [rbp+790h+var_37]
0x18000d46b  mov     [rsp+890h+var_837], 80408040h
0x18000d473  mov     [rbp+790h+var_20], rax
0x18000d47a  mov     r8d, 1
0x18000d480  lea     rax, [rsp+890h+var_832]
0x18000d485  mov     [rsp+890h+var_833], 0
0x18000d48a  mov     [rbp+790h+var_28], rax
0x18000d491  movups  [rsp+890h+var_870], xmm0
0x18000d496  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18000d49b  movups  [rsp+890h+var_850], xmm0
0x18000d4a0  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18000d4a5  mov     rcx, [rbx+0F0h]
0x18000d4ac  lea     r9, [rsp+890h+var_870]
0x18000d4b1  mov     r8, rax
0x18000d4b4  call    TestUnlockData
0x18000d4b9  mov     eax, dword ptr [rsp+890h+pv+4]
0x18000d4bd  or      [rbx+40h], eax
0x18000d4c0  cmp     [rsp+890h+pv+8], 0
0x18000d4c6  jnz     short loc_18000D4D2
0x18000d4c8  mov     eax, dword ptr [rsp+890h+pv]
0x18000d4cc  mov     [rbx+0B8h], eax
0x18000d4d2  lea     rcx, [rsp+890h+var_840]
0x18000d4d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000d4dc  mov     rcx, [rsp+890h+pv+8]; pv
0x18000d4e1  call    cs:__imp_CoTaskMemFree
0x18000d4e7  dec     dword ptr [rbx+0E8h]
0x18000d4ed  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18000d4f4  call    cs:__imp_LeaveCriticalSection
0x18000d4fa  mov     rcx, [rbp+790h+var_10]
0x18000d501  xor     rcx, rsp; StackCookie
0x18000d504  call    __security_check_cookie
0x18000d509  mov     rbx, [rsp+890h+arg_8]
0x18000d511  add     rsp, 890h
0x18000d518  pop     rbp
0x18000d519  retn
```
