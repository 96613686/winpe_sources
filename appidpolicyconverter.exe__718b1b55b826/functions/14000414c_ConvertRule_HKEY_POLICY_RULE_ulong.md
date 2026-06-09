# ConvertRule(HKEY__ *,_POLICY_RULE *,ulong *)

- ea: `0x14000414c`
- end: `0x140004584`
- name: `?ConvertRule@@YAKPEAUHKEY__@@PEAU_POLICY_RULE@@PEAK@Z`
- size: `1080`
- prototype: `__int64 __fastcall(HKEY, LPCWSTR *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140003bc0`

## callees

- `0x1400028e0`
- `0x14000414c`
- `0x140005af0`
- `0x140007078`
- `0x140007150`
- `0x1400071d8`
- `0x140007428`
- `0x140007d00`
- `0x140007edc`
- `0x140008d30`
- `0x140008ef4`
- `0x140013ab7`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400041b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400041b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004542`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000433b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000440e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000433b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000440e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140004404`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140004404`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14000438d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14000438d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004528`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004528`
- `OLEAUT32!__imp_SysFreeString` at `0x14000454c`
- `OLEAUT32!__imp_SysFreeString` at `0x140004558`
- `OLEAUT32!__imp_SysFreeString` at `0x140004564`
- `OLEAUT32!__imp_SysFreeString` at `0x14000454c`
- `OLEAUT32!__imp_SysFreeString` at `0x140004558`
- `OLEAUT32!__imp_SysFreeString` at `0x140004564`
- `OLEAUT32!__imp_SysStringLen` at `0x14000445c`
- `OLEAUT32!__imp_SysStringLen` at `0x1400044ac`
- `OLEAUT32!__imp_SysStringLen` at `0x14000445c`
- `OLEAUT32!__imp_SysStringLen` at `0x1400044ac`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140004331`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140004331`

## pseudocode

```c
__int64 __fastcall ConvertRule(HKEY a1, LPCWSTR *a2, unsigned int *a3)
{
  unsigned int *v3; // r15
  LPCWSTR *v4; // r14
  WCHAR *v5; // rbx
  unsigned int LastError; // edi
  int v7; // r8d
  _QWORD *v8; // rcx
  int v9; // edx
  struct ATL::CComBSTR *v10; // r9
  unsigned int v11; // ebx
  int v12; // r8d
  _QWORD *v13; // rcx
  int v14; // edx
  int v15; // eax
  __int64 v16; // r8
  WCHAR *v17; // rax
  UINT v18; // eax
  size_t v19; // r15
  WCHAR *v20; // rax
  UINT v21; // eax
  size_t v22; // r15
  WCHAR *v23; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-98h]
  LPCWSTR StringSecurityDescriptor; // [rsp+30h] [rbp-88h] BYREF
  WINBOOL bDaclPresent; // [rsp+38h] [rbp-80h] BYREF
  unsigned __int16 *v28; // [rsp+40h] [rbp-78h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-70h] BYREF
  unsigned int v30; // [rsp+50h] [rbp-68h]
  ULONG SecurityDescriptorSize; // [rsp+54h] [rbp-64h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+58h] [rbp-60h] BYREF
  LPVOID pAce; // [rsp+60h] [rbp-58h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-40h] BYREF
  PACL pDacl; // [rsp+80h] [rbp-38h] BYREF
  ATL::CAtlException *v38; // [rsp+88h] [rbp-30h] BYREF

  v3 = a3;
  v4 = a2;
  hKey = 0;
  v28 = 0;
  bstrString = 0;
  pbstr = 0;
  v5 = 0;
  StringSecurityDescriptor = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pAce = 0;
  LastError = RegOpenKeyExW(a1, *a2, 0, 0x20019u, &hKey);
  if ( LastError )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      v9 = 20;
LABEL_5:
      phkResult = (PHKEY)*v4;
LABEL_6:
      WPP_SF_dS(v8[2], v9, v7, LastError, (__int64)phkResult);
      goto LABEL_46;
    }
    goto LABEL_46;
  }
  LastError = ReadStringValue(hKey, L"Value", &v28);
  v30 = LastError;
  if ( LastError )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      v9 = 21;
      goto LABEL_5;
    }
    goto LABEL_46;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ATL::CComBSTR::operator=(&bstrString, v28);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
    {
      v11 = -2147024882;
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_14000425C);
LABEL_12:
      LastError = WIN32_FROM_HRESULT(v11);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
        goto LABEL_16;
      v14 = 22;
LABEL_15:
      WPP_SF_dS(v13[2], v14, v12, v11, (__int64)v28);
LABEL_16:
      v5 = (WCHAR *)StringSecurityDescriptor;
      goto LABEL_46;
    }
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v38) )
    {
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_140004265);
      v11 = *(_DWORD *)v38;
      if ( *(int *)v38 < 0 )
        goto LABEL_12;
      v3 = a3;
      v4 = a2;
      LastError = v30;
    }
  }
  v15 = AppId::RuleCompiler::Compile(
          (AppId::RuleCompiler *)&bstrString,
          &pbstr,
          (OLECHAR **)&StringSecurityDescriptor,
          v10);
  v11 = v15;
  if ( v15 < 0 )
  {
    LastError = WIN32_FROM_HRESULT((unsigned int)v15);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_16;
    v14 = 23;
    goto LABEL_15;
  }
  v5 = (WCHAR *)StringSecurityDescriptor;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         StringSecurityDescriptor,
         1u,
         &SecurityDescriptor,
         &SecurityDescriptorSize) )
  {
    if ( GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      if ( bDaclPresent && pDacl->AceCount == 1 )
      {
        if ( !GetAce(pDacl, 0, &pAce) )
        {
          LastError = GetLastError();
          goto LABEL_46;
        }
        v17 = (WCHAR *)AiAlloc(*((unsigned __int16 *)pAce + 1));
        v4[3] = v17;
        if ( !v17 )
          goto LABEL_35;
        memcpy_0(v17, pAce, *((unsigned __int16 *)pAce + 1));
        UpdateAttributeMask(v5, v3);
        v18 = SysStringLen(v5);
        if ( v18 > 0x100 )
        {
          *(_DWORD *)(v5 + 253) = 3014702;
          *(_DWORD *)(v5 + 255) = 46;
          v18 = 256;
        }
        v19 = 2LL * (v18 + 1);
        v20 = (WCHAR *)AiAlloc(v19);
        v4[2] = v20;
        if ( !v20 )
          goto LABEL_35;
        memcpy_0(v20, v5, v19);
        v21 = SysStringLen(pbstr);
        if ( v21 > 0x7FFF )
        {
          LastError = 87;
          goto LABEL_46;
        }
        v22 = 2LL * (v21 + 1);
        v23 = (WCHAR *)AiAlloc(v22);
        v4[1] = v23;
        if ( !v23 )
        {
LABEL_35:
          LastError = 8;
          goto LABEL_46;
        }
        memcpy_0(v23, pbstr, v22);
      }
      else
      {
        LastError = 87;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v16, v5);
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c8ab8980b27f3479e08bdbe236c5fb3b_Traceguids, LastError);
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      v9 = 24;
      phkResult = (PHKEY)v5;
      goto LABEL_6;
    }
  }
LABEL_46:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  AiFree(v28);
  if ( hKey )
    RegCloseKey(hKey);
  SysFreeString(v5);
  SysFreeString(pbstr);
  SysFreeString(bstrString);
  return LastError;
}

```

## disassembly

```asm
0x14000414c  mov     rax, rsp
0x14000414f  mov     [rax+8], rbx
0x140004153  mov     [rax+18h], r8
0x140004157  mov     [rax+10h], rdx
0x14000415b  push    rsi
0x14000415c  push    rdi
0x14000415d  push    r12
0x14000415f  push    r14
0x140004161  push    r15
0x140004163  sub     rsp, 90h
0x14000416a  mov     r15, r8
0x14000416d  mov     r14, rdx
0x140004170  xor     esi, esi
0x140004172  mov     [rax-48h], rsi
0x140004176  mov     [rax-78h], rsi
0x14000417a  mov     [rax-40h], rsi
0x14000417e  mov     [rax-70h], rsi
0x140004182  mov     ebx, esi
0x140004184  mov     [rsp+0B8h+StringSecurityDescriptor], rbx
0x140004189  mov     [rax-50h], rsi
0x14000418d  mov     [rax-64h], esi
0x140004190  mov     [rax-38h], rsi
0x140004194  mov     [rax-80h], esi
0x140004197  mov     [rax-60h], esi
0x14000419a  mov     [rax-58h], rsi
0x14000419e  lea     rax, [rax-48h]
0x1400041a2  mov     [rsp+0B8h+phkResult], rax; phkResult
0x1400041a7  mov     r9d, 20019h; samDesired
0x1400041ad  xor     r8d, r8d; ulOptions
0x1400041b0  mov     rdx, [rdx]; lpSubKey
0x1400041b3  call    cs:__imp_RegOpenKeyExW
0x1400041b9  mov     edi, eax
0x1400041bb  test    eax, eax
0x1400041bd  jz      short loc_1400041FF
0x1400041bf  lea     rax, WPP_GLOBAL_Control
0x1400041c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400041cd  cmp     rcx, rax
0x1400041d0  jz      loc_14000451E
0x1400041d6  test    dword ptr [rcx+1Ch], 800h
0x1400041dd  jz      loc_14000451E
0x1400041e3  lea     edx, [rsi+14h]
0x1400041e6  mov     rax, [r14]
0x1400041e9  mov     [rsp+0B8h+phkResult], rax
0x1400041ee  mov     r9d, edi
0x1400041f1  mov     rcx, [rcx+10h]
0x1400041f5  call    WPP_SF_dS
0x1400041fa  jmp     loc_14000451E
0x1400041ff  lea     r8, [rsp+0B8h+var_78]; unsigned __int16 **
0x140004204  lea     rdx, aValue; "Value"
0x14000420b  mov     rcx, [rsp+0B8h+hKey]; hKey
0x140004210  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x140004215  mov     edi, eax
0x140004217  mov     [rsp+0B8h+var_68], eax
0x14000421b  test    eax, eax
0x14000421d  jz      short loc_14000424A
0x14000421f  lea     rax, WPP_GLOBAL_Control
0x140004226  mov     rcx, cs:WPP_GLOBAL_Control
0x14000422d  cmp     rcx, rax
0x140004230  jz      loc_14000451E
0x140004236  test    dword ptr [rcx+1Ch], 800h
0x14000423d  jz      loc_14000451E
0x140004243  mov     edx, 15h
0x140004248  jmp     short loc_1400041E6
0x14000424a  mov     rdx, [rsp+0B8h+var_78]
0x14000424f  lea     rcx, [rsp+0B8h+bstrString]
0x140004254  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140004259  nop
0x14000425a  jmp     short loc_1400042D0
0x14000425c  mov     ebx, [rsp+0B8h+arg_18]
0x140004263  jmp     short loc_140004272
0x140004265  mov     ebx, [rsp+0B8h+arg_18]
0x14000426c  xor     esi, esi
0x14000426e  test    ebx, ebx
0x140004270  jns     short loc_1400042BC
0x140004272  mov     ecx, ebx
0x140004274  call    WIN32_FROM_HRESULT
0x140004279  mov     edi, eax
0x14000427b  lea     rax, WPP_GLOBAL_Control
0x140004282  mov     rcx, cs:WPP_GLOBAL_Control
0x140004289  cmp     rcx, rax
0x14000428c  jz      short loc_1400042B2
0x14000428e  test    dword ptr [rcx+1Ch], 800h
0x140004295  jz      short loc_1400042B2
0x140004297  mov     edx, 16h
0x14000429c  mov     rax, [rsp+0B8h+var_78]
0x1400042a1  mov     [rsp+0B8h+phkResult], rax
0x1400042a6  mov     r9d, ebx
0x1400042a9  mov     rcx, [rcx+10h]
0x1400042ad  call    WPP_SF_dS
0x1400042b2  mov     rbx, [rsp+0B8h+StringSecurityDescriptor]
0x1400042b7  jmp     loc_14000451E
0x1400042bc  mov     r15, [rsp+0B8h+arg_10]
0x1400042c4  mov     r14, [rsp+0B8h+arg_8]
0x1400042cc  mov     edi, [rsp+0B8h+var_68]
0x1400042d0  lea     r8, [rsp+0B8h+StringSecurityDescriptor]; struct ATL::CComBSTR *
0x1400042d5  lea     rdx, [rsp+0B8h+pbstr]; struct ATL::CComBSTR *
0x1400042da  lea     rcx, [rsp+0B8h+bstrString]; this
0x1400042df  call    ?Compile@RuleCompiler@AppId@@YAJAEBVCComBSTR@ATL@@AEAV34@1@Z; AppId::RuleCompiler::Compile(ATL::CComBSTR const &,ATL::CComBSTR &,ATL::CComBSTR &)
0x1400042e4  mov     ebx, eax
0x1400042e6  test    eax, eax
0x1400042e8  jns     short loc_140004316
0x1400042ea  mov     ecx, eax
0x1400042ec  call    WIN32_FROM_HRESULT
0x1400042f1  mov     edi, eax
0x1400042f3  lea     rax, WPP_GLOBAL_Control
0x1400042fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140004301  cmp     rcx, rax
0x140004304  jz      short loc_1400042B2
0x140004306  test    dword ptr [rcx+1Ch], 800h
0x14000430d  jz      short loc_1400042B2
0x14000430f  mov     edx, 17h
0x140004314  jmp     short loc_14000429C
0x140004316  lea     r9, [rsp+0B8h+SecurityDescriptorSize]; SecurityDescriptorSize
0x14000431b  lea     r8, [rsp+0B8h+SecurityDescriptor]; SecurityDescriptor
0x140004320  mov     r12d, 1
0x140004326  mov     edx, r12d; StringSDRevision
0x140004329  mov     rbx, [rsp+0B8h+StringSecurityDescriptor]
0x14000432e  mov     rcx, rbx; StringSecurityDescriptor
0x140004331  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140004337  test    eax, eax
0x140004339  jnz     short loc_140004376
0x14000433b  call    cs:__imp_GetLastError
0x140004341  mov     edi, eax
0x140004343  lea     rax, WPP_GLOBAL_Control
0x14000434a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004351  cmp     rcx, rax
0x140004354  jz      loc_14000451E
0x14000435a  test    dword ptr [rcx+1Ch], 800h
0x140004361  jz      loc_14000451E
0x140004367  lea     edx, [r12+17h]
0x14000436c  mov     [rsp+0B8h+phkResult], rbx
0x140004371  jmp     loc_1400041EE
0x140004376  lea     r9, [rsp+0B8h+bDaclDefaulted]; lpbDaclDefaulted
0x14000437b  lea     r8, [rsp+0B8h+pDacl]; pDacl
0x140004383  lea     rdx, [rsp+0B8h+bDaclPresent]; lpbDaclPresent
0x140004388  mov     rcx, [rsp+0B8h+SecurityDescriptor]; pSecurityDescriptor
0x14000438d  call    cs:__imp_GetSecurityDescriptorDacl
0x140004393  test    eax, eax
0x140004395  jnz     short loc_1400043E0
0x140004397  call    cs:__imp_GetLastError
0x14000439d  mov     edi, eax
0x14000439f  lea     rax, WPP_GLOBAL_Control
0x1400043a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043ad  cmp     rcx, rax
0x1400043b0  jz      loc_14000451E
0x1400043b6  test    dword ptr [rcx+1Ch], 800h
0x1400043bd  jz      loc_14000451E
0x1400043c3  mov     edx, 19h
0x1400043c8  mov     r9d, edi
0x1400043cb  lea     r8, WPP_c8ab8980b27f3479e08bdbe236c5fb3b_Traceguids
0x1400043d2  mov     rcx, [rcx+10h]
0x1400043d6  call    WPP_SF_d
0x1400043db  jmp     loc_14000451E
0x1400043e0  cmp     [rsp+0B8h+bDaclPresent], esi
0x1400043e4  jz      loc_1400044EE
0x1400043ea  mov     rcx, [rsp+0B8h+pDacl]; pAcl
0x1400043f2  cmp     [rcx+4], r12w
0x1400043f7  jnz     loc_1400044EE
0x1400043fd  lea     r8, [rsp+0B8h+pAce]; pAce
0x140004402  xor     edx, edx; dwAceIndex
0x140004404  call    cs:__imp_GetAce
0x14000440a  test    eax, eax
0x14000440c  jnz     short loc_14000441B
0x14000440e  call    cs:__imp_GetLastError
0x140004414  mov     edi, eax
0x140004416  jmp     loc_14000451E
0x14000441b  mov     rax, [rsp+0B8h+pAce]
0x140004420  movzx   ecx, word ptr [rax+2]
0x140004424  call    AiAlloc
0x140004429  mov     [r14+18h], rax
0x14000442d  test    rax, rax
0x140004430  jnz     short loc_14000443C
0x140004432  mov     edi, 8
0x140004437  jmp     loc_14000451E
0x14000443c  mov     rdx, [rsp+0B8h+pAce]; Src
0x140004441  movzx   r8d, word ptr [rdx+2]; Size
0x140004446  mov     rcx, rax; void *
0x140004449  call    memcpy_0
0x14000444e  mov     rdx, r15; unsigned int *
0x140004451  mov     rcx, rbx; Str
0x140004454  call    ?UpdateAttributeMask@@YAXPEBGPEAK@Z; UpdateAttributeMask(ushort const *,ulong *)
0x140004459  mov     rcx, rbx; pbstr
0x14000445c  call    cs:__imp_SysStringLen
0x140004462  mov     ecx, 100h
0x140004467  cmp     eax, ecx
0x140004469  jbe     short loc_140004481
0x14000446b  mov     dword ptr [rbx+1FAh], 2E002Eh
0x140004475  mov     dword ptr [rbx+1FEh], 2Eh ; '.'
0x14000447f  mov     eax, ecx
0x140004481  lea     r15d, [rax+1]
0x140004485  add     r15, r15
0x140004488  mov     rcx, r15
0x14000448b  call    AiAlloc
0x140004490  mov     [r14+10h], rax
0x140004494  test    rax, rax
0x140004497  jz      short loc_140004432
0x140004499  mov     r8, r15; Size
0x14000449c  mov     rdx, rbx; Src
0x14000449f  mov     rcx, rax; void *
0x1400044a2  call    memcpy_0
0x1400044a7  mov     rcx, [rsp+0B8h+pbstr]; pbstr
0x1400044ac  call    cs:__imp_SysStringLen
0x1400044b2  cmp     eax, 7FFFh
0x1400044b7  jbe     short loc_1400044C0
0x1400044b9  mov     edi, 57h ; 'W'
0x1400044be  jmp     short loc_14000451E
0x1400044c0  lea     r15d, [rax+1]
0x1400044c4  add     r15, r15
0x1400044c7  mov     rcx, r15
0x1400044ca  call    AiAlloc
0x1400044cf  mov     [r14+8], rax
0x1400044d3  test    rax, rax
0x1400044d6  jz      loc_140004432
0x1400044dc  mov     r8, r15; Size
0x1400044df  mov     rdx, [rsp+0B8h+pbstr]; Src
0x1400044e4  mov     rcx, rax; void *
0x1400044e7  call    memcpy_0
0x1400044ec  jmp     short loc_14000451E
0x1400044ee  mov     edi, 57h ; 'W'
0x1400044f3  lea     rax, WPP_GLOBAL_Control
0x1400044fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140004501  cmp     rcx, rax
0x140004504  jz      short loc_14000451E
0x140004506  test    dword ptr [rcx+1Ch], 800h
0x14000450d  jz      short loc_14000451E
0x14000450f  lea     edx, [rdi-3Dh]
0x140004512  mov     r9, rbx
0x140004515  mov     rcx, [rcx+10h]
0x140004519  call    WPP_SF_S
0x14000451e  mov     rcx, [rsp+0B8h+SecurityDescriptor]; hMem
0x140004523  test    rcx, rcx
0x140004526  jz      short loc_14000452E
0x140004528  call    cs:__imp_LocalFree
0x14000452e  mov     rcx, [rsp+0B8h+var_78]
0x140004533  call    AiFree
0x140004538  mov     rcx, [rsp+0B8h+hKey]; hKey
0x14000453d  test    rcx, rcx
0x140004540  jz      short loc_140004549
0x140004542  call    cs:__imp_RegCloseKey
0x140004548  nop
0x140004549  mov     rcx, rbx; bstrString
0x14000454c  call    cs:__imp_SysFreeString
0x140004552  nop
0x140004553  mov     rcx, [rsp+0B8h+pbstr]; bstrString
0x140004558  call    cs:__imp_SysFreeString
0x14000455e  nop
0x14000455f  mov     rcx, [rsp+0B8h+bstrString]; bstrString
0x140004564  call    cs:__imp_SysFreeString
0x14000456a  mov     eax, edi
0x14000456c  mov     rbx, [rsp+0B8h+arg_0]
0x140004574  add     rsp, 90h
0x14000457b  pop     r15
0x14000457d  pop     r14
0x14000457f  pop     r12
0x140004581  pop     rdi
0x140004582  pop     rsi
0x140004583  retn
```
