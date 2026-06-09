# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180016bf4`
- end: `0x180016d22`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800165bc`
- `0x180030850`
- `0x180056bc4`
- `0x180056bfc`

## callees

- `0x180007900`
- `0x1800150c8`
- `0x180016344`
- `0x180016bf4`
- `0x180037780`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016cfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ce9`

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
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v7);
    CoTaskMemFree(pv[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x180016bf4  mov     [rsp-8+arg_8], rbx
0x180016bf9  push    rbp
0x180016bfa  lea     rbp, [rsp-790h]
0x180016c02  sub     rsp, 890h
0x180016c09  mov     rax, cs:__security_cookie
0x180016c10  xor     rax, rsp
0x180016c13  mov     [rbp+790h+var_10], rax
0x180016c1a  bts     dword ptr [rcx+40h], 0Bh
0x180016c1f  mov     rbx, rcx
0x180016c22  cmp     qword ptr [rcx+0F0h], 0
0x180016c2a  jz      loc_180016CEF
0x180016c30  test    dword ptr [rcx+40h], 100h
0x180016c37  jnz     loc_180016CEF
0x180016c3d  test    dword ptr [rcx+14h], 8000h
0x180016c44  jnz     loc_180016CEF
0x180016c4a  xorps   xmm0, xmm0
0x180016c4d  mov     [rsp+890h+var_840], 0
0x180016c56  lea     rax, [rsp+890h+var_837]
0x180016c5b  mov     [rsp+890h+var_838], 0
0x180016c60  mov     [rbp+790h+var_30], rax
0x180016c67  lea     rdx, [rsp+890h+var_840]
0x180016c6c  lea     rax, [rbp+790h+var_37]
0x180016c73  mov     [rsp+890h+var_837], 80408040h
0x180016c7b  mov     [rbp+790h+var_20], rax
0x180016c82  mov     r8d, 1
0x180016c88  lea     rax, [rsp+890h+var_832]
0x180016c8d  mov     [rsp+890h+var_833], 0
0x180016c92  mov     [rbp+790h+var_28], rax
0x180016c99  movups  [rsp+890h+var_870], xmm0
0x180016c9e  movups  xmmword ptr [rsp+890h+pv], xmm0
0x180016ca3  movups  [rsp+890h+var_850], xmm0
0x180016ca8  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180016cad  mov     rcx, [rbx+0F0h]
0x180016cb4  lea     r9, [rsp+890h+var_870]
0x180016cb9  mov     r8, rax
0x180016cbc  call    TestUnlockData
0x180016cc1  mov     eax, dword ptr [rsp+890h+pv+4]
0x180016cc5  or      [rbx+40h], eax
0x180016cc8  cmp     [rsp+890h+pv+8], 0
0x180016cce  jnz     short loc_180016CDA
0x180016cd0  mov     eax, dword ptr [rsp+890h+pv]
0x180016cd4  mov     [rbx+0B8h], eax
0x180016cda  lea     rcx, [rsp+890h+var_840]; void *
0x180016cdf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180016ce4  mov     rcx, [rsp+890h+pv+8]; pv
0x180016ce9  call    cs:__imp_CoTaskMemFree
0x180016cef  dec     dword ptr [rbx+0E8h]
0x180016cf5  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180016cfc  call    cs:__imp_LeaveCriticalSection
0x180016d02  mov     rcx, [rbp+790h+var_10]
0x180016d09  xor     rcx, rsp; StackCookie
0x180016d0c  call    __security_check_cookie
0x180016d11  mov     rbx, [rsp+890h+arg_8]
0x180016d19  add     rsp, 890h
0x180016d20  pop     rbp
0x180016d21  retn
```
