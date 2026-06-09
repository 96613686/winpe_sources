# CLocationEventHelper::CreateLocationEvent(ATL::CSid const &,ATL::CSid const &,bool,ATL::CComBSTR &,void * *)

- ea: `0x18001733c`
- end: `0x1800178d0`
- name: `?CreateLocationEvent@CLocationEventHelper@@SAJAEBVCSid@ATL@@0_NAEAVCComBSTR@3@PEAPEAX@Z`
- size: `1428`
- prototype: `__int64 __fastcall(const struct ATL::CSid *, const struct ATL::CSid *, unsigned __int8, BSTR *, void **)`
- caller_count: `4`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800170b8`
- `0x1800d9600`
- `0x1800f93ec`
- `0x180108630`

## callees

- `0x180016e8c`
- `0x18001733c`
- `0x1800178e0`
- `0x180017a6c`
- `0x180017b00`
- `0x180017bac`
- `0x180018228`
- `0x180018308`
- `0x1800187c0`
- `0x180018e30`
- `0x18001e170`
- `0x18001e4dc`
- `0x18001e838`
- `0x18001eb88`
- `0x18001efe0`
- `0x18001f09c`
- `0x18001f334`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800bf724`
- `0x18015e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001764d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001771c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800177a8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001764d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001771c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800177a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800175e4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800175e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175ed`
- `OLEAUT32!__imp_SysAllocString` at `0x180017480`
- `OLEAUT32!__imp_SysAllocString` at `0x1800174ad`
- `OLEAUT32!__imp_SysAllocString` at `0x180017480`
- `OLEAUT32!__imp_SysAllocString` at `0x1800174ad`
- `OLEAUT32!__imp_SysFreeString` at `0x180017388`
- `OLEAUT32!__imp_SysFreeString` at `0x180017473`
- `OLEAUT32!__imp_SysFreeString` at `0x1800174eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800174fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180017686`
- `OLEAUT32!__imp_SysFreeString` at `0x180017755`
- `OLEAUT32!__imp_SysFreeString` at `0x1800177e0`
- `OLEAUT32!__imp_SysFreeString` at `0x180017388`
- `OLEAUT32!__imp_SysFreeString` at `0x180017473`
- `OLEAUT32!__imp_SysFreeString` at `0x1800174eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800174fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180017686`
- `OLEAUT32!__imp_SysFreeString` at `0x180017755`
- `OLEAUT32!__imp_SysFreeString` at `0x1800177e0`
- `OLEAUT32!__imp_SysStringLen` at `0x1800174c2`
- `OLEAUT32!__imp_SysStringLen` at `0x1800174c2`
- `OLEAUT32!__imp_VarBstrCat` at `0x1800174dc`
- `OLEAUT32!__imp_VarBstrCat` at `0x1800174dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001789e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001789e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017576`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017853`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017576`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017853`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180017461`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180017461`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800174a3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800174a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLocationEventHelper::CreateLocationEvent(
        const struct ATL::CSid *a1,
        const struct ATL::CSid *a2,
        unsigned __int8 a3,
        BSTR *a4,
        void **a5)
{
  DWORD v6; // r13d
  HRESULT v9; // edi
  HRESULT v10; // ebx
  OLECHAR *v11; // rbx
  OLECHAR *v12; // rax
  OLECHAR *v13; // rsi
  bool v14; // r8
  unsigned int v15; // r8d
  unsigned __int8 v16; // r9
  unsigned int v17; // r8d
  unsigned __int8 v18; // r9
  bool v19; // r8
  HANDLE v20; // rdi
  signed int LastError; // eax
  unsigned int v23; // r8d
  unsigned __int8 v24; // r9
  BSTR v25; // [rsp+20h] [rbp-E0h] BYREF
  void **v26; // [rsp+28h] [rbp-D8h]
  BSTR pbstrResult; // [rsp+30h] [rbp-D0h] BYREF
  struct _SID pSid1; // [rsp+38h] [rbp-C8h] BYREF
  struct _SECURITY_DESCRIPTOR *v29[2]; // [rsp+48h] [rbp-B8h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+58h] [rbp-A8h] BYREF
  void **v31; // [rsp+70h] [rbp-90h] BYREF
  void *v32; // [rsp+78h] [rbp-88h]
  void *Block[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int128 v35; // [rsp+98h] [rbp-68h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  void **v38; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+D0h] [rbp-30h]
  GUID pguid; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v42[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE pSid2[120]; // [rsp+F8h] [rbp-8h] BYREF
  OLECHAR sz[64]; // [rsp+170h] [rbp+70h] BYREF

  v6 = a3;
  v26 = a5;
  SysFreeString(*a4);
  v9 = 0;
  *a4 = 0;
  *a5 = 0;
  pguid = 0;
  v38 = &ATL::CAccessToken::`vftable';
  v39 = 0;
  v40 = 0;
  memset_0(v42, 0, 0x78u);
  ATL::CSid::CSid((ATL::CSid *)v42);
  v29[0] = (struct _SECURITY_DESCRIPTOR *)&ATL::CSecurityDesc::`vftable';
  v29[1] = 0;
  Block[1] = 0;
  v34 = 0x200000000LL;
  Block[0] = &ATL::CDacl::`vftable';
  v35 = 0;
  v36 = 0;
  v37 = 0;
  *(_DWORD *)&pSid1.Revision = 257;
  *(_DWORD *)&pSid1.IdentifierAuthority.Value[2] = 83886080;
  pSid1.SubAuthority[0] = 18;
  v31 = &ATL::CSecurityDesc::`vftable';
  v32 = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v10 = CoCreateGuid(&pguid);
  if ( v10 < 0 )
  {
    v31 = &ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v31);
    Block[0] = &ATL::CDacl::`vftable';
    ATL::CDacl::RemoveAllAces((ATL::CDacl *)Block);
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(&v35);
    Block[0] = &ATL::CAcl::`vftable';
    free(Block[1]);
    v29[0] = (struct _SECURITY_DESCRIPTOR *)&ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)v29);
    ATL::CSid::~CSid((ATL::CSid *)v42);
    v38 = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&v38);
    SysFreeString(0);
    return (unsigned int)v10;
  }
  else
  {
    SysFreeString(0);
    v11 = SysAllocString(L"Global\\");
    v25 = v11;
    if ( !v11 )
      ATL::AtlThrowImpl(-2147024882);
    StringFromGUID2(&pguid, sz, 64);
    v12 = SysAllocString(sz);
    v13 = v12;
    if ( !v12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( SysStringLen(v12) )
    {
      pbstrResult = 0;
      v9 = VarBstrCat(v11, v13, &pbstrResult);
      if ( v9 >= 0 )
      {
        SysFreeString(v11);
        v11 = pbstrResult;
        v25 = pbstrResult;
      }
    }
    SysFreeString(v13);
    if ( v9 < 0 )
      goto LABEL_21;
    if ( !ATL::CAccessToken::GetEffectiveToken((ATL::CAccessToken *)&v38, 8u) )
    {
      v9 = -2147467259;
LABEL_21:
      v31 = &ATL::CSecurityDesc::`vftable';
      ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v31);
      Block[0] = &ATL::CDacl::`vftable';
      ATL::CDacl::RemoveAllAces((ATL::CDacl *)Block);
      ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(&v35);
      Block[0] = &ATL::CAcl::`vftable';
      free(Block[1]);
LABEL_22:
      v29[0] = (struct _SECURITY_DESCRIPTOR *)&ATL::CSecurityDesc::`vftable';
      ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)v29);
      ATL::CSid::~CSid((ATL::CSid *)v42);
      v38 = &ATL::CAccessToken::`vftable';
      ATL::CAccessToken::Clear((ATL::CAccessToken *)&v38);
      SysFreeString(v11);
      return (unsigned int)v9;
    }
    if ( !(unsigned __int8)ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(&v38, v42) )
    {
      v31 = &ATL::CSecurityDesc::`vftable';
      ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v31);
      ATL::CDacl::~CDacl((ATL::CDacl *)Block);
      v9 = -2147467259;
      goto LABEL_22;
    }
    ATL::CSecurityDesc::SetOwner((ATL::CSecurityDesc *)v29, (const struct ATL::CSid *)v42, v14);
    if ( ATL::CSid::IsValid(a1) )
      ATL::CDacl::AddAllowedAce((ATL::CDacl *)Block, a1, v15, v16);
    if ( ATL::CSid::IsValid(a2) )
      ATL::CDacl::AddAllowedAce((ATL::CDacl *)Block, a2, v17, v18);
    if ( !EqualSid(&pSid1, pSid2) && (!ATL::CSid::IsValid(a1) || !EqualSid(&pSid1, (char *)a1 + 8)) )
    {
      memset_0(sz, 0, 0x78u);
      ATL::CSid::CSid((ATL::CSid *)sz, &pSid1);
      ATL::CDacl::AddAllowedAce((ATL::CDacl *)Block, (const struct ATL::CSid *)sz, v23, v24);
      ATL::CSid::~CSid((ATL::CSid *)sz);
    }
    ATL::CSecurityDesc::SetDacl((ATL::CSecurityDesc *)v29, (const struct ATL::CDacl *)Block, v19);
    ((void (__fastcall *)(void ***))v31[1])(&v31);
    if ( v29[1] )
      ATL::CSecurityDesc::Init((ATL::CSecurityDesc *)&v31, v29[1]);
    EventAttributes.nLength = 24;
    EventAttributes.lpSecurityDescriptor = v32;
    EventAttributes.bInheritHandle = 0;
    v20 = CreateEventExW(&EventAttributes, v11, v6, 0x1F0003u);
    LastError = GetLastError();
    if ( !v20 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v9 = LastError;
      goto LABEL_21;
    }
    if ( LastError == 183 )
    {
      CloseHandle(v20);
      v31 = &ATL::CSecurityDesc::`vftable';
      ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v31);
      ATL::CDacl::~CDacl((ATL::CDacl *)Block);
      v9 = -2147024713;
      goto LABEL_22;
    }
    *v26 = v20;
    ATL::CComBSTR::operator=(a4, &v25);
    v31 = &ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v31);
    Block[0] = &ATL::CDacl::`vftable';
    ATL::CDacl::RemoveAllAces((ATL::CDacl *)Block);
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(&v35);
    Block[0] = &ATL::CAcl::`vftable';
    free(Block[1]);
    v29[0] = (struct _SECURITY_DESCRIPTOR *)&ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)v29);
    ATL::CSid::~CSid((ATL::CSid *)v42);
    v38 = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&v38);
    SysFreeString(v11);
    return 0;
  }
}

```

## disassembly

```asm
0x18001733c  mov     [rsp-8+arg_10], rbx
0x180017341  push    rbp
0x180017342  push    rsi
0x180017343  push    rdi
0x180017344  push    r12
0x180017346  push    r13
0x180017348  push    r14
0x18001734a  push    r15
0x18001734c  lea     rbp, [rsp-100h]
0x180017354  sub     rsp, 200h
0x18001735b  mov     rax, cs:__security_cookie
0x180017362  xor     rax, rsp
0x180017365  mov     [rbp+130h+var_40], rax
0x18001736c  mov     r12, r9
0x18001736f  movzx   r13d, r8b
0x180017373  mov     r15, rdx
0x180017376  mov     r14, rcx
0x180017379  mov     rbx, [rbp+130h+arg_20]
0x180017380  mov     [rsp+230h+var_208], rbx
0x180017385  mov     rcx, [r9]; bstrString
0x180017388  call    cs:__imp_SysFreeString
0x18001738e  xor     edi, edi
0x180017390  mov     [r12], rdi
0x180017394  mov     [rbx], rdi
0x180017397  xorps   xmm0, xmm0
0x18001739a  movups  xmmword ptr [rbp+130h+pguid.Data1], xmm0
0x18001739e  movups  [rbp+130h+var_178], xmm0
0x1800173a2  movups  [rbp+130h+var_168], xmm0
0x1800173a6  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x1800173ad  mov     qword ptr [rbp+130h+var_178], rax
0x1800173b1  movdqu  [rbp+130h+var_178+8], xmm0
0x1800173b6  mov     qword ptr [rbp+130h+var_168+8], rdi
0x1800173ba  xor     edx, edx; Val
0x1800173bc  lea     r8d, [rdi+78h]; Size
0x1800173c0  lea     rcx, [rbp+130h+var_140]; void *
0x1800173c4  call    memset_0
0x1800173c9  lea     rcx, [rbp+130h+var_140]; this
0x1800173cd  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x1800173d2  nop
0x1800173d3  xorps   xmm0, xmm0
0x1800173d6  movups  xmmword ptr [rsp+230h+var_1E8], xmm0
0x1800173db  lea     rsi, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x1800173e2  mov     [rsp+230h+var_1E8], rsi
0x1800173e7  mov     [rsp+230h+var_1E8+8], rdi
0x1800173ec  xor     eax, eax
0x1800173ee  movups  xmmword ptr [rbp+130h+Block], xmm0
0x1800173f2  movups  [rbp+130h+var_1A0], xmm0
0x1800173f6  movups  [rbp+130h+var_190], xmm0
0x1800173fa  mov     [rbp+130h+var_180], rax
0x1800173fe  mov     [rbp+130h+Block+8], rdi
0x180017402  mov     byte ptr [rbp+130h+var_1A0], dil
0x180017406  mov     dword ptr [rbp+130h+var_1A0+4], 2
0x18001740d  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x180017414  mov     [rbp+130h+Block], rax
0x180017418  movdqu  [rbp+130h+var_1A0+8], xmm0
0x18001741d  mov     qword ptr [rbp+130h+var_190+8], rdi
0x180017421  mov     dword ptr [rbp+130h+var_180], edi
0x180017424  mov     [rsp+230h+pSid1], 101h
0x18001742c  mov     [rsp+230h+var_1F4], 5000000h
0x180017434  mov     [rsp+230h+var_1F0], 12h
0x18001743c  movups  xmmword ptr [rsp+230h+EventAttributes.nLength], xmm0
0x180017441  movups  xmmword ptr [rsp+230h+EventAttributes.bInheritHandle], xmm0
0x180017446  mov     [rsp+230h+var_1C0], rsi
0x18001744b  mov     [rsp+230h+var_1B8], rdi
0x180017450  mov     [rsp+230h+EventAttributes.nLength], edi
0x180017454  mov     [rsp+230h+EventAttributes.lpSecurityDescriptor], rdi
0x180017459  mov     [rsp+230h+EventAttributes.bInheritHandle], edi
0x18001745d  lea     rcx, [rbp+130h+pguid]; pguid
0x180017461  call    cs:__imp_CoCreateGuid
0x180017467  mov     ebx, eax
0x180017469  test    eax, eax
0x18001746b  js      loc_18001776C
0x180017471  xor     ecx, ecx; bstrString
0x180017473  call    cs:__imp_SysFreeString
0x180017479  lea     rcx, psz; "Global\\"
0x180017480  call    cs:__imp_SysAllocString
0x180017486  mov     rbx, rax
0x180017489  mov     [rsp+230h+var_210], rax
0x18001748e  test    rax, rax
0x180017491  jz      loc_1800177ED
0x180017497  lea     r8d, [rdi+40h]; cchMax
0x18001749b  lea     rdx, [rbp+130h+sz]; lpsz
0x18001749f  lea     rcx, [rbp+130h+pguid]; rguid
0x1800174a3  call    cs:__imp_StringFromGUID2
0x1800174a9  lea     rcx, [rbp+130h+sz]; psz
0x1800174ad  call    cs:__imp_SysAllocString
0x1800174b3  mov     rsi, rax
0x1800174b6  test    rax, rax
0x1800174b9  jz      loc_1800177F8
0x1800174bf  mov     rcx, rax; pbstr
0x1800174c2  call    cs:__imp_SysStringLen
0x1800174c8  test    eax, eax
0x1800174ca  jz      short loc_1800174FB
0x1800174cc  mov     [rsp+230h+pbstrResult], rdi
0x1800174d1  lea     r8, [rsp+230h+pbstrResult]; pbstrResult
0x1800174d6  mov     rdx, rsi; bstrRight
0x1800174d9  mov     rcx, rbx; bstrLeft
0x1800174dc  call    cs:__imp_VarBstrCat
0x1800174e2  mov     edi, eax
0x1800174e4  test    eax, eax
0x1800174e6  js      short loc_1800174FB
0x1800174e8  mov     rcx, rbx; bstrString
0x1800174eb  call    cs:__imp_SysFreeString
0x1800174f1  mov     rbx, [rsp+230h+pbstrResult]
0x1800174f6  mov     [rsp+230h+var_210], rbx
0x1800174fb  mov     rcx, rsi; bstrString
0x1800174fe  call    cs:__imp_SysFreeString
0x180017504  test    edi, edi
0x180017506  js      loc_18001760A
0x18001750c  mov     edx, 8; unsigned int
0x180017511  lea     rcx, [rbp+130h+var_178]; this
0x180017515  call    ?GetEffectiveToken@CAccessToken@ATL@@QEAA_NK@Z; ATL::CAccessToken::GetEffectiveToken(ulong)
0x18001751a  test    al, al
0x18001751c  jz      loc_180017762
0x180017522  lea     rdx, [rbp+130h+var_140]
0x180017526  lea     rcx, [rbp+130h+var_178]
0x18001752a  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x18001752f  test    al, al
0x180017531  jz      loc_180017803
0x180017537  lea     rdx, [rbp+130h+var_140]; struct ATL::CSid *
0x18001753b  lea     rcx, [rsp+230h+var_1E8]; this
0x180017540  call    ?SetOwner@CSecurityDesc@ATL@@QEAAXAEBVCSid@2@_N@Z; ATL::CSecurityDesc::SetOwner(ATL::CSid const &,bool)
0x180017545  mov     rcx, r14; this
0x180017548  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x18001754d  test    al, al
0x18001754f  jz      short loc_18001755D
0x180017551  mov     rdx, r14; struct ATL::CSid *
0x180017554  lea     rcx, [rbp+130h+Block]; this
0x180017558  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x18001755d  mov     rcx, r15; this
0x180017560  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x180017565  test    al, al
0x180017567  jnz     loc_18001782D
0x18001756d  lea     rdx, [rbp+130h+pSid2]; pSid2
0x180017571  lea     rcx, [rsp+230h+pSid1]; pSid1
0x180017576  call    cs:__imp_EqualSid
0x18001757c  test    eax, eax
0x18001757e  jz      loc_18001783E
0x180017584  lea     rdx, [rbp+130h+Block]; struct ATL::CDacl *
0x180017588  lea     rcx, [rsp+230h+var_1E8]; this
0x18001758d  call    ?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z; ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)
0x180017592  mov     rax, [rsp+230h+var_1C0]
0x180017597  lea     rcx, [rsp+230h+var_1C0]
0x18001759c  mov     rax, [rax+8]
0x1800175a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175a5  mov     rdx, [rsp+230h+var_1E8+8]; struct _SECURITY_DESCRIPTOR *
0x1800175aa  test    rdx, rdx
0x1800175ad  jz      short loc_1800175B9
0x1800175af  lea     rcx, [rsp+230h+var_1C0]; this
0x1800175b4  call    ?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z; ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)
0x1800175b9  mov     [rsp+230h+EventAttributes.nLength], 18h
0x1800175c1  mov     rax, [rsp+230h+var_1B8]
0x1800175c6  mov     [rsp+230h+EventAttributes.lpSecurityDescriptor], rax
0x1800175cb  mov     [rsp+230h+EventAttributes.bInheritHandle], 0
0x1800175d3  mov     r8d, r13d; dwFlags
0x1800175d6  mov     r9d, 1F0003h; dwDesiredAccess
0x1800175dc  mov     rdx, rbx; lpName
0x1800175df  lea     rcx, [rsp+230h+EventAttributes]; lpEventAttributes
0x1800175e4  call    cs:__imp_CreateEventExW
0x1800175ea  mov     rdi, rax
0x1800175ed  call    cs:__imp_GetLastError
0x1800175f3  test    rdi, rdi
0x1800175f6  jnz     loc_1800176B8
0x1800175fc  test    eax, eax
0x1800175fe  jle     short loc_180017608
0x180017600  movzx   eax, ax
0x180017603  or      eax, 80070000h
0x180017608  mov     edi, eax
0x18001760a  lea     rsi, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x180017611  mov     [rsp+230h+var_1C0], rsi
0x180017616  lea     rcx, [rsp+230h+var_1C0]; this
0x18001761b  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x180017620  nop
0x180017621  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x180017628  mov     [rbp+130h+Block], rax
0x18001762c  lea     rcx, [rbp+130h+Block]; this
0x180017630  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180017635  lea     rcx, [rbp+130h+var_1A0+8]
0x180017639  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x18001763e  lea     rcx, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x180017645  mov     [rbp+130h+Block], rcx
0x180017649  mov     rcx, [rbp+130h+Block+8]; Block
0x18001764d  call    cs:__imp_free
0x180017653  nop
0x180017654  mov     [rsp+230h+var_1E8], rsi
0x180017659  lea     rcx, [rsp+230h+var_1E8]; this
0x18001765e  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x180017663  nop
0x180017664  lea     rcx, [rbp+130h+var_140]; this
0x180017668  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18001766d  nop
0x18001766e  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180017675  mov     qword ptr [rbp+130h+var_178], rax
0x180017679  lea     rcx, [rbp+130h+var_178]; this
0x18001767d  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180017682  nop
0x180017683  mov     rcx, rbx; bstrString
0x180017686  call    cs:__imp_SysFreeString
0x18001768c  mov     eax, edi
0x18001768e  mov     rcx, [rbp+130h+var_40]
0x180017695  xor     rcx, rsp; StackCookie
0x180017698  call    __security_check_cookie
0x18001769d  mov     rbx, [rsp+230h+arg_10]
0x1800176a5  add     rsp, 200h
0x1800176ac  pop     r15
0x1800176ae  pop     r14
0x1800176b0  pop     r13
0x1800176b2  pop     r12
0x1800176b4  pop     rdi
0x1800176b5  pop     rsi
0x1800176b6  pop     rbp
0x1800176b7  retn
0x1800176b8  cmp     eax, 0B7h
0x1800176bd  jz      loc_18001789B
0x1800176c3  mov     rax, [rsp+230h+var_208]
0x1800176c8  mov     [rax], rdi
0x1800176cb  lea     rdx, [rsp+230h+var_210]
0x1800176d0  mov     rcx, r12
0x1800176d3  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x1800176d8  nop
0x1800176d9  lea     rsi, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x1800176e0  mov     [rsp+230h+var_1C0], rsi
0x1800176e5  lea     rcx, [rsp+230h+var_1C0]; this
0x1800176ea  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x1800176ef  nop
0x1800176f0  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x1800176f7  mov     [rbp+130h+Block], rax
0x1800176fb  lea     rcx, [rbp+130h+Block]; this
0x1800176ff  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180017704  lea     rcx, [rbp+130h+var_1A0+8]
0x180017708  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x18001770d  lea     rcx, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x180017714  mov     [rbp+130h+Block], rcx
0x180017718  mov     rcx, [rbp+130h+Block+8]; Block
0x18001771c  call    cs:__imp_free
0x180017722  nop
0x180017723  mov     [rsp+230h+var_1E8], rsi
0x180017728  lea     rcx, [rsp+230h+var_1E8]; this
0x18001772d  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x180017732  nop
0x180017733  lea     rcx, [rbp+130h+var_140]; this
0x180017737  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18001773c  nop
0x18001773d  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180017744  mov     qword ptr [rbp+130h+var_178], rax
0x180017748  lea     rcx, [rbp+130h+var_178]; this
0x18001774c  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180017751  nop
0x180017752  mov     rcx, rbx; bstrString
0x180017755  call    cs:__imp_SysFreeString
0x18001775b  xor     eax, eax
0x18001775d  jmp     loc_18001768E
0x180017762  mov     edi, 80004005h
0x180017767  jmp     loc_18001760A
0x18001776c  mov     [rsp+230h+var_1C0], rsi
0x180017771  lea     rcx, [rsp+230h+var_1C0]; this
0x180017776  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x18001777b  nop
0x18001777c  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x180017783  mov     [rbp+130h+Block], rax
0x180017787  lea     rcx, [rbp+130h+Block]; this
0x18001778b  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180017790  lea     rcx, [rbp+130h+var_1A0+8]
0x180017794  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x180017799  lea     rcx, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x1800177a0  mov     [rbp+130h+Block], rcx
0x1800177a4  mov     rcx, [rbp+130h+Block+8]; Block
0x1800177a8  call    cs:__imp_free
0x1800177ae  nop
0x1800177af  mov     [rsp+230h+var_1E8], rsi
0x1800177b4  lea     rcx, [rsp+230h+var_1E8]; this
0x1800177b9  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x1800177be  nop
0x1800177bf  lea     rcx, [rbp+130h+var_140]; this
0x1800177c3  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800177c8  nop
0x1800177c9  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x1800177d0  mov     qword ptr [rbp+130h+var_178], rax
0x1800177d4  lea     rcx, [rbp+130h+var_178]; this
0x1800177d8  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x1800177dd  nop
0x1800177de  xor     ecx, ecx; bstrString
0x1800177e0  call    cs:__imp_SysFreeString
0x1800177e6  mov     eax, ebx
0x1800177e8  jmp     loc_18001768E
0x1800177ed  mov     ecx, 8007000Eh; int
0x1800177f2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800177f8  mov     ecx, 8007000Eh; int
0x1800177fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180017803  lea     rsi, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x18001780a  mov     [rsp+230h+var_1C0], rsi
0x18001780f  lea     rcx, [rsp+230h+var_1C0]; this
0x180017814  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x180017819  nop
0x18001781a  lea     rcx, [rbp+130h+Block]; this
0x18001781e  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x180017823  mov     edi, 80004005h
0x180017828  jmp     loc_180017654
0x18001782d  mov     rdx, r15; struct ATL::CSid *
0x180017830  lea     rcx, [rbp+130h+Block]; this
  ... truncated ...
```
