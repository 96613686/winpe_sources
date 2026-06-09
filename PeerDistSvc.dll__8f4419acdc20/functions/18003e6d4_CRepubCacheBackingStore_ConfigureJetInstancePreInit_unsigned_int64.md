# CRepubCacheBackingStore::ConfigureJetInstancePreInit(unsigned __int64)

- ea: `0x18003e6d4`
- end: `0x18003edaa`
- name: `?ConfigureJetInstancePreInit@CRepubCacheBackingStore@@AEAAK_K@Z`
- size: `1750`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180041740`

## callees

- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x180018340`
- `0x18003e6d4`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetSetSystemParameterW` at `0x18003ea22`
- `ESENT!JetSetSystemParameterW` at `0x18003ea7d`
- `ESENT!JetSetSystemParameterW` at `0x18003ead8`
- `ESENT!JetSetSystemParameterW` at `0x18003eb36`
- `ESENT!JetSetSystemParameterW` at `0x18003eb91`
- `ESENT!JetSetSystemParameterW` at `0x18003ebee`
- `ESENT!JetSetSystemParameterW` at `0x18003ec48`
- `ESENT!JetSetSystemParameterW` at `0x18003eca5`
- `ESENT!JetSetSystemParameterW` at `0x18003ed02`
- `ESENT!JetSetSystemParameterW` at `0x18003ed50`
- `ESENT!JetSetSystemParameterW` at `0x18003ea22`
- `ESENT!JetSetSystemParameterW` at `0x18003ea7d`
- `ESENT!JetSetSystemParameterW` at `0x18003ead8`
- `ESENT!JetSetSystemParameterW` at `0x18003eb36`
- `ESENT!JetSetSystemParameterW` at `0x18003eb91`
- `ESENT!JetSetSystemParameterW` at `0x18003ebee`
- `ESENT!JetSetSystemParameterW` at `0x18003ec48`
- `ESENT!JetSetSystemParameterW` at `0x18003eca5`
- `ESENT!JetSetSystemParameterW` at `0x18003ed02`
- `ESENT!JetSetSystemParameterW` at `0x18003ed50`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::ConfigureJetInstancePreInit(CRepubCacheBackingStore *this, JET_INSTANCE a2)
{
  unsigned __int64 v2; // rdi
  unsigned int v4; // ebx
  unsigned __int64 v5; // r14
  unsigned __int64 v6; // rsi
  __int64 v7; // rbp
  JET_API_PTR v8; // r15
  CHostedCacheMsgEncoding *v9; // r10
  JET_ERR v10; // eax
  CHostedCacheMsgEncoding *v11; // rcx
  __int64 v12; // rdx
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  JET_ERR v18; // eax
  JET_ERR v19; // eax
  JET_ERR v20; // eax
  JET_ERR v21; // eax
  JET_INSTANCE pinstance; // [rsp+88h] [rbp+10h] BYREF

  pinstance = a2;
  v2 = *((unsigned int *)this + 38);
  if ( !(_DWORD)v2 )
    return 4054;
  v5 = *((_QWORD *)this + 415);
  v6 = *((_QWORD *)this + 14) >> 15;
  v7 = *((_QWORD *)this + 416) >> 15;
  if ( v6 > 0xFFFFFFFF )
    LODWORD(v6) = -1;
  if ( v5 > 0x7FFFFFFF )
    *((_QWORD *)this + 415) = 0x7FFFFFFF;
  v8 = *((unsigned int *)this + 830);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 30, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v9 + 12), 31, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
        {
          WPP_SF_S(*((_QWORD *)v9 + 12), 32, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, (char *)this + 2272);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
          {
            WPP_SF_S(*((_QWORD *)v9 + 12), 33, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, (char *)this + 2272);
            v9 = WPP_GLOBAL_Control;
          }
          if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
            {
              WPP_SF_S(*((_QWORD *)v9 + 12), 34, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, L"True");
              v9 = WPP_GLOBAL_Control;
            }
            if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
              {
                WPP_SF_d(*((_QWORD *)v9 + 12), 35, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, (unsigned int)v7);
                v9 = WPP_GLOBAL_Control;
              }
              if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
                {
                  WPP_SF_d(
                    *((_QWORD *)v9 + 12),
                    36,
                    WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
                    *((unsigned int *)this + 30));
                  v9 = WPP_GLOBAL_Control;
                }
                if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
                  {
                    WPP_SF_d(*((_QWORD *)v9 + 12), 37, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, 1024);
                    v9 = WPP_GLOBAL_Control;
                  }
                  if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
                    {
                      WPP_SF_d(*((_QWORD *)v9 + 12), 38, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, 0x8000);
                      v9 = WPP_GLOBAL_Control;
                    }
                    if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
                      {
                        WPP_SF_d(*((_QWORD *)v9 + 12), 39, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, 0x4000);
                        v9 = WPP_GLOBAL_Control;
                      }
                      if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                      {
                        if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
                        {
                          WPP_SF_d(
                            *((_QWORD *)v9 + 12),
                            40,
                            WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
                            (unsigned int)v6);
                          v9 = WPP_GLOBAL_Control;
                        }
                        if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                        {
                          if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
                          {
                            WPP_SF_d(*((_QWORD *)v9 + 12), 41, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v5 / v2);
                            v9 = WPP_GLOBAL_Control;
                          }
                          if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)v9 + 108) & 4) != 0
                            && *((_BYTE *)v9 + 105) >= 3u )
                          {
                            WPP_SF_(*((_QWORD *)v9 + 12), 42, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
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
  }
  v10 = JetSetSystemParameterW(&pinstance, 0, 2u, 0, (JET_PCWSTR)this + 1136);
  if ( v10 )
  {
    v4 = TranslateJetError(v10);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v12 = 43;
LABEL_110:
      WPP_SF_Dd(*((_QWORD *)v11 + 12), v12, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    }
  }
  else
  {
    v13 = JetSetSystemParameterW(&pinstance, 0, 0, 0, (JET_PCWSTR)this + 1136);
    if ( v13 )
    {
      v4 = TranslateJetError(v13);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v12 = 44;
        goto LABEL_110;
      }
    }
    else
    {
      v14 = JetSetSystemParameterW(&pinstance, 0, 0x11u, 1u, 0);
      if ( v14 )
      {
        v4 = TranslateJetError(v14);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v12 = 45;
          goto LABEL_110;
        }
      }
      else if ( (_DWORD)v7 && (v15 = JetSetSystemParameterW(&pinstance, 0, 0x12u, (unsigned int)v7, 0)) != 0 )
      {
        v4 = TranslateJetError(v15);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v12 = 46;
          goto LABEL_110;
        }
      }
      else
      {
        v16 = JetSetSystemParameterW(&pinstance, 0, 0xCu, *((unsigned int *)this + 30), 0);
        if ( v16 )
        {
          v4 = TranslateJetError(v16);
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v12 = 47;
            goto LABEL_110;
          }
        }
        else
        {
          v17 = JetSetSystemParameterW(&pinstance, 0, 5u, 0x400u, 0);
          if ( v17 )
          {
            v4 = TranslateJetError(v17);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              v12 = 48;
              goto LABEL_110;
            }
          }
          else
          {
            v18 = JetSetSystemParameterW(&pinstance, 0, 0x18u, v8, 0);
            if ( v18 )
            {
              v4 = TranslateJetError(v18);
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
                v12 = 49;
                goto LABEL_110;
              }
            }
            else
            {
              v19 = JetSetSystemParameterW(&pinstance, 0, 8u, 0x8000u, 0);
              if ( v19 )
              {
                v4 = TranslateJetError(v19);
                v11 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  v12 = 50;
                  goto LABEL_110;
                }
              }
              else
              {
                v20 = JetSetSystemParameterW(&pinstance, 0, 6u, 0x4000u, 0);
                if ( v20 )
                {
                  v4 = TranslateJetError(v20);
                  v11 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                  {
                    v12 = 51;
                    goto LABEL_110;
                  }
                }
                else
                {
                  v4 = 0;
                  v21 = JetSetSystemParameterW(&pinstance, 0, 9u, (unsigned int)v6, 0);
                  if ( v21 )
                  {
                    v4 = TranslateJetError(v21);
                    v11 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                    {
                      v12 = 52;
                      goto LABEL_110;
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
  return v4;
}

```

## disassembly

```asm
0x18003e6d4  mov     [rsp+pinstance], rdx
0x18003e6d9  push    rbx
0x18003e6da  push    rbp
0x18003e6db  push    rsi
0x18003e6dc  push    rdi
0x18003e6dd  push    r12
0x18003e6df  push    r13
0x18003e6e1  push    r14
0x18003e6e3  push    r15
0x18003e6e5  sub     rsp, 38h
0x18003e6e9  mov     edi, [rcx+98h]
0x18003e6ef  mov     rbx, rcx
0x18003e6f2  test    edi, edi
0x18003e6f4  jnz     short loc_18003E700
0x18003e6f6  mov     ebx, 0FD6h
0x18003e6fb  jmp     loc_18003ED97
0x18003e700  mov     rbp, [rcx+0D00h]
0x18003e707  mov     eax, 0FFFFFFFFh
0x18003e70c  mov     rsi, [rcx+70h]
0x18003e710  mov     r14, [rcx+0CF8h]
0x18003e717  shr     rsi, 0Fh
0x18003e71b  shr     rbp, 0Fh
0x18003e71f  cmp     rsi, rax
0x18003e722  cmova   rsi, rax
0x18003e726  mov     eax, 7FFFFFFFh
0x18003e72b  cmp     r14, rax
0x18003e72e  jbe     short loc_18003E737
0x18003e730  mov     [rcx+0CF8h], rax
0x18003e737  mov     r15d, [rcx+0CF8h]
0x18003e73e  mov     r10, cs:WPP_GLOBAL_Control
0x18003e745  lea     r13, WPP_GLOBAL_Control
0x18003e74c  mov     r12b, 4
0x18003e74f  cmp     r10, r13
0x18003e752  jz      loc_18003EA05
0x18003e758  test    [r10+6Ch], r12b
0x18003e75c  jz      short loc_18003E780
0x18003e75e  cmp     [r10+69h], r12b
0x18003e762  jb      short loc_18003E780
0x18003e764  mov     rcx, [r10+60h]
0x18003e768  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e76f  mov     edx, 1Eh
0x18003e774  call    WPP_SF_
0x18003e779  mov     r10, cs:WPP_GLOBAL_Control
0x18003e780  cmp     r10, r13
0x18003e783  jz      loc_18003EA05
0x18003e789  test    [r10+6Ch], r12b
0x18003e78d  jz      short loc_18003E7B2
0x18003e78f  cmp     byte ptr [r10+69h], 3
0x18003e794  jb      short loc_18003E7B2
0x18003e796  mov     rcx, [r10+60h]
0x18003e79a  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e7a1  mov     edx, 1Fh
0x18003e7a6  call    WPP_SF_
0x18003e7ab  mov     r10, cs:WPP_GLOBAL_Control
0x18003e7b2  cmp     r10, r13
0x18003e7b5  jz      loc_18003EA05
0x18003e7bb  test    [r10+6Ch], r12b
0x18003e7bf  jz      short loc_18003E7EB
0x18003e7c1  cmp     byte ptr [r10+69h], 3
0x18003e7c6  jb      short loc_18003E7EB
0x18003e7c8  mov     rcx, [r10+60h]
0x18003e7cc  lea     r9, [rbx+8E0h]
0x18003e7d3  mov     edx, 20h ; ' '
0x18003e7d8  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e7df  call    WPP_SF_S
0x18003e7e4  mov     r10, cs:WPP_GLOBAL_Control
0x18003e7eb  cmp     r10, r13
0x18003e7ee  jz      loc_18003EA05
0x18003e7f4  test    [r10+6Ch], r12b
0x18003e7f8  jz      short loc_18003E824
0x18003e7fa  cmp     byte ptr [r10+69h], 3
0x18003e7ff  jb      short loc_18003E824
0x18003e801  mov     rcx, [r10+60h]
0x18003e805  lea     r9, [rbx+8E0h]
0x18003e80c  mov     edx, 21h ; '!'
0x18003e811  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e818  call    WPP_SF_S
0x18003e81d  mov     r10, cs:WPP_GLOBAL_Control
0x18003e824  cmp     r10, r13
0x18003e827  jz      loc_18003EA05
0x18003e82d  test    [r10+6Ch], r12b
0x18003e831  jz      short loc_18003E85D
0x18003e833  cmp     byte ptr [r10+69h], 3
0x18003e838  jb      short loc_18003E85D
0x18003e83a  mov     rcx, [r10+60h]
0x18003e83e  lea     r9, aTrue_1; "True"
0x18003e845  mov     edx, 22h ; '"'
0x18003e84a  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e851  call    WPP_SF_S
0x18003e856  mov     r10, cs:WPP_GLOBAL_Control
0x18003e85d  cmp     r10, r13
0x18003e860  jz      loc_18003EA05
0x18003e866  test    [r10+6Ch], r12b
0x18003e86a  jz      short loc_18003E892
0x18003e86c  cmp     byte ptr [r10+69h], 3
0x18003e871  jb      short loc_18003E892
0x18003e873  mov     rcx, [r10+60h]
0x18003e877  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e87e  mov     edx, 23h ; '#'
0x18003e883  mov     r9d, ebp
0x18003e886  call    WPP_SF_d
0x18003e88b  mov     r10, cs:WPP_GLOBAL_Control
0x18003e892  cmp     r10, r13
0x18003e895  jz      loc_18003EA05
0x18003e89b  test    [r10+6Ch], r12b
0x18003e89f  jz      short loc_18003E8C8
0x18003e8a1  cmp     byte ptr [r10+69h], 3
0x18003e8a6  jb      short loc_18003E8C8
0x18003e8a8  mov     r9d, [rbx+78h]
0x18003e8ac  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e8b3  mov     rcx, [r10+60h]
0x18003e8b7  mov     edx, 24h ; '$'
0x18003e8bc  call    WPP_SF_d
0x18003e8c1  mov     r10, cs:WPP_GLOBAL_Control
0x18003e8c8  cmp     r10, r13
0x18003e8cb  jz      loc_18003EA05
0x18003e8d1  test    [r10+6Ch], r12b
0x18003e8d5  jz      short loc_18003E900
0x18003e8d7  cmp     byte ptr [r10+69h], 3
0x18003e8dc  jb      short loc_18003E900
0x18003e8de  mov     rcx, [r10+60h]
0x18003e8e2  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e8e9  mov     edx, 25h ; '%'
0x18003e8ee  mov     r9d, 400h
0x18003e8f4  call    WPP_SF_d
0x18003e8f9  mov     r10, cs:WPP_GLOBAL_Control
0x18003e900  cmp     r10, r13
0x18003e903  jz      loc_18003EA05
0x18003e909  test    [r10+6Ch], r12b
0x18003e90d  jz      short loc_18003E938
0x18003e90f  cmp     byte ptr [r10+69h], 3
0x18003e914  jb      short loc_18003E938
0x18003e916  mov     rcx, [r10+60h]
0x18003e91a  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e921  mov     edx, 26h ; '&'
0x18003e926  mov     r9d, 8000h
0x18003e92c  call    WPP_SF_d
0x18003e931  mov     r10, cs:WPP_GLOBAL_Control
0x18003e938  cmp     r10, r13
0x18003e93b  jz      loc_18003EA05
0x18003e941  test    [r10+6Ch], r12b
0x18003e945  jz      short loc_18003E970
0x18003e947  cmp     byte ptr [r10+69h], 3
0x18003e94c  jb      short loc_18003E970
0x18003e94e  mov     rcx, [r10+60h]
0x18003e952  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e959  mov     edx, 27h ; '''
0x18003e95e  mov     r9d, 4000h
0x18003e964  call    WPP_SF_d
0x18003e969  mov     r10, cs:WPP_GLOBAL_Control
0x18003e970  cmp     r10, r13
0x18003e973  jz      loc_18003EA05
0x18003e979  test    [r10+6Ch], r12b
0x18003e97d  jz      short loc_18003E9A5
0x18003e97f  cmp     byte ptr [r10+69h], 3
0x18003e984  jb      short loc_18003E9A5
0x18003e986  mov     rcx, [r10+60h]
0x18003e98a  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e991  mov     r9d, esi
0x18003e994  mov     edx, 28h ; '('
0x18003e999  call    WPP_SF_d
0x18003e99e  mov     r10, cs:WPP_GLOBAL_Control
0x18003e9a5  cmp     r10, r13
0x18003e9a8  jz      short loc_18003EA05
0x18003e9aa  test    [r10+6Ch], r12b
0x18003e9ae  jz      short loc_18003E9DE
0x18003e9b0  cmp     byte ptr [r10+69h], 3
0x18003e9b5  jb      short loc_18003E9DE
0x18003e9b7  mov     rcx, [r10+60h]
0x18003e9bb  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e9c2  xor     edx, edx
0x18003e9c4  mov     rax, r14
0x18003e9c7  div     rdi
0x18003e9ca  mov     edx, 29h ; ')'
0x18003e9cf  mov     r9, rax
0x18003e9d2  call    WPP_SF_d
0x18003e9d7  mov     r10, cs:WPP_GLOBAL_Control
0x18003e9de  cmp     r10, r13
0x18003e9e1  jz      short loc_18003EA05
0x18003e9e3  test    [r10+6Ch], r12b
0x18003e9e7  jz      short loc_18003EA05
0x18003e9e9  cmp     byte ptr [r10+69h], 3
0x18003e9ee  jb      short loc_18003EA05
0x18003e9f0  mov     rcx, [r10+60h]
0x18003e9f4  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e9fb  mov     edx, 2Ah ; '*'
0x18003ea00  call    WPP_SF_
0x18003ea05  xor     r9d, r9d; lParam
0x18003ea08  lea     rdi, [rbx+8E0h]
0x18003ea0f  xor     edx, edx; sesid
0x18003ea11  mov     [rsp+78h+szParam], rdi; szParam
0x18003ea16  lea     rcx, [rsp+78h+pinstance]; pinstance
0x18003ea1e  lea     r8d, [r9+2]; paramid
0x18003ea22  call    cs:__imp_JetSetSystemParameterW
0x18003ea28  xor     r14d, r14d
0x18003ea2b  mov     r9d, eax
0x18003ea2e  test    eax, eax
0x18003ea30  jz      short loc_18003EA68
0x18003ea32  mov     ecx, eax; int
0x18003ea34  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003ea39  mov     ebx, eax
0x18003ea3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea42  cmp     rcx, r13
0x18003ea45  jz      loc_18003ED97
0x18003ea4b  test    [rcx+6Ch], r12b
0x18003ea4f  jz      loc_18003ED97
0x18003ea55  cmp     byte ptr [rcx+69h], 1
0x18003ea59  jb      loc_18003ED97
0x18003ea5f  lea     edx, [r14+2Bh]
0x18003ea63  jmp     loc_18003ED83
0x18003ea68  xor     r9d, r9d; lParam
0x18003ea6b  mov     [rsp+78h+szParam], rdi; szParam
0x18003ea70  xor     r8d, r8d; paramid
0x18003ea73  lea     rcx, [rsp+78h+pinstance]; pinstance
0x18003ea7b  xor     edx, edx; sesid
0x18003ea7d  call    cs:__imp_JetSetSystemParameterW
0x18003ea83  mov     r9d, eax
0x18003ea86  test    eax, eax
0x18003ea88  jz      short loc_18003EAC1
0x18003ea8a  mov     ecx, eax; int
0x18003ea8c  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003ea91  mov     ebx, eax
0x18003ea93  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea9a  cmp     rcx, r13
0x18003ea9d  jz      loc_18003ED97
0x18003eaa3  test    [rcx+6Ch], r12b
0x18003eaa7  jz      loc_18003ED97
0x18003eaad  cmp     byte ptr [rcx+69h], 1
0x18003eab1  jb      loc_18003ED97
0x18003eab7  mov     edx, 2Ch ; ','
0x18003eabc  jmp     loc_18003ED83
0x18003eac1  xor     edx, edx; sesid
0x18003eac3  mov     [rsp+78h+szParam], r14; szParam
0x18003eac8  lea     rcx, [rsp+78h+pinstance]; pinstance
0x18003ead0  lea     r9d, [rdx+1]; lParam
0x18003ead4  lea     r8d, [rdx+11h]; paramid
0x18003ead8  call    cs:__imp_JetSetSystemParameterW
0x18003eade  mov     r9d, eax
0x18003eae1  test    eax, eax
0x18003eae3  jz      short loc_18003EB1C
0x18003eae5  mov     ecx, eax; int
0x18003eae7  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003eaec  mov     ebx, eax
0x18003eaee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eaf5  cmp     rcx, r13
0x18003eaf8  jz      loc_18003ED97
0x18003eafe  test    [rcx+6Ch], r12b
0x18003eb02  jz      loc_18003ED97
0x18003eb08  cmp     byte ptr [rcx+69h], 1
0x18003eb0c  jb      loc_18003ED97
0x18003eb12  mov     edx, 2Dh ; '-'
0x18003eb17  jmp     loc_18003ED83
0x18003eb1c  test    ebp, ebp
0x18003eb1e  jz      short loc_18003EB7A
0x18003eb20  xor     edx, edx; sesid
0x18003eb22  mov     r9d, ebp; lParam
0x18003eb25  lea     rcx, [rsp+78h+pinstance]; pinstance
0x18003eb2d  mov     [rsp+78h+szParam], r14; szParam
0x18003eb32  lea     r8d, [rdx+12h]; paramid
0x18003eb36  call    cs:__imp_JetSetSystemParameterW
0x18003eb3c  mov     r9d, eax
0x18003eb3f  test    eax, eax
0x18003eb41  jz      short loc_18003EB7A
0x18003eb43  mov     ecx, eax; int
0x18003eb45  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003eb4a  mov     ebx, eax
0x18003eb4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eb53  cmp     rcx, r13
0x18003eb56  jz      loc_18003ED97
0x18003eb5c  test    [rcx+6Ch], r12b
0x18003eb60  jz      loc_18003ED97
0x18003eb66  cmp     byte ptr [rcx+69h], 1
0x18003eb6a  jb      loc_18003ED97
0x18003eb70  mov     edx, 2Eh ; '.'
0x18003eb75  jmp     loc_18003ED83
0x18003eb7a  mov     r9d, [rbx+78h]; lParam
0x18003eb7e  lea     rcx, [rsp+78h+pinstance]; pinstance
0x18003eb86  xor     edx, edx; sesid
0x18003eb88  mov     [rsp+78h+szParam], r14; szParam
0x18003eb8d  lea     r8d, [rdx+0Ch]; paramid
0x18003eb91  call    cs:__imp_JetSetSystemParameterW
0x18003eb97  mov     r9d, eax
0x18003eb9a  test    eax, eax
0x18003eb9c  jz      short loc_18003EBD5
0x18003eb9e  mov     ecx, eax; int
0x18003eba0  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003eba5  mov     ebx, eax
0x18003eba7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ebae  cmp     rcx, r13
0x18003ebb1  jz      loc_18003ED97
0x18003ebb7  test    [rcx+6Ch], r12b
0x18003ebbb  jz      loc_18003ED97
0x18003ebc1  cmp     byte ptr [rcx+69h], 1
0x18003ebc5  jb      loc_18003ED97
0x18003ebcb  mov     edx, 2Fh ; '/'
0x18003ebd0  jmp     loc_18003ED83
0x18003ebd5  xor     edx, edx; sesid
0x18003ebd7  mov     [rsp+78h+szParam], r14; szParam
0x18003ebdc  mov     r9d, 400h; lParam
0x18003ebe2  lea     rcx, [rsp+78h+pinstance]; pinstance
  ... truncated ...
```
