# tip2::details::shared_data<0,0,1>::end_update(void)

- ea: `0x1800c6fe4`
- end: `0x1800c7112`
- name: `?end_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c4240`

## callees

- `0x180005860`
- `0x18006cecc`
- `0x18007437c`
- `0x1800c6fe4`
- `0x1800c7b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c70ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c70ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c70d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c70d9`

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
0x1800c6fe4  mov     [rsp-8+arg_8], rbx
0x1800c6fe9  push    rbp
0x1800c6fea  lea     rbp, [rsp-790h]
0x1800c6ff2  sub     rsp, 890h
0x1800c6ff9  mov     rax, cs:__security_cookie
0x1800c7000  xor     rax, rsp
0x1800c7003  mov     [rbp+790h+var_10], rax
0x1800c700a  bts     dword ptr [rcx+40h], 0Bh
0x1800c700f  mov     rbx, rcx
0x1800c7012  cmp     qword ptr [rcx+0F0h], 0
0x1800c701a  jz      loc_1800C70DF
0x1800c7020  test    dword ptr [rcx+40h], 100h
0x1800c7027  jnz     loc_1800C70DF
0x1800c702d  test    dword ptr [rcx+14h], 8000h
0x1800c7034  jnz     loc_1800C70DF
0x1800c703a  xorps   xmm0, xmm0
0x1800c703d  mov     [rsp+890h+var_840], 0
0x1800c7046  lea     rax, [rsp+890h+var_837]
0x1800c704b  mov     [rsp+890h+var_838], 0
0x1800c7050  mov     [rbp+790h+var_30], rax
0x1800c7057  lea     rdx, [rsp+890h+var_840]
0x1800c705c  lea     rax, [rbp+790h+var_37]
0x1800c7063  mov     [rsp+890h+var_837], 80408040h
0x1800c706b  mov     [rbp+790h+var_20], rax
0x1800c7072  mov     r8d, 1
0x1800c7078  lea     rax, [rsp+890h+var_832]
0x1800c707d  mov     [rsp+890h+var_833], 0
0x1800c7082  mov     [rbp+790h+var_28], rax
0x1800c7089  movups  [rsp+890h+var_870], xmm0
0x1800c708e  movups  xmmword ptr [rsp+890h+pv], xmm0
0x1800c7093  movups  [rsp+890h+var_850], xmm0
0x1800c7098  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800c709d  mov     rcx, [rbx+0F0h]
0x1800c70a4  lea     r9, [rsp+890h+var_870]
0x1800c70a9  mov     r8, rax
0x1800c70ac  call    TestUnlockData
0x1800c70b1  mov     eax, dword ptr [rsp+890h+pv+4]
0x1800c70b5  or      [rbx+40h], eax
0x1800c70b8  cmp     [rsp+890h+pv+8], 0
0x1800c70be  jnz     short loc_1800C70CA
0x1800c70c0  mov     eax, dword ptr [rsp+890h+pv]
0x1800c70c4  mov     [rbx+0B8h], eax
0x1800c70ca  lea     rcx, [rsp+890h+var_840]
0x1800c70cf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800c70d4  mov     rcx, [rsp+890h+pv+8]; pv
0x1800c70d9  call    cs:__imp_CoTaskMemFree
0x1800c70df  dec     dword ptr [rbx+0E8h]
0x1800c70e5  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800c70ec  call    cs:__imp_LeaveCriticalSection
0x1800c70f2  mov     rcx, [rbp+790h+var_10]
0x1800c70f9  xor     rcx, rsp; StackCookie
0x1800c70fc  call    __security_check_cookie
0x1800c7101  mov     rbx, [rsp+890h+arg_8]
0x1800c7109  add     rsp, 890h
0x1800c7110  pop     rbp
0x1800c7111  retn
```
