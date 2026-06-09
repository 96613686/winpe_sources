# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x1800cd0cc`
- end: `0x1800cd1fc`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c9b14`
- `0x1800d8920`

## callees

- `0x180005860`
- `0x18006cecc`
- `0x180073ba0`
- `0x18007437c`
- `0x1800ccf38`
- `0x1800cd0cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd1d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd1d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd1c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd1c3`

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
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v7, 1);
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
0x1800cd0cc  mov     [rsp-8+arg_8], rbx
0x1800cd0d1  push    rbp
0x1800cd0d2  lea     rbp, [rsp-790h]
0x1800cd0da  sub     rsp, 890h
0x1800cd0e1  mov     rax, cs:__security_cookie
0x1800cd0e8  xor     rax, rsp
0x1800cd0eb  mov     [rbp+790h+var_10], rax
0x1800cd0f2  bts     dword ptr [rcx+40h], 0Bh
0x1800cd0f7  mov     rbx, rcx
0x1800cd0fa  cmp     qword ptr [rcx+0F0h], 0
0x1800cd102  jz      loc_1800CD1C9
0x1800cd108  test    dword ptr [rcx+40h], 100h
0x1800cd10f  jnz     loc_1800CD1C9
0x1800cd115  xorps   xmm0, xmm0
0x1800cd118  mov     [rsp+890h+var_840], 0
0x1800cd121  lea     rax, [rsp+890h+var_837]
0x1800cd126  mov     [rsp+890h+var_838], 0
0x1800cd12b  mov     [rbp+790h+var_30], rax
0x1800cd132  lea     rdx, [rsp+890h+var_840]
0x1800cd137  lea     rax, [rbp+790h+var_37]
0x1800cd13e  mov     [rsp+890h+var_837], 80408040h
0x1800cd146  mov     [rbp+790h+var_20], rax
0x1800cd14d  mov     r8d, 1
0x1800cd153  lea     rax, [rsp+890h+var_832]
0x1800cd158  mov     [rsp+890h+var_833], 0
0x1800cd15d  mov     [rbp+790h+var_28], rax
0x1800cd164  movups  [rsp+890h+var_870], xmm0
0x1800cd169  movups  xmmword ptr [rsp+890h+pv], xmm0
0x1800cd16e  movups  [rsp+890h+var_850], xmm0
0x1800cd173  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800cd178  mov     rcx, [rbx+0F0h]
0x1800cd17f  lea     r9, [rsp+890h+var_870]
0x1800cd184  mov     r8, rax
0x1800cd187  call    TestUnlockData
0x1800cd18c  mov     eax, dword ptr [rsp+890h+pv+4]
0x1800cd190  or      [rbx+40h], eax
0x1800cd193  cmp     [rsp+890h+pv+8], 0
0x1800cd199  jz      short loc_1800CD1AA
0x1800cd19b  lea     rdx, [rsp+890h+var_870]
0x1800cd1a0  mov     rcx, rbx
0x1800cd1a3  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800cd1a8  jmp     short loc_1800CD1B4
0x1800cd1aa  mov     eax, dword ptr [rsp+890h+pv]
0x1800cd1ae  mov     [rbx+0B8h], eax
0x1800cd1b4  lea     rcx, [rsp+890h+var_840]
0x1800cd1b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800cd1be  mov     rcx, [rsp+890h+pv+8]; pv
0x1800cd1c3  call    cs:__imp_CoTaskMemFree
0x1800cd1c9  dec     dword ptr [rbx+0E8h]
0x1800cd1cf  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800cd1d6  call    cs:__imp_LeaveCriticalSection
0x1800cd1dc  mov     rcx, [rbp+790h+var_10]
0x1800cd1e3  xor     rcx, rsp; StackCookie
0x1800cd1e6  call    __security_check_cookie
0x1800cd1eb  mov     rbx, [rsp+890h+arg_8]
0x1800cd1f3  add     rsp, 890h
0x1800cd1fa  pop     rbp
0x1800cd1fb  retn
```
