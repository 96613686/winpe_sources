# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x18002cf38`
- end: `0x18002d07b`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `323`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180021e34`
- `0x180021e6c`
- `0x18003e918`

## callees

- `0x180002b20`
- `0x180003cf6`
- `0x18000e1c8`
- `0x18001be70`
- `0x18001d0e8`
- `0x18002cf38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d055`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d042`

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
  _BYTE v11[2043]; // [rsp+5Eh] [rbp-A2h] BYREF
  char v12; // [rsp+859h] [rbp+759h] BYREF
  int *v13; // [rsp+860h] [rbp+760h]
  _BYTE *v14; // [rsp+868h] [rbp+768h]
  char *v15; // [rsp+870h] [rbp+770h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
  {
    v4 = 0;
    *(_OWORD *)pv = 0;
    v6 = 0;
    memset_0(v11, 0, 0x802u);
    v7 = 0;
    v13 = &v9;
    v8 = 0;
    v15 = &v12;
    v9 = -2143256512;
    v14 = v11;
    v10 = 0;
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v7, 1);
    ((void (__fastcall *)(_QWORD, __int64, __int64, __int128 *))TestUnlockData)(*(_QWORD *)(a1 + 240), v3, v2, &v4);
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
0x18002cf38  mov     [rsp-8+arg_8], rbx
0x18002cf3d  push    rbp
0x18002cf3e  lea     rbp, [rsp-790h]
0x18002cf46  sub     rsp, 890h
0x18002cf4d  mov     rax, cs:__security_cookie
0x18002cf54  xor     rax, rsp
0x18002cf57  mov     [rbp+790h+var_10], rax
0x18002cf5e  bts     dword ptr [rcx+40h], 0Bh
0x18002cf63  mov     rbx, rcx
0x18002cf66  cmp     qword ptr [rcx+0F0h], 0
0x18002cf6e  jz      loc_18002D048
0x18002cf74  test    dword ptr [rcx+40h], 100h
0x18002cf7b  jnz     loc_18002D048
0x18002cf81  test    dword ptr [rcx+14h], 8000h
0x18002cf88  jnz     loc_18002D048
0x18002cf8e  xorps   xmm0, xmm0
0x18002cf91  lea     rcx, [rsp+890h+var_832]; void *
0x18002cf96  xor     edx, edx; Val
0x18002cf98  mov     r8d, 802h; Size
0x18002cf9e  movups  [rsp+890h+var_870], xmm0
0x18002cfa3  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18002cfa8  movups  [rsp+890h+var_850], xmm0
0x18002cfad  call    memset_0
0x18002cfb2  lea     rax, [rsp+890h+var_837]
0x18002cfb7  mov     [rsp+890h+var_840], 0
0x18002cfc0  mov     [rbp+790h+var_30], rax
0x18002cfc7  lea     rdx, [rsp+890h+var_840]
0x18002cfcc  lea     rax, [rbp+790h+var_37]
0x18002cfd3  mov     [rsp+890h+var_838], 0
0x18002cfd8  mov     [rbp+790h+var_20], rax
0x18002cfdf  mov     r8d, 1
0x18002cfe5  lea     rax, [rsp+890h+var_832]
0x18002cfea  mov     [rsp+890h+var_837], 80408040h
0x18002cff2  mov     rcx, rbx
0x18002cff5  mov     [rbp+790h+var_28], rax
0x18002cffc  mov     [rsp+890h+var_833], 0
0x18002d001  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18002d006  mov     rcx, [rbx+0F0h]
0x18002d00d  lea     r9, [rsp+890h+var_870]
0x18002d012  mov     r8, rax
0x18002d015  call    TestUnlockData
0x18002d01a  mov     eax, dword ptr [rsp+890h+pv+4]
0x18002d01e  or      [rbx+40h], eax
0x18002d021  cmp     [rsp+890h+pv+8], 0
0x18002d027  jnz     short loc_18002D033
0x18002d029  mov     eax, dword ptr [rsp+890h+pv]
0x18002d02d  mov     [rbx+0B8h], eax
0x18002d033  lea     rcx, [rsp+890h+var_840]
0x18002d038  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002d03d  mov     rcx, [rsp+890h+pv+8]; pv
0x18002d042  call    cs:__imp_CoTaskMemFree
0x18002d048  dec     dword ptr [rbx+0E8h]
0x18002d04e  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18002d055  call    cs:__imp_LeaveCriticalSection
0x18002d05b  mov     rcx, [rbp+790h+var_10]
0x18002d062  xor     rcx, rsp; StackCookie
0x18002d065  call    __security_check_cookie
0x18002d06a  mov     rbx, [rsp+890h+arg_8]
0x18002d072  add     rsp, 890h
0x18002d079  pop     rbp
0x18002d07a  retn
```
