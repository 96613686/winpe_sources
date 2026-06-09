# CSyncSharePartnershipManagerInternal::DiscoverServerUrl(ushort *,ushort * *,ISyncCredentialsInfo * *)

- ea: `0x180016e20`
- end: `0x18001727c`
- name: `?DiscoverServerUrl@CSyncSharePartnershipManagerInternal@@UEAAJPEAGPEAPEAGPEAPEAUISyncCredentialsInfo@@@Z`
- size: `1116`
- prototype: `int(CSyncSharePartnershipManagerInternal *__hidden this, unsigned __int16 *, unsigned __int16 **, struct ISyncCredentialsInfo **)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180007e10`
- `0x180007f1c`
- `0x180008b60`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x18001511c`
- `0x180015150`
- `0x1800151d8`
- `0x18001520c`
- `0x1800155e0`
- `0x1800162b8`
- `0x180016e20`
- `0x180019db8`
- `0x180021448`
- `0x180021508`
- `0x180023e64`
- `0x180024e18`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180017089`
- `OLEAUT32!__imp_SysFreeString` at `0x180017089`
- `OLEAUT32!__imp_SysStringLen` at `0x180016ef8`
- `OLEAUT32!__imp_SysStringLen` at `0x180016ef8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800170af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800170af`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180016f6d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180016f6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSyncSharePartnershipManagerInternal::DiscoverServerUrl(
        CSyncSharePartnershipManagerInternal *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        struct ISyncCredentialsInfo **a4)
{
  OLECHAR *v5; // rdi
  _BYTE *v7; // rax
  char v8; // al
  HRESULT v9; // eax
  const unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  unsigned __int16 *v12; // r14
  unsigned __int64 v13; // rdx
  int v14; // ecx
  signed int v15; // eax
  __int64 v16; // rax
  __int64 v17; // r8
  signed int v18; // ecx
  struct ISyncCredentialsInfo *v19; // rdx
  DWORD v20; // ebx
  DWORD dwMessageId; // [rsp+30h] [rbp-958h] BYREF
  int v23; // [rsp+34h] [rbp-954h]
  char v24; // [rsp+38h] [rbp-950h]
  const char *v25; // [rsp+40h] [rbp-948h]
  __int64 v26; // [rsp+48h] [rbp-940h]
  unsigned __int16 *v27; // [rsp+50h] [rbp-938h] BYREF
  int pExceptionObject; // [rsp+58h] [rbp-930h] BYREF
  int v29; // [rsp+5Ch] [rbp-92Ch] BYREF
  HRESULT v30; // [rsp+60h] [rbp-928h] BYREF
  int v31; // [rsp+64h] [rbp-924h] BYREF
  signed int v32; // [rsp+68h] [rbp-920h] BYREF
  signed int v33; // [rsp+6Ch] [rbp-91Ch] BYREF
  int v34; // [rsp+70h] [rbp-918h] BYREF
  unsigned __int16 *v35; // [rsp+78h] [rbp-910h] BYREF
  struct ISyncCredentialsInfo *v36; // [rsp+80h] [rbp-908h] BYREF
  struct ISyncCredentialsInfo **v37; // [rsp+88h] [rbp-900h]
  DWORD v38; // [rsp+90h] [rbp-8F8h] BYREF
  DWORD v39; // [rsp+94h] [rbp-8F4h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+98h] [rbp-8F0h] BYREF
  char v41; // [rsp+A0h] [rbp-8E8h]
  DWORD *v42; // [rsp+A8h] [rbp-8E0h] BYREF
  DWORD *v43; // [rsp+B0h] [rbp-8D8h] BYREF
  _BYTE v44[32]; // [rsp+C0h] [rbp-8C8h] BYREF
  char v45[32]; // [rsp+E0h] [rbp-8A8h] BYREF
  int v46; // [rsp+100h] [rbp-888h]
  unsigned int v47; // [rsp+104h] [rbp-884h]
  _BYTE v48[32]; // [rsp+110h] [rbp-878h] BYREF
  _BYTE v49[32]; // [rsp+130h] [rbp-858h] BYREF
  unsigned __int16 v50; // [rsp+150h] [rbp-838h] BYREF
  char v51[2046]; // [rsp+152h] [rbp-836h] BYREF

  v5 = a2;
  v27 = a2;
  v37 = a4;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 74, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( (v7[68] & 8) != 0 && v7[65] >= 6u )
  {
    v8 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v8 = 0;
LABEL_9:
  dwMessageId = 0;
  v23 = 1078;
  v24 = v8;
  v25 = "CSyncSharePartnershipManagerInternal::DiscoverServerUrl";
  v26 = 0;
  if ( a3 )
    *a3 = 0;
  if ( v37 )
    *v37 = 0;
  AuthenticationInfo::AuthenticationInfo((AuthenticationInfo *)v44);
  try
  {
    if ( !SysStringLen(v5) )
    {
      dwMessageId = -2147024809;
      HIWORD(v23) = 1086;
      pExceptionObject = -2147024809;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v23) = 1086;
    dwMessageId = 0;
    if ( !a3 )
    {
      dwMessageId = -2147024809;
      HIWORD(v23) = 1087;
      v29 = -2147024809;
      throw (long *)&v29;
    }
    LOWORD(v23) = 1087;
    v9 = CoImpersonateClient();
    dwMessageId = v9;
    if ( v9 < 0 )
    {
      HIWORD(v23) = 1089;
      v30 = v9;
      throw (long *)&v30;
    }
    LOWORD(v23) = 1089;
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
      (__int64)&lpCriticalSection,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
    CSyncStateManager::AddImpersonatingUser(*((CSyncStateManager **)this + 18), (__int64)v49);
    std::wstring::~wstring((__int64)v49);
    std::wstring::wstring((__int64)v48);
    CSyncStateManager::DiscoverServerUrl(*((_QWORD *)this + 18), v5, v48, v44);
    v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v48);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v35, v10);
    v12 = v35;
    if ( !v35 )
    {
      dwMessageId = -2147024882;
      HIWORD(v23) = 1100;
      v31 = -2147024882;
      throw (long *)&v31;
    }
    dwMessageId = 0;
    LOWORD(v23) = 1100;
    if ( (Microsoft_Windows_WorkFoldersEnableBits & 1) != 0 )
      McTemplateU0zz_EventWriteTransfer(v11, ECSHOST_EVENT_DISCOVER_SERVER, v5, v35);
    v35 = 0;
    *a3 = v12;
    SysFreeString(0);
    std::wstring::~wstring((__int64)v48);
    if ( v41 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v41 = 0;
    }
  }
  catch ( long v38 )
  {
    dwMessageId = v38;
    LODWORD(v5) = (_DWORD)v27;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v23) = 1106;
    dwMessageId = -2147024882;
    LODWORD(v5) = (_DWORD)v27;
  }
  catch ( std::exception )
  {
    HIWORD(v23) = 1106;
    dwMessageId = -2147418113;
    LODWORD(v5) = (_DWORD)v27;
  }
  catch ( const ATL::CAtlException *v42 )
  {
    HIWORD(v23) = 1106;
    dwMessageId = *v42;
    LODWORD(v5) = (_DWORD)v27;
  }
  if ( (dwMessageId & 0x80000000) != 0 )
  {
    LOBYTE(v27) = Microsoft_Windows_WorkFoldersEnableBits & 2;
    if ( (Microsoft_Windows_WorkFoldersEnableBits & 2) != 0 )
    {
      v50 = 0;
      memset_0(v51, 0, sizeof(v51));
      CEcsFunctionTracer::GetErrorText(dwMessageId, v13, &v50);
      McTemplateU0zzd_EventWriteTransfer(
        v14,
        (unsigned int)ECSHOST_EVENT_DISCOVER_SERVER_FAILED,
        (_DWORD)v5,
        (unsigned int)&v50,
        dwMessageId);
    }
  }
  if ( dwMessageId == -2134375680 )
  {
    try
    {
      v27 = 0;
      v15 = ATL::CComObject<CSyncCredentialsInfo>::CreateInstance(&v27);
      dwMessageId = v15;
      if ( v15 < 0 )
      {
        HIWORD(v23) = 1118;
        v32 = v15;
        throw (long *)&v32;
      }
      LOWORD(v23) = 1118;
      ATL::CComPtr<ISyncShareExtendedInfo>::CComPtr<ISyncShareExtendedInfo>(&v36, (__int64)v27);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
      v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44);
      v18 = CSyncCredentialsInfo::Initialize(v27, v16, v17, v47, v46);
      dwMessageId = v18;
      if ( v18 < 0 )
      {
        HIWORD(v23) = 1123;
        v33 = v18;
        throw (long *)&v33;
      }
      LOWORD(v23) = 1123;
      v19 = v36;
      v36 = 0;
      *v37 = v19;
      dwMessageId = -2134375680;
      HIWORD(v23) = 1126;
      v34 = -2134375680;
      throw (long *)&v34;
    }
    catch ( long v39 )
    {
      dwMessageId = v39;
    }
    catch ( std::bad_alloc )
    {
      HIWORD(v23) = 1128;
      dwMessageId = -2147024882;
    }
    catch ( std::exception )
    {
      HIWORD(v23) = 1128;
      dwMessageId = -2147418113;
    }
    catch ( const ATL::CAtlException *v43 )
    {
      HIWORD(v23) = 1128;
      dwMessageId = *v43;
    }
  }
  v20 = dwMessageId;
  DiscoverSyncShareResponseType::~DiscoverSyncShareResponseType((DiscoverSyncShareResponseType *)v44);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&dwMessageId);
  return v20;
}

```

## disassembly

```asm
0x180016e20  push    rbx
0x180016e22  push    rsi
0x180016e23  push    rdi
0x180016e24  push    r14
0x180016e26  sub     rsp, 968h
0x180016e2d  mov     rax, cs:__security_cookie
0x180016e34  xor     rax, rsp
0x180016e37  mov     [rsp+988h+var_38], rax
0x180016e3f  mov     rsi, r8
0x180016e42  mov     rdi, rdx
0x180016e45  mov     r14, rcx
0x180016e48  mov     [rsp+988h+var_938], rdx
0x180016e4d  mov     [rsp+988h+var_900], r9
0x180016e55  lea     rcx, WPP_GLOBAL_Control
0x180016e5c  mov     rax, cs:WPP_GLOBAL_Control
0x180016e63  cmp     rax, rcx
0x180016e66  jz      short loc_180016E90
0x180016e68  test    byte ptr [rax+44h], 8
0x180016e6c  jz      short loc_180016EA2
0x180016e6e  cmp     byte ptr [rax+41h], 6
0x180016e72  jb      short loc_180016E90
0x180016e74  mov     edx, 4Ah ; 'J'
0x180016e79  lea     r8, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids
0x180016e80  mov     rcx, [rax+38h]
0x180016e84  call    WPP_SF_
0x180016e89  mov     rax, cs:WPP_GLOBAL_Control
0x180016e90  test    byte ptr [rax+44h], 8
0x180016e94  jz      short loc_180016EA2
0x180016e96  cmp     byte ptr [rax+41h], 6
0x180016e9a  jb      short loc_180016EA2
0x180016e9c  mov     al, 1
0x180016e9e  xor     ebx, ebx
0x180016ea0  jmp     short loc_180016EA6
0x180016ea2  xor     ebx, ebx
0x180016ea4  mov     al, bl
0x180016ea6  mov     [rsp+988h+dwMessageId], ebx
0x180016eaa  mov     [rsp+988h+var_954], 436h
0x180016eb2  mov     [rsp+988h+var_950], al
0x180016eb6  lea     rax, aCsyncsharepart_54; "CSyncSharePartnershipManagerInternal::D"...
0x180016ebd  mov     [rsp+988h+var_948], rax
0x180016ec2  mov     [rsp+988h+var_940], rbx
0x180016ec7  test    rsi, rsi
0x180016eca  jz      short loc_180016ECF
0x180016ecc  mov     [rsi], rbx
0x180016ecf  mov     rax, [rsp+988h+var_900]
0x180016ed7  test    rax, rax
0x180016eda  jz      short loc_180016EDF
0x180016edc  mov     [rax], rbx
0x180016edf  lea     rcx, [rsp+988h+var_8C8]; this
0x180016ee7  call    ??0AuthenticationInfo@@QEAA@XZ; AuthenticationInfo::AuthenticationInfo(void)
0x180016eec  nop
0x180016eed  mov     eax, [rsp+988h+dwMessageId]
0x180016ef1  mov     [rsp+988h+dwMessageId], eax
0x180016ef5  mov     rcx, rdi; pbstr
0x180016ef8  call    cs:__imp_SysStringLen
0x180016efe  mov     ecx, 43Eh
0x180016f03  test    eax, eax
0x180016f05  jnz     short loc_180016F2A
0x180016f07  mov     eax, 80070057h
0x180016f0c  mov     [rsp+988h+dwMessageId], eax
0x180016f10  mov     word ptr [rsp+988h+var_954+2], cx
0x180016f15  mov     [rsp+988h+pExceptionObject], eax
0x180016f19  lea     rdx, _TI1J; pThrowInfo
0x180016f20  lea     rcx, [rsp+988h+pExceptionObject]; pExceptionObject
0x180016f25  call    _CxxThrowException_0
0x180016f2a  mov     [rsp+988h+dwMessageId], ebx
0x180016f2e  mov     word ptr [rsp+988h+var_954], cx
0x180016f33  mov     [rsp+988h+dwMessageId], ebx
0x180016f37  mov     ecx, 43Fh
0x180016f3c  test    rsi, rsi
0x180016f3f  jnz     short loc_180016F64
0x180016f41  mov     eax, 80070057h
0x180016f46  mov     [rsp+988h+dwMessageId], eax
0x180016f4a  mov     word ptr [rsp+988h+var_954+2], cx
0x180016f4f  mov     [rsp+988h+var_92C], eax
0x180016f53  lea     rdx, _TI1J; pThrowInfo
0x180016f5a  lea     rcx, [rsp+988h+var_92C]; pExceptionObject
0x180016f5f  call    _CxxThrowException_0
0x180016f64  mov     [rsp+988h+dwMessageId], ebx
0x180016f68  mov     word ptr [rsp+988h+var_954], cx
0x180016f6d  call    cs:__imp_CoImpersonateClient
0x180016f73  mov     [rsp+988h+dwMessageId], eax
0x180016f77  mov     [rsp+988h+dwMessageId], eax
0x180016f7b  mov     ecx, 441h
0x180016f80  test    eax, eax
0x180016f82  jns     short loc_180016F9E
0x180016f84  mov     word ptr [rsp+988h+var_954+2], cx
0x180016f89  mov     [rsp+988h+var_928], eax
0x180016f8d  lea     rdx, _TI1J; pThrowInfo
0x180016f94  lea     rcx, [rsp+988h+var_928]; pExceptionObject
0x180016f99  call    _CxxThrowException_0
0x180016f9e  mov     word ptr [rsp+988h+var_954], cx
0x180016fa3  lea     rdx, [r14+0D8h]
0x180016faa  lea     rcx, [rsp+988h+lpCriticalSection]
0x180016fb2  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x180016fb7  nop
0x180016fb8  lea     rdx, [rsp+988h+var_858]
0x180016fc0  mov     rcx, [r14+90h]; this
0x180016fc7  call    ?AddImpersonatingUser@CSyncStateManager@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CSyncStateManager::AddImpersonatingUser(void)
0x180016fcc  lea     rcx, [rsp+988h+var_858]
0x180016fd4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016fd9  lea     rcx, [rsp+988h+var_878]
0x180016fe1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016fe6  nop
0x180016fe7  lea     r9, [rsp+988h+var_8C8]
0x180016fef  lea     r8, [rsp+988h+var_878]
0x180016ff7  mov     rdx, rdi
0x180016ffa  mov     rcx, [r14+90h]
0x180017001  call    ?DiscoverServerUrl@CSyncStateManager@@QEAAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUAuthenticationInfo@@@Z; CSyncStateManager::DiscoverServerUrl(ushort const *,std::wstring &,AuthenticationInfo &)
0x180017006  lea     rcx, [rsp+988h+var_878]
0x18001700e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017013  mov     rdx, rax; unsigned __int16 *
0x180017016  lea     rcx, [rsp+988h+var_910]; this
0x18001701b  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180017020  nop
0x180017021  mov     eax, [rsp+988h+dwMessageId]
0x180017025  mov     [rsp+988h+dwMessageId], eax
0x180017029  mov     r14, [rsp+988h+var_910]
0x18001702e  mov     eax, 44Ch
0x180017033  test    r14, r14
0x180017036  jnz     short loc_18001705B
0x180017038  mov     ecx, 8007000Eh
0x18001703d  mov     [rsp+988h+dwMessageId], ecx
0x180017041  mov     word ptr [rsp+988h+var_954+2], ax
0x180017046  mov     [rsp+988h+var_924], ecx
0x18001704a  lea     rdx, _TI1J; pThrowInfo
0x180017051  lea     rcx, [rsp+988h+var_924]; pExceptionObject
0x180017056  call    _CxxThrowException_0
0x18001705b  mov     [rsp+988h+dwMessageId], ebx
0x18001705f  mov     word ptr [rsp+988h+var_954], ax
0x180017064  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 1
0x18001706b  jz      short loc_18001707F
0x18001706d  mov     r9, r14
0x180017070  mov     r8, rdi
0x180017073  lea     rdx, ECSHOST_EVENT_DISCOVER_SERVER
0x18001707a  call    McTemplateU0zz_EventWriteTransfer
0x18001707f  mov     [rsp+988h+var_910], rbx
0x180017084  mov     [rsi], r14
0x180017087  xor     ecx, ecx; bstrString
0x180017089  call    cs:__imp_SysFreeString
0x18001708f  nop
0x180017090  lea     rcx, [rsp+988h+var_878]
0x180017098  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001709d  nop
0x18001709e  cmp     [rsp+988h+var_8E8], bl
0x1800170a5  jz      short loc_1800170BC
0x1800170a7  mov     rcx, [rsp+988h+lpCriticalSection]; lpCriticalSection
0x1800170af  call    cs:__imp_LeaveCriticalSection
0x1800170b5  mov     [rsp+988h+var_8E8], bl
0x1800170bc  jmp     short loc_1800170CB
0x1800170be  jmp     short loc_1800170C4
0x1800170c0  jmp     short loc_1800170C4
0x1800170c2  jmp     short $+2
0x1800170c4  mov     rdi, [rsp+988h+var_938]
0x1800170c9  xor     ebx, ebx
0x1800170cb  mov     esi, [rsp+988h+dwMessageId]
0x1800170cf  test    esi, esi
0x1800170d1  jns     short loc_180017128
0x1800170d3  mov     al, byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits
0x1800170d9  and     al, 2
0x1800170db  mov     byte ptr [rsp+988h+var_938], al
0x1800170df  jz      short loc_180017128
0x1800170e1  mov     [rsp+988h+var_838], bx
0x1800170e9  xor     edx, edx; Val
0x1800170eb  mov     r8d, 7FEh; Size
0x1800170f1  lea     rcx, [rsp+988h+var_836]; void *
0x1800170f9  call    memset_0
0x1800170fe  lea     r8, [rsp+988h+var_838]; unsigned __int16 *
0x180017106  mov     ecx, esi; dwMessageId
0x180017108  call    ?GetErrorText@CEcsFunctionTracer@@SAXJ_KPEAG@Z; CEcsFunctionTracer::GetErrorText(long,unsigned __int64,ushort *)
0x18001710d  mov     [rsp+988h+var_968], esi
0x180017111  lea     r9, [rsp+988h+var_838]
0x180017119  mov     r8, rdi
0x18001711c  lea     rdx, ECSHOST_EVENT_DISCOVER_SERVER_FAILED
0x180017123  call    McTemplateU0zzd_EventWriteTransfer
0x180017128  mov     edi, 80C80300h
0x18001712d  cmp     [rsp+988h+dwMessageId], edi
0x180017131  jnz     loc_180017241
0x180017137  mov     [rsp+988h+var_938], rbx
0x18001713c  lea     rcx, [rsp+988h+var_938]
0x180017141  call    ?CreateInstance@?$CComObject@VCSyncCredentialsInfo@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSyncCredentialsInfo>::CreateInstance(ATL::CComObject<CSyncCredentialsInfo> * *)
0x180017146  mov     [rsp+988h+dwMessageId], eax
0x18001714a  mov     [rsp+988h+dwMessageId], eax
0x18001714e  mov     ecx, 45Eh
0x180017153  test    eax, eax
0x180017155  jns     short loc_180017171
0x180017157  mov     word ptr [rsp+988h+var_954+2], cx
0x18001715c  mov     [rsp+988h+var_920], eax
0x180017160  lea     rdx, _TI1J; pThrowInfo
0x180017167  lea     rcx, [rsp+988h+var_920]; pExceptionObject
0x18001716c  call    _CxxThrowException_0
0x180017171  mov     word ptr [rsp+988h+var_954], cx
0x180017176  mov     rdx, [rsp+988h+var_938]
0x18001717b  lea     rcx, [rsp+988h+var_908]
0x180017183  call    ??0?$CComPtr@UISyncShareExtendedInfo@@@ATL@@QEAA@PEAUISyncShareExtendedInfo@@@Z; ATL::CComPtr<ISyncShareExtendedInfo>::CComPtr<ISyncShareExtendedInfo>(ISyncShareExtendedInfo *)
0x180017188  nop
0x180017189  lea     rcx, [rsp+988h+var_8A8]
0x180017191  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017196  mov     r8, rax
0x180017199  lea     rcx, [rsp+988h+var_8C8]
0x1800171a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800171a6  mov     edx, [rsp+988h+var_888]
0x1800171ad  mov     [rsp+988h+var_968], edx
0x1800171b1  mov     r9d, [rsp+988h+var_884]
0x1800171b9  mov     rdx, rax
0x1800171bc  mov     rcx, [rsp+988h+var_938]
0x1800171c1  call    ?Initialize@CSyncCredentialsInfo@@QEAAJPEBG0KW4SYNCSHAREPARTNERSHIP_AUTHENTICATION_METHOD@@@Z; CSyncCredentialsInfo::Initialize(ushort const *,ushort const *,ulong,SYNCSHAREPARTNERSHIP_AUTHENTICATION_METHOD)
0x1800171c6  mov     ecx, eax
0x1800171c8  mov     [rsp+988h+dwMessageId], eax
0x1800171cc  mov     [rsp+988h+dwMessageId], eax
0x1800171d0  mov     eax, 463h
0x1800171d5  test    ecx, ecx
0x1800171d7  jns     short loc_1800171F3
0x1800171d9  mov     word ptr [rsp+988h+var_954+2], ax
0x1800171de  mov     [rsp+988h+var_91C], ecx
0x1800171e2  lea     rdx, _TI1J; pThrowInfo
0x1800171e9  lea     rcx, [rsp+988h+var_91C]; pExceptionObject
0x1800171ee  call    _CxxThrowException_0
0x1800171f3  mov     word ptr [rsp+988h+var_954], ax
0x1800171f8  mov     rdx, [rsp+988h+var_908]
0x180017200  mov     [rsp+988h+var_908], rbx
0x180017208  mov     rax, [rsp+988h+var_900]
0x180017210  mov     [rax], rdx
0x180017213  mov     [rsp+988h+dwMessageId], ecx
0x180017217  mov     [rsp+988h+dwMessageId], edi
0x18001721b  mov     eax, 466h
0x180017220  mov     word ptr [rsp+988h+var_954+2], ax
0x180017225  mov     [rsp+988h+var_918], edi
0x180017229  lea     rdx, _TI1J; pThrowInfo
0x180017230  lea     rcx, [rsp+988h+var_918]; pExceptionObject
0x180017235  call    _CxxThrowException_0
0x18001723b  jmp     short loc_180017241
0x18001723d  jmp     short loc_180017241
0x18001723f  jmp     short $+2
0x180017241  mov     ebx, [rsp+988h+dwMessageId]
0x180017245  lea     rcx, [rsp+988h+var_8C8]; this
0x18001724d  call    ??1DiscoverSyncShareResponseType@@QEAA@XZ; DiscoverSyncShareResponseType::~DiscoverSyncShareResponseType(void)
0x180017252  nop
0x180017253  lea     rcx, [rsp+988h+dwMessageId]; this
0x180017258  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18001725d  mov     eax, ebx
0x18001725f  mov     rcx, [rsp+988h+var_38]
0x180017267  xor     rcx, rsp; StackCookie
0x18001726a  call    __security_check_cookie
0x18001726f  add     rsp, 968h
0x180017276  pop     r14
0x180017278  pop     rdi
0x180017279  pop     rsi
0x18001727a  pop     rbx
0x18001727b  retn
```
