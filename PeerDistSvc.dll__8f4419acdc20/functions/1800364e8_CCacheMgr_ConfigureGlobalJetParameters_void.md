# CCacheMgr::ConfigureGlobalJetParameters(void)

- ea: `0x1800364e8`
- end: `0x18003698d`
- name: `?ConfigureGlobalJetParameters@CCacheMgr@@AEAAKXZ`
- size: `1189`
- prototype: `unsigned int __fastcall(CCacheMgr *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180038b50`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800364e8`

## import_xrefs

- `ESENT!JetGetSystemParameterW` at `0x1800367ae`
- `ESENT!JetGetSystemParameterW` at `0x18003688a`
- `ESENT!JetGetSystemParameterW` at `0x1800367ae`
- `ESENT!JetGetSystemParameterW` at `0x18003688a`
- `ESENT!JetSetSystemParameterW` at `0x180036664`
- `ESENT!JetSetSystemParameterW` at `0x1800366b5`
- `ESENT!JetSetSystemParameterW` at `0x180036703`
- `ESENT!JetSetSystemParameterW` at `0x180036753`
- `ESENT!JetSetSystemParameterW` at `0x180036664`
- `ESENT!JetSetSystemParameterW` at `0x1800366b5`
- `ESENT!JetSetSystemParameterW` at `0x180036703`
- `ESENT!JetSetSystemParameterW` at `0x180036753`

## pseudocode

```c
__int64 __fastcall CCacheMgr::ConfigureGlobalJetParameters(CCacheMgr *this)
{
  CHostedCacheMsgEncoding *v1; // rcx
  unsigned int v2; // ebx
  unsigned int SystemParameterW; // eax
  CHostedCacheMsgEncoding *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // esi
  CHostedCacheMsgEncoding *v7; // rcx
  unsigned int v8; // edi
  JET_API_PTR plParam; // [rsp+60h] [rbp+8h] BYREF

  plParam = (JET_API_PTR)this;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 60, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids);
      v1 = WPP_GLOBAL_Control;
    }
    if ( v1 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v1 + 108) & 4) != 0 && *((_BYTE *)v1 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v1 + 12), 61, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids);
        v1 = WPP_GLOBAL_Control;
      }
      if ( v1 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v1 + 108) & 4) != 0 && *((_BYTE *)v1 + 105) >= 3u )
        {
          WPP_SF_(*((_QWORD *)v1 + 12), 62, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids);
          v1 = WPP_GLOBAL_Control;
        }
        if ( v1 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v1 + 108) & 4) != 0 && *((_BYTE *)v1 + 105) >= 3u )
          {
            WPP_SF_(*((_QWORD *)v1 + 12), 63, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids);
            v1 = WPP_GLOBAL_Control;
          }
          if ( v1 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v1 + 108) & 4) != 0 && *((_BYTE *)v1 + 105) >= 3u )
            {
              WPP_SF_d(*((_QWORD *)v1 + 12), 64, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids, 0x8000);
              v1 = WPP_GLOBAL_Control;
            }
            if ( v1 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v1 + 108) & 4) != 0 && *((_BYTE *)v1 + 105) >= 3u )
              {
                WPP_SF_d(*((_QWORD *)v1 + 12), 65, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids, 0x8000);
                v1 = WPP_GLOBAL_Control;
              }
              if ( v1 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_BYTE *)v1 + 108) & 4) != 0
                && *((_BYTE *)v1 + 105) >= 3u )
              {
                WPP_SF_(*((_QWORD *)v1 + 12), 66, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids);
              }
            }
          }
        }
      }
    }
  }
  v2 = 0;
  SystemParameterW = JetSetSystemParameterW(0, 0, 0x7Eu, 1u, 0);
  if ( SystemParameterW )
  {
    if ( SystemParameterW != -1030 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return 774;
      }
      v5 = 68;
      goto LABEL_62;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 67, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids, 4294966266LL);
    }
  }
  SystemParameterW = JetSetSystemParameterW(0, 0, 0x7Fu, 1u, 0);
  if ( SystemParameterW )
  {
    if ( SystemParameterW != -1030 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return 774;
      }
      v5 = 70;
      goto LABEL_62;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 69, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids, 4294966266LL);
    }
  }
  SystemParameterW = JetSetSystemParameterW(0, 0, 0x40u, 0x8000u, 0);
  if ( SystemParameterW )
  {
    if ( SystemParameterW != -1030 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return 774;
      }
      v5 = 72;
      goto LABEL_62;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 71, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids, 4294966266LL);
    }
  }
  SystemParameterW = JetSetSystemParameterW(0, 0, 0x80u, 0x8000u, 0);
  if ( SystemParameterW )
  {
    if ( SystemParameterW != -1030 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return 774;
      }
      v5 = 74;
      goto LABEL_62;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 73, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids, 4294966266LL);
    }
  }
  plParam = 0;
  SystemParameterW = JetGetSystemParameterW(0, 0, 0x86u, &plParam, 0, 0);
  if ( SystemParameterW )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return 774;
    }
    v5 = 75;
LABEL_62:
    WPP_SF_d(*((_QWORD *)v4 + 12), v5, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids, SystemParameterW);
    return 774;
  }
  v6 = plParam;
  SystemParameterW = JetGetSystemParameterW(0, 0, 0xABu, &plParam, 0, 0);
  if ( SystemParameterW )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return 774;
    }
    v5 = 76;
    goto LABEL_62;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    v8 = plParam;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 77, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v7 + 108) & 4) != 0 && *((_BYTE *)v7 + 105) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)v7 + 12), 78, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids, v6);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v7 + 108) & 4) != 0 && *((_BYTE *)v7 + 105) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)v7 + 12), 79, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids, v8);
          v7 = WPP_GLOBAL_Control;
        }
        if ( v7 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)v7 + 108) & 4) != 0
          && *((_BYTE *)v7 + 105) >= 3u )
        {
          WPP_SF_(*((_QWORD *)v7 + 12), 80, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids);
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800364e8  mov     [rsp+arg_8], rbx
0x1800364ed  mov     [rsp+arg_10], rbp
0x1800364f2  mov     [rsp+plParam], rcx
0x1800364f7  push    rsi
0x1800364f8  push    rdi
0x1800364f9  push    r13
0x1800364fb  push    r14
0x1800364fd  push    r15
0x1800364ff  sub     rsp, 30h
0x180036503  mov     rcx, cs:WPP_GLOBAL_Control
0x18003650a  lea     r14, WPP_GLOBAL_Control
0x180036511  lea     r15, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids
0x180036518  mov     r13d, 8000h
0x18003651e  mov     bpl, 4
0x180036521  cmp     rcx, r14
0x180036524  jz      loc_18003664F
0x18003652a  test    [rcx+6Ch], bpl
0x18003652e  jz      short loc_18003654E
0x180036530  cmp     [rcx+69h], bpl
0x180036534  jb      short loc_18003654E
0x180036536  mov     rcx, [rcx+60h]
0x18003653a  mov     edx, 3Ch ; '<'
0x18003653f  mov     r8, r15
0x180036542  call    WPP_SF_
0x180036547  mov     rcx, cs:WPP_GLOBAL_Control
0x18003654e  cmp     rcx, r14
0x180036551  jz      loc_18003664F
0x180036557  test    [rcx+6Ch], bpl
0x18003655b  jz      short loc_18003657B
0x18003655d  cmp     byte ptr [rcx+69h], 3
0x180036561  jb      short loc_18003657B
0x180036563  mov     rcx, [rcx+60h]
0x180036567  mov     edx, 3Dh ; '='
0x18003656c  mov     r8, r15
0x18003656f  call    WPP_SF_
0x180036574  mov     rcx, cs:WPP_GLOBAL_Control
0x18003657b  cmp     rcx, r14
0x18003657e  jz      loc_18003664F
0x180036584  test    [rcx+6Ch], bpl
0x180036588  jz      short loc_1800365A8
0x18003658a  cmp     byte ptr [rcx+69h], 3
0x18003658e  jb      short loc_1800365A8
0x180036590  mov     rcx, [rcx+60h]
0x180036594  mov     edx, 3Eh ; '>'
0x180036599  mov     r8, r15
0x18003659c  call    WPP_SF_
0x1800365a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365a8  cmp     rcx, r14
0x1800365ab  jz      loc_18003664F
0x1800365b1  test    [rcx+6Ch], bpl
0x1800365b5  jz      short loc_1800365D5
0x1800365b7  cmp     byte ptr [rcx+69h], 3
0x1800365bb  jb      short loc_1800365D5
0x1800365bd  mov     rcx, [rcx+60h]
0x1800365c1  mov     edx, 3Fh ; '?'
0x1800365c6  mov     r8, r15
0x1800365c9  call    WPP_SF_
0x1800365ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365d5  cmp     rcx, r14
0x1800365d8  jz      short loc_18003664F
0x1800365da  test    [rcx+6Ch], bpl
0x1800365de  jz      short loc_180036601
0x1800365e0  cmp     byte ptr [rcx+69h], 3
0x1800365e4  jb      short loc_180036601
0x1800365e6  mov     rcx, [rcx+60h]
0x1800365ea  mov     edx, 40h ; '@'
0x1800365ef  mov     r9d, r13d
0x1800365f2  mov     r8, r15
0x1800365f5  call    WPP_SF_d
0x1800365fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180036601  cmp     rcx, r14
0x180036604  jz      short loc_18003664F
0x180036606  test    [rcx+6Ch], bpl
0x18003660a  jz      short loc_18003662D
0x18003660c  cmp     byte ptr [rcx+69h], 3
0x180036610  jb      short loc_18003662D
0x180036612  mov     rcx, [rcx+60h]
0x180036616  mov     edx, 41h ; 'A'
0x18003661b  mov     r9d, r13d
0x18003661e  mov     r8, r15
0x180036621  call    WPP_SF_d
0x180036626  mov     rcx, cs:WPP_GLOBAL_Control
0x18003662d  cmp     rcx, r14
0x180036630  jz      short loc_18003664F
0x180036632  test    [rcx+6Ch], bpl
0x180036636  jz      short loc_18003664F
0x180036638  cmp     byte ptr [rcx+69h], 3
0x18003663c  jb      short loc_18003664F
0x18003663e  mov     rcx, [rcx+60h]
0x180036642  mov     edx, 42h ; 'B'
0x180036647  mov     r8, r15
0x18003664a  call    WPP_SF_
0x18003664f  xor     ebx, ebx
0x180036651  xor     edx, edx; sesid
0x180036653  xor     ecx, ecx; pinstance
0x180036655  mov     [rsp+58h+szParam], rbx; szParam
0x18003665a  lea     edi, [rbx+1]
0x18003665d  mov     r9d, edi; lParam
0x180036660  lea     r8d, [rbx+7Eh]; paramid
0x180036664  call    cs:__imp_JetSetSystemParameterW
0x18003666a  mov     esi, 0FFFFFBFAh
0x18003666f  test    eax, eax
0x180036671  jz      short loc_1800366A5
0x180036673  cmp     eax, esi
0x180036675  jnz     loc_1800367DB
0x18003667b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036682  cmp     rcx, r14
0x180036685  jz      short loc_1800366A5
0x180036687  test    [rcx+6Ch], bpl
0x18003668b  jz      short loc_1800366A5
0x18003668d  cmp     [rcx+69h], bpl
0x180036691  jb      short loc_1800366A5
0x180036693  mov     rcx, [rcx+60h]
0x180036697  lea     edx, [rbx+43h]
0x18003669a  mov     r9d, esi
0x18003669d  mov     r8, r15
0x1800366a0  call    WPP_SF_d
0x1800366a5  xor     edx, edx; sesid
0x1800366a7  mov     [rsp+58h+szParam], rbx; szParam
0x1800366ac  mov     r9, rdi; lParam
0x1800366af  xor     ecx, ecx; pinstance
0x1800366b1  lea     r8d, [rdx+7Fh]; paramid
0x1800366b5  call    cs:__imp_JetSetSystemParameterW
0x1800366bb  test    eax, eax
0x1800366bd  jz      short loc_1800366F3
0x1800366bf  cmp     eax, esi
0x1800366c1  jnz     loc_180036811
0x1800366c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366ce  cmp     rcx, r14
0x1800366d1  jz      short loc_1800366F3
0x1800366d3  test    [rcx+6Ch], bpl
0x1800366d7  jz      short loc_1800366F3
0x1800366d9  cmp     [rcx+69h], bpl
0x1800366dd  jb      short loc_1800366F3
0x1800366df  mov     rcx, [rcx+60h]
0x1800366e3  mov     edx, 45h ; 'E'
0x1800366e8  mov     r9d, esi
0x1800366eb  mov     r8, r15
0x1800366ee  call    WPP_SF_d
0x1800366f3  xor     edx, edx; sesid
0x1800366f5  mov     [rsp+58h+szParam], rbx; szParam
0x1800366fa  mov     r9, r13; lParam
0x1800366fd  xor     ecx, ecx; pinstance
0x1800366ff  lea     r8d, [rdx+40h]; paramid
0x180036703  call    cs:__imp_JetSetSystemParameterW
0x180036709  test    eax, eax
0x18003670b  jz      short loc_180036741
0x18003670d  cmp     eax, esi
0x18003670f  jnz     loc_180036830
0x180036715  mov     rcx, cs:WPP_GLOBAL_Control
0x18003671c  cmp     rcx, r14
0x18003671f  jz      short loc_180036741
0x180036721  test    [rcx+6Ch], bpl
0x180036725  jz      short loc_180036741
0x180036727  cmp     [rcx+69h], bpl
0x18003672b  jb      short loc_180036741
0x18003672d  mov     rcx, [rcx+60h]
0x180036731  mov     edx, 47h ; 'G'
0x180036736  mov     r9d, esi
0x180036739  mov     r8, r15
0x18003673c  call    WPP_SF_d
0x180036741  mov     r9, r13; lParam
0x180036744  mov     [rsp+58h+szParam], rbx; szParam
0x180036749  xor     edx, edx; sesid
0x18003674b  xor     ecx, ecx; pinstance
0x18003674d  mov     r8d, 80h; paramid
0x180036753  call    cs:__imp_JetSetSystemParameterW
0x180036759  test    eax, eax
0x18003675b  jz      short loc_180036791
0x18003675d  cmp     eax, esi
0x18003675f  jnz     loc_18003684F
0x180036765  mov     rcx, cs:WPP_GLOBAL_Control
0x18003676c  cmp     rcx, r14
0x18003676f  jz      short loc_180036791
0x180036771  test    [rcx+6Ch], bpl
0x180036775  jz      short loc_180036791
0x180036777  cmp     [rcx+69h], bpl
0x18003677b  jb      short loc_180036791
0x18003677d  mov     rcx, [rcx+60h]
0x180036781  mov     edx, 49h ; 'I'
0x180036786  mov     r9d, esi
0x180036789  mov     r8, r15
0x18003678c  call    WPP_SF_d
0x180036791  mov     [rsp+58h+cbMax], ebx; cbMax
0x180036795  lea     r9, [rsp+58h+plParam]; plParam
0x18003679a  xor     edx, edx; sesid
0x18003679c  mov     [rsp+58h+szParam], rbx; szParam
0x1800367a1  xor     ecx, ecx; instance
0x1800367a3  mov     [rsp+58h+plParam], rbx
0x1800367a8  mov     r8d, 86h; paramid
0x1800367ae  call    cs:__imp_JetGetSystemParameterW
0x1800367b4  test    eax, eax
0x1800367b6  jz      loc_18003686E
0x1800367bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367c3  cmp     rcx, r14
0x1800367c6  jz      short loc_180036807
0x1800367c8  test    [rcx+6Ch], bpl
0x1800367cc  jz      short loc_180036807
0x1800367ce  cmp     [rcx+69h], dil
0x1800367d2  jb      short loc_180036807
0x1800367d4  mov     edx, 4Bh ; 'K'
0x1800367d9  jmp     short loc_1800367F8
0x1800367db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367e2  cmp     rcx, r14
0x1800367e5  jz      short loc_180036807
0x1800367e7  test    [rcx+6Ch], bpl
0x1800367eb  jz      short loc_180036807
0x1800367ed  cmp     [rcx+69h], dil
0x1800367f1  jb      short loc_180036807
0x1800367f3  mov     edx, 44h ; 'D'
0x1800367f8  mov     rcx, [rcx+60h]
0x1800367fc  mov     r9d, eax
0x1800367ff  mov     r8, r15
0x180036802  call    WPP_SF_d
0x180036807  mov     ebx, 306h
0x18003680c  jmp     loc_180036974
0x180036811  mov     rcx, cs:WPP_GLOBAL_Control
0x180036818  cmp     rcx, r14
0x18003681b  jz      short loc_180036807
0x18003681d  test    [rcx+6Ch], bpl
0x180036821  jz      short loc_180036807
0x180036823  cmp     [rcx+69h], dil
0x180036827  jb      short loc_180036807
0x180036829  mov     edx, 46h ; 'F'
0x18003682e  jmp     short loc_1800367F8
0x180036830  mov     rcx, cs:WPP_GLOBAL_Control
0x180036837  cmp     rcx, r14
0x18003683a  jz      short loc_180036807
0x18003683c  test    [rcx+6Ch], bpl
0x180036840  jz      short loc_180036807
0x180036842  cmp     [rcx+69h], dil
0x180036846  jb      short loc_180036807
0x180036848  mov     edx, 48h ; 'H'
0x18003684d  jmp     short loc_1800367F8
0x18003684f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036856  cmp     rcx, r14
0x180036859  jz      short loc_180036807
0x18003685b  test    [rcx+6Ch], bpl
0x18003685f  jz      short loc_180036807
0x180036861  cmp     [rcx+69h], dil
0x180036865  jb      short loc_180036807
0x180036867  mov     edx, 4Ah ; 'J'
0x18003686c  jmp     short loc_1800367F8
0x18003686e  mov     esi, dword ptr [rsp+58h+plParam]
0x180036872  lea     r9, [rsp+58h+plParam]; plParam
0x180036877  mov     [rsp+58h+cbMax], ebx; cbMax
0x18003687b  xor     edx, edx; sesid
0x18003687d  xor     ecx, ecx; instance
0x18003687f  mov     [rsp+58h+szParam], rbx; szParam
0x180036884  mov     r8d, 0ABh; paramid
0x18003688a  call    cs:__imp_JetGetSystemParameterW
0x180036890  test    eax, eax
0x180036892  jz      short loc_1800368C2
0x180036894  mov     rcx, cs:WPP_GLOBAL_Control
0x18003689b  cmp     rcx, r14
0x18003689e  jz      loc_180036807
0x1800368a4  test    [rcx+6Ch], bpl
0x1800368a8  jz      loc_180036807
0x1800368ae  cmp     [rcx+69h], dil
0x1800368b2  jb      loc_180036807
0x1800368b8  mov     edx, 4Ch ; 'L'
0x1800368bd  jmp     loc_1800367F8
0x1800368c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800368c9  cmp     rcx, r14
0x1800368cc  jz      loc_180036974
0x1800368d2  mov     edi, dword ptr [rsp+58h+plParam]
0x1800368d6  test    [rcx+6Ch], bpl
0x1800368da  jz      short loc_1800368FA
0x1800368dc  cmp     byte ptr [rcx+69h], 3
0x1800368e0  jb      short loc_1800368FA
0x1800368e2  mov     rcx, [rcx+60h]
0x1800368e6  mov     edx, 4Dh ; 'M'
0x1800368eb  mov     r8, r15
0x1800368ee  call    WPP_SF_
0x1800368f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800368fa  cmp     rcx, r14
0x1800368fd  jz      short loc_180036974
0x1800368ff  test    [rcx+6Ch], bpl
0x180036903  jz      short loc_180036926
0x180036905  cmp     byte ptr [rcx+69h], 3
0x180036909  jb      short loc_180036926
0x18003690b  mov     rcx, [rcx+60h]
0x18003690f  mov     edx, 4Eh ; 'N'
0x180036914  mov     r9d, esi
0x180036917  mov     r8, r15
0x18003691a  call    WPP_SF_d
0x18003691f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036926  cmp     rcx, r14
0x180036929  jz      short loc_180036974
0x18003692b  test    [rcx+6Ch], bpl
0x18003692f  jz      short loc_180036952
0x180036931  cmp     byte ptr [rcx+69h], 3
0x180036935  jb      short loc_180036952
0x180036937  mov     rcx, [rcx+60h]
0x18003693b  mov     edx, 4Fh ; 'O'
0x180036940  mov     r9d, edi
0x180036943  mov     r8, r15
0x180036946  call    WPP_SF_d
0x18003694b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036952  cmp     rcx, r14
  ... truncated ...
```
