# CCookieContainerProps::SetCookie(CJetContext *,unsigned __int64,_RPC_COOKIE *,ushort const *)

- ea: `0x1800220c8`
- end: `0x180022842`
- name: `?SetCookie@CCookieContainerProps@@AEAAJPEAVCJetContext@@_KPEAU_RPC_COOKIE@@PEBG@Z`
- size: `1914`
- prototype: `int(CCookieContainerProps *__hidden this, struct CJetContext *, unsigned __int64, struct _RPC_COOKIE *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180022e70`
- `0x1801c8268`
- `0x1801c8aa0`

## callees

- `0x1800220c8`
- `0x180022848`
- `0x180022be0`
- `0x18007ec9c`
- `0x18007ed10`
- `0x1800ee168`
- `0x1800eee94`
- `0x18014a7a0`
- `0x1801c9384`
- `0x1801e1790`
- `0x1801e2f9c`
- `0x1801e3c78`
- `0x1801e6358`

## import_xrefs

- `ESENT!JetSetColumn` at `0x1800223ce`
- `ESENT!JetSetColumn` at `0x180022437`
- `ESENT!JetSetColumn` at `0x180022474`
- `ESENT!JetSetColumn` at `0x1800224ab`
- `ESENT!JetSetColumn` at `0x1800225b0`
- `ESENT!JetSetColumn` at `0x180022622`
- `ESENT!JetSetColumn` at `0x1800226a3`
- `ESENT!JetSetColumn` at `0x1800223ce`
- `ESENT!JetSetColumn` at `0x180022437`
- `ESENT!JetSetColumn` at `0x180022474`
- `ESENT!JetSetColumn` at `0x1800224ab`
- `ESENT!JetSetColumn` at `0x1800225b0`
- `ESENT!JetSetColumn` at `0x180022622`
- `ESENT!JetSetColumn` at `0x1800226a3`
- `ESENT!JetRetrieveColumn` at `0x180022542`
- `ESENT!JetRetrieveColumn` at `0x180022542`
- `ESENT!JetCommitTransaction` at `0x180022700`
- `ESENT!JetCommitTransaction` at `0x180022700`
- `ESENT!JetUpdate` at `0x1800224ce`
- `ESENT!JetUpdate` at `0x1800224ce`
- `ESENT!JetPrepareUpdate` at `0x180022332`
- `ESENT!JetPrepareUpdate` at `0x1800224f6`
- `ESENT!JetPrepareUpdate` at `0x180022332`
- `ESENT!JetPrepareUpdate` at `0x1800224f6`
- `ESENT!JetRollback` at `0x180022502`
- `ESENT!JetRollback` at `0x180022502`
- `ESENT!JetBeginTransaction` at `0x180022290`
- `ESENT!JetBeginTransaction` at `0x180022290`

## pseudocode

```c
__int64 __fastcall CCookieContainerProps::SetCookie(
        CCookieContainerProps *this,
        struct CJetContext *a2,
        unsigned __int64 a3,
        struct _RPC_COOKIE *a4,
        const unsigned __int16 *a5)
{
  unsigned int v5; // r14d
  JET_ERR BasicColumn; // ebx
  _WORD *v9; // r8
  unsigned int *v10; // r12
  unsigned int v11; // r9d
  const WCHAR *v12; // r11
  unsigned int v13; // ebx
  int v14; // edx
  int v15; // r10d
  unsigned int i; // r10d
  __int64 v17; // rax
  char *v18; // r11
  int v19; // edx
  _WORD *v20; // r9
  int v21; // r10d
  int v22; // edx
  int v23; // r8d
  int v24; // edx
  JET_SESID v25; // rcx
  JET_ERR v26; // eax
  int v28; // eax
  JET_ERR v29; // eax
  int v30; // edx
  int v31; // r8d
  unsigned int cbData; // ebx
  JET_TABLEID v33; // r15
  JET_SESID v34; // r12
  __int64 v35; // rcx
  __int64 v36; // r13
  JET_COLUMNID v37; // r14d
  JET_ERR v38; // eax
  unsigned int v39; // eax
  JET_ERR v40; // eax
  JET_ERR v41; // eax
  int v42; // edx
  int v43; // r8d
  JET_TABLEID v44; // r14
  JET_SESID v45; // r15
  JET_COLUMNID v46; // ebx
  JET_ERR v47; // eax
  unsigned int v48; // eax
  JET_ERR v49; // eax
  __int64 v50; // rcx
  unsigned int pcbActual; // [rsp+58h] [rbp-29h] BYREF
  unsigned __int64 v53; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int64 v54; // [rsp+68h] [rbp-19h] BYREF
  unsigned __int64 pvData; // [rsp+70h] [rbp-11h] BYREF
  unsigned int v56[2]; // [rsp+78h] [rbp-9h] BYREF
  int v57; // [rsp+80h] [rbp-1h]

  v5 = 0;
  v53 = a3;
  *(_QWORD *)v56 = 0;
  v57 = 0;
  pvData = 0;
  pcbActual = 0;
  v54 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qqiq(
      (_DWORD)this,
      30,
      (unsigned int)&WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids,
      (_DWORD)this,
      (__int64)a2,
      a3,
      (__int64)a4);
  BasicColumn = ValidateRpcCookie(a4);
  if ( BasicColumn >= 0 )
  {
    v9 = *(_WORD **)a4;
    v10 = (unsigned int *)((char *)a4 + 16);
    v11 = 0;
    v12 = &UnicodeCharStr;
    v13 = 0;
    v14 = 0;
    v15 = 0;
    do
    {
      v14 = dword_180226530[(unsigned __int64)*v12 >> 8]
          ^ __ROL4__(dword_180226530[(unsigned __int8)*v12] ^ __ROL4__(v14, 1), 1);
      if ( !*v12 )
        break;
      ++v12;
      ++v15;
    }
    while ( !v15 );
    if ( v9 )
    {
      for ( i = 0;
            i < *v10;
            v11 = dword_180226530[(unsigned __int64)(unsigned __int16)v9[v17] >> 8]
                ^ __ROL4__(dword_180226530[(unsigned __int8)v9[v17]] ^ __ROL4__(v11, 1), 1) )
      {
        v17 = i++;
      }
      v13 = v14;
    }
    if ( v53 != (v13 ^ ((unsigned __int64)v11 << 31)) )
    {
      BasicColumn = -2147024809;
      goto LABEL_20;
    }
    v18 = (char *)*((_QWORD *)a4 + 6);
    v19 = 0;
    v20 = (_WORD *)*((_QWORD *)a4 + 1);
    v21 = 0;
    if ( v9 )
    {
      do
      {
        v19 = dword_180226530[(unsigned __int64)(unsigned __int16)*v9 >> 8]
            ^ __ROL4__(dword_180226530[(unsigned __int8)*v9] ^ __ROL4__(v19, 1), 1);
        if ( !*v9 )
          break;
        ++v9;
        ++v21;
      }
      while ( v21 != -1 );
    }
    v56[0] = v19;
    v22 = 0;
    v23 = 0;
    if ( v20 )
    {
      do
      {
        v22 = dword_180226530[(unsigned __int64)(unsigned __int16)*v20 >> 8]
            ^ __ROL4__(dword_180226530[(unsigned __int8)*v20] ^ __ROL4__(v22, 1), 1);
        if ( !*v20 )
          break;
        ++v20;
        ++v23;
      }
      while ( v23 != -1 );
    }
    v56[1] = v22;
    v24 = 0;
    if ( v18 )
    {
      do
      {
        v50 = *v18++;
        v24 = dword_180226530[v50] ^ __ROL4__(v24, 1);
      }
      while ( (_BYTE)v50 );
    }
    v25 = *((_QWORD *)a2 + 2);
    v57 = v24;
    v26 = JetBeginTransaction(v25);
    BasicColumn = HRESULTFromJET_ERR(v26, 1);
    if ( BasicColumn >= 0 )
    {
      v28 = SeekToCookie(a2, v53, v56, a4);
      BasicColumn = v28;
      if ( v28 < 0 )
        goto LABEL_41;
      if ( !v28 )
      {
        if ( a5 )
        {
          BasicColumn = CJetContext::GetBasicColumn(a2, 0xAu, &v54, 8u);
          if ( BasicColumn < 0 )
            goto LABEL_41;
          if ( v54 > *((_QWORD *)a4 + 4) )
          {
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_(1036, 31, &WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids);
            BasicColumn = 1;
            goto LABEL_41;
          }
        }
        v5 = 2;
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_(1036, 32, &WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids);
      }
      v29 = JetPrepareUpdate(*((_QWORD *)a2 + 2), *((_QWORD *)a2 + 4), v5);
      BasicColumn = HRESULTFromJET_ERR(v29, 1);
      if ( BasicColumn >= 0 )
      {
        if ( *((_DWORD *)this + 25) )
        {
          v41 = JetRetrieveColumn(
                  *((_QWORD *)a2 + 2),
                  *((_QWORD *)a2 + 4),
                  **(_DWORD **)(*((_QWORD *)a2 + 5) + 8LL),
                  &pvData,
                  8u,
                  &pcbActual,
                  1u,
                  0);
          BasicColumn = HRESULTFromJET_ERR(v41, 1);
          if ( BasicColumn < 0 )
            goto LABEL_40;
        }
        if ( !v5 )
        {
          BasicColumn = JetSetColumn(
                          *((_QWORD *)a2 + 2),
                          *((_QWORD *)a2 + 4),
                          *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 5) + 8LL) + 4LL),
                          &v53,
                          8u,
                          0,
                          0);
          if ( BasicColumn < 0 )
            goto LABEL_40;
          v44 = *((_QWORD *)a2 + 4);
          v45 = *((_QWORD *)a2 + 2);
          v46 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 5) + 8LL) + 8LL);
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_iiiqd((unsigned int)v56, v42, v43, v45, v44, v46, (__int64)v56);
          v47 = JetSetColumn(v45, v44, v46, v56, 0xCu, 0, 0);
          v48 = HRESULTFromJET_ERR(v47, 1);
          BasicColumn = v48;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_d(1036, 21, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v48);
          if ( BasicColumn < 0 )
            goto LABEL_40;
          BasicColumn = CJetContext::SetStringColumn(a2, 3u, *(const unsigned __int16 **)a4);
          if ( BasicColumn < 0 )
            goto LABEL_40;
          BasicColumn = JetSetColumn(
                          *((_QWORD *)a2 + 2),
                          *((_QWORD *)a2 + 4),
                          *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 5) + 8LL) + 16LL),
                          (char *)a4 + 16,
                          4u,
                          0,
                          0);
          if ( BasicColumn < 0 )
            goto LABEL_40;
          BasicColumn = CJetContext::SetStringColumn(a2, 5u, *((const unsigned __int16 **)a4 + 1));
          if ( BasicColumn < 0 )
            goto LABEL_40;
          BasicColumn = CJetContext::SetBinaryColumn(a2, 6u, *((const unsigned __int8 **)a4 + 6), *((_DWORD *)a4 + 10));
          if ( BasicColumn < 0 )
            goto LABEL_40;
        }
        cbData = *((_DWORD *)a4 + 11);
        v33 = *((_QWORD *)a2 + 4);
        v34 = *((_QWORD *)a2 + 2);
        v35 = *(_QWORD *)(*((_QWORD *)a2 + 5) + 8LL);
        v36 = *((_QWORD *)a4 + 7);
        v37 = *(_DWORD *)(v35 + 28);
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_iiiqd(v35, v30, v31, v34, v33, v37, v36);
        v38 = JetSetColumn(v34, v33, v37, (const void *)(v36 & -(__int64)(cbData != 0)), cbData, 0, 0);
        v39 = HRESULTFromJET_ERR(v38, 1);
        BasicColumn = v39;
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_d(1036, 21, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v39);
        if ( BasicColumn >= 0
          && (BasicColumn = JetSetColumn(
                              *((_QWORD *)a2 + 2),
                              *((_QWORD *)a2 + 4),
                              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 5) + 8LL) + 32LL),
                              (char *)a4 + 20,
                              4u,
                              0,
                              0),
              BasicColumn >= 0)
          && (BasicColumn = JetSetColumn(
                              *((_QWORD *)a2 + 2),
                              *((_QWORD *)a2 + 4),
                              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 5) + 8LL) + 36LL),
                              (char *)a4 + 24,
                              8u,
                              0,
                              0),
              BasicColumn >= 0)
          && (BasicColumn = JetSetColumn(
                              *((_QWORD *)a2 + 2),
                              *((_QWORD *)a2 + 4),
                              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 5) + 8LL) + 40LL),
                              (char *)a4 + 32,
                              8u,
                              0,
                              0),
              BasicColumn >= 0)
          && (v40 = JetUpdate(*((_QWORD *)a2 + 2), *((_QWORD *)a2 + 4), 0, 0, 0),
              BasicColumn = HRESULTFromJET_ERR(v40, 1),
              BasicColumn >= 0) )
        {
          v49 = JetCommitTransaction(*((_QWORD *)a2 + 2), 1u);
          BasicColumn = HRESULTFromJET_ERR(v49, 1);
          if ( BasicColumn >= 0 )
          {
            if ( *((_DWORD *)this + 25) )
              CCookieContainerProps::UpdateRoamingCookieFile(this, pvData, a4, a5);
            BasicColumn = 0;
            goto LABEL_20;
          }
        }
        else
        {
LABEL_40:
          JetPrepareUpdate(*((_QWORD *)a2 + 2), *((_QWORD *)a2 + 4), 3u);
        }
      }
LABEL_41:
      JetRollback(*((_QWORD *)a2 + 2), 0);
    }
  }
LABEL_20:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 33, &WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids, (unsigned int)BasicColumn);
  return (unsigned int)BasicColumn;
}

```

## disassembly

```asm
0x1800220c8  push    rbp
0x1800220ca  push    rbx
0x1800220cb  push    rsi
0x1800220cc  push    rdi
0x1800220cd  push    r12
0x1800220cf  push    r13
0x1800220d1  push    r14
0x1800220d3  push    r15
0x1800220d5  lea     rbp, [rsp-17h]
0x1800220da  sub     rsp, 98h
0x1800220e1  mov     rax, cs:__security_cookie
0x1800220e8  xor     rax, rsp
0x1800220eb  mov     [rbp+4Fh+var_48], rax
0x1800220ef  mov     r13, [rbp+4Fh+arg_20]
0x1800220f3  xor     r14d, r14d
0x1800220f6  xor     eax, eax
0x1800220f8  mov     [rbp+4Fh+var_70], r8
0x1800220fc  mov     qword ptr [rbp+4Fh+var_58], rax
0x180022100  mov     rsi, r9
0x180022103  mov     [rbp+4Fh+var_50], eax
0x180022106  mov     rdi, rdx
0x180022109  mov     [rbp+4Fh+var_88], rcx
0x18002210d  mov     [rbp+4Fh+var_80], r13
0x180022111  mov     [rbp+4Fh+var_8C], r14d
0x180022115  mov     [rbp+4Fh+pvData], r14
0x180022119  mov     [rbp+4Fh+pcbActual], r14d
0x18002211d  mov     [rbp+4Fh+var_68], r14
0x180022121  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180022128  jz      short loc_18002214B
0x18002212a  mov     [rsp+0D0h+psetinfo], r9
0x18002212f  lea     edx, [rax+1Eh]
0x180022132  mov     qword ptr [rsp+0D0h+grbit], r8
0x180022137  mov     r9, rcx
0x18002213a  lea     r8, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids
0x180022141  mov     qword ptr [rsp+0D0h+cbData], rdi
0x180022146  call    WPP_SF_qqiq
0x18002214b  mov     rcx, rsi; struct _RPC_COOKIE *
0x18002214e  call    ?ValidateRpcCookie@@YAJPEAU_RPC_COOKIE@@@Z; ValidateRpcCookie(_RPC_COOKIE *)
0x180022153  mov     ebx, eax
0x180022155  test    eax, eax
0x180022157  js      loc_18002257A
0x18002215d  mov     r8, [rsi]
0x180022160  lea     r12, [rsi+10h]
0x180022164  mov     r9d, r14d
0x180022167  lea     r11, UnicodeCharStr
0x18002216e  mov     ebx, r14d
0x180022171  lea     r15, dword_180226530
0x180022178  mov     edx, r14d
0x18002217b  mov     r10d, r14d
0x18002217e  movzx   ecx, word ptr [r11]
0x180022182  rol     edx, 1
0x180022184  movzx   eax, cl
0x180022187  xor     edx, [r15+rax*4]
0x18002218b  mov     eax, ecx
0x18002218d  shr     rax, 8
0x180022191  rol     edx, 1
0x180022193  xor     edx, [r15+rax*4]
0x180022197  test    cx, cx
0x18002219a  jz      short loc_1800221A9
0x18002219c  add     r11, 2
0x1800221a0  inc     r10d
0x1800221a3  cmp     r10d, 1
0x1800221a7  jb      short loc_18002217E
0x1800221a9  mov     r15, [rbp+4Fh+var_88]
0x1800221ad  test    r8, r8
0x1800221b0  jz      short loc_1800221EA
0x1800221b2  mov     r10d, r14d
0x1800221b5  cmp     [r12], r14d
0x1800221b9  jbe     short loc_1800221E8
0x1800221bb  lea     r11, dword_180226530
0x1800221c2  rol     r9d, 1
0x1800221c5  mov     eax, r10d
0x1800221c8  inc     r10d
0x1800221cb  movzx   ecx, word ptr [r8+rax*2]
0x1800221d0  movzx   eax, cl
0x1800221d3  shr     rcx, 8
0x1800221d7  xor     r9d, [r11+rax*4]
0x1800221db  rol     r9d, 1
0x1800221de  xor     r9d, [r11+rcx*4]
0x1800221e2  cmp     r10d, [r12]
0x1800221e6  jb      short loc_1800221C2
0x1800221e8  mov     ebx, edx
0x1800221ea  mov     ecx, r9d
0x1800221ed  shl     rcx, 1Fh
0x1800221f1  mov     eax, ebx
0x1800221f3  xor     rcx, rax
0x1800221f6  cmp     [rbp+4Fh+var_70], rcx
0x1800221fa  jnz     loc_180022745
0x180022200  mov     r11, [rsi+30h]
0x180022204  mov     edx, r14d
0x180022207  mov     r9, [rsi+8]
0x18002220b  mov     r10d, r14d
0x18002220e  lea     rbx, dword_180226530
0x180022215  test    r8, r8
0x180022218  jz      short loc_180022243
0x18002221a  movzx   ecx, word ptr [r8]
0x18002221e  rol     edx, 1
0x180022220  movzx   eax, cl
0x180022223  xor     edx, [rbx+rax*4]
0x180022226  mov     eax, ecx
0x180022228  shr     rax, 8
0x18002222c  rol     edx, 1
0x18002222e  xor     edx, [rbx+rax*4]
0x180022231  test    cx, cx
0x180022234  jz      short loc_180022243
0x180022236  add     r8, 2
0x18002223a  inc     r10d
0x18002223d  cmp     r10d, 0FFFFFFFFh
0x180022241  jb      short loc_18002221A
0x180022243  mov     [rbp+4Fh+var_58], edx
0x180022246  mov     edx, r14d
0x180022249  mov     r8d, r14d
0x18002224c  test    r9, r9
0x18002224f  jz      short loc_18002227A
0x180022251  movzx   ecx, word ptr [r9]
0x180022255  rol     edx, 1
0x180022257  movzx   eax, cl
0x18002225a  xor     edx, [rbx+rax*4]
0x18002225d  mov     eax, ecx
0x18002225f  shr     rax, 8
0x180022263  rol     edx, 1
0x180022265  xor     edx, [rbx+rax*4]
0x180022268  test    cx, cx
0x18002226b  jz      short loc_18002227A
0x18002226d  add     r9, 2
0x180022271  inc     r8d
0x180022274  cmp     r8d, 0FFFFFFFFh
0x180022278  jb      short loc_180022251
0x18002227a  mov     [rbp+4Fh+var_58+4], edx
0x18002227d  mov     edx, r14d
0x180022280  test    r11, r11
0x180022283  jnz     loc_180022730
0x180022289  mov     rcx, [rdi+10h]; sesid
0x18002228d  mov     [rbp+4Fh+var_50], edx
0x180022290  call    cs:__imp_JetBeginTransaction
0x180022296  mov     ecx, eax; int
0x180022298  mov     edx, 1; int
0x18002229d  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800222a2  mov     ebx, eax
0x1800222a4  test    eax, eax
0x1800222a6  jns     short loc_1800222EC
0x1800222a8  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800222af  jz      short loc_1800222CA
0x1800222b1  mov     edx, 21h ; '!'
0x1800222b6  lea     r8, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids
0x1800222bd  mov     ecx, 40Ch
0x1800222c2  mov     r9d, ebx
0x1800222c5  call    WPP_SF_d
0x1800222ca  mov     eax, ebx
0x1800222cc  mov     rcx, [rbp+4Fh+var_48]
0x1800222d0  xor     rcx, rsp; StackCookie
0x1800222d3  call    __security_check_cookie
0x1800222d8  add     rsp, 98h
0x1800222df  pop     r15
0x1800222e1  pop     r14
0x1800222e3  pop     r13
0x1800222e5  pop     r12
0x1800222e7  pop     rdi
0x1800222e8  pop     rsi
0x1800222e9  pop     rbx
0x1800222ea  pop     rbp
0x1800222eb  retn
0x1800222ec  mov     rdx, [rbp+4Fh+var_70]; unsigned __int64
0x1800222f0  lea     r8, [rbp+4Fh+var_58]; unsigned int *
0x1800222f4  mov     r9, rsi; struct _RPC_COOKIE *
0x1800222f7  mov     rcx, rdi; struct CJetContext *
0x1800222fa  call    ?SeekToCookie@@YAJPEAVCJetContext@@_KPEAKPEAU_RPC_COOKIE@@@Z; SeekToCookie(CJetContext *,unsigned __int64,ulong *,_RPC_COOKIE *)
0x1800222ff  mov     ebx, eax
0x180022301  test    eax, eax
0x180022303  js      loc_180022756
0x180022309  jnz     short loc_180022327
0x18002230b  test    r13, r13
0x18002230e  jnz     loc_180022762
0x180022314  mov     r14d, 2
0x18002231a  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180022321  jnz     loc_18002255F
0x180022327  mov     rdx, [rdi+20h]; tableid
0x18002232b  mov     r8d, r14d; prep
0x18002232e  mov     rcx, [rdi+10h]; sesid
0x180022332  call    cs:__imp_JetPrepareUpdate
0x180022338  mov     ecx, eax; int
0x18002233a  mov     edx, 1; int
0x18002233f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180022344  xor     r13d, r13d
0x180022347  mov     ebx, eax
0x180022349  test    eax, eax
0x18002234b  js      loc_1800224FC
0x180022351  cmp     [r15+64h], r13d
0x180022355  jnz     loc_18002250D
0x18002235b  test    r14d, r14d
0x18002235e  jz      loc_180022586
0x180022364  mov     rax, [rdi+28h]
0x180022368  mov     ebx, [rsi+2Ch]
0x18002236b  mov     r15, [rdi+20h]
0x18002236f  mov     r12, [rdi+10h]
0x180022373  mov     rcx, [rax+8]
0x180022377  mov     r13, [rsi+38h]
0x18002237b  mov     r14d, [rcx+1Ch]
0x18002237f  mov     [rbp+4Fh+var_8C], 0
0x180022386  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18002238d  jz      short loc_1800223AA
0x18002238f  mov     dword ptr [rsp+0D0h+pretinfo], ebx
0x180022393  mov     r9, r12
0x180022396  mov     [rsp+0D0h+psetinfo], r13
0x18002239b  mov     qword ptr [rsp+0D0h+grbit], r14
0x1800223a0  mov     qword ptr [rsp+0D0h+cbData], r15
0x1800223a5  call    WPP_SF_iiiqd
0x1800223aa  mov     eax, ebx
0x1800223ac  mov     r8d, r14d; columnid
0x1800223af  neg     eax
0x1800223b1  mov     rdx, r15; tableid
0x1800223b4  mov     rcx, r12; sesid
0x1800223b7  sbb     r9, r9
0x1800223ba  and     r9, r13; pvData
0x1800223bd  xor     r13d, r13d
0x1800223c0  mov     [rsp+0D0h+psetinfo], r13; psetinfo
0x1800223c5  mov     [rsp+0D0h+grbit], r13d; grbit
0x1800223ca  mov     [rsp+0D0h+cbData], ebx; cbData
0x1800223ce  call    cs:__imp_JetSetColumn
0x1800223d4  lea     r14d, [r13+1]
0x1800223d8  mov     ecx, eax; int
0x1800223da  mov     edx, r14d; int
0x1800223dd  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800223e2  mov     ebx, eax
0x1800223e4  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800223eb  jz      short loc_180022405
0x1800223ed  lea     edx, [r13+15h]
0x1800223f1  mov     ecx, 40Ch
0x1800223f6  mov     r9d, eax
0x1800223f9  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x180022400  call    WPP_SF_d
0x180022405  test    ebx, ebx
0x180022407  js      loc_1800227FD
0x18002240d  mov     rax, [rdi+28h]
0x180022411  lea     r9, [rsi+14h]; pvData
0x180022415  mov     rdx, [rdi+20h]; tableid
0x180022419  mov     rcx, [rdi+10h]; sesid
0x18002241d  mov     [rsp+0D0h+psetinfo], r13; psetinfo
0x180022422  mov     r8, [rax+8]
0x180022426  mov     [rsp+0D0h+grbit], r13d; grbit
0x18002242b  mov     [rsp+0D0h+cbData], 4; cbData
0x180022433  mov     r8d, [r8+20h]; columnid
0x180022437  call    cs:__imp_JetSetColumn
0x18002243d  mov     ebx, eax
0x18002243f  test    eax, eax
0x180022441  js      loc_180022809
0x180022447  mov     rax, [rdi+28h]
0x18002244b  lea     r9, [rsi+18h]; pvData
0x18002244f  mov     rdx, [rdi+20h]; tableid
0x180022453  mov     r15d, 8
0x180022459  mov     rcx, [rdi+10h]; sesid
0x18002245d  mov     [rsp+0D0h+psetinfo], r13; psetinfo
0x180022462  mov     r8, [rax+8]
0x180022466  mov     [rsp+0D0h+grbit], r13d; grbit
0x18002246b  mov     [rsp+0D0h+cbData], r15d; cbData
0x180022470  mov     r8d, [r8+24h]; columnid
0x180022474  call    cs:__imp_JetSetColumn
0x18002247a  mov     ebx, eax
0x18002247c  test    eax, eax
0x18002247e  js      loc_180022815
0x180022484  mov     rax, [rdi+28h]
0x180022488  lea     r9, [rsi+20h]; pvData
0x18002248c  mov     rdx, [rdi+20h]; tableid
0x180022490  mov     rcx, [rdi+10h]; sesid
0x180022494  mov     [rsp+0D0h+psetinfo], r13; psetinfo
0x180022499  mov     r8, [rax+8]
0x18002249d  mov     [rsp+0D0h+grbit], r13d; grbit
0x1800224a2  mov     [rsp+0D0h+cbData], r15d; cbData
0x1800224a7  mov     r8d, [r8+28h]; columnid
0x1800224ab  call    cs:__imp_JetSetColumn
0x1800224b1  mov     ebx, eax
0x1800224b3  test    eax, eax
0x1800224b5  js      loc_180022821
0x1800224bb  mov     rdx, [rdi+20h]; tableid
0x1800224bf  xor     r9d, r9d; cbBookmark
0x1800224c2  mov     rcx, [rdi+10h]; sesid
0x1800224c6  xor     r8d, r8d; pvBookmark
0x1800224c9  mov     qword ptr [rsp+0D0h+cbData], r13; pcbActual
0x1800224ce  call    cs:__imp_JetUpdate
0x1800224d4  mov     ecx, eax; int
0x1800224d6  mov     edx, r14d; int
0x1800224d9  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800224de  mov     ebx, eax
0x1800224e0  test    eax, eax
0x1800224e2  jns     loc_1800226F9
0x1800224e8  mov     rdx, [rdi+20h]; tableid
0x1800224ec  mov     r8d, 3; prep
0x1800224f2  mov     rcx, [rdi+10h]; sesid
0x1800224f6  call    cs:__imp_JetPrepareUpdate
0x1800224fc  mov     rcx, [rdi+10h]; sesid
0x180022500  xor     edx, edx; grbit
0x180022502  call    cs:__imp_JetRollback
0x180022508  jmp     loc_1800222A8
0x18002250d  mov     rax, [rdi+28h]
0x180022511  lea     r9, [rbp+4Fh+pvData]; pvData
0x180022515  mov     rdx, [rdi+20h]; tableid
0x180022519  mov     rcx, [rdi+10h]; sesid
0x18002251d  mov     [rsp+0D0h+pretinfo], r13; pretinfo
0x180022522  mov     r8, [rax+8]
0x180022526  lea     rax, [rbp+4Fh+pcbActual]
  ... truncated ...
```
