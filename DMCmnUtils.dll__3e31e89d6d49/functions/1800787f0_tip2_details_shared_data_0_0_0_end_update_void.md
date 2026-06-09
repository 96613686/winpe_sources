# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x1800787f0`
- end: `0x18007892b`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180074a34`

## callees

- `0x180007270`
- `0x18005b938`
- `0x1800787f0`
- `0x180079b10`
- `0x18007a278`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800788fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800788fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800788e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800788e5`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int128 v4; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h]
  __int128 v6; // [rsp+40h] [rbp-C0h]
  __int64 v7; // [rsp+50h] [rbp-B0h] BYREF
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
0x1800787f0  mov     [rsp-8+arg_8], rbx
0x1800787f5  push    rbp
0x1800787f6  lea     rbp, [rsp-790h]
0x1800787fe  sub     rsp, 890h
0x180078805  mov     rax, cs:__security_cookie
0x18007880c  xor     rax, rsp
0x18007880f  mov     [rbp+790h+var_10], rax
0x180078816  bts     dword ptr [rcx+40h], 0Bh
0x18007881b  mov     rbx, rcx
0x18007881e  cmp     qword ptr [rcx+0F0h], 0
0x180078826  jz      loc_1800788F1
0x18007882c  test    dword ptr [rcx+40h], 100h
0x180078833  jnz     loc_1800788F1
0x180078839  test    dword ptr [rcx+14h], 8000h
0x180078840  jnz     loc_1800788F1
0x180078846  xorps   xmm0, xmm0
0x180078849  mov     [rsp+890h+var_840], 0
0x180078852  lea     rax, [rsp+890h+var_837]
0x180078857  mov     [rsp+890h+var_838], 0
0x18007885c  mov     [rbp+790h+var_30], rax
0x180078863  lea     rdx, [rsp+890h+var_840]
0x180078868  lea     rax, [rbp+790h+var_37]
0x18007886f  mov     [rsp+890h+var_837], 80408040h
0x180078877  mov     [rbp+790h+var_20], rax
0x18007887e  mov     r8d, 1
0x180078884  lea     rax, [rsp+890h+var_832]
0x180078889  mov     [rsp+890h+var_833], 0
0x18007888e  mov     [rbp+790h+var_28], rax
0x180078895  movups  [rsp+890h+var_870], xmm0
0x18007889a  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18007889f  movups  [rsp+890h+var_850], xmm0
0x1800788a4  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800788a9  mov     rcx, [rbx+0F0h]
0x1800788b0  lea     r9, [rsp+890h+var_870]
0x1800788b5  mov     r8, rax
0x1800788b8  call    TestUnlockData
0x1800788bd  mov     eax, dword ptr [rsp+890h+pv+4]
0x1800788c1  or      [rbx+40h], eax
0x1800788c4  cmp     [rsp+890h+pv+8], 0
0x1800788ca  jnz     short loc_1800788D6
0x1800788cc  mov     eax, dword ptr [rsp+890h+pv]
0x1800788d0  mov     [rbx+0B8h], eax
0x1800788d6  lea     rcx, [rsp+890h+var_840]
0x1800788db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800788e0  mov     rcx, [rsp+890h+pv+8]; pv
0x1800788e5  call    cs:__imp_CoTaskMemFree
0x1800788ec  nop     dword ptr [rax+rax+00h]
0x1800788f1  dec     dword ptr [rbx+0E8h]
0x1800788f7  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800788fe  call    cs:__imp_LeaveCriticalSection
0x180078905  nop     dword ptr [rax+rax+00h]
0x18007890a  mov     rcx, [rbp+790h+var_10]
0x180078911  xor     rcx, rsp; StackCookie
0x180078914  call    __security_check_cookie
0x180078919  mov     rbx, [rsp+890h+arg_8]
0x180078921  add     rsp, 890h
0x180078928  pop     rbp
0x180078929  retn
```
