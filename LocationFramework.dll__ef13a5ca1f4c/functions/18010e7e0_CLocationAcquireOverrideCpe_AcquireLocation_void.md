# CLocationAcquireOverrideCpe::AcquireLocation(void)

- ea: `0x18010e7e0`
- end: `0x18010eba7`
- name: `?AcquireLocation@CLocationAcquireOverrideCpe@@EEAAJXZ`
- size: `967`
- prototype: `__int64 __fastcall(CLocationAcquireOverrideCpe *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006b5c`
- `0x180012398`
- `0x18001be08`
- `0x180020504`
- `0x180020994`
- `0x18002ae4c`
- `0x180053618`
- `0x180056544`
- `0x18009c310`
- `0x1800a98c0`
- `0x18010e7e0`
- `0x18010ebbc`
- `0x18010ecf4`
- `0x18010ee3c`
- `0x18015e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18010e8be`
- `OLEAUT32!__imp_SysFreeString` at `0x18010e9dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18010eb25`
- `OLEAUT32!__imp_SysFreeString` at `0x18010eb4b`
- `OLEAUT32!__imp_SysFreeString` at `0x18010eb6d`
- `OLEAUT32!__imp_SysFreeString` at `0x18010e8be`
- `OLEAUT32!__imp_SysFreeString` at `0x18010e9dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18010eb25`
- `OLEAUT32!__imp_SysFreeString` at `0x18010eb4b`
- `OLEAUT32!__imp_SysFreeString` at `0x18010eb6d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18010eab3`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18010eab3`

## string_xrefs

- `0x18010e853`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationacquireoverridecpe.cpp`
- `0x18010e89d`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationacquireoverridecpe.cpp`
- `0x18010e9bd`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationacquireoverridecpe.cpp`
- `0x18010eb01`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationacquireoverridecpe.cpp`
- `0x18010e88d`: `pSession->get_UserContext(&userSidStr)`
- `0x18010e8fa`: `LocationSystemHelper::GetSid(std::wstring(userSidStr), m_userSid)`
- `0x18010eaee`: `LocationHelper::CreateErrorPositionInfo( HRESULT_FROM_WIN32(ERROR_NO_DATA), LOCATION_POSITIONINGENGINE_USER, &pLocationInformation)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CLocationAcquireOverrideCpe::AcquireLocation(HANDLE *this)
{
  int FirstSubscriberSession; // ebx
  struct ILocationSessionInternal *v3; // rbx
  int Sid; // esi
  const char *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rax
  unsigned int OverrideMode; // r14d
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  unsigned int v12; // eax
  DWORD v13; // ebx
  char v14; // r15
  int v15; // r9d
  int v16; // eax
  unsigned int v17; // esi
  DWORD v18; // eax
  int v19; // eax
  wil::details *v21; // [rsp+28h] [rbp-71h]
  int v22; // [rsp+30h] [rbp-69h]
  struct ILocationSessionInternal *v23; // [rsp+40h] [rbp-59h] BYREF
  int v24; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v25; // [rsp+4Ch] [rbp-4Dh] BYREF
  BSTR v26; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v27[32]; // [rsp+58h] [rbp-41h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-21h] BYREF
  struct ILocationInformation *v29; // [rsp+80h] [rbp-19h] BYREF
  int v30; // [rsp+88h] [rbp-11h] BYREF
  _OWORD v31[2]; // [rsp+90h] [rbp-9h] BYREF
  int v32; // [rsp+B0h] [rbp+17h]
  HANDLE Handles; // [rsp+B8h] [rbp+1Fh] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v23 = 0;
  FirstSubscriberSession = CLocationAcquireBase::GetFirstSubscriberSession((CLocationAcquireBase *)this, &v23);
  if ( FirstSubscriberSession < 0 )
    goto LABEL_36;
  v3 = v23;
  if ( !v23 )
  {
    FirstSubscriberSession = -2147418113;
    LODWORD(v21) = -2147418113;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationacquireoverridecpe.cpp",
      "CLocationAcquireOverrideCpe::AcquireLocation",
      "pSession",
      v21,
      v22);
LABEL_36:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    return (unsigned int)FirstSubscriberSession;
  }
  bstrString = 0;
  Sid = (*(__int64 (__fastcall **)(struct ILocationSessionInternal *, BSTR *))(*(_QWORD *)v23 + 176LL))(
          v23,
          &bstrString);
  if ( Sid < 0 )
  {
    v5 = "pSession->get_UserContext(&userSidStr)";
    v6 = 31;
LABEL_6:
    LODWORD(v21) = Sid;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationacquireoverridecpe.cpp",
      "CLocationAcquireOverrideCpe::AcquireLocation",
      v5,
      v21,
      v22);
    SysFreeString(bstrString);
    FirstSubscriberSession = Sid;
    goto LABEL_36;
  }
  std::wstring::wstring(v27, bstrString);
  Sid = LocationSystemHelper::GetSid(v7, this + 29);
  std::wstring::_Tidy_deallocate(v27);
  if ( Sid < 0 )
  {
    v5 = "LocationSystemHelper::GetSid(std::wstring(userSidStr), m_userSid)";
    v6 = 32;
    goto LABEL_6;
  }
  OverrideMode = CLocationAcquireOverrideCpe::GetOverrideMode(this);
  v30 = 0;
  (*(void (__fastcall **)(struct ILocationSessionInternal *, int *))(*(_QWORD *)v3 + 80LL))(v3, &v30);
  if ( (unsigned int)dword_1801DDEF8 > 5 )
  {
    v24 = v30;
    v26 = bstrString;
    v25 = OverrideMode;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)byte_1801B2C81,
      v9,
      v10,
      (__int64)&v25,
      (__int64)&v26,
      (__int64)&v24);
  }
  v29 = 0;
  memset(v31, 0, sizeof(v31));
  v32 = 0;
  v11 = (*(__int64 (__fastcall **)(struct ILocationSessionInternal *, _OWORD *))(*(_QWORD *)v3 + 72LL))(v3, v31);
  FirstSubscriberSession = v11;
  if ( v11 < 0 )
  {
    LODWORD(v21) = v11;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationacquireoverridecpe.cpp",
      "CLocationAcquireOverrideCpe::AcquireLocation",
      "pSession->get_LocationRequest(&subscriberRequest)",
      v21,
      v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    SysFreeString(bstrString);
    goto LABEL_36;
  }
  if ( LODWORD(v31[0]) == 2 )
  {
    v12 = (int)((double)SHIDWORD(v31[0]) / 36.0 * 1000.0);
    if ( v12 <= 0x3E8 )
      v12 = 1000;
LABEL_19:
    v13 = 10000;
    if ( v12 >= 0x2710 )
      goto LABEL_22;
    v13 = v12;
    if ( v12 > 0x3E8 )
      goto LABEL_22;
    goto LABEL_21;
  }
  if ( LODWORD(v31[0]) == 3 )
  {
    v12 = HIDWORD(v31[0]);
    goto LABEL_19;
  }
LABEL_21:
  v13 = 1000;
LABEL_22:
  Handles = this[1];
  v14 = 0;
  while ( 1 )
  {
    if ( (int)CLocationAcquireOverrideCpe::GetLocationInformation(this, OverrideMode, &v29) < 0 )
    {
LABEL_33:
      v19 = LocationHelper::CreateErrorPositionInfo(2147942632LL, 8, &v29);
      if ( v19 < 0 )
      {
        LODWORD(v21) = v19;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x5A,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationacquireoverridecpe.cpp",
          "CLocationAcquireOverrideCpe::AcquireLocation",
          "LocationHelper::CreateErrorPositionInfo( HRESULT_FROM_WIN32(ERROR_NO_DATA), LOCATION_POSITIONINGENGINE_USER, &"
          "pLocationInformation)",
          (const char *)v21,
          v22);
      }
    }
    v16 = OverrideMode == 2
        ? CLocationAcquireOverrideCpe::PostPositionToSubscribersForUser(
            (CLocationAcquireOverrideCpe *)this,
            (const struct ATL::CSid *)(this + 29),
            v29,
            v15)
        : (*((__int64 (__fastcall **)(HANDLE *, struct ILocationInformation *, _QWORD))*this + 16))(this, v29, 0);
    v17 = v16;
    if ( v16 < 0 )
      break;
    if ( v14 || LODWORD(v31[0]) == 1 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      SysFreeString(bstrString);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
      return 0;
    }
    v18 = WaitForMultipleObjects(1u, &Handles, 0, v13);
    if ( !v18 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      SysFreeString(bstrString);
      FirstSubscriberSession = 1;
      goto LABEL_36;
    }
    if ( v18 != 258 )
    {
      v14 = 1;
      goto LABEL_33;
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  SysFreeString(bstrString);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  return v17;
}

```

## disassembly

```asm
0x18010e7e0  mov     [rsp-8+arg_8], rbx
0x18010e7e5  mov     [rsp-8+arg_10], rsi
0x18010e7ea  push    rbp
0x18010e7eb  push    rdi
0x18010e7ec  push    r12
0x18010e7ee  push    r14
0x18010e7f0  push    r15
0x18010e7f2  lea     rbp, [rsp-37h]
0x18010e7f7  sub     rsp, 0D0h
0x18010e7fe  mov     rax, cs:__security_cookie
0x18010e805  xor     rax, rsp
0x18010e808  mov     [rbp+57h+var_30], rax
0x18010e80c  mov     rdi, rcx
0x18010e80f  mov     [rbp+57h+var_B0], 0
0x18010e817  lea     rdx, [rbp+57h+var_B0]; struct ILocationSessionInternal **
0x18010e81b  call    ?GetFirstSubscriberSession@CLocationAcquireBase@@QEAAJPEAPEAUILocationSessionInternal@@@Z; CLocationAcquireBase::GetFirstSubscriberSession(ILocationSessionInternal * *)
0x18010e820  mov     ebx, eax
0x18010e822  test    eax, eax
0x18010e824  js      loc_18010EB30
0x18010e82a  mov     rbx, [rbp+57h+var_B0]
0x18010e82e  test    rbx, rbx
0x18010e831  jnz     short loc_18010E869
0x18010e833  mov     rcx, [rbp+5Fh]; this
0x18010e837  mov     ebx, 8000FFFFh
0x18010e83c  mov     dword ptr [rsp+0F0h+var_C8], ebx; wil::details *
0x18010e840  lea     rax, aPsession; "pSession"
0x18010e847  mov     [rsp+0F0h+var_D0], rax; char *
0x18010e84c  lea     r9, aClocationacqui_19; "CLocationAcquireOverrideCpe::AcquireLoc"...
0x18010e853  lea     r8, aOnecoreuapDriv_35; "onecoreuap\\drivers\\mobilepc\\location"...
0x18010e85a  mov     edx, 1Bh; void *
0x18010e85f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18010e864  jmp     loc_18010EB30
0x18010e869  mov     [rbp+57h+bstrString], 0
0x18010e871  mov     rax, [rbx]
0x18010e874  lea     rdx, [rbp+57h+bstrString]
0x18010e878  mov     rcx, rbx
0x18010e87b  mov     rax, [rax+0B0h]
0x18010e882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e887  mov     esi, eax
0x18010e889  test    eax, eax
0x18010e88b  jns     short loc_18010E8CB
0x18010e88d  lea     rax, aPsessionGetUse; "pSession->get_UserContext(&userSidStr)"
0x18010e894  mov     edx, 1Fh; void *
0x18010e899  mov     dword ptr [rsp+0F0h+var_C8], esi; wil::details *
0x18010e89d  lea     r8, aOnecoreuapDriv_35; "onecoreuap\\drivers\\mobilepc\\location"...
0x18010e8a4  lea     r9, aClocationacqui_19; "CLocationAcquireOverrideCpe::AcquireLoc"...
0x18010e8ab  mov     [rsp+0F0h+var_D0], rax; char *
0x18010e8b0  mov     rcx, [rbp+5Fh]; this
0x18010e8b4  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18010e8b9  nop
0x18010e8ba  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18010e8be  call    cs:__imp_SysFreeString
0x18010e8c4  mov     ebx, esi
0x18010e8c6  jmp     loc_18010EB30
0x18010e8cb  mov     rdx, [rbp+57h+bstrString]
0x18010e8cf  lea     rcx, [rbp+57h+var_98]
0x18010e8d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010e8d8  nop
0x18010e8d9  lea     r12, [rdi+0E8h]
0x18010e8e0  mov     rdx, r12
0x18010e8e3  mov     rcx, rax
0x18010e8e6  call    ?GetSid@LocationSystemHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVCSid@ATL@@@Z; LocationSystemHelper::GetSid(std::wstring const &,ATL::CSid &)
0x18010e8eb  mov     esi, eax
0x18010e8ed  lea     rcx, [rbp+57h+var_98]
0x18010e8f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e8f6  test    esi, esi
0x18010e8f8  jns     short loc_18010E908
0x18010e8fa  lea     rax, aLocationsystem_2; "LocationSystemHelper::GetSid(std::wstri"...
0x18010e901  mov     edx, 20h ; ' '
0x18010e906  jmp     short loc_18010E899
0x18010e908  mov     rcx, rdi
0x18010e90b  call    ?GetOverrideMode@CLocationAcquireOverrideCpe@@AEAA?AW4OverrideMode@1@XZ; CLocationAcquireOverrideCpe::GetOverrideMode(void)
0x18010e910  mov     r14d, eax
0x18010e913  mov     [rbp+57h+var_68], 0
0x18010e91a  mov     rcx, [rbx]
0x18010e91d  mov     rax, [rcx+50h]
0x18010e921  lea     rdx, [rbp+57h+var_68]
0x18010e925  mov     rcx, rbx
0x18010e928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e92d  mov     ecx, cs:dword_1801DDEF8
0x18010e933  cmp     ecx, 5
0x18010e936  jbe     short loc_18010E971
0x18010e938  mov     ecx, [rbp+57h+var_68]
0x18010e93b  mov     [rbp+57h+var_A8], ecx
0x18010e93e  mov     rax, [rbp+57h+bstrString]
0x18010e942  mov     [rbp+57h+var_A0], rax
0x18010e946  mov     [rbp+57h+var_A4], r14d
0x18010e94a  lea     rax, [rbp+57h+var_A8]
0x18010e94e  mov     qword ptr [rsp+0F0h+var_C0], rax; int
0x18010e953  lea     rax, [rbp+57h+var_A0]
0x18010e957  mov     [rsp+0F0h+var_C8], rax
0x18010e95c  lea     rax, [rbp+57h+var_A4]
0x18010e960  mov     [rsp+0F0h+var_D0], rax
0x18010e965  lea     rdx, byte_1801B2C81
0x18010e96c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18010e971  mov     [rbp+57h+var_70], 0
0x18010e979  xorps   xmm0, xmm0
0x18010e97c  xor     eax, eax
0x18010e97e  movups  [rbp+57h+var_60], xmm0
0x18010e982  movups  [rbp+57h+var_50], xmm0
0x18010e986  mov     [rbp+57h+var_40], eax
0x18010e989  mov     rax, [rbx]
0x18010e98c  lea     rdx, [rbp+57h+var_60]
0x18010e990  mov     rcx, rbx
0x18010e993  mov     rax, [rax+48h]
0x18010e997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e99c  mov     ebx, eax
0x18010e99e  test    eax, eax
0x18010e9a0  jns     short loc_18010E9E8
0x18010e9a2  mov     rcx, [rbp+5Fh]; this
0x18010e9a6  mov     dword ptr [rsp+0F0h+var_C8], eax; wil::details *
0x18010e9aa  lea     rax, aPsessionGetLoc; "pSession->get_LocationRequest(&subscrib"...
0x18010e9b1  mov     [rsp+0F0h+var_D0], rax; char *
0x18010e9b6  lea     r9, aClocationacqui_19; "CLocationAcquireOverrideCpe::AcquireLoc"...
0x18010e9bd  lea     r8, aOnecoreuapDriv_35; "onecoreuap\\drivers\\mobilepc\\location"...
0x18010e9c4  mov     edx, 37h ; '7'; void *
0x18010e9c9  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18010e9ce  nop
0x18010e9cf  lea     rcx, [rbp+57h+var_70]
0x18010e9d3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18010e9d8  nop
0x18010e9d9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18010e9dd  call    cs:__imp_SysFreeString
0x18010e9e3  jmp     loc_18010EB30
0x18010e9e8  mov     ecx, 3E8h
0x18010e9ed  cmp     dword ptr [rbp+57h+var_60], 2
0x18010e9f1  jnz     short loc_18010EA1A
0x18010e9f3  mov     eax, dword ptr [rbp+57h+var_60+0Ch]
0x18010e9f6  xorps   xmm0, xmm0
0x18010e9f9  cvtsi2sd xmm0, rax
0x18010e9fe  divsd   xmm0, cs:__real@4042000000000000
0x18010ea06  mulsd   xmm0, cs:__real@408f400000000000
0x18010ea0e  cvttsd2si rax, xmm0
0x18010ea13  cmp     eax, ecx
0x18010ea15  cmovbe  eax, ecx
0x18010ea18  jmp     short loc_18010EA23
0x18010ea1a  cmp     dword ptr [rbp+57h+var_60], 3
0x18010ea1e  jnz     short loc_18010EA32
0x18010ea20  mov     eax, dword ptr [rbp+57h+var_60+0Ch]
0x18010ea23  mov     ebx, 2710h
0x18010ea28  cmp     eax, ebx
0x18010ea2a  jnb     short loc_18010EA34
0x18010ea2c  mov     ebx, eax
0x18010ea2e  cmp     eax, ecx
0x18010ea30  ja      short loc_18010EA34
0x18010ea32  mov     ebx, ecx
0x18010ea34  mov     rax, [rdi+8]
0x18010ea38  mov     [rbp+57h+Handles], rax
0x18010ea3c  xor     r15b, r15b
0x18010ea3f  lea     r8, [rbp+57h+var_70]
0x18010ea43  mov     edx, r14d
0x18010ea46  mov     rcx, rdi
0x18010ea49  call    ?GetLocationInformation@CLocationAcquireOverrideCpe@@AEAAJW4OverrideMode@1@PEAPEAUILocationInformation@@@Z; CLocationAcquireOverrideCpe::GetLocationInformation(CLocationAcquireOverrideCpe::OverrideMode,ILocationInformation * *)
0x18010ea4e  test    eax, eax
0x18010ea50  js      short loc_18010EACB
0x18010ea52  mov     rdx, [rbp+57h+var_70]
0x18010ea56  mov     ecx, r14d
0x18010ea59  sub     ecx, 1
0x18010ea5c  jz      short loc_18010EA73
0x18010ea5e  cmp     ecx, 1
0x18010ea61  jnz     short loc_18010EA73
0x18010ea63  mov     r8, rdx; struct ILocationInformation *
0x18010ea66  mov     rdx, r12; struct ATL::CSid *
0x18010ea69  mov     rcx, rdi; this
0x18010ea6c  call    ?PostPositionToSubscribersForUser@CLocationAcquireOverrideCpe@@AEAAJAEBVCSid@ATL@@PEAUILocationInformation@@H@Z; CLocationAcquireOverrideCpe::PostPositionToSubscribersForUser(ATL::CSid const &,ILocationInformation *,int)
0x18010ea71  jmp     short loc_18010EA88
0x18010ea73  mov     rax, [rdi]
0x18010ea76  xor     r8d, r8d
0x18010ea79  mov     rcx, rdi
0x18010ea7c  mov     rax, [rax+80h]
0x18010ea83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ea88  mov     esi, eax
0x18010ea8a  test    eax, eax
0x18010ea8c  js      loc_18010EB5F
0x18010ea92  test    r15b, r15b
0x18010ea95  jnz     loc_18010EB3D
0x18010ea9b  cmp     dword ptr [rbp+57h+var_60], 1
0x18010ea9f  jz      loc_18010EB3D
0x18010eaa5  mov     r9d, ebx; dwMilliseconds
0x18010eaa8  xor     r8d, r8d; bWaitAll
0x18010eaab  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18010eaaf  lea     ecx, [r8+1]; nCount
0x18010eab3  call    cs:__imp_WaitForMultipleObjects
0x18010eab9  test    eax, eax
0x18010eabb  jz      short loc_18010EB17
0x18010eabd  cmp     eax, 102h
0x18010eac2  jz      loc_18010EA3F
0x18010eac8  mov     r15b, 1
0x18010eacb  lea     r8, [rbp+57h+var_70]
0x18010eacf  mov     edx, 8
0x18010ead4  mov     ecx, 800700E8h
0x18010ead9  call    ?CreateErrorPositionInfo@LocationHelper@@SAJJW4LOCATION_POSITIONINGENGINE@@PEAPEAUILocationInformation@@@Z; LocationHelper::CreateErrorPositionInfo(long,LOCATION_POSITIONINGENGINE,ILocationInformation * *)
0x18010eade  mov     rcx, [rbp+5Fh]; this
0x18010eae2  test    eax, eax
0x18010eae4  jns     loc_18010EA52
0x18010eaea  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18010eaee  lea     rax, aLocationhelper_3; "LocationHelper::CreateErrorPositionInfo"...
0x18010eaf5  mov     [rsp+0F0h+var_D0], rax; char *
0x18010eafa  lea     r9, aClocationacqui_19; "CLocationAcquireOverrideCpe::AcquireLoc"...
0x18010eb01  lea     r8, aOnecoreuapDriv_35; "onecoreuap\\drivers\\mobilepc\\location"...
0x18010eb08  mov     edx, 5Ah ; 'Z'; void *
0x18010eb0d  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18010eb12  jmp     loc_18010EA52
0x18010eb17  lea     rcx, [rbp+57h+var_70]
0x18010eb1b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18010eb20  nop
0x18010eb21  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18010eb25  call    cs:__imp_SysFreeString
0x18010eb2b  mov     ebx, 1
0x18010eb30  lea     rcx, [rbp+57h+var_B0]
0x18010eb34  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18010eb39  mov     eax, ebx
0x18010eb3b  jmp     short loc_18010EB7F
0x18010eb3d  lea     rcx, [rbp+57h+var_70]
0x18010eb41  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18010eb46  nop
0x18010eb47  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18010eb4b  call    cs:__imp_SysFreeString
0x18010eb51  nop
0x18010eb52  lea     rcx, [rbp+57h+var_B0]
0x18010eb56  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18010eb5b  xor     eax, eax
0x18010eb5d  jmp     short loc_18010EB7F
0x18010eb5f  lea     rcx, [rbp+57h+var_70]
0x18010eb63  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18010eb68  nop
0x18010eb69  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18010eb6d  call    cs:__imp_SysFreeString
0x18010eb73  nop
0x18010eb74  lea     rcx, [rbp+57h+var_B0]
0x18010eb78  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18010eb7d  mov     eax, esi
0x18010eb7f  mov     rcx, [rbp+57h+var_30]
0x18010eb83  xor     rcx, rsp; StackCookie
0x18010eb86  call    __security_check_cookie
0x18010eb8b  lea     r11, [rsp+0F0h+var_20]
0x18010eb93  mov     rbx, [r11+38h]
0x18010eb97  mov     rsi, [r11+40h]
0x18010eb9b  mov     rsp, r11
0x18010eb9e  pop     r15
0x18010eba0  pop     r14
0x18010eba2  pop     r12
0x18010eba4  pop     rdi
0x18010eba5  pop     rbp
0x18010eba6  retn
```
