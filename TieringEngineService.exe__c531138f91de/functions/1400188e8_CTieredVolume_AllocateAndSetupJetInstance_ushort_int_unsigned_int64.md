# CTieredVolume::AllocateAndSetupJetInstance(ushort *,int,unsigned __int64 *)

- ea: `0x1400188e8`
- end: `0x1400192be`
- name: `?AllocateAndSetupJetInstance@CTieredVolume@@QEAAJPEAGHPEA_K@Z`
- size: `2518`
- prototype: `__int64 __fastcall(CTieredVolume *__hidden this, unsigned __int16 *, int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001a270`

## callees

- `0x14000108c`
- `0x140002323`
- `0x140002db0`
- `0x140004aa8`
- `0x140009c08`
- `0x140017e78`
- `0x1400188e8`
- `0x1400192c4`
- `0x140019ad8`
- `0x14001ca98`
- `0x14001ce18`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1400189ac`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1400189ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140018978`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140018996`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140018978`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140018996`
- `ESENT!JetSetSystemParameterW` at `0x140018b45`
- `ESENT!JetSetSystemParameterW` at `0x140018b9c`
- `ESENT!JetSetSystemParameterW` at `0x140018bf3`
- `ESENT!JetSetSystemParameterW` at `0x140018c4a`
- `ESENT!JetSetSystemParameterW` at `0x140018ca0`
- `ESENT!JetSetSystemParameterW` at `0x140018cf7`
- `ESENT!JetSetSystemParameterW` at `0x140018d4e`
- `ESENT!JetSetSystemParameterW` at `0x140018da5`
- `ESENT!JetSetSystemParameterW` at `0x140018dfc`
- `ESENT!JetSetSystemParameterW` at `0x140018e54`
- `ESENT!JetSetSystemParameterW` at `0x140018eab`
- `ESENT!JetSetSystemParameterW` at `0x140018f02`
- `ESENT!JetSetSystemParameterW` at `0x140018f62`
- `ESENT!JetSetSystemParameterW` at `0x140018b45`
- `ESENT!JetSetSystemParameterW` at `0x140018b9c`
- `ESENT!JetSetSystemParameterW` at `0x140018bf3`
- `ESENT!JetSetSystemParameterW` at `0x140018c4a`
- `ESENT!JetSetSystemParameterW` at `0x140018ca0`
- `ESENT!JetSetSystemParameterW` at `0x140018cf7`
- `ESENT!JetSetSystemParameterW` at `0x140018d4e`
- `ESENT!JetSetSystemParameterW` at `0x140018da5`
- `ESENT!JetSetSystemParameterW` at `0x140018dfc`
- `ESENT!JetSetSystemParameterW` at `0x140018e54`
- `ESENT!JetSetSystemParameterW` at `0x140018eab`
- `ESENT!JetSetSystemParameterW` at `0x140018f02`
- `ESENT!JetSetSystemParameterW` at `0x140018f62`
- `ESENT!JetCreateInstance2W` at `0x140018ad3`
- `ESENT!JetCreateInstance2W` at `0x140018ad3`

## pseudocode

```c
__int64 __fastcall CTieredVolume::AllocateAndSetupJetInstance(
        CTieredVolume *this,
        unsigned __int16 *a2,
        int a3,
        unsigned __int64 *a4)
{
  char v7; // bl
  int v9; // r14d
  HRESULT v10; // eax
  unsigned int v11; // esi
  int v12; // edi
  _QWORD *v13; // r10
  int v14; // edx
  JET_ERR Instance2W; // eax
  int v16; // edx
  int v17; // r8d
  JET_ERR v18; // eax
  int v19; // edx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // ecx
  CTieredVolume *v24; // rdi
  int v25; // ecx
  char v27; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v30; // [rsp+94h] [rbp-6Ch] BYREF
  int v31; // [rsp+98h] [rbp-68h] BYREF
  GUID pguid; // [rsp+A0h] [rbp-60h] BYREF
  char v33[32]; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  __int64 v36; // [rsp+E0h] [rbp-20h]
  _DWORD v37[2]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v38; // [rsp+F0h] [rbp-10h]
  int v39; // [rsp+F8h] [rbp-8h]
  int v40; // [rsp+FCh] [rbp-4h]
  WCHAR *v41; // [rsp+100h] [rbp+0h]
  int v42; // [rsp+108h] [rbp+8h]
  int v43; // [rsp+10Ch] [rbp+Ch]
  int *v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+118h] [rbp+18h]
  unsigned int *v46; // [rsp+120h] [rbp+20h]
  __int64 v47; // [rsp+128h] [rbp+28h]
  const char *v48; // [rsp+130h] [rbp+30h]
  __int64 v49; // [rsp+138h] [rbp+38h]
  int *v50; // [rsp+140h] [rbp+40h]
  __int64 v51; // [rsp+148h] [rbp+48h]
  WCHAR szInstanceName[304]; // [rsp+150h] [rbp+50h] BYREF

  v7 = 0;
  v27 = 0;
  pguid = 0;
  memset_0(szInstanceName, 0, 0x258u);
  CTieredVolume::EnableJetMultiInstance(this, a2);
  if ( *(_WORD *)((char *)this + 165)
    || WaitForSingleObject(*((HANDLE *)this + 96), 0) != 258
    || WaitForSingleObject(*((HANDLE *)this + 95), 0) != 258 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (char *)this + 672);
      v13 = WPP_GLOBAL_Control;
    }
    v12 = 6;
    v9 = -1000;
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 2u )
    {
      WPP_SF_Dd(v13[2], 16, &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids, *((unsigned int *)this + 32), -1000);
      v13 = WPP_GLOBAL_Control;
    }
    goto LABEL_104;
  }
  v9 = 0;
  v10 = CoCreateGuid(&pguid);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 21;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_119;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_112;
    v14 = 17;
    goto LABEL_9;
  }
  v10 = StringCchPrintfW(
          szInstanceName,
          0x12Cu,
          L"%s{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
          a2,
          pguid.Data1,
          pguid.Data2,
          pguid.Data3,
          pguid.Data4[0],
          pguid.Data4[1],
          pguid.Data4[2],
          pguid.Data4[3],
          pguid.Data4[4],
          pguid.Data4[5],
          pguid.Data4[6],
          pguid.Data4[7]);
  v12 = 0;
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 22;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v7 = 0;
      goto LABEL_119;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_112;
    v14 = 18;
LABEL_9:
    WPP_SF_Sd(v13[2], v14, (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids, (_DWORD)a2, v10);
    goto LABEL_111;
  }
  Instance2W = JetCreateInstance2W(a4, szInstanceName, szInstanceName, 0);
  v9 = Instance2W;
  if ( Instance2W )
  {
    v12 = 7;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    WPP_SF_SSL(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, (_DWORD)a2, (__int64)szInstanceName, Instance2W);
  }
  else
  {
    v27 = 1;
    v18 = JetSetSystemParameterW(a4, 0, 0, 0, a2);
    v9 = v18;
    if ( v18 )
    {
      v12 = 8;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_88;
      }
      v19 = 20;
    }
    else
    {
      v18 = JetSetSystemParameterW(a4, 0, 2u, 0, a2);
      v9 = v18;
      if ( v18 )
      {
        v12 = 9;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_88;
        }
        v19 = 21;
      }
      else
      {
        v18 = JetSetSystemParameterW(a4, 0, 0x11u, 1u, 0);
        v9 = v18;
        if ( v18 )
        {
          v12 = 10;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_88;
          }
          v19 = 22;
        }
        else
        {
          v18 = JetSetSystemParameterW(a4, 0, 0x30u, 1u, 0);
          v9 = v18;
          if ( v18 )
          {
            v12 = 11;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_88;
            }
            v19 = 23;
          }
          else
          {
            v18 = JetSetSystemParameterW(a4, 0, 1u, 0, a2);
            v9 = v18;
            if ( v18 )
            {
              v12 = 12;
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_88;
              }
              v19 = 24;
            }
            else
            {
              v18 = JetSetSystemParameterW(a4, 0, 0x71u, 0, a2);
              v9 = v18;
              if ( v18 )
              {
                v12 = 13;
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_88;
                }
                v19 = 25;
              }
              else
              {
                v18 = JetSetSystemParameterW(a4, 0, 0x33u, 0, 0);
                v9 = v18;
                if ( v18 )
                {
                  v12 = 14;
                  v13 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_88;
                  }
                  v19 = 27;
                }
                else
                {
                  v18 = JetSetSystemParameterW(a4, 0, 0x2Du, 1u, 0);
                  v9 = v18;
                  if ( v18 )
                  {
                    v12 = 15;
                    v13 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_88;
                    }
                    v19 = 28;
                  }
                  else
                  {
                    v18 = JetSetSystemParameterW(a4, 0, 0x36u, 1u, 0);
                    v9 = v18;
                    if ( v18 )
                    {
                      v12 = 16;
                      v13 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                      {
                        goto LABEL_88;
                      }
                      v19 = 29;
                    }
                    else
                    {
                      v18 = JetSetSystemParameterW(a4, 0, 0xAu, 2u, 0);
                      v9 = v18;
                      if ( v18 )
                      {
                        v12 = 17;
                        v13 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                        {
                          goto LABEL_88;
                        }
                        v19 = 30;
                      }
                      else
                      {
                        v18 = JetSetSystemParameterW(a4, 0, 0x7Du, 1u, 0);
                        v9 = v18;
                        if ( v18 )
                        {
                          v12 = 18;
                          v13 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                          {
                            goto LABEL_88;
                          }
                          v19 = 31;
                        }
                        else
                        {
                          v18 = JetSetSystemParameterW(a4, 0, 0x2Eu, 0, 0);
                          v9 = v18;
                          if ( v18 )
                          {
                            v12 = 19;
                            v13 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                            {
                              goto LABEL_88;
                            }
                            v19 = 32;
                          }
                          else
                          {
                            if ( !a3 )
                              goto LABEL_111;
                            v18 = JetSetSystemParameterW(a4, 0, 0x22u, 0, L"Off");
                            v9 = v18;
                            if ( !v18 )
                              goto LABEL_111;
                            v12 = 20;
                            v13 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                            {
                              goto LABEL_88;
                            }
                            v19 = 33;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    WPP_SF_Sd(v13[2], v19, (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids, (_DWORD)a2, v18);
  }
  v13 = WPP_GLOBAL_Control;
LABEL_88:
  if ( v9 == -529 || v9 == -1092 || v9 == -1808 )
  {
    v11 = ATL::AtlHresultFromWin32(0x70u);
    goto LABEL_107;
  }
  if ( v9 == -1011 )
  {
    v11 = -2147024882;
    goto LABEL_107;
  }
LABEL_104:
  v20 = -v9;
  if ( v9 > 0 )
    LOWORD(v20) = v9;
  v11 = v9 & 0x8E5E0000 | (unsigned __int16)v20 | 0xE5E0000;
LABEL_107:
  if ( v13 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v13 + 28) & 1) == 0 || *((_BYTE *)v13 + 25) < 2u )
    {
LABEL_112:
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 2u )
        WPP_SF_Sd(v13[2], 35, (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids, (_DWORD)a2, v11);
      goto LABEL_116;
    }
    WPP_SF_Sd(v13[2], 34, (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids, (_DWORD)a2, v9);
LABEL_111:
    v13 = WPP_GLOBAL_Control;
    goto LABEL_112;
  }
LABEL_116:
  if ( !v11 )
    return v11;
  v7 = v27;
LABEL_119:
  if ( (unsigned int)dword_14004C098 > 5
    && (qword_14004C0A8 & 0x400000000000LL) != 0
    && (qword_14004C0B0 & 0x400000000000LL) == qword_14004C0B0 )
  {
    v29 = v12;
    v50 = &v29;
    v30 = v11;
    v48 = "AllocateAndSetupJetInstance";
    v21 = -1;
    v31 = v9;
    v46 = &v30;
    v44 = &v31;
    v22 = -1;
    v51 = 4;
    v49 = 28;
    v47 = 4;
    v45 = 4;
    do
      ++v22;
    while ( szInstanceName[v22] );
    v43 = 0;
    v41 = szInstanceName;
    v42 = 2 * v22 + 2;
    if ( a2 )
    {
      do
        ++v21;
      while ( a2[v21] );
      v23 = 2 * v21 + 2;
    }
    else
    {
      a2 = (unsigned __int16 *)&qword_140043BD0;
      v23 = 2;
    }
    v24 = this;
    v39 = v23;
    v34 = v37;
    v38 = a2;
    v40 = 0;
    v35 = 2;
    v25 = *((unsigned __int16 *)this + 348);
    v36 = *((_QWORD *)this + 88);
    v37[0] = v25;
    v37[1] = 0;
    tlgWriteTransfer_EventWriteTransfer(&dword_14004C098, byte_140045ED5, 0, 0, 10, v33);
  }
  else
  {
    v24 = this;
  }
  if ( v7 )
    CTieredVolume::CallJetTerm(v24, *a4, 8u);
  return v11;
}

```

## disassembly

```asm
0x1400188e8  mov     [rsp-8+arg_10], rbx
0x1400188ed  push    rbp
0x1400188ee  push    rsi
0x1400188ef  push    rdi
0x1400188f0  push    r12
0x1400188f2  push    r13
0x1400188f4  push    r14
0x1400188f6  push    r15
0x1400188f8  lea     rbp, [rsp-2C0h]
0x140018900  sub     rsp, 3C0h
0x140018907  mov     rax, cs:__security_cookie
0x14001890e  xor     rax, rsp
0x140018911  mov     [rbp+2F0h+var_40], rax
0x140018918  mov     r12d, r8d
0x14001891b  mov     [rbp+2F0h+var_368], rcx
0x14001891f  mov     r15, rdx
0x140018922  mov     rsi, rcx
0x140018925  xorps   xmm0, xmm0
0x140018928  lea     rcx, [rbp+2F0h+szInstanceName]; void *
0x14001892c  xor     bl, bl
0x14001892e  xor     edx, edx; Val
0x140018930  mov     r8d, 258h; Size
0x140018936  mov     [rbp+2F0h+var_370], bl
0x140018939  movups  xmmword ptr [rbp+2F0h+pguid.Data1], xmm0
0x14001893d  mov     r13, r9
0x140018940  call    memset_0
0x140018945  mov     rdx, r15; unsigned __int16 *
0x140018948  mov     rcx, rsi; this
0x14001894b  call    ?EnableJetMultiInstance@CTieredVolume@@QEAAXPEAG@Z; CTieredVolume::EnableJetMultiInstance(ushort *)
0x140018950  lea     rdi, WPP_GLOBAL_Control
0x140018957  cmp     [rsi+0A5h], bl
0x14001895d  jnz     loc_140019015
0x140018963  cmp     [rsi+0A6h], bl
0x140018969  jnz     loc_140019015
0x14001896f  mov     rcx, [rsi+300h]; hHandle
0x140018976  xor     edx, edx; dwMilliseconds
0x140018978  call    cs:__imp_WaitForSingleObject
0x14001897e  mov     r14d, 102h
0x140018984  cmp     eax, r14d
0x140018987  jnz     loc_140019015
0x14001898d  mov     rcx, [rsi+2F8h]; hHandle
0x140018994  xor     edx, edx; dwMilliseconds
0x140018996  call    cs:__imp_WaitForSingleObject
0x14001899c  cmp     eax, r14d
0x14001899f  jnz     loc_140019015
0x1400189a5  lea     rcx, [rbp+2F0h+pguid]; pguid
0x1400189a9  xor     r14d, r14d
0x1400189ac  call    cs:__imp_CoCreateGuid
0x1400189b2  mov     esi, eax
0x1400189b4  test    eax, eax
0x1400189b6  jns     short loc_140018A0A
0x1400189b8  lea     edi, [r14+15h]
0x1400189bc  mov     r10, cs:WPP_GLOBAL_Control
0x1400189c3  lea     r12, WPP_GLOBAL_Control
0x1400189ca  cmp     r10, r12
0x1400189cd  jz      loc_140019136
0x1400189d3  lea     ebx, [rdi-14h]
0x1400189d6  test    [r10+1Ch], bl
0x1400189da  jz      loc_1400190F5
0x1400189e0  cmp     byte ptr [r10+19h], 2
0x1400189e5  jb      loc_1400190F5
0x1400189eb  lea     edx, [rdi-4]
0x1400189ee  mov     rcx, [r10+10h]
0x1400189f2  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x1400189f9  mov     r9, r15
0x1400189fc  mov     dword ptr [rsp+3F0h+szParam], eax
0x140018a00  call    WPP_SF_Sd
0x140018a05  jmp     loc_1400190EE
0x140018a0a  movzx   eax, [rbp+2F0h+pguid.Data4+7]
0x140018a0e  movzx   ecx, [rbp+2F0h+pguid.Data4+6]
0x140018a12  movzx   edx, [rbp+2F0h+pguid.Data4+5]
0x140018a16  movzx   r8d, [rbp+2F0h+pguid.Data4+4]
0x140018a1b  movzx   r9d, [rbp+2F0h+pguid.Data4+3]
0x140018a20  movzx   r10d, [rbp+2F0h+pguid.Data4+2]
0x140018a25  movzx   r11d, [rbp+2F0h+pguid.Data4+1]
0x140018a2a  movzx   ebx, [rbp+2F0h+pguid.Data4]
0x140018a2e  movzx   edi, [rbp+2F0h+pguid.Data3]
0x140018a32  movzx   esi, [rbp+2F0h+pguid.Data2]
0x140018a36  mov     [rsp+3F0h+var_380], eax
0x140018a3a  mov     eax, [rbp+2F0h+pguid.Data1]
0x140018a3d  mov     [rsp+3F0h+var_388], ecx
0x140018a41  lea     rcx, [rbp+2F0h+szInstanceName]; unsigned __int16 *
0x140018a45  mov     [rsp+3F0h+var_390], edx
0x140018a49  mov     edx, 12Ch; unsigned __int64
0x140018a4e  mov     [rsp+3F0h+var_398], r8d
0x140018a53  lea     r8, aS08x04x04x02x0; "%s{%08x-%04x-%04x-%02x%02x-%02x%02x%02x"...
0x140018a5a  mov     [rsp+3F0h+var_3A0], r9d
0x140018a5f  mov     r9, r15
0x140018a62  mov     [rsp+3F0h+var_3A8], r10d
0x140018a67  mov     [rsp+3F0h+var_3B0], r11d
0x140018a6c  mov     [rsp+3F0h+var_3B8], ebx
0x140018a70  mov     [rsp+3F0h+var_3C0], edi
0x140018a74  mov     dword ptr [rsp+3F0h+var_3C8], esi
0x140018a78  mov     dword ptr [rsp+3F0h+szParam], eax
0x140018a7c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140018a81  xor     edi, edi
0x140018a83  mov     esi, eax
0x140018a85  test    eax, eax
0x140018a87  jns     short loc_140018AC5
0x140018a89  mov     edi, 16h
0x140018a8e  mov     r10, cs:WPP_GLOBAL_Control
0x140018a95  lea     r12, WPP_GLOBAL_Control
0x140018a9c  cmp     r10, r12
0x140018a9f  jz      loc_140019133
0x140018aa5  lea     ebx, [rdi-15h]
0x140018aa8  test    [r10+1Ch], bl
0x140018aac  jz      loc_1400190F5
0x140018ab2  cmp     byte ptr [r10+19h], 2
0x140018ab7  jb      loc_1400190F5
0x140018abd  lea     edx, [rdi-4]
0x140018ac0  jmp     loc_1400189EE
0x140018ac5  xor     r9d, r9d; grbit
0x140018ac8  lea     r8, [rbp+2F0h+szInstanceName]; szDisplayName
0x140018acc  lea     rdx, [rbp+2F0h+szInstanceName]; szInstanceName
0x140018ad0  mov     rcx, r13; pinstance
0x140018ad3  call    cs:__imp_JetCreateInstance2W
0x140018ad9  mov     r14d, eax
0x140018adc  mov     ebx, 1
0x140018ae1  test    eax, eax
0x140018ae3  jz      short loc_140018B32
0x140018ae5  lea     edi, [rbx+6]
0x140018ae8  mov     r10, cs:WPP_GLOBAL_Control
0x140018aef  lea     r12, WPP_GLOBAL_Control
0x140018af6  cmp     r10, r12
0x140018af9  jz      loc_140018FB9
0x140018aff  test    [r10+1Ch], bl
0x140018b03  jz      loc_140018FB9
0x140018b09  cmp     byte ptr [r10+19h], 2
0x140018b0e  jb      loc_140018FB9
0x140018b14  mov     rcx, [r10+10h]
0x140018b18  mov     r9, r15
0x140018b1b  mov     dword ptr [rsp+3F0h+var_3C8], eax
0x140018b1f  lea     rax, [rbp+2F0h+szInstanceName]
0x140018b23  mov     [rsp+3F0h+szParam], rax
0x140018b28  call    WPP_SF_SSL
0x140018b2d  jmp     loc_140018FB2
0x140018b32  xor     r9d, r9d; lParam
0x140018b35  mov     [rbp+2F0h+var_370], bl
0x140018b38  xor     r8d, r8d; paramid
0x140018b3b  mov     [rsp+3F0h+szParam], r15; szParam
0x140018b40  xor     edx, edx; sesid
0x140018b42  mov     rcx, r13; pinstance
0x140018b45  call    cs:__imp_JetSetSystemParameterW
0x140018b4b  mov     r14d, eax
0x140018b4e  test    eax, eax
0x140018b50  jz      short loc_140018B8B
0x140018b52  mov     edi, 8
0x140018b57  mov     r10, cs:WPP_GLOBAL_Control
0x140018b5e  lea     r12, WPP_GLOBAL_Control
0x140018b65  cmp     r10, r12
0x140018b68  jz      loc_140018FB9
0x140018b6e  test    [r10+1Ch], bl
0x140018b72  jz      loc_140018FB9
0x140018b78  cmp     byte ptr [r10+19h], 2
0x140018b7d  jb      loc_140018FB9
0x140018b83  lea     edx, [rdi+0Ch]
0x140018b86  jmp     loc_140018F9B
0x140018b8b  xor     r9d, r9d; lParam
0x140018b8e  mov     [rsp+3F0h+szParam], r15; szParam
0x140018b93  xor     edx, edx; sesid
0x140018b95  mov     rcx, r13; pinstance
0x140018b98  lea     r8d, [r9+2]; paramid
0x140018b9c  call    cs:__imp_JetSetSystemParameterW
0x140018ba2  mov     r14d, eax
0x140018ba5  test    eax, eax
0x140018ba7  jz      short loc_140018BE2
0x140018ba9  mov     edi, 9
0x140018bae  mov     r10, cs:WPP_GLOBAL_Control
0x140018bb5  lea     r12, WPP_GLOBAL_Control
0x140018bbc  cmp     r10, r12
0x140018bbf  jz      loc_140018FB9
0x140018bc5  test    [r10+1Ch], bl
0x140018bc9  jz      loc_140018FB9
0x140018bcf  cmp     byte ptr [r10+19h], 2
0x140018bd4  jb      loc_140018FB9
0x140018bda  lea     edx, [rdi+0Ch]
0x140018bdd  jmp     loc_140018F9B
0x140018be2  xor     edx, edx; sesid
0x140018be4  mov     [rsp+3F0h+szParam], rdi; szParam
0x140018be9  mov     r9, rbx; lParam
0x140018bec  mov     rcx, r13; pinstance
0x140018bef  lea     r8d, [rdx+11h]; paramid
0x140018bf3  call    cs:__imp_JetSetSystemParameterW
0x140018bf9  mov     r14d, eax
0x140018bfc  test    eax, eax
0x140018bfe  jz      short loc_140018C39
0x140018c00  mov     edi, 0Ah
0x140018c05  mov     r10, cs:WPP_GLOBAL_Control
0x140018c0c  lea     r12, WPP_GLOBAL_Control
0x140018c13  cmp     r10, r12
0x140018c16  jz      loc_140018FB9
0x140018c1c  test    [r10+1Ch], bl
0x140018c20  jz      loc_140018FB9
0x140018c26  cmp     byte ptr [r10+19h], 2
0x140018c2b  jb      loc_140018FB9
0x140018c31  lea     edx, [rdi+0Ch]
0x140018c34  jmp     loc_140018F9B
0x140018c39  xor     edx, edx; sesid
0x140018c3b  mov     [rsp+3F0h+szParam], rdi; szParam
0x140018c40  mov     r9, rbx; lParam
0x140018c43  mov     rcx, r13; pinstance
0x140018c46  lea     r8d, [rdx+30h]; paramid
0x140018c4a  call    cs:__imp_JetSetSystemParameterW
0x140018c50  mov     r14d, eax
0x140018c53  test    eax, eax
0x140018c55  jz      short loc_140018C90
0x140018c57  mov     edi, 0Bh
0x140018c5c  mov     r10, cs:WPP_GLOBAL_Control
0x140018c63  lea     r12, WPP_GLOBAL_Control
0x140018c6a  cmp     r10, r12
0x140018c6d  jz      loc_140018FB9
0x140018c73  test    [r10+1Ch], bl
0x140018c77  jz      loc_140018FB9
0x140018c7d  cmp     byte ptr [r10+19h], 2
0x140018c82  jb      loc_140018FB9
0x140018c88  lea     edx, [rdi+0Ch]
0x140018c8b  jmp     loc_140018F9B
0x140018c90  xor     r9d, r9d; lParam
0x140018c93  mov     [rsp+3F0h+szParam], r15; szParam
0x140018c98  mov     r8d, ebx; paramid
0x140018c9b  xor     edx, edx; sesid
0x140018c9d  mov     rcx, r13; pinstance
0x140018ca0  call    cs:__imp_JetSetSystemParameterW
0x140018ca6  mov     r14d, eax
0x140018ca9  test    eax, eax
0x140018cab  jz      short loc_140018CE6
0x140018cad  mov     edi, 0Ch
0x140018cb2  mov     r10, cs:WPP_GLOBAL_Control
0x140018cb9  lea     r12, WPP_GLOBAL_Control
0x140018cc0  cmp     r10, r12
0x140018cc3  jz      loc_140018FB9
0x140018cc9  test    [r10+1Ch], bl
0x140018ccd  jz      loc_140018FB9
0x140018cd3  cmp     byte ptr [r10+19h], 2
0x140018cd8  jb      loc_140018FB9
0x140018cde  lea     edx, [rdi+0Ch]
0x140018ce1  jmp     loc_140018F9B
0x140018ce6  xor     r9d, r9d; lParam
0x140018ce9  mov     [rsp+3F0h+szParam], r15; szParam
0x140018cee  xor     edx, edx; sesid
0x140018cf0  mov     rcx, r13; pinstance
0x140018cf3  lea     r8d, [r9+71h]; paramid
0x140018cf7  call    cs:__imp_JetSetSystemParameterW
0x140018cfd  mov     r14d, eax
0x140018d00  test    eax, eax
0x140018d02  jz      short loc_140018D3D
0x140018d04  mov     edi, 0Dh
0x140018d09  mov     r10, cs:WPP_GLOBAL_Control
0x140018d10  lea     r12, WPP_GLOBAL_Control
0x140018d17  cmp     r10, r12
0x140018d1a  jz      loc_140018FB9
0x140018d20  test    [r10+1Ch], bl
0x140018d24  jz      loc_140018FB9
0x140018d2a  cmp     byte ptr [r10+19h], 2
0x140018d2f  jb      loc_140018FB9
0x140018d35  lea     edx, [rdi+0Ch]
0x140018d38  jmp     loc_140018F9B
0x140018d3d  xor     r9d, r9d; lParam
0x140018d40  mov     [rsp+3F0h+szParam], rdi; szParam
0x140018d45  xor     edx, edx; sesid
0x140018d47  mov     rcx, r13; pinstance
0x140018d4a  lea     r8d, [r9+33h]; paramid
0x140018d4e  call    cs:__imp_JetSetSystemParameterW
0x140018d54  mov     r14d, eax
0x140018d57  test    eax, eax
0x140018d59  jz      short loc_140018D94
0x140018d5b  mov     edi, 0Eh
0x140018d60  mov     r10, cs:WPP_GLOBAL_Control
0x140018d67  lea     r12, WPP_GLOBAL_Control
0x140018d6e  cmp     r10, r12
0x140018d71  jz      loc_140018FB9
0x140018d77  test    [r10+1Ch], bl
0x140018d7b  jz      loc_140018FB9
0x140018d81  cmp     byte ptr [r10+19h], 2
0x140018d86  jb      loc_140018FB9
0x140018d8c  lea     edx, [rdi+0Dh]
0x140018d8f  jmp     loc_140018F9B
0x140018d94  xor     edx, edx; sesid
0x140018d96  mov     [rsp+3F0h+szParam], rdi; szParam
0x140018d9b  mov     r9, rbx; lParam
0x140018d9e  mov     rcx, r13; pinstance
0x140018da1  lea     r8d, [rdx+2Dh]; paramid
0x140018da5  call    cs:__imp_JetSetSystemParameterW
0x140018dab  mov     r14d, eax
0x140018dae  test    eax, eax
0x140018db0  jz      short loc_140018DEB
0x140018db2  mov     edi, 0Fh
0x140018db7  mov     r10, cs:WPP_GLOBAL_Control
0x140018dbe  lea     r12, WPP_GLOBAL_Control
0x140018dc5  cmp     r10, r12
0x140018dc8  jz      loc_140018FB9
0x140018dce  test    [r10+1Ch], bl
0x140018dd2  jz      loc_140018FB9
0x140018dd8  cmp     byte ptr [r10+19h], 2
0x140018ddd  jb      loc_140018FB9
0x140018de3  lea     edx, [rdi+0Dh]
0x140018de6  jmp     loc_140018F9B
0x140018deb  xor     edx, edx; sesid
0x140018ded  mov     [rsp+3F0h+szParam], rdi; szParam
0x140018df2  mov     r9, rbx; lParam
  ... truncated ...
```
