# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x14002b300`
- end: `0x14002b42e`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14000ebf8`
- `0x140033828`
- `0x140033aa8`
- `0x14003bf98`

## callees

- `0x140005f30`
- `0x14000ecbc`
- `0x14002b300`
- `0x14002ccbc`
- `0x14002db38`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14002b408`
- `KERNEL32!LeaveCriticalSection` at `0x14002b408`
- `ole32!CoTaskMemFree` at `0x14002b3f5`
- `ole32!CoTaskMemFree` at `0x14002b3f5`

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
0x14002b300  mov     [rsp-8+arg_8], rbx
0x14002b305  push    rbp
0x14002b306  lea     rbp, [rsp-790h]
0x14002b30e  sub     rsp, 890h
0x14002b315  mov     rax, cs:__security_cookie
0x14002b31c  xor     rax, rsp
0x14002b31f  mov     [rbp+790h+var_10], rax
0x14002b326  bts     dword ptr [rcx+40h], 0Bh
0x14002b32b  mov     rbx, rcx
0x14002b32e  cmp     qword ptr [rcx+0F0h], 0
0x14002b336  jz      loc_14002B3FB
0x14002b33c  test    dword ptr [rcx+40h], 100h
0x14002b343  jnz     loc_14002B3FB
0x14002b349  test    dword ptr [rcx+14h], 8000h
0x14002b350  jnz     loc_14002B3FB
0x14002b356  xorps   xmm0, xmm0
0x14002b359  mov     [rsp+890h+var_840], 0
0x14002b362  lea     rax, [rsp+890h+var_837]
0x14002b367  mov     [rsp+890h+var_838], 0
0x14002b36c  mov     [rbp+790h+var_30], rax
0x14002b373  lea     rdx, [rsp+890h+var_840]
0x14002b378  lea     rax, [rbp+790h+var_37]
0x14002b37f  mov     [rsp+890h+var_837], 80408040h
0x14002b387  mov     [rbp+790h+var_20], rax
0x14002b38e  mov     r8d, 1
0x14002b394  lea     rax, [rsp+890h+var_832]
0x14002b399  mov     [rsp+890h+var_833], 0
0x14002b39e  mov     [rbp+790h+var_28], rax
0x14002b3a5  movups  [rsp+890h+var_870], xmm0
0x14002b3aa  movups  xmmword ptr [rsp+890h+pv], xmm0
0x14002b3af  movups  [rsp+890h+var_850], xmm0
0x14002b3b4  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14002b3b9  mov     rcx, [rbx+0F0h]
0x14002b3c0  lea     r9, [rsp+890h+var_870]
0x14002b3c5  mov     r8, rax
0x14002b3c8  call    TestUnlockData
0x14002b3cd  mov     eax, dword ptr [rsp+890h+pv+4]
0x14002b3d1  or      [rbx+40h], eax
0x14002b3d4  cmp     [rsp+890h+pv+8], 0
0x14002b3da  jnz     short loc_14002B3E6
0x14002b3dc  mov     eax, dword ptr [rsp+890h+pv]
0x14002b3e0  mov     [rbx+0B8h], eax
0x14002b3e6  lea     rcx, [rsp+890h+var_840]
0x14002b3eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14002b3f0  mov     rcx, [rsp+890h+pv+8]; pv
0x14002b3f5  call    cs:__imp_CoTaskMemFree
0x14002b3fb  dec     dword ptr [rbx+0E8h]
0x14002b401  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x14002b408  call    cs:__imp_LeaveCriticalSection
0x14002b40e  mov     rcx, [rbp+790h+var_10]
0x14002b415  xor     rcx, rsp; StackCookie
0x14002b418  call    __security_check_cookie
0x14002b41d  mov     rbx, [rsp+890h+arg_8]
0x14002b425  add     rsp, 890h
0x14002b42c  pop     rbp
0x14002b42d  retn
```
