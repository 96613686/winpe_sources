# tip2::details::shared_data<0,0,1>::end_update(void)

- ea: `0x140035158`
- end: `0x140035286`
- name: `?end_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140020f50`

## callees

- `0x140005240`
- `0x14000f22c`
- `0x140035158`
- `0x14003882c`
- `0x14003a02c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140035260`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140035260`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003524d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003524d`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::end_update(__int64 a1)
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
    v2 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &v7, 1);
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
0x140035158  mov     [rsp-8+arg_8], rbx
0x14003515d  push    rbp
0x14003515e  lea     rbp, [rsp-790h]
0x140035166  sub     rsp, 890h
0x14003516d  mov     rax, cs:__security_cookie
0x140035174  xor     rax, rsp
0x140035177  mov     [rbp+790h+var_10], rax
0x14003517e  bts     dword ptr [rcx+40h], 0Bh
0x140035183  mov     rbx, rcx
0x140035186  cmp     qword ptr [rcx+0F0h], 0
0x14003518e  jz      loc_140035253
0x140035194  test    dword ptr [rcx+40h], 100h
0x14003519b  jnz     loc_140035253
0x1400351a1  test    dword ptr [rcx+14h], 8000h
0x1400351a8  jnz     loc_140035253
0x1400351ae  xorps   xmm0, xmm0
0x1400351b1  mov     [rsp+890h+var_840], 0
0x1400351ba  lea     rax, [rsp+890h+var_837]
0x1400351bf  mov     [rsp+890h+var_838], 0
0x1400351c4  mov     [rbp+790h+var_30], rax
0x1400351cb  lea     rdx, [rsp+890h+var_840]
0x1400351d0  lea     rax, [rbp+790h+var_37]
0x1400351d7  mov     [rsp+890h+var_837], 80408040h
0x1400351df  mov     [rbp+790h+var_20], rax
0x1400351e6  mov     r8d, 1
0x1400351ec  lea     rax, [rsp+890h+var_832]
0x1400351f1  mov     [rsp+890h+var_833], 0
0x1400351f6  mov     [rbp+790h+var_28], rax
0x1400351fd  movups  [rsp+890h+var_870], xmm0
0x140035202  movups  xmmword ptr [rsp+890h+pv], xmm0
0x140035207  movups  [rsp+890h+var_850], xmm0
0x14003520c  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x140035211  mov     rcx, [rbx+0F0h]
0x140035218  lea     r9, [rsp+890h+var_870]
0x14003521d  mov     r8, rax
0x140035220  call    TestUnlockData
0x140035225  mov     eax, dword ptr [rsp+890h+pv+4]
0x140035229  or      [rbx+40h], eax
0x14003522c  cmp     [rsp+890h+pv+8], 0
0x140035232  jnz     short loc_14003523E
0x140035234  mov     eax, dword ptr [rsp+890h+pv]
0x140035238  mov     [rbx+0B8h], eax
0x14003523e  lea     rcx, [rsp+890h+var_840]
0x140035243  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140035248  mov     rcx, [rsp+890h+pv+8]; pv
0x14003524d  call    cs:__imp_CoTaskMemFree
0x140035253  dec     dword ptr [rbx+0E8h]
0x140035259  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x140035260  call    cs:__imp_LeaveCriticalSection
0x140035266  mov     rcx, [rbp+790h+var_10]
0x14003526d  xor     rcx, rsp; StackCookie
0x140035270  call    __security_check_cookie
0x140035275  mov     rbx, [rsp+890h+arg_8]
0x14003527d  add     rsp, 890h
0x140035284  pop     rbp
0x140035285  retn
```
