# CSyncSharePartnershipManagerInternal::ProvisionPartnership(ISyncSharePartnershipDescriptor *)

- ea: `0x18001acf0`
- end: `0x18001b7fd`
- name: `?ProvisionPartnership@CSyncSharePartnershipManagerInternal@@UEAAJPEAUISyncSharePartnershipDescriptor@@@Z`
- size: `2829`
- prototype: `__int64 __fastcall(CSyncStateManager **this, struct ISyncSharePartnershipDescriptor *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180007e10`
- `0x180007f1c`
- `0x180008108`
- `0x180008b60`
- `0x180009158`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x18001133c`
- `0x18001520c`
- `0x18001588c`
- `0x180015904`
- `0x180015920`
- `0x18001acf0`
- `0x1800215e0`
- `0x1800217f4`
- `0x180023e64`
- `0x180024ab0`
- `0x180028fcc`
- `0x18003385c`
- `0x18013e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001b6bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b6cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b6e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b6f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7c1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b6bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b6cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b6e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b6f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7c1`
- `OLEAUT32!__imp_SysStringLen` at `0x18001aec5`
- `OLEAUT32!__imp_SysStringLen` at `0x18001afa9`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b043`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b0e0`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b224`
- `OLEAUT32!__imp_SysStringLen` at `0x18001aec5`
- `OLEAUT32!__imp_SysStringLen` at `0x18001afa9`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b043`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b0e0`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b224`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b70f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b70f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001ada5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001ada5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncSharePartnershipManagerInternal::ProvisionPartnership(
        CSyncStateManager **this,
        struct ISyncSharePartnershipDescriptor *a2)
{
  _BYTE *v4; // rax
  char v5; // al
  HRESULT v6; // eax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  char v15; // si
  __int64 DefaultSyncRootFolder; // rax
  __int64 v17; // rax
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  unsigned int v24; // edi
  int v25; // ecx
  DWORD v26; // edi
  unsigned __int64 v27; // rdx
  int v28; // ecx
  DWORD dwMessageId; // [rsp+40h] [rbp-B58h] BYREF
  int v31; // [rsp+44h] [rbp-B54h]
  char v32; // [rsp+48h] [rbp-B50h]
  const char *v33; // [rsp+50h] [rbp-B48h]
  __int64 v34; // [rsp+58h] [rbp-B40h]
  _WORD v35[2]; // [rsp+60h] [rbp-B38h] BYREF
  __int16 v36; // [rsp+64h] [rbp-B34h] BYREF
  __int16 v37; // [rsp+68h] [rbp-B30h] BYREF
  __int64 v38; // [rsp+70h] [rbp-B28h] BYREF
  BSTR v39; // [rsp+78h] [rbp-B20h] BYREF
  BSTR v40; // [rsp+80h] [rbp-B18h] BYREF
  BSTR v41; // [rsp+88h] [rbp-B10h] BYREF
  int v42; // [rsp+90h] [rbp-B08h] BYREF
  unsigned int v43; // [rsp+94h] [rbp-B04h] BYREF
  BSTR v44; // [rsp+98h] [rbp-B00h] BYREF
  BSTR pbstr; // [rsp+A0h] [rbp-AF8h] BYREF
  signed int v46; // [rsp+A8h] [rbp-AF0h] BYREF
  int v47; // [rsp+ACh] [rbp-AECh] BYREF
  signed int v48; // [rsp+B0h] [rbp-AE8h] BYREF
  int v49; // [rsp+B4h] [rbp-AE4h] BYREF
  signed int v50; // [rsp+B8h] [rbp-AE0h] BYREF
  signed int v51; // [rsp+BCh] [rbp-ADCh] BYREF
  signed int v52; // [rsp+C0h] [rbp-AD8h] BYREF
  signed int v53; // [rsp+C4h] [rbp-AD4h] BYREF
  signed int v54; // [rsp+C8h] [rbp-AD0h] BYREF
  signed int v55; // [rsp+CCh] [rbp-ACCh] BYREF
  signed int v56; // [rsp+D0h] [rbp-AC8h] BYREF
  signed int v57; // [rsp+D4h] [rbp-AC4h] BYREF
  signed int v58; // [rsp+D8h] [rbp-AC0h] BYREF
  int v59; // [rsp+DCh] [rbp-ABCh] BYREF
  HRESULT pExceptionObject; // [rsp+E0h] [rbp-AB8h] BYREF
  int v61; // [rsp+E4h] [rbp-AB4h] BYREF
  signed int v62; // [rsp+E8h] [rbp-AB0h] BYREF
  int v63; // [rsp+ECh] [rbp-AACh] BYREF
  signed int v64; // [rsp+F0h] [rbp-AA8h] BYREF
  signed int v65; // [rsp+F4h] [rbp-AA4h] BYREF
  BSTR bstrString; // [rsp+F8h] [rbp-AA0h] BYREF
  BSTR v67; // [rsp+100h] [rbp-A98h] BYREF
  int v68; // [rsp+108h] [rbp-A90h] BYREF
  __int64 v69; // [rsp+110h] [rbp-A88h] BYREF
  __int64 v70; // [rsp+118h] [rbp-A80h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+128h] [rbp-A70h] BYREF
  char v72; // [rsp+130h] [rbp-A68h]
  DWORD v73; // [rsp+138h] [rbp-A60h] BYREF
  DWORD *v74; // [rsp+140h] [rbp-A58h] BYREF
  _BYTE v75[40]; // [rsp+148h] [rbp-A50h] BYREF
  _BYTE v76[40]; // [rsp+170h] [rbp-A28h] BYREF
  _BYTE v77[96]; // [rsp+198h] [rbp-A00h] BYREF
  _BYTE v78[32]; // [rsp+1F8h] [rbp-9A0h] BYREF
  _BYTE v79[32]; // [rsp+218h] [rbp-980h] BYREF
  _BYTE v80[160]; // [rsp+238h] [rbp-960h] BYREF
  int v81; // [rsp+2D8h] [rbp-8C0h]
  bool v82; // [rsp+2ECh] [rbp-8ACh]
  unsigned int v83; // [rsp+2F0h] [rbp-8A8h]
  bool v84; // [rsp+2F8h] [rbp-8A0h]
  char v85; // [rsp+2F9h] [rbp-89Fh]
  bool v86; // [rsp+2FBh] [rbp-89Dh]
  __int64 v87; // [rsp+300h] [rbp-898h]
  __int64 v88; // [rsp+308h] [rbp-890h]
  _BYTE v89[32]; // [rsp+310h] [rbp-888h] BYREF
  _BYTE v90[32]; // [rsp+330h] [rbp-868h] BYREF
  _BYTE v91[32]; // [rsp+350h] [rbp-848h] BYREF
  unsigned __int16 v92; // [rsp+370h] [rbp-828h] BYREF
  _BYTE v93[2046]; // [rsp+372h] [rbp-826h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v5 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 61, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 8) == 0 || v4[65] < 6u )
    goto LABEL_8;
  v5 = 1;
LABEL_9:
  dwMessageId = 0;
  v31 = 598;
  v32 = v5;
  v33 = "CSyncSharePartnershipManagerInternal::ProvisionPartnership";
  v34 = 0;
  v39 = 0;
  v41 = 0;
  v40 = 0;
  try
  {
    v6 = CoImpersonateClient();
    dwMessageId = v6;
    if ( v6 < 0 )
    {
      HIWORD(v31) = 606;
      pExceptionObject = v6;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v31) = 606;
    dwMessageId = v6;
    if ( !a2 )
    {
      dwMessageId = -2147024809;
      HIWORD(v31) = 608;
      v61 = -2147024809;
      throw (long *)&v61;
    }
    dwMessageId = 0;
    LOWORD(v31) = 608;
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(&lpCriticalSection, this + 27);
    CSyncStateManager::AddImpersonatingUser(this[18], (__int64)v75);
    std::wstring::~wstring(v75);
    pbstr = 0;
    v44 = 0;
    v35[0] = 0;
    v7 = (*(__int64 (__fastcall **)(struct ISyncSharePartnershipDescriptor *, BSTR *))(*(_QWORD *)a2 + 56LL))(
           a2,
           &pbstr);
    dwMessageId = v7;
    if ( v7 < 0 )
    {
      HIWORD(v31) = 619;
      v62 = v7;
      throw (long *)&v62;
    }
    LOWORD(v31) = 619;
    dwMessageId = v7;
    if ( !SysStringLen(pbstr) )
    {
      dwMessageId = -2147024809;
      HIWORD(v31) = 620;
      v63 = -2147024809;
      throw (long *)&v63;
    }
    dwMessageId = 0;
    LOWORD(v31) = 620;
    v8 = (*(__int64 (__fastcall **)(struct ISyncSharePartnershipDescriptor *, BSTR *))(*(_QWORD *)a2 + 120LL))(a2, &v39);
    dwMessageId = v8;
    if ( v8 < 0 )
    {
      HIWORD(v31) = 622;
      v64 = v8;
      throw (long *)&v64;
    }
    LOWORD(v31) = 622;
    v9 = (*(__int64 (__fastcall **)(struct ISyncSharePartnershipDescriptor *, BSTR *))(*(_QWORD *)a2 + 72LL))(a2, &v44);
    dwMessageId = v9;
    if ( v9 < 0 )
    {
      HIWORD(v31) = 625;
      v65 = v9;
      throw (long *)&v65;
    }
    LOWORD(v31) = 625;
    dwMessageId = v9;
    if ( !SysStringLen(v44) )
    {
      dwMessageId = -2147024809;
      HIWORD(v31) = 626;
      v68 = -2147024809;
      throw (long *)&v68;
    }
    dwMessageId = 0;
    LOWORD(v31) = 626;
    v10 = (*(__int64 (__fastcall **)(struct ISyncSharePartnershipDescriptor *, BSTR *))(*(_QWORD *)a2 + 88LL))(a2, &v41);
    dwMessageId = v10;
    if ( v10 < 0 )
    {
      HIWORD(v31) = 628;
      v46 = v10;
      throw (long *)&v46;
    }
    LOWORD(v31) = 628;
    dwMessageId = v10;
    if ( !SysStringLen(v41) )
    {
      dwMessageId = -2147024809;
      HIWORD(v31) = 629;
      v47 = -2147024809;
      throw (long *)&v47;
    }
    dwMessageId = 0;
    LOWORD(v31) = 629;
    v11 = (*(__int64 (__fastcall **)(struct ISyncSharePartnershipDescriptor *, BSTR *))(*(_QWORD *)a2 + 136LL))(
            a2,
            &v40);
    dwMessageId = v11;
    if ( v11 < 0 )
    {
      HIWORD(v31) = 631;
      v48 = v11;
      throw (long *)&v48;
    }
    LOWORD(v31) = 631;
    dwMessageId = v11;
    if ( !SysStringLen(v40) )
    {
      dwMessageId = -2147024809;
      HIWORD(v31) = 632;
      v49 = -2147024809;
      throw (long *)&v49;
    }
    dwMessageId = 0;
    LOWORD(v31) = 632;
    v12 = (*(__int64 (__fastcall **)(struct ISyncSharePartnershipDescriptor *, _WORD *))(*(_QWORD *)a2 + 152LL))(
            a2,
            v35);
    dwMessageId = v12;
    if ( v12 < 0 )
    {
      HIWORD(v31) = 634;
      v50 = v12;
      throw (long *)&v50;
    }
    LOWORD(v31) = 634;
    v42 = 0;
    v13 = (*(__int64 (__fastcall **)(struct ISyncSharePartnershipDescriptor *, int *))(*(_QWORD *)a2 + 168LL))(a2, &v42);
    dwMessageId = v13;
    if ( v13 < 0 )
    {
      HIWORD(v31) = 637;
      v51 = v13;
      throw (long *)&v51;
    }
    LOWORD(v31) = 637;
    v43 = 0;
    v14 = (*(__int64 (__fastcall **)(struct ISyncSharePartnershipDescriptor *, unsigned int *))(*(_QWORD *)a2 + 200LL))(
            a2,
            &v43);
    dwMessageId = v14;
    if ( v14 < 0 )
    {
      HIWORD(v31) = 640;
      v52 = v14;
      throw (long *)&v52;
    }
    LOWORD(v31) = 640;
    v15 = 0;
    if ( !SysStringLen(v39) )
    {
      DefaultSyncRootFolder = CPartnershipStateManager::GetDefaultSyncRootFolder(v75);
      v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(DefaultSyncRootFolder);
      ATL::CComBSTR::operator=(&v39, v17);
      std::wstring::~wstring(v75);
      v15 = 1;
    }
    ClientPartnershipDescriptor::ClientPartnershipDescriptor((ClientPartnershipDescriptor *)v76);
    std::wstring::operator=(v89, pbstr);
    std::wstring::operator=(v77, v39);
    std::wstring::operator=(v90, v44);
    std::wstring::operator=(v78, v41);
    v84 = v35[0] != 0;
    std::wstring::operator=(v80, v40);
    v81 = v42;
    v85 = v15;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v67, L"WorkFolders");
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, &Format);
    v36 = 0;
    v37 = 0;
    v69 = 0;
    v70 = 0;
    v38 = 0;
    if ( (*(int (__fastcall **)(struct ISyncSharePartnershipDescriptor *, __int64 *))(*(_QWORD *)a2 + 184LL))(a2, &v38) >= 0
      && v38 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v38 + 56LL))(v38, &v67);
      dwMessageId = v18;
      if ( v18 < 0 )
      {
        HIWORD(v31) = 678;
        v53 = v18;
        throw (long *)&v53;
      }
      LOWORD(v31) = 678;
      v19 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v38 + 72LL))(v38, &bstrString);
      dwMessageId = v19;
      if ( v19 < 0 )
      {
        HIWORD(v31) = 679;
        v54 = v19;
        throw (long *)&v54;
      }
      LOWORD(v31) = 679;
      v20 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v38 + 120LL))(v38, &v36);
      dwMessageId = v20;
      if ( v20 < 0 )
      {
        HIWORD(v31) = 681;
        v55 = v20;
        throw (long *)&v55;
      }
      LOWORD(v31) = 681;
      v21 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v38 + 136LL))(v38, &v37);
      dwMessageId = v21;
      if ( v21 < 0 )
      {
        HIWORD(v31) = 682;
        v56 = v21;
        throw (long *)&v56;
      }
      LOWORD(v31) = 682;
      v22 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 88LL))(v38, &v69);
      dwMessageId = v22;
      if ( v22 < 0 )
      {
        HIWORD(v31) = 684;
        v57 = v22;
        throw (long *)&v57;
      }
      LOWORD(v31) = 684;
      v23 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 104LL))(v38, &v70);
      dwMessageId = v23;
      if ( v23 < 0 )
      {
        HIWORD(v31) = 685;
        v58 = v23;
        throw (long *)&v58;
      }
      LOWORD(v31) = 685;
    }
    std::wstring::operator=(v79, v67);
    std::wstring::operator=(v91, bstrString);
    v86 = v36 == -1;
    v87 = v69;
    v88 = v70;
    v82 = v37 == -1;
    if ( v43 )
    {
      if ( v43 != 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 62, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids, v43);
        }
        dwMessageId = -2134372349;
        HIWORD(v31) = 711;
        v59 = -2134372349;
        throw (long *)&v59;
      }
      v24 = 3;
    }
    else
    {
      v24 = 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 63, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids, v24, v43);
    }
    v83 = v24;
    CSyncStateManager::CreatePartnership(this[18], (struct ClientPartnershipDescriptor *)v76);
    if ( (Microsoft_Windows_WorkFoldersEnableBits & 1) != 0 )
      McTemplateU0zzz_EventWriteTransfer(
        v25,
        (unsigned int)ECSHOST_EVENT_PARTNERSHIP_CREATED,
        (_DWORD)v39,
        (_DWORD)v41,
        (__int64)v40);
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v38);
    SysFreeString(bstrString);
    SysFreeString(v67);
    ClientPartnershipDescriptor::~ClientPartnershipDescriptor((ClientPartnershipDescriptor *)v76);
    SysFreeString(v44);
    SysFreeString(pbstr);
    if ( v72 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v72 = 0;
    }
  }
  catch ( long v73 )
  {
    dwMessageId = v73;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v31) = 723;
    dwMessageId = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v31) = 723;
    dwMessageId = -2147418113;
  }
  catch ( const ATL::CAtlException *v74 )
  {
    HIWORD(v31) = 723;
    dwMessageId = *v74;
  }
  v6 = CoImpersonateClient();
  dwMessageId = v6;
  if ( v6 < 0 )
  {
    HIWORD(v31) = 606;
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v31) = 606;
  dwMessageId = v6;
  if ( !a2 )
  {
    dwMessageId = -2147024809;
    HIWORD(v31) = 608;
    v61 = -2147024809;
    throw (long *)&v61;
  }
  dwMessageId = 0;
}

```

## disassembly

```asm
0x18001acf0  mov     [rsp+arg_10], rbx
0x18001acf5  mov     [rsp+arg_18], rsi
0x18001acfa  push    rdi
0x18001acfb  push    r14
0x18001acfd  push    r15
0x18001acff  sub     rsp, 0B80h
0x18001ad06  mov     rax, cs:__security_cookie
0x18001ad0d  xor     rax, rsp
0x18001ad10  mov     [rsp+0B98h+var_28], rax
0x18001ad18  mov     rdi, rdx
0x18001ad1b  mov     r14, rcx
0x18001ad1e  lea     r15, WPP_GLOBAL_Control
0x18001ad25  mov     rax, cs:WPP_GLOBAL_Control
0x18001ad2c  cmp     rax, r15
0x18001ad2f  jz      short loc_18001AD59
0x18001ad31  test    byte ptr [rax+44h], 8
0x18001ad35  jz      short loc_18001AD6B
0x18001ad37  cmp     byte ptr [rax+41h], 6
0x18001ad3b  jb      short loc_18001AD59
0x18001ad3d  mov     edx, 3Dh ; '='
0x18001ad42  lea     r8, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids
0x18001ad49  mov     rcx, [rax+38h]
0x18001ad4d  call    WPP_SF_
0x18001ad52  mov     rax, cs:WPP_GLOBAL_Control
0x18001ad59  test    byte ptr [rax+44h], 8
0x18001ad5d  jz      short loc_18001AD6B
0x18001ad5f  cmp     byte ptr [rax+41h], 6
0x18001ad63  jb      short loc_18001AD6B
0x18001ad65  mov     al, 1
0x18001ad67  xor     ebx, ebx
0x18001ad69  jmp     short loc_18001AD6F
0x18001ad6b  xor     ebx, ebx
0x18001ad6d  mov     al, bl
0x18001ad6f  mov     [rsp+0B98h+dwMessageId], ebx
0x18001ad73  mov     [rsp+0B98h+var_B54], 256h
0x18001ad7b  mov     [rsp+0B98h+var_B50], al
0x18001ad7f  lea     rax, aCsyncsharepart_15; "CSyncSharePartnershipManagerInternal::P"...
0x18001ad86  mov     [rsp+0B98h+var_B48], rax
0x18001ad8b  mov     [rsp+0B98h+var_B40], rbx
0x18001ad90  mov     [rsp+0B98h+var_B20], rbx
0x18001ad95  mov     [rsp+0B98h+var_B10], rbx
0x18001ad9d  mov     [rsp+0B98h+var_B18], rbx
0x18001ada5  call    cs:__imp_CoImpersonateClient
0x18001adab  mov     [rsp+0B98h+dwMessageId], eax
0x18001adaf  mov     [rsp+0B98h+dwMessageId], eax
0x18001adb3  mov     ecx, 25Eh
0x18001adb8  test    eax, eax
0x18001adba  jns     short loc_18001ADDC
0x18001adbc  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001adc1  mov     [rsp+0B98h+pExceptionObject], eax
0x18001adc8  lea     rdx, _TI1J; pThrowInfo
0x18001adcf  lea     rcx, [rsp+0B98h+pExceptionObject]; pExceptionObject
0x18001add7  call    _CxxThrowException_0
0x18001addc  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001ade1  mov     [rsp+0B98h+dwMessageId], eax
0x18001ade5  mov     ecx, 260h
0x18001adea  test    rdi, rdi
0x18001aded  jnz     short loc_18001AE18
0x18001adef  mov     eax, 80070057h
0x18001adf4  mov     [rsp+0B98h+dwMessageId], eax
0x18001adf8  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001adfd  mov     [rsp+0B98h+var_AB4], eax
0x18001ae04  lea     rdx, _TI1J; pThrowInfo
0x18001ae0b  lea     rcx, [rsp+0B98h+var_AB4]; pExceptionObject
0x18001ae13  call    _CxxThrowException_0
0x18001ae18  mov     [rsp+0B98h+dwMessageId], ebx
0x18001ae1c  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001ae21  lea     rdx, [r14+0D8h]
0x18001ae28  lea     rcx, [rsp+0B98h+lpCriticalSection]
0x18001ae30  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x18001ae35  nop
0x18001ae36  lea     rdx, [rsp+0B98h+var_A50]
0x18001ae3e  mov     rcx, [r14+90h]; this
0x18001ae45  call    ?AddImpersonatingUser@CSyncStateManager@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CSyncStateManager::AddImpersonatingUser(void)
0x18001ae4a  lea     rcx, [rsp+0B98h+var_A50]
0x18001ae52  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ae57  mov     [rsp+0B98h+pbstr], rbx
0x18001ae5f  mov     [rsp+0B98h+var_B00], rbx
0x18001ae67  mov     [rsp+0B98h+var_B38], bx
0x18001ae6c  mov     rax, [rdi]
0x18001ae6f  lea     rdx, [rsp+0B98h+pbstr]
0x18001ae77  mov     rcx, rdi
0x18001ae7a  mov     rax, [rax+38h]
0x18001ae7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae83  mov     [rsp+0B98h+dwMessageId], eax
0x18001ae87  mov     [rsp+0B98h+dwMessageId], eax
0x18001ae8b  mov     ecx, 26Bh
0x18001ae90  test    eax, eax
0x18001ae92  jns     short loc_18001AEB4
0x18001ae94  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001ae99  mov     [rsp+0B98h+var_AB0], eax
0x18001aea0  lea     rdx, _TI1J; pThrowInfo
0x18001aea7  lea     rcx, [rsp+0B98h+var_AB0]; pExceptionObject
0x18001aeaf  call    _CxxThrowException_0
0x18001aeb4  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001aeb9  mov     [rsp+0B98h+dwMessageId], eax
0x18001aebd  mov     rcx, [rsp+0B98h+pbstr]; pbstr
0x18001aec5  call    cs:__imp_SysStringLen
0x18001aecb  mov     ecx, 26Ch
0x18001aed0  test    eax, eax
0x18001aed2  jnz     short loc_18001AEFD
0x18001aed4  mov     eax, 80070057h
0x18001aed9  mov     [rsp+0B98h+dwMessageId], eax
0x18001aedd  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001aee2  mov     [rsp+0B98h+var_AAC], eax
0x18001aee9  lea     rdx, _TI1J; pThrowInfo
0x18001aef0  lea     rcx, [rsp+0B98h+var_AAC]; pExceptionObject
0x18001aef8  call    _CxxThrowException_0
0x18001aefd  mov     [rsp+0B98h+dwMessageId], ebx
0x18001af01  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001af06  mov     rax, [rdi]
0x18001af09  lea     rdx, [rsp+0B98h+var_B20]
0x18001af0e  mov     rcx, rdi
0x18001af11  mov     rax, [rax+78h]
0x18001af15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af1a  mov     [rsp+0B98h+dwMessageId], eax
0x18001af1e  mov     [rsp+0B98h+dwMessageId], eax
0x18001af22  mov     ecx, 26Eh
0x18001af27  test    eax, eax
0x18001af29  jns     short loc_18001AF4B
0x18001af2b  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001af30  mov     [rsp+0B98h+var_AA8], eax
0x18001af37  lea     rdx, _TI1J; pThrowInfo
0x18001af3e  lea     rcx, [rsp+0B98h+var_AA8]; pExceptionObject
0x18001af46  call    _CxxThrowException_0
0x18001af4b  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001af50  mov     rax, [rdi]
0x18001af53  lea     rdx, [rsp+0B98h+var_B00]
0x18001af5b  mov     rcx, rdi
0x18001af5e  mov     rax, [rax+48h]
0x18001af62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af67  mov     [rsp+0B98h+dwMessageId], eax
0x18001af6b  mov     [rsp+0B98h+dwMessageId], eax
0x18001af6f  mov     ecx, 271h
0x18001af74  test    eax, eax
0x18001af76  jns     short loc_18001AF98
0x18001af78  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001af7d  mov     [rsp+0B98h+var_AA4], eax
0x18001af84  lea     rdx, _TI1J; pThrowInfo
0x18001af8b  lea     rcx, [rsp+0B98h+var_AA4]; pExceptionObject
0x18001af93  call    _CxxThrowException_0
0x18001af98  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001af9d  mov     [rsp+0B98h+dwMessageId], eax
0x18001afa1  mov     rcx, [rsp+0B98h+var_B00]; pbstr
0x18001afa9  call    cs:__imp_SysStringLen
0x18001afaf  mov     ecx, 272h
0x18001afb4  test    eax, eax
0x18001afb6  jnz     short loc_18001AFE1
0x18001afb8  mov     eax, 80070057h
0x18001afbd  mov     [rsp+0B98h+dwMessageId], eax
0x18001afc1  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001afc6  mov     [rsp+0B98h+var_A90], eax
0x18001afcd  lea     rdx, _TI1J; pThrowInfo
0x18001afd4  lea     rcx, [rsp+0B98h+var_A90]; pExceptionObject
0x18001afdc  call    _CxxThrowException_0
0x18001afe1  mov     [rsp+0B98h+dwMessageId], ebx
0x18001afe5  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001afea  mov     rax, [rdi]
0x18001afed  lea     rdx, [rsp+0B98h+var_B10]
0x18001aff5  mov     rcx, rdi
0x18001aff8  mov     rax, [rax+58h]
0x18001affc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b001  mov     [rsp+0B98h+dwMessageId], eax
0x18001b005  mov     [rsp+0B98h+dwMessageId], eax
0x18001b009  mov     ecx, 274h
0x18001b00e  test    eax, eax
0x18001b010  jns     short loc_18001B032
0x18001b012  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001b017  mov     [rsp+0B98h+var_AF0], eax
0x18001b01e  lea     rdx, _TI1J; pThrowInfo
0x18001b025  lea     rcx, [rsp+0B98h+var_AF0]; pExceptionObject
0x18001b02d  call    _CxxThrowException_0
0x18001b032  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001b037  mov     [rsp+0B98h+dwMessageId], eax
0x18001b03b  mov     rcx, [rsp+0B98h+var_B10]; pbstr
0x18001b043  call    cs:__imp_SysStringLen
0x18001b049  mov     ecx, 275h
0x18001b04e  test    eax, eax
0x18001b050  jnz     short loc_18001B07B
0x18001b052  mov     eax, 80070057h
0x18001b057  mov     [rsp+0B98h+dwMessageId], eax
0x18001b05b  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001b060  mov     [rsp+0B98h+var_AEC], eax
0x18001b067  lea     rdx, _TI1J; pThrowInfo
0x18001b06e  lea     rcx, [rsp+0B98h+var_AEC]; pExceptionObject
0x18001b076  call    _CxxThrowException_0
0x18001b07b  mov     [rsp+0B98h+dwMessageId], ebx
0x18001b07f  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001b084  mov     rax, [rdi]
0x18001b087  lea     rdx, [rsp+0B98h+var_B18]
0x18001b08f  mov     rcx, rdi
0x18001b092  mov     rax, [rax+88h]
0x18001b099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b09e  mov     [rsp+0B98h+dwMessageId], eax
0x18001b0a2  mov     [rsp+0B98h+dwMessageId], eax
0x18001b0a6  mov     ecx, 277h
0x18001b0ab  test    eax, eax
0x18001b0ad  jns     short loc_18001B0CF
0x18001b0af  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001b0b4  mov     [rsp+0B98h+var_AE8], eax
0x18001b0bb  lea     rdx, _TI1J; pThrowInfo
0x18001b0c2  lea     rcx, [rsp+0B98h+var_AE8]; pExceptionObject
0x18001b0ca  call    _CxxThrowException_0
0x18001b0cf  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001b0d4  mov     [rsp+0B98h+dwMessageId], eax
0x18001b0d8  mov     rcx, [rsp+0B98h+var_B18]; pbstr
0x18001b0e0  call    cs:__imp_SysStringLen
0x18001b0e6  mov     ecx, 278h
0x18001b0eb  test    eax, eax
0x18001b0ed  jnz     short loc_18001B118
0x18001b0ef  mov     eax, 80070057h
0x18001b0f4  mov     [rsp+0B98h+dwMessageId], eax
0x18001b0f8  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001b0fd  mov     [rsp+0B98h+var_AE4], eax
0x18001b104  lea     rdx, _TI1J; pThrowInfo
0x18001b10b  lea     rcx, [rsp+0B98h+var_AE4]; pExceptionObject
0x18001b113  call    _CxxThrowException_0
0x18001b118  mov     [rsp+0B98h+dwMessageId], ebx
0x18001b11c  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001b121  mov     rax, [rdi]
0x18001b124  lea     rdx, [rsp+0B98h+var_B38]
0x18001b129  mov     rcx, rdi
0x18001b12c  mov     rax, [rax+98h]
0x18001b133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b138  mov     [rsp+0B98h+dwMessageId], eax
0x18001b13c  mov     [rsp+0B98h+dwMessageId], eax
0x18001b140  mov     ecx, 27Ah
0x18001b145  test    eax, eax
0x18001b147  jns     short loc_18001B169
0x18001b149  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001b14e  mov     [rsp+0B98h+var_AE0], eax
0x18001b155  lea     rdx, _TI1J; pThrowInfo
0x18001b15c  lea     rcx, [rsp+0B98h+var_AE0]; pExceptionObject
0x18001b164  call    _CxxThrowException_0
0x18001b169  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001b16e  mov     [rsp+0B98h+var_B08], ebx
0x18001b175  mov     rax, [rdi]
0x18001b178  lea     rdx, [rsp+0B98h+var_B08]
0x18001b180  mov     rcx, rdi
0x18001b183  mov     rax, [rax+0A8h]
0x18001b18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b18f  mov     [rsp+0B98h+dwMessageId], eax
0x18001b193  mov     [rsp+0B98h+dwMessageId], eax
0x18001b197  mov     ecx, 27Dh
0x18001b19c  test    eax, eax
0x18001b19e  jns     short loc_18001B1C0
0x18001b1a0  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001b1a5  mov     [rsp+0B98h+var_ADC], eax
0x18001b1ac  lea     rdx, _TI1J; pThrowInfo
0x18001b1b3  lea     rcx, [rsp+0B98h+var_ADC]; pExceptionObject
0x18001b1bb  call    _CxxThrowException_0
0x18001b1c0  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001b1c5  mov     [rsp+0B98h+var_B04], ebx
0x18001b1cc  mov     rax, [rdi]
0x18001b1cf  lea     rdx, [rsp+0B98h+var_B04]
0x18001b1d7  mov     rcx, rdi
0x18001b1da  mov     rax, [rax+0C8h]
0x18001b1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1e6  mov     [rsp+0B98h+dwMessageId], eax
0x18001b1ea  mov     [rsp+0B98h+dwMessageId], eax
0x18001b1ee  mov     ecx, 280h
0x18001b1f3  test    eax, eax
0x18001b1f5  jns     short loc_18001B217
0x18001b1f7  mov     word ptr [rsp+0B98h+var_B54+2], cx
0x18001b1fc  mov     [rsp+0B98h+var_AD8], eax
0x18001b203  lea     rdx, _TI1J; pThrowInfo
0x18001b20a  lea     rcx, [rsp+0B98h+var_AD8]; pExceptionObject
0x18001b212  call    _CxxThrowException_0
0x18001b217  mov     word ptr [rsp+0B98h+var_B54], cx
0x18001b21c  mov     sil, bl
0x18001b21f  mov     rcx, [rsp+0B98h+var_B20]; pbstr
0x18001b224  call    cs:__imp_SysStringLen
0x18001b22a  test    eax, eax
0x18001b22c  jnz     short loc_18001B262
0x18001b22e  lea     rcx, [rsp+0B98h+var_A50]
0x18001b236  call    ?GetDefaultSyncRootFolder@CPartnershipStateManager@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CPartnershipStateManager::GetDefaultSyncRootFolder(void)
0x18001b23b  nop
0x18001b23c  mov     rcx, rax
0x18001b23f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b244  mov     rdx, rax
0x18001b247  lea     rcx, [rsp+0B98h+var_B20]
0x18001b24c  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18001b251  nop
0x18001b252  lea     rcx, [rsp+0B98h+var_A50]
0x18001b25a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b25f  mov     sil, 1
0x18001b262  lea     rcx, [rsp+0B98h+var_A28]; this
0x18001b26a  call    ??0ClientPartnershipDescriptor@@QEAA@XZ; ClientPartnershipDescriptor::ClientPartnershipDescriptor(void)
0x18001b26f  nop
0x18001b270  mov     rdx, [rsp+0B98h+pbstr]
0x18001b278  lea     rcx, [rsp+0B98h+var_888]
0x18001b280  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18001b285  mov     rdx, [rsp+0B98h+var_B20]
0x18001b28a  lea     rcx, [rsp+0B98h+var_A00]
0x18001b292  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18001b297  mov     rdx, [rsp+0B98h+var_B00]
0x18001b29f  lea     rcx, [rsp+0B98h+var_868]
0x18001b2a7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18001b2ac  mov     rdx, [rsp+0B98h+var_B10]
0x18001b2b4  lea     rcx, [rsp+0B98h+var_9A0]
  ... truncated ...
```
