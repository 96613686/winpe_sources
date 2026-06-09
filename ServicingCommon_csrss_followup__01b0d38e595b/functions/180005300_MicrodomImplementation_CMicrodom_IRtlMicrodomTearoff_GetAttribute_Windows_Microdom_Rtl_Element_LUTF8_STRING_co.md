# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetAttribute(Windows::Microdom::Rtl::Element,_LUTF8_STRING const *,_LUTF8_STRING const * *)

- ea: `0x180005300`
- end: `0x1800057a1`
- name: `?GetAttribute@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJUElement@Rtl@Microdom@Windows@@PEBU_LUTF8_STRING@@PEAPEBU7@@Z`
- size: `1185`
- prototype: `int __high(struct Windows::Microdom::Rtl::Element, const struct _LUTF8_STRING *, const struct _LUTF8_STRING **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180005300`
- `0x1800057b0`
- `0x180005a90`
- `0x180005f80`
- `0x180006a40`
- `0x180009820`
- `0x180018aa8`
- `0x18001f1d8`
- `0x1800253f4`
- `0x180026e18`
- `0x18002d2b0`

## string_xrefs

- `0x180005382`: `MicrodomImplementation::CDomLayoutCache::FindObject`
- `0x180005773`: `MicrodomImplementation::CDomLayoutCache::FindObject`
- `0x18000538d`: `onecore\base\xml\udom_microdom.cpp`
- `0x180005617`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800056b3`: `onecore\base\xml\udom_microdom.cpp`
- `0x18000575c`: `onecore\base\xml\udom_microdom.cpp`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetAttribute(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        const struct _LUTF8_STRING **a4)
{
  __int64 v6; // r12
  _QWORD *v7; // r13
  unsigned int v8; // r14d
  MicrodomImplementation::CDomLayoutCache *v9; // r15
  __int64 v10; // rax
  unsigned __int64 v11; // rbx
  __int64 v12; // r13
  void *v13; // rcx
  unsigned __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // xmm1_8
  __int64 v17; // rdx
  MicrodomImplementation::CMicrodom *v18; // r10
  __int64 v19; // rcx
  char v20; // al
  char *v21; // r13
  __int64 v22; // r12
  __int64 v23; // r8
  _BYTE *v24; // r9
  _QWORD *v25; // rdx
  int v26; // eax
  unsigned __int64 v27; // r12
  int v28; // edx
  int NodeMapNamedItem; // eax
  __int64 v30; // rax
  const struct _MICRODOM_DOM_NODE_HEADER *v31; // rbx
  __int64 v33; // r8
  __int128 v34; // [rsp+30h] [rbp-59h] BYREF
  __int64 v35; // [rsp+40h] [rbp-49h]
  const char *v36; // [rsp+48h] [rbp-41h]
  __int64 v37; // [rsp+50h] [rbp-39h] BYREF
  _BYTE *v38; // [rsp+60h] [rbp-29h] BYREF
  int v39; // [rsp+68h] [rbp-21h]
  int v40; // [rsp+6Ch] [rbp-1Dh]
  MicrodomImplementation::CMicrodom *v41; // [rsp+70h] [rbp-19h]
  __int128 v42; // [rsp+78h] [rbp-11h] BYREF
  __int128 v43; // [rsp+88h] [rbp-1h]
  unsigned __int64 v44; // [rsp+98h] [rbp+Fh] BYREF

  LODWORD(v44) = 0;
  if ( !a4 )
  {
    v35 = 3302;
    *(_QWORD *)&v34 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v34 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetAttribute";
    v36 = "Not-null check failed: Value";
    RtlReportErrorOrigination(&v34, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  *a4 = 0;
  if ( a3 && *a3 <= a3[1] && (a3[2] || !*a3) )
  {
    v6 = *(unsigned int *)(a2 + 8);
    v7 = *(_QWORD **)(a1 - 8);
    v8 = -1;
    v9 = (MicrodomImplementation::CDomLayoutCache *)(v7 + 6);
    v42 = 0;
    DWORD2(v42) = -1;
    v10 = v7[12];
    v41 = (MicrodomImplementation::CMicrodom *)v7;
    v43 = 0;
    LODWORD(v44) = 0;
    if ( (unsigned int)v6 >= *(_DWORD *)(v10 + 8) )
    {
      *(_QWORD *)&v34 = "onecore\\base\\xml\\udom_microdom.cpp";
      *((_QWORD *)&v34 + 1) = "MicrodomImplementation::CDomLayoutCache::FindObject";
      v38 = 0;
      v35 = 3861;
      v36 = "ulIndex < m_Header->ulTotalNodeCount";
      LODWORD(v11) = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                       &v44,
                       &v34);
      if ( (v11 & 0x80000000) != 0LL )
        return (unsigned int)v11;
    }
    else
    {
      LODWORD(v11) = MicrodomImplementation::CDomLayoutCache::AdvanceCachedPointer(
                       (MicrodomImplementation::CDomLayoutCache *)(v7 + 6),
                       v6);
      if ( (v11 & 0x80000000) != 0LL )
        return (unsigned int)v11;
      _mm_lfence();
      v38 = *(_BYTE **)(*(_QWORD *)v9 + 40 * v6 + 8);
    }
    v12 = 152 * v6 + v7[75];
    if ( !*(_BYTE *)(v12 + 145) )
    {
      v44 = 0;
      v37 = 0;
      v35 = 0;
      v34 = 0;
      LODWORD(v11) = MicrodomImplementation::CDomLayoutCache::GetNodeChildren(
                       (_DWORD)v9,
                       v6,
                       (unsigned int)&v34,
                       (unsigned int)&v44,
                       (__int64)&v37);
      if ( (v11 & 0x80000000) != 0LL )
      {
        BUCL::CVector<Windows::Microdom::Rtl::Node,BUCL::Rtl::CCallDisposition>::Close(&v34);
        return (unsigned int)v11;
      }
      v13 = *(void **)(v12 + 16);
      v14 = v44;
      v15 = v37;
      v16 = v35;
      *(_OWORD *)(v12 + 16) = v34;
      *(_QWORD *)(v12 + 32) = v16;
      v17 = *(_QWORD *)(v12 + 16);
      *(_QWORD *)(v12 + 48) = v14;
      *(_QWORD *)(v12 + 40) = v17;
      *(_QWORD *)(v12 + 64) = v15;
      *(_QWORD *)(v12 + 56) = v17 + 16 * v14;
      *(_BYTE *)(v12 + 145) = 1;
      if ( v13 )
        operator delete(v13);
    }
    v18 = v41;
    v19 = *((_QWORD *)v41 + 75) + 152 * v6;
    v20 = *v38 & 0xF;
    v37 = v19;
    if ( v20 == 1 && *(_DWORD *)(v19 + 8) == -1 )
    {
      v21 = (char *)v41 + 576;
      v22 = *((_QWORD *)v41 + 73);
      v23 = *((_QWORD *)v41 + 74);
      v24 = (_BYTE *)*((_QWORD *)v41 + 72);
      v38 = v24;
      if ( v22 == v23 )
      {
        v33 = (v23 - (__int64)v24) >> 3;
        if ( v33 == -1 )
        {
          LODWORD(v11) = -1073741675;
          return (unsigned int)v11;
        }
        BUCL::CVector<Windows::Vector<Windows::Microdom::Rtl::Node const> *,BUCL::Rtl::CCallDisposition>::GrowToAtLeast(
          (char *)v41 + 576,
          &v44,
          v33 + 1);
        LODWORD(v11) = v44;
        if ( (v44 & 0x80000000) != 0LL )
          return (unsigned int)v11;
        v19 = v37;
        v18 = v41;
        v24 = v38;
      }
      v25 = (_QWORD *)*((_QWORD *)v21 + 1);
      if ( v25 )
        *v25 = v19 + 56;
      *((_QWORD *)v21 + 1) += 8LL;
      v26 = 0;
      v27 = (v22 - (__int64)v24) >> 3;
      v44 = 0;
      if ( v27 > 0xFFFFFFFF )
      {
        HIDWORD(v44) = -1073741675;
      }
      else
      {
        v26 = v27;
        LODWORD(v44) = v27;
        if ( v27 == (unsigned int)v27 )
          HIDWORD(v44) = 0;
        else
          HIDWORD(v44) = -1073741595;
      }
      v11 = HIDWORD(v44);
      *(_DWORD *)(v19 + 8) = v26;
      if ( (v11 & 0x80000000) != 0LL )
        return (unsigned int)v11;
    }
    v28 = *(_DWORD *)(v19 + 8);
    if ( v28 != -1 )
    {
      v38 = (_BYTE *)v43;
      v40 = HIDWORD(v43);
      v39 = v28;
      NodeMapNamedItem = MicrodomImplementation::CMicrodom::GetNodeMapNamedItem(v18, &v38, 0, a3, &v42);
      if ( NodeMapNamedItem < 0 )
        goto LABEL_29;
      v8 = DWORD2(v42);
    }
    if ( v8 == -1 )
      return 0;
    v30 = *((_QWORD *)v9 + 6);
    LODWORD(v44) = 0;
    if ( v8 >= *(_DWORD *)(v30 + 8) )
    {
      v35 = 3861;
      *(_QWORD *)&v34 = "onecore\\base\\xml\\udom_microdom.cpp";
      v31 = 0;
      *((_QWORD *)&v34 + 1) = "MicrodomImplementation::CDomLayoutCache::FindObject";
      v36 = "ulIndex < m_Header->ulTotalNodeCount";
      NodeMapNamedItem = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                           &v44,
                           &v34);
      if ( NodeMapNamedItem < 0 )
        goto LABEL_29;
LABEL_28:
      NodeMapNamedItem = MicrodomImplementation::CMicrodom::GetNodeValue(v41, v8, v31, a4);
      if ( NodeMapNamedItem < 0 )
        goto LABEL_29;
      return 0;
    }
    NodeMapNamedItem = MicrodomImplementation::CDomLayoutCache::AdvanceCachedPointer(v9, v8);
    if ( NodeMapNamedItem >= 0 )
    {
      v31 = *(const struct _MICRODOM_DOM_NODE_HEADER **)(*(_QWORD *)v9 + 40LL * v8 + 8);
      goto LABEL_28;
    }
LABEL_29:
    LODWORD(v11) = NodeMapNamedItem;
    return (unsigned int)v11;
  }
  v35 = 3303;
  *(_QWORD *)&v34 = "onecore\\base\\xml\\udom_microdom.cpp";
  *((_QWORD *)&v34 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetAttribute";
  v36 = "RtlIsLUtf8StringValid(Name)";
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v44,
           &v34);
}

```

## disassembly

```asm
0x180005300  push    rbp
0x180005302  push    rsi
0x180005303  push    rdi
0x180005304  lea     rbp, [rsp-47h]
0x180005309  sub     rsp, 0D0h
0x180005310  mov     rax, cs:__security_cookie
0x180005317  xor     rax, rsp
0x18000531a  mov     [rbp+57h+var_40], rax
0x18000531e  mov     rdi, r8
0x180005321  mov     rsi, r9
0x180005324  xor     r8d, r8d
0x180005327  mov     dword ptr [rbp+57h+var_48], r8d
0x18000532b  test    r9, r9
0x18000532e  jz      loc_180005617
0x180005334  mov     [r9], r8
0x180005337  test    rdi, rdi
0x18000533a  jz      loc_1800056B3
0x180005340  mov     rax, [rdi]
0x180005343  cmp     rax, [rdi+8]
0x180005347  ja      loc_1800056B3
0x18000534d  cmp     [rdi+10h], r8
0x180005351  jz      loc_1800056AA
0x180005357  mov     [rsp+0E0h+arg_10], rbx
0x18000535f  lea     r9, aUlindexMHeader; "ulIndex < m_Header->ulTotalNodeCount"
0x180005366  mov     [rsp+0E0h+var_18], r12
0x18000536e  mov     eax, 0FFFFFFFFh
0x180005373  mov     r12d, [rdx+8]
0x180005377  xorps   xmm0, xmm0
0x18000537a  mov     [rsp+0E0h+var_20], r13
0x180005382  lea     rdx, aMicrodomimplem_18; "MicrodomImplementation::CDomLayoutCache"...
0x180005389  mov     r13, [rcx-8]
0x18000538d  lea     rcx, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180005394  mov     [rsp+0E0h+var_28], r14
0x18000539c  mov     r14d, eax
0x18000539f  mov     [rsp+0E0h+var_30], r15
0x1800053a7  lea     r15, [r13+30h]
0x1800053ab  movups  [rbp+57h+var_68], xmm0
0x1800053af  mov     dword ptr [rbp+57h+var_68+8], eax
0x1800053b2  mov     rax, [r15+30h]
0x1800053b6  mov     [rbp+57h+var_70], r13
0x1800053ba  movups  [rbp+57h+var_58], xmm0
0x1800053be  mov     dword ptr [rbp+57h+var_48], r8d
0x1800053c2  cmp     r12d, [rax+8]
0x1800053c6  jnb     loc_1800056EE
0x1800053cc  mov     edx, r12d; unsigned int
0x1800053cf  mov     rcx, r15; this
0x1800053d2  call    ?AdvanceCachedPointer@CDomLayoutCache@MicrodomImplementation@@AEAAJK@Z; MicrodomImplementation::CDomLayoutCache::AdvanceCachedPointer(ulong)
0x1800053d7  mov     ebx, eax
0x1800053d9  test    eax, eax
0x1800053db  js      loc_1800055D1
0x1800053e1  lfence
0x1800053e4  mov     rax, [r15]
0x1800053e7  lea     rcx, [r12+r12*4]
0x1800053eb  mov     rax, [rax+rcx*8+8]
0x1800053f0  mov     [rbp+57h+var_80], rax
0x1800053f4  mov     r13, [r13+258h]
0x1800053fb  imul    rcx, r12, 98h
0x180005402  add     r13, rcx
0x180005405  cmp     byte ptr [r13+91h], 0
0x18000540d  jnz     loc_18000549B
0x180005413  xor     eax, eax
0x180005415  lea     r9, [rbp+57h+var_48]
0x180005419  mov     [rbp+57h+var_48], rax
0x18000541d  lea     r8, [rbp+57h+var_B0]
0x180005421  mov     [rbp+57h+var_90], rax
0x180005425  xorps   xmm0, xmm0
0x180005428  mov     [rbp+57h+var_A0], rax
0x18000542c  mov     edx, r12d
0x18000542f  lea     rax, [rbp+57h+var_90]
0x180005433  mov     rcx, r15
0x180005436  mov     [rsp+0E0h+var_C0], rax
0x18000543b  movdqu  [rbp+57h+var_B0], xmm0
0x180005440  call    ?GetNodeChildren@CDomLayoutCache@MicrodomImplementation@@QEAAJKPEAV?$CVector@UNode@Rtl@Microdom@Windows@@VCCallDisposition@2BUCL@@@BUCL@@PEA_K1@Z; MicrodomImplementation::CDomLayoutCache::GetNodeChildren(ulong,BUCL::CVector<Windows::Microdom::Rtl::Node,BUCL::Rtl::CCallDisposition> *,unsigned __int64 *,unsigned __int64 *)
0x180005445  mov     ebx, eax
0x180005447  test    eax, eax
0x180005449  js      loc_180005722
0x18000544f  mov     rcx, [r13+10h]; Block
0x180005453  mov     r8, [rbp+57h+var_48]
0x180005457  movups  xmm0, [rbp+57h+var_B0]
0x18000545b  mov     rax, [rbp+57h+var_90]
0x18000545f  movsd   xmm1, [rbp+57h+var_A0]
0x180005464  movups  xmmword ptr [r13+10h], xmm0
0x180005469  movsd   qword ptr [r13+20h], xmm1
0x18000546f  mov     rdx, [r13+10h]
0x180005473  mov     [r13+30h], r8
0x180005477  shl     r8, 4
0x18000547b  add     r8, rdx
0x18000547e  mov     [r13+28h], rdx
0x180005482  mov     [r13+40h], rax
0x180005486  mov     [r13+38h], r8
0x18000548a  mov     byte ptr [r13+91h], 1
0x180005492  test    rcx, rcx
0x180005495  jnz     loc_180005730
0x18000549b  mov     rax, [rbp+57h+var_80]
0x18000549f  mov     r11, r14
0x1800054a2  mov     r10, [rbp+57h+var_70]
0x1800054a6  imul    rcx, r12, 98h
0x1800054ad  movzx   eax, byte ptr [rax]
0x1800054b0  add     rcx, [r10+258h]
0x1800054b7  and     al, 0Fh
0x1800054b9  mov     [rbp+57h+var_90], rcx
0x1800054bd  cmp     al, 1
0x1800054bf  jnz     short loc_18000553B
0x1800054c1  cmp     [rcx+8], r14d
0x1800054c5  jnz     short loc_18000553B
0x1800054c7  lea     r13, [r10+240h]
0x1800054ce  mov     r12, [r13+8]
0x1800054d2  mov     r8, [r13+10h]
0x1800054d6  mov     r9, [r13+0]
0x1800054da  mov     [rbp+57h+var_80], r9
0x1800054de  cmp     r12, r8
0x1800054e1  jz      loc_18000573A
0x1800054e7  mov     rdx, [r13+8]
0x1800054eb  test    rdx, rdx
0x1800054ee  jz      short loc_1800054F7
0x1800054f0  lea     rax, [rcx+38h]
0x1800054f4  mov     [rdx], rax
0x1800054f7  add     qword ptr [r13+8], 8
0x1800054fc  sub     r12, r9
0x1800054ff  xor     eax, eax
0x180005501  sar     r12, 3
0x180005505  mov     [rbp+57h+var_48], rax
0x180005509  cmp     r12, r11
0x18000550c  ja      loc_18000565D
0x180005512  mov     eax, r12d
0x180005515  mov     dword ptr [rbp+57h+var_48], eax
0x180005518  cmp     r12, rax
0x18000551b  jnz     loc_180005750
0x180005521  mov     dword ptr [rbp+57h+var_48+4], 0
0x180005528  mov     rbx, [rbp+57h+var_48]
0x18000552c  shr     rbx, 20h
0x180005530  mov     [rcx+8], eax
0x180005533  test    ebx, ebx
0x180005535  js      loc_1800055D1
0x18000553b  mov     edx, [rcx+8]
0x18000553e  cmp     edx, r11d
0x180005541  jz      short loc_18000557D
0x180005543  mov     rax, qword ptr [rbp+57h+var_58]
0x180005547  mov     r9, rdi
0x18000554a  mov     [rbp+57h+var_80], rax
0x18000554e  xor     r8d, r8d
0x180005551  mov     eax, dword ptr [rbp+57h+var_58+0Ch]
0x180005554  mov     rcx, r10
0x180005557  mov     [rbp+57h+var_74], eax
0x18000555a  lea     rax, [rbp+57h+var_68]
0x18000555e  mov     [rbp+57h+var_78], edx
0x180005561  lea     rdx, [rbp+57h+var_80]
0x180005565  mov     [rsp+0E0h+var_C0], rax
0x18000556a  call    ?GetNodeMapNamedItem@CMicrodom@MicrodomImplementation@@QEAAJUNamedNodeMap@Rtl@Microdom@Windows@@PEBU_LUTF8_STRING@@1PEAUNode@456@@Z; MicrodomImplementation::CMicrodom::GetNodeMapNamedItem(Windows::Microdom::Rtl::NamedNodeMap,_LUTF8_STRING const *,_LUTF8_STRING const *,Windows::Microdom::Rtl::Node *)
0x18000556f  test    eax, eax
0x180005571  js      short loc_1800055CF
0x180005573  mov     r14d, dword ptr [rbp+57h+var_68+8]
0x180005577  mov     r11d, 0FFFFFFFFh
0x18000557d  cmp     r14d, r11d
0x180005580  jz      loc_180005613
0x180005586  mov     rax, [r15+30h]
0x18000558a  mov     dword ptr [rbp+57h+var_48], 0
0x180005591  cmp     r14d, [rax+8]
0x180005595  jnb     loc_18000575C
0x18000559b  mov     edx, r14d; unsigned int
0x18000559e  mov     rcx, r15; this
0x1800055a1  call    ?AdvanceCachedPointer@CDomLayoutCache@MicrodomImplementation@@AEAAJK@Z; MicrodomImplementation::CDomLayoutCache::AdvanceCachedPointer(ulong)
0x1800055a6  test    eax, eax
0x1800055a8  js      short loc_1800055CF
0x1800055aa  mov     eax, r14d
0x1800055ad  lea     r8, [rax+rax*4]
0x1800055b1  mov     rax, [r15]
0x1800055b4  mov     rbx, [rax+r8*8+8]
0x1800055b9  mov     rcx, [rbp+57h+var_70]; this
0x1800055bd  mov     r9, rsi; struct _LUTF8_STRING **
0x1800055c0  mov     r8, rbx; struct _MICRODOM_DOM_NODE_HEADER *
0x1800055c3  mov     edx, r14d; unsigned int
0x1800055c6  call    ?GetNodeValue@CMicrodom@MicrodomImplementation@@QEAAJKPEBU_MICRODOM_DOM_NODE_HEADER@@PEAPEBU_LUTF8_STRING@@@Z; MicrodomImplementation::CMicrodom::GetNodeValue(ulong,_MICRODOM_DOM_NODE_HEADER const *,_LUTF8_STRING const * *)
0x1800055cb  test    eax, eax
0x1800055cd  jns     short loc_180005613
0x1800055cf  mov     ebx, eax
0x1800055d1  mov     eax, ebx
0x1800055d3  mov     r14, [rsp+0E0h+var_28]
0x1800055db  mov     r13, [rsp+0E0h+var_20]
0x1800055e3  mov     r12, [rsp+0E0h+var_18]
0x1800055eb  mov     rbx, [rsp+0E0h+arg_10]
0x1800055f3  mov     r15, [rsp+0E0h+var_30]
0x1800055fb  mov     rcx, [rbp+57h+var_40]
0x1800055ff  xor     rcx, rsp; StackCookie
0x180005602  call    __security_check_cookie
0x180005607  add     rsp, 0D0h
0x18000560e  pop     rdi
0x18000560f  pop     rsi
0x180005610  pop     rbp
0x180005611  retn
0x180005613  xor     eax, eax
0x180005615  jmp     short loc_1800055D3
0x180005617  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18000561e  mov     [rbp+57h+var_A0], 0CE6h
0x180005626  mov     qword ptr [rbp+57h+var_B0], rax
0x18000562a  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180005631  lea     rax, aMicrodomimplem_7; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180005638  mov     r8d, 0C000000Dh
0x18000563e  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180005642  lea     rcx, [rbp+57h+var_B0]
0x180005646  lea     rax, aNotNullCheckFa_20; "Not-null check failed: Value"
0x18000564d  mov     [rbp+57h+var_98], rax
0x180005651  call    RtlReportErrorOrigination
0x180005656  mov     eax, 0C000000Dh
0x18000565b  jmp     short loc_1800055FB
0x18000565d  mov     ebx, 0C0000095h
0x180005662  mov     dword ptr [rbp+57h+var_48+4], ebx
0x180005665  jmp     loc_180005528
0x18000566a  mov     ebx, 0C0000095h
0x18000566f  test    ebx, ebx
0x180005671  jns     loc_18000557D
0x180005677  jmp     loc_1800055D1
0x18000567c  inc     r8
0x18000567f  lea     rdx, [rbp+57h+var_48]
0x180005683  mov     rcx, r13
0x180005686  call    ?GrowToAtLeast@?$CVector@PEAU?$Vector@$$CBUNode@Rtl@Microdom@Windows@@@Windows@@VCCallDisposition@Rtl@BUCL@@@BUCL@@AEAA?AVCCallDisposition@Rtl@2@_KW4GrowthPolicy@2@@Z; BUCL::CVector<Windows::Vector<Windows::Microdom::Rtl::Node const> *,BUCL::Rtl::CCallDisposition>::GrowToAtLeast(unsigned __int64,BUCL::GrowthPolicy)
0x18000568b  mov     ebx, dword ptr [rbp+57h+var_48]
0x18000568e  mov     r11, r14
0x180005691  test    ebx, ebx
0x180005693  js      loc_1800055D1
0x180005699  mov     rcx, [rbp+57h+var_90]
0x18000569d  mov     r10, [rbp+57h+var_70]
0x1800056a1  mov     r9, [rbp+57h+var_80]
0x1800056a5  jmp     loc_1800054E7
0x1800056aa  test    rax, rax
0x1800056ad  jz      loc_180005357
0x1800056b3  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800056ba  mov     [rbp+57h+var_A0], 0CE7h
0x1800056c2  mov     qword ptr [rbp+57h+var_B0], rax
0x1800056c6  lea     rdx, [rbp+57h+var_B0]
0x1800056ca  lea     rax, aMicrodomimplem_7; "MicrodomImplementation::CMicrodom_IRtlM"...
0x1800056d1  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1800056d5  lea     rcx, [rbp+57h+var_48]
0x1800056d9  lea     rax, aRtlislutf8stri_13; "RtlIsLUtf8StringValid(Name)"
0x1800056e0  mov     [rbp+57h+var_98], rax
0x1800056e4  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800056e9  jmp     loc_1800055FB
0x1800056ee  mov     qword ptr [rbp+57h+var_B0], rcx
0x1800056f2  lea     rcx, [rbp+57h+var_48]
0x1800056f6  mov     qword ptr [rbp+57h+var_B0+8], rdx
0x1800056fa  lea     rdx, [rbp+57h+var_B0]
0x1800056fe  mov     [rbp+57h+var_80], r8
0x180005702  mov     [rbp+57h+var_A0], 0F15h
0x18000570a  mov     [rbp+57h+var_98], r9
0x18000570e  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180005713  mov     ebx, eax
0x180005715  test    eax, eax
0x180005717  jns     loc_1800053F4
0x18000571d  jmp     loc_1800055D1
0x180005722  lea     rcx, [rbp+57h+var_B0]
0x180005726  call    ?Close@?$CVector@UNode@Rtl@Microdom@Windows@@VCCallDisposition@2BUCL@@@BUCL@@QEAAXXZ; BUCL::CVector<Windows::Microdom::Rtl::Node,BUCL::Rtl::CCallDisposition>::Close(void)
0x18000572b  jmp     loc_1800055D1
0x180005730  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005735  jmp     loc_18000549B
0x18000573a  sub     r8, r9
0x18000573d  sar     r8, 3
0x180005741  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180005745  jz      loc_18000566A
0x18000574b  jmp     loc_18000567C
0x180005750  mov     dword ptr [rbp+57h+var_48+4], 0C00000E5h
0x180005757  jmp     loc_180005528
0x18000575c  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180005763  mov     [rbp+57h+var_A0], 0F15h
0x18000576b  mov     qword ptr [rbp+57h+var_B0], rax
0x18000576f  lea     rdx, [rbp+57h+var_B0]
0x180005773  lea     rax, aMicrodomimplem_18; "MicrodomImplementation::CDomLayoutCache"...
0x18000577a  xor     ebx, ebx
0x18000577c  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180005780  lea     rcx, [rbp+57h+var_48]
0x180005784  lea     rax, aUlindexMHeader; "ulIndex < m_Header->ulTotalNodeCount"
0x18000578b  mov     [rbp+57h+var_98], rax
0x18000578f  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180005794  test    eax, eax
0x180005796  jns     loc_1800055B9
0x18000579c  jmp     loc_1800055CF
```
