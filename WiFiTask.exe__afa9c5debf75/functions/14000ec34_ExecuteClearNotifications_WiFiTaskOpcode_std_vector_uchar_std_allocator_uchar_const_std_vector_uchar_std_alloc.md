# ExecuteClearNotifications(WiFiTaskOpcode,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x14000ec34`
- end: `0x14000ed42`
- name: `?ExecuteClearNotifications@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z`
- size: `270`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006b40`

## callees

- `0x14000bf20`
- `0x14000ec34`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ec70`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ec70`

## pseudocode

```c
__int64 ExecuteClearNotifications()
{
  HRESULT v0; // ebx
  LPVOID v2; // [rsp+48h] [rbp+10h] BYREF
  __int64 v3; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  v3 = 0;
  v0 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         4u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &v2);
  if ( v0 >= 0 )
  {
    v0 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v2 + 24LL))(v2, &v3);
    if ( v0 >= 0 )
      v0 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v3 + 72LL))(
             v3,
             L"System",
             L"Windows.SystemToast.WiFiNetworkManager",
             0);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      &WPP_d7e0deef0d8c389735c42bf67fb2c31a_Traceguids,
      (unsigned int)v0);
  }
  if ( v0 < 0 )
  {
    if ( (v0 & 0x1FFF0000) == 0x70000 )
      v0 = (unsigned __int16)v0;
  }
  else
  {
    v0 = 0;
  }
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v2 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000ec34  mov     r11, rsp
0x14000ec37  mov     [r11+18h], r8
0x14000ec3b  mov     [r11+10h], rdx
0x14000ec3f  push    rbx
0x14000ec40  sub     rsp, 30h
0x14000ec44  mov     qword ptr [r11+10h], 0
0x14000ec4c  mov     qword ptr [r11+18h], 0
0x14000ec54  lea     rax, [r11+10h]
0x14000ec58  mov     [r11-18h], rax
0x14000ec5c  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x14000ec63  xor     edx, edx; pUnkOuter
0x14000ec65  lea     r8d, [rdx+4]; dwClsContext
0x14000ec69  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x14000ec70  call    cs:__imp_CoCreateInstance
0x14000ec76  mov     ebx, eax
0x14000ec78  test    eax, eax
0x14000ec7a  js      short loc_14000ECBC
0x14000ec7c  mov     rcx, [rsp+38h+arg_8]
0x14000ec81  mov     rax, [rcx]
0x14000ec84  lea     rdx, [rsp+38h+arg_10]
0x14000ec89  mov     rax, [rax+18h]
0x14000ec8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec92  mov     ebx, eax
0x14000ec94  test    eax, eax
0x14000ec96  js      short loc_14000ECBC
0x14000ec98  mov     rcx, [rsp+38h+arg_10]
0x14000ec9d  mov     rax, [rcx]
0x14000eca0  xor     r9d, r9d
0x14000eca3  lea     r8, aWindowsSystemt; "Windows.SystemToast.WiFiNetworkManager"
0x14000ecaa  lea     rdx, aSystem; "System"
0x14000ecb1  mov     rax, [rax+48h]
0x14000ecb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ecba  mov     ebx, eax
0x14000ecbc  lea     rax, WPP_GLOBAL_Control
0x14000ecc3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ecca  cmp     rcx, rax
0x14000eccd  jz      short loc_14000ECF3
0x14000eccf  cmp     byte ptr [rcx+19h], 4
0x14000ecd3  jb      short loc_14000ECF3
0x14000ecd5  test    byte ptr [rcx+1Ch], 1
0x14000ecd9  jz      short loc_14000ECF3
0x14000ecdb  mov     edx, 16h
0x14000ece0  mov     r9d, ebx
0x14000ece3  lea     r8, WPP_d7e0deef0d8c389735c42bf67fb2c31a_Traceguids
0x14000ecea  mov     rcx, [rcx+10h]
0x14000ecee  call    WPP_SF_d
0x14000ecf3  test    ebx, ebx
0x14000ecf5  js      short loc_14000ECFB
0x14000ecf7  xor     ebx, ebx
0x14000ecf9  jmp     short loc_14000ED0C
0x14000ecfb  mov     eax, ebx
0x14000ecfd  and     eax, 1FFF0000h
0x14000ed02  cmp     eax, 70000h
0x14000ed07  jnz     short loc_14000ED0C
0x14000ed09  movzx   ebx, bx
0x14000ed0c  mov     rcx, [rsp+38h+arg_10]
0x14000ed11  test    rcx, rcx
0x14000ed14  jz      short loc_14000ED23
0x14000ed16  mov     rax, [rcx]
0x14000ed19  mov     rax, [rax+10h]
0x14000ed1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed22  nop
0x14000ed23  mov     rcx, [rsp+38h+arg_8]
0x14000ed28  test    rcx, rcx
0x14000ed2b  jz      short loc_14000ED3A
0x14000ed2d  mov     rdx, [rcx]
0x14000ed30  mov     rax, [rdx+10h]
0x14000ed34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed39  nop
0x14000ed3a  mov     eax, ebx
0x14000ed3c  add     rsp, 30h
0x14000ed40  pop     rbx
0x14000ed41  retn
```
