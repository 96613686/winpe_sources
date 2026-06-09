# PutSecurityDescriptor

- ea: `0x140022778`
- end: `0x140022d2f`
- name: `PutSecurityDescriptor`
- size: `1463`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x140005240`
- `0x140005264`
- `0x140005918`
- `0x1400061f8`
- `0x140006210`
- `0x14000d5c4`
- `0x14000f1c4`
- `0x14000f368`
- `0x14000f944`
- `0x140015958`
- `0x140022778`
- `0x140028044`
- `0x14003178c`
- `0x1400317a8`
- `0x1400317c8`
- `0x14003c05c`
- `0x14003c630`
- `0x14004698c`
- `0x140046d08`
- `0x140046ff8`
- `0x140047074`
- `0x1400471dc`
- `0x140047318`
- `0x1400473a8`
- `0x140070010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140022925`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140022925`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x140022baf`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x140022baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022bb9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140022a46`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140022a46`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140022b18`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140022b18`

## string_xrefs

- `0x1400229d7`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx"`
- `0x140022a0f`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx"`
- `0x1400229b3`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrdaemon.cxx`
- `0x140022b2a`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrdaemon.cxx`
- `0x140022c78`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrdaemon.cxx`
- `0x1400229cb`: `[SrchFilterDaemon] Fltrdmn: ACL is too big 0x%08x`
- `0x1400228f2`: `[SrchFilterDaemon] Fltrdmn: failure reading ACL 0x%08x`
- `0x140022bd0`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`
- `0x140022be7`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x140022bc4`: `[UtilSecurity] SetSecurityDescriptorSacl failed. 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PutSecurityDescriptor(CFilterSink *this, __int64 a2)
{
  char *v4; // rbx
  char *p_pSecurityDescriptor; // r14
  unsigned int v6; // r15d
  int v7; // eax
  int v8; // esi
  char *v9; // rcx
  LONG SecurityDescriptorLength; // eax
  int v11; // edx
  int v12; // r9d
  const wchar_t *v13; // r8
  __int64 v14; // rdx
  PSECURITY_DESCRIPTOR v15; // rdx
  signed int LastError; // eax
  int i; // ebx
  __int64 v18; // rdx
  __int64 v19; // r8
  const char *v20; // r9
  int v21; // edx
  int v22; // r9d
  const wchar_t *v23; // rbx
  int v25; // ebx
  unsigned int v26; // [rsp+20h] [rbp-578h]
  _BYTE v27[8]; // [rsp+30h] [rbp-568h] BYREF
  unsigned int v28[2]; // [rsp+38h] [rbp-560h] BYREF
  int v29; // [rsp+40h] [rbp-558h] BYREF
  PSID Sid; // [rsp+48h] [rbp-550h] BYREF
  char *v31; // [rsp+50h] [rbp-548h]
  char *v32; // [rsp+58h] [rbp-540h] BYREF
  char *v33; // [rsp+60h] [rbp-538h] BYREF
  _QWORD v34[3]; // [rsp+68h] [rbp-530h] BYREF
  struct tagPROPVARIANT v35; // [rsp+80h] [rbp-518h] BYREF
  _BYTE pAbsoluteSecurityDescriptor[56]; // [rsp+A0h] [rbp-4F8h] BYREF
  struct _ACL *v37[3]; // [rsp+D8h] [rbp-4C0h] BYREF
  LPCWSTR StringSid[6]; // [rsp+F0h] [rbp-4A8h]
  struct tagSTAT_CHUNK v39; // [rsp+120h] [rbp-478h] BYREF
  char pSecurityDescriptor; // [rsp+160h] [rbp-438h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+598h] [rbp+0h]

  StringSid[4] = (LPCWSTR)-2LL;
  v34[1] = this;
  memset_0(&v39, 0, sizeof(v39));
  v39.breakType = CHUNK_EOS;
  v39.flags = CHUNK_VALUE;
  v39.attribute.guidPropSet = GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04;
  v39.attribute.psProperty.ulKind = 1;
  LODWORD(v39.attribute.psProperty.propid) = 6;
  memset(&v35, 0, sizeof(v35));
  v4 = 0;
  v33 = 0;
  v32 = 0;
  p_pSecurityDescriptor = &pSecurityDescriptor;
  v6 = 1024;
  v28[1] = 0;
  v28[0] = 0;
LABEL_2:
  v31 = p_pSecurityDescriptor;
  while ( 1 )
  {
    while ( g_perUserSD )
    {
      v28[1] = g_perUserSDLength;
      if ( g_perUserSDLength <= v6 )
      {
        memcpy_0(p_pSecurityDescriptor, g_perUserSD, g_perUserSDLength);
LABEL_18:
        SecurityDescriptorLength = GetSecurityDescriptorLength(p_pSecurityDescriptor);
        goto LABEL_19;
      }
    }
    v7 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, unsigned int *))(*(_QWORD *)a2 + 88LL))(
           a2,
           p_pSecurityDescriptor,
           v6,
           &v28[1]);
    v8 = v7;
    if ( !v7 )
      goto LABEL_18;
    if ( v7 == 266768 || v7 == -2147467263 )
      break;
    if ( v7 == -2147024774 )
    {
      if ( v6 != 1024 )
      {
        v13 = (const wchar_t *)L"[SrchFilterDaemon] Fltrdmn: gave bigger buffer but it was not big enough! 0x%08x";
        v14 = 2113;
        goto LABEL_28;
      }
      if ( v28[1] <= 0x400 )
      {
        v13 = L"[SrchFilterDaemon] Fltrdmn: PH wants smaller buffer 0x%08x";
        v14 = 2123;
LABEL_28:
        v8 = -2147418113;
        SearchIndexerTrace::Error(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrdaemon.cxx\"",
          (const wchar_t *)v14,
          (unsigned int)v13,
          (const wchar_t *)0x8000FFFFLL);
        goto LABEL_51;
      }
      if ( v28[1] >= 0x10000 )
      {
        SearchIndexerTrace::Error(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrdaemon.cxx\"",
          (const wchar_t *)0x855,
          (unsigned int)L"[SrchFilterDaemon] Fltrdmn: ACL is too big 0x%08x",
          (const wchar_t *)0x80041212LL);
        v8 = -2147216878;
        goto LABEL_51;
      }
      p_pSecurityDescriptor = (char *)operator new[](v28[1]);
      v9 = v4;
      v4 = p_pSecurityDescriptor;
      v33 = p_pSecurityDescriptor;
      if ( v9 )
        operator delete(v9);
      v6 = v28[1];
      goto LABEL_2;
    }
    if ( v7 < 0 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrdaemon.cxx\"",
        (const wchar_t *)0x86D,
        (unsigned int)L"[SrchFilterDaemon] Fltrdmn: failure reading ACL 0x%08x",
        (const wchar_t *)(unsigned int)v7);
LABEL_51:
      SecUtil::CSID::~CSID((SecUtil::CSID *)&v32);
      SecUtil::CSID::~CSID((SecUtil::CSID *)&v33);
      return (unsigned int)v8;
    }
  }
  v15 = g_sdWorld;
  if ( !g_sdWorld )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:WDG:AUD:P(A;NP;FR;;;WD)",
            1u,
            &g_sdWorld,
            &g_cbWorldSD) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = LastError;
      goto LABEL_51;
    }
    v15 = g_sdWorld;
  }
  if ( g_cbWorldSD > v6 )
  {
    v8 = -2147024774;
    goto LABEL_51;
  }
  memcpy_0(p_pSecurityDescriptor, v15, g_cbWorldSD);
  SecurityDescriptorLength = g_cbWorldSD;
LABEL_19:
  v28[0] = SecurityDescriptorLength;
  if ( SecurityDescriptorLength )
  {
    try
    {
      SecUtil::CSecurityDescriptor::CSecurityDescriptor(pAbsoluteSecurityDescriptor);
      SecUtil::CSecurityDescriptor::InitializeFromSelfRelative(pAbsoluteSecurityDescriptor, p_pSecurityDescriptor);
      if ( v37[0] )
      {
        if ( *((_DWORD *)this + 393) )
        {
          SecUtil::CSID_AdministratorsGroup::CSID_AdministratorsGroup((SecUtil::CSID_AdministratorsGroup *)&Sid);
          SecUtil::CACL::RemoveAceByPrefix((SecUtil::CACL *)v37, Sid);
          if ( !SecUtil::CACL::GetAceCount((SecUtil::CACL *)v37) )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x886,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
              (const char *)0x80040DAALL,
              v26);
          SecUtil::CSecurityDescriptor::SetDacl(
            (SecUtil::CSecurityDescriptor *)pAbsoluteSecurityDescriptor,
            v11,
            v37[0],
            v12);
          SecUtil::CSID::~CSID((SecUtil::CSID *)&Sid);
        }
        StringSid[0] = L"S-1-15-3-1024-1822509804-4202500280-131100095-208896226-3924139855-286224443-1964377501-2274755015";
        StringSid[1] = L"S-1-15-3-1024-724741592-1210917904-489960769-637019204-3345707629-3097053430-1727148295-85063603";
        StringSid[2] = L"S-1-15-3-128907917-1049808183-3772720920-2589851895-2273257875-2082631859-2896883434";
        StringSid[3] = L"S-1-15-3-1861897761-1695161497-2927542615-642690995-327840285-2659745135-2630312742";
        for ( i = 0; (unsigned __int64)i < 4; ++i )
        {
          Sid = 0;
          if ( !ConvertStringSidToSidW(StringSid[i], &Sid) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x894,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
              v20);
          v34[0] = Sid;
          v27[0] = 0;
          v29 = 2031745;
          SecUtil::CACL::AddAccessXXXAces(v37, v18, v19, v34, &v29, v27);
          SecUtil::CSecurityDescriptor::SetDacl(
            (SecUtil::CSecurityDescriptor *)pAbsoluteSecurityDescriptor,
            v21,
            v37[0],
            v22);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
        }
      }
      if ( !SetSecurityDescriptorSacl(pAbsoluteSecurityDescriptor, 0, 0, 0) )
      {
        v23 = (const wchar_t *)GetLastError();
        SearchIndexerTrace::Error(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\secutil\\\\secutil.cxx\"",
          (const wchar_t *)0xCE,
          (unsigned int)L"[UtilSecurity] SetSecurityDescriptorSacl failed. 0x%08x",
          v23);
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xCF,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
          (const char *)(unsigned int)v23,
          v26);
      }
      v8 = SecUtil::CSecurityDescriptor::Export(
             (SecUtil::CSecurityDescriptor *)pAbsoluteSecurityDescriptor,
             (unsigned __int8 *)p_pSecurityDescriptor,
             v6,
             v28);
      if ( v8 == -2147024774 )
      {
        p_pSecurityDescriptor = (char *)operator new[](v28[0]);
        v32 = p_pSecurityDescriptor;
        v8 = SecUtil::CSecurityDescriptor::Export(
               (SecUtil::CSecurityDescriptor *)pAbsoluteSecurityDescriptor,
               (unsigned __int8 *)p_pSecurityDescriptor,
               v28[0],
               v28);
        v31 = p_pSecurityDescriptor;
      }
      SecUtil::CSecurityDescriptor::~CSecurityDescriptor((SecUtil::CSecurityDescriptor *)pAbsoluteSecurityDescriptor);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        2219,
        "onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx");
    }
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8AE,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
        (const char *)(unsigned int)v8,
        v26);
      goto LABEL_51;
    }
    SecurityDescriptorLength = v28[0];
  }
  v35.vt = 65;
  v35.lVal = SecurityDescriptorLength;
  v35.bstrblobVal.pData = (BYTE *)p_pSecurityDescriptor;
  v25 = CFilterSink::AddChunk(this, &v39);
  if ( v25 >= 0 )
    v25 = CFilterSink::AddValue(this, &v35);
  SecUtil::CSID::~CSID((SecUtil::CSID *)&v32);
  SecUtil::CSID::~CSID((SecUtil::CSID *)&v33);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x140022778  mov     r11, rsp
0x14002277b  push    rdi
0x14002277c  push    r12
0x14002277e  push    r13
0x140022780  push    r14
0x140022782  push    r15
0x140022784  sub     rsp, 570h
0x14002278b  mov     qword ptr [r11-488h], 0FFFFFFFFFFFFFFFEh
0x140022796  mov     [r11+18h], rbx
0x14002279a  mov     [r11+20h], rsi
0x14002279e  mov     rax, cs:__security_cookie
0x1400227a5  xor     rax, rsp
0x1400227a8  mov     [rsp+598h+var_38], rax
0x1400227b0  mov     r13, rdx
0x1400227b3  mov     r12, rcx
0x1400227b6  mov     [rsp+598h+var_528], rcx
0x1400227bb  xor     edx, edx; Val
0x1400227bd  lea     r8d, [rdx+40h]; Size
0x1400227c1  lea     rcx, [r11-478h]; void *
0x1400227c8  call    memset_0
0x1400227cd  mov     eax, 2
0x1400227d2  mov     [rsp+598h+var_478.breakType], eax
0x1400227d9  mov     [rsp+598h+var_478.flags], eax
0x1400227e0  movups  xmm0, xmmword ptr cs:_GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data1
0x1400227e7  movdqu  xmmword ptr [rsp+598h+var_478.attribute.guidPropSet.Data1], xmm0
0x1400227f0  mov     [rsp+598h+var_478.attribute.psProperty.ulKind], 1
0x1400227fb  mov     dword ptr [rsp+598h+var_478.attribute.psProperty.8], 6
0x140022806  xorps   xmm0, xmm0
0x140022809  xor     eax, eax
0x14002280b  movups  xmmword ptr [rsp+598h+var_518], xmm0
0x140022813  mov     qword ptr [rsp+598h+var_518+10h], rax
0x14002281b  xor     edi, edi
0x14002281d  mov     ebx, edi
0x14002281f  mov     [rsp+598h+var_538], rbx
0x140022824  mov     [rsp+598h+var_540], rdi
0x140022829  lea     r14, [rsp+598h+pSecurityDescriptor]
0x140022831  mov     r15d, 400h
0x140022837  mov     [rsp+598h+var_560+4], edi
0x14002283b  mov     [rsp+598h+var_560], edi
0x14002283f  mov     [rsp+598h+var_548], r14
0x140022844  mov     eax, cs:?g_perUserSDLength@@3KA; ulong g_perUserSDLength
0x14002284a  cmp     cs:?g_perUserSD@@3PEAU_SECURITY_DESCRIPTOR@@EA, rdi; _SECURITY_DESCRIPTOR * g_perUserSD
0x140022851  jnz     loc_140022903
0x140022857  mov     rax, [r13+0]
0x14002285b  lea     r9, [rsp+598h+var_560+4]
0x140022860  mov     r8d, r15d
0x140022863  mov     rdx, r14
0x140022866  mov     rcx, r13
0x140022869  mov     rax, [rax+58h]
0x14002286d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022872  mov     esi, eax
0x140022874  test    eax, eax
0x140022876  jz      loc_140022922
0x14002287c  cmp     eax, 41210h
0x140022881  jz      loc_140022A20
0x140022887  cmp     eax, 80004001h
0x14002288c  jz      loc_140022A20
0x140022892  cmp     eax, 8007007Ah
0x140022897  jnz     short loc_1400228E7
0x140022899  mov     esi, 400h
0x14002289e  cmp     r15d, esi
0x1400228a1  jnz     loc_1400229FB
0x1400228a7  mov     eax, [rsp+598h+var_560+4]
0x1400228ab  cmp     eax, esi
0x1400228ad  jbe     loc_1400229ED
0x1400228b3  cmp     eax, 10000h
0x1400228b8  jnb     loc_1400229C5
0x1400228be  mov     ecx, eax; unsigned __int64
0x1400228c0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400228c5  mov     r14, rax
0x1400228c8  mov     rcx, rbx; Block
0x1400228cb  mov     rbx, rax
0x1400228ce  mov     [rsp+598h+var_538], rax
0x1400228d3  test    rcx, rcx
0x1400228d6  jz      short loc_1400228DD
0x1400228d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400228dd  mov     r15d, [rsp+598h+var_560+4]
0x1400228e2  jmp     loc_14002283F
0x1400228e7  test    eax, eax
0x1400228e9  jns     loc_140022844
0x1400228ef  mov     r9d, eax
0x1400228f2  lea     r8, aSrchfilterdaem_7; "[SrchFilterDaemon] Fltrdmn: failure rea"...
0x1400228f9  mov     edx, 86Dh
0x1400228fe  jmp     loc_140022A0F
0x140022903  mov     [rsp+598h+var_560+4], eax
0x140022907  cmp     eax, r15d
0x14002290a  ja      loc_14002284A
0x140022910  mov     r8d, eax; Size
0x140022913  mov     rdx, cs:?g_perUserSD@@3PEAU_SECURITY_DESCRIPTOR@@EA; Src
0x14002291a  mov     rcx, r14; void *
0x14002291d  call    memcpy_0
0x140022922  mov     rcx, r14; pSecurityDescriptor
0x140022925  call    cs:__imp_GetSecurityDescriptorLength
0x14002292b  mov     ecx, eax
0x14002292d  mov     [rsp+598h+var_560], eax
0x140022931  test    eax, eax
0x140022933  jz      loc_140022CA7
0x140022939  lea     rcx, [rsp+598h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x140022941  call    ??0CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::CSecurityDescriptor(void)
0x140022946  nop
0x140022947  mov     rdx, r14; pSelfRelativeSecurityDescriptor
0x14002294a  lea     rcx, [rsp+598h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x140022952  call    ?InitializeFromSelfRelative@CSecurityDescriptor@SecUtil@@QEAAXPEAX@Z; SecUtil::CSecurityDescriptor::InitializeFromSelfRelative(void *)
0x140022957  cmp     [rsp+598h+var_4C0], rdi
0x14002295f  jz      loc_140022B9F
0x140022965  cmp     [r12+624h], edi
0x14002296d  jz      loc_140022ABB
0x140022973  lea     rcx, [rsp+598h+Sid]; this
0x140022978  call    ??0CSID_AdministratorsGroup@SecUtil@@QEAA@XZ; SecUtil::CSID_AdministratorsGroup::CSID_AdministratorsGroup(void)
0x14002297d  nop
0x14002297e  mov     rdx, [rsp+598h+Sid]; void *
0x140022983  lea     rcx, [rsp+598h+var_4C0]; this
0x14002298b  call    ?RemoveAceByPrefix@CACL@SecUtil@@QEAAXPEAX@Z; SecUtil::CACL::RemoveAceByPrefix(void *)
0x140022990  lea     rcx, [rsp+598h+var_4C0]; this
0x140022998  call    ?GetAceCount@CACL@SecUtil@@QEBAKXZ; SecUtil::CACL::GetAceCount(void)
0x14002299d  test    eax, eax
0x14002299f  jnz     loc_140022A9B
0x1400229a5  mov     rcx, [rsp+598h]; this
0x1400229ad  mov     r9d, 80040DAAh; char *
0x1400229b3  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\sea"...
0x1400229ba  mov     edx, 886h; void *
0x1400229bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400229c5  mov     r9d, 80041212h; wchar_t *
0x1400229cb  lea     r8, aSrchfilterdaem_29; "[SrchFilterDaemon] Fltrdmn: ACL is too "...
0x1400229d2  mov     edx, 855h; wchar_t *
0x1400229d7  lea     rcx, aOnecoreuapBase_54; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1400229de  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1400229e3  mov     esi, 80041212h
0x1400229e8  jmp     loc_140022C8A
0x1400229ed  lea     r8, aSrchfilterdaem_27; "[SrchFilterDaemon] Fltrdmn: PH wants sm"...
0x1400229f4  mov     edx, 84Bh
0x1400229f9  jmp     short loc_140022A07
0x1400229fb  lea     r8, aSrchfilterdaem_40; "[SrchFilterDaemon] Fltrdmn: gave bigger"...
0x140022a02  mov     edx, 841h; wchar_t *
0x140022a07  mov     esi, 8000FFFFh
0x140022a0c  mov     r9d, esi; wchar_t *
0x140022a0f  lea     rcx, aOnecoreuapBase_54; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140022a16  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140022a1b  jmp     loc_140022C8A
0x140022a20  mov     rdx, cs:?g_sdWorld@@3PEAU_SECURITY_DESCRIPTOR@@EA; _SECURITY_DESCRIPTOR * g_sdWorld
0x140022a27  test    rdx, rdx
0x140022a2a  jnz     short loc_140022A70
0x140022a2c  lea     r9, ?g_cbWorldSD@@3KA; SecurityDescriptorSize
0x140022a33  lea     r8, ?g_sdWorld@@3PEAU_SECURITY_DESCRIPTOR@@EA; SecurityDescriptor
0x140022a3a  mov     edx, 1; StringSDRevision
0x140022a3f  lea     rcx, StringSecurityDescriptor; "O:WDG:AUD:P(A;NP;FR;;;WD)"
0x140022a46  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140022a4c  test    eax, eax
0x140022a4e  jnz     short loc_140022A69
0x140022a50  call    cs:__imp_GetLastError
0x140022a56  test    eax, eax
0x140022a58  jle     short loc_140022A62
0x140022a5a  movzx   eax, ax
0x140022a5d  or      eax, 80070000h
0x140022a62  mov     esi, eax
0x140022a64  jmp     loc_140022C8A
0x140022a69  mov     rdx, cs:?g_sdWorld@@3PEAU_SECURITY_DESCRIPTOR@@EA; Src
0x140022a70  mov     eax, cs:?g_cbWorldSD@@3KA; ulong g_cbWorldSD
0x140022a76  cmp     eax, r15d
0x140022a79  jbe     short loc_140022A85
0x140022a7b  mov     esi, 8007007Ah
0x140022a80  jmp     loc_140022C8A
0x140022a85  mov     r8, rax; Size
0x140022a88  mov     rcx, r14; void *
0x140022a8b  call    memcpy_0
0x140022a90  mov     eax, cs:?g_cbWorldSD@@3KA; ulong g_cbWorldSD
0x140022a96  jmp     loc_14002292B
0x140022a9b  mov     r8, [rsp+598h+var_4C0]; struct _ACL *
0x140022aa3  lea     rcx, [rsp+598h+pAbsoluteSecurityDescriptor]; this
0x140022aab  call    ?SetDacl@CSecurityDescriptor@SecUtil@@QEAAXHPEAU_ACL@@H@Z; SecUtil::CSecurityDescriptor::SetDacl(int,_ACL *,int)
0x140022ab0  nop
0x140022ab1  lea     rcx, [rsp+598h+Sid]; this
0x140022ab6  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x140022abb  lea     rax, aS1153102418225; "S-1-15-3-1024-1822509804-4202500280-131"...
0x140022ac2  mov     [rsp+598h+StringSid], rax
0x140022aca  lea     rax, aS1153102472474; "S-1-15-3-1024-724741592-1210917904-4899"...
0x140022ad1  mov     [rsp+598h+var_4A0], rax
0x140022ad9  lea     rax, aS1153128907917; "S-1-15-3-128907917-1049808183-377272092"...
0x140022ae0  mov     [rsp+598h+var_498], rax
0x140022ae8  lea     rax, aS1153186189776; "S-1-15-3-1861897761-1695161497-29275426"...
0x140022aef  mov     [rsp+598h+var_490], rax
0x140022af7  mov     ebx, edi
0x140022af9  movsxd  rcx, ebx
0x140022afc  cmp     rcx, 4
0x140022b00  jnb     loc_140022B9F
0x140022b06  mov     [rsp+598h+Sid], rdi
0x140022b0b  lea     rdx, [rsp+598h+Sid]; Sid
0x140022b10  mov     rcx, [rsp+rcx*8+598h+StringSid]; StringSid
0x140022b18  call    cs:__imp_ConvertStringSidToSidW
0x140022b1e  mov     rcx, [rsp+598h]; this
0x140022b26  test    eax, eax
0x140022b28  jnz     short loc_140022B3B
0x140022b2a  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140022b31  mov     edx, 894h; void *
0x140022b36  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140022b3b  mov     rax, [rsp+598h+Sid]
0x140022b40  mov     [rsp+598h+var_530], rax
0x140022b45  mov     [rsp+598h+var_568], dil
0x140022b4a  mov     [rsp+598h+var_558], 1F0081h
0x140022b52  lea     rax, [rsp+598h+var_568]
0x140022b57  mov     [rsp+598h+var_570], rax
0x140022b5c  lea     rax, [rsp+598h+var_558]
0x140022b61  mov     [rsp+598h+var_578], rax
0x140022b66  lea     r9, [rsp+598h+var_530]
0x140022b6b  lea     rcx, [rsp+598h+var_4C0]
0x140022b73  call    ?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z; SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)
0x140022b78  mov     r8, [rsp+598h+var_4C0]; struct _ACL *
0x140022b80  lea     rcx, [rsp+598h+pAbsoluteSecurityDescriptor]; this
0x140022b88  call    ?SetDacl@CSecurityDescriptor@SecUtil@@QEAAXHPEAU_ACL@@H@Z; SecUtil::CSecurityDescriptor::SetDacl(int,_ACL *,int)
0x140022b8d  nop
0x140022b8e  lea     rcx, [rsp+598h+Sid]
0x140022b93  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140022b98  inc     ebx
0x140022b9a  jmp     loc_140022AF9
0x140022b9f  xor     r9d, r9d; bSaclDefaulted
0x140022ba2  xor     r8d, r8d; pSacl
0x140022ba5  xor     edx, edx; bSaclPresent
0x140022ba7  lea     rcx, [rsp+598h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x140022baf  call    cs:__imp_SetSecurityDescriptorSacl
0x140022bb5  test    eax, eax
0x140022bb7  jnz     short loc_140022BF8
0x140022bb9  call    cs:__imp_GetLastError
0x140022bbf  mov     ebx, eax
0x140022bc1  mov     r9d, eax; wchar_t *
0x140022bc4  lea     r8, aUtilsecuritySe_0; "[UtilSecurity] SetSecurityDescriptorSac"...
0x140022bcb  mov     edx, 0CEh; wchar_t *
0x140022bd0  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140022bd7  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140022bdc  mov     rcx, [rsp+598h]; this
0x140022be4  mov     r9d, ebx; char *
0x140022be7  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x140022bee  mov     edx, 0CFh; void *
0x140022bf3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140022bf8  lea     r9, [rsp+598h+var_560]; unsigned int *
0x140022bfd  mov     r8d, r15d; unsigned int
0x140022c00  mov     rdx, r14; unsigned __int8 *
0x140022c03  lea     rcx, [rsp+598h+pAbsoluteSecurityDescriptor]; this
0x140022c0b  call    ?Export@CSecurityDescriptor@SecUtil@@QEAAJPEAEKPEAK@Z; SecUtil::CSecurityDescriptor::Export(uchar *,ulong,ulong *)
0x140022c10  mov     esi, eax
0x140022c12  cmp     eax, 8007007Ah
0x140022c17  jnz     short loc_140022C4B
0x140022c19  mov     ecx, [rsp+598h+var_560]; unsigned __int64
0x140022c1d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140022c22  mov     r14, rax
0x140022c25  mov     [rsp+598h+var_540], rax
0x140022c2a  lea     r9, [rsp+598h+var_560]; unsigned int *
0x140022c2f  mov     r8d, [rsp+598h+var_560]; unsigned int
0x140022c34  mov     rdx, rax; unsigned __int8 *
0x140022c37  lea     rcx, [rsp+598h+pAbsoluteSecurityDescriptor]; this
0x140022c3f  call    ?Export@CSecurityDescriptor@SecUtil@@QEAAJPEAEKPEAK@Z; SecUtil::CSecurityDescriptor::Export(uchar *,ulong,ulong *)
0x140022c44  mov     esi, eax
0x140022c46  mov     [rsp+598h+var_548], r14
0x140022c4b  lea     rcx, [rsp+598h+pAbsoluteSecurityDescriptor]; this
0x140022c53  call    ??1CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::~CSecurityDescriptor(void)
0x140022c58  nop
0x140022c59  jmp     short loc_140022C69
0x140022c5b  mov     esi, [rsp+598h+var_558]
0x140022c5f  mov     r14, [rsp+598h+var_548]
0x140022c64  mov     r12, [rsp+598h+var_528]
0x140022c69  test    esi, esi
0x140022c6b  jns     short loc_140022CA3
0x140022c6d  mov     rcx, [rsp+598h]; this
0x140022c75  mov     r9d, esi; char *
0x140022c78  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140022c7f  mov     edx, 8AEh; void *
0x140022c84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022c89  nop
0x140022c8a  lea     rcx, [rsp+598h+var_540]; this
0x140022c8f  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x140022c94  nop
0x140022c95  lea     rcx, [rsp+598h+var_538]; this
0x140022c9a  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x140022c9f  mov     eax, esi
0x140022ca1  jmp     short loc_140022D02
0x140022ca3  mov     eax, [rsp+598h+var_560]
0x140022ca7  mov     ecx, 41h ; 'A'
0x140022cac  mov     word ptr [rsp+598h+var_518], cx
0x140022cb4  mov     dword ptr [rsp+598h+var_518+8], eax
0x140022cbb  mov     qword ptr [rsp+598h+var_518+10h], r14
0x140022cc3  lea     rdx, [rsp+598h+var_478]; struct tagSTAT_CHUNK *
0x140022ccb  mov     rcx, r12; this
0x140022cce  call    ?AddChunk@CFilterSink@@QEAAJPEAUtagSTAT_CHUNK@@@Z; CFilterSink::AddChunk(tagSTAT_CHUNK *)
0x140022cd3  mov     ebx, eax
0x140022cd5  test    eax, eax
0x140022cd7  js      short loc_140022CEB
0x140022cd9  lea     rdx, [rsp+598h+var_518]; struct tagPROPVARIANT *
0x140022ce1  mov     rcx, r12; this
0x140022ce4  call    ?AddValue@CFilterSink@@QEAAJPEAUtagPROPVARIANT@@@Z; CFilterSink::AddValue(tagPROPVARIANT *)
0x140022ce9  mov     ebx, eax
0x140022ceb  lea     rcx, [rsp+598h+var_540]; this
0x140022cf0  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x140022cf5  nop
0x140022cf6  lea     rcx, [rsp+598h+var_538]; this
0x140022cfb  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x140022d00  mov     eax, ebx
0x140022d02  mov     rcx, [rsp+598h+var_38]
0x140022d0a  xor     rcx, rsp; StackCookie
0x140022d0d  call    __security_check_cookie
0x140022d12  lea     r11, [rsp+598h+var_28]
0x140022d1a  mov     rbx, [r11+40h]
  ... truncated ...
```
