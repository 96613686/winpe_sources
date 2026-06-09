# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180022758`
- end: `0x180022886`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `27`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001ff14`
- `0x180022ff0`
- `0x180023070`
- `0x180096b30`
- `0x180096b60`
- `0x18009d84c`
- `0x18009d87c`
- `0x1800a178c`
- `0x1800a3d98`
- `0x1800b0db8`
- `0x1800b72c0`
- `0x1800b72f0`
- `0x1800bf474`
- `0x1800bf4a4`
- `0x1800c3b48`
- `0x1800d6314`
- `0x1800d6344`
- `0x1800dedd0`
- `0x1800dee00`
- `0x1800e46cc`
- `0x1800e46fc`
- `0x1800e784c`
- `0x1800ed70c`
- `0x1800ed73c`
- `0x1800fdd9c`
- `0x1800fddcc`
- `0x1800fe8e8`

## callees

- `0x18000c6e0`
- `0x180013590`
- `0x18001666c`
- `0x180022758`
- `0x180023ecc`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180022860`
- `KERNEL32!LeaveCriticalSection` at `0x180022860`
- `OLE32!CoTaskMemFree` at `0x18002284d`
- `OLE32!CoTaskMemFree` at `0x18002284d`

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
0x180022758  mov     [rsp-8+arg_8], rbx
0x18002275d  push    rbp
0x18002275e  lea     rbp, [rsp-790h]
0x180022766  sub     rsp, 890h
0x18002276d  mov     rax, cs:__security_cookie
0x180022774  xor     rax, rsp
0x180022777  mov     [rbp+790h+var_10], rax
0x18002277e  bts     dword ptr [rcx+40h], 0Bh
0x180022783  mov     rbx, rcx
0x180022786  cmp     qword ptr [rcx+0F0h], 0
0x18002278e  jz      loc_180022853
0x180022794  test    dword ptr [rcx+40h], 100h
0x18002279b  jnz     loc_180022853
0x1800227a1  test    dword ptr [rcx+14h], 8000h
0x1800227a8  jnz     loc_180022853
0x1800227ae  xorps   xmm0, xmm0
0x1800227b1  mov     [rsp+890h+var_840], 0
0x1800227ba  lea     rax, [rsp+890h+var_837]
0x1800227bf  mov     [rsp+890h+var_838], 0
0x1800227c4  mov     [rbp+790h+var_30], rax
0x1800227cb  lea     rdx, [rsp+890h+var_840]
0x1800227d0  lea     rax, [rbp+790h+var_37]
0x1800227d7  mov     [rsp+890h+var_837], 80408040h
0x1800227df  mov     [rbp+790h+var_20], rax
0x1800227e6  mov     r8d, 1
0x1800227ec  lea     rax, [rsp+890h+var_832]
0x1800227f1  mov     [rsp+890h+var_833], 0
0x1800227f6  mov     [rbp+790h+var_28], rax
0x1800227fd  movups  [rsp+890h+var_870], xmm0
0x180022802  movups  xmmword ptr [rsp+890h+pv], xmm0
0x180022807  movups  [rsp+890h+var_850], xmm0
0x18002280c  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180022811  mov     rcx, [rbx+0F0h]
0x180022818  lea     r9, [rsp+890h+var_870]
0x18002281d  mov     r8, rax
0x180022820  call    TestUnlockData
0x180022825  mov     eax, dword ptr [rsp+890h+pv+4]
0x180022829  or      [rbx+40h], eax
0x18002282c  cmp     [rsp+890h+pv+8], 0
0x180022832  jnz     short loc_18002283E
0x180022834  mov     eax, dword ptr [rsp+890h+pv]
0x180022838  mov     [rbx+0B8h], eax
0x18002283e  lea     rcx, [rsp+890h+var_840]
0x180022843  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022848  mov     rcx, [rsp+890h+pv+8]; pv
0x18002284d  call    cs:__imp_CoTaskMemFree
0x180022853  dec     dword ptr [rbx+0E8h]
0x180022859  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180022860  call    cs:__imp_LeaveCriticalSection
0x180022866  mov     rcx, [rbp+790h+var_10]
0x18002286d  xor     rcx, rsp; StackCookie
0x180022870  call    __security_check_cookie
0x180022875  mov     rbx, [rsp+890h+arg_8]
0x18002287d  add     rsp, 890h
0x180022884  pop     rbp
0x180022885  retn
```
