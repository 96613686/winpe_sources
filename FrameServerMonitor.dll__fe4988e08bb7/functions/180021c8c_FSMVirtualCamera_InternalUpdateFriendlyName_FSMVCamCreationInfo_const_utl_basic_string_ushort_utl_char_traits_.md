# FSMVirtualCamera::InternalUpdateFriendlyName(FSMVCamCreationInfo const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180021c8c`
- end: `0x18002210a`
- name: `?InternalUpdateFriendlyName@FSMVirtualCamera@@IEAAJAEBUFSMVCamCreationInfo@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1150`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callers

- `0x18001fb2c`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000723c`
- `0x18000d060`
- `0x18000d1e0`
- `0x18000d3d8`
- `0x18000d418`
- `0x18000d498`
- `0x18000e25c`
- `0x180021c8c`
- `0x18002544c`
- `0x180025474`
- `0x180025614`
- `0x180040914`
- `0x180040b74`

## import_xrefs

- `ntdll!wcsstr` at `0x180021f3f`
- `ntdll!wcsstr` at `0x180021f3f`

## pseudocode

```c
__int64 __fastcall FSMVirtualCamera::InternalUpdateFriendlyName(__int64 a1, __int64 a2, __int64 *a3)
{
  const char **v6; // rbx
  const char *v7; // rax
  signed int v8; // edi
  char v9; // di
  int v10; // ecx
  unsigned int v11; // r12d
  const struct std::nothrow_t *unique; // rax
  const struct std::nothrow_t *v13; // rdx
  wchar_t *v14; // rbx
  const struct std::nothrow_t *v15; // rdx
  int v16; // ecx
  __int64 v17; // rdx
  const WCHAR *v18; // rcx
  ULONG v19; // r9d
  __int64 v20; // rdx
  wchar_t *v21; // rax
  __int64 v22; // rdx
  const struct std::nothrow_t *v23; // rdx
  unsigned __int8 Level; // al
  void *v26[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v27; // [rsp+80h] [rbp+40h] BYREF
  wchar_t *SubStr; // [rsp+98h] [rbp+58h] BYREF

  v27 = 0;
  v6 = (const char **)(a1 + 632);
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v7 = L"<nullptr>";
    if ( *v6 )
      v7 = *v6;
    WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 27), *(_QWORD *)(a2 + 24), (__int64)v7);
  }
  if ( !*v6 )
  {
    v8 = -1072875850;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        226,
        &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
        a1,
        -1072875850);
    goto LABEL_53;
  }
  v9 = 1;
  if ( FSGetDeviceInterfaceProperty(
         *(LPCWSTR *)(a2 + 24),
         (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FriendlyName,
         0,
         0,
         &v27) >= 0 )
    goto LABEL_21;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      227,
      &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      *(_QWORD *)(a2 + 24));
  v9 = 0;
  if ( (int)FSGetDeviceNodeProperty(*(LPCWSTR *)(a2 + 24), (DEVPROPKEY *)&DEVPKEY_Device_FriendlyName, 0, 0, &v27) >= 0 )
  {
LABEL_21:
    v11 = (v27 >> 1) + 2;
    SubStr = 0;
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(v26, v11);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&SubStr, unique);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(v26, v13);
    v14 = SubStr;
    if ( !SubStr )
    {
      v8 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v17 = 229;
LABEL_51:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, a1, v16);
        goto LABEL_52;
      }
      goto LABEL_52;
    }
    v18 = *(const WCHAR **)(a2 + 24);
    v19 = 2 * v11;
    if ( v9 )
    {
      v8 = FSGetDeviceInterfaceProperty(
             v18,
             (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FriendlyName,
             (PBYTE)SubStr,
             v19,
             &v27);
      if ( v8 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_52;
        v20 = 230;
LABEL_28:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, a1, v8);
        goto LABEL_52;
      }
    }
    else
    {
      v8 = FSGetDeviceNodeProperty(v18, (DEVPROPKEY *)&DEVPKEY_Device_FriendlyName, (PBYTE)SubStr, v19, &v27);
      if ( v8 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_52;
        v20 = 231;
        goto LABEL_28;
      }
    }
    v21 = wcsstr(*(const wchar_t **)(a2 + 16), v14);
    v22 = *(_QWORD *)(a2 + 16);
    if ( v21 )
    {
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               a3,
                               v22)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               a3,
                               L" (",
                               2)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               a3,
                               *(_QWORD *)(a1 + 632))
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               a3,
                               L")",
                               1) )
      {
        v8 = -2147024882;
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v17 = 232;
          goto LABEL_51;
        }
LABEL_52:
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&SubStr, v15);
        goto LABEL_53;
      }
    }
    else if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                  a3,
                                  v22)
           || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  a3,
                                  L" (",
                                  2)
           || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  a3,
                                  *(_QWORD *)(a1 + 632))
           || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  a3,
                                  L" - ",
                                  3)
           || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  a3,
                                  v14)
           || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  a3,
                                  L")",
                                  1) )
    {
      v8 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v17 = 233;
        goto LABEL_51;
      }
      goto LABEL_52;
    }
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&SubStr, v23);
    goto LABEL_46;
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      228,
      &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      *(_QWORD *)(a2 + 24));
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           a3,
                           *(_QWORD *)(a2 + 16))
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           a3,
                           L" (",
                           2)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           a3,
                           *(_QWORD *)(a1 + 632))
    || (v8 = 0,
        !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                            a3,
                            L")",
                            1)) )
  {
    v8 = -2147024882;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, a1, v10);
LABEL_53:
      Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
LABEL_54:
      if ( Level )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          235,
          &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          (unsigned int)v8);
      return (unsigned int)v8;
    }
  }
LABEL_46:
  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  if ( v8 < 0 )
    goto LABEL_54;
  if ( Level >= 8u )
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      236,
      (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      v8,
      *a3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021c8c  mov     [rsp-38h+arg_8], rbx
0x180021c91  push    rbp
0x180021c92  push    rsi
0x180021c93  push    rdi
0x180021c94  push    r12
0x180021c96  push    r13
0x180021c98  push    r14
0x180021c9a  push    r15
0x180021c9c  mov     rbp, rsp
0x180021c9f  sub     rsp, 40h
0x180021ca3  mov     rsi, r8
0x180021ca6  mov     [rbp+arg_0], 0
0x180021cad  mov     r13, rdx
0x180021cb0  mov     r15, rcx
0x180021cb3  lea     rbx, [rcx+278h]
0x180021cba  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180021cbf  lea     r12, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180021cc6  cmp     al, 8
0x180021cc8  jb      short loc_180021D06
0x180021cca  cmp     qword ptr [rbx], 0
0x180021cce  lea     rax, aNullptr; "<nullptr>"
0x180021cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cdc  mov     edx, 0E1h
0x180021ce1  cmovnz  rax, [rbx]
0x180021ce5  mov     r8, r12
0x180021ce8  mov     r9, [r13+10h]
0x180021cec  mov     [rsp+40h+var_18], rax; __int64
0x180021cf1  mov     rax, [r13+18h]
0x180021cf5  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180021cfc  mov     [rsp+40h+var_20], rax; __int64
0x180021d01  call    WPP_SF_SSS
0x180021d06  cmp     qword ptr [rbx], 0
0x180021d0a  jnz     short loc_180021D49
0x180021d0c  mov     edi, 0C00D36B6h
0x180021d11  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021d16  mov     r14d, 1
0x180021d1c  cmp     al, r14b
0x180021d1f  jb      loc_1800220C4
0x180021d25  mov     edx, 0E2h
0x180021d2a  mov     dword ptr [rsp+40h+var_20], edi
0x180021d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d35  mov     r9, r15
0x180021d38  mov     r8, r12
0x180021d3b  mov     rcx, [rcx+10h]
0x180021d3f  call    WPP_SF_qD
0x180021d44  jmp     loc_1800220C4
0x180021d49  mov     rcx, [r13+18h]; pszDeviceInterface
0x180021d4d  lea     rax, [rbp+arg_0]
0x180021d51  mov     r14d, 1
0x180021d57  mov     [rsp+40h+var_20], rax; unsigned int *
0x180021d5c  xor     r9d, r9d; unsigned int
0x180021d5f  lea     rdx, DEVPKEY_DeviceInterface_FriendlyName; PropertyKey
0x180021d66  xor     r8d, r8d; PropertyBuffer
0x180021d69  mov     dil, r14b
0x180021d6c  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180021d71  test    eax, eax
0x180021d73  jns     loc_180021E6E
0x180021d79  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180021d7e  cmp     al, 8
0x180021d80  jb      short loc_180021DA1
0x180021d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d89  mov     edx, 0E3h
0x180021d8e  mov     r9, [r13+18h]
0x180021d92  mov     r8, r12
0x180021d95  mov     rcx, [rcx+0D8h]
0x180021d9c  call    WPP_SF_S
0x180021da1  mov     rcx, [r13+18h]; pszDeviceInterface
0x180021da5  lea     rax, [rbp+arg_0]
0x180021da9  xor     r9d, r9d; unsigned int
0x180021dac  mov     [rsp+40h+var_20], rax; unsigned int *
0x180021db1  xor     r8d, r8d; PropertyBuffer
0x180021db4  lea     rdx, DEVPKEY_Device_FriendlyName; PropertyKey
0x180021dbb  xor     dil, dil
0x180021dbe  call    ?FSGetDeviceNodeProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceNodeProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180021dc3  test    eax, eax
0x180021dc5  jns     loc_180021E6E
0x180021dcb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180021dd0  cmp     al, 8
0x180021dd2  jb      short loc_180021DF3
0x180021dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ddb  mov     edx, 0E4h
0x180021de0  mov     r9, [r13+18h]
0x180021de4  mov     r8, r12
0x180021de7  mov     rcx, [rcx+0D8h]
0x180021dee  call    WPP_SF_S
0x180021df3  mov     rdx, [r13+10h]
0x180021df7  mov     rcx, rsi
0x180021dfa  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180021dff  test    al, al
0x180021e01  jz      short loc_180021E4B
0x180021e03  mov     r8d, 2
0x180021e09  lea     rdx, asc_180053A84; " ("
0x180021e10  mov     rcx, rsi
0x180021e13  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180021e18  test    al, al
0x180021e1a  jz      short loc_180021E4B
0x180021e1c  mov     rdx, [r15+278h]
0x180021e23  mov     rcx, rsi
0x180021e26  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180021e2b  test    al, al
0x180021e2d  jz      short loc_180021E4B
0x180021e2f  mov     r8, r14
0x180021e32  lea     rdx, asc_180052ABC; ")"
0x180021e39  mov     rcx, rsi
0x180021e3c  xor     edi, edi
0x180021e3e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180021e43  test    al, al
0x180021e45  jnz     loc_18002204E
0x180021e4b  mov     ecx, 8007000Eh
0x180021e50  mov     edi, ecx
0x180021e52  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021e57  cmp     al, r14b
0x180021e5a  jb      loc_18002204E
0x180021e60  mov     edx, 0EAh
0x180021e65  mov     dword ptr [rsp+40h+var_20], ecx
0x180021e69  jmp     loc_180021D2E
0x180021e6e  mov     r12d, [rbp+arg_0]
0x180021e72  lea     rcx, [rbp+var_10]
0x180021e76  shr     r12d, 1
0x180021e79  add     r12d, 2
0x180021e7d  mov     [rbp+SubStr], 0
0x180021e85  mov     edx, r12d
0x180021e88  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180021e8d  mov     rdx, rax
0x180021e90  lea     rcx, [rbp+SubStr]
0x180021e94  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180021e99  lea     rcx, [rbp+var_10]
0x180021e9d  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180021ea2  mov     rbx, [rbp+SubStr]
0x180021ea6  test    rbx, rbx
0x180021ea9  jnz     short loc_180021ECA
0x180021eab  mov     ecx, 8007000Eh
0x180021eb0  mov     edi, ecx
0x180021eb2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021eb7  cmp     al, r14b
0x180021eba  jb      loc_1800220BB
0x180021ec0  mov     edx, 0E5h
0x180021ec5  jmp     loc_18002209D
0x180021eca  mov     rcx, [r13+18h]; pszDeviceInterface
0x180021ece  lea     rax, [rbp+arg_0]
0x180021ed2  mov     [rsp+40h+var_20], rax; unsigned int *
0x180021ed7  lea     r9d, [r12+r12]; unsigned int
0x180021edb  mov     r8, rbx; PropertyBuffer
0x180021ede  test    dil, dil
0x180021ee1  jz      short loc_180021F11
0x180021ee3  lea     rdx, DEVPKEY_DeviceInterface_FriendlyName; PropertyKey
0x180021eea  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180021eef  mov     edi, eax
0x180021ef1  test    eax, eax
0x180021ef3  jns     short loc_180021F38
0x180021ef5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021efa  cmp     al, r14b
0x180021efd  jb      loc_1800220BB
0x180021f03  mov     edx, 0E6h
0x180021f08  mov     dword ptr [rsp+40h+var_20], edi
0x180021f0c  jmp     loc_1800220A1
0x180021f11  lea     rdx, DEVPKEY_Device_FriendlyName; PropertyKey
0x180021f18  call    ?FSGetDeviceNodeProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceNodeProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180021f1d  mov     edi, eax
0x180021f1f  test    eax, eax
0x180021f21  jns     short loc_180021F38
0x180021f23  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021f28  cmp     al, r14b
0x180021f2b  jb      loc_1800220BB
0x180021f31  mov     edx, 0E7h
0x180021f36  jmp     short loc_180021F08
0x180021f38  mov     rcx, [r13+10h]; Str
0x180021f3c  mov     rdx, rbx; SubStr
0x180021f3f  call    cs:__imp_wcsstr
0x180021f45  mov     rdx, [r13+10h]
0x180021f49  mov     rcx, rsi
0x180021f4c  test    rax, rax
0x180021f4f  jz      short loc_180021FBF
0x180021f51  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180021f56  test    al, al
0x180021f58  jz      short loc_180021FA0
0x180021f5a  mov     r8d, 2
0x180021f60  lea     rdx, asc_180053A84; " ("
0x180021f67  mov     rcx, rsi
0x180021f6a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180021f6f  test    al, al
0x180021f71  jz      short loc_180021FA0
0x180021f73  mov     rdx, [r15+278h]
0x180021f7a  mov     rcx, rsi
0x180021f7d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180021f82  test    al, al
0x180021f84  jz      short loc_180021FA0
0x180021f86  mov     r8, r14
0x180021f89  lea     rdx, asc_180052ABC; ")"
0x180021f90  mov     rcx, rsi
0x180021f93  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180021f98  test    al, al
0x180021f9a  jnz     loc_18002203E
0x180021fa0  mov     ecx, 8007000Eh
0x180021fa5  mov     edi, ecx
0x180021fa7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021fac  cmp     al, r14b
0x180021faf  jb      loc_1800220BB
0x180021fb5  mov     edx, 0E8h
0x180021fba  jmp     loc_18002209D
0x180021fbf  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180021fc4  test    al, al
0x180021fc6  jz      loc_180022087
0x180021fcc  mov     r8d, 2
0x180021fd2  lea     rdx, asc_180053A84; " ("
0x180021fd9  mov     rcx, rsi
0x180021fdc  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180021fe1  test    al, al
0x180021fe3  jz      loc_180022087
0x180021fe9  mov     rdx, [r15+278h]
0x180021ff0  mov     rcx, rsi
0x180021ff3  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180021ff8  test    al, al
0x180021ffa  jz      loc_180022087
0x180022000  mov     r8d, 3
0x180022006  lea     rdx, asc_180053A90; " - "
0x18002200d  mov     rcx, rsi
0x180022010  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180022015  test    al, al
0x180022017  jz      short loc_180022087
0x180022019  mov     rdx, rbx
0x18002201c  mov     rcx, rsi
0x18002201f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180022024  test    al, al
0x180022026  jz      short loc_180022087
0x180022028  mov     r8, r14
0x18002202b  lea     rdx, asc_180052ABC; ")"
0x180022032  mov     rcx, rsi
0x180022035  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18002203a  test    al, al
0x18002203c  jz      short loc_180022087
0x18002203e  lea     rcx, [rbp+SubStr]
0x180022042  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180022047  lea     r12, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18002204e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180022053  test    edi, edi
0x180022055  js      short loc_1800220C9
0x180022057  cmp     al, 8
0x180022059  jb      loc_1800220F0
0x18002205f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022066  mov     edx, 0ECh
0x18002206b  mov     rax, [rsi]
0x18002206e  mov     r9d, edi
0x180022071  mov     r8, r12
0x180022074  mov     [rsp+40h+var_20], rax
0x180022079  mov     rcx, [rcx+0D8h]
0x180022080  call    WPP_SF_DS
0x180022085  jmp     short loc_1800220F0
0x180022087  mov     ecx, 8007000Eh
0x18002208c  mov     edi, ecx
0x18002208e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022093  cmp     al, r14b
0x180022096  jb      short loc_1800220BB
0x180022098  mov     edx, 0E9h
0x18002209d  mov     dword ptr [rsp+40h+var_20], ecx
0x1800220a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220a8  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x1800220af  mov     r9, r15
0x1800220b2  mov     rcx, [rcx+10h]
0x1800220b6  call    WPP_SF_qD
0x1800220bb  lea     rcx, [rbp+SubStr]
0x1800220bf  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x1800220c4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800220c9  cmp     al, r14b
0x1800220cc  jb      short loc_1800220F0
0x1800220ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220d5  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x1800220dc  mov     edx, 0EBh
0x1800220e1  mov     r9d, edi
0x1800220e4  mov     rcx, [rcx+0D8h]
0x1800220eb  call    WPP_SF_d
0x1800220f0  mov     rbx, [rsp+40h+arg_8]
0x1800220f8  mov     eax, edi
0x1800220fa  add     rsp, 40h
0x1800220fe  pop     r15
0x180022100  pop     r14
0x180022102  pop     r13
0x180022104  pop     r12
0x180022106  pop     rdi
0x180022107  pop     rsi
0x180022108  pop     rbp
0x180022109  retn
```
