# ExecuteRemoveNotification(WiFiTaskOpcode,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x14000f1c8`
- end: `0x14000f32f`
- name: `?ExecuteRemoveNotification@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z`
- size: `359`
- prototype: `__int64 __fastcall(__int64, unsigned int **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006b40`

## callees

- `0x1400016a0`
- `0x14000f1c8`
- `0x140010178`
- `0x140012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x14000f208`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x14000f208`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f23b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f23b`

## pseudocode

```c
__int64 __fastcall ExecuteRemoveNotification(__int64 a1, unsigned int **a2)
{
  HRESULT v2; // ebx
  int v3; // r8d
  __int64 v5; // [rsp+40h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-38h] BYREF
  _OWORD v7[2]; // [rsp+50h] [rbp-30h] BYREF
  __int16 v8; // [rsp+70h] [rbp-10h]

  memset(v7, 0, sizeof(v7));
  v8 = 0;
  _o__itow_s(**a2, v7, 17, 10);
  ppv = 0;
  v5 = 0;
  v2 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         4u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &ppv);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v5);
    if ( v2 >= 0 )
      v2 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, _OWORD *, _QWORD))(*(_QWORD *)v5 + 80LL))(
             v5,
             L"System",
             L"Windows.SystemToast.WiFiNetworkManager",
             0,
             v7,
             0);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v3, (unsigned int)v7, v2);
  }
  if ( v2 < 0 )
  {
    if ( (v2 & 0x1FFF0000) == 0x70000 )
      v2 = (unsigned __int16)v2;
  }
  else
  {
    v2 = 0;
  }
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000f1c8  mov     [rsp-8+arg_0], rbx
0x14000f1cd  push    rbp
0x14000f1ce  mov     rbp, rsp
0x14000f1d1  sub     rsp, 80h
0x14000f1d8  mov     rax, cs:__security_cookie
0x14000f1df  xor     rax, rsp
0x14000f1e2  mov     [rbp+var_8], rax
0x14000f1e6  xorps   xmm0, xmm0
0x14000f1e9  xor     eax, eax
0x14000f1eb  movups  [rbp+var_30], xmm0
0x14000f1ef  movups  [rbp+var_20], xmm0
0x14000f1f3  mov     [rbp+var_10], ax
0x14000f1f7  mov     rcx, [rdx]
0x14000f1fa  lea     r9d, [rax+0Ah]
0x14000f1fe  lea     r8d, [rax+11h]
0x14000f202  lea     rdx, [rbp+var_30]
0x14000f206  mov     ecx, [rcx]
0x14000f208  call    cs:__imp__o__itow_s
0x14000f20e  mov     [rbp+var_38], 0
0x14000f216  mov     [rbp+var_40], 0
0x14000f21e  lea     rax, [rbp+var_38]
0x14000f222  mov     [rsp+80h+ppv], rax; ppv
0x14000f227  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x14000f22e  xor     edx, edx; pUnkOuter
0x14000f230  lea     r8d, [rdx+4]; dwClsContext
0x14000f234  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x14000f23b  call    cs:__imp_CoCreateInstance
0x14000f241  mov     ebx, eax
0x14000f243  test    eax, eax
0x14000f245  js      short loc_14000F296
0x14000f247  mov     rcx, [rbp+var_38]
0x14000f24b  mov     rax, [rcx]
0x14000f24e  lea     rdx, [rbp+var_40]
0x14000f252  mov     rax, [rax+18h]
0x14000f256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f25b  mov     ebx, eax
0x14000f25d  test    eax, eax
0x14000f25f  js      short loc_14000F296
0x14000f261  mov     rcx, [rbp+var_40]
0x14000f265  mov     rax, [rcx]
0x14000f268  mov     [rsp+80h+var_58], 0
0x14000f271  lea     rdx, [rbp+var_30]
0x14000f275  mov     [rsp+80h+ppv], rdx
0x14000f27a  xor     r9d, r9d
0x14000f27d  lea     r8, aWindowsSystemt; "Windows.SystemToast.WiFiNetworkManager"
0x14000f284  lea     rdx, aSystem; "System"
0x14000f28b  mov     rax, [rax+50h]
0x14000f28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f294  mov     ebx, eax
0x14000f296  lea     rax, WPP_GLOBAL_Control
0x14000f29d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f2a4  cmp     rcx, rax
0x14000f2a7  jz      short loc_14000F2CB
0x14000f2a9  cmp     byte ptr [rcx+19h], 4
0x14000f2ad  jb      short loc_14000F2CB
0x14000f2af  test    byte ptr [rcx+1Ch], 1
0x14000f2b3  jz      short loc_14000F2CB
0x14000f2b5  mov     edx, 15h
0x14000f2ba  mov     dword ptr [rsp+80h+ppv], ebx
0x14000f2be  lea     r9, [rbp+var_30]
0x14000f2c2  mov     rcx, [rcx+10h]
0x14000f2c6  call    WPP_SF_SD
0x14000f2cb  test    ebx, ebx
0x14000f2cd  js      short loc_14000F2D3
0x14000f2cf  xor     ebx, ebx
0x14000f2d1  jmp     short loc_14000F2E4
0x14000f2d3  mov     eax, ebx
0x14000f2d5  and     eax, 1FFF0000h
0x14000f2da  cmp     eax, 70000h
0x14000f2df  jnz     short loc_14000F2E4
0x14000f2e1  movzx   ebx, bx
0x14000f2e4  mov     rcx, [rbp+var_40]
0x14000f2e8  test    rcx, rcx
0x14000f2eb  jz      short loc_14000F2FA
0x14000f2ed  mov     rax, [rcx]
0x14000f2f0  mov     rax, [rax+10h]
0x14000f2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f2f9  nop
0x14000f2fa  mov     rcx, [rbp+var_38]
0x14000f2fe  test    rcx, rcx
0x14000f301  jz      short loc_14000F310
0x14000f303  mov     rdx, [rcx]
0x14000f306  mov     rax, [rdx+10h]
0x14000f30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f30f  nop
0x14000f310  mov     eax, ebx
0x14000f312  mov     rcx, [rbp+var_8]
0x14000f316  xor     rcx, rsp; StackCookie
0x14000f319  call    __security_check_cookie
0x14000f31e  mov     rbx, [rsp+80h+arg_0]
0x14000f326  add     rsp, 80h
0x14000f32d  pop     rbp
0x14000f32e  retn
```
