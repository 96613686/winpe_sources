# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x140019320`
- end: `0x14001944e`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140009004`
- `0x140010490`

## callees

- `0x140003620`
- `0x140009088`
- `0x140019320`
- `0x14001b764`
- `0x14001c23c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140019428`
- `KERNEL32!LeaveCriticalSection` at `0x140019428`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019415`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019415`

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
0x140019320  mov     [rsp-8+arg_8], rbx
0x140019325  push    rbp
0x140019326  lea     rbp, [rsp-790h]
0x14001932e  sub     rsp, 890h
0x140019335  mov     rax, cs:__security_cookie
0x14001933c  xor     rax, rsp
0x14001933f  mov     [rbp+790h+var_10], rax
0x140019346  bts     dword ptr [rcx+40h], 0Bh
0x14001934b  mov     rbx, rcx
0x14001934e  cmp     qword ptr [rcx+0F0h], 0
0x140019356  jz      loc_14001941B
0x14001935c  test    dword ptr [rcx+40h], 100h
0x140019363  jnz     loc_14001941B
0x140019369  test    dword ptr [rcx+14h], 8000h
0x140019370  jnz     loc_14001941B
0x140019376  xorps   xmm0, xmm0
0x140019379  mov     [rsp+890h+var_840], 0
0x140019382  lea     rax, [rsp+890h+var_837]
0x140019387  mov     [rsp+890h+var_838], 0
0x14001938c  mov     [rbp+790h+var_30], rax
0x140019393  lea     rdx, [rsp+890h+var_840]
0x140019398  lea     rax, [rbp+790h+var_37]
0x14001939f  mov     [rsp+890h+var_837], 80408040h
0x1400193a7  mov     [rbp+790h+var_20], rax
0x1400193ae  mov     r8d, 1
0x1400193b4  lea     rax, [rsp+890h+var_832]
0x1400193b9  mov     [rsp+890h+var_833], 0
0x1400193be  mov     [rbp+790h+var_28], rax
0x1400193c5  movups  [rsp+890h+var_870], xmm0
0x1400193ca  movups  xmmword ptr [rsp+890h+pv], xmm0
0x1400193cf  movups  [rsp+890h+var_850], xmm0
0x1400193d4  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1400193d9  mov     rcx, [rbx+0F0h]
0x1400193e0  lea     r9, [rsp+890h+var_870]
0x1400193e5  mov     r8, rax
0x1400193e8  call    TestUnlockData
0x1400193ed  mov     eax, dword ptr [rsp+890h+pv+4]
0x1400193f1  or      [rbx+40h], eax
0x1400193f4  cmp     [rsp+890h+pv+8], 0
0x1400193fa  jnz     short loc_140019406
0x1400193fc  mov     eax, dword ptr [rsp+890h+pv]
0x140019400  mov     [rbx+0B8h], eax
0x140019406  lea     rcx, [rsp+890h+var_840]
0x14001940b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140019410  mov     rcx, [rsp+890h+pv+8]; pv
0x140019415  call    cs:__imp_CoTaskMemFree
0x14001941b  dec     dword ptr [rbx+0E8h]
0x140019421  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x140019428  call    cs:__imp_LeaveCriticalSection
0x14001942e  mov     rcx, [rbp+790h+var_10]
0x140019435  xor     rcx, rsp; StackCookie
0x140019438  call    __security_check_cookie
0x14001943d  mov     rbx, [rsp+890h+arg_8]
0x140019445  add     rsp, 890h
0x14001944c  pop     rbp
0x14001944d  retn
```
