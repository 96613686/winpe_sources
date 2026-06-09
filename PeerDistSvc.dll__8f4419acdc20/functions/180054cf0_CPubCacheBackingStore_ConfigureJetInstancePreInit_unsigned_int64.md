# CPubCacheBackingStore::ConfigureJetInstancePreInit(unsigned __int64)

- ea: `0x180054cf0`
- end: `0x180055369`
- name: `?ConfigureJetInstancePreInit@CPubCacheBackingStore@@AEAAK_K@Z`
- size: `1657`
- prototype: `unsigned int __fastcall(CPubCacheBackingStore *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800562b0`

## callees

- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x180018340`
- `0x180054cf0`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetSetSystemParameterW` at `0x180054fe5`
- `ESENT!JetSetSystemParameterW` at `0x18005503e`
- `ESENT!JetSetSystemParameterW` at `0x18005509b`
- `ESENT!JetSetSystemParameterW` at `0x1800550f9`
- `ESENT!JetSetSystemParameterW` at `0x180055157`
- `ESENT!JetSetSystemParameterW` at `0x1800551b4`
- `ESENT!JetSetSystemParameterW` at `0x18005520e`
- `ESENT!JetSetSystemParameterW` at `0x18005526b`
- `ESENT!JetSetSystemParameterW` at `0x1800552c8`
- `ESENT!JetSetSystemParameterW` at `0x180055313`
- `ESENT!JetSetSystemParameterW` at `0x180054fe5`
- `ESENT!JetSetSystemParameterW` at `0x18005503e`
- `ESENT!JetSetSystemParameterW` at `0x18005509b`
- `ESENT!JetSetSystemParameterW` at `0x1800550f9`
- `ESENT!JetSetSystemParameterW` at `0x180055157`
- `ESENT!JetSetSystemParameterW` at `0x1800551b4`
- `ESENT!JetSetSystemParameterW` at `0x18005520e`
- `ESENT!JetSetSystemParameterW` at `0x18005526b`
- `ESENT!JetSetSystemParameterW` at `0x1800552c8`
- `ESENT!JetSetSystemParameterW` at `0x180055313`

## pseudocode

```c
__int64 __fastcall CPubCacheBackingStore::ConfigureJetInstancePreInit(CPubCacheBackingStore *this, JET_INSTANCE a2)
{
  unsigned __int64 v2; // rax
  unsigned int v4; // ebx
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // r14
  __int64 v7; // rsi
  CHostedCacheMsgEncoding *v8; // rcx
  JET_ERR v9; // eax
  CHostedCacheMsgEncoding *v10; // rcx
  __int64 v11; // rdx
  JET_ERR v12; // eax
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  JET_ERR v18; // eax
  JET_ERR v19; // eax
  JET_ERR v20; // eax
  JET_INSTANCE pinstance; // [rsp+88h] [rbp+10h] BYREF

  pinstance = a2;
  v2 = *((unsigned int *)this + 48);
  if ( !(_DWORD)v2 )
    return 4054;
  v5 = *((_QWORD *)this + 19) >> 15;
  v6 = *((_QWORD *)this + 15) / v2;
  v7 = *((_QWORD *)this + 16) >> 15;
  if ( v5 > 0xFFFFFFFF )
    LODWORD(v5) = -1;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 32, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v8 + 108) & 4) != 0 && *((_BYTE *)v8 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v8 + 12), 33, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v8 + 108) & 4) != 0 && *((_BYTE *)v8 + 105) >= 3u )
        {
          WPP_SF_S(*((_QWORD *)v8 + 12), 34, WPP_817cd87503153d87380e6127cb13644a_Traceguids, (char *)this + 2320);
          v8 = WPP_GLOBAL_Control;
        }
        if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v8 + 108) & 4) != 0 && *((_BYTE *)v8 + 105) >= 3u )
          {
            WPP_SF_S(*((_QWORD *)v8 + 12), 35, WPP_817cd87503153d87380e6127cb13644a_Traceguids, (char *)this + 2320);
            v8 = WPP_GLOBAL_Control;
          }
          if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v8 + 108) & 4) != 0 && *((_BYTE *)v8 + 105) >= 3u )
            {
              WPP_SF_S(*((_QWORD *)v8 + 12), 36, WPP_817cd87503153d87380e6127cb13644a_Traceguids, L"True");
              v8 = WPP_GLOBAL_Control;
            }
            if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v8 + 108) & 4) != 0 && *((_BYTE *)v8 + 105) >= 3u )
              {
                WPP_SF_d(*((_QWORD *)v8 + 12), 37, WPP_817cd87503153d87380e6127cb13644a_Traceguids, (unsigned int)v7);
                v8 = WPP_GLOBAL_Control;
              }
              if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v8 + 108) & 4) != 0 && *((_BYTE *)v8 + 105) >= 3u )
                {
                  WPP_SF_d(
                    *((_QWORD *)v8 + 12),
                    38,
                    WPP_817cd87503153d87380e6127cb13644a_Traceguids,
                    *((unsigned int *)this + 40));
                  v8 = WPP_GLOBAL_Control;
                }
                if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v8 + 108) & 4) != 0 && *((_BYTE *)v8 + 105) >= 3u )
                  {
                    WPP_SF_d(*((_QWORD *)v8 + 12), 39, WPP_817cd87503153d87380e6127cb13644a_Traceguids, 1024);
                    v8 = WPP_GLOBAL_Control;
                  }
                  if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)v8 + 108) & 4) != 0 && *((_BYTE *)v8 + 105) >= 3u )
                    {
                      WPP_SF_d(*((_QWORD *)v8 + 12), 40, WPP_817cd87503153d87380e6127cb13644a_Traceguids, 0x8000);
                      v8 = WPP_GLOBAL_Control;
                    }
                    if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)v8 + 108) & 4) != 0 && *((_BYTE *)v8 + 105) >= 3u )
                      {
                        WPP_SF_d(*((_QWORD *)v8 + 12), 41, WPP_817cd87503153d87380e6127cb13644a_Traceguids, 0x4000);
                        v8 = WPP_GLOBAL_Control;
                      }
                      if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                      {
                        if ( (*((_BYTE *)v8 + 108) & 4) != 0 && *((_BYTE *)v8 + 105) >= 3u )
                        {
                          WPP_SF_d(
                            *((_QWORD *)v8 + 12),
                            42,
                            WPP_817cd87503153d87380e6127cb13644a_Traceguids,
                            (unsigned int)v5);
                          v8 = WPP_GLOBAL_Control;
                        }
                        if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                        {
                          if ( (*((_BYTE *)v8 + 108) & 4) != 0 && *((_BYTE *)v8 + 105) >= 3u )
                          {
                            WPP_SF_d(
                              *((_QWORD *)v8 + 12),
                              43,
                              WPP_817cd87503153d87380e6127cb13644a_Traceguids,
                              (unsigned int)v6);
                            v8 = WPP_GLOBAL_Control;
                          }
                          if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)v8 + 108) & 4) != 0
                            && *((_BYTE *)v8 + 105) >= 3u )
                          {
                            WPP_SF_(*((_QWORD *)v8 + 12), 44, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
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
  v9 = JetSetSystemParameterW(&pinstance, 0, 2u, 0, (JET_PCWSTR)this + 1160);
  if ( v9 )
  {
    v4 = TranslateJetError(v9);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v11 = 45;
LABEL_108:
      WPP_SF_Dd(*((_QWORD *)v10 + 12), v11, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
    }
  }
  else
  {
    v12 = JetSetSystemParameterW(&pinstance, 0, 0, 0, (JET_PCWSTR)this + 1160);
    v4 = 0;
    if ( v12 )
    {
      v4 = TranslateJetError(v12);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v11 = 46;
        goto LABEL_108;
      }
    }
    else
    {
      v13 = JetSetSystemParameterW(&pinstance, 0, 0x11u, 1u, 0);
      if ( v13 )
      {
        v4 = TranslateJetError(v13);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v11 = 47;
          goto LABEL_108;
        }
      }
      else if ( (_DWORD)v7 && (v14 = JetSetSystemParameterW(&pinstance, 0, 0x12u, (unsigned int)v7, 0)) != 0 )
      {
        v4 = TranslateJetError(v14);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v11 = 48;
          goto LABEL_108;
        }
      }
      else
      {
        v15 = JetSetSystemParameterW(&pinstance, 0, 0xCu, *((unsigned int *)this + 40), 0);
        if ( v15 )
        {
          v4 = TranslateJetError(v15);
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v11 = 49;
            goto LABEL_108;
          }
        }
        else
        {
          v16 = JetSetSystemParameterW(&pinstance, 0, 5u, 0x400u, 0);
          if ( v16 )
          {
            v4 = TranslateJetError(v16);
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              v11 = 50;
              goto LABEL_108;
            }
          }
          else
          {
            v17 = JetSetSystemParameterW(&pinstance, 0, 0xEu, (unsigned int)v6, 0);
            if ( v17 )
            {
              v4 = TranslateJetError(v17);
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
                v11 = 51;
                goto LABEL_108;
              }
            }
            else
            {
              v18 = JetSetSystemParameterW(&pinstance, 0, 8u, 0x8000u, 0);
              if ( v18 )
              {
                v4 = TranslateJetError(v18);
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  v11 = 52;
                  goto LABEL_108;
                }
              }
              else
              {
                v19 = JetSetSystemParameterW(&pinstance, 0, 6u, 0x4000u, 0);
                if ( v19 )
                {
                  v4 = TranslateJetError(v19);
                  v10 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                  {
                    v11 = 53;
                    goto LABEL_108;
                  }
                }
                else
                {
                  v20 = JetSetSystemParameterW(&pinstance, 0, 9u, (unsigned int)v5, 0);
                  if ( v20 )
                  {
                    v4 = TranslateJetError(v20);
                    v10 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                    {
                      v11 = 54;
                      goto LABEL_108;
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
0x180054cf0  mov     [rsp+pinstance], rdx
0x180054cf5  push    rbx
0x180054cf6  push    rbp
0x180054cf7  push    rsi
0x180054cf8  push    rdi
0x180054cf9  push    r12
0x180054cfb  push    r13
0x180054cfd  push    r14
0x180054cff  push    r15
0x180054d01  sub     rsp, 38h
0x180054d05  mov     eax, [rcx+0C0h]
0x180054d0b  mov     rdi, rcx
0x180054d0e  test    eax, eax
0x180054d10  jnz     short loc_180054D1C
0x180054d12  mov     ebx, 0FD6h
0x180054d17  jmp     loc_180055356
0x180054d1c  mov     rsi, [rcx+80h]
0x180054d23  xor     edx, edx
0x180054d25  mov     rbp, [rdi+98h]
0x180054d2c  mov     rcx, rax
0x180054d2f  mov     rax, [rdi+78h]
0x180054d33  div     rcx
0x180054d36  shr     rbp, 0Fh
0x180054d3a  mov     r14, rax
0x180054d3d  shr     rsi, 0Fh
0x180054d41  mov     eax, 0FFFFFFFFh
0x180054d46  cmp     rbp, rax
0x180054d49  cmova   rbp, rax
0x180054d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d54  lea     r12, WPP_GLOBAL_Control
0x180054d5b  lea     r13, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180054d62  mov     r15b, 4
0x180054d65  cmp     rcx, r12
0x180054d68  jz      loc_180054FC8
0x180054d6e  test    [rcx+6Ch], r15b
0x180054d72  jz      short loc_180054D92
0x180054d74  cmp     [rcx+69h], r15b
0x180054d78  jb      short loc_180054D92
0x180054d7a  mov     rcx, [rcx+60h]
0x180054d7e  mov     edx, 20h ; ' '
0x180054d83  mov     r8, r13
0x180054d86  call    WPP_SF_
0x180054d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d92  cmp     rcx, r12
0x180054d95  jz      loc_180054FC8
0x180054d9b  mov     bl, 3
0x180054d9d  test    [rcx+6Ch], r15b
0x180054da1  jz      short loc_180054DC0
0x180054da3  cmp     [rcx+69h], bl
0x180054da6  jb      short loc_180054DC0
0x180054da8  mov     rcx, [rcx+60h]
0x180054dac  mov     edx, 21h ; '!'
0x180054db1  mov     r8, r13
0x180054db4  call    WPP_SF_
0x180054db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180054dc0  cmp     rcx, r12
0x180054dc3  jz      loc_180054FC8
0x180054dc9  test    [rcx+6Ch], r15b
0x180054dcd  jz      short loc_180054DF3
0x180054dcf  cmp     [rcx+69h], bl
0x180054dd2  jb      short loc_180054DF3
0x180054dd4  mov     rcx, [rcx+60h]
0x180054dd8  lea     r9, [rdi+910h]
0x180054ddf  mov     edx, 22h ; '"'
0x180054de4  mov     r8, r13
0x180054de7  call    WPP_SF_S
0x180054dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180054df3  cmp     rcx, r12
0x180054df6  jz      loc_180054FC8
0x180054dfc  test    [rcx+6Ch], r15b
0x180054e00  jz      short loc_180054E26
0x180054e02  cmp     [rcx+69h], bl
0x180054e05  jb      short loc_180054E26
0x180054e07  mov     rcx, [rcx+60h]
0x180054e0b  lea     r9, [rdi+910h]
0x180054e12  mov     edx, 23h ; '#'
0x180054e17  mov     r8, r13
0x180054e1a  call    WPP_SF_S
0x180054e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054e26  cmp     rcx, r12
0x180054e29  jz      loc_180054FC8
0x180054e2f  test    [rcx+6Ch], r15b
0x180054e33  jz      short loc_180054E59
0x180054e35  cmp     [rcx+69h], bl
0x180054e38  jb      short loc_180054E59
0x180054e3a  mov     rcx, [rcx+60h]
0x180054e3e  lea     r9, aTrue_1; "True"
0x180054e45  mov     edx, 24h ; '$'
0x180054e4a  mov     r8, r13
0x180054e4d  call    WPP_SF_S
0x180054e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180054e59  cmp     rcx, r12
0x180054e5c  jz      loc_180054FC8
0x180054e62  test    [rcx+6Ch], r15b
0x180054e66  jz      short loc_180054E88
0x180054e68  cmp     [rcx+69h], bl
0x180054e6b  jb      short loc_180054E88
0x180054e6d  mov     rcx, [rcx+60h]
0x180054e71  mov     edx, 25h ; '%'
0x180054e76  mov     r9d, esi
0x180054e79  mov     r8, r13
0x180054e7c  call    WPP_SF_d
0x180054e81  mov     rcx, cs:WPP_GLOBAL_Control
0x180054e88  cmp     rcx, r12
0x180054e8b  jz      loc_180054FC8
0x180054e91  test    [rcx+6Ch], r15b
0x180054e95  jz      short loc_180054EBB
0x180054e97  cmp     [rcx+69h], bl
0x180054e9a  jb      short loc_180054EBB
0x180054e9c  mov     r9d, [rdi+0A0h]
0x180054ea3  mov     edx, 26h ; '&'
0x180054ea8  mov     rcx, [rcx+60h]
0x180054eac  mov     r8, r13
0x180054eaf  call    WPP_SF_d
0x180054eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ebb  cmp     rcx, r12
0x180054ebe  jz      loc_180054FC8
0x180054ec4  test    [rcx+6Ch], r15b
0x180054ec8  jz      short loc_180054EED
0x180054eca  cmp     [rcx+69h], bl
0x180054ecd  jb      short loc_180054EED
0x180054ecf  mov     rcx, [rcx+60h]
0x180054ed3  mov     edx, 27h ; '''
0x180054ed8  mov     r9d, 400h
0x180054ede  mov     r8, r13
0x180054ee1  call    WPP_SF_d
0x180054ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x180054eed  cmp     rcx, r12
0x180054ef0  jz      loc_180054FC8
0x180054ef6  test    [rcx+6Ch], r15b
0x180054efa  jz      short loc_180054F1F
0x180054efc  cmp     [rcx+69h], bl
0x180054eff  jb      short loc_180054F1F
0x180054f01  mov     rcx, [rcx+60h]
0x180054f05  mov     edx, 28h ; '('
0x180054f0a  mov     r9d, 8000h
0x180054f10  mov     r8, r13
0x180054f13  call    WPP_SF_d
0x180054f18  mov     rcx, cs:WPP_GLOBAL_Control
0x180054f1f  cmp     rcx, r12
0x180054f22  jz      loc_180054FC8
0x180054f28  test    [rcx+6Ch], r15b
0x180054f2c  jz      short loc_180054F51
0x180054f2e  cmp     [rcx+69h], bl
0x180054f31  jb      short loc_180054F51
0x180054f33  mov     rcx, [rcx+60h]
0x180054f37  mov     edx, 29h ; ')'
0x180054f3c  mov     r9d, 4000h
0x180054f42  mov     r8, r13
0x180054f45  call    WPP_SF_d
0x180054f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180054f51  cmp     rcx, r12
0x180054f54  jz      short loc_180054FC8
0x180054f56  test    [rcx+6Ch], r15b
0x180054f5a  jz      short loc_180054F7C
0x180054f5c  cmp     [rcx+69h], bl
0x180054f5f  jb      short loc_180054F7C
0x180054f61  mov     rcx, [rcx+60h]
0x180054f65  mov     r9d, ebp
0x180054f68  mov     edx, 2Ah ; '*'
0x180054f6d  mov     r8, r13
0x180054f70  call    WPP_SF_d
0x180054f75  mov     rcx, cs:WPP_GLOBAL_Control
0x180054f7c  cmp     rcx, r12
0x180054f7f  jz      short loc_180054FC8
0x180054f81  test    [rcx+6Ch], r15b
0x180054f85  jz      short loc_180054FA7
0x180054f87  cmp     [rcx+69h], bl
0x180054f8a  jb      short loc_180054FA7
0x180054f8c  mov     rcx, [rcx+60h]
0x180054f90  mov     edx, 2Bh ; '+'
0x180054f95  mov     r9d, r14d
0x180054f98  mov     r8, r13
0x180054f9b  call    WPP_SF_d
0x180054fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180054fa7  cmp     rcx, r12
0x180054faa  jz      short loc_180054FC8
0x180054fac  test    [rcx+6Ch], r15b
0x180054fb0  jz      short loc_180054FC8
0x180054fb2  cmp     [rcx+69h], bl
0x180054fb5  jb      short loc_180054FC8
0x180054fb7  mov     rcx, [rcx+60h]
0x180054fbb  mov     edx, 2Ch ; ','
0x180054fc0  mov     r8, r13
0x180054fc3  call    WPP_SF_
0x180054fc8  xor     r9d, r9d; lParam
0x180054fcb  lea     rbx, [rdi+910h]
0x180054fd2  xor     edx, edx; sesid
0x180054fd4  mov     [rsp+78h+szParam], rbx; szParam
0x180054fd9  lea     rcx, [rsp+78h+pinstance]; pinstance
0x180054fe1  lea     r8d, [r9+2]; paramid
0x180054fe5  call    cs:__imp_JetSetSystemParameterW
0x180054feb  mov     r9d, eax
0x180054fee  test    eax, eax
0x180054ff0  jz      short loc_180055029
0x180054ff2  mov     ecx, eax; int
0x180054ff4  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180054ff9  mov     ebx, eax
0x180054ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x180055002  cmp     rcx, r12
0x180055005  jz      loc_180055356
0x18005500b  test    [rcx+6Ch], r15b
0x18005500f  jz      loc_180055356
0x180055015  cmp     byte ptr [rcx+69h], 1
0x180055019  jb      loc_180055356
0x18005501f  mov     edx, 2Dh ; '-'
0x180055024  jmp     loc_180055346
0x180055029  xor     r9d, r9d; lParam
0x18005502c  mov     [rsp+78h+szParam], rbx; szParam
0x180055031  xor     r8d, r8d; paramid
0x180055034  lea     rcx, [rsp+78h+pinstance]; pinstance
0x18005503c  xor     edx, edx; sesid
0x18005503e  call    cs:__imp_JetSetSystemParameterW
0x180055044  xor     ebx, ebx
0x180055046  mov     r9d, eax
0x180055049  test    eax, eax
0x18005504b  jz      short loc_180055084
0x18005504d  mov     ecx, eax; int
0x18005504f  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180055054  mov     ebx, eax
0x180055056  mov     rcx, cs:WPP_GLOBAL_Control
0x18005505d  cmp     rcx, r12
0x180055060  jz      loc_180055356
0x180055066  test    [rcx+6Ch], r15b
0x18005506a  jz      loc_180055356
0x180055070  cmp     byte ptr [rcx+69h], 1
0x180055074  jb      loc_180055356
0x18005507a  mov     edx, 2Eh ; '.'
0x18005507f  jmp     loc_180055346
0x180055084  xor     edx, edx; sesid
0x180055086  mov     [rsp+78h+szParam], rbx; szParam
0x18005508b  lea     rcx, [rsp+78h+pinstance]; pinstance
0x180055093  lea     r9d, [rdx+1]; lParam
0x180055097  lea     r8d, [rdx+11h]; paramid
0x18005509b  call    cs:__imp_JetSetSystemParameterW
0x1800550a1  mov     r9d, eax
0x1800550a4  test    eax, eax
0x1800550a6  jz      short loc_1800550DF
0x1800550a8  mov     ecx, eax; int
0x1800550aa  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x1800550af  mov     ebx, eax
0x1800550b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800550b8  cmp     rcx, r12
0x1800550bb  jz      loc_180055356
0x1800550c1  test    [rcx+6Ch], r15b
0x1800550c5  jz      loc_180055356
0x1800550cb  cmp     byte ptr [rcx+69h], 1
0x1800550cf  jb      loc_180055356
0x1800550d5  mov     edx, 2Fh ; '/'
0x1800550da  jmp     loc_180055346
0x1800550df  test    esi, esi
0x1800550e1  jz      short loc_18005513D
0x1800550e3  xor     edx, edx; sesid
0x1800550e5  mov     r9d, esi; lParam
0x1800550e8  lea     rcx, [rsp+78h+pinstance]; pinstance
0x1800550f0  mov     [rsp+78h+szParam], rbx; szParam
0x1800550f5  lea     r8d, [rdx+12h]; paramid
0x1800550f9  call    cs:__imp_JetSetSystemParameterW
0x1800550ff  mov     r9d, eax
0x180055102  test    eax, eax
0x180055104  jz      short loc_18005513D
0x180055106  mov     ecx, eax; int
0x180055108  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18005510d  mov     ebx, eax
0x18005510f  mov     rcx, cs:WPP_GLOBAL_Control
0x180055116  cmp     rcx, r12
0x180055119  jz      loc_180055356
0x18005511f  test    [rcx+6Ch], r15b
0x180055123  jz      loc_180055356
0x180055129  cmp     byte ptr [rcx+69h], 1
0x18005512d  jb      loc_180055356
0x180055133  mov     edx, 30h ; '0'
0x180055138  jmp     loc_180055346
0x18005513d  mov     r9d, [rdi+0A0h]; lParam
0x180055144  lea     rcx, [rsp+78h+pinstance]; pinstance
0x18005514c  xor     edx, edx; sesid
0x18005514e  mov     [rsp+78h+szParam], rbx; szParam
0x180055153  lea     r8d, [rdx+0Ch]; paramid
0x180055157  call    cs:__imp_JetSetSystemParameterW
0x18005515d  mov     r9d, eax
0x180055160  test    eax, eax
0x180055162  jz      short loc_18005519B
0x180055164  mov     ecx, eax; int
0x180055166  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18005516b  mov     ebx, eax
0x18005516d  mov     rcx, cs:WPP_GLOBAL_Control
0x180055174  cmp     rcx, r12
0x180055177  jz      loc_180055356
0x18005517d  test    [rcx+6Ch], r15b
0x180055181  jz      loc_180055356
0x180055187  cmp     byte ptr [rcx+69h], 1
0x18005518b  jb      loc_180055356
0x180055191  mov     edx, 31h ; '1'
0x180055196  jmp     loc_180055346
0x18005519b  xor     edx, edx; sesid
0x18005519d  mov     [rsp+78h+szParam], rbx; szParam
0x1800551a2  mov     r9d, 400h; lParam
0x1800551a8  lea     rcx, [rsp+78h+pinstance]; pinstance
0x1800551b0  lea     r8d, [rdx+5]; paramid
0x1800551b4  call    cs:__imp_JetSetSystemParameterW
  ... truncated ...
```
