# _lambda_4d192a1ee078ff4af3b07e632a08e019_::operator()

- ea: `0x180006af8`
- end: `0x18000726e`
- name: `_lambda_4d192a1ee078ff4af3b07e632a08e019_::operator()`
- size: `1910`
- prototype: `void __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, installer_update`

## callers

- `0x18000d2dc`

## callees

- `0x180004120`
- `0x180005308`
- `0x18000536c`
- `0x180005edc`
- `0x180006208`
- `0x180006608`
- `0x180006af8`
- `0x180007274`
- `0x1800072d8`
- `0x18000895c`
- `0x18000cab4`
- `0x18000cb40`
- `0x18000d1e8`
- `0x18000e90c`
- `0x18000ec70`
- `0x18000f4a0`
- `0x18000fd1c`
- `0x180010294`
- `0x18001044c`
- `0x1800108e4`
- `0x18001114c`
- `0x1800112c8`
- `0x1800113fc`
- `0x180011500`
- `0x1800117e8`
- `0x1800119b6`
- `0x1800119f0`

## import_xrefs

- `msvcrt!swscanf_s` at `0x1800070ff`
- `msvcrt!swscanf_s` at `0x1800070ff`

## string_xrefs

- `0x180007017`: `Configuration`

## pseudocode

```c
void __fastcall lambda_4d192a1ee078ff4af3b07e632a08e019_::operator()(__int64 **a1)
{
  __int64 v2; // rcx
  __int64 *v3; // r8
  NetSetup2::Property *lpVtbl; // rcx
  bool Boolean; // bl
  WCHAR *p_Buffer; // rcx
  bool v7; // r8
  void *v8; // r9
  const wchar_t *v9; // rdx
  struct Property v10; // rax
  char *Uint64; // rbx
  HKEY v12; // rdx
  int NumSubKeys; // r14d
  int v14; // esi
  __int64 v15; // rbx
  __int64 v16; // r15
  const WCHAR *v17; // r8
  const wchar_t *v18; // rcx
  unsigned int i; // edx
  const WCHAR *v20; // r8
  HKEY v21; // rdx
  _DWORD Buf2[7]; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE pExceptionObject[208]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v24[24]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v25[24]; // [rsp+158h] [rbp+58h] BYREF
  HKEY v26; // [rsp+170h] [rbp+70h] BYREF
  HKEY v27; // [rsp+178h] [rbp+78h] BYREF
  __int128 Buf1; // [rsp+180h] [rbp+80h] BYREF
  wchar_t *Buffer; // [rsp+190h] [rbp+90h] BYREF
  _QWORD *v30; // [rsp+198h] [rbp+98h] BYREF
  int v31; // [rsp+1A0h] [rbp+A0h]
  __int128 v32; // [rsp+1A4h] [rbp+A4h]
  __int64 v33; // [rsp+1B8h] [rbp+B8h] BYREF
  HKEY *v34; // [rsp+1C0h] [rbp+C0h] BYREF
  int v35; // [rsp+1C8h] [rbp+C8h]
  const WCHAR *v36; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD *v37; // [rsp+1D8h] [rbp+D8h] BYREF
  int v38; // [rsp+1E0h] [rbp+E0h]
  __int128 v39; // [rsp+1E4h] [rbp+E4h] BYREF
  _BYTE v40[8]; // [rsp+200h] [rbp+100h] BYREF
  _QWORD *v41[4]; // [rsp+208h] [rbp+108h] BYREF

  *(_QWORD *)&Buf2[5] = -2;
  v2 = **a1;
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_f1172f7f51b138cada6e87324e167680_Traceguids,
        "hNetSetup != nullptr");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  v3 = a1[1];
  if ( !*v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_f1172f7f51b138cada6e87324e167680_Traceguids,
        "ObjectId != nullptr");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  if ( *(_DWORD *)a1[2] != 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_f1172f7f51b138cada6e87324e167680_Traceguids,
        "ObjectType == NetSetupObjectTypeInterface");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  if ( !*a1[3] )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_f1172f7f51b138cada6e87324e167680_Traceguids,
        "hkey != nullptr");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  v33 = v2;
  NetSetup2::details::TransactionBase::GetNetworkInterfaceById(&v33, v40, *v3);
  *(_QWORD *)*a1[3] = 0;
  Buffer = (wchar_t *)&v33;
  v30 = 0;
  v31 = 9;
  v32 = 0;
  lpVtbl = (NetSetup2::Property *)NetSetup2::ActiveObject::GetProperty(
                                    (NetSetup2::ActiveObject *)&Buffer,
                                    (const struct _NETSETUPPROPKEY *)&v36,
                                    (unsigned int)NETSETUPPKEY_Transaction_IsOnline).lpVtbl;
  Boolean = NetSetup2::Property::GetBoolean(lpVtbl);
  std::vector<unsigned char>::_Tidy((__int64)&v39 + 4);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v30);
  if ( Boolean )
  {
    NetSetup2::NetworkInterface::tryget_PnpInstance(v40, &Buffer);
    if ( !BYTE12(v32) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_f1172f7f51b138cada6e87324e167680_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147020577);
      throw (HResultException *)pExceptionObject;
    }
    p_Buffer = (WCHAR *)&Buffer;
    if ( *(_QWORD *)((char *)&v32 + 4) >= 8u )
      p_Buffer = Buffer;
    if ( !NetSetupDevice::IsDeviceInstalled(p_Buffer) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = &Buffer;
        if ( *(_QWORD *)((char *)&v32 + 4) >= 8u )
          v8 = Buffer;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_f1172f7f51b138cada6e87324e167680_Traceguids, v8);
      }
      HResultException::HResultException((HResultException *)pExceptionObject, -2147020577);
      throw (HResultException *)pExceptionObject;
    }
    v9 = (const wchar_t *)&Buffer;
    if ( *(_QWORD *)((char *)&v32 + 4) >= 8u )
      v9 = Buffer;
    NetSetupDevice::NetSetupDevice((NetSetupDevice *)&Buf1, v9, v7);
    v36 = (const WCHAR *)&v33;
    v37 = 0;
    v38 = 9;
    v39 = 0;
    v10.lpVtbl = NetSetup2::ActiveObject::GetProperty(
                   (NetSetup2::ActiveObject *)&v36,
                   (const struct _NETSETUPPROPKEY *)v24,
                   (unsigned int)NETSETUPPKEY_Transaction_KtmHandle).lpVtbl;
    Uint64 = (char *)NetSetup2::Property::GetUint64((NetSetup2::Property *)v10.lpVtbl);
    std::vector<unsigned char>::_Tidy((__int64)v25);
    NetSetupDevice::OpenDeviceKey((NetSetupDevice *)&Buf1, (RegistryKey *)&v26, *(_DWORD *)a1[4], Uint64);
    std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v37);
    v12 = v26;
    v26 = 0;
    *(_QWORD *)*a1[3] = v12;
    RegistryKey::~RegistryKey(&v26);
    if ( BYTE12(v32) )
    {
      std::wstring::_Tidy((void **)&Buffer, 1, 0);
      BYTE12(v32) = 0;
    }
    goto LABEL_40;
  }
  GetNetClassKey((RegistryKey *)&v27);
  if ( !v27 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_f1172f7f51b138cada6e87324e167680_Traceguids);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147023728);
    throw (HResultException *)pExceptionObject;
  }
  NumSubKeys = RegistryKey::GetNumSubKeys(&v27);
  v34 = &v27;
  v14 = 0;
  v35 = 0;
  v15 = *(__int64 *)((char *)&v41[2] + 4);
  v16 = *(__int64 *)((char *)&v41[1] + 4);
  while ( 1 )
  {
    if ( v14 == NumSubKeys )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_f1172f7f51b138cada6e87324e167680_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147023728);
      throw (HResultException *)pExceptionObject;
    }
    RegistryKeyIterator::operator*((__int64)&v34, (__int64)&v36);
    if ( (unsigned __int8)std::operator!=<wchar_t>(&v36, L"Properties") )
    {
      if ( (unsigned __int8)std::operator!=<wchar_t>(&v36, L"Configuration") )
        break;
    }
LABEL_61:
    std::wstring::_Tidy((void **)&v36, 1, 0);
    v35 = ++v14;
  }
  v17 = (const WCHAR *)&v36;
  if ( *(_QWORD *)((char *)&v39 + 4) >= 8u )
    v17 = v36;
  RegistryKey::OpenSubKey(&v27, (HKEY)&v26, v17, 1u);
  if ( !RegistryKey::ValueExists(&v26, L"NetCfgInstanceId") )
  {
LABEL_60:
    RegistryKey::~RegistryKey(&v26);
    goto LABEL_61;
  }
  RegistryKey::GetValueString(&v26, (__int64)&Buffer, L"NetCfgInstanceId");
  Buf1 = 0;
  v18 = (const wchar_t *)&Buffer;
  if ( *(_QWORD *)((char *)&v32 + 4) >= 8u )
    v18 = Buffer;
  if ( swscanf_s(
         v18,
         L"{%x-%hx-%hx-%4hx-%4hx%4hx%4hx}",
         &Buf1,
         (char *)&Buf1 + 4,
         (char *)&Buf1 + 6,
         (char *)&Buf1 + 8,
         (char *)&Buf1 + 10,
         (char *)&Buf1 + 12,
         (char *)&Buf1 + 14) != 7 )
    goto LABEL_59;
  for ( i = 0; i < 8; i += 2 )
    *(_WORD *)((char *)&Buf1 + (int)i + 8) = __ROR2__(*(_WORD *)((char *)&Buf1 + (int)i + 8), 8);
  *(_QWORD *)Buf2 = v16;
  *(_QWORD *)&Buf2[2] = v15;
  if ( memcmp_0(&Buf1, Buf2, 0x10u) )
  {
LABEL_59:
    std::wstring::_Tidy((void **)&Buffer, 1, 0);
    goto LABEL_60;
  }
  v20 = (const WCHAR *)&v36;
  if ( *(_QWORD *)((char *)&v39 + 4) >= 8u )
    v20 = v36;
  RegistryKey::OpenSubKey(&v27, (HKEY)&v34, v20, *(_DWORD *)a1[4]);
  v21 = (HKEY)v34;
  v34 = 0;
  *(_QWORD *)*a1[3] = v21;
  RegistryKey::~RegistryKey((HKEY *)&v34);
  std::wstring::_Tidy((void **)&Buffer, 1, 0);
  RegistryKey::~RegistryKey(&v26);
  std::wstring::_Tidy((void **)&v36, 1, 0);
  RegistryKey::~RegistryKey(&v27);
LABEL_40:
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v41);
}

```

## disassembly

```asm
0x180006af8  push    rbp
0x180006afa  push    rbx
0x180006afb  push    rsi
0x180006afc  push    rdi
0x180006afd  push    r12
0x180006aff  push    r13
0x180006b01  push    r14
0x180006b03  push    r15
0x180006b05  lea     rbp, [rsp-138h]
0x180006b0d  sub     rsp, 238h
0x180006b14  mov     [rsp+270h+var_208], 0FFFFFFFFFFFFFFFEh
0x180006b1d  mov     rax, cs:__security_cookie
0x180006b24  xor     rax, rsp
0x180006b27  mov     [rbp+170h+var_48], rax
0x180006b2e  mov     rdi, rcx
0x180006b31  xor     r13d, r13d
0x180006b34  mov     rax, [rcx]
0x180006b37  mov     rcx, [rax]
0x180006b3a  test    rcx, rcx
0x180006b3d  jnz     short loc_180006B94
0x180006b3f  lea     rax, WPP_GLOBAL_Control
0x180006b46  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b4d  cmp     rcx, rax
0x180006b50  jz      short loc_180006B73
0x180006b52  cmp     byte ptr [rcx+19h], 2
0x180006b56  jb      short loc_180006B73
0x180006b58  lea     edx, [r13+1Bh]
0x180006b5c  lea     r9, aHnetsetupNullp; "hNetSetup != nullptr"
0x180006b63  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x180006b6a  mov     rcx, [rcx+10h]
0x180006b6e  call    WPP_SF_s
0x180006b73  mov     edx, 80070057h; int
0x180006b78  lea     rcx, [rsp+270h+pExceptionObject]; this
0x180006b7d  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180006b82  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180006b89  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x180006b8e  call    _CxxThrowException_0
0x180006b94  mov     r8, [rdi+8]
0x180006b98  cmp     [r8], r13
0x180006b9b  jnz     short loc_180006BF3
0x180006b9d  lea     rax, WPP_GLOBAL_Control
0x180006ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bab  cmp     rcx, rax
0x180006bae  jz      short loc_180006BD2
0x180006bb0  cmp     byte ptr [rcx+19h], 2
0x180006bb4  jb      short loc_180006BD2
0x180006bb6  mov     edx, 1Ch
0x180006bbb  lea     r9, aObjectidNullpt; "ObjectId != nullptr"
0x180006bc2  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x180006bc9  mov     rcx, [rcx+10h]
0x180006bcd  call    WPP_SF_s
0x180006bd2  mov     edx, 80070057h; int
0x180006bd7  lea     rcx, [rsp+270h+pExceptionObject]; this
0x180006bdc  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180006be1  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180006be8  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x180006bed  call    _CxxThrowException_0
0x180006bf3  mov     rax, [rdi+10h]
0x180006bf7  cmp     dword ptr [rax], 2
0x180006bfa  jz      short loc_180006C52
0x180006bfc  lea     rax, WPP_GLOBAL_Control
0x180006c03  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c0a  cmp     rcx, rax
0x180006c0d  jz      short loc_180006C31
0x180006c0f  cmp     byte ptr [rcx+19h], 2
0x180006c13  jb      short loc_180006C31
0x180006c15  mov     edx, 1Dh
0x180006c1a  lea     r9, aObjecttypeNets; "ObjectType == NetSetupObjectTypeInterfa"...
0x180006c21  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x180006c28  mov     rcx, [rcx+10h]
0x180006c2c  call    WPP_SF_s
0x180006c31  mov     edx, 80070057h; int
0x180006c36  lea     rcx, [rsp+270h+pExceptionObject]; this
0x180006c3b  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180006c40  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180006c47  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x180006c4c  call    _CxxThrowException_0
0x180006c52  mov     rax, [rdi+18h]
0x180006c56  cmp     [rax], r13
0x180006c59  jnz     short loc_180006CB1
0x180006c5b  lea     rax, WPP_GLOBAL_Control
0x180006c62  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c69  cmp     rcx, rax
0x180006c6c  jz      short loc_180006C90
0x180006c6e  cmp     byte ptr [rcx+19h], 2
0x180006c72  jb      short loc_180006C90
0x180006c74  mov     edx, 1Eh
0x180006c79  lea     r9, aHkeyNullptr; "hkey != nullptr"
0x180006c80  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x180006c87  mov     rcx, [rcx+10h]
0x180006c8b  call    WPP_SF_s
0x180006c90  mov     edx, 80070057h; int
0x180006c95  lea     rcx, [rsp+270h+pExceptionObject]; this
0x180006c9a  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180006c9f  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180006ca6  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x180006cab  call    _CxxThrowException_0
0x180006cb1  mov     [rbp+170h+var_B8], rcx
0x180006cb8  mov     r8, [r8]
0x180006cbb  lea     rdx, [rbp+170h+var_70]
0x180006cc2  lea     rcx, [rbp+170h+var_B8]
0x180006cc9  call    ?GetNetworkInterfaceById@TransactionBase@details@NetSetup2@@QEAA?AVNetworkInterface@3@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::GetNetworkInterfaceById(_GUID const &)
0x180006cce  nop
0x180006ccf  mov     rax, [rdi+18h]
0x180006cd3  mov     rcx, [rax]
0x180006cd6  mov     [rcx], r13
0x180006cd9  xorps   xmm0, xmm0
0x180006cdc  lea     rax, [rbp+170h+var_B8]
0x180006ce3  mov     [rbp+170h+Buffer], rax
0x180006cea  mov     [rbp+170h+var_D8], r13
0x180006cf1  mov     esi, 9
0x180006cf6  mov     [rbp+170h+var_D0], esi
0x180006cfc  movdqu  [rbp+170h+var_CC], xmm0
0x180006d04  lea     r8, NETSETUPPKEY_Transaction_IsOnline
0x180006d0b  lea     rdx, [rbp+170h+var_A0]; struct _NETSETUPPROPKEY *
0x180006d12  lea     rcx, [rbp+170h+Buffer]; this
0x180006d19  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x180006d1e  nop
0x180006d1f  mov     rcx, rax; this
0x180006d22  call    ?GetBoolean@Property@NetSetup2@@QEBA_NXZ; NetSetup2::Property::GetBoolean(void)
0x180006d27  mov     bl, al
0x180006d29  lea     rcx, [rbp+170h+var_88]
0x180006d30  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180006d35  nop
0x180006d36  lea     rcx, [rbp+170h+var_D8]
0x180006d3d  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180006d42  test    bl, bl
0x180006d44  jz      loc_180006F43
0x180006d4a  lea     rdx, [rbp+170h+Buffer]
0x180006d51  lea     rcx, [rbp+170h+var_70]
0x180006d58  call    ?tryget_PnpInstance@NetworkInterface@NetSetup2@@QEBA?AV?$Optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@details@2@XZ; NetSetup2::NetworkInterface::tryget_PnpInstance(void)
0x180006d5d  nop
0x180006d5e  cmp     byte ptr [rbp+170h+var_CC+0Ch], r13b
0x180006d65  jnz     short loc_180006DB4
0x180006d67  lea     rax, WPP_GLOBAL_Control
0x180006d6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d75  cmp     rcx, rax
0x180006d78  jz      short loc_180006D93
0x180006d7a  cmp     byte ptr [rcx+19h], 2
0x180006d7e  jb      short loc_180006D93
0x180006d80  lea     edx, [rsi+16h]
0x180006d83  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x180006d8a  mov     rcx, [rcx+10h]
0x180006d8e  call    WPP_SF_
0x180006d93  mov     edx, 800710DFh; int
0x180006d98  lea     rcx, [rsp+270h+pExceptionObject]; this
0x180006d9d  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180006da2  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180006da9  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x180006dae  call    _CxxThrowException_0
0x180006db4  lea     rcx, [rbp+170h+Buffer]
0x180006dbb  cmp     qword ptr [rbp+170h+var_CC+4], 8
0x180006dc3  cmovnb  rcx, [rbp+170h+Buffer]; pDeviceID
0x180006dcb  call    ?IsDeviceInstalled@NetSetupDevice@@SA_NPEB_W@Z; NetSetupDevice::IsDeviceInstalled(wchar_t const *)
0x180006dd0  test    al, al
0x180006dd2  jnz     short loc_180006E3A
0x180006dd4  lea     rax, WPP_GLOBAL_Control
0x180006ddb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006de2  cmp     rcx, rax
0x180006de5  jz      short loc_180006E19
0x180006de7  cmp     byte ptr [rcx+19h], 2
0x180006deb  jb      short loc_180006E19
0x180006ded  lea     r9, [rbp+170h+Buffer]
0x180006df4  cmp     qword ptr [rbp+170h+var_CC+4], 8
0x180006dfc  cmovnb  r9, [rbp+170h+Buffer]
0x180006e04  mov     edx, 20h ; ' '
0x180006e09  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x180006e10  mov     rcx, [rcx+10h]
0x180006e14  call    WPP_SF_S
0x180006e19  mov     edx, 800710DFh; int
0x180006e1e  lea     rcx, [rsp+270h+pExceptionObject]; this
0x180006e23  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180006e28  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180006e2f  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x180006e34  call    _CxxThrowException_0
0x180006e3a  lea     rdx, [rbp+170h+Buffer]
0x180006e41  cmp     qword ptr [rbp+170h+var_CC+4], 8
0x180006e49  cmovnb  rdx, [rbp+170h+Buffer]; wchar_t *
0x180006e51  lea     rcx, [rbp+170h+Buf1]; this
0x180006e58  call    ??0NetSetupDevice@@QEAA@PEB_W_N@Z; NetSetupDevice::NetSetupDevice(wchar_t const *,bool)
0x180006e5d  xorps   xmm0, xmm0
0x180006e60  lea     rax, [rbp+170h+var_B8]
0x180006e67  mov     [rbp+170h+var_A0], rax
0x180006e6e  mov     [rbp+170h+var_98], r13
0x180006e75  mov     [rbp+170h+var_90], esi
0x180006e7b  movdqu  xmmword ptr [rbp+0E4h], xmm0
0x180006e83  lea     r8, NETSETUPPKEY_Transaction_KtmHandle
0x180006e8a  lea     rdx, [rbp+170h+var_130]; struct _NETSETUPPROPKEY *
0x180006e8e  lea     rcx, [rbp+170h+var_A0]; this
0x180006e95  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x180006e9a  nop
0x180006e9b  mov     rcx, rax; this
0x180006e9e  call    ?GetUint64@Property@NetSetup2@@QEBA_KXZ; NetSetup2::Property::GetUint64(void)
0x180006ea3  mov     rbx, rax
0x180006ea6  lea     rcx, [rbp+170h+var_118]
0x180006eaa  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180006eaf  mov     r8, [rdi+20h]
0x180006eb3  mov     r9, rbx
0x180006eb6  mov     r8d, [r8]
0x180006eb9  lea     rdx, [rbp+170h+var_100]
0x180006ebd  lea     rcx, [rbp+170h+Buf1]
0x180006ec4  call    ?OpenDeviceKey@NetSetupDevice@@AEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@KK@Z; NetSetupDevice::OpenDeviceKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy,ulong,ulong)
0x180006ec9  nop
0x180006eca  lea     rcx, [rbp+170h+var_98]
0x180006ed1  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180006ed6  mov     rdx, [rbp+170h+var_100]
0x180006eda  mov     [rbp+170h+var_100], r13
0x180006ede  mov     rax, [rdi+18h]
0x180006ee2  mov     rcx, [rax]
0x180006ee5  mov     [rcx], rdx
0x180006ee8  lea     rcx, [rbp+170h+var_100]; this
0x180006eec  call    ??1RegistryKey@@QEAA@XZ; RegistryKey::~RegistryKey(void)
0x180006ef1  nop
0x180006ef2  cmp     byte ptr [rbp+170h+var_CC+0Ch], r13b
0x180006ef9  jz      short loc_180006F13
0x180006efb  xor     r8d, r8d
0x180006efe  mov     dl, 1
0x180006f00  lea     rcx, [rbp+170h+Buffer]
0x180006f07  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180006f0c  mov     byte ptr [rbp+170h+var_CC+0Ch], r13b
0x180006f13  lea     rcx, [rbp+170h+var_68]
0x180006f1a  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180006f1f  nop
0x180006f20  mov     rcx, [rbp+170h+var_48]
0x180006f27  xor     rcx, rsp; StackCookie
0x180006f2a  call    __security_check_cookie
0x180006f2f  add     rsp, 238h
0x180006f36  pop     r15
0x180006f38  pop     r14
0x180006f3a  pop     r13
0x180006f3c  pop     r12
0x180006f3e  pop     rdi
0x180006f3f  pop     rsi
0x180006f40  pop     rbx
0x180006f41  pop     rbp
0x180006f42  retn
0x180006f43  lea     rdx, [rbp+170h+var_B8]
0x180006f4a  lea     rcx, [rbp+170h+var_F8]; this
0x180006f4e  call    GetNetClassKey
0x180006f53  nop
0x180006f54  cmp     [rbp+170h+var_F8], r13
0x180006f58  jnz     short loc_180006FA9
0x180006f5a  lea     rax, WPP_GLOBAL_Control
0x180006f61  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f68  cmp     rcx, rax
0x180006f6b  jz      short loc_180006F88
0x180006f6d  cmp     byte ptr [rcx+19h], 2
0x180006f71  jb      short loc_180006F88
0x180006f73  mov     edx, 21h ; '!'
0x180006f78  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x180006f7f  mov     rcx, [rcx+10h]
0x180006f83  call    WPP_SF_
0x180006f88  mov     edx, 80070490h; int
0x180006f8d  lea     rcx, [rsp+270h+pExceptionObject]; this
0x180006f92  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180006f97  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180006f9e  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x180006fa3  call    _CxxThrowException_0
0x180006fa9  lea     rcx, [rbp+170h+var_F8]; this
0x180006fad  call    ?GetNumSubKeys@RegistryKey@@QEBAKXZ; RegistryKey::GetNumSubKeys(void)
0x180006fb2  mov     r14d, eax
0x180006fb5  lea     rax, [rbp+170h+var_F8]
0x180006fb9  mov     [rbp+170h+var_B0], rax
0x180006fc0  mov     esi, r13d
0x180006fc3  mov     [rbp+170h+var_A8], r13d
0x180006fca  mov     rbx, [rbp+170h+var_54]
0x180006fd1  mov     r15, [rbp+170h+var_5C]
0x180006fd8  mov     r12d, [rbp+170h+var_60]
0x180006fdf  cmp     esi, r14d
0x180006fe2  jz      loc_18000721F
0x180006fe8  lea     rdx, [rbp+170h+var_A0]
0x180006fef  lea     rcx, [rbp+170h+var_B0]
0x180006ff6  call    ??DRegistryKeyIterator@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RegistryKeyIterator::operator*(void)
0x180006ffb  nop
0x180006ffc  lea     rdx, aProperties; "Properties"
0x180007003  lea     rcx, [rbp+170h+var_A0]
0x18000700a  call    ??$?9_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@PEB_W@Z; std::operator!=<wchar_t>(std::wstring const &,wchar_t const *)
0x18000700f  test    al, al
0x180007011  jz      loc_180007172
0x180007017  lea     rdx, aConfiguration; "Configuration"
0x18000701e  lea     rcx, [rbp+170h+var_A0]
0x180007025  call    ??$?9_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@PEB_W@Z; std::operator!=<wchar_t>(std::wstring const &,wchar_t const *)
0x18000702a  test    al, al
0x18000702c  jz      loc_180007172
0x180007032  lea     r8, [rbp+170h+var_A0]
0x180007039  cmp     [rbp+170h+var_88], 8
0x180007041  cmovnb  r8, [rbp+170h+var_A0]
0x180007049  mov     r9d, 1
0x18000704f  lea     rdx, [rbp+170h+var_100]
0x180007053  lea     rcx, [rbp+170h+var_F8]
0x180007057  call    ?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)
0x18000705c  nop
0x18000705d  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x180007064  lea     rcx, [rbp+170h+var_100]; this
0x180007068  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18000706d  test    al, al
0x18000706f  jz      loc_180007168
0x180007075  lea     r8, aNetcfginstance; "NetCfgInstanceId"
0x18000707c  lea     rdx, [rbp+170h+Buffer]
0x180007083  lea     rcx, [rbp+170h+var_100]
  ... truncated ...
```
