# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x140035020`
- end: `0x140035150`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000f0f4`
- `0x140020ed0`

## callees

- `0x140005240`
- `0x14000f22c`
- `0x140034cb0`
- `0x140035020`
- `0x14003865c`
- `0x14003a02c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003512a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003512a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035117`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035117`

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
    v2 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v7, 1);
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
0x140035020  mov     [rsp-8+arg_8], rbx
0x140035025  push    rbp
0x140035026  lea     rbp, [rsp-790h]
0x14003502e  sub     rsp, 890h
0x140035035  mov     rax, cs:__security_cookie
0x14003503c  xor     rax, rsp
0x14003503f  mov     [rbp+790h+var_10], rax
0x140035046  bts     dword ptr [rcx+40h], 0Bh
0x14003504b  mov     rbx, rcx
0x14003504e  cmp     qword ptr [rcx+0F0h], 0
0x140035056  jz      loc_14003511D
0x14003505c  test    dword ptr [rcx+40h], 100h
0x140035063  jnz     loc_14003511D
0x140035069  xorps   xmm0, xmm0
0x14003506c  mov     [rsp+890h+var_840], 0
0x140035075  lea     rax, [rsp+890h+var_837]
0x14003507a  mov     [rsp+890h+var_838], 0
0x14003507f  mov     [rbp+790h+var_30], rax
0x140035086  lea     rdx, [rsp+890h+var_840]
0x14003508b  lea     rax, [rbp+790h+var_37]
0x140035092  mov     [rsp+890h+var_837], 80408040h
0x14003509a  mov     [rbp+790h+var_20], rax
0x1400350a1  mov     r8d, 1
0x1400350a7  lea     rax, [rsp+890h+var_832]
0x1400350ac  mov     [rsp+890h+var_833], 0
0x1400350b1  mov     [rbp+790h+var_28], rax
0x1400350b8  movups  [rsp+890h+var_870], xmm0
0x1400350bd  movups  xmmword ptr [rsp+890h+pv], xmm0
0x1400350c2  movups  [rsp+890h+var_850], xmm0
0x1400350c7  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1400350cc  mov     rcx, [rbx+0F0h]
0x1400350d3  lea     r9, [rsp+890h+var_870]
0x1400350d8  mov     r8, rax
0x1400350db  call    TestUnlockData
0x1400350e0  mov     eax, dword ptr [rsp+890h+pv+4]
0x1400350e4  or      [rbx+40h], eax
0x1400350e7  cmp     [rsp+890h+pv+8], 0
0x1400350ed  jz      short loc_1400350FE
0x1400350ef  lea     rdx, [rsp+890h+var_870]
0x1400350f4  mov     rcx, rbx
0x1400350f7  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1400350fc  jmp     short loc_140035108
0x1400350fe  mov     eax, dword ptr [rsp+890h+pv]
0x140035102  mov     [rbx+0B8h], eax
0x140035108  lea     rcx, [rsp+890h+var_840]
0x14003510d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140035112  mov     rcx, [rsp+890h+pv+8]; pv
0x140035117  call    cs:__imp_CoTaskMemFree
0x14003511d  dec     dword ptr [rbx+0E8h]
0x140035123  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x14003512a  call    cs:__imp_LeaveCriticalSection
0x140035130  mov     rcx, [rbp+790h+var_10]
0x140035137  xor     rcx, rsp; StackCookie
0x14003513a  call    __security_check_cookie
0x14003513f  mov     rbx, [rsp+890h+arg_8]
0x140035147  add     rsp, 890h
0x14003514e  pop     rbp
0x14003514f  retn
```
