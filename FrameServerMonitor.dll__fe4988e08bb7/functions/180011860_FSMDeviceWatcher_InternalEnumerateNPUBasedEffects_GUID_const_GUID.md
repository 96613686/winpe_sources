# FSMDeviceWatcher::InternalEnumerateNPUBasedEffects(_GUID const &,_GUID *)

- ea: `0x180011860`
- end: `0x180011c13`
- name: `?InternalEnumerateNPUBasedEffects@FSMDeviceWatcher@@MEAAJAEBU_GUID@@PEAU2@@Z`
- size: `947`
- prototype: `__int64 __fastcall(FSMDeviceWatcher *__hidden this, const struct _GUID *, struct _GUID *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180006a98`
- `0x18000723c`
- `0x18000d154`
- `0x18000d1e0`
- `0x18000d4f8`
- `0x18000d62c`
- `0x18000d778`
- `0x18000e25c`
- `0x180011438`
- `0x180011860`
- `0x180018418`
- `0x18002fa3c`
- `0x18002fd04`
- `0x180040004`
- `0x180040a10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180011b30`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180011b30`

## string_xrefs

- `0x180011a3b`: `CustomCaptureSourceClsid`
- `0x180011ad7`: `CustomCaptureSourceClsid`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::InternalEnumerateNPUBasedEffects(
        FSMDeviceWatcher *this,
        const struct _GUID *a2,
        struct _GUID *a3)
{
  char v4; // al
  GUID v6; // xmm0
  GuidTrace *v8; // rax
  const char *String; // rax
  unsigned int v10; // edi
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdx
  char v14; // al
  void **i; // rbx
  unsigned int v16; // r15d
  __int64 v17; // rdi
  const struct std::nothrow_t *unique; // rax
  BYTE *v19; // rbx
  LPCOLESTR v20; // rcx
  __int64 v21; // rdx
  unsigned int *v23; // [rsp+28h] [rbp-51h]
  unsigned int *v24; // [rsp+28h] [rbp-51h]
  unsigned int v25; // [rsp+30h] [rbp-49h] BYREF
  void **v26[2]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v27; // [rsp+48h] [rbp-31h]
  LPCOLESTR lpsz; // [rsp+50h] [rbp-29h] BYREF
  __int64 v29; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v30[32]; // [rsp+60h] [rbp-19h] BYREF
  GUID pclsid; // [rsp+80h] [rbp+7h] BYREF

  v4 = 0;
  v6 = GUID_00000000_0000_0000_0000_000000000000;
  v26[0] = (void **)v26;
  v27 = 0;
  pclsid = GUID_00000000_0000_0000_0000_000000000000;
  v26[1] = (void **)v26;
  v25 = 0;
  lpsz = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v8 = GuidTrace::GuidTrace((GuidTrace *)v30, a2);
    String = GuidTrace::GetString(v8);
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      261,
      (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
      (_DWORD)this,
      (__int64)String);
    v6 = GUID_00000000_0000_0000_0000_000000000000;
    v4 = 1;
  }
  if ( (v4 & 1) != 0 )
  {
    FSString::~FSString((FSString *)v30, (const struct std::nothrow_t *)a2);
    v6 = GUID_00000000_0000_0000_0000_000000000000;
  }
  if ( !a3 )
  {
    v10 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_39;
    v11 = 262;
    goto LABEL_8;
  }
  *a3 = v6;
  v12 = FSEnumDeviceInterfaces(a2, a2, v26);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_39;
    v13 = 263;
LABEL_38:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v12);
    goto LABEL_39;
  }
  if ( v27 )
  {
    v14 = byte_18005E5A5;
    if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
    {
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          265,
          &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
          this,
          v27);
        v14 = byte_18005E5A5;
      }
      for ( i = v26[0]; i != (void **)v26; i = (void **)*i )
      {
        if ( (unsigned __int8)v14 >= 8u )
        {
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            266,
            (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
            (_DWORD)this,
            (__int64)i[2]);
          v14 = byte_18005E5A5;
        }
      }
    }
    if ( (unsigned int)FSGetDeviceInterfaceRegistryEntry2(
                         *((LPCWSTR *)v26[0] + 2),
                         L"CustomCaptureSourceClsid",
                         0,
                         0,
                         &v25,
                         v23) == -1072860816
      && v25 > 2 )
    {
      v16 = (v25 >> 1) + 1;
      v17 = v16;
      unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v29, v16);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&lpsz, unique);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v29);
      v19 = (BYTE *)lpsz;
      if ( !lpsz )
      {
        v10 = -2147024882;
        if ( g_wppLevels )
        {
          v11 = 268;
LABEL_8:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v11,
            &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
            this,
            v10);
        }
LABEL_39:
        if ( byte_18005E5A5 )
        {
          v21 = 272;
LABEL_46:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v21,
            &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
            this,
            v10);
          goto LABEL_47;
        }
        goto LABEL_47;
      }
      v20 = lpsz;
      do
      {
        *v20++ = 0;
        --v17;
      }
      while ( v17 );
      v12 = FSGetDeviceInterfaceRegistryEntry2(
              *((LPCWSTR *)v26[0] + 2),
              L"CustomCaptureSourceClsid",
              v19,
              2 * v16,
              &v25,
              v24);
      v10 = v12;
      if ( v12 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_39;
        v13 = 269;
        goto LABEL_38;
      }
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          270,
          (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
          (_DWORD)this,
          (__int64)v19);
      v12 = CLSIDFromString((LPCOLESTR)v19, &pclsid);
      v10 = v12;
      if ( v12 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_39;
        v13 = 271;
        goto LABEL_38;
      }
      *a3 = pclsid;
    }
    else
    {
      v10 = 0;
      if ( (unsigned __int8)byte_18005E5A5 < 8u )
        goto LABEL_47;
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        267,
        (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        (_DWORD)this,
        (__int64)v26[0][2]);
    }
  }
  else
  {
    if ( (unsigned __int8)byte_18005E5A5 < 8u )
      goto LABEL_47;
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 264, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v21 = 273;
    goto LABEL_46;
  }
LABEL_47:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&lpsz);
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(v26);
  return v10;
}

```

## disassembly

```asm
0x180011860  push    rbp
0x180011862  push    rbx
0x180011863  push    rsi
0x180011864  push    rdi
0x180011865  push    r12
0x180011867  push    r14
0x180011869  push    r15
0x18001186b  lea     rbp, [rsp-27h]
0x180011870  sub     rsp, 0A0h
0x180011877  mov     rax, cs:__security_cookie
0x18001187e  xor     rax, rsp
0x180011881  mov     [rbp+57h+var_40], rax
0x180011885  xor     r15d, r15d
0x180011888  mov     rsi, rcx
0x18001188b  lea     rcx, [rbp+57h+var_98]
0x18001188f  mov     eax, r15d
0x180011892  mov     [rbp+57h+var_A0], eax
0x180011895  mov     r14, r8
0x180011898  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001189f  mov     [rbp+57h+var_98], rcx
0x1800118a3  mov     rbx, rdx
0x1800118a6  lea     rcx, [rbp+57h+var_98]
0x1800118aa  mov     [rbp+57h+var_88], r15
0x1800118ae  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x1800118b3  mov     [rbp+57h+var_90], rcx
0x1800118b7  mov     [rbp+57h+var_A0], r15d
0x1800118bb  mov     [rbp+57h+lpsz], r15
0x1800118bf  cmp     cs:byte_18005E5A5, 8
0x1800118c6  lea     r12, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800118cd  jb      short loc_18001190E
0x1800118cf  lea     rcx, [rbp+57h+var_70]; this
0x1800118d3  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800118d8  mov     rcx, rax; this
0x1800118db  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800118e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118e7  mov     edx, 105h
0x1800118ec  mov     r9, rsi
0x1800118ef  mov     [rsp+0D0h+var_B0], rax
0x1800118f4  mov     r8, r12
0x1800118f7  mov     rcx, [rcx+0D8h]
0x1800118fe  call    WPP_SF_qs
0x180011903  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001190a  lea     eax, [r15+1]
0x18001190e  test    al, 1
0x180011910  jz      short loc_180011922
0x180011912  lea     rcx, [rbp+57h+var_70]; this
0x180011916  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18001191b  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180011922  test    r14, r14
0x180011925  jnz     short loc_180011947
0x180011927  mov     edi, 80004003h
0x18001192c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180011933  jb      loc_180011B64
0x180011939  mov     edx, 106h
0x18001193e  mov     dword ptr [rsp+0D0h+var_B0], edi
0x180011942  jmp     loc_180011B4E
0x180011947  lea     r8, [rbp+57h+var_98]
0x18001194b  mov     rcx, rbx
0x18001194e  movdqu  xmmword ptr [r14], xmm0
0x180011953  call    ?FSEnumDeviceInterfaces@@YAJAEBU_GUID@@_NAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSEnumDeviceInterfaces(_GUID const &,bool,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x180011958  mov     edi, eax
0x18001195a  test    eax, eax
0x18001195c  jns     short loc_180011975
0x18001195e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180011965  jb      loc_180011B64
0x18001196b  mov     edx, 107h
0x180011970  jmp     loc_180011B4A
0x180011975  mov     rcx, [rbp+57h+var_88]
0x180011979  test    rcx, rcx
0x18001197c  jnz     short loc_1800119AE
0x18001197e  cmp     cs:byte_18005E5A5, 8
0x180011985  jb      loc_180011BE1
0x18001198b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011992  mov     edx, 108h
0x180011997  mov     r9, rsi
0x18001199a  mov     r8, r12
0x18001199d  mov     rcx, [rcx+0D8h]
0x1800119a4  call    WPP_SF_q
0x1800119a9  jmp     loc_180011BB6
0x1800119ae  mov     al, cs:byte_18005E5A5
0x1800119b4  cmp     al, 10h
0x1800119b6  jb      short loc_180011A28
0x1800119b8  cmp     al, 8
0x1800119ba  jb      short loc_1800119E5
0x1800119bc  mov     [rsp+0D0h+var_B0], rcx
0x1800119c1  mov     edx, 109h
0x1800119c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119cd  mov     r9, rsi
0x1800119d0  mov     r8, r12
0x1800119d3  mov     rcx, [rcx+0D8h]
0x1800119da  call    WPP_SF_qq
0x1800119df  mov     al, cs:byte_18005E5A5
0x1800119e5  mov     rbx, [rbp+57h+var_98]
0x1800119e9  lea     rcx, [rbp+57h+var_98]
0x1800119ed  cmp     rbx, rcx
0x1800119f0  jz      short loc_180011A28
0x1800119f2  cmp     al, 8
0x1800119f4  jb      short loc_180011A23
0x1800119f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119fd  mov     edx, 10Ah
0x180011a02  mov     rax, [rbx+10h]
0x180011a06  mov     r9, rsi
0x180011a09  mov     r8, r12
0x180011a0c  mov     [rsp+0D0h+var_B0], rax
0x180011a11  mov     rcx, [rcx+0D8h]
0x180011a18  call    WPP_SF_qS
0x180011a1d  mov     al, cs:byte_18005E5A5
0x180011a23  mov     rbx, [rbx]
0x180011a26  jmp     short loc_1800119E9
0x180011a28  mov     rcx, [rbp+57h+var_98]
0x180011a2c  lea     rax, [rbp+57h+var_A0]
0x180011a30  xor     r9d, r9d; unsigned int
0x180011a33  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x180011a38  xor     r8d, r8d; lpData
0x180011a3b  lea     rdx, aCustomcaptures; "CustomCaptureSourceClsid"
0x180011a42  mov     rcx, [rcx+10h]; pszDeviceInterface
0x180011a46  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x180011a4b  cmp     eax, 0C00D7170h
0x180011a50  jnz     loc_180011B7F
0x180011a56  mov     eax, [rbp+57h+var_A0]
0x180011a59  cmp     eax, 2
0x180011a5c  jbe     loc_180011B7F
0x180011a62  shr     eax, 1
0x180011a64  lea     rcx, [rbp+57h+var_78]
0x180011a68  lea     r15d, [rax+1]
0x180011a6c  mov     edx, r15d
0x180011a6f  mov     edi, r15d
0x180011a72  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180011a77  mov     rdx, rax
0x180011a7a  lea     rcx, [rbp+57h+lpsz]
0x180011a7e  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180011a83  lea     rcx, [rbp+57h+var_78]
0x180011a87  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180011a8c  mov     rbx, [rbp+57h+lpsz]
0x180011a90  test    rbx, rbx
0x180011a93  jnz     short loc_180011AB1
0x180011a95  mov     edi, 8007000Eh
0x180011a9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180011aa1  jb      loc_180011B64
0x180011aa7  mov     edx, 10Ch
0x180011aac  jmp     loc_18001193E
0x180011ab1  mov     rcx, rbx
0x180011ab4  xor     eax, eax
0x180011ab6  mov     [rcx], ax
0x180011ab9  lea     rcx, [rcx+2]
0x180011abd  sub     rdi, 1
0x180011ac1  jnz     short loc_180011AB4
0x180011ac3  mov     rcx, [rbp+57h+var_98]
0x180011ac7  lea     rax, [rbp+57h+var_A0]
0x180011acb  lea     r9d, [r15+r15]; unsigned int
0x180011acf  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x180011ad4  mov     r8, rbx; lpData
0x180011ad7  lea     rdx, aCustomcaptures; "CustomCaptureSourceClsid"
0x180011ade  mov     rcx, [rcx+10h]; pszDeviceInterface
0x180011ae2  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x180011ae7  mov     edi, eax
0x180011ae9  test    eax, eax
0x180011aeb  jns     short loc_180011AFD
0x180011aed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180011af4  jb      short loc_180011B64
0x180011af6  mov     edx, 10Dh
0x180011afb  jmp     short loc_180011B4A
0x180011afd  cmp     cs:byte_18005E5A5, 8
0x180011b04  jb      short loc_180011B29
0x180011b06  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b0d  mov     edx, 10Eh
0x180011b12  mov     r9, rsi
0x180011b15  mov     [rsp+0D0h+var_B0], rbx
0x180011b1a  mov     r8, r12
0x180011b1d  mov     rcx, [rcx+0D8h]
0x180011b24  call    WPP_SF_qS
0x180011b29  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180011b2d  mov     rcx, rbx; lpsz
0x180011b30  call    cs:__imp_CLSIDFromString
0x180011b36  mov     edi, eax
0x180011b38  test    eax, eax
0x180011b3a  jns     short loc_180011B74
0x180011b3c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180011b43  jb      short loc_180011B64
0x180011b45  mov     edx, 10Fh
0x180011b4a  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180011b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b55  mov     r9, rsi
0x180011b58  mov     r8, r12
0x180011b5b  mov     rcx, [rcx+10h]
0x180011b5f  call    WPP_SF_qD
0x180011b64  cmp     cs:byte_18005E5A5, 1
0x180011b6b  jb      short loc_180011BE1
0x180011b6d  mov     edx, 110h
0x180011b72  jmp     short loc_180011BC4
0x180011b74  movups  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x180011b78  movdqu  xmmword ptr [r14], xmm0
0x180011b7d  jmp     short loc_180011BB6
0x180011b7f  mov     edi, r15d
0x180011b82  cmp     cs:byte_18005E5A5, 8
0x180011b89  jb      short loc_180011BE1
0x180011b8b  mov     rax, [rbp+57h+var_98]
0x180011b8f  mov     edx, 10Bh
0x180011b94  mov     r9, rsi
0x180011b97  mov     r8, r12
0x180011b9a  mov     rcx, [rax+10h]
0x180011b9e  mov     [rsp+0D0h+var_B0], rcx
0x180011ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011baa  mov     rcx, [rcx+0D8h]
0x180011bb1  call    WPP_SF_qS
0x180011bb6  cmp     cs:byte_18005E5A5, 8
0x180011bbd  jb      short loc_180011BE1
0x180011bbf  mov     edx, 111h
0x180011bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bcb  mov     r9, rsi
0x180011bce  mov     r8, r12
0x180011bd1  mov     dword ptr [rsp+0D0h+var_B0], edi
0x180011bd5  mov     rcx, [rcx+0D8h]
0x180011bdc  call    WPP_SF_qD
0x180011be1  lea     rcx, [rbp+57h+lpsz]
0x180011be5  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180011bea  lea     rcx, [rbp+57h+var_98]
0x180011bee  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x180011bf3  mov     eax, edi
0x180011bf5  mov     rcx, [rbp+57h+var_40]
0x180011bf9  xor     rcx, rsp; StackCookie
0x180011bfc  call    __security_check_cookie
0x180011c01  add     rsp, 0A0h
0x180011c08  pop     r15
0x180011c0a  pop     r14
0x180011c0c  pop     r12
0x180011c0e  pop     rdi
0x180011c0f  pop     rsi
0x180011c10  pop     rbx
0x180011c11  pop     rbp
0x180011c12  retn
```
