# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x18004e8f4`
- end: `0x18004ea2a`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `310`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180031c34`
- `0x180044700`

## callees

- `0x180004ca0`
- `0x18004e4d0`
- `0x18004e8f4`
- `0x180053bb4`
- `0x180054e14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ea04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ea04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e9e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e9f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e9e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e9f1`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int128 v4; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID v5[2]; // [rsp+30h] [rbp-D0h]
  __int128 v6; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
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
    pv = 0;
    v8 = 0;
    v13 = &v9;
    v9 = -2143256512;
    v15 = &v12;
    v10 = 0;
    v14 = &v11;
    v4 = 0;
    *(_OWORD *)v5 = 0;
    v6 = 0;
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
    ((void (__fastcall *)(_QWORD, __int64, __int64, __int128 *))TestUnlockData)(*(_QWORD *)(a1 + 240), v3, v2, &v4);
    *(_DWORD *)(a1 + 64) |= HIDWORD(v5[0]);
    if ( v5[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v4);
    else
      *(_DWORD *)(a1 + 184) = v5[0];
    if ( pv )
      CoTaskMemFree(pv);
    CoTaskMemFree(v5[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x18004e8f4  mov     [rsp-8+arg_8], rbx
0x18004e8f9  push    rbp
0x18004e8fa  lea     rbp, [rsp-790h]
0x18004e902  sub     rsp, 890h
0x18004e909  mov     rax, cs:__security_cookie
0x18004e910  xor     rax, rsp
0x18004e913  mov     [rbp+790h+var_10], rax
0x18004e91a  bts     dword ptr [rcx+40h], 0Bh
0x18004e91f  mov     rbx, rcx
0x18004e922  cmp     qword ptr [rcx+0F0h], 0
0x18004e92a  jz      loc_18004E9F7
0x18004e930  test    dword ptr [rcx+40h], 100h
0x18004e937  jnz     loc_18004E9F7
0x18004e93d  xorps   xmm0, xmm0
0x18004e940  mov     [rsp+890h+pv], 0
0x18004e949  lea     rax, [rsp+890h+var_837]
0x18004e94e  mov     [rsp+890h+var_838], 0
0x18004e953  mov     [rbp+790h+var_30], rax
0x18004e95a  lea     rdx, [rsp+890h+pv]
0x18004e95f  lea     rax, [rbp+790h+var_37]
0x18004e966  mov     [rsp+890h+var_837], 80408040h
0x18004e96e  mov     [rbp+790h+var_20], rax
0x18004e975  mov     r8d, 1
0x18004e97b  lea     rax, [rsp+890h+var_832]
0x18004e980  mov     [rsp+890h+var_833], 0
0x18004e985  mov     [rbp+790h+var_28], rax
0x18004e98c  movups  [rsp+890h+var_870], xmm0
0x18004e991  movups  xmmword ptr [rsp+890h+var_860], xmm0
0x18004e996  movups  [rsp+890h+var_850], xmm0
0x18004e99b  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18004e9a0  mov     rcx, [rbx+0F0h]
0x18004e9a7  lea     r9, [rsp+890h+var_870]
0x18004e9ac  mov     r8, rax
0x18004e9af  call    TestUnlockData
0x18004e9b4  mov     eax, dword ptr [rsp+890h+var_860+4]
0x18004e9b8  or      [rbx+40h], eax
0x18004e9bb  cmp     [rsp+890h+var_860+8], 0
0x18004e9c1  jz      short loc_18004E9D2
0x18004e9c3  lea     rdx, [rsp+890h+var_870]
0x18004e9c8  mov     rcx, rbx
0x18004e9cb  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004e9d0  jmp     short loc_18004E9DC
0x18004e9d2  mov     eax, dword ptr [rsp+890h+var_860]
0x18004e9d6  mov     [rbx+0B8h], eax
0x18004e9dc  mov     rcx, [rsp+890h+pv]; pv
0x18004e9e1  test    rcx, rcx
0x18004e9e4  jz      short loc_18004E9EC
0x18004e9e6  call    cs:__imp_CoTaskMemFree
0x18004e9ec  mov     rcx, [rsp+890h+var_860+8]; pv
0x18004e9f1  call    cs:__imp_CoTaskMemFree
0x18004e9f7  dec     dword ptr [rbx+0E8h]
0x18004e9fd  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18004ea04  call    cs:__imp_LeaveCriticalSection
0x18004ea0a  mov     rcx, [rbp+790h+var_10]
0x18004ea11  xor     rcx, rsp; StackCookie
0x18004ea14  call    __security_check_cookie
0x18004ea19  mov     rbx, [rsp+890h+arg_8]
0x18004ea21  add     rsp, 890h
0x18004ea28  pop     rbp
0x18004ea29  retn
```
