# CommonUtil::MpCoDontHandleExceptions(void)

- ea: `0x180008bd4`
- end: `0x180008d62`
- name: `?MpCoDontHandleExceptions@CommonUtil@@YAJXZ`
- size: `398`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002490`

## callees

- `0x180004b7c`
- `0x180008bd4`
- `0x180008d68`
- `0x180008e4c`
- `0x180009440`
- `0x18000a010`

## import_xrefs

- `ole32!CoUninitialize` at `0x180008c25`
- `ole32!CoUninitialize` at `0x180008ce1`
- `ole32!CoUninitialize` at `0x180008d45`
- `ole32!CoUninitialize` at `0x180008c25`
- `ole32!CoUninitialize` at `0x180008ce1`
- `ole32!CoUninitialize` at `0x180008d45`
- `ole32!CoCreateInstance` at `0x180008c66`
- `ole32!CoCreateInstance` at `0x180008c66`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpCoDontHandleExceptions(
        CommonUtil *this,
        struct CommonUtil::MpCoLibraryType **a2,
        void *a3,
        unsigned int a4)
{
  int v4; // eax
  int v5; // ebx
  HRESULT v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // edi
  _BYTE *v11; // rcx
  __int64 v12; // rdx
  LPVOID ppv; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+38h] [rbp-30h] BYREF
  IID rclsid; // [rsp+40h] [rbp-28h] BYREF

  if ( byte_18001381C )
    return 0;
  byte_18001381C = 1;
  v14 = 0;
  v4 = CommonUtil::MpSmartCoInitialize((CommonUtil *)&v14, a2, a3, a4);
  v5 = 0;
  if ( v4 != -2147417850 )
    v5 = v4;
  if ( v5 < 0 )
  {
    if ( v14 )
      CoUninitialize();
    return (unsigned int)v5;
  }
  *(_QWORD *)&rclsid.Data1 = 843;
  *(_DWORD *)rclsid.Data4 = 192;
  *(_DWORD *)&rclsid.Data4[4] = 1174405120;
  ppv = 0;
  v7 = CoCreateInstance(&rclsid, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  v10 = v7;
  if ( v7 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_16;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, &rclsid, v7);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || (v11[28] & 1) == 0 )
      goto LABEL_16;
    v12 = 10;
    goto LABEL_15;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 2);
  if ( v10 >= 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v14 )
      CoUninitialize();
    return 0;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_16;
  v12 = 11;
LABEL_15:
  WPP_SF_d(*((_QWORD *)v11 + 2), v12, &WPP_1c756af73aa03d742fb0eb712210c2f8_Traceguids, (unsigned int)v10);
LABEL_16:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v14 )
    CoUninitialize();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180008bd4  push    rbp
0x180008bd6  push    rbx
0x180008bd7  push    rsi
0x180008bd8  push    rdi
0x180008bd9  mov     rbp, rsp
0x180008bdc  sub     rsp, 68h
0x180008be0  mov     rax, cs:__security_cookie
0x180008be7  xor     rax, rsp
0x180008bea  mov     [rbp+var_18], rax
0x180008bee  xor     esi, esi
0x180008bf0  cmp     cs:byte_18001381C, sil
0x180008bf7  jnz     loc_180008D4B
0x180008bfd  lea     rcx, [rbp+var_30]; this
0x180008c01  mov     cs:byte_18001381C, 1
0x180008c08  mov     [rbp+var_30], rsi
0x180008c0c  call    ?MpSmartCoInitialize@CommonUtil@@YAJPEAPEAUMpCoLibraryType@1@PEAXK@Z; CommonUtil::MpSmartCoInitialize(CommonUtil::MpCoLibraryType * *,void *,ulong)
0x180008c11  cmp     eax, 80010106h
0x180008c16  mov     ebx, esi
0x180008c18  cmovnz  ebx, eax
0x180008c1b  test    ebx, ebx
0x180008c1d  jns     short loc_180008C32
0x180008c1f  cmp     [rbp+var_30], rsi
0x180008c23  jz      short loc_180008C2B
0x180008c25  call    cs:__imp_CoUninitialize
0x180008c2b  mov     eax, ebx
0x180008c2d  jmp     loc_180008D4D
0x180008c32  xor     edx, edx; pUnkOuter
0x180008c34  mov     qword ptr [rbp+rclsid.Data1], 34Bh
0x180008c3c  lea     rax, [rbp+var_38]
0x180008c40  mov     dword ptr [rbp+rclsid.Data4], 0C0h
0x180008c47  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180008c4e  mov     dword ptr [rbp+rclsid.Data4+4], 46000000h
0x180008c55  lea     rcx, [rbp+rclsid]; rclsid
0x180008c59  mov     [rbp+var_38], rsi
0x180008c5d  lea     r8d, [rdx+1]; dwClsContext
0x180008c61  mov     [rsp+68h+ppv], rax; ppv
0x180008c66  call    cs:__imp_CoCreateInstance
0x180008c6c  mov     edi, eax
0x180008c6e  test    eax, eax
0x180008c70  jns     short loc_180008CEB
0x180008c72  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c79  lea     rbx, WPP_GLOBAL_Control
0x180008c80  cmp     rcx, rbx
0x180008c83  jz      short loc_180008CC6
0x180008c85  test    byte ptr [rcx+1Ch], 1
0x180008c89  jz      short loc_180008CA3
0x180008c8b  mov     rcx, [rcx+10h]
0x180008c8f  lea     r9, [rbp+rclsid]
0x180008c93  mov     dword ptr [rsp+68h+ppv], eax
0x180008c97  call    WPP_SF__guid_d
0x180008c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ca3  cmp     rcx, rbx
0x180008ca6  jz      short loc_180008CC6
0x180008ca8  test    byte ptr [rcx+1Ch], 1
0x180008cac  jz      short loc_180008CC6
0x180008cae  mov     edx, 0Ah
0x180008cb3  mov     rcx, [rcx+10h]
0x180008cb7  lea     r8, WPP_1c756af73aa03d742fb0eb712210c2f8_Traceguids
0x180008cbe  mov     r9d, edi
0x180008cc1  call    WPP_SF_d
0x180008cc6  mov     rcx, [rbp+var_38]
0x180008cca  test    rcx, rcx
0x180008ccd  jz      short loc_180008CDB
0x180008ccf  mov     rax, [rcx]
0x180008cd2  mov     rax, [rax+10h]
0x180008cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cdb  cmp     [rbp+var_30], rsi
0x180008cdf  jz      short loc_180008CE7
0x180008ce1  call    cs:__imp_CoUninitialize
0x180008ce7  mov     eax, edi
0x180008ce9  jmp     short loc_180008D4D
0x180008ceb  mov     rcx, [rbp+var_38]
0x180008cef  mov     edx, 1
0x180008cf4  mov     rax, [rcx]
0x180008cf7  lea     r8d, [rdx+1]
0x180008cfb  mov     rax, [rax+18h]
0x180008cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d04  mov     edi, eax
0x180008d06  test    eax, eax
0x180008d08  jns     short loc_180008D2A
0x180008d0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d11  lea     rbx, WPP_GLOBAL_Control
0x180008d18  cmp     rcx, rbx
0x180008d1b  jz      short loc_180008CC6
0x180008d1d  test    byte ptr [rcx+1Ch], 1
0x180008d21  jz      short loc_180008CC6
0x180008d23  mov     edx, 0Bh
0x180008d28  jmp     short loc_180008CB3
0x180008d2a  mov     rcx, [rbp+var_38]
0x180008d2e  test    rcx, rcx
0x180008d31  jz      short loc_180008D3F
0x180008d33  mov     rax, [rcx]
0x180008d36  mov     rax, [rax+10h]
0x180008d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d3f  cmp     [rbp+var_30], rsi
0x180008d43  jz      short loc_180008D4B
0x180008d45  call    cs:__imp_CoUninitialize
0x180008d4b  xor     eax, eax
0x180008d4d  mov     rcx, [rbp+var_18]
0x180008d51  xor     rcx, rsp; StackCookie
0x180008d54  call    __security_check_cookie
0x180008d59  add     rsp, 68h
0x180008d5d  pop     rdi
0x180008d5e  pop     rsi
0x180008d5f  pop     rbx
0x180008d60  pop     rbp
0x180008d61  retn
```
