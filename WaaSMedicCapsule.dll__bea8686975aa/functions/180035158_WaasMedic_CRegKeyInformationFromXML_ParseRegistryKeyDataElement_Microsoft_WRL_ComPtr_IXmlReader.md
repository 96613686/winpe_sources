# WaasMedic::CRegKeyInformationFromXML::ParseRegistryKeyDataElement(Microsoft::WRL::ComPtr<IXmlReader>)

- ea: `0x180035158`
- end: `0x180035808`
- name: `?ParseRegistryKeyDataElement@CRegKeyInformationFromXML@WaasMedic@@QEAAJV?$ComPtr@UIXmlReader@@@WRL@Microsoft@@@Z`
- size: `1712`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180034290`

## callees

- `0x180003bd4`
- `0x180003c18`
- `0x1800040b8`
- `0x180005ef1`
- `0x180009a54`
- `0x18000b308`
- `0x18000b6ec`
- `0x18002543c`
- `0x18003337c`
- `0x1800338d8`
- `0x180033e68`
- `0x180033f58`
- `0x180035158`
- `0x180035810`
- `0x180064010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180035785`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180035785`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800352aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800353c5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800354e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035551`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003562a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003570e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800352aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800353c5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800354e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035551`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003562a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003570e`

## string_xrefs

- `0x1800351d6`: `MoveToFirstAttribute failed on registryKey element.`
- `0x18003578f`: `MoveToFirstAttribute failed with hr = 0x%08x on registryKey element.`
- `0x1800355aa`: `	registryValue '%s' = '%s' found`
- `0x180035703`: `securityDescriptorDefinition`
- `0x18003533f`: `registryValue`
- `0x1800353ba`: `registryValue`
- `0x18003566a`: `registryValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaasMedic::CRegKeyInformationFromXML::ParseRegistryKeyDataElement(char **a1, _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // r8
  void *v8; // r9
  unsigned __int64 v9; // rdx
  char *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rcx
  _OWORD *v13; // rax
  _OWORD *v14; // rdi
  WaasMedic::CRegistryValueFromXML *v15; // r15
  int v16; // eax
  __int64 v17; // r8
  void *v18; // r9
  unsigned __int64 v19; // rdx
  char *v20; // r14
  __int64 v21; // rbx
  void **v22; // rcx
  unsigned int *v23; // r8
  int v24; // eax
  _QWORD *v25; // rbx
  _QWORD *v26; // r9
  _OWORD *v27; // r8
  char *v28; // rbx
  char **v29; // rax
  char *v30; // rcx
  __int64 v31; // rdx
  unsigned __int16 *v32; // rax
  int v33; // edx
  void *v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v40; // [rsp+20h] [rbp-40h]
  const char *v41; // [rsp+28h] [rbp-38h]
  _WORD *v42; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v43[3]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v44; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int v46; // [rsp+B0h] [rbp+50h] BYREF
  void *Src; // [rsp+B8h] [rbp+58h] BYREF

  if ( !*a2 )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E5,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)0x80004003LL,
      v40);
    v5 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return v4;
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 64LL))(*a2);
  if ( (v4 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x4E8,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)v4,
      (int)"MoveToFirstAttribute failed on registryKey element.",
      v41);
    v6 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v4;
  }
  while ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 152LL))(*a2) )
  {
LABEL_26:
    v4 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 72LL))(*a2);
    if ( v4 )
      goto LABEL_27;
  }
  v43[0] = 0;
  Src = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, v43, 0);
  if ( (v4 & 0x80000000) == 0 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, void **, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, &Src, 0);
    if ( (v4 & 0x80000000) == 0 )
    {
      if ( v43[0] && *(_WORD *)v43[0] && Src && *(_WORD *)Src )
      {
        if ( (unsigned int)_o__wcsicmp(v43[0], L"keyName") )
        {
          LogLevelW(3u, L"Unexpected attribute for %s. Ignoring.", L"keyName");
        }
        else
        {
          v8 = Src;
          v9 = -1;
          do
            ++v9;
          while ( *((_WORD *)Src + v9) );
          if ( v9 > (unsigned __int64)a1[3] )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              a1,
              v9,
              v7,
              Src);
          }
          else
          {
            if ( (unsigned __int64)a1[3] <= 7 )
              v10 = (char *)a1;
            else
              v10 = *a1;
            a1[2] = (char *)v9;
            v11 = 2 * v9;
            memmove_0(v10, v8, 2 * v9);
            *(_WORD *)&v10[v11] = 0;
          }
        }
      }
      goto LABEL_26;
    }
  }
LABEL_27:
  if ( v4 > 1 )
  {
    LogLevelW(
      2u,
      L"Unexpected failure while iterating through attributes for %s with hr = 0x%08x.",
      L"registryValue",
      v4);
    v12 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v4;
  }
  v46 = 0;
  while ( 1 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a2 + 48LL))(*a2, &v46);
    if ( v4 )
      break;
    v43[0] = 0;
    if ( v46 != 1 || (*(int (__fastcall **)(_QWORD, _QWORD *, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, v43, 0) < 0 )
      continue;
    if ( !(unsigned int)_o__wcsicmp(v43[0], L"registryValue") )
    {
      v13 = operator new(v4 + 104, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      Src = v13;
      if ( v13 )
      {
        *v13 = 0;
        *((_QWORD *)v13 + 2) = 0;
        *((_QWORD *)v13 + 3) = 7;
        *(_WORD *)v13 = 0;
        *((_DWORD *)v13 + 8) = 0;
        *(_OWORD *)((char *)v13 + 40) = 0;
        *((_QWORD *)v13 + 7) = 0;
        *((_QWORD *)v13 + 8) = 7;
        *((_WORD *)v13 + 20) = 0;
        *((_DWORD *)v13 + 18) = 0;
        *((_QWORD *)v13 + 10) = 0;
        *((_QWORD *)v13 + 11) = 0;
        *((_QWORD *)v13 + 12) = 0;
      }
      else
      {
        v14 = 0;
      }
      v15 = (WaasMedic::CRegistryValueFromXML *)v14;
      v43[1] = v14;
      v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 64LL))(*a2);
      v4 = v16;
      if ( v16 < 0 )
      {
        LogLevelW(2u, L"MoveToFirstAttribute failed with hr = 0x%08x on registryKey element.", (unsigned int)v16);
        if ( v14 )
        {
          WaasMedic::CRegistryValueFromXML::~CRegistryValueFromXML((WaasMedic::CRegistryValueFromXML *)v14);
          operator delete(v14, (const struct std::nothrow_t *)0x68);
        }
        v37 = *a2;
        if ( *a2 )
        {
          *a2 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        }
        return v4;
      }
LABEL_40:
      if ( !(*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 152LL))(*a2) )
      {
        v42 = 0;
        Src = 0;
        if ( (*(int (__fastcall **)(_QWORD, _WORD **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &v42, 0) < 0
          || (*(int (__fastcall **)(_QWORD, void **, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, &Src, 0) < 0 )
        {
          goto LABEL_61;
        }
        if ( v42 && *v42 && Src && *(_WORD *)Src )
        {
          if ( (unsigned int)_o__wcsicmp(v42, L"name") )
          {
            if ( (unsigned int)_o__wcsicmp(v42, L"valueType") )
            {
              if ( (unsigned int)_o__wcsicmp(v42, L"value") )
              {
                LogLevelW(3u, L"Unexpected attribute %s for %s.  Ignoring.", v42, L"registryValue");
              }
              else
              {
                v18 = Src;
                v22 = (void **)v14 + 5;
                v19 = -1;
                do
                  ++v19;
                while ( *((_WORD *)Src + v19) );
                if ( v19 > *((_QWORD *)v14 + 8) )
                  goto LABEL_57;
                v20 = (char *)v14 + 40;
                if ( *((_QWORD *)v14 + 8) > 7u )
                  v20 = (char *)*v22;
                *((_QWORD *)v14 + 7) = v19;
LABEL_55:
                v21 = 2 * v19;
                memmove_0(v20, v18, 2 * v19);
                *(_WORD *)&v20[v21] = 0;
              }
            }
            else
            {
              v24 = WaasMedic::ConvertToRegValueType((WaasMedic *)Src, (const unsigned __int16 *)v14 + 16, v23);
              if ( v24 < 0 )
              {
                LogLevelW(2u, L"ConvertToRegValueType failed for %s with hr = 0x%08x", Src, (unsigned int)v24);
LABEL_61:
                v25 = (_QWORD *)v14 + 5;
                v26 = (_QWORD *)v14 + 5;
                if ( *((_QWORD *)v14 + 8) > 7u )
                  v26 = (_QWORD *)*v25;
                v27 = v14;
                if ( *((_QWORD *)v14 + 3) > 7u )
                  v27 = *(_OWORD **)v14;
                LogLevelW(4u, L"\tregistryValue '%s' = '%s' found", v27, v26);
                if ( (int)WaasMedic::CRegistryValueFromXML::ConvertRegValueFromXmlToRealType((WaasMedic::CRegistryValueFromXML *)v14) < 0 )
                {
                  if ( *((_QWORD *)v14 + 3) <= 7u )
                    LODWORD(v31) = (_DWORD)v14;
                  else
                    v31 = *(_QWORD *)v14;
                  if ( *((_QWORD *)v14 + 8) > 7u )
                    v25 = (_QWORD *)*v25;
                  v32 = WaasMedic::ConvertToRegValueTypeToString((WaasMedic *)*((unsigned int *)v14 + 8), v31);
                  v40 = v33;
                  LogLevelW(3u, L"Failed to convert to %s from string %s for regKey value %s.", v32, v25);
                }
                else
                {
                  if ( a1[9] == (char *)0xAAAAAAAAAAAAAAALL )
                    std::_Xlength_error("list too long");
                  v28 = a1[8];
                  v43[2] = a1 + 8;
                  v44 = 0;
                  v29 = (char **)operator new(0x18u);
                  v15 = 0;
                  v29[2] = (char *)v14;
                  ++a1[9];
                  v30 = (char *)*((_QWORD *)v28 + 1);
                  *v29 = v28;
                  v29[1] = v30;
                  v44 = 0;
                  *((_QWORD *)v28 + 1) = v29;
                  *(_QWORD *)v30 = v29;
                }
                if ( v15 )
                {
                  WaasMedic::CRegistryValueFromXML::~CRegistryValueFromXML(v15);
                  operator delete(v15, (const struct std::nothrow_t *)0x68);
                }
                continue;
              }
            }
          }
          else
          {
            v18 = Src;
            v19 = -1;
            do
              ++v19;
            while ( *((_WORD *)Src + v19) );
            if ( v19 <= *((_QWORD *)v14 + 3) )
            {
              if ( *((_QWORD *)v14 + 3) <= 7u )
                v20 = (char *)v14;
              else
                v20 = *(char **)v14;
              *((_QWORD *)v14 + 2) = v19;
              goto LABEL_55;
            }
            v22 = (void **)v14;
LABEL_57:
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              v22,
              v19,
              v17,
              v18);
          }
        }
      }
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 72LL))(*a2) )
        goto LABEL_61;
      goto LABEL_40;
    }
    if ( !(unsigned int)_o__wcsicmp(v43[0], L"securityDescriptorDefinition") )
    {
      v34 = (void *)*a2;
      Src = v34;
      if ( v34 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 8LL))(v34);
      v35 = WaasMedic::CRegKeyInformationFromXML::ParseSecurityDescriptorDefinitions(a1, &Src);
      v4 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x559,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
          (const char *)(unsigned int)v35,
          v40);
        v36 = *a2;
        if ( *a2 )
        {
          *a2 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        }
        return v4;
      }
    }
  }
  v38 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  return v4;
}

```

## disassembly

```asm
0x180035158  mov     [rsp-38h+arg_0], rbx
0x18003515d  mov     [rsp-38h+arg_8], rdx
0x180035162  push    rbp
0x180035163  push    rsi
0x180035164  push    rdi
0x180035165  push    r12
0x180035167  push    r13
0x180035169  push    r14
0x18003516b  push    r15
0x18003516d  mov     rbp, rsp
0x180035170  sub     rsp, 60h
0x180035174  mov     rsi, rdx
0x180035177  mov     r12, rcx
0x18003517a  mov     rcx, [rdx]
0x18003517d  xor     r13d, r13d
0x180035180  test    rcx, rcx
0x180035183  jnz     short loc_1800351C0
0x180035185  mov     rcx, [rbp+38h]; this
0x180035189  mov     ebx, 80004003h
0x18003518e  mov     r9d, ebx; char *
0x180035191  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180035198  mov     edx, 4E5h; void *
0x18003519d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800351a2  nop
0x1800351a3  mov     rcx, [rsi]
0x1800351a6  test    rcx, rcx
0x1800351a9  jz      short loc_1800351BB
0x1800351ab  mov     [rsi], r13
0x1800351ae  mov     rdx, [rcx]
0x1800351b1  mov     rax, [rdx+10h]
0x1800351b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351ba  nop
0x1800351bb  jmp     loc_1800357EE
0x1800351c0  mov     rax, [rcx]
0x1800351c3  mov     rax, [rax+40h]
0x1800351c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351cc  mov     ebx, eax
0x1800351ce  test    eax, eax
0x1800351d0  jns     short loc_180035214
0x1800351d2  mov     rcx, [rbp+38h]; this
0x1800351d6  lea     rax, aMovetofirstatt; "MoveToFirstAttribute failed on registry"...
0x1800351dd  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800351e2  mov     r9d, ebx; char *
0x1800351e5  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800351ec  mov     edx, 4E8h; void *
0x1800351f1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800351f6  nop
0x1800351f7  mov     rcx, [rsi]
0x1800351fa  test    rcx, rcx
0x1800351fd  jz      short loc_18003520F
0x1800351ff  mov     [rsi], r13
0x180035202  mov     rax, [rcx]
0x180035205  mov     rax, [rax+10h]
0x180035209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003520e  nop
0x18003520f  jmp     loc_1800357EE
0x180035214  mov     rcx, [rsi]
0x180035217  mov     rax, [rcx]
0x18003521a  mov     rax, [rax+98h]
0x180035221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035226  test    eax, eax
0x180035228  jnz     loc_18003531E
0x18003522e  mov     [rbp+var_28], r13
0x180035232  mov     [rbp+Src], r13
0x180035236  mov     rcx, [rsi]
0x180035239  mov     rax, [rcx]
0x18003523c  xor     r8d, r8d
0x18003523f  lea     rdx, [rbp+var_28]
0x180035243  mov     rax, [rax+70h]
0x180035247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003524c  mov     ebx, eax
0x18003524e  test    eax, eax
0x180035250  js      loc_180035337
0x180035256  mov     rcx, [rsi]
0x180035259  mov     rax, [rcx]
0x18003525c  xor     r8d, r8d
0x18003525f  lea     rdx, [rbp+Src]
0x180035263  mov     rax, [rax+80h]
0x18003526a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003526f  mov     ebx, eax
0x180035271  test    eax, eax
0x180035273  js      loc_180035337
0x180035279  mov     rcx, [rbp+var_28]
0x18003527d  test    rcx, rcx
0x180035280  jz      loc_18003531E
0x180035286  cmp     r13w, [rcx]
0x18003528a  jz      loc_18003531E
0x180035290  mov     rdx, [rbp+Src]
0x180035294  test    rdx, rdx
0x180035297  jz      loc_18003531E
0x18003529d  cmp     r13w, [rdx]
0x1800352a1  jz      short loc_18003531E
0x1800352a3  lea     rdx, aKeyname; "keyName"
0x1800352aa  call    cs:__imp__o__wcsicmp
0x1800352b0  test    eax, eax
0x1800352b2  jnz     short loc_180035306
0x1800352b4  mov     r9, [rbp+Src]
0x1800352b8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800352bc  inc     rdx
0x1800352bf  cmp     [r9+rdx*2], r13w
0x1800352c4  jnz     short loc_1800352BC
0x1800352c6  cmp     rdx, [r12+18h]
0x1800352cb  ja      short loc_1800352FC
0x1800352cd  cmp     qword ptr [r12+18h], 7
0x1800352d3  jbe     short loc_1800352DB
0x1800352d5  mov     rdi, [r12]
0x1800352d9  jmp     short loc_1800352DE
0x1800352db  mov     rdi, r12
0x1800352de  mov     [r12+10h], rdx
0x1800352e3  lea     rbx, [rdx+rdx]
0x1800352e7  mov     r8, rbx; Size
0x1800352ea  mov     rdx, r9; Src
0x1800352ed  mov     rcx, rdi; void *
0x1800352f0  call    memmove_0
0x1800352f5  mov     [rbx+rdi], r13w
0x1800352fa  jmp     short loc_18003531E
0x1800352fc  mov     rcx, r12
0x1800352ff  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180035304  jmp     short loc_18003531E
0x180035306  lea     r8, aKeyname; "keyName"
0x18003530d  lea     rdx, aUnexpectedAttr_0; "Unexpected attribute for %s. Ignoring."
0x180035314  mov     ecx, 3; unsigned __int8
0x180035319  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003531e  mov     rcx, [rsi]
0x180035321  mov     rax, [rcx]
0x180035324  mov     rax, [rax+48h]
0x180035328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003532d  mov     ebx, eax
0x18003532f  test    eax, eax
0x180035331  jz      loc_180035214
0x180035337  cmp     ebx, 1
0x18003533a  jbe     short loc_180035375
0x18003533c  mov     r9d, ebx
0x18003533f  lea     r8, aRegistryvalue; "registryValue"
0x180035346  lea     rdx, aUnexpectedFail_0; "Unexpected failure while iterating thro"...
0x18003534d  mov     ecx, 2; unsigned __int8
0x180035352  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035357  nop
0x180035358  mov     rcx, [rsi]
0x18003535b  test    rcx, rcx
0x18003535e  jz      short loc_180035370
0x180035360  mov     [rsi], r13
0x180035363  mov     rax, [rcx]
0x180035366  mov     rax, [rax+10h]
0x18003536a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003536f  nop
0x180035370  jmp     loc_1800357EE
0x180035375  mov     [rbp+arg_10], r13d
0x180035379  mov     rcx, [rsi]
0x18003537c  mov     rax, [rcx]
0x18003537f  lea     rdx, [rbp+arg_10]
0x180035383  mov     rax, [rax+30h]
0x180035387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003538c  mov     ebx, eax
0x18003538e  test    eax, eax
0x180035390  jnz     loc_1800357D6
0x180035396  mov     [rbp+var_28], r13
0x18003539a  cmp     [rbp+arg_10], 1
0x18003539e  jnz     short loc_180035379
0x1800353a0  mov     rcx, [rsi]
0x1800353a3  mov     rax, [rcx]
0x1800353a6  xor     r8d, r8d
0x1800353a9  lea     rdx, [rbp+var_28]
0x1800353ad  mov     rax, [rax+70h]
0x1800353b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800353b6  test    eax, eax
0x1800353b8  js      short loc_180035379
0x1800353ba  lea     rdx, aRegistryvalue; "registryValue"
0x1800353c1  mov     rcx, [rbp+var_28]
0x1800353c5  call    cs:__imp__o__wcsicmp
0x1800353cb  test    eax, eax
0x1800353cd  jnz     loc_180035703
0x1800353d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800353da  lea     ecx, [rbx+68h]; unsigned __int64
0x1800353dd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800353e2  mov     rdi, rax
0x1800353e5  mov     [rbp+Src], rax
0x1800353e9  test    rax, rax
0x1800353ec  jz      short loc_18003542F
0x1800353ee  xorps   xmm0, xmm0
0x1800353f1  movups  xmmword ptr [rax], xmm0
0x1800353f4  mov     [rax+10h], r13
0x1800353f8  mov     qword ptr [rax+18h], 7
0x180035400  mov     [rax], r13w
0x180035404  mov     [rax+20h], r13d
0x180035408  movups  xmmword ptr [rax+28h], xmm0
0x18003540c  mov     [rax+38h], r13
0x180035410  mov     qword ptr [rax+40h], 7
0x180035418  mov     [rax+28h], r13w
0x18003541d  mov     [rax+48h], r13d
0x180035421  mov     [rax+50h], r13
0x180035425  mov     [rax+58h], r13
0x180035429  mov     [rax+60h], r13
0x18003542d  jmp     short loc_180035432
0x18003542f  mov     rdi, r13
0x180035432  mov     r15, rdi
0x180035435  mov     [rbp+var_20], rdi
0x180035439  mov     rcx, [rsi]
0x18003543c  mov     rax, [rcx]
0x18003543f  mov     rax, [rax+40h]
0x180035443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035448  mov     ebx, eax
0x18003544a  test    eax, eax
0x18003544c  js      loc_18003578C
0x180035452  mov     rcx, [rsi]
0x180035455  mov     rax, [rcx]
0x180035458  mov     rax, [rax+98h]
0x18003545f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035464  test    eax, eax
0x180035466  jnz     loc_180035686
0x18003546c  mov     [rbp+var_30], r13
0x180035470  mov     [rbp+Src], r13
0x180035474  mov     rcx, [rsi]
0x180035477  mov     rax, [rcx]
0x18003547a  xor     r8d, r8d
0x18003547d  lea     rdx, [rbp+var_30]
0x180035481  mov     rax, [rax+70h]
0x180035485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003548a  test    eax, eax
0x18003548c  js      loc_18003558C
0x180035492  mov     rcx, [rsi]
0x180035495  mov     rax, [rcx]
0x180035498  xor     r8d, r8d
0x18003549b  lea     rdx, [rbp+Src]
0x18003549f  mov     rax, [rax+80h]
0x1800354a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354ab  test    eax, eax
0x1800354ad  js      loc_18003558C
0x1800354b3  mov     rcx, [rbp+var_30]
0x1800354b7  test    rcx, rcx
0x1800354ba  jz      loc_180035686
0x1800354c0  cmp     r13w, [rcx]
0x1800354c4  jz      loc_180035686
0x1800354ca  mov     rdx, [rbp+Src]
0x1800354ce  test    rdx, rdx
0x1800354d1  jz      loc_180035686
0x1800354d7  cmp     r13w, [rdx]
0x1800354db  jz      loc_180035686
0x1800354e1  lea     rdx, aName; "name"
0x1800354e8  call    cs:__imp__o__wcsicmp
0x1800354ee  test    eax, eax
0x1800354f0  jnz     short loc_180035546
0x1800354f2  mov     r9, [rbp+Src]
0x1800354f6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800354fa  inc     rdx
0x1800354fd  cmp     [r9+rdx*2], r13w
0x180035502  jnz     short loc_1800354FA
0x180035504  cmp     rdx, [rdi+18h]
0x180035508  ja      short loc_180035539
0x18003550a  cmp     qword ptr [rdi+18h], 7
0x18003550f  jbe     short loc_180035516
0x180035511  mov     r14, [rdi]
0x180035514  jmp     short loc_180035519
0x180035516  mov     r14, rdi
0x180035519  mov     [rdi+10h], rdx
0x18003551d  lea     rbx, [rdx+rdx]
0x180035521  mov     r8, rbx; Size
0x180035524  mov     rdx, r9; Src
0x180035527  mov     rcx, r14; void *
0x18003552a  call    memmove_0
0x18003552f  mov     [rbx+r14], r13w
0x180035534  jmp     loc_180035686
0x180035539  mov     rcx, rdi
0x18003553c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180035541  jmp     loc_180035686
0x180035546  lea     rdx, aValuetype; "valueType"
0x18003554d  mov     rcx, [rbp+var_30]
0x180035551  call    cs:__imp__o__wcsicmp
0x180035557  test    eax, eax
0x180035559  jnz     loc_18003561F
0x18003555f  lea     rdx, [rdi+20h]; unsigned __int16 *
0x180035563  mov     rcx, [rbp+Src]; this
0x180035567  call    ?ConvertToRegValueType@WaasMedic@@YAJPEBGPEAK@Z; WaasMedic::ConvertToRegValueType(ushort const *,ulong *)
0x18003556c  test    eax, eax
0x18003556e  jns     loc_180035686
0x180035574  mov     r9d, eax
0x180035577  mov     r8, [rbp+Src]
0x18003557b  lea     rdx, aConverttoregva; "ConvertToRegValueType failed for %s wit"...
0x180035582  mov     ecx, 2; unsigned __int8
0x180035587  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003558c  lea     rbx, [rdi+28h]
0x180035590  mov     r9, rbx
0x180035593  cmp     qword ptr [rbx+18h], 7
0x180035598  jbe     short loc_18003559D
0x18003559a  mov     r9, [rbx]
0x18003559d  mov     r8, rdi
0x1800355a0  cmp     qword ptr [rdi+18h], 7
0x1800355a5  jbe     short loc_1800355AA
0x1800355a7  mov     r8, [rdi]
0x1800355aa  lea     rdx, aRegistryvalueS_0; "\tregistryValue '%s' = '%s' found"
0x1800355b1  mov     ecx, 4; unsigned __int8
0x1800355b6  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800355bb  mov     rcx, rdi; this
0x1800355be  call    ?ConvertRegValueFromXmlToRealType@CRegistryValueFromXML@WaasMedic@@QEAAJXZ; WaasMedic::CRegistryValueFromXML::ConvertRegValueFromXmlToRealType(void)
0x1800355c3  test    eax, eax
0x1800355c5  js      loc_1800356A2
0x1800355cb  lea     r14, [r12+40h]
0x1800355d0  mov     rax, 0AAAAAAAAAAAAAAAh
0x1800355da  cmp     [r14+8], rax
0x1800355de  jz      loc_18003577E
  ... truncated ...
```
