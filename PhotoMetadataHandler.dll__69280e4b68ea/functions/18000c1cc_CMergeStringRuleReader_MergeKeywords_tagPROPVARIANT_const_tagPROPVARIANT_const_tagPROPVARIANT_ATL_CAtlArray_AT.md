# CMergeStringRuleReader::MergeKeywords(tagPROPVARIANT const &,tagPROPVARIANT const &,tagPROPVARIANT *,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)

- ea: `0x18000c1cc`
- end: `0x18000c3e6`
- name: `?MergeKeywords@CMergeStringRuleReader@@CAJAEBUtagPROPVARIANT@@0PEAU2@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000b5e0`

## callees

- `0x18000b504`
- `0x18000b57c`
- `0x18000bbe8`
- `0x18000bddc`
- `0x18000c1cc`
- `0x18000c3ec`
- `0x18000c458`
- `0x1800101a8`
- `0x1800147f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c32d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c34a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c367`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c32d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c34a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c367`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMergeStringRuleReader::MergeKeywords(_WORD *a1, __int64 a2, PROPVARIANT *a3, __int64 a4)
{
  char v7; // r12
  int v8; // ebx
  _QWORD *i; // rsi
  int v10; // edi
  char *j; // rbx
  unsigned int v12; // edi
  void *v13; // rbx
  _QWORD *v15; // rax
  void *Block; // [rsp+20h] [rbp-60h] BYREF
  unsigned __int64 v17; // [rsp+28h] [rbp-58h]
  __int64 v18; // [rsp+30h] [rbp-50h]
  int v19; // [rsp+38h] [rbp-48h]
  void *v20; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int64 v21; // [rsp+48h] [rbp-38h]
  __int64 v22; // [rsp+50h] [rbp-30h]
  int v23; // [rsp+58h] [rbp-28h]
  void *v24; // [rsp+60h] [rbp-20h] BYREF
  __int64 v25; // [rsp+68h] [rbp-18h]
  __int64 v26; // [rsp+70h] [rbp-10h]
  int v27; // [rsp+78h] [rbp-8h]

  if ( *a1 != 4127 )
    return 0;
  v7 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  Block = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  ConvertPropVariantVectorToStringArray(a3, &v24);
  ConvertPropVariantVectorToStringArray(a1, &Block);
  v8 = 0;
  for ( i = Block; v8 < (int)v17; ++v8 )
  {
    if ( v8 >= v17 )
      ATL::AtlThrowImpl(-2147024809);
    if ( (unsigned int)FindStringInStringArray(&v24, &i[v8]) == -1 )
    {
      ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
        &v24,
        i[v8]);
      v7 = 1;
    }
  }
  if ( *(_WORD *)a2 == 4127 && *(_DWORD *)(a2 + 8) )
  {
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    ConvertPropVariantVectorToStringArray(a2, &v20);
    v10 = 0;
    for ( j = (char *)v20; v10 < (int)v21; ++v10 )
    {
      if ( v10 >= v21 )
        ATL::AtlThrowImpl(-2147024809);
      if ( (unsigned int)FindStringInStringArray(&Block, &j[8 * v10]) == -1 )
      {
        v15 = (_QWORD *)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                          &v20,
                          v10);
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
          a4,
          *v15);
      }
    }
    if ( j )
    {
      ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
        j,
        v21);
      free(j);
    }
  }
  if ( !v7 )
  {
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(&Block);
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(&v24);
    return 0;
  }
  v12 = ConvertStringArrayToPropVariantVector((__int64)&v24, a3);
  if ( i )
  {
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
      i,
      v17);
    free(i);
  }
  v13 = v24;
  if ( v24 )
  {
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
      v24,
      v25);
    free(v13);
  }
  return v12;
}

```

## disassembly

```asm
0x18000c1cc  mov     [rsp-28h+arg_0], rbx
0x18000c1d1  mov     [rsp-28h+arg_8], rsi
0x18000c1d6  mov     [rsp-28h+arg_18], r9
0x18000c1db  push    rbp
0x18000c1dc  push    rdi
0x18000c1dd  push    r12
0x18000c1df  push    r13
0x18000c1e1  push    r14
0x18000c1e3  mov     rbp, rsp
0x18000c1e6  sub     rsp, 80h
0x18000c1ed  mov     r13, r8
0x18000c1f0  mov     rdi, rdx
0x18000c1f3  mov     rbx, rcx
0x18000c1f6  mov     eax, 101Fh
0x18000c1fb  cmp     [rcx], ax
0x18000c1fe  jnz     loc_18000C3DF
0x18000c204  xor     r14d, r14d
0x18000c207  mov     r12b, r14b
0x18000c20a  mov     [rbp+var_20], r14
0x18000c20e  mov     [rbp+var_18], r14
0x18000c212  mov     [rbp+var_10], r14
0x18000c216  mov     [rbp+var_8], r14d
0x18000c21a  mov     [rbp+Block], r14
0x18000c21e  mov     [rbp+var_58], r14
0x18000c222  mov     [rbp+var_50], r14
0x18000c226  mov     [rbp+var_48], r14d
0x18000c22a  lea     rdx, [rbp+var_20]
0x18000c22e  mov     rcx, r8
0x18000c231  call    ?ConvertPropVariantVectorToStringArray@@YAXAEBUtagPROPVARIANT@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; ConvertPropVariantVectorToStringArray(tagPROPVARIANT const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x18000c236  lea     rdx, [rbp+Block]
0x18000c23a  mov     rcx, rbx
0x18000c23d  call    ?ConvertPropVariantVectorToStringArray@@YAXAEBUtagPROPVARIANT@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; ConvertPropVariantVectorToStringArray(tagPROPVARIANT const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x18000c242  mov     ebx, r14d
0x18000c245  mov     rsi, [rbp+Block]
0x18000c249  cmp     dword ptr [rbp+var_58], r14d
0x18000c24d  jg      loc_18000C30A
0x18000c253  mov     eax, 101Fh
0x18000c258  cmp     [rdi], ax
0x18000c25b  jnz     short loc_18000C2C6
0x18000c25d  cmp     [rdi+8], r14d
0x18000c261  jbe     short loc_18000C2C6
0x18000c263  mov     [rbp+var_40], r14
0x18000c267  mov     [rbp+var_38], r14
0x18000c26b  mov     [rbp+var_30], r14
0x18000c26f  mov     [rbp+var_28], r14d
0x18000c273  lea     rdx, [rbp+var_40]
0x18000c277  mov     rcx, rdi
0x18000c27a  call    ?ConvertPropVariantVectorToStringArray@@YAXAEBUtagPROPVARIANT@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; ConvertPropVariantVectorToStringArray(tagPROPVARIANT const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x18000c27f  mov     edi, r14d
0x18000c282  mov     rbx, [rbp+var_40]
0x18000c286  cmp     dword ptr [rbp+var_38], r14d
0x18000c28a  jle     short loc_18000C2BD
0x18000c28c  movsxd  r14, edi
0x18000c28f  cmp     r14, [rbp+var_38]
0x18000c293  jb      short loc_18000C2A0
0x18000c295  mov     ecx, 80070057h; int
0x18000c29a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c2a0  lea     rdx, [rbx+r14*8]
0x18000c2a4  lea     rcx, [rbp+Block]
0x18000c2a8  call    ?FindStringInStringArray@@YAHAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; FindStringInStringArray(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000c2ad  cmp     eax, 0FFFFFFFFh
0x18000c2b0  jz      loc_18000C3AF
0x18000c2b6  inc     edi
0x18000c2b8  cmp     edi, dword ptr [rbp+var_38]
0x18000c2bb  jl      short loc_18000C28C
0x18000c2bd  test    rbx, rbx
0x18000c2c0  jnz     loc_18000C358
0x18000c2c6  test    r12b, r12b
0x18000c2c9  jz      loc_18000C3CC
0x18000c2cf  mov     rdx, r13
0x18000c2d2  lea     rcx, [rbp+var_20]
0x18000c2d6  call    ?ConvertStringArrayToPropVariantVector@@YAJAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAUtagPROPVARIANT@@@Z; ConvertStringArrayToPropVariantVector(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,tagPROPVARIANT *)
0x18000c2db  mov     edi, eax
0x18000c2dd  test    rsi, rsi
0x18000c2e0  jnz     short loc_18000C31E
0x18000c2e2  mov     rbx, [rbp+var_20]
0x18000c2e6  test    rbx, rbx
0x18000c2e9  jnz     short loc_18000C33B
0x18000c2eb  mov     eax, edi
0x18000c2ed  lea     r11, [rsp+80h+var_s0]
0x18000c2f5  mov     rbx, [r11+30h]
0x18000c2f9  mov     rsi, [r11+38h]
0x18000c2fd  mov     rsp, r11
0x18000c300  pop     r14
0x18000c302  pop     r13
0x18000c304  pop     r12
0x18000c306  pop     rdi
0x18000c307  pop     rbp
0x18000c308  retn
0x18000c30a  movsxd  rax, ebx
0x18000c30d  cmp     rax, [rbp+var_58]
0x18000c311  jb      short loc_18000C378
0x18000c313  mov     ecx, 80070057h; int
0x18000c318  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c31e  mov     rdx, [rbp+var_58]
0x18000c322  mov     rcx, rsi
0x18000c325  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000c32a  mov     rcx, rsi; Block
0x18000c32d  call    cs:__imp_free
0x18000c334  nop     dword ptr [rax+rax+00h]
0x18000c339  jmp     short loc_18000C2E2
0x18000c33b  mov     rdx, [rbp+var_18]
0x18000c33f  mov     rcx, rbx
0x18000c342  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000c347  mov     rcx, rbx; Block
0x18000c34a  call    cs:__imp_free
0x18000c351  nop     dword ptr [rax+rax+00h]
0x18000c356  jmp     short loc_18000C2EB
0x18000c358  mov     rdx, [rbp+var_38]
0x18000c35c  mov     rcx, rbx
0x18000c35f  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000c364  mov     rcx, rbx; Block
0x18000c367  call    cs:__imp_free
0x18000c36e  nop     dword ptr [rax+rax+00h]
0x18000c373  jmp     loc_18000C2C6
0x18000c378  lea     r14, [rsi+rax*8]
0x18000c37c  mov     rdx, r14
0x18000c37f  lea     rcx, [rbp+var_20]
0x18000c383  call    ?FindStringInStringArray@@YAHAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; FindStringInStringArray(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000c388  cmp     eax, 0FFFFFFFFh
0x18000c38b  jnz     short loc_18000C39C
0x18000c38d  mov     rdx, [r14]
0x18000c390  lea     rcx, [rbp+var_20]
0x18000c394  call    ?Add@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_KPEBG@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ushort const *)
0x18000c399  mov     r12b, 1
0x18000c39c  inc     ebx
0x18000c39e  cmp     ebx, dword ptr [rbp+var_58]
0x18000c3a1  jl      loc_18000C30A
0x18000c3a7  xor     r14d, r14d
0x18000c3aa  jmp     loc_18000C253
0x18000c3af  mov     rdx, r14
0x18000c3b2  lea     rcx, [rbp+var_40]
0x18000c3b6  call    ??A?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](unsigned __int64)
0x18000c3bb  mov     rdx, [rax]
0x18000c3be  mov     rcx, [rbp+arg_18]
0x18000c3c2  call    ?Add@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_KPEBG@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ushort const *)
0x18000c3c7  jmp     loc_18000C2B6
0x18000c3cc  lea     rcx, [rbp+Block]
0x18000c3d0  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18000c3d5  nop
0x18000c3d6  lea     rcx, [rbp+var_20]
0x18000c3da  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18000c3df  xor     eax, eax
0x18000c3e1  jmp     loc_18000C2ED
```
