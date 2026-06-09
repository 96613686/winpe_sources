# ShieldProvider::FirewallManager::GetPillarStatusEx(PillarStatusEx * *)

- ea: `0x180049ee4`
- end: `0x18004a669`
- name: `?GetPillarStatusEx@FirewallManager@ShieldProvider@@QEAAJPEAPEAUPillarStatusEx@@@Z`
- size: `1925`
- prototype: `__int64 __fastcall(ShieldProvider::FirewallManager *__hidden this, struct PillarStatusEx **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045fd0`

## callees

- `0x18000d7fc`
- `0x180037d70`
- `0x1800489d8`
- `0x180049ee4`
- `0x18004a670`
- `0x1800e1764`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a0cb`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a0f2`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a2cd`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a318`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a36e`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a3ca`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a434`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a0cb`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a0f2`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a2cd`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a318`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a36e`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a3ca`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18004a434`
- `ole32!CoTaskMemFree` at `0x180049fa3`
- `ole32!CoTaskMemFree` at `0x180049fb6`
- `ole32!CoTaskMemFree` at `0x180049fc3`
- `ole32!CoTaskMemFree` at `0x18004a03c`
- `ole32!CoTaskMemFree` at `0x18004a04f`
- `ole32!CoTaskMemFree` at `0x18004a05c`
- `ole32!CoTaskMemFree` at `0x18004a180`
- `ole32!CoTaskMemFree` at `0x18004a197`
- `ole32!CoTaskMemFree` at `0x18004a1a8`
- `ole32!CoTaskMemFree` at `0x18004a54d`
- `ole32!CoTaskMemFree` at `0x18004a564`
- `ole32!CoTaskMemFree` at `0x180049fa3`
- `ole32!CoTaskMemFree` at `0x180049fb6`
- `ole32!CoTaskMemFree` at `0x180049fc3`
- `ole32!CoTaskMemFree` at `0x18004a03c`
- `ole32!CoTaskMemFree` at `0x18004a04f`
- `ole32!CoTaskMemFree` at `0x18004a05c`
- `ole32!CoTaskMemFree` at `0x18004a180`
- `ole32!CoTaskMemFree` at `0x18004a197`
- `ole32!CoTaskMemFree` at `0x18004a1a8`
- `ole32!CoTaskMemFree` at `0x18004a54d`
- `ole32!CoTaskMemFree` at `0x18004a564`

## pseudocode

```c
__int64 __fastcall ShieldProvider::FirewallManager::GetPillarStatusEx(
        ShieldProvider::FirewallManager *this,
        struct PillarStatusEx **a2)
{
  ShieldProvider::FirewallManager *v4; // rcx
  int v5; // edi
  _QWORD *v6; // rbx
  void *v7; // rcx
  void *v8; // rcx
  struct tagFIREWALL_PROFILE_STATUS_EX *v9; // rdx
  unsigned __int16 *v10; // r8
  int PillarSubstatus; // r12d
  _QWORD *v12; // rbx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  ShieldProvider *v16; // rbx
  int v17; // eax
  int v18; // ecx
  wchar_t *v19; // rdx
  wchar_t *v20; // r14
  unsigned __int16 **v21; // r15
  const wchar_t *v22; // rdx
  _QWORD *v23; // rdi
  int v24; // r14d
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  void *v27; // rcx
  void *v28; // rcx
  wchar_t *v29; // rcx
  unsigned int v30; // edi
  unsigned int v31; // r15d
  wchar_t *v32; // r13
  struct tagFIREWALL_PROFILE_STATUS_EX *v33; // r9
  __int64 v34; // r8
  const wchar_t *v35; // rdx
  int v36; // eax
  unsigned int v37; // ecx
  wchar_t *v38; // rcx
  const wchar_t *v39; // rdx
  int v40; // eax
  unsigned int v41; // ecx
  unsigned __int16 **v42; // rcx
  struct tagFIREWALL_PROFILE_STATUS_EX *v43; // rdx
  wchar_t *v44; // rax
  _DWORD *v45; // rdi
  unsigned __int16 **v46; // r14
  const wchar_t *v47; // rdx
  int v48; // eax
  unsigned int v49; // ecx
  struct tagFIREWALL_PROFILE_STATUS_EX *v50; // r9
  const wchar_t *v51; // rdx
  int v52; // eax
  unsigned int v53; // ecx
  bool v54; // zf
  bool v55; // cc
  _QWORD *v56; // rcx
  __int64 v57; // rdx
  void *v58; // rcx
  void *v59; // rcx
  struct PillarStatusEx *v60; // rax
  unsigned __int16 **v61; // [rsp+20h] [rbp-18h]
  struct tagFIREWALL_PROFILE_STATUS_EX *v62; // [rsp+28h] [rbp-10h]
  ShieldProvider *v63; // [rsp+80h] [rbp+48h] BYREF
  struct PillarStatusEx **v64; // [rsp+88h] [rbp+50h]
  LPVOID pv; // [rsp+90h] [rbp+58h] BYREF
  wchar_t *String2; // [rsp+98h] [rbp+60h]

  v64 = a2;
  v63 = this;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids, 2147942487LL);
    return 2147942487LL;
  }
  pv = 0;
  v5 = CommonUtil::UtilCoTaskMemAllocObject<PillarStatusEx>(&pv);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
        (unsigned int)v5);
    v6 = pv;
    if ( pv )
    {
      v7 = (void *)*((_QWORD *)pv + 1);
      if ( v7 )
      {
        CoTaskMemFree(v7);
        v6[1] = 0;
      }
      v8 = (void *)v6[2];
      if ( v8 )
      {
        CoTaskMemFree(v8);
        v6[2] = 0;
      }
      CoTaskMemFree(v6);
    }
    return (unsigned int)v5;
  }
  v63 = 0;
  PillarSubstatus = ShieldProvider::FirewallManager::GetPillarSubstatusEx(v4, &v63);
  if ( PillarSubstatus < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
        (unsigned int)PillarSubstatus);
    if ( v63 )
      ShieldProvider::FreeFirewallProfileStatusEx(v63, v9);
    v12 = pv;
    if ( !pv )
      return (unsigned int)PillarSubstatus;
    v13 = (void *)*((_QWORD *)pv + 1);
    if ( v13 )
    {
      CoTaskMemFree(v13);
      v12[1] = 0;
    }
    v14 = (void *)v12[2];
    if ( v14 )
    {
      CoTaskMemFree(v14);
      v12[2] = 0;
    }
    v15 = v12;
    goto LABEL_29;
  }
  v16 = v63;
  v17 = *((_DWORD *)v63 + 1);
  v18 = *((_DWORD *)v63 + 7);
  v19 = (wchar_t *)*((unsigned int *)v63 + 13);
  LODWORD(v63) = v18;
  if ( v17 != 1 || (_DWORD)v19 != 1 || v18 != 1 )
  {
    if ( *(_DWORD *)v16 == 100 || *((_DWORD *)v16 + 12) == 100 || *((_DWORD *)v16 + 6) == 100 )
    {
      v60 = (struct PillarStatusEx *)pv;
      *((_DWORD *)pv + 1) = 8;
      *(_DWORD *)v60 = 100;
      *((_QWORD *)v60 + 1) = 0;
      *((_QWORD *)v60 + 2) = 0;
    }
    else
    {
      if ( *(_DWORD *)v16 != 99 && *((_DWORD *)v16 + 12) != 99 && *((_DWORD *)v16 + 6) != 99 )
      {
        v29 = 0;
        String2 = 0;
        v30 = 0;
        v62 = 0;
        if ( v17 == 8 )
        {
          v31 = 1;
          v32 = (wchar_t *)*((_QWORD *)v16 + 1);
          v61 = (unsigned __int16 **)*((_QWORD *)v16 + 2);
        }
        else
        {
          v31 = 0;
          v61 = 0;
          v32 = 0;
          if ( v17 == 4 )
          {
            v29 = (wchar_t *)*((_QWORD *)v16 + 1);
            v30 = 1;
            v33 = (struct tagFIREWALL_PROFILE_STATUS_EX *)*((_QWORD *)v16 + 2);
            String2 = v29;
            v62 = v33;
          }
        }
        v34 = 32;
        if ( (_DWORD)v19 == 8 )
        {
          if ( !v31 )
          {
            v31 = 1;
            v32 = (wchar_t *)*((_QWORD *)v16 + 7);
            v61 = (unsigned __int16 **)*((_QWORD *)v16 + 8);
            goto LABEL_85;
          }
          if ( !v32 || (v35 = (const wchar_t *)*((_QWORD *)v16 + 7)) == 0 )
          {
            ++v31;
            goto LABEL_85;
          }
          v36 = _wcsnicmp(v32, v35, 0x20u);
          v37 = v31 + 1;
          if ( !v36 )
            v37 = v31;
          v31 = v37;
        }
        else
        {
          if ( (_DWORD)v19 != 4 )
            goto LABEL_85;
          if ( !v30 )
          {
            v38 = (wchar_t *)*((_QWORD *)v16 + 7);
            v30 = 1;
            v50 = (struct tagFIREWALL_PROFILE_STATUS_EX *)*((_QWORD *)v16 + 8);
            String2 = v38;
            v62 = v50;
LABEL_86:
            if ( (_DWORD)v63 == 8 )
            {
              if ( !v31 )
              {
                v42 = (unsigned __int16 **)*((_QWORD *)v16 + 5);
                v31 = 1;
                v32 = (wchar_t *)*((_QWORD *)v16 + 4);
                v61 = v42;
                goto LABEL_94;
              }
              if ( v32 && (v39 = (const wchar_t *)*((_QWORD *)v16 + 4)) != 0 )
              {
                v40 = _wcsnicmp(v32, v39, 0x20u);
                v41 = v31 + 1;
                if ( !v40 )
                  v41 = v31;
                v31 = v41;
              }
              else
              {
                ++v31;
              }
            }
            else if ( (_DWORD)v63 == 4 )
            {
              if ( !v30 )
              {
                v44 = (wchar_t *)*((_QWORD *)v16 + 4);
                v30 = 1;
                v43 = (struct tagFIREWALL_PROFILE_STATUS_EX *)*((_QWORD *)v16 + 5);
                v42 = v61;
LABEL_95:
                v63 = 0;
                if ( v31 == 1 )
                {
                  if ( v30 == 1 )
                  {
                    if ( v32 && v44 && !_wcsnicmp(v32, v44, 0x20u) )
                    {
                      v45 = pv;
                      *((_DWORD *)pv + 1) = 8;
                      v46 = v61;
                      *v45 = 98;
                      goto LABEL_135;
                    }
                    v45 = pv;
                    v32 = 0;
                    *((_DWORD *)pv + 1) = 8;
                    v46 = 0;
                    *v45 = 100;
                    goto LABEL_134;
                  }
                }
                else if ( !v31 )
                {
LABEL_127:
                  if ( v31 <= 1 )
                  {
                    if ( v31 == 1 )
                    {
                      v45 = pv;
                      *((_DWORD *)pv + 1) = 8;
                      v46 = v42;
                      *v45 = 98;
                    }
                    else
                    {
                      v54 = v30 == 1;
                      v55 = v30 <= 1;
                      v45 = pv;
                      if ( !v55 )
                      {
                        *((_DWORD *)pv + 1) = 4;
                        *v45 = 99;
                        goto LABEL_147;
                      }
                      if ( !v54 )
                      {
                        *((_DWORD *)pv + 1) = 2;
                        *v45 = 96;
                        goto LABEL_147;
                      }
                      *((_DWORD *)pv + 1) = 4;
                      v32 = v44;
                      *v45 = 97;
                      v46 = (unsigned __int16 **)v43;
                    }
LABEL_134:
                    if ( v32 )
                    {
LABEL_135:
                      PillarSubstatus = CommonUtil::UtilCoDuplicateString(
                                          (CommonUtil *)(v45 + 2),
                                          (unsigned __int16 **)v32,
                                          (unsigned __int16 *)v34);
                      if ( PillarSubstatus < 0 )
                      {
                        v56 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                          goto LABEL_140;
                        v57 = 91;
LABEL_139:
                        WPP_SF_d(
                          v56[2],
                          v57,
                          &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
                          (unsigned int)PillarSubstatus);
LABEL_140:
                        ShieldProvider::FreeFirewallProfileStatusEx(v16, v43);
                        if ( !v45 )
                          return (unsigned int)PillarSubstatus;
                        v58 = (void *)*((_QWORD *)v45 + 1);
                        if ( v58 )
                        {
                          CoTaskMemFree(v58);
                          *((_QWORD *)v45 + 1) = 0;
                        }
                        v59 = (void *)*((_QWORD *)v45 + 2);
                        if ( v59 )
                        {
                          CoTaskMemFree(v59);
                          *((_QWORD *)v45 + 2) = 0;
                        }
                        v15 = v45;
LABEL_29:
                        CoTaskMemFree(v15);
                        return (unsigned int)PillarSubstatus;
                      }
LABEL_149:
                      if ( v46 )
                      {
                        PillarSubstatus = CommonUtil::UtilCoDuplicateString(
                                            (CommonUtil *)(v45 + 4),
                                            v46,
                                            (unsigned __int16 *)v34);
                        if ( PillarSubstatus < 0 )
                        {
                          v56 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                          {
                            goto LABEL_140;
                          }
                          v57 = 92;
                          goto LABEL_139;
                        }
                      }
                      else
                      {
                        *((_QWORD *)v45 + 2) = 0;
                      }
                      *v64 = (struct PillarStatusEx *)v45;
                      ShieldProvider::FreeFirewallProfileStatusEx(v16, v43);
                      return (unsigned int)PillarSubstatus;
                    }
LABEL_148:
                    *((_QWORD *)v45 + 1) = 0;
                    goto LABEL_149;
                  }
LABEL_126:
                  v45 = pv;
                  *((_DWORD *)pv + 1) = 8;
                  *v45 = 100;
LABEL_147:
                  v46 = (unsigned __int16 **)v63;
                  goto LABEL_148;
                }
                if ( v30 )
                  goto LABEL_126;
                goto LABEL_127;
              }
              if ( v38 && (v51 = (const wchar_t *)*((_QWORD *)v16 + 4)) != 0 )
              {
                v52 = _wcsnicmp(v38, v51, 0x20u);
                v53 = v30 + 1;
                if ( !v52 )
                  v53 = v30;
                v30 = v53;
              }
              else
              {
                ++v30;
              }
            }
            v42 = v61;
LABEL_94:
            v43 = v62;
            v44 = String2;
            goto LABEL_95;
          }
          if ( !v29 || (v47 = (const wchar_t *)*((_QWORD *)v16 + 7)) == 0 )
          {
            ++v30;
            goto LABEL_85;
          }
          v48 = _wcsnicmp(v29, v47, 0x20u);
          v49 = v30 + 1;
          if ( !v48 )
            v49 = v30;
          v30 = v49;
        }
        v34 = 32;
LABEL_85:
        v38 = String2;
        goto LABEL_86;
      }
      if ( v17 == 8 || (_DWORD)v19 == 8 || v18 == 8 )
      {
        v60 = (struct PillarStatusEx *)pv;
        *((_DWORD *)pv + 1) = 8;
        *(_DWORD *)v60 = 100;
      }
      else
      {
        v60 = (struct PillarStatusEx *)pv;
        *((_DWORD *)pv + 1) = 4;
        *(_DWORD *)v60 = 99;
      }
      *((_QWORD *)v60 + 1) = 0;
      *((_QWORD *)v60 + 2) = 0;
    }
    *a2 = v60;
    goto LABEL_164;
  }
  v20 = (wchar_t *)*((_QWORD *)v16 + 1);
  if ( v20 )
    v21 = (unsigned __int16 **)*((_QWORD *)v16 + 2);
  else
    v21 = 0;
  v22 = (const wchar_t *)*((_QWORD *)v16 + 7);
  if ( v22 )
  {
    if ( v20 )
    {
      if ( _wcsnicmp(*((const wchar_t **)v16 + 1), v22, 0x20u) )
      {
LABEL_45:
        v20 = 0;
        v21 = 0;
        goto LABEL_46;
      }
    }
    else
    {
      v21 = (unsigned __int16 **)*((_QWORD *)v16 + 8);
      v20 = (wchar_t *)*((_QWORD *)v16 + 7);
    }
  }
  v19 = (wchar_t *)*((_QWORD *)v16 + 4);
  if ( !v19 )
    goto LABEL_46;
  if ( !v20 )
  {
    v21 = (unsigned __int16 **)*((_QWORD *)v16 + 5);
    v20 = (wchar_t *)*((_QWORD *)v16 + 4);
    goto LABEL_46;
  }
  if ( _wcsnicmp(v20, v19, 0x20u) )
    goto LABEL_45;
LABEL_46:
  v23 = pv;
  *((_DWORD *)pv + 1) = 1;
  *(_DWORD *)v23 = v20 != 0 ? 143 : 23;
  if ( !v20 )
  {
    v23[1] = 0;
    goto LABEL_60;
  }
  v24 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v23 + 1), (unsigned __int16 **)v20, v10);
  if ( v24 >= 0 )
  {
LABEL_60:
    if ( v21 )
    {
      v24 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v23 + 2), v21, v10);
      if ( v24 < 0 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_52;
        v26 = 90;
        goto LABEL_51;
      }
    }
    else
    {
      v23[2] = 0;
    }
    *a2 = (struct PillarStatusEx *)v23;
LABEL_164:
    ShieldProvider::FreeFirewallProfileStatusEx(v16, (struct tagFIREWALL_PROFILE_STATUS_EX *)v19);
    return 0;
  }
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_52;
  v26 = 89;
LABEL_51:
  WPP_SF_d(v25[2], v26, &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids, (unsigned int)v24);
LABEL_52:
  ShieldProvider::FreeFirewallProfileStatusEx(v16, (struct tagFIREWALL_PROFILE_STATUS_EX *)v19);
  if ( v23 )
  {
    v27 = (void *)v23[1];
    if ( v27 )
    {
      CoTaskMemFree(v27);
      v23[1] = 0;
    }
    v28 = (void *)v23[2];
    if ( v28 )
    {
      CoTaskMemFree(v28);
      v23[2] = 0;
    }
    CoTaskMemFree(v23);
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x180049ee4  mov     [rsp-40h+arg_8], rdx
0x180049ee9  mov     [rsp-40h+arg_0], rcx
0x180049eee  push    rbp
0x180049eef  push    rbx
0x180049ef0  push    rsi
0x180049ef1  push    rdi
0x180049ef2  push    r12
0x180049ef4  push    r13
0x180049ef6  push    r14
0x180049ef8  push    r15
0x180049efa  mov     rbp, rsp
0x180049efd  sub     rsp, 38h
0x180049f01  xor     r14d, r14d
0x180049f04  mov     r13, rdx
0x180049f07  test    rdx, rdx
0x180049f0a  jnz     short loc_180049F4A
0x180049f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f13  lea     rax, WPP_GLOBAL_Control
0x180049f1a  mov     ebx, 80070057h
0x180049f1f  cmp     rcx, rax
0x180049f22  jz      short loc_180049F43
0x180049f24  lea     esi, [rdx+1]
0x180049f27  test    [rcx+1Ch], sil
0x180049f2b  jz      short loc_180049F43
0x180049f2d  mov     rcx, [rcx+10h]
0x180049f31  lea     edx, [rsi+55h]
0x180049f34  mov     r9d, ebx
0x180049f37  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x180049f3e  call    WPP_SF_d
0x180049f43  mov     eax, ebx
0x180049f45  jmp     loc_18004A658
0x180049f4a  lea     rcx, [rbp+pv]
0x180049f4e  mov     [rbp+pv], r14
0x180049f52  call    ??$UtilCoTaskMemAllocObject@UPillarStatusEx@@@CommonUtil@@YAJPEAPEAUPillarStatusEx@@_K_N@Z; CommonUtil::UtilCoTaskMemAllocObject<PillarStatusEx>(PillarStatusEx * *,unsigned __int64,bool)
0x180049f57  mov     edi, eax
0x180049f59  test    eax, eax
0x180049f5b  jns     short loc_180049FD0
0x180049f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f64  lea     rax, WPP_GLOBAL_Control
0x180049f6b  cmp     rcx, rax
0x180049f6e  jz      short loc_180049F91
0x180049f70  mov     esi, 1
0x180049f75  test    [rcx+1Ch], sil
0x180049f79  jz      short loc_180049F91
0x180049f7b  mov     rcx, [rcx+10h]
0x180049f7f  lea     edx, [rsi+56h]
0x180049f82  mov     r9d, edi
0x180049f85  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x180049f8c  call    WPP_SF_d
0x180049f91  mov     rbx, [rbp+pv]
0x180049f95  test    rbx, rbx
0x180049f98  jz      short loc_180049FC9
0x180049f9a  mov     rcx, [rbx+8]; pv
0x180049f9e  test    rcx, rcx
0x180049fa1  jz      short loc_180049FAD
0x180049fa3  call    cs:__imp_CoTaskMemFree
0x180049fa9  mov     [rbx+8], r14
0x180049fad  mov     rcx, [rbx+10h]; pv
0x180049fb1  test    rcx, rcx
0x180049fb4  jz      short loc_180049FC0
0x180049fb6  call    cs:__imp_CoTaskMemFree
0x180049fbc  mov     [rbx+10h], r14
0x180049fc0  mov     rcx, rbx; pv
0x180049fc3  call    cs:__imp_CoTaskMemFree
0x180049fc9  mov     eax, edi
0x180049fcb  jmp     loc_18004A658
0x180049fd0  lea     rdx, [rbp+arg_0]; struct tagFIREWALL_PROFILE_STATUS_EX **
0x180049fd4  mov     [rbp+arg_0], r14
0x180049fd8  call    ?GetPillarSubstatusEx@FirewallManager@ShieldProvider@@QEAAJPEAPEAUtagFIREWALL_PROFILE_STATUS_EX@@@Z; ShieldProvider::FirewallManager::GetPillarSubstatusEx(tagFIREWALL_PROFILE_STATUS_EX * *)
0x180049fdd  mov     r12d, eax
0x180049fe0  test    eax, eax
0x180049fe2  jns     loc_18004A06A
0x180049fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x180049fef  lea     rax, WPP_GLOBAL_Control
0x180049ff6  cmp     rcx, rax
0x180049ff9  jz      short loc_18004A01C
0x180049ffb  mov     esi, 1
0x18004a000  test    [rcx+1Ch], sil
0x18004a004  jz      short loc_18004A01C
0x18004a006  mov     rcx, [rcx+10h]
0x18004a00a  lea     edx, [rsi+57h]
0x18004a00d  mov     r9d, r12d
0x18004a010  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x18004a017  call    WPP_SF_d
0x18004a01c  mov     rcx, [rbp+arg_0]; this
0x18004a020  test    rcx, rcx
0x18004a023  jz      short loc_18004A02A
0x18004a025  call    ?FreeFirewallProfileStatusEx@ShieldProvider@@YAXPEAUtagFIREWALL_PROFILE_STATUS_EX@@@Z; ShieldProvider::FreeFirewallProfileStatusEx(tagFIREWALL_PROFILE_STATUS_EX *)
0x18004a02a  mov     rbx, [rbp+pv]
0x18004a02e  test    rbx, rbx
0x18004a031  jz      short loc_18004A062
0x18004a033  mov     rcx, [rbx+8]; pv
0x18004a037  test    rcx, rcx
0x18004a03a  jz      short loc_18004A046
0x18004a03c  call    cs:__imp_CoTaskMemFree
0x18004a042  mov     [rbx+8], r14
0x18004a046  mov     rcx, [rbx+10h]; pv
0x18004a04a  test    rcx, rcx
0x18004a04d  jz      short loc_18004A059
0x18004a04f  call    cs:__imp_CoTaskMemFree
0x18004a055  mov     [rbx+10h], r14
0x18004a059  mov     rcx, rbx; pv
0x18004a05c  call    cs:__imp_CoTaskMemFree
0x18004a062  mov     eax, r12d
0x18004a065  jmp     loc_18004A658
0x18004a06a  mov     rbx, [rbp+arg_0]
0x18004a06e  mov     esi, 1
0x18004a073  mov     eax, [rbx+4]
0x18004a076  mov     ecx, [rbx+1Ch]
0x18004a079  mov     edx, [rbx+34h]; struct tagFIREWALL_PROFILE_STATUS_EX *
0x18004a07c  mov     dword ptr [rbp+arg_0], ecx
0x18004a07f  cmp     eax, esi
0x18004a081  jnz     loc_18004A20E
0x18004a087  cmp     edx, esi
0x18004a089  jnz     loc_18004A20E
0x18004a08f  cmp     ecx, esi
0x18004a091  jnz     loc_18004A20E
0x18004a097  mov     r14, [rbx+8]
0x18004a09b  test    r14, r14
0x18004a09e  jz      short loc_18004A0A6
0x18004a0a0  mov     r15, [rbx+10h]
0x18004a0a4  jmp     short loc_18004A0A9
0x18004a0a6  xor     r15d, r15d
0x18004a0a9  mov     rdx, [rbx+38h]; String2
0x18004a0ad  mov     edi, 20h ; ' '
0x18004a0b2  test    rdx, rdx
0x18004a0b5  jz      short loc_18004A0D5
0x18004a0b7  test    r14, r14
0x18004a0ba  jnz     short loc_18004A0C5
0x18004a0bc  mov     r15, [rbx+40h]
0x18004a0c0  mov     r14, rdx
0x18004a0c3  jmp     short loc_18004A0D5
0x18004a0c5  mov     r8, rdi; MaxCount
0x18004a0c8  mov     rcx, r14; String1
0x18004a0cb  call    cs:__imp__wcsnicmp
0x18004a0d1  test    eax, eax
0x18004a0d3  jnz     short loc_18004A0FC
0x18004a0d5  mov     rdx, [rbx+20h]; String2
0x18004a0d9  test    rdx, rdx
0x18004a0dc  jz      short loc_18004A102
0x18004a0de  test    r14, r14
0x18004a0e1  jnz     short loc_18004A0EC
0x18004a0e3  mov     r15, [rbx+28h]
0x18004a0e7  mov     r14, rdx
0x18004a0ea  jmp     short loc_18004A102
0x18004a0ec  mov     r8, rdi; MaxCount
0x18004a0ef  mov     rcx, r14; String1
0x18004a0f2  call    cs:__imp__wcsnicmp
0x18004a0f8  test    eax, eax
0x18004a0fa  jz      short loc_18004A102
0x18004a0fc  xor     r14d, r14d
0x18004a0ff  xor     r15d, r15d
0x18004a102  mov     rdi, [rbp+pv]
0x18004a106  mov     rax, r14
0x18004a109  neg     rax
0x18004a10c  sbb     ecx, ecx
0x18004a10e  and     ecx, 78h
0x18004a111  mov     [rdi+4], esi
0x18004a114  add     ecx, 17h
0x18004a117  mov     [rdi], ecx
0x18004a119  test    r14, r14
0x18004a11c  jz      loc_18004A1B6
0x18004a122  lea     rcx, [rdi+8]; this
0x18004a126  mov     rdx, r14; unsigned __int16 **
0x18004a129  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18004a12e  mov     r14d, eax
0x18004a131  test    eax, eax
0x18004a133  jns     loc_18004A1BE
0x18004a139  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a140  lea     rax, WPP_GLOBAL_Control
0x18004a147  cmp     rcx, rax
0x18004a14a  jz      short loc_18004A16A
0x18004a14c  test    [rcx+1Ch], sil
0x18004a150  jz      short loc_18004A16A
0x18004a152  mov     edx, 59h ; 'Y'
0x18004a157  mov     rcx, [rcx+10h]
0x18004a15b  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x18004a162  mov     r9d, r14d
0x18004a165  call    WPP_SF_d
0x18004a16a  mov     rcx, rbx; this
0x18004a16d  call    ?FreeFirewallProfileStatusEx@ShieldProvider@@YAXPEAUtagFIREWALL_PROFILE_STATUS_EX@@@Z; ShieldProvider::FreeFirewallProfileStatusEx(tagFIREWALL_PROFILE_STATUS_EX *)
0x18004a172  test    rdi, rdi
0x18004a175  jz      short loc_18004A1AE
0x18004a177  mov     rcx, [rdi+8]; pv
0x18004a17b  test    rcx, rcx
0x18004a17e  jz      short loc_18004A18E
0x18004a180  call    cs:__imp_CoTaskMemFree
0x18004a186  mov     qword ptr [rdi+8], 0
0x18004a18e  mov     rcx, [rdi+10h]; pv
0x18004a192  test    rcx, rcx
0x18004a195  jz      short loc_18004A1A5
0x18004a197  call    cs:__imp_CoTaskMemFree
0x18004a19d  mov     qword ptr [rdi+10h], 0
0x18004a1a5  mov     rcx, rdi; pv
0x18004a1a8  call    cs:__imp_CoTaskMemFree
0x18004a1ae  mov     eax, r14d
0x18004a1b1  jmp     loc_18004A658
0x18004a1b6  mov     qword ptr [rdi+8], 0
0x18004a1be  test    r15, r15
0x18004a1c1  jz      short loc_18004A1FD
0x18004a1c3  lea     rcx, [rdi+10h]; this
0x18004a1c7  mov     rdx, r15; unsigned __int16 **
0x18004a1ca  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18004a1cf  mov     r14d, eax
0x18004a1d2  test    eax, eax
0x18004a1d4  jns     short loc_18004A205
0x18004a1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a1dd  lea     rax, WPP_GLOBAL_Control
0x18004a1e4  cmp     rcx, rax
0x18004a1e7  jz      short loc_18004A16A
0x18004a1e9  test    [rcx+1Ch], sil
0x18004a1ed  jz      loc_18004A16A
0x18004a1f3  mov     edx, 5Ah ; 'Z'
0x18004a1f8  jmp     loc_18004A157
0x18004a1fd  mov     qword ptr [rdi+10h], 0
0x18004a205  mov     [r13+0], rdi
0x18004a209  jmp     loc_18004A64E
0x18004a20e  mov     r8d, 64h ; 'd'
0x18004a214  cmp     [rbx], r8d
0x18004a217  jz      loc_18004A634
0x18004a21d  cmp     [rbx+30h], r8d
0x18004a221  jz      loc_18004A634
0x18004a227  cmp     [rbx+18h], r8d
0x18004a22b  jz      loc_18004A634
0x18004a231  lea     r9d, [r8-1]
0x18004a235  cmp     [rbx], r9d
0x18004a238  jz      loc_18004A5F2
0x18004a23e  cmp     [rbx+30h], r9d
0x18004a242  jz      loc_18004A5F2
0x18004a248  cmp     [rbx+18h], r9d
0x18004a24c  jz      loc_18004A5F2
0x18004a252  xor     ecx, ecx
0x18004a254  lea     r14d, [r8-5Ch]
0x18004a258  xor     r9d, r9d
0x18004a25b  mov     [rbp+String2], rcx
0x18004a25f  xor     edi, edi
0x18004a261  mov     [rbp+var_10], r9
0x18004a265  cmp     eax, r14d
0x18004a268  jnz     short loc_18004A27B
0x18004a26a  mov     r9, [rbx+10h]
0x18004a26e  mov     r15d, esi
0x18004a271  mov     r13, [rbx+8]
0x18004a275  mov     [rbp+var_18], r9
0x18004a279  jmp     short loc_18004A29C
0x18004a27b  xor     r15d, r15d
0x18004a27e  mov     [rbp+var_18], r9
0x18004a282  xor     r13d, r13d
0x18004a285  cmp     eax, 4
0x18004a288  jnz     short loc_18004A29C
0x18004a28a  mov     rcx, [rbx+8]; String1
0x18004a28e  mov     edi, esi
0x18004a290  mov     r9, [rbx+10h]
0x18004a294  mov     [rbp+String2], rcx
0x18004a298  mov     [rbp+var_10], r9
0x18004a29c  mov     r8d, 20h ; ' '; MaxCount
0x18004a2a2  cmp     edx, r14d
0x18004a2a5  jnz     loc_18004A3AF
0x18004a2ab  test    r15d, r15d
0x18004a2ae  jz      loc_18004A39B
0x18004a2b4  test    r13, r13
0x18004a2b7  jz      loc_18004A393
0x18004a2bd  mov     rdx, [rbx+38h]; String2
0x18004a2c1  test    rdx, rdx
0x18004a2c4  jz      loc_18004A393
0x18004a2ca  mov     rcx, r13; String1
0x18004a2cd  call    cs:__imp__wcsnicmp
0x18004a2d3  lea     ecx, [r15+1]
0x18004a2d7  test    eax, eax
0x18004a2d9  cmovz   ecx, r15d
0x18004a2dd  mov     r15d, ecx
0x18004a2e0  mov     r8d, 20h ; ' '; MaxCount
0x18004a2e6  mov     rcx, [rbp+String2]; String1
0x18004a2ea  mov     eax, dword ptr [rbp+arg_0]
0x18004a2ed  cmp     eax, r14d
0x18004a2f0  jnz     loc_18004A419
0x18004a2f6  test    r15d, r15d
0x18004a2f9  jz      loc_18004A405
0x18004a2ff  test    r13, r13
0x18004a302  jz      loc_18004A3FD
0x18004a308  mov     rdx, [rbx+20h]; String2
0x18004a30c  test    rdx, rdx
0x18004a30f  jz      loc_18004A3FD
0x18004a315  mov     rcx, r13; String1
0x18004a318  call    cs:__imp__wcsnicmp
0x18004a31e  lea     ecx, [r15+1]
0x18004a322  test    eax, eax
0x18004a324  cmovz   ecx, r15d
0x18004a328  mov     r15d, ecx
0x18004a32b  mov     rcx, [rbp+var_18]
0x18004a32f  mov     rdx, [rbp+var_10]; struct tagFIREWALL_PROFILE_STATUS_EX *
0x18004a333  mov     rax, [rbp+String2]
0x18004a337  mov     [rbp+arg_0], 0
0x18004a33f  cmp     r15d, esi
0x18004a342  jnz     loc_18004A479
0x18004a348  cmp     edi, esi
0x18004a34a  jnz     loc_18004A47E
0x18004a350  test    r13, r13
0x18004a353  jz      loc_18004A463
0x18004a359  test    rax, rax
0x18004a35c  jz      loc_18004A463
  ... truncated ...
```
