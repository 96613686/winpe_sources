# Algorithms::QuickSort<ColumnEntry,CoreFragmentInspector::CompareTuplesFunctor,Algorithms::SwapFunctor<ColumnEntry>>(ColumnEntry *,ulong,CoreFragmentInspector::CompareTuplesFunctor,Algorithms::SwapFunctor<ColumnEntry>)

- ea: `0x180090bbc`
- end: `0x180090f6e`
- name: `??$QuickSort@UColumnEntry@@UCompareTuplesFunctor@CoreFragmentInspector@@U?$SwapFunctor@UColumnEntry@@@Algorithms@@@Algorithms@@SAXPEAUColumnEntry@@KUCompareTuplesFunctor@CoreFragmentInspector@@U?$SwapFunctor@UColumnEntry@@@0@@Z`
- size: `946`
- prototype: `signed __int64 __fastcall(unsigned __int64, unsigned int, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001c994`

## callees

- `0x180008ab0`
- `0x180011f60`
- `0x18001a1f0`
- `0x180090bbc`
- `0x180090f74`
- `0x180091018`
- `0x18009323e`
- `0x180093270`

## pseudocode

```c
signed __int64 __fastcall Algorithms::QuickSort<ColumnEntry,CoreFragmentInspector::CompareTuplesFunctor,Algorithms::SwapFunctor<ColumnEntry>>(
        unsigned __int64 a1,
        unsigned int a2,
        char a3)
{
  __int64 v4; // rdi
  signed __int64 result; // rax
  signed __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // r12d
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // r13
  _DWORD *v13; // rsi
  __int64 v14; // rcx
  int v15; // edi
  __int64 v16; // rcx
  int v17; // edi
  __int64 v18; // rcx
  int v19; // edi
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // r12
  unsigned __int64 v22; // rdi
  int v23; // edi
  unsigned __int64 v24; // rax
  int v25; // [rsp+20h] [rbp-E0h]
  _BYTE v26[4]; // [rsp+28h] [rbp-D8h] BYREF
  int v27; // [rsp+2Ch] [rbp-D4h]
  __int64 v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+38h] [rbp-C8h]
  _QWORD v30[62]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v31[62]; // [rsp+230h] [rbp+130h] BYREF

  v4 = a2;
  memset_0(v30, 0, sizeof(v30));
  result = (signed __int64)memset_0(v31, 0, sizeof(v31));
  if ( (unsigned int)v4 >= 2 )
  {
    v9 = 0;
    v25 = 0;
    v10 = a1 + 24 * (v4 - 1);
    while ( 1 )
    {
      while ( 1 )
      {
        v11 = -1431655765 * (unsigned int)((__int64)(v10 - a1) >> 3) + 1;
        if ( (unsigned int)v11 <= 8 )
        {
          LOBYTE(v8) = a3;
          result = Algorithms::ShortSort<ColumnEntry,CoreFragmentInspector::CompareTuplesFunctor,Algorithms::SwapFunctor<ColumnEntry>>(
                     a1,
                     v10,
                     v8);
          goto LABEL_5;
        }
        v12 = a1 + 24 * (v11 >> 1);
        v13 = (_DWORD *)(v12 + 16);
        if ( (int)CoreFragmentInspector::CompareTuplesFunctor::operator()(v7, a1, v12) > 0 )
        {
          v27 = *(_DWORD *)(a1 + 4);
          v28 = *(_QWORD *)(a1 + 8);
          SyncId::AddRef((SyncId *)v26);
          v29 = *(_DWORD *)(a1 + 16);
          v15 = v29;
          SyncId::operator=(a1, v12);
          *(_DWORD *)(a1 + 16) = *v13;
          SyncId::operator=(v12, v26);
          *v13 = v15;
          SyncId::~SyncId((SyncId *)v26);
        }
        if ( (int)CoreFragmentInspector::CompareTuplesFunctor::operator()(v14, a1, v10) > 0 )
        {
          v27 = *(_DWORD *)(a1 + 4);
          v28 = *(_QWORD *)(a1 + 8);
          SyncId::AddRef((SyncId *)v26);
          v29 = *(_DWORD *)(a1 + 16);
          v17 = v29;
          SyncId::operator=(a1, v10);
          *(_DWORD *)(a1 + 16) = *(_DWORD *)(v10 + 16);
          SyncId::operator=(v10, v26);
          *(_DWORD *)(v10 + 16) = v17;
          SyncId::~SyncId((SyncId *)v26);
        }
        if ( (int)CoreFragmentInspector::CompareTuplesFunctor::operator()(v16, v12, v10) > 0 )
        {
          v27 = *(_DWORD *)(v12 + 4);
          v28 = *(_QWORD *)(v12 + 8);
          SyncId::AddRef((SyncId *)v26);
          v29 = *v13;
          v19 = v29;
          SyncId::operator=(v12, v10);
          *v13 = *(_DWORD *)(v10 + 16);
          SyncId::operator=(v10, v26);
          *(_DWORD *)(v10 + 16) = v19;
          SyncId::~SyncId((SyncId *)v26);
        }
        v20 = a1;
        v21 = v10;
        while ( 1 )
        {
          if ( v12 > v20 )
          {
            while ( 1 )
            {
              v20 += 24LL;
              if ( v20 >= v12 )
                break;
              if ( (int)CoreFragmentInspector::CompareTuplesFunctor::operator()(v18, v20, v12) > 0 )
                goto LABEL_20;
            }
          }
          do
            v20 += 24LL;
          while ( v20 <= v10 && (int)CoreFragmentInspector::CompareTuplesFunctor::operator()(v18, v20, v12) <= 0 );
          do
          {
LABEL_20:
            v22 = v21;
            v21 -= 24LL;
          }
          while ( v21 > v12 && (int)CoreFragmentInspector::CompareTuplesFunctor::operator()(v18, v21, v12) > 0 );
          if ( v21 < v20 )
            break;
          v27 = *(_DWORD *)(v20 + 4);
          v28 = *(_QWORD *)(v20 + 8);
          SyncId::AddRef((SyncId *)v26);
          v29 = *(_DWORD *)(v20 + 16);
          v23 = v29;
          SyncId::operator=(v20, v21);
          *(_DWORD *)(v20 + 16) = *(_DWORD *)(v21 + 16);
          SyncId::operator=(v21, v26);
          *(_DWORD *)(v21 + 16) = v23;
          SyncId::~SyncId((SyncId *)v26);
          v24 = v20;
          if ( v12 != v21 )
            v24 = v12;
          v12 = v24;
        }
        if ( v12 < v22 )
        {
          while ( 1 )
          {
            v22 -= 24LL;
            if ( v22 <= v12 )
              break;
            if ( (unsigned int)CoreFragmentInspector::CompareTuplesFunctor::operator()(v18, v22, v12) )
              goto LABEL_32;
          }
        }
        do
          v22 -= 24LL;
        while ( v22 > a1 && !(unsigned int)CoreFragmentInspector::CompareTuplesFunctor::operator()(v18, v22, v12) );
LABEL_32:
        v7 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v10 - v20) >> 3);
        result = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v22 - a1) >> 3);
        if ( result >= v7 )
          break;
        if ( v20 >= v10 )
        {
          v9 = v25;
        }
        else
        {
          v30[v25] = v20;
          v31[v25] = v10;
          v9 = ++v25;
        }
        if ( a1 >= v22 )
        {
LABEL_5:
          v25 = --v9;
          if ( v9 < 0 )
            return result;
          a1 = v30[v9];
          v10 = v31[v9];
        }
        else
        {
          v10 = v22;
        }
      }
      if ( a1 >= v22 )
      {
        v9 = v25;
      }
      else
      {
        v30[v25] = a1;
        v31[v25] = v22;
        v9 = ++v25;
      }
      if ( v20 >= v10 )
        goto LABEL_5;
      a1 = v20;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180090bbc  mov     [rsp-8+arg_18], rbx
0x180090bc1  push    rbp
0x180090bc2  push    rsi
0x180090bc3  push    rdi
0x180090bc4  push    r12
0x180090bc6  push    r13
0x180090bc8  push    r14
0x180090bca  push    r15
0x180090bcc  lea     rbp, [rsp-330h]
0x180090bd4  sub     rsp, 430h
0x180090bdb  mov     rax, cs:__security_cookie
0x180090be2  xor     rax, rsp
0x180090be5  mov     [rbp+360h+var_40], rax
0x180090bec  mov     bl, r8b
0x180090bef  mov     edi, edx
0x180090bf1  mov     r14, rcx
0x180090bf4  mov     esi, 1F0h
0x180090bf9  mov     r8d, esi; Size
0x180090bfc  lea     rcx, [rsp+460h+var_420]; void *
0x180090c01  xor     edx, edx; Val
0x180090c03  call    memset_0
0x180090c08  mov     r8d, esi; Size
0x180090c0b  lea     rcx, [rbp+360h+var_230]; void *
0x180090c12  xor     edx, edx; Val
0x180090c14  call    memset_0
0x180090c19  cmp     edi, 2
0x180090c1c  jb      loc_180090F44
0x180090c22  lea     r15, [rdi-1]
0x180090c26  xor     r12d, r12d
0x180090c29  lea     r15, [r15+r15*2]
0x180090c2d  mov     [rsp+460h+var_440], r12d
0x180090c32  lea     r15, [r14+r15*8]
0x180090c36  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180090c40  mov     rax, r15
0x180090c43  sub     rax, r14
0x180090c46  sar     rax, 3
0x180090c4a  imul    rax, rdx
0x180090c4e  inc     eax
0x180090c50  cmp     eax, 8
0x180090c53  ja      short loc_180090C8E
0x180090c55  mov     r8b, bl
0x180090c58  mov     rdx, r15
0x180090c5b  mov     rcx, r14
0x180090c5e  call    ??$ShortSort@UColumnEntry@@UCompareTuplesFunctor@CoreFragmentInspector@@U?$SwapFunctor@UColumnEntry@@@Algorithms@@@Algorithms@@CAXPEAUColumnEntry@@0UCompareTuplesFunctor@CoreFragmentInspector@@U?$SwapFunctor@UColumnEntry@@@0@@Z; Algorithms::ShortSort<ColumnEntry,CoreFragmentInspector::CompareTuplesFunctor,Algorithms::SwapFunctor<ColumnEntry>>(ColumnEntry *,ColumnEntry *,CoreFragmentInspector::CompareTuplesFunctor,Algorithms::SwapFunctor<ColumnEntry>)
0x180090c63  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180090c6d  sub     r12d, 1
0x180090c71  mov     [rsp+460h+var_440], r12d
0x180090c76  js      loc_180090F44
0x180090c7c  movsxd  rax, r12d
0x180090c7f  mov     r14, [rsp+rax*8+460h+var_420]
0x180090c84  mov     r15, [rbp+rax*8+360h+var_230]
0x180090c8c  jmp     short loc_180090C40
0x180090c8e  shr     rax, 1
0x180090c91  mov     rdx, r14
0x180090c94  lea     rax, [rax+rax*2]
0x180090c98  lea     r13, [r14+rax*8]
0x180090c9c  mov     r8, r13
0x180090c9f  lea     rsi, [r13+10h]
0x180090ca3  call    ??RCompareTuplesFunctor@CoreFragmentInspector@@QEAAJPEBUColumnEntry@@0@Z; CoreFragmentInspector::CompareTuplesFunctor::operator()(ColumnEntry const *,ColumnEntry const *)
0x180090ca8  test    eax, eax
0x180090caa  jle     short loc_180090CF9
0x180090cac  mov     eax, [r14+4]
0x180090cb0  lea     rcx, [rsp+460h+var_438]; this
0x180090cb5  mov     [rsp+460h+var_434], eax
0x180090cb9  mov     rax, [r14+8]
0x180090cbd  mov     [rsp+460h+var_430], rax
0x180090cc2  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x180090cc7  mov     edi, [r14+10h]
0x180090ccb  mov     rdx, r13
0x180090cce  mov     rcx, r14
0x180090cd1  mov     [rsp+460h+var_428], edi
0x180090cd5  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x180090cda  mov     eax, [rsi]
0x180090cdc  lea     rdx, [rsp+460h+var_438]
0x180090ce1  mov     rcx, r13
0x180090ce4  mov     [r14+10h], eax
0x180090ce8  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x180090ced  lea     rcx, [rsp+460h+var_438]; this
0x180090cf2  mov     [rsi], edi
0x180090cf4  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180090cf9  mov     r8, r15
0x180090cfc  mov     rdx, r14
0x180090cff  call    ??RCompareTuplesFunctor@CoreFragmentInspector@@QEAAJPEBUColumnEntry@@0@Z; CoreFragmentInspector::CompareTuplesFunctor::operator()(ColumnEntry const *,ColumnEntry const *)
0x180090d04  test    eax, eax
0x180090d06  jle     short loc_180090D59
0x180090d08  mov     eax, [r14+4]
0x180090d0c  lea     rcx, [rsp+460h+var_438]; this
0x180090d11  mov     [rsp+460h+var_434], eax
0x180090d15  mov     rax, [r14+8]
0x180090d19  mov     [rsp+460h+var_430], rax
0x180090d1e  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x180090d23  mov     edi, [r14+10h]
0x180090d27  mov     rdx, r15
0x180090d2a  mov     rcx, r14
0x180090d2d  mov     [rsp+460h+var_428], edi
0x180090d31  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x180090d36  mov     eax, [r15+10h]
0x180090d3a  lea     rdx, [rsp+460h+var_438]
0x180090d3f  mov     rcx, r15
0x180090d42  mov     [r14+10h], eax
0x180090d46  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x180090d4b  lea     rcx, [rsp+460h+var_438]; this
0x180090d50  mov     [r15+10h], edi
0x180090d54  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180090d59  mov     r8, r15
0x180090d5c  mov     rdx, r13
0x180090d5f  call    ??RCompareTuplesFunctor@CoreFragmentInspector@@QEAAJPEBUColumnEntry@@0@Z; CoreFragmentInspector::CompareTuplesFunctor::operator()(ColumnEntry const *,ColumnEntry const *)
0x180090d64  test    eax, eax
0x180090d66  jle     short loc_180090DB5
0x180090d68  mov     eax, [r13+4]
0x180090d6c  lea     rcx, [rsp+460h+var_438]; this
0x180090d71  mov     [rsp+460h+var_434], eax
0x180090d75  mov     rax, [r13+8]
0x180090d79  mov     [rsp+460h+var_430], rax
0x180090d7e  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x180090d83  mov     edi, [rsi]
0x180090d85  mov     rdx, r15
0x180090d88  mov     rcx, r13
0x180090d8b  mov     [rsp+460h+var_428], edi
0x180090d8f  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x180090d94  mov     eax, [r15+10h]
0x180090d98  lea     rdx, [rsp+460h+var_438]
0x180090d9d  mov     rcx, r15
0x180090da0  mov     [rsi], eax
0x180090da2  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x180090da7  lea     rcx, [rsp+460h+var_438]; this
0x180090dac  mov     [r15+10h], edi
0x180090db0  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180090db5  mov     rsi, r14
0x180090db8  mov     r12, r15
0x180090dbb  cmp     r13, rsi
0x180090dbe  jbe     short loc_180090DDA
0x180090dc0  add     rsi, 18h
0x180090dc4  cmp     rsi, r13
0x180090dc7  jnb     short loc_180090DDA
0x180090dc9  mov     r8, r13
0x180090dcc  mov     rdx, rsi
0x180090dcf  call    ??RCompareTuplesFunctor@CoreFragmentInspector@@QEAAJPEBUColumnEntry@@0@Z; CoreFragmentInspector::CompareTuplesFunctor::operator()(ColumnEntry const *,ColumnEntry const *)
0x180090dd4  test    eax, eax
0x180090dd6  jle     short loc_180090DC0
0x180090dd8  jmp     short loc_180090DF2
0x180090dda  add     rsi, 18h
0x180090dde  cmp     rsi, r15
0x180090de1  ja      short loc_180090DF2
0x180090de3  mov     r8, r13
0x180090de6  mov     rdx, rsi
0x180090de9  call    ??RCompareTuplesFunctor@CoreFragmentInspector@@QEAAJPEBUColumnEntry@@0@Z; CoreFragmentInspector::CompareTuplesFunctor::operator()(ColumnEntry const *,ColumnEntry const *)
0x180090dee  test    eax, eax
0x180090df0  jle     short loc_180090DDA
0x180090df2  mov     rdi, r12
0x180090df5  sub     r12, 18h
0x180090df9  cmp     r12, r13
0x180090dfc  jbe     short loc_180090E0D
0x180090dfe  mov     r8, r13
0x180090e01  mov     rdx, r12
0x180090e04  call    ??RCompareTuplesFunctor@CoreFragmentInspector@@QEAAJPEBUColumnEntry@@0@Z; CoreFragmentInspector::CompareTuplesFunctor::operator()(ColumnEntry const *,ColumnEntry const *)
0x180090e09  test    eax, eax
0x180090e0b  jg      short loc_180090DF2
0x180090e0d  cmp     r12, rsi
0x180090e10  jb      short loc_180090E74
0x180090e12  mov     eax, [rsi+4]
0x180090e15  lea     rcx, [rsp+460h+var_438]; this
0x180090e1a  mov     [rsp+460h+var_434], eax
0x180090e1e  mov     rax, [rsi+8]
0x180090e22  mov     [rsp+460h+var_430], rax
0x180090e27  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x180090e2c  mov     edi, [rsi+10h]
0x180090e2f  mov     rdx, r12
0x180090e32  mov     rcx, rsi
0x180090e35  mov     [rsp+460h+var_428], edi
0x180090e39  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x180090e3e  mov     eax, [r12+10h]
0x180090e43  lea     rdx, [rsp+460h+var_438]
0x180090e48  mov     rcx, r12
0x180090e4b  mov     [rsi+10h], eax
0x180090e4e  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x180090e53  lea     rcx, [rsp+460h+var_438]; this
0x180090e58  mov     [r12+10h], edi
0x180090e5d  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180090e62  cmp     r13, r12
0x180090e65  mov     rax, rsi
0x180090e68  cmovnz  rax, r13
0x180090e6c  mov     r13, rax
0x180090e6f  jmp     loc_180090DBB
0x180090e74  cmp     r13, rdi
0x180090e77  jnb     short loc_180090E93
0x180090e79  sub     rdi, 18h
0x180090e7d  cmp     rdi, r13
0x180090e80  jbe     short loc_180090E93
0x180090e82  mov     r8, r13
0x180090e85  mov     rdx, rdi
0x180090e88  call    ??RCompareTuplesFunctor@CoreFragmentInspector@@QEAAJPEBUColumnEntry@@0@Z; CoreFragmentInspector::CompareTuplesFunctor::operator()(ColumnEntry const *,ColumnEntry const *)
0x180090e8d  test    eax, eax
0x180090e8f  jz      short loc_180090E79
0x180090e91  jmp     short loc_180090EAB
0x180090e93  sub     rdi, 18h
0x180090e97  cmp     rdi, r14
0x180090e9a  jbe     short loc_180090EAB
0x180090e9c  mov     r8, r13
0x180090e9f  mov     rdx, rdi
0x180090ea2  call    ??RCompareTuplesFunctor@CoreFragmentInspector@@QEAAJPEBUColumnEntry@@0@Z; CoreFragmentInspector::CompareTuplesFunctor::operator()(ColumnEntry const *,ColumnEntry const *)
0x180090ea7  test    eax, eax
0x180090ea9  jz      short loc_180090E93
0x180090eab  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180090eb5  mov     rcx, r15
0x180090eb8  sub     rcx, rsi
0x180090ebb  mov     rax, rdi
0x180090ebe  sub     rax, r14
0x180090ec1  sar     rcx, 3
0x180090ec5  sar     rax, 3
0x180090ec9  imul    rcx, rdx
0x180090ecd  imul    rax, rdx
0x180090ed1  cmp     rax, rcx
0x180090ed4  jl      short loc_180090F0D
0x180090ed6  cmp     r14, rdi
0x180090ed9  jnb     short loc_180090EF7
0x180090edb  movsxd  r12, [rsp+460h+var_440]
0x180090ee0  mov     [rsp+r12*8+460h+var_420], r14
0x180090ee5  mov     [rbp+r12*8+360h+var_230], rdi
0x180090eed  inc     r12d
0x180090ef0  mov     [rsp+460h+var_440], r12d
0x180090ef5  jmp     short loc_180090EFC
0x180090ef7  mov     r12d, [rsp+460h+var_440]
0x180090efc  cmp     rsi, r15
0x180090eff  jnb     loc_180090C6D
0x180090f05  mov     r14, rsi
0x180090f08  jmp     loc_180090C40
0x180090f0d  cmp     rsi, r15
0x180090f10  jnb     short loc_180090F2E
0x180090f12  movsxd  r12, [rsp+460h+var_440]
0x180090f17  mov     [rsp+r12*8+460h+var_420], rsi
0x180090f1c  mov     [rbp+r12*8+360h+var_230], r15
0x180090f24  inc     r12d
0x180090f27  mov     [rsp+460h+var_440], r12d
0x180090f2c  jmp     short loc_180090F33
0x180090f2e  mov     r12d, [rsp+460h+var_440]
0x180090f33  cmp     r14, rdi
0x180090f36  jnb     loc_180090C6D
0x180090f3c  mov     r15, rdi
0x180090f3f  jmp     loc_180090C40
0x180090f44  mov     rcx, [rbp+360h+var_40]
0x180090f4b  xor     rcx, rsp; StackCookie
0x180090f4e  call    __security_check_cookie
0x180090f53  mov     rbx, [rsp+460h+arg_18]
0x180090f5b  add     rsp, 430h
0x180090f62  pop     r15
0x180090f64  pop     r14
0x180090f66  pop     r13
0x180090f68  pop     r12
0x180090f6a  pop     rdi
0x180090f6b  pop     rsi
0x180090f6c  pop     rbp
0x180090f6d  retn
```
