# CMergeStringRuleReader::MergeKeywords(tagPROPVARIANT const &,tagPROPVARIANT const &,tagPROPVARIANT *,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)

- ea: `0x18000bc38`
- end: `0x18000be3f`
- name: `?MergeKeywords@CMergeStringRuleReader@@CAJAEBUtagPROPVARIANT@@0PEAU2@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z`
- size: `519`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000b0a0`

## callees

- `0x18000afc4`
- `0x18000b034`
- `0x18000b684`
- `0x18000b864`
- `0x18000bc38`
- `0x18000be48`
- `0x18000beb0`
- `0x18000fa20`
- `0x180013e34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bd98`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bdaf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bdc6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bd98`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bdaf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bdc6`

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
  ConvertPropVariantVectorToStringArray((__int64)a3, (__int64)&v24);
  ConvertPropVariantVectorToStringArray((__int64)a1, (__int64)&Block);
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
    ConvertPropVariantVectorToStringArray(a2, (__int64)&v20);
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
0x18000bc38  mov     [rsp-28h+arg_0], rbx
0x18000bc3d  mov     [rsp-28h+arg_8], rsi
0x18000bc42  mov     [rsp-28h+arg_18], r9
0x18000bc47  push    rbp
0x18000bc48  push    rdi
0x18000bc49  push    r12
0x18000bc4b  push    r13
0x18000bc4d  push    r14
0x18000bc4f  mov     rbp, rsp
0x18000bc52  sub     rsp, 80h
0x18000bc59  mov     r13, r8
0x18000bc5c  mov     rdi, rdx
0x18000bc5f  mov     rbx, rcx
0x18000bc62  mov     eax, 101Fh
0x18000bc67  cmp     [rcx], ax
0x18000bc6a  jnz     loc_18000BE38
0x18000bc70  xor     r14d, r14d
0x18000bc73  mov     r12b, r14b
0x18000bc76  mov     [rbp+var_20], r14
0x18000bc7a  mov     [rbp+var_18], r14
0x18000bc7e  mov     [rbp+var_10], r14
0x18000bc82  mov     [rbp+var_8], r14d
0x18000bc86  mov     [rbp+Block], r14
0x18000bc8a  mov     [rbp+var_58], r14
0x18000bc8e  mov     [rbp+var_50], r14
0x18000bc92  mov     [rbp+var_48], r14d
0x18000bc96  lea     rdx, [rbp+var_20]
0x18000bc9a  mov     rcx, r8
0x18000bc9d  call    ?ConvertPropVariantVectorToStringArray@@YAXAEBUtagPROPVARIANT@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; ConvertPropVariantVectorToStringArray(tagPROPVARIANT const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x18000bca2  lea     rdx, [rbp+Block]
0x18000bca6  mov     rcx, rbx
0x18000bca9  call    ?ConvertPropVariantVectorToStringArray@@YAXAEBUtagPROPVARIANT@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; ConvertPropVariantVectorToStringArray(tagPROPVARIANT const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x18000bcae  mov     ebx, r14d
0x18000bcb1  mov     rsi, [rbp+Block]
0x18000bcb5  cmp     dword ptr [rbp+var_58], r14d
0x18000bcb9  jg      loc_18000BD75
0x18000bcbf  mov     eax, 101Fh
0x18000bcc4  cmp     [rdi], ax
0x18000bcc7  jnz     short loc_18000BD32
0x18000bcc9  cmp     [rdi+8], r14d
0x18000bccd  jbe     short loc_18000BD32
0x18000bccf  mov     [rbp+var_40], r14
0x18000bcd3  mov     [rbp+var_38], r14
0x18000bcd7  mov     [rbp+var_30], r14
0x18000bcdb  mov     [rbp+var_28], r14d
0x18000bcdf  lea     rdx, [rbp+var_40]
0x18000bce3  mov     rcx, rdi
0x18000bce6  call    ?ConvertPropVariantVectorToStringArray@@YAXAEBUtagPROPVARIANT@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; ConvertPropVariantVectorToStringArray(tagPROPVARIANT const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x18000bceb  mov     edi, r14d
0x18000bcee  mov     rbx, [rbp+var_40]
0x18000bcf2  cmp     dword ptr [rbp+var_38], r14d
0x18000bcf6  jle     short loc_18000BD29
0x18000bcf8  movsxd  r14, edi
0x18000bcfb  cmp     r14, [rbp+var_38]
0x18000bcff  jb      short loc_18000BD0C
0x18000bd01  mov     ecx, 80070057h; int
0x18000bd06  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000bd0c  lea     rdx, [rbx+r14*8]
0x18000bd10  lea     rcx, [rbp+Block]
0x18000bd14  call    ?FindStringInStringArray@@YAHAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; FindStringInStringArray(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000bd19  cmp     eax, 0FFFFFFFFh
0x18000bd1c  jz      loc_18000BE08
0x18000bd22  inc     edi
0x18000bd24  cmp     edi, dword ptr [rbp+var_38]
0x18000bd27  jl      short loc_18000BCF8
0x18000bd29  test    rbx, rbx
0x18000bd2c  jnz     loc_18000BDB7
0x18000bd32  test    r12b, r12b
0x18000bd35  jz      loc_18000BE25
0x18000bd3b  mov     rdx, r13
0x18000bd3e  lea     rcx, [rbp+var_20]
0x18000bd42  call    ?ConvertStringArrayToPropVariantVector@@YAJAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAUtagPROPVARIANT@@@Z; ConvertStringArrayToPropVariantVector(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,tagPROPVARIANT *)
0x18000bd47  mov     edi, eax
0x18000bd49  test    rsi, rsi
0x18000bd4c  jnz     short loc_18000BD89
0x18000bd4e  mov     rbx, [rbp+var_20]
0x18000bd52  test    rbx, rbx
0x18000bd55  jnz     short loc_18000BDA0
0x18000bd57  mov     eax, edi
0x18000bd59  lea     r11, [rsp+80h+var_s0]
0x18000bd61  mov     rbx, [r11+30h]
0x18000bd65  mov     rsi, [r11+38h]
0x18000bd69  mov     rsp, r11
0x18000bd6c  pop     r14
0x18000bd6e  pop     r13
0x18000bd70  pop     r12
0x18000bd72  pop     rdi
0x18000bd73  pop     rbp
0x18000bd74  retn
0x18000bd75  movsxd  rax, ebx
0x18000bd78  cmp     rax, [rbp+var_58]
0x18000bd7c  jb      short loc_18000BDD1
0x18000bd7e  mov     ecx, 80070057h; int
0x18000bd83  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000bd89  mov     rdx, [rbp+var_58]
0x18000bd8d  mov     rcx, rsi
0x18000bd90  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000bd95  mov     rcx, rsi; Block
0x18000bd98  call    cs:__imp_free
0x18000bd9e  jmp     short loc_18000BD4E
0x18000bda0  mov     rdx, [rbp+var_18]
0x18000bda4  mov     rcx, rbx
0x18000bda7  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000bdac  mov     rcx, rbx; Block
0x18000bdaf  call    cs:__imp_free
0x18000bdb5  jmp     short loc_18000BD57
0x18000bdb7  mov     rdx, [rbp+var_38]
0x18000bdbb  mov     rcx, rbx
0x18000bdbe  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000bdc3  mov     rcx, rbx; Block
0x18000bdc6  call    cs:__imp_free
0x18000bdcc  jmp     loc_18000BD32
0x18000bdd1  lea     r14, [rsi+rax*8]
0x18000bdd5  mov     rdx, r14
0x18000bdd8  lea     rcx, [rbp+var_20]
0x18000bddc  call    ?FindStringInStringArray@@YAHAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; FindStringInStringArray(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000bde1  cmp     eax, 0FFFFFFFFh
0x18000bde4  jnz     short loc_18000BDF5
0x18000bde6  mov     rdx, [r14]
0x18000bde9  lea     rcx, [rbp+var_20]
0x18000bded  call    ?Add@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_KPEBG@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ushort const *)
0x18000bdf2  mov     r12b, 1
0x18000bdf5  inc     ebx
0x18000bdf7  cmp     ebx, dword ptr [rbp+var_58]
0x18000bdfa  jl      loc_18000BD75
0x18000be00  xor     r14d, r14d
0x18000be03  jmp     loc_18000BCBF
0x18000be08  mov     rdx, r14
0x18000be0b  lea     rcx, [rbp+var_40]
0x18000be0f  call    ??A?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](unsigned __int64)
0x18000be14  mov     rdx, [rax]
0x18000be17  mov     rcx, [rbp+arg_18]
0x18000be1b  call    ?Add@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_KPEBG@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ushort const *)
0x18000be20  jmp     loc_18000BD22
0x18000be25  lea     rcx, [rbp+Block]
0x18000be29  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18000be2e  nop
0x18000be2f  lea     rcx, [rbp+var_20]
0x18000be33  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18000be38  xor     eax, eax
0x18000be3a  jmp     loc_18000BD59
```
