# ExecuteClearWwanNotifications(WiFiTaskOpcode,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x14000ed48`
- end: `0x14000ee5b`
- name: `?ExecuteClearWwanNotifications@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z`
- size: `275`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006b40`

## callees

- `0x14000bf20`
- `0x14000ed48`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ed87`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ed87`

## pseudocode

```c
__int64 __fastcall ExecuteClearWwanNotifications(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v3; // rdi
  HRESULT v4; // ebx
  LPVOID v6; // [rsp+48h] [rbp+10h] BYREF
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = a3;
  v3 = *a2;
  v6 = 0;
  v7 = 0;
  v4 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         4u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &v6);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v6 + 24LL))(v6, &v7);
    if ( v4 >= 0 )
      v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v7 + 72LL))(
             v7,
             v3 + 18,
             v3 + 274,
             0);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_d7e0deef0d8c389735c42bf67fb2c31a_Traceguids,
      (unsigned int)v4);
  }
  if ( v4 < 0 )
  {
    if ( (v4 & 0x1FFF0000) == 0x70000 )
      v4 = (unsigned __int16)v4;
  }
  else
  {
    v4 = 0;
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000ed48  mov     r11, rsp
0x14000ed4b  mov     [r11+8], rbx
0x14000ed4f  mov     [r11+18h], r8
0x14000ed53  push    rdi
0x14000ed54  sub     rsp, 30h
0x14000ed58  mov     rdi, [rdx]
0x14000ed5b  mov     qword ptr [r11+10h], 0
0x14000ed63  mov     qword ptr [r11+18h], 0
0x14000ed6b  lea     rax, [r11+10h]
0x14000ed6f  mov     [r11-18h], rax
0x14000ed73  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x14000ed7a  xor     edx, edx; pUnkOuter
0x14000ed7c  lea     r8d, [rdx+4]; dwClsContext
0x14000ed80  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x14000ed87  call    cs:__imp_CoCreateInstance
0x14000ed8d  mov     ebx, eax
0x14000ed8f  test    eax, eax
0x14000ed91  js      short loc_14000EDD0
0x14000ed93  mov     rcx, [rsp+38h+arg_8]
0x14000ed98  mov     rax, [rcx]
0x14000ed9b  lea     rdx, [rsp+38h+arg_10]
0x14000eda0  mov     rax, [rax+18h]
0x14000eda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eda9  mov     ebx, eax
0x14000edab  test    eax, eax
0x14000edad  js      short loc_14000EDD0
0x14000edaf  mov     rcx, [rsp+38h+arg_10]
0x14000edb4  mov     rax, [rcx]
0x14000edb7  lea     r8, [rdi+112h]
0x14000edbe  lea     rdx, [rdi+12h]
0x14000edc2  xor     r9d, r9d
0x14000edc5  mov     rax, [rax+48h]
0x14000edc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000edce  mov     ebx, eax
0x14000edd0  lea     rax, WPP_GLOBAL_Control
0x14000edd7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000edde  cmp     rcx, rax
0x14000ede1  jz      short loc_14000EE07
0x14000ede3  cmp     byte ptr [rcx+19h], 4
0x14000ede7  jb      short loc_14000EE07
0x14000ede9  test    byte ptr [rcx+1Ch], 1
0x14000eded  jz      short loc_14000EE07
0x14000edef  mov     edx, 1Ah
0x14000edf4  mov     r9d, ebx
0x14000edf7  lea     r8, WPP_d7e0deef0d8c389735c42bf67fb2c31a_Traceguids
0x14000edfe  mov     rcx, [rcx+10h]
0x14000ee02  call    WPP_SF_d
0x14000ee07  test    ebx, ebx
0x14000ee09  js      short loc_14000EE0F
0x14000ee0b  xor     ebx, ebx
0x14000ee0d  jmp     short loc_14000EE20
0x14000ee0f  mov     eax, ebx
0x14000ee11  and     eax, 1FFF0000h
0x14000ee16  cmp     eax, 70000h
0x14000ee1b  jnz     short loc_14000EE20
0x14000ee1d  movzx   ebx, bx
0x14000ee20  mov     rcx, [rsp+38h+arg_10]
0x14000ee25  test    rcx, rcx
0x14000ee28  jz      short loc_14000EE37
0x14000ee2a  mov     rax, [rcx]
0x14000ee2d  mov     rax, [rax+10h]
0x14000ee31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee36  nop
0x14000ee37  mov     rcx, [rsp+38h+arg_8]
0x14000ee3c  test    rcx, rcx
0x14000ee3f  jz      short loc_14000EE4E
0x14000ee41  mov     rdx, [rcx]
0x14000ee44  mov     rax, [rdx+10h]
0x14000ee48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee4d  nop
0x14000ee4e  mov     eax, ebx
0x14000ee50  mov     rbx, [rsp+38h+arg_0]
0x14000ee55  add     rsp, 30h
0x14000ee59  pop     rdi
0x14000ee5a  retn
```
