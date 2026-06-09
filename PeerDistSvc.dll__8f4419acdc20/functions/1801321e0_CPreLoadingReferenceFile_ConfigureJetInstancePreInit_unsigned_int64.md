# CPreLoadingReferenceFile::ConfigureJetInstancePreInit(unsigned __int64)

- ea: `0x1801321e0`
- end: `0x1801326f0`
- name: `?ConfigureJetInstancePreInit@CPreLoadingReferenceFile@@AEAAK_K@Z`
- size: `1296`
- prototype: `unsigned int __fastcall(CPreLoadingReferenceFile *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1801327c4`

## callees

- `0x180004374`
- `0x180008290`
- `0x180008798`
- `0x180018340`
- `0x1801321e0`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetSetSystemParameterW` at `0x1801324d6`
- `ESENT!JetSetSystemParameterW` at `0x180132521`
- `ESENT!JetSetSystemParameterW` at `0x180132571`
- `ESENT!JetSetSystemParameterW` at `0x1801325c2`
- `ESENT!JetSetSystemParameterW` at `0x180132611`
- `ESENT!JetSetSystemParameterW` at `0x18013265b`
- `ESENT!JetSetSystemParameterW` at `0x180132699`
- `ESENT!JetSetSystemParameterW` at `0x1801324d6`
- `ESENT!JetSetSystemParameterW` at `0x180132521`
- `ESENT!JetSetSystemParameterW` at `0x180132571`
- `ESENT!JetSetSystemParameterW` at `0x1801325c2`
- `ESENT!JetSetSystemParameterW` at `0x180132611`
- `ESENT!JetSetSystemParameterW` at `0x18013265b`
- `ESENT!JetSetSystemParameterW` at `0x180132699`

## pseudocode

```c
__int64 __fastcall CPreLoadingReferenceFile::ConfigureJetInstancePreInit(
        CPreLoadingReferenceFile *this,
        JET_INSTANCE a2)
{
  unsigned __int64 v2; // rbx
  unsigned int v4; // r14d
  unsigned __int64 v5; // r13
  unsigned __int64 v6; // rdi
  unsigned int MaxMemorySpace; // eax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r13
  JET_API_PTR v10; // r12
  CHostedCacheMsgEncoding *v11; // rcx
  const WCHAR *szParam; // r12
  unsigned int v13; // r15d
  CHostedCacheMsgEncoding *v14; // rcx
  __int64 v15; // rdx
  JET_API_PTR v17; // [rsp+80h] [rbp+48h] BYREF
  JET_INSTANCE pinstance; // [rsp+88h] [rbp+50h] BYREF
  unsigned __int64 v19; // [rsp+90h] [rbp+58h] BYREF
  JET_API_PTR lParam; // [rsp+98h] [rbp+60h]

  pinstance = a2;
  v2 = *((unsigned int *)this + 520);
  if ( !(_DWORD)v2 )
    return 4054;
  v5 = *((_QWORD *)this + 259);
  v6 = *((_QWORD *)this + 258);
  v19 = 0;
  v17 = 0;
  MaxMemorySpace = GetMaxMemorySpace(&v19, &v17);
  v4 = MaxMemorySpace;
  if ( !MaxMemorySpace )
  {
    v8 = v19;
    v9 = v5 >> 15;
    lParam = v6 / v2;
    if ( v19 > v17 )
      v8 = v17;
    v10 = (10 * (v8 / 0x64)) >> 15;
    if ( v10 > 0xFFFFFFFF )
      v10 = 0xFFFFFFFFLL;
    v17 = v10;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 30, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids);
        v11 = WPP_GLOBAL_Control;
      }
      if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v11 + 108) & 4) != 0 && *((_BYTE *)v11 + 105) >= 3u )
        {
          WPP_SF_(*((_QWORD *)v11 + 12), 31, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids);
          v11 = WPP_GLOBAL_Control;
        }
        if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v11 + 108) & 4) != 0 && *((_BYTE *)v11 + 105) >= 3u )
          {
            WPP_SF_S(*((_QWORD *)v11 + 12), 32, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, (char *)this + 2604);
            v11 = WPP_GLOBAL_Control;
          }
          if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v11 + 108) & 4) != 0 && *((_BYTE *)v11 + 105) >= 3u )
            {
              WPP_SF_S(*((_QWORD *)v11 + 12), 33, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, (char *)this + 2604);
              v11 = WPP_GLOBAL_Control;
            }
            if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v11 + 108) & 4) != 0 && *((_BYTE *)v11 + 105) >= 3u )
              {
                WPP_SF_S(*((_QWORD *)v11 + 12), 34, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, L"True");
                v11 = WPP_GLOBAL_Control;
              }
              if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v11 + 108) & 4) != 0 && *((_BYTE *)v11 + 105) >= 3u )
                {
                  WPP_SF_d(*((_QWORD *)v11 + 12), 35, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, (unsigned int)v9);
                  v11 = WPP_GLOBAL_Control;
                }
                if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v11 + 108) & 4) != 0 && *((_BYTE *)v11 + 105) >= 3u )
                  {
                    WPP_SF_d(*((_QWORD *)v11 + 12), 36, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, 0x4000);
                    v11 = WPP_GLOBAL_Control;
                  }
                  if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)v11 + 108) & 4) != 0 && *((_BYTE *)v11 + 105) >= 3u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)v11 + 12),
                        37,
                        WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids,
                        (unsigned int)v10);
                      v11 = WPP_GLOBAL_Control;
                    }
                    if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)v11 + 108) & 4) != 0 && *((_BYTE *)v11 + 105) >= 3u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)v11 + 12),
                          38,
                          WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids,
                          (unsigned int)lParam);
                        v11 = WPP_GLOBAL_Control;
                      }
                      if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)v11 + 108) & 4) != 0
                        && *((_BYTE *)v11 + 105) >= 3u )
                      {
                        WPP_SF_(*((_QWORD *)v11 + 12), 39, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids);
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
    szParam = (const WCHAR *)((char *)this + 2604);
    v13 = JetSetSystemParameterW(&pinstance, 0, 2u, 0, (JET_PCWSTR)this + 1302);
    if ( v13 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return TranslateJetError(v13);
      }
      v15 = 40;
    }
    else
    {
      v13 = JetSetSystemParameterW(&pinstance, 0, 0, 0, szParam);
      if ( v13 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          return TranslateJetError(v13);
        }
        v15 = 41;
      }
      else
      {
        v13 = JetSetSystemParameterW(&pinstance, 0, 0x11u, 1u, 0);
        if ( v13 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            return TranslateJetError(v13);
          }
          v15 = 42;
        }
        else if ( (_DWORD)v9 && (v13 = JetSetSystemParameterW(&pinstance, 0, 0x12u, (unsigned int)v9, 0)) != 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            return TranslateJetError(v13);
          }
          v15 = 43;
        }
        else
        {
          v13 = JetSetSystemParameterW(&pinstance, 0, 0xCu, 0x4000u, 0);
          if ( v13 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              return TranslateJetError(v13);
            }
            v15 = 44;
          }
          else
          {
            v13 = JetSetSystemParameterW(&pinstance, 0, 0xEu, (unsigned int)lParam, 0);
            if ( v13 )
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
                || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
                return TranslateJetError(v13);
              }
              v15 = 45;
            }
            else
            {
              v13 = JetSetSystemParameterW(&pinstance, 0, 9u, (unsigned int)v17, 0);
              if ( !v13 )
                return v4;
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
                || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
                return TranslateJetError(v13);
              }
              v15 = 46;
            }
          }
        }
      }
    }
    WPP_SF_d(*((_QWORD *)v14 + 12), v15, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, v13);
    return TranslateJetError(v13);
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, MaxMemorySpace);
  }
  return v4;
}

```

## disassembly

```asm
0x1801321e0  mov     [rsp-40h+pinstance], rdx
0x1801321e5  push    rbp
0x1801321e6  push    rbx
0x1801321e7  push    rsi
0x1801321e8  push    rdi
0x1801321e9  push    r12
0x1801321eb  push    r13
0x1801321ed  push    r14
0x1801321ef  push    r15
0x1801321f1  mov     rbp, rsp
0x1801321f4  sub     rsp, 38h
0x1801321f8  mov     ebx, [rcx+820h]
0x1801321fe  mov     r15, rcx
0x180132201  test    ebx, ebx
0x180132203  jnz     short loc_180132210
0x180132205  mov     r14d, 0FD6h
0x18013220b  jmp     loc_1801326DC
0x180132210  mov     r13, [rcx+818h]
0x180132217  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x18013221b  mov     rdi, [rcx+810h]
0x180132222  lea     rcx, [rbp+arg_10]; unsigned __int64 *
0x180132226  mov     [rbp+arg_10], 0
0x18013222e  mov     [rbp+arg_0], 0
0x180132236  call    ?GetMaxMemorySpace@@YAKPEA_K0@Z; GetMaxMemorySpace(unsigned __int64 *,unsigned __int64 *)
0x18013223b  mov     r14d, eax
0x18013223e  test    eax, eax
0x180132240  jz      short loc_18013228B
0x180132242  mov     rcx, cs:WPP_GLOBAL_Control
0x180132249  lea     rdi, WPP_GLOBAL_Control
0x180132250  cmp     rcx, rdi
0x180132253  jz      loc_1801326DC
0x180132259  mov     bl, 4
0x18013225b  test    [rcx+6Ch], bl
0x18013225e  jz      loc_1801326DC
0x180132264  cmp     byte ptr [rcx+69h], 1
0x180132268  jb      loc_1801326DC
0x18013226e  mov     rcx, [rcx+60h]
0x180132272  lea     r8, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x180132279  mov     edx, 1Dh
0x18013227e  mov     r9d, eax
0x180132281  call    WPP_SF_d
0x180132286  jmp     loc_1801326DC
0x18013228b  mov     rcx, [rbp+arg_10]
0x18013228f  xor     edx, edx
0x180132291  mov     rax, rdi
0x180132294  shr     r13, 0Fh
0x180132298  div     rbx
0x18013229b  cmp     rcx, [rbp+arg_0]
0x18013229f  mov     [rbp+lParam], rax
0x1801322a3  mov     rax, 47AE147AE147AE15h
0x1801322ad  cmova   rcx, [rbp+arg_0]
0x1801322b2  mul     rcx
0x1801322b5  mov     eax, 0FFFFFFFFh
0x1801322ba  sub     rcx, rdx
0x1801322bd  shr     rcx, 1
0x1801322c0  add     rcx, rdx
0x1801322c3  shr     rcx, 6
0x1801322c7  lea     r12, [rcx+rcx*4]
0x1801322cb  add     r12, r12
0x1801322ce  shr     r12, 0Fh
0x1801322d2  cmp     r12, rax
0x1801322d5  cmova   r12, rax
0x1801322d9  mov     [rbp+arg_0], r12
0x1801322dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1801322e4  lea     rdi, WPP_GLOBAL_Control
0x1801322eb  lea     rsi, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x1801322f2  mov     bl, 4
0x1801322f4  cmp     rcx, rdi
0x1801322f7  jz      loc_1801324BD
0x1801322fd  test    [rcx+6Ch], bl
0x180132300  jz      short loc_18013231F
0x180132302  cmp     [rcx+69h], bl
0x180132305  jb      short loc_18013231F
0x180132307  mov     rcx, [rcx+60h]
0x18013230b  mov     edx, 1Eh
0x180132310  mov     r8, rsi
0x180132313  call    WPP_SF_
0x180132318  mov     rcx, cs:WPP_GLOBAL_Control
0x18013231f  cmp     rcx, rdi
0x180132322  jz      loc_1801324BD
0x180132328  test    [rcx+6Ch], bl
0x18013232b  jz      short loc_18013234B
0x18013232d  cmp     byte ptr [rcx+69h], 3
0x180132331  jb      short loc_18013234B
0x180132333  mov     rcx, [rcx+60h]
0x180132337  mov     edx, 1Fh
0x18013233c  mov     r8, rsi
0x18013233f  call    WPP_SF_
0x180132344  mov     rcx, cs:WPP_GLOBAL_Control
0x18013234b  cmp     rcx, rdi
0x18013234e  jz      loc_1801324BD
0x180132354  test    [rcx+6Ch], bl
0x180132357  jz      short loc_18013237E
0x180132359  cmp     byte ptr [rcx+69h], 3
0x18013235d  jb      short loc_18013237E
0x18013235f  mov     rcx, [rcx+60h]
0x180132363  lea     r9, [r15+0A2Ch]
0x18013236a  mov     edx, 20h ; ' '
0x18013236f  mov     r8, rsi
0x180132372  call    WPP_SF_S
0x180132377  mov     rcx, cs:WPP_GLOBAL_Control
0x18013237e  cmp     rcx, rdi
0x180132381  jz      loc_1801324BD
0x180132387  test    [rcx+6Ch], bl
0x18013238a  jz      short loc_1801323B1
0x18013238c  cmp     byte ptr [rcx+69h], 3
0x180132390  jb      short loc_1801323B1
0x180132392  mov     rcx, [rcx+60h]
0x180132396  lea     r9, [r15+0A2Ch]
0x18013239d  mov     edx, 21h ; '!'
0x1801323a2  mov     r8, rsi
0x1801323a5  call    WPP_SF_S
0x1801323aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1801323b1  cmp     rcx, rdi
0x1801323b4  jz      loc_1801324BD
0x1801323ba  test    [rcx+6Ch], bl
0x1801323bd  jz      short loc_1801323E4
0x1801323bf  cmp     byte ptr [rcx+69h], 3
0x1801323c3  jb      short loc_1801323E4
0x1801323c5  mov     rcx, [rcx+60h]
0x1801323c9  lea     r9, aTrue_1; "True"
0x1801323d0  mov     edx, 22h ; '"'
0x1801323d5  mov     r8, rsi
0x1801323d8  call    WPP_SF_S
0x1801323dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1801323e4  cmp     rcx, rdi
0x1801323e7  jz      loc_1801324BD
0x1801323ed  test    [rcx+6Ch], bl
0x1801323f0  jz      short loc_180132413
0x1801323f2  cmp     byte ptr [rcx+69h], 3
0x1801323f6  jb      short loc_180132413
0x1801323f8  mov     rcx, [rcx+60h]
0x1801323fc  mov     edx, 23h ; '#'
0x180132401  mov     r9d, r13d
0x180132404  mov     r8, rsi
0x180132407  call    WPP_SF_d
0x18013240c  mov     rcx, cs:WPP_GLOBAL_Control
0x180132413  cmp     rcx, rdi
0x180132416  jz      loc_1801324BD
0x18013241c  test    [rcx+6Ch], bl
0x18013241f  jz      short loc_180132445
0x180132421  cmp     byte ptr [rcx+69h], 3
0x180132425  jb      short loc_180132445
0x180132427  mov     rcx, [rcx+60h]
0x18013242b  mov     edx, 24h ; '$'
0x180132430  mov     r9d, 4000h
0x180132436  mov     r8, rsi
0x180132439  call    WPP_SF_d
0x18013243e  mov     rcx, cs:WPP_GLOBAL_Control
0x180132445  cmp     rcx, rdi
0x180132448  jz      short loc_1801324BD
0x18013244a  test    [rcx+6Ch], bl
0x18013244d  jz      short loc_180132470
0x18013244f  cmp     byte ptr [rcx+69h], 3
0x180132453  jb      short loc_180132470
0x180132455  mov     rcx, [rcx+60h]
0x180132459  mov     r9d, r12d
0x18013245c  mov     edx, 25h ; '%'
0x180132461  mov     r8, rsi
0x180132464  call    WPP_SF_d
0x180132469  mov     rcx, cs:WPP_GLOBAL_Control
0x180132470  cmp     rcx, rdi
0x180132473  jz      short loc_1801324BD
0x180132475  test    [rcx+6Ch], bl
0x180132478  jz      short loc_18013249C
0x18013247a  cmp     byte ptr [rcx+69h], 3
0x18013247e  jb      short loc_18013249C
0x180132480  mov     r9d, dword ptr [rbp+lParam]
0x180132484  mov     edx, 26h ; '&'
0x180132489  mov     rcx, [rcx+60h]
0x18013248d  mov     r8, rsi
0x180132490  call    WPP_SF_d
0x180132495  mov     rcx, cs:WPP_GLOBAL_Control
0x18013249c  cmp     rcx, rdi
0x18013249f  jz      short loc_1801324BD
0x1801324a1  test    [rcx+6Ch], bl
0x1801324a4  jz      short loc_1801324BD
0x1801324a6  cmp     byte ptr [rcx+69h], 3
0x1801324aa  jb      short loc_1801324BD
0x1801324ac  mov     rcx, [rcx+60h]
0x1801324b0  mov     edx, 27h ; '''
0x1801324b5  mov     r8, rsi
0x1801324b8  call    WPP_SF_
0x1801324bd  xor     r9d, r9d; lParam
0x1801324c0  lea     r12, [r15+0A2Ch]
0x1801324c7  xor     edx, edx; sesid
0x1801324c9  mov     [rsp+38h+szParam], r12; szParam
0x1801324ce  lea     rcx, [rbp+pinstance]; pinstance
0x1801324d2  lea     r8d, [r9+2]; paramid
0x1801324d6  call    cs:__imp_JetSetSystemParameterW
0x1801324dc  mov     r15d, eax
0x1801324df  test    eax, eax
0x1801324e1  jz      short loc_180132510
0x1801324e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801324ea  cmp     rcx, rdi
0x1801324ed  jz      loc_1801326D1
0x1801324f3  test    [rcx+6Ch], bl
0x1801324f6  jz      loc_1801326D1
0x1801324fc  cmp     byte ptr [rcx+69h], 1
0x180132500  jb      loc_1801326D1
0x180132506  mov     edx, 28h ; '('
0x18013250b  jmp     loc_1801326C2
0x180132510  xor     r9d, r9d; lParam
0x180132513  mov     [rsp+38h+szParam], r12; szParam
0x180132518  xor     r8d, r8d; paramid
0x18013251b  lea     rcx, [rbp+pinstance]; pinstance
0x18013251f  xor     edx, edx; sesid
0x180132521  call    cs:__imp_JetSetSystemParameterW
0x180132527  xor     r12d, r12d
0x18013252a  mov     r15d, eax
0x18013252d  test    eax, eax
0x18013252f  jz      short loc_18013255E
0x180132531  mov     rcx, cs:WPP_GLOBAL_Control
0x180132538  cmp     rcx, rdi
0x18013253b  jz      loc_1801326D1
0x180132541  test    [rcx+6Ch], bl
0x180132544  jz      loc_1801326D1
0x18013254a  cmp     byte ptr [rcx+69h], 1
0x18013254e  jb      loc_1801326D1
0x180132554  lea     edx, [r12+29h]
0x180132559  jmp     loc_1801326C2
0x18013255e  xor     edx, edx; sesid
0x180132560  mov     [rsp+38h+szParam], r12; szParam
0x180132565  lea     rcx, [rbp+pinstance]; pinstance
0x180132569  lea     r9d, [rdx+1]; lParam
0x18013256d  lea     r8d, [rdx+11h]; paramid
0x180132571  call    cs:__imp_JetSetSystemParameterW
0x180132577  mov     r15d, eax
0x18013257a  test    eax, eax
0x18013257c  jz      short loc_1801325AB
0x18013257e  mov     rcx, cs:WPP_GLOBAL_Control
0x180132585  cmp     rcx, rdi
0x180132588  jz      loc_1801326D1
0x18013258e  test    [rcx+6Ch], bl
0x180132591  jz      loc_1801326D1
0x180132597  cmp     byte ptr [rcx+69h], 1
0x18013259b  jb      loc_1801326D1
0x1801325a1  mov     edx, 2Ah ; '*'
0x1801325a6  jmp     loc_1801326C2
0x1801325ab  test    r13d, r13d
0x1801325ae  jz      short loc_1801325FC
0x1801325b0  xor     edx, edx; sesid
0x1801325b2  mov     r9d, r13d; lParam
0x1801325b5  lea     rcx, [rbp+pinstance]; pinstance
0x1801325b9  mov     [rsp+38h+szParam], r12; szParam
0x1801325be  lea     r8d, [rdx+12h]; paramid
0x1801325c2  call    cs:__imp_JetSetSystemParameterW
0x1801325c8  mov     r15d, eax
0x1801325cb  test    eax, eax
0x1801325cd  jz      short loc_1801325FC
0x1801325cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801325d6  cmp     rcx, rdi
0x1801325d9  jz      loc_1801326D1
0x1801325df  test    [rcx+6Ch], bl
0x1801325e2  jz      loc_1801326D1
0x1801325e8  cmp     byte ptr [rcx+69h], 1
0x1801325ec  jb      loc_1801326D1
0x1801325f2  mov     edx, 2Bh ; '+'
0x1801325f7  jmp     loc_1801326C2
0x1801325fc  xor     edx, edx; sesid
0x1801325fe  mov     [rsp+38h+szParam], r12; szParam
0x180132603  mov     r9d, 4000h; lParam
0x180132609  lea     rcx, [rbp+pinstance]; pinstance
0x18013260d  lea     r8d, [rdx+0Ch]; paramid
0x180132611  call    cs:__imp_JetSetSystemParameterW
0x180132617  mov     r15d, eax
0x18013261a  test    eax, eax
0x18013261c  jz      short loc_180132648
0x18013261e  mov     rcx, cs:WPP_GLOBAL_Control
0x180132625  cmp     rcx, rdi
0x180132628  jz      loc_1801326D1
0x18013262e  test    [rcx+6Ch], bl
0x180132631  jz      loc_1801326D1
0x180132637  cmp     byte ptr [rcx+69h], 1
0x18013263b  jb      loc_1801326D1
0x180132641  mov     edx, 2Ch ; ','
0x180132646  jmp     short loc_1801326C2
0x180132648  mov     r9d, dword ptr [rbp+lParam]; lParam
0x18013264c  lea     rcx, [rbp+pinstance]; pinstance
0x180132650  xor     edx, edx; sesid
0x180132652  mov     [rsp+38h+szParam], r12; szParam
0x180132657  lea     r8d, [rdx+0Eh]; paramid
0x18013265b  call    cs:__imp_JetSetSystemParameterW
0x180132661  mov     r15d, eax
0x180132664  test    eax, eax
0x180132666  jz      short loc_180132686
0x180132668  mov     rcx, cs:WPP_GLOBAL_Control
0x18013266f  cmp     rcx, rdi
0x180132672  jz      short loc_1801326D1
0x180132674  test    [rcx+6Ch], bl
0x180132677  jz      short loc_1801326D1
0x180132679  cmp     byte ptr [rcx+69h], 1
0x18013267d  jb      short loc_1801326D1
0x18013267f  mov     edx, 2Dh ; '-'
0x180132684  jmp     short loc_1801326C2
0x180132686  mov     r9d, dword ptr [rbp+arg_0]; lParam
0x18013268a  lea     rcx, [rbp+pinstance]; pinstance
0x18013268e  xor     edx, edx; sesid
0x180132690  mov     [rsp+38h+szParam], r12; szParam
0x180132695  lea     r8d, [rdx+9]; paramid
  ... truncated ...
```
