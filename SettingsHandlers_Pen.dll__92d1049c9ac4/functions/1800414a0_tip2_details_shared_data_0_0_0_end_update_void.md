# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x1800414a0`
- end: `0x1800415ce`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003edd0`
- `0x180040150`

## callees

- `0x1800030e0`
- `0x180020740`
- `0x1800414a0`
- `0x180042940`
- `0x1800431a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800415a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800415a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041595`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041595`

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
0x1800414a0  mov     [rsp-8+arg_8], rbx
0x1800414a5  push    rbp
0x1800414a6  lea     rbp, [rsp-790h]
0x1800414ae  sub     rsp, 890h
0x1800414b5  mov     rax, cs:__security_cookie
0x1800414bc  xor     rax, rsp
0x1800414bf  mov     [rbp+790h+var_10], rax
0x1800414c6  bts     dword ptr [rcx+40h], 0Bh
0x1800414cb  mov     rbx, rcx
0x1800414ce  cmp     qword ptr [rcx+0F0h], 0
0x1800414d6  jz      loc_18004159B
0x1800414dc  test    dword ptr [rcx+40h], 100h
0x1800414e3  jnz     loc_18004159B
0x1800414e9  test    dword ptr [rcx+14h], 8000h
0x1800414f0  jnz     loc_18004159B
0x1800414f6  xorps   xmm0, xmm0
0x1800414f9  mov     [rsp+890h+var_840], 0
0x180041502  lea     rax, [rsp+890h+var_837]
0x180041507  mov     [rsp+890h+var_838], 0
0x18004150c  mov     [rbp+790h+var_30], rax
0x180041513  lea     rdx, [rsp+890h+var_840]
0x180041518  lea     rax, [rbp+790h+var_37]
0x18004151f  mov     [rsp+890h+var_837], 80408040h
0x180041527  mov     [rbp+790h+var_20], rax
0x18004152e  mov     r8d, 1
0x180041534  lea     rax, [rsp+890h+var_832]
0x180041539  mov     [rsp+890h+var_833], 0
0x18004153e  mov     [rbp+790h+var_28], rax
0x180041545  movups  [rsp+890h+var_870], xmm0
0x18004154a  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18004154f  movups  [rsp+890h+var_850], xmm0
0x180041554  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180041559  mov     rcx, [rbx+0F0h]
0x180041560  lea     r9, [rsp+890h+var_870]
0x180041565  mov     r8, rax
0x180041568  call    TestUnlockData
0x18004156d  mov     eax, dword ptr [rsp+890h+pv+4]
0x180041571  or      [rbx+40h], eax
0x180041574  cmp     [rsp+890h+pv+8], 0
0x18004157a  jnz     short loc_180041586
0x18004157c  mov     eax, dword ptr [rsp+890h+pv]
0x180041580  mov     [rbx+0B8h], eax
0x180041586  lea     rcx, [rsp+890h+var_840]
0x18004158b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180041590  mov     rcx, [rsp+890h+pv+8]; pv
0x180041595  call    cs:__imp_CoTaskMemFree
0x18004159b  dec     dword ptr [rbx+0E8h]
0x1800415a1  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800415a8  call    cs:__imp_LeaveCriticalSection
0x1800415ae  mov     rcx, [rbp+790h+var_10]
0x1800415b5  xor     rcx, rsp; StackCookie
0x1800415b8  call    __security_check_cookie
0x1800415bd  mov     rbx, [rsp+890h+arg_8]
0x1800415c5  add     rsp, 890h
0x1800415cc  pop     rbp
0x1800415cd  retn
```
