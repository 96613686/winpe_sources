# CMergeStringRuleReader::ReadKey(tagPROPVARIANT *)

- ea: `0x18000b0a0`
- end: `0x18000b3b3`
- name: `?ReadKey@CMergeStringRuleReader@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `787`
- prototype: `__int64 __fastcall(CMergeStringRuleReader *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000b0a0`
- `0x18000b3bc`
- `0x18000b684`
- `0x18000b864`
- `0x18000bac0`
- `0x18000bc38`
- `0x18000beb0`
- `0x18000bef4`
- `0x180013e34`
- `0x180020564`
- `0x180028010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b1a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b2ff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b354`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b1a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b2ff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b354`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b338`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b338`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b22c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b22c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMergeStringRuleReader::ReadKey(CMergeStringRuleReader *this, struct tagPROPVARIANT *a2)
{
  VARTYPE vt; // ax
  char *v4; // r14
  unsigned __int64 v5; // r15
  unsigned int v6; // ebx
  char *v7; // rbx
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // r12
  LONG lVal; // esi
  LONG i; // r13d
  char v12; // r12
  int v13; // r13d
  int StringInStringArray; // eax
  HRESULT v15; // esi
  void *v16; // rbx
  unsigned __int64 v18; // rax
  __int64 v19; // [rsp+20h] [rbp-49h]
  PROPVARIANT pvar; // [rsp+28h] [rbp-41h] BYREF
  void *Block; // [rsp+40h] [rbp-29h] BYREF
  __int64 v22; // [rsp+48h] [rbp-21h]
  unsigned __int64 v23; // [rsp+50h] [rbp-19h]
  int v24; // [rsp+58h] [rbp-11h]
  char *v25; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int64 v26; // [rsp+68h] [rbp-1h]
  __int64 v27; // [rsp+70h] [rbp+7h]
  int v28; // [rsp+78h] [rbp+Fh]
  void (__fastcall ***v29)(_QWORD, __int64); // [rsp+D0h] [rbp+67h] BYREF
  PROPVARIANT *pvarDest; // [rsp+D8h] [rbp+6Fh]
  __int64 v31; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int64 v32; // [rsp+E8h] [rbp+7Fh]

  pvarDest = a2;
  v29 = 0;
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  memset(&pvar, 0, sizeof(pvar));
  vt = 4127;
  pvar.vt = 4127;
  v4 = 0;
  v25 = 0;
  v5 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v6 = 0;
  if ( !*((_DWORD *)this + 6) )
  {
LABEL_7:
    v7 = 0;
    Block = 0;
    v8 = 0;
    v22 = 0;
    v9 = 0;
    v23 = 0;
    v24 = 0;
    if ( vt == 4127 )
    {
      lVal = pvar.lVal;
      for ( i = 0; i < lVal; ++i )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v31,
          *(_QWORD *)&pvar.bstrblobVal.pData[8 * i]);
        v19 = v31;
        v18 = v8;
        v32 = v8;
        if ( v8 >= v9 )
        {
          if ( !(unsigned __int8)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GrowBuffer(
                                   &Block,
                                   v8 + 1) )
            ATL::AtlThrowImpl(-2147024882);
          v9 = v23;
          v8 = v22;
          v7 = (char *)Block;
          v18 = v32;
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v7[8 * v18],
          v19);
        v22 = ++v8;
        ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
      }
    }
    v12 = 0;
    v13 = 0;
    if ( (int)v5 > 0 )
    {
      do
      {
        if ( v13 >= v5 )
          ATL::AtlThrowImpl(-2147024809);
        StringInStringArray = FindStringInStringArray(&Block, &v4[8 * v13]);
        if ( StringInStringArray != -1 )
        {
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
            &Block,
            StringInStringArray);
          v12 = 1;
        }
        ++v13;
      }
      while ( v13 < (int)v5 );
      if ( v12 )
      {
        v15 = ConvertStringArrayToPropVariantVector(&Block, &pvar);
        v16 = Block;
        if ( Block )
        {
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
            Block,
            v22);
          free(v16);
        }
        if ( v15 < 0 )
          goto LABEL_22;
LABEL_20:
        if ( pvar.lVal )
          v15 = PropVariantCopy(pvarDest, &pvar);
        else
          v15 = -2003292352;
        goto LABEL_22;
      }
      v8 = v22;
      v7 = (char *)Block;
    }
    if ( v7 )
    {
      ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
        v7,
        v8);
      free(v7);
    }
    goto LABEL_20;
  }
  while ( 1 )
  {
    if ( (*(int (__fastcall **)(CMergeStringRuleReader *, unsigned __int64, void (__fastcall ****)(_QWORD, __int64)))(*(_QWORD *)this + 48LL))(
           this,
           *((_QWORD *)this + 2) + ((unsigned __int64)v6 << 6),
           &v29) >= 0 )
    {
      v15 = CMergeStringRuleReader::MergeKeywords(v29 + 1, v29 + 4, &pvar, &v25);
      if ( v15 < 0 )
        break;
    }
    if ( v29 )
      (**v29)(v29, 1);
    v29 = 0;
    if ( ++v6 >= *((_DWORD *)this + 6) )
    {
      vt = pvar.vt;
      v5 = v26;
      v4 = v25;
      goto LABEL_7;
    }
  }
  v5 = v26;
  v4 = v25;
LABEL_22:
  if ( v29 )
    (**v29)(v29, 1);
  if ( v4 )
  {
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
      v4,
      v5);
    free(v4);
  }
  PropVariantClear(&pvar);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000b0a0  mov     [rsp-8+pvarDest], rdx
0x18000b0a5  push    rbp
0x18000b0a6  push    rbx
0x18000b0a7  push    rsi
0x18000b0a8  push    rdi
0x18000b0a9  push    r12
0x18000b0ab  push    r13
0x18000b0ad  push    r14
0x18000b0af  push    r15
0x18000b0b1  lea     rbp, [rsp-1Fh]
0x18000b0b6  sub     rsp, 88h
0x18000b0bd  mov     rdi, rcx
0x18000b0c0  xor     esi, esi
0x18000b0c2  mov     [rbp+57h+arg_0], rsi
0x18000b0c6  xorps   xmm0, xmm0
0x18000b0c9  xor     ecx, ecx
0x18000b0cb  movups  xmmword ptr [rdx], xmm0
0x18000b0ce  mov     [rdx+10h], rcx
0x18000b0d2  xor     eax, eax
0x18000b0d4  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000b0d8  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18000b0dc  mov     r13d, 101Fh
0x18000b0e2  movzx   eax, r13w
0x18000b0e6  mov     word ptr [rbp+57h+pvar], ax
0x18000b0ea  mov     r14d, esi
0x18000b0ed  mov     [rbp+57h+var_60], rsi
0x18000b0f1  mov     r15d, esi
0x18000b0f4  mov     [rbp+57h+var_58], rsi
0x18000b0f8  mov     [rbp+57h+var_50], rsi
0x18000b0fc  mov     [rbp+57h+var_48], esi
0x18000b0ff  mov     ebx, esi
0x18000b101  cmp     [rdi+18h], ebx
0x18000b104  jbe     short loc_18000B159
0x18000b106  nop     word ptr [rax+rax+00000000h]
0x18000b110  mov     rax, [rdi]
0x18000b113  mov     edx, ebx
0x18000b115  shl     rdx, 6
0x18000b119  add     rdx, [rdi+10h]
0x18000b11d  lea     r8, [rbp+57h+arg_0]
0x18000b121  mov     rcx, rdi
0x18000b124  mov     rax, [rax+30h]
0x18000b128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b12d  test    eax, eax
0x18000b12f  jns     loc_18000B2AC
0x18000b135  mov     rcx, [rbp+57h+arg_0]
0x18000b139  test    rcx, rcx
0x18000b13c  jnz     loc_18000B2DC
0x18000b142  mov     [rbp+57h+arg_0], rsi
0x18000b146  inc     ebx
0x18000b148  cmp     ebx, [rdi+18h]
0x18000b14b  jb      short loc_18000B110
0x18000b14d  movzx   eax, word ptr [rbp+57h+pvar]
0x18000b151  mov     r15, [rbp+57h+var_58]
0x18000b155  mov     r14, [rbp+57h+var_60]
0x18000b159  mov     rbx, rsi
0x18000b15c  mov     [rbp+57h+Block], rbx
0x18000b160  mov     rdi, rsi
0x18000b163  mov     [rbp+57h+var_78], rsi
0x18000b167  mov     r12, rsi
0x18000b16a  mov     [rbp+57h+var_70], rsi
0x18000b16e  mov     [rbp+57h+var_68], esi
0x18000b171  cmp     ax, r13w
0x18000b175  jnz     short loc_18000B185
0x18000b177  mov     esi, dword ptr [rbp+57h+pvar+8]
0x18000b17a  xor     r13d, r13d
0x18000b17d  test    esi, esi
0x18000b17f  jg      loc_18000B250
0x18000b185  xor     r12b, r12b
0x18000b188  xor     r13d, r13d
0x18000b18b  test    r15d, r15d
0x18000b18e  jg      short loc_18000B1B0
0x18000b190  test    rbx, rbx
0x18000b193  jz      short loc_18000B203
0x18000b195  mov     rdx, rdi
0x18000b198  mov     rcx, rbx
0x18000b19b  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000b1a0  mov     rcx, rbx; Block
0x18000b1a3  call    cs:__imp_free
0x18000b1a9  jmp     short loc_18000B203
0x18000b1b0  movsxd  rax, r13d
0x18000b1b3  cmp     rax, r15
0x18000b1b6  jnb     loc_18000B392
0x18000b1bc  lea     rdx, [r14+rax*8]
0x18000b1c0  lea     rcx, [rbp+57h+Block]
0x18000b1c4  call    ?FindStringInStringArray@@YAHAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; FindStringInStringArray(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000b1c9  cmp     eax, 0FFFFFFFFh
0x18000b1cc  jnz     loc_18000B371
0x18000b1d2  inc     r13d
0x18000b1d5  cmp     r13d, r15d
0x18000b1d8  jl      short loc_18000B1B0
0x18000b1da  test    r12b, r12b
0x18000b1dd  jz      loc_18000B385
0x18000b1e3  lea     rdx, [rbp+57h+pvar]
0x18000b1e7  lea     rcx, [rbp+57h+Block]
0x18000b1eb  call    ?ConvertStringArrayToPropVariantVector@@YAJAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAUtagPROPVARIANT@@@Z; ConvertStringArrayToPropVariantVector(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,tagPROPVARIANT *)
0x18000b1f0  mov     esi, eax
0x18000b1f2  mov     rbx, [rbp+57h+Block]
0x18000b1f6  test    rbx, rbx
0x18000b1f9  jnz     loc_18000B345
0x18000b1ff  test    esi, esi
0x18000b201  js      short loc_18000B212
0x18000b203  cmp     dword ptr [rbp+57h+pvar+8], 0
0x18000b207  ja      loc_18000B330
0x18000b20d  mov     esi, 88982F40h
0x18000b212  mov     rcx, [rbp+57h+arg_0]
0x18000b216  test    rcx, rcx
0x18000b219  jnz     loc_18000B39D
0x18000b21f  test    r14, r14
0x18000b222  jnz     loc_18000B2F1
0x18000b228  lea     rcx, [rbp+57h+pvar]; pvar
0x18000b22c  call    cs:__imp_PropVariantClear
0x18000b232  mov     eax, esi
0x18000b234  add     rsp, 88h
0x18000b23b  pop     r15
0x18000b23d  pop     r14
0x18000b23f  pop     r13
0x18000b241  pop     r12
0x18000b243  pop     rdi
0x18000b244  pop     rsi
0x18000b245  pop     rbx
0x18000b246  pop     rbp
0x18000b247  retn
0x18000b250  movsxd  rax, r13d
0x18000b253  mov     rdx, qword ptr [rbp+57h+pvar+10h]
0x18000b257  mov     rdx, [rdx+rax*8]
0x18000b25b  lea     rcx, [rbp+57h+arg_10]
0x18000b25f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000b264  nop
0x18000b265  mov     rax, [rbp+57h+arg_10]
0x18000b269  mov     [rbp+57h+var_A0], rax
0x18000b26d  mov     rax, rdi
0x18000b270  mov     [rbp+57h+arg_18], rax
0x18000b274  cmp     rdi, r12
0x18000b277  jnb     loc_18000B30A
0x18000b27d  lea     rcx, [rbx+rax*8]
0x18000b281  mov     rdx, [rbp+57h+var_A0]
0x18000b285  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000b28a  inc     rdi
0x18000b28d  mov     [rbp+57h+var_78], rdi
0x18000b291  mov     rcx, [rbp+57h+arg_10]
0x18000b295  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000b299  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000b29e  inc     r13d
0x18000b2a1  cmp     r13d, esi
0x18000b2a4  jge     loc_18000B185
0x18000b2aa  jmp     short loc_18000B250
0x18000b2ac  mov     rcx, [rbp+57h+arg_0]
0x18000b2b0  lea     rdx, [rcx+20h]
0x18000b2b4  add     rcx, 8
0x18000b2b8  lea     r9, [rbp+57h+var_60]
0x18000b2bc  lea     r8, [rbp+57h+pvar]
0x18000b2c0  call    ?MergeKeywords@CMergeStringRuleReader@@CAJAEBUtagPROPVARIANT@@0PEAU2@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; CMergeStringRuleReader::MergeKeywords(tagPROPVARIANT const &,tagPROPVARIANT const &,tagPROPVARIANT *,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x18000b2c5  mov     esi, eax
0x18000b2c7  test    eax, eax
0x18000b2c9  jns     loc_18000B35F
0x18000b2cf  mov     r15, [rbp+57h+var_58]
0x18000b2d3  mov     r14, [rbp+57h+var_60]
0x18000b2d7  jmp     loc_18000B212
0x18000b2dc  mov     rax, [rcx]
0x18000b2df  mov     edx, 1
0x18000b2e4  mov     rax, [rax]
0x18000b2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2ec  jmp     loc_18000B142
0x18000b2f1  mov     rdx, r15
0x18000b2f4  mov     rcx, r14
0x18000b2f7  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000b2fc  mov     rcx, r14; Block
0x18000b2ff  call    cs:__imp_free
0x18000b305  jmp     loc_18000B228
0x18000b30a  lea     rdx, [rdi+1]
0x18000b30e  lea     rcx, [rbp+57h+Block]
0x18000b312  call    ?GrowBuffer@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GrowBuffer(unsigned __int64)
0x18000b317  test    al, al
0x18000b319  jz      short loc_18000B366
0x18000b31b  mov     r12, [rbp+57h+var_70]
0x18000b31f  mov     rdi, [rbp+57h+var_78]
0x18000b323  mov     rbx, [rbp+57h+Block]
0x18000b327  mov     rax, [rbp+57h+arg_18]
0x18000b32b  jmp     loc_18000B27D
0x18000b330  lea     rdx, [rbp+57h+pvar]; pvarSrc
0x18000b334  mov     rcx, [rbp+57h+pvarDest]; pvarDest
0x18000b338  call    cs:__imp_PropVariantCopy
0x18000b33e  mov     esi, eax
0x18000b340  jmp     loc_18000B212
0x18000b345  mov     rdx, [rbp+57h+var_78]
0x18000b349  mov     rcx, rbx
0x18000b34c  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000b351  mov     rcx, rbx; Block
0x18000b354  call    cs:__imp_free
0x18000b35a  jmp     loc_18000B1FF
0x18000b35f  xor     esi, esi
0x18000b361  jmp     loc_18000B135
0x18000b366  mov     ecx, 8007000Eh; int
0x18000b36b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b371  movsxd  rdx, eax
0x18000b374  lea     rcx, [rbp+57h+Block]
0x18000b378  call    ?RemoveAt@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAX_K0@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(unsigned __int64,unsigned __int64)
0x18000b37d  mov     r12b, 1
0x18000b380  jmp     loc_18000B1D2
0x18000b385  mov     rdi, [rbp+57h+var_78]
0x18000b389  mov     rbx, [rbp+57h+Block]
0x18000b38d  jmp     loc_18000B190
0x18000b392  mov     ecx, 80070057h; int
0x18000b397  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b39d  mov     rax, [rcx]
0x18000b3a0  mov     edx, 1
0x18000b3a5  mov     rax, [rax]
0x18000b3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ad  jmp     loc_18000B21F
```
