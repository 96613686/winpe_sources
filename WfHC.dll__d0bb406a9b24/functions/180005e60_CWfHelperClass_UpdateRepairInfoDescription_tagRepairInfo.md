# CWfHelperClass::UpdateRepairInfoDescription(tagRepairInfo *)

- ea: `0x180005e60`
- end: `0x18000655a`
- name: `?UpdateRepairInfoDescription@CWfHelperClass@@AEAAJPEAUtagRepairInfo@@@Z`
- size: `1786`
- prototype: `__int64 __fastcall(CWfHelperClass *__hidden this, struct tagRepairInfo *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800040b0`

## callees

- `0x180002576`
- `0x180005dc0`
- `0x180005e60`
- `0x180006730`
- `0x18000a768`
- `0x18000aab8`
- `0x18000afd8`
- `0x18000bd28`
- `0x18000c03c`
- `0x18000c5b0`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006466`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000649d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800064f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006466`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000649d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800064f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006501`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180006254`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180006254`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000601b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000601b`
- `FirewallAPI!FwFree` at `0x180006246`
- `FirewallAPI!FwFree` at `0x18000629c`
- `FirewallAPI!FwFree` at `0x180006516`
- `FirewallAPI!FwFree` at `0x180006528`
- `FirewallAPI!FwFree` at `0x180006246`
- `FirewallAPI!FwFree` at `0x18000629c`
- `FirewallAPI!FwFree` at `0x180006516`
- `FirewallAPI!FwFree` at `0x180006528`
- `FirewallAPI!FwAlloc` at `0x180006056`
- `FirewallAPI!FwAlloc` at `0x1800061ff`
- `FirewallAPI!FwAlloc` at `0x180006056`
- `FirewallAPI!FwAlloc` at `0x1800061ff`
- `fwbase!FwStringCopy` at `0x180006262`
- `fwbase!FwStringCopy` at `0x180006262`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x1800061ee`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x180006235`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x1800061ee`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x180006235`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180005feb`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180005feb`

## string_xrefs

- `0x1800063eb`: `LinkButtonText`

## pseudocode

```c
__int64 __fastcall CWfHelperClass::UpdateRepairInfoDescription(CWfHelperClass *this, struct tagRepairInfo *a2)
{
  __int64 *v2; // r14
  int StringW; // edi
  unsigned int Data1; // ebx
  unsigned int v5; // r15d
  unsigned int v6; // r12d
  int v7; // r13d
  bool v8; // zf
  bool v9; // zf
  __int64 v10; // rax
  const WCHAR *v11; // rdi
  HRESULT v12; // eax
  int v13; // edi
  __int64 v14; // rax
  size_t v15; // rdi
  __int64 *v16; // rax
  const WCHAR *v17; // rsi
  DiagnosisTextBuilderImpl *v18; // rax
  LPWSTR FileNameW; // rax
  __int64 v20; // rax
  const unsigned __int16 *v21; // rdi
  DiagnosisTextBuilderImpl *v22; // rsi
  volatile signed __int32 *v23; // rdx
  volatile signed __int32 *v24; // rdx
  int v26; // [rsp+30h] [rbp-D0h]
  DiagnosisTextBuilderImpl *v27; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchOut[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct tagRepairInfo *v29; // [rsp+48h] [rbp-B8h]
  __int64 *v30; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v31[12]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszOutBuf[1024]; // [rsp+70h] [rbp-90h] BYREF

  v29 = a2;
  v2 = 0;
  v30 = 0;
  if ( !a2 )
  {
    StringW = -2147024809;
    goto LABEL_112;
  }
  v26 = 0;
  Data1 = a2->guid.Data1;
  v5 = *(_DWORD *)&a2->guid.Data2;
  v6 = *(_DWORD *)a2->guid.Data4;
  v7 = *(_DWORD *)&a2->guid.Data4[4];
  v31[0] = 0;
  switch ( Data1 )
  {
    case 0x9708BAFu:
      if ( __PAIR64__(v6, v5) == *(_QWORD *)((char *)&ID_FW_LOWH_REPAIR_REPRO_MODE + 4)
        && v7 == HIDWORD(ID_FW_LOWH_REPAIR_REPRO_MODE) )
      {
        v2 = &qword_1800117E0;
        goto LABEL_83;
      }
      goto LABEL_111;
    case 0x47A55ECAu:
      if ( v5 != 1190871987 || v6 != -928417657 )
        goto LABEL_111;
      v8 = v7 == 515148882;
      goto LABEL_55;
    case 0xF070B430:
      if ( v5 != 1259410963 || v6 != 1337867145 )
        goto LABEL_111;
      v9 = v7 == 1863415667;
      goto LABEL_15;
  }
  if ( Data1 != -1323459278 )
  {
    switch ( Data1 )
    {
      case 0xB588A5E2:
        if ( v5 != 1141012179 || v6 != -944569443 || v7 != 1480956634 )
          goto LABEL_111;
        a2->UiInfo.type = UIT_HELP_PANE;
        StringW = UtilStringCopyWithAlloc(&a2->UiInfo.pwzNull, 0x3Au, 0);
        if ( StringW < 0 )
          goto LABEL_112;
        v2 = &qword_1800117E0;
        goto LABEL_83;
      case 0xF88C91EB:
        if ( v5 != 1249207754 || v6 != -711941211 )
          goto LABEL_111;
        v9 = v7 == -632930353;
        break;
      case 0x5A0E47BCu:
        if ( v5 != 1252141224 || v6 != 8518537 )
          goto LABEL_111;
        v8 = v7 == -219112160;
        goto LABEL_55;
      case 0x6AAF56BCu:
        if ( v5 != 1168759786 || v6 != 1682703769 )
          goto LABEL_111;
        v9 = v7 == 1965658279;
        break;
      case 0xCB366EB8:
        if ( v5 != 1309869108 || v6 != 1946640023 )
          goto LABEL_111;
        v8 = v7 == -385466497;
LABEL_55:
        if ( !v8 )
          goto LABEL_111;
        v26 = 1;
        v17 = *(const WCHAR **)(*((_QWORD *)this + 20) + 16LL);
        pcchOut[0] = 0;
        v27 = 0;
        if ( !v17 )
        {
          StringW = -2147024809;
          goto LABEL_109;
        }
        if ( AssocQueryStringW(2u, ASSOCSTR_FRIENDLYAPPNAME, v17, 0, 0, pcchOut) >= 0 )
        {
          v18 = (DiagnosisTextBuilderImpl *)FwAlloc(2LL * pcchOut[0]);
          v27 = v18;
          if ( !v18 )
          {
            StringW = -2147024882;
LABEL_67:
            if ( v18 )
            {
              if ( StringW < 0 )
              {
                FwFree(v18);
                goto LABEL_109;
              }
              goto LABEL_83;
            }
            if ( StringW >= 0 )
              goto LABEL_83;
LABEL_109:
            if ( v2 )
              FwFree(v2);
            goto LABEL_112;
          }
          StringW = AssocQueryStringW(2u, ASSOCSTR_FRIENDLYAPPNAME, v17, 0, (LPWSTR)v18, pcchOut);
          if ( StringW >= 0 )
          {
LABEL_63:
            v18 = v27;
            if ( !v27 )
            {
              StringW = -2147418113;
              goto LABEL_109;
            }
            v2 = (__int64 *)v27;
            goto LABEL_67;
          }
          FwFree(v27);
          v27 = 0;
        }
        FileNameW = PathFindFileNameW(v17);
        StringW = FwStringCopy(FileNameW, &v27);
        if ( StringW < 0 )
        {
          v18 = v27;
          goto LABEL_67;
        }
        goto LABEL_63;
      case 0x4377A944u:
        if ( v5 != 1265743297 || v6 != -915285884 )
          goto LABEL_111;
        if ( v7 != 2128836902 )
        {
LABEL_80:
          if ( Data1 != 1977464185 || v5 != 1319095511 || v6 != 576277135 || v7 != -740309910 )
          {
LABEL_111:
            StringW = -2147418113;
            goto LABEL_112;
          }
        }
        v20 = *((_QWORD *)this + 20);
        v2 = &qword_1800117E0;
        if ( *(_QWORD *)(v20 + 16) )
          v2 = *(__int64 **)(v20 + 16);
        goto LABEL_83;
      default:
        goto LABEL_80;
    }
LABEL_15:
    if ( !v9 )
      goto LABEL_111;
    StringCchPrintfW(v31, 0xAu, L"%d", *(unsigned __int16 *)(*((_QWORD *)this + 20) + 16LL));
    v2 = (__int64 *)v31;
    goto LABEL_83;
  }
  if ( v5 != 1286160545 || v6 != 1213122447 || v7 != 1629318174 )
    goto LABEL_111;
  v10 = *((_QWORD *)this + 20);
  v11 = *(const WCHAR **)(v10 + 16);
  if ( v11 )
  {
    v12 = SHLoadIndirectString(*(PCWSTR *)(v10 + 16), pszOutBuf, 0x400u, 0);
    if ( v12 >= 0 )
    {
      if ( CompareStringW(0x7Fu, 1u, v11, -1, pszOutBuf, -1) == 2 && (*v11 & 0xFFBF) == 0 )
        goto LABEL_83;
      v14 = -1;
      do
        ++v14;
      while ( pszOutBuf[v14] );
      v15 = 2 * v14 + 2;
      v16 = (__int64 *)FwAlloc(v15);
      v2 = v16;
      v30 = v16;
      if ( v16 )
      {
        memcpy_0(v16, pszOutBuf, v15);
        v13 = 0;
      }
      else
      {
        v13 = 8;
      }
    }
    else
    {
      v13 = (unsigned __int16)v12;
    }
    if ( v13 )
    {
      StringW = v13 | 0x80070000;
      goto LABEL_112;
    }
  }
LABEL_83:
  *(_QWORD *)pcchOut = v29->pwszDescription;
  v21 = *(const unsigned __int16 **)pcchOut;
  DiagnosisTextBuilder::DiagnosisTextBuilder((DiagnosisTextBuilder *)&v27, hInstance);
  StringW = DiagnosisTextBuilder::SetTextV((DiagnosisTextBuilder *)&v27, v21, v2);
  v22 = v27;
  if ( StringW < 0 )
    goto LABEL_100;
  if ( Data1 == 158370735 )
  {
    if ( __PAIR64__(v6, v5) == *(_QWORD *)((char *)&ID_FW_LOWH_REPAIR_REPRO_MODE + 4)
      && v7 == HIDWORD(ID_FW_LOWH_REPAIR_REPRO_MODE) )
    {
      if ( v27 )
      {
        StringW = DiagnosisTextBuilderImpl::AddParameter(v27, (char *)v27 + 40, L"ContinueButtonText", 2000);
        goto LABEL_96;
      }
      goto LABEL_95;
    }
  }
  else if ( Data1 == -1249335838 && v5 == 1141012179 && v6 == -944569443 && v7 == 1480956634 )
  {
    if ( v27 )
    {
      StringW = DiagnosisTextBuilderImpl::AddParameter(v27, (char *)v27 + 40, L"LinkButtonText", 1024);
      goto LABEL_96;
    }
LABEL_95:
    StringW = -2147024882;
LABEL_96:
    if ( StringW < 0 )
      goto LABEL_100;
  }
  if ( v22 )
    StringW = DiagnosisTextBuilderImpl::GetXML(v22, &v29->pwszDescription);
  else
    StringW = -2147024882;
LABEL_100:
  if ( v22 )
  {
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::_Erase(
      (__int64)v22 + 40,
      *(_QWORD **)(*((_QWORD *)v22 + 5) + 8LL));
    *(_QWORD *)(*((_QWORD *)v22 + 5) + 8LL) = *((_QWORD *)v22 + 5);
    **((_QWORD **)v22 + 5) = *((_QWORD *)v22 + 5);
    *(_QWORD *)(*((_QWORD *)v22 + 5) + 16LL) = *((_QWORD *)v22 + 5);
    *((_QWORD *)v22 + 6) = 0;
    operator delete(*((void **)v22 + 5));
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::_Erase(
      (__int64)v22 + 24,
      *(_QWORD **)(*((_QWORD *)v22 + 3) + 8LL));
    *(_QWORD *)(*((_QWORD *)v22 + 3) + 8LL) = *((_QWORD *)v22 + 3);
    **((_QWORD **)v22 + 3) = *((_QWORD *)v22 + 3);
    *(_QWORD *)(*((_QWORD *)v22 + 3) + 16LL) = *((_QWORD *)v22 + 3);
    *((_QWORD *)v22 + 4) = 0;
    operator delete(*((void **)v22 + 3));
    v23 = (volatile signed __int32 *)(*((_QWORD *)v22 + 2) - 24LL);
    if ( _InterlockedExchangeAdd(v23 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
    v24 = (volatile signed __int32 *)(*((_QWORD *)v22 + 1) - 24LL);
    if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24);
    operator delete(v22);
  }
  if ( StringW >= 0 )
    CoTaskMemFree(*(LPVOID *)pcchOut);
  if ( v26 )
    goto LABEL_109;
LABEL_112:
  FwFree(v30);
  return (unsigned int)StringW;
}

```

## disassembly

```asm
0x180005e60  mov     [rsp-8+arg_10], rbx
0x180005e65  push    rbp
0x180005e66  push    rsi
0x180005e67  push    rdi
0x180005e68  push    r12
0x180005e6a  push    r13
0x180005e6c  push    r14
0x180005e6e  push    r15
0x180005e70  lea     rbp, [rsp-780h]
0x180005e78  sub     rsp, 880h
0x180005e7f  mov     rax, cs:__security_cookie
0x180005e86  xor     rax, rsp
0x180005e89  mov     [rbp+7B0h+var_40], rax
0x180005e90  mov     [rsp+8B0h+var_868], rdx
0x180005e95  xor     r8d, r8d; unsigned __int16 *
0x180005e98  mov     r14d, r8d
0x180005e9b  mov     [rsp+8B0h+var_860], r8
0x180005ea0  test    rdx, rdx
0x180005ea3  jnz     short loc_180005EAF
0x180005ea5  mov     edi, 80070057h
0x180005eaa  jmp     loc_180006523
0x180005eaf  mov     [rsp+8B0h+var_880], r8d
0x180005eb4  mov     ebx, [rdx]
0x180005eb6  mov     r15d, [rdx+4]
0x180005eba  mov     r12d, [rdx+8]
0x180005ebe  mov     r13d, [rdx+0Ch]
0x180005ec2  mov     [rsp+8B0h+var_858], r8w
0x180005ec8  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180005ecf  cmp     ebx, 9708BAFh
0x180005ed5  jnz     short loc_180005F0A
0x180005ed7  cmp     r15d, dword ptr cs:ID_FW_LOWH_REPAIR_REPRO_MODE+4
0x180005ede  jnz     loc_18000651E
0x180005ee4  cmp     r12d, dword ptr cs:ID_FW_LOWH_REPAIR_REPRO_MODE+8
0x180005eeb  jnz     loc_18000651E
0x180005ef1  cmp     r13d, dword ptr cs:ID_FW_LOWH_REPAIR_REPRO_MODE+0Ch
0x180005ef8  jnz     loc_18000651E
0x180005efe  lea     r14, qword_1800117E0
0x180005f05  jmp     loc_180006335
0x180005f0a  cmp     ebx, 47A55ECAh
0x180005f10  jnz     short loc_180005F38
0x180005f12  cmp     r15d, cs:dword_180011B24
0x180005f19  jnz     loc_18000651E
0x180005f1f  cmp     r12d, cs:dword_180011B28
0x180005f26  jnz     loc_18000651E
0x180005f2c  cmp     r13d, cs:dword_180011B2C
0x180005f33  jmp     loc_1800061A3
0x180005f38  cmp     ebx, 0F070B430h
0x180005f3e  jnz     short loc_180005F93
0x180005f40  cmp     r15d, cs:dword_180011B14
0x180005f47  jnz     loc_18000651E
0x180005f4d  cmp     r12d, cs:dword_180011B18
0x180005f54  jnz     loc_18000651E
0x180005f5a  cmp     r13d, cs:dword_180011B1C
0x180005f61  jnz     loc_18000651E
0x180005f67  mov     rax, [rcx+0A0h]
0x180005f6e  movzx   r9d, word ptr [rax+10h]
0x180005f73  lea     r8, aD; "%d"
0x180005f7a  mov     edx, 0Ah; unsigned __int64
0x180005f7f  lea     rcx, [rsp+8B0h+var_858]; unsigned __int16 *
0x180005f84  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005f89  lea     r14, [rsp+8B0h+var_858]
0x180005f8e  jmp     loc_180006335
0x180005f93  cmp     ebx, 0B11D9D32h
0x180005f99  jnz     loc_180006095
0x180005f9f  cmp     r15d, cs:dword_180011B34
0x180005fa6  jnz     loc_18000651E
0x180005fac  cmp     r12d, cs:dword_180011B38
0x180005fb3  jnz     loc_18000651E
0x180005fb9  cmp     r13d, cs:dword_180011B3C
0x180005fc0  jnz     loc_18000651E
0x180005fc6  mov     rax, [rcx+0A0h]
0x180005fcd  mov     rdi, [rax+10h]
0x180005fd1  test    rdi, rdi
0x180005fd4  jz      loc_180006335
0x180005fda  xor     r9d, r9d; ppvReserved
0x180005fdd  mov     r8d, 400h; cchOutBuf
0x180005fe3  lea     rdx, [rsp+8B0h+pszOutBuf]; pszOutBuf
0x180005fe8  mov     rcx, rdi; pszSource
0x180005feb  call    cs:__imp_SHLoadIndirectString
0x180005ff1  test    eax, eax
0x180005ff3  jns     short loc_180005FFD
0x180005ff5  movzx   edi, ax
0x180005ff8  jmp     loc_180006082
0x180005ffd  mov     [rsp+8B0h+cchCount2], esi; cchCount2
0x180006001  lea     rax, [rsp+8B0h+pszOutBuf]
0x180006006  mov     [rsp+8B0h+lpString2], rax; lpString2
0x18000600b  mov     r9d, esi; cchCount1
0x18000600e  mov     r8, rdi; lpString1
0x180006011  mov     edx, 1; dwCmpFlags
0x180006016  mov     ecx, 7Fh; Locale
0x18000601b  call    cs:__imp_CompareStringW
0x180006021  cmp     eax, 2
0x180006024  jnz     short loc_180006034
0x180006026  mov     eax, 0FFBFh
0x18000602b  test    [rdi], ax
0x18000602e  jz      loc_180006335
0x180006034  lea     rcx, [rsp+8B0h+pszOutBuf]
0x180006039  mov     rax, rsi
0x18000603c  nop     dword ptr [rax+00h]
0x180006040  lea     rax, [rax+1]
0x180006044  cmp     [rcx+rax*2], r14w
0x180006049  jnz     short loc_180006040
0x18000604b  lea     rdi, ds:2[rax*2]
0x180006053  mov     rcx, rdi
0x180006056  call    cs:__imp_FwAlloc
0x18000605c  mov     r14, rax
0x18000605f  mov     [rsp+8B0h+var_860], rax
0x180006064  test    rax, rax
0x180006067  jnz     short loc_180006070
0x180006069  mov     edi, 8
0x18000606e  jmp     short loc_180006082
0x180006070  mov     r8, rdi; Size
0x180006073  lea     rdx, [rsp+8B0h+pszOutBuf]; Src
0x180006078  mov     rcx, rax; void *
0x18000607b  call    memcpy_0
0x180006080  xor     edi, edi
0x180006082  test    edi, edi
0x180006084  jz      loc_180006335
0x18000608a  or      edi, 80070000h
0x180006090  jmp     loc_180006523
0x180006095  cmp     ebx, 0B588A5E2h
0x18000609b  jnz     short loc_1800060EF
0x18000609d  cmp     r15d, cs:dword_180011A94
0x1800060a4  jnz     loc_18000651E
0x1800060aa  cmp     r12d, cs:dword_180011A98
0x1800060b1  jnz     loc_18000651E
0x1800060b7  cmp     r13d, cs:dword_180011A9C
0x1800060be  jnz     loc_18000651E
0x1800060c4  mov     dword ptr [rdx+38h], 3
0x1800060cb  lea     rcx, [rdx+40h]; unsigned __int16 **
0x1800060cf  mov     edx, 3Ah ; ':'; unsigned int
0x1800060d4  call    ?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z; UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)
0x1800060d9  mov     edi, eax
0x1800060db  test    eax, eax
0x1800060dd  js      loc_180006523
0x1800060e3  lea     r14, qword_1800117E0
0x1800060ea  jmp     loc_180006335
0x1800060ef  cmp     ebx, 0F88C91EBh
0x1800060f5  jnz     short loc_18000611D
0x1800060f7  cmp     r15d, cs:dword_180011AD4
0x1800060fe  jnz     loc_18000651E
0x180006104  cmp     r12d, cs:dword_180011AD8
0x18000610b  jnz     loc_18000651E
0x180006111  cmp     r13d, cs:dword_180011ADC
0x180006118  jmp     loc_180005F61
0x18000611d  cmp     ebx, 5A0E47BCh
0x180006123  jnz     short loc_180006148
0x180006125  cmp     r15d, cs:dword_180011AE4
0x18000612c  jnz     loc_18000651E
0x180006132  cmp     r12d, cs:dword_180011AE8
0x180006139  jnz     loc_18000651E
0x18000613f  cmp     r13d, cs:dword_180011AEC
0x180006146  jmp     short loc_1800061A3
0x180006148  cmp     ebx, 6AAF56BCh
0x18000614e  jnz     short loc_180006176
0x180006150  cmp     r15d, cs:dword_180011AA4
0x180006157  jnz     loc_18000651E
0x18000615d  cmp     r12d, cs:dword_180011AA8
0x180006164  jnz     loc_18000651E
0x18000616a  cmp     r13d, cs:dword_180011AAC
0x180006171  jmp     loc_180005F61
0x180006176  cmp     ebx, 0CB366EB8h
0x18000617c  jnz     loc_1800062BE
0x180006182  cmp     r15d, cs:dword_180011AB4
0x180006189  jnz     loc_18000651E
0x18000618f  cmp     r12d, cs:dword_180011AB8
0x180006196  jnz     loc_18000651E
0x18000619c  cmp     r13d, cs:dword_180011ABC
0x1800061a3  jnz     loc_18000651E
0x1800061a9  mov     [rsp+8B0h+var_880], 1
0x1800061b1  mov     rax, [rcx+0A0h]
0x1800061b8  mov     rsi, [rax+10h]
0x1800061bc  mov     [rsp+8B0h+pcchOut], r8d
0x1800061c1  mov     [rsp+8B0h+var_878], r8
0x1800061c6  test    rsi, rsi
0x1800061c9  jz      loc_1800062B4
0x1800061cf  lea     rax, [rsp+8B0h+pcchOut]
0x1800061d4  mov     qword ptr [rsp+8B0h+cchCount2], rax; pcchOut
0x1800061d9  mov     [rsp+8B0h+lpString2], r8; pszOut
0x1800061de  xor     r9d, r9d; pszExtra
0x1800061e1  mov     r8, rsi; pszAssoc
0x1800061e4  mov     edx, 4; str
0x1800061e9  mov     ecx, 2; flags
0x1800061ee  call    cs:__imp_AssocQueryStringW
0x1800061f4  test    eax, eax
0x1800061f6  js      short loc_180006251
0x1800061f8  mov     ecx, [rsp+8B0h+pcchOut]
0x1800061fc  add     rcx, rcx
0x1800061ff  call    cs:__imp_FwAlloc
0x180006205  mov     [rsp+8B0h+var_878], rax
0x18000620a  test    rax, rax
0x18000620d  jnz     short loc_180006216
0x18000620f  mov     edi, 8007000Eh
0x180006214  jmp     short loc_18000628C
0x180006216  lea     r8, [rsp+8B0h+pcchOut]
0x18000621b  mov     qword ptr [rsp+8B0h+cchCount2], r8; pcchOut
0x180006220  mov     [rsp+8B0h+lpString2], rax; pszOut
0x180006225  xor     r9d, r9d; pszExtra
0x180006228  mov     r8, rsi; pszAssoc
0x18000622b  mov     edx, 4; str
0x180006230  mov     ecx, 2; flags
0x180006235  call    cs:__imp_AssocQueryStringW
0x18000623b  mov     edi, eax
0x18000623d  test    eax, eax
0x18000623f  jns     short loc_18000626E
0x180006241  mov     rcx, [rsp+8B0h+var_878]
0x180006246  call    cs:__imp_FwFree
0x18000624c  mov     [rsp+8B0h+var_878], r14
0x180006251  mov     rcx, rsi; pszPath
0x180006254  call    cs:__imp_PathFindFileNameW
0x18000625a  mov     rcx, rax
0x18000625d  lea     rdx, [rsp+8B0h+var_878]
0x180006262  call    cs:__imp_FwStringCopy
0x180006268  mov     edi, eax
0x18000626a  test    eax, eax
0x18000626c  js      short loc_180006287
0x18000626e  mov     rax, [rsp+8B0h+var_878]
0x180006273  test    rax, rax
0x180006276  jnz     short loc_180006282
0x180006278  mov     edi, 8000FFFFh
0x18000627d  jmp     loc_18000650E
0x180006282  mov     r14, rax
0x180006285  jmp     short loc_18000628C
0x180006287  mov     rax, [rsp+8B0h+var_878]
0x18000628c  test    rax, rax
0x18000628f  jz      short loc_1800062A7
0x180006291  test    edi, edi
0x180006293  jns     loc_180006335
0x180006299  mov     rcx, rax
0x18000629c  call    cs:__imp_FwFree
0x1800062a2  jmp     loc_18000650E
0x1800062a7  test    edi, edi
0x1800062a9  js      loc_18000650E
0x1800062af  jmp     loc_180006335
0x1800062b4  mov     edi, 80070057h
0x1800062b9  jmp     loc_18000650E
0x1800062be  cmp     ebx, 4377A944h
0x1800062c4  jnz     short loc_1800062E9
0x1800062c6  cmp     r15d, cs:dword_180011B04
0x1800062cd  jnz     loc_18000651E
0x1800062d3  cmp     r12d, cs:dword_180011B08
0x1800062da  jnz     loc_18000651E
0x1800062e0  cmp     r13d, cs:dword_180011B0C
0x1800062e7  jz      short loc_18000631C
0x1800062e9  cmp     ebx, 75DDB579h
0x1800062ef  jnz     loc_18000651E
0x1800062f5  cmp     r15d, cs:dword_180011AF4
0x1800062fc  jnz     loc_18000651E
0x180006302  cmp     r12d, cs:dword_180011AF8
0x180006309  jnz     loc_18000651E
0x18000630f  cmp     r13d, cs:dword_180011AFC
0x180006316  jnz     loc_18000651E
0x18000631c  mov     rax, [rcx+0A0h]
0x180006323  mov     rcx, [rax+10h]
0x180006327  lea     r14, qword_1800117E0
0x18000632e  test    rcx, rcx
0x180006331  cmovnz  r14, rcx
0x180006335  mov     rax, [rsp+8B0h+var_868]
0x18000633a  mov     rdi, [rax+18h]
0x18000633e  mov     qword ptr [rsp+8B0h+pcchOut], rdi
0x180006343  mov     rdx, cs:hInstance; HINSTANCE
0x18000634a  lea     rcx, [rsp+8B0h+var_878]; this
0x18000634f  call    ??0DiagnosisTextBuilder@@QEAA@PEAUHINSTANCE__@@@Z; DiagnosisTextBuilder::DiagnosisTextBuilder(HINSTANCE__ *)
0x180006354  nop
0x180006355  mov     r8, r14
0x180006358  mov     rdx, rdi; unsigned __int16 *
0x18000635b  lea     rcx, [rsp+8B0h+var_878]; this
0x180006360  call    ?SetTextV@DiagnosisTextBuilder@@QEAAJPEBGZZ; DiagnosisTextBuilder::SetTextV(ushort const *,...)
0x180006365  mov     edi, eax
0x180006367  mov     rsi, [rsp+8B0h+var_878]
0x18000636c  test    eax, eax
0x18000636e  js      loc_18000642A
0x180006374  cmp     ebx, 9708BAFh
0x18000637a  jnz     short loc_1800063BD
0x18000637c  cmp     r15d, dword ptr cs:ID_FW_LOWH_REPAIR_REPRO_MODE+4
0x180006383  jnz     loc_18000640B
0x180006389  cmp     r12d, dword ptr cs:ID_FW_LOWH_REPAIR_REPRO_MODE+8
0x180006390  jnz     short loc_18000640B
0x180006392  cmp     r13d, dword ptr cs:ID_FW_LOWH_REPAIR_REPRO_MODE+0Ch
0x180006399  jnz     short loc_18000640B
0x18000639b  test    rsi, rsi
0x18000639e  jz      short loc_180006402
0x1800063a0  mov     r9d, 7D0h
0x1800063a6  lea     r8, aContinuebutton; "ContinueButtonText"
0x1800063ad  lea     rdx, [rsi+28h]
0x1800063b1  mov     rcx, rsi
0x1800063b4  call    ?AddParameter@DiagnosisTextBuilderImpl@@AEAAJAEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@PEBG1@Z; DiagnosisTextBuilderImpl::AddParameter(std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,ushort const *,ushort const *)
0x1800063b9  mov     edi, eax
0x1800063bb  jmp     short loc_180006407
0x1800063bd  cmp     ebx, 0B588A5E2h
0x1800063c3  jnz     short loc_18000640B
0x1800063c5  cmp     r15d, cs:dword_180011A94
0x1800063cc  jnz     short loc_18000640B
0x1800063ce  cmp     r12d, cs:dword_180011A98
0x1800063d5  jnz     short loc_18000640B
0x1800063d7  cmp     r13d, cs:dword_180011A9C
0x1800063de  jnz     short loc_18000640B
0x1800063e0  test    rsi, rsi
0x1800063e3  jz      short loc_180006402
0x1800063e5  mov     r9d, 400h
  ... truncated ...
```
