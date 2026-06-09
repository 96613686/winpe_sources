# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x18001ad3c`
- end: `0x18001ae6b`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a06c`
- `0x18001c4c8`

## callees

- `0x180003c20`
- `0x18000a0f0`
- `0x18001ad3c`
- `0x18001c32c`
- `0x18001d368`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae31`

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
    v4 = 0;
    *(_OWORD *)pv = 0;
    v6 = 0;
    v7 = 0;
    v8 = 0;
    v13 = &v9;
    v15 = &v12;
    v9 = -2143256512;
    v10 = 0;
    v14 = &v11;
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
0x18001ad3c  mov     [rsp-8+arg_8], rbx
0x18001ad41  push    rbp
0x18001ad42  lea     rbp, [rsp-790h]
0x18001ad4a  sub     rsp, 890h
0x18001ad51  mov     rax, cs:__security_cookie
0x18001ad58  xor     rax, rsp
0x18001ad5b  mov     [rbp+790h+var_10], rax
0x18001ad62  mov     rbx, rcx
0x18001ad65  bts     dword ptr [rcx+40h], 0Bh
0x18001ad6a  cmp     qword ptr [rcx+0F0h], 0
0x18001ad72  jz      loc_18001AE37
0x18001ad78  test    dword ptr [rcx+40h], 100h
0x18001ad7f  jnz     loc_18001AE37
0x18001ad85  test    dword ptr [rcx+14h], 8000h
0x18001ad8c  jnz     loc_18001AE37
0x18001ad92  xorps   xmm0, xmm0
0x18001ad95  movups  [rsp+890h+var_870], xmm0
0x18001ad9a  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18001ad9f  movups  [rsp+890h+var_850], xmm0
0x18001ada4  mov     [rsp+890h+var_840], 0
0x18001adad  mov     [rsp+890h+var_838], 0
0x18001adb2  lea     rax, [rsp+890h+var_837]
0x18001adb7  mov     [rbp+790h+var_30], rax
0x18001adbe  lea     rax, [rbp+790h+var_37]
0x18001adc5  mov     [rbp+790h+var_20], rax
0x18001adcc  mov     [rsp+890h+var_837], 80408040h
0x18001add4  mov     [rsp+890h+var_833], 0
0x18001add9  lea     rax, [rsp+890h+var_832]
0x18001adde  mov     [rbp+790h+var_28], rax
0x18001ade5  mov     r8d, 1
0x18001adeb  lea     rdx, [rsp+890h+var_840]
0x18001adf0  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18001adf5  lea     r9, [rsp+890h+var_870]
0x18001adfa  mov     r8, rax
0x18001adfd  mov     rcx, [rbx+0F0h]
0x18001ae04  call    TestUnlockData
0x18001ae09  mov     eax, dword ptr [rsp+890h+pv+4]
0x18001ae0d  or      [rbx+40h], eax
0x18001ae10  cmp     [rsp+890h+pv+8], 0
0x18001ae16  jnz     short loc_18001AE22
0x18001ae18  mov     eax, dword ptr [rsp+890h+pv]
0x18001ae1c  mov     [rbx+0B8h], eax
0x18001ae22  lea     rcx, [rsp+890h+var_840]
0x18001ae27  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ae2c  mov     rcx, [rsp+890h+pv+8]; pv
0x18001ae31  call    cs:__imp_CoTaskMemFree
0x18001ae37  dec     dword ptr [rbx+0E8h]
0x18001ae3d  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18001ae44  call    cs:__imp_LeaveCriticalSection
0x18001ae4a  nop
0x18001ae4b  mov     rcx, [rbp+790h+var_10]
0x18001ae52  xor     rcx, rsp; StackCookie
0x18001ae55  call    __security_check_cookie
0x18001ae5a  mov     rbx, [rsp+890h+arg_8]
0x18001ae62  add     rsp, 890h
0x18001ae69  pop     rbp
0x18001ae6a  retn
```
