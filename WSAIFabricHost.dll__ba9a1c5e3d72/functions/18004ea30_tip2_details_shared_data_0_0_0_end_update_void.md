# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x18004ea30`
- end: `0x18004eb69`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `313`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180031bac`
- `0x180031cbc`
- `0x180031d44`
- `0x180031dcc`
- `0x180051d68`

## callees

- `0x180004ca0`
- `0x18004ea30`
- `0x180053bb4`
- `0x180054e14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004eb43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004eb43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eb22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eb30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eb22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eb30`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  void *v4; // rdx
  __int128 v5; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID v6[2]; // [rsp+30h] [rbp-D0h]
  __int128 v7; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  char v9; // [rsp+58h] [rbp-A8h]
  int v10; // [rsp+59h] [rbp-A7h] BYREF
  char v11; // [rsp+5Dh] [rbp-A3h]
  char v12; // [rsp+5Eh] [rbp-A2h] BYREF
  char v13; // [rsp+859h] [rbp+759h] BYREF
  int *v14; // [rsp+860h] [rbp+760h]
  char *v15; // [rsp+868h] [rbp+768h]
  char *v16; // [rsp+870h] [rbp+770h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
  {
    pv = 0;
    v9 = 0;
    v14 = &v10;
    v10 = -2143256512;
    v16 = &v13;
    v11 = 0;
    v15 = &v12;
    v5 = 0;
    *(_OWORD *)v6 = 0;
    v7 = 0;
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
    ((void (__fastcall *)(_QWORD, __int64, __int64, __int128 *))TestUnlockData)(*(_QWORD *)(a1 + 240), v3, v2, &v5);
    *(_DWORD *)(a1 + 64) |= HIDWORD(v6[0]);
    v4 = v6[1];
    if ( !v6[1] )
      *(_DWORD *)(a1 + 184) = v6[0];
    if ( pv )
    {
      CoTaskMemFree(pv);
      v4 = v6[1];
    }
    CoTaskMemFree(v4);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x18004ea30  mov     [rsp-8+arg_8], rbx
0x18004ea35  push    rbp
0x18004ea36  lea     rbp, [rsp-790h]
0x18004ea3e  sub     rsp, 890h
0x18004ea45  mov     rax, cs:__security_cookie
0x18004ea4c  xor     rax, rsp
0x18004ea4f  mov     [rbp+790h+var_10], rax
0x18004ea56  bts     dword ptr [rcx+40h], 0Bh
0x18004ea5b  mov     rbx, rcx
0x18004ea5e  cmp     qword ptr [rcx+0F0h], 0
0x18004ea66  jz      loc_18004EB36
0x18004ea6c  test    dword ptr [rcx+40h], 100h
0x18004ea73  jnz     loc_18004EB36
0x18004ea79  test    dword ptr [rcx+14h], 8000h
0x18004ea80  jnz     loc_18004EB36
0x18004ea86  xorps   xmm0, xmm0
0x18004ea89  mov     [rsp+890h+pv], 0
0x18004ea92  lea     rax, [rsp+890h+var_837]
0x18004ea97  mov     [rsp+890h+var_838], 0
0x18004ea9c  mov     [rbp+790h+var_30], rax
0x18004eaa3  lea     rdx, [rsp+890h+pv]
0x18004eaa8  lea     rax, [rbp+790h+var_37]
0x18004eaaf  mov     [rsp+890h+var_837], 80408040h
0x18004eab7  mov     [rbp+790h+var_20], rax
0x18004eabe  mov     r8d, 1
0x18004eac4  lea     rax, [rsp+890h+var_832]
0x18004eac9  mov     [rsp+890h+var_833], 0
0x18004eace  mov     [rbp+790h+var_28], rax
0x18004ead5  movups  [rsp+890h+var_870], xmm0
0x18004eada  movups  xmmword ptr [rsp+890h+var_860], xmm0
0x18004eadf  movups  [rsp+890h+var_850], xmm0
0x18004eae4  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18004eae9  mov     rcx, [rbx+0F0h]
0x18004eaf0  lea     r9, [rsp+890h+var_870]
0x18004eaf5  mov     r8, rax
0x18004eaf8  call    TestUnlockData
0x18004eafd  mov     eax, dword ptr [rsp+890h+var_860+4]
0x18004eb01  or      [rbx+40h], eax
0x18004eb04  mov     rdx, [rsp+890h+var_860+8]
0x18004eb09  test    rdx, rdx
0x18004eb0c  jnz     short loc_18004EB18
0x18004eb0e  mov     eax, dword ptr [rsp+890h+var_860]
0x18004eb12  mov     [rbx+0B8h], eax
0x18004eb18  mov     rcx, [rsp+890h+pv]; pv
0x18004eb1d  test    rcx, rcx
0x18004eb20  jz      short loc_18004EB2D
0x18004eb22  call    cs:__imp_CoTaskMemFree
0x18004eb28  mov     rdx, [rsp+890h+var_860+8]
0x18004eb2d  mov     rcx, rdx; pv
0x18004eb30  call    cs:__imp_CoTaskMemFree
0x18004eb36  dec     dword ptr [rbx+0E8h]
0x18004eb3c  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18004eb43  call    cs:__imp_LeaveCriticalSection
0x18004eb49  mov     rcx, [rbp+790h+var_10]
0x18004eb50  xor     rcx, rsp; StackCookie
0x18004eb53  call    __security_check_cookie
0x18004eb58  mov     rbx, [rsp+890h+arg_8]
0x18004eb60  add     rsp, 890h
0x18004eb67  pop     rbp
0x18004eb68  retn
```
