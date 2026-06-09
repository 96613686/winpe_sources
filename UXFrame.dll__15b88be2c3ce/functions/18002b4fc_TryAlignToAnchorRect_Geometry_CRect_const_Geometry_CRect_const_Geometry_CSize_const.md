# TryAlignToAnchorRect(Geometry::CRect const &,Geometry::CRect const &,Geometry::CSize const &)

- ea: `0x18002b4fc`
- end: `0x18002b784`
- name: `?TryAlignToAnchorRect@@YA?AUCRect@Geometry@@AEBU12@0AEBUCSize@2@@Z`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800261dc`

## callees

- `0x18001049c`
- `0x1800228f4`
- `0x180023ccc`
- `0x180026d38`
- `0x180028360`
- `0x18002b4fc`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18002b521`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18002b521`

## string_xrefs

- `0x18002b707`: `pcshell\shell\uxframe\dll\WindowPositioningBehavior.h`

## pseudocode

```c
__int64 __fastcall TryAlignToAnchorRect(__int64 a1, int *a2, int *a3, _DWORD *a4)
{
  LANGID ThreadUILanguage; // ax
  unsigned int v9; // eax
  int v10; // r11d
  const char *v11; // r9
  int v12; // ebx
  int v13; // r8d
  int v14; // edx
  int v15; // r10d
  int v16; // ecx
  int v17; // eax
  int v18; // esi
  _DWORD *v19; // rbx
  _DWORD *v20; // rsi
  int SegmentOffset; // eax
  int v22; // r10d
  int v23; // r11d
  int v24; // eax
  int v25; // eax
  int v26; // r10d
  int v27; // r11d
  int v28; // esi
  int v29; // edi
  int v30; // ebx
  int v31; // eax
  int v32; // r11d
  int v33; // r10d
  __int64 v34; // r8
  int *AnchorPointOnRect; // rdx
  unsigned int v36; // ebx
  __int128 v38; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  int v40; // [rsp+70h] [rbp+40h] BYREF
  int v41; // [rsp+74h] [rbp+44h]
  int v42; // [rsp+78h] [rbp+48h] BYREF
  int v43; // [rsp+7Ch] [rbp+4Ch]

  ThreadUILanguage = GetThreadUILanguage();
  v9 = IsBiDiLocale(ThreadUILanguage);
  v10 = a3[2];
  v11 = (const char *)v9;
  v12 = *a3;
  v13 = v10 - *a3;
  if ( *a4 > v13 || (v14 = a3[3], v15 = a3[1], v16 = v14 - v15, a4[1] > v14 - v15) )
  {
    v36 = v9 != 0 ? 2 : 0;
    AnchorPointOnRect = (int *)GetAnchorPointOnRect(&v40, v36, a3, -v9);
    v34 = v36;
    goto LABEL_31;
  }
  v17 = *a3;
  v18 = a3[1];
  if ( *a2 > v12 )
    v17 = *a2;
  if ( a2[1] > v15 )
    v18 = a2[1];
  if ( a2[2] < v10 )
    v10 = a2[2];
  if ( a2[3] < v14 )
    v14 = a2[3];
  if ( v17 >= v10 || v18 >= v14 )
  {
    v40 = v12 + v13 / 2;
    v34 = 4;
    AnchorPointOnRect = &v40;
    v41 = v15 + v16 / 2;
LABEL_31:
    AlignToAnchorPoint(a1, AnchorPointOnRect, v34, a4);
    return a1;
  }
  v19 = &unk_180061A20;
  if ( !(_DWORD)v11 )
    v19 = &unk_180061A60;
  v20 = v19 + 15;
  while ( 1 )
  {
    if ( v19 == v20 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x316,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\WindowPositioningBehavior.h",
        v11);
    GetAnchorPointOnRect(&v40, (unsigned int)v19[1], a2, v11);
    AlignToAnchorPoint(&v38, &v40, (unsigned int)v19[2], a4);
    if ( !*v19 )
    {
      if ( (int)v38 >= *a3 && SDWORD2(v38) <= a3[2] )
      {
        v42 = a3[1];
        v43 = a3[3];
        v40 = DWORD1(v38);
        v41 = HIDWORD(v38);
        SegmentOffset = GetSegmentOffset(
                          (const struct Geometry::CSegment1D *)&v42,
                          (const struct Geometry::CSegment1D *)&v40);
        HIDWORD(v38) = SegmentOffset + v22;
        DWORD1(v38) = SegmentOffset + v23;
LABEL_21:
        *(_OWORD *)a1 = v38;
        return a1;
      }
      goto LABEL_25;
    }
    v24 = a3[1];
    if ( *v19 != 1 )
      break;
    if ( SDWORD1(v38) >= v24 && SHIDWORD(v38) <= a3[3] )
    {
      v42 = *a3;
      v43 = a3[2];
      v40 = v38;
      v41 = DWORD2(v38);
      v25 = GetSegmentOffset((const struct Geometry::CSegment1D *)&v42, (const struct Geometry::CSegment1D *)&v40);
      LODWORD(v38) = v25 + v26;
      DWORD2(v38) = v25 + v27;
      goto LABEL_21;
    }
LABEL_25:
    v19 += 3;
  }
  v28 = DWORD1(v38);
  v29 = HIDWORD(v38);
  v43 = a3[3];
  v40 = DWORD1(v38);
  v41 = HIDWORD(v38);
  v42 = v24;
  GetSegmentOffset((const struct Geometry::CSegment1D *)&v42, (const struct Geometry::CSegment1D *)&v40);
  v30 = v38;
  v40 = v38;
  v42 = *a3;
  v43 = a3[2];
  v41 = DWORD2(v38);
  v31 = GetSegmentOffset((const struct Geometry::CSegment1D *)&v42, (const struct Geometry::CSegment1D *)&v40);
  *(_DWORD *)a1 = v30 + v31;
  *(_DWORD *)(a1 + 4) = v32 + v28;
  *(_DWORD *)(a1 + 8) = v31 + v33;
  *(_DWORD *)(a1 + 12) = v32 + v29;
  return a1;
}

```

## disassembly

```asm
0x18002b4fc  mov     [rsp-28h+arg_0], rbx
0x18002b501  mov     [rsp-28h+arg_8], rsi
0x18002b506  push    rbp
0x18002b507  push    rdi
0x18002b508  push    r12
0x18002b50a  push    r14
0x18002b50c  push    r15
0x18002b50e  mov     rbp, rsp
0x18002b511  sub     rsp, 30h
0x18002b515  mov     rdi, r9
0x18002b518  mov     r14, r8
0x18002b51b  mov     r12, rdx
0x18002b51e  mov     r15, rcx
0x18002b521  call    cs:__imp_GetThreadUILanguage
0x18002b527  movzx   ecx, ax; unsigned int
0x18002b52a  call    ?IsBiDiLocale@@YAHK@Z; IsBiDiLocale(ulong)
0x18002b52f  mov     r11d, [r14+8]
0x18002b533  mov     r9d, eax; char *
0x18002b536  mov     ebx, [r14]
0x18002b539  mov     r8d, r11d
0x18002b53c  sub     r8d, ebx
0x18002b53f  cmp     [rdi], r8d
0x18002b542  jg      loc_18002B743
0x18002b548  mov     edx, [r14+0Ch]
0x18002b54c  mov     ecx, edx
0x18002b54e  mov     r10d, [r14+4]
0x18002b552  sub     ecx, r10d
0x18002b555  cmp     [rdi+4], ecx
0x18002b558  jg      loc_18002B743
0x18002b55e  cmp     [r12], ebx
0x18002b562  mov     eax, ebx
0x18002b564  mov     esi, r10d
0x18002b567  cmovg   eax, [r12]
0x18002b56c  cmp     [r12+4], r10d
0x18002b571  cmovg   esi, [r12+4]
0x18002b577  cmp     [r12+8], r11d
0x18002b57c  cmovl   r11d, [r12+8]
0x18002b582  cmp     [r12+0Ch], edx
0x18002b587  cmovl   edx, [r12+0Ch]
0x18002b58d  cmp     eax, r11d
0x18002b590  jge     loc_18002B719
0x18002b596  cmp     esi, edx
0x18002b598  jge     loc_18002B719
0x18002b59e  test    r9d, r9d
0x18002b5a1  lea     rax, unk_180061A60
0x18002b5a8  lea     rbx, unk_180061A20
0x18002b5af  cmovz   rbx, rax
0x18002b5b3  lea     rsi, [rbx+3Ch]
0x18002b5b7  cmp     rbx, rsi
0x18002b5ba  jz      loc_18002B703
0x18002b5c0  mov     edx, [rbx+4]
0x18002b5c3  lea     rcx, [rbp+arg_10]
0x18002b5c7  mov     r8, r12
0x18002b5ca  call    ?GetAnchorPointOnRect@@YA?AUCPoint@Geometry@@W4AnchorPointType@@AEBUCRect@2@@Z; GetAnchorPointOnRect(AnchorPointType,Geometry::CRect const &)
0x18002b5cf  mov     r8d, [rbx+8]
0x18002b5d3  lea     rdx, [rbp+arg_10]
0x18002b5d7  mov     r9, rdi
0x18002b5da  lea     rcx, [rbp+var_10]
0x18002b5de  call    ?AlignToAnchorPoint@@YA?AUCRect@Geometry@@AEBUCPoint@2@W4AnchorPointType@@AEBUCSize@2@@Z; AlignToAnchorPoint(Geometry::CPoint const &,AnchorPointType,Geometry::CSize const &)
0x18002b5e3  cmp     dword ptr [rbx], 0
0x18002b5e6  jnz     short loc_18002B640
0x18002b5e8  mov     eax, [r14]
0x18002b5eb  cmp     dword ptr [rbp+var_10], eax
0x18002b5ee  jl      short loc_18002B657
0x18002b5f0  mov     eax, [r14+8]
0x18002b5f4  cmp     dword ptr [rbp+var_10+8], eax
0x18002b5f7  jg      short loc_18002B657
0x18002b5f9  mov     eax, [r14+4]
0x18002b5fd  lea     rdx, [rbp+arg_10]; struct Geometry::CSegment1D *
0x18002b601  mov     r11d, dword ptr [rbp+var_10+4]
0x18002b605  lea     rcx, [rbp+arg_18]; struct Geometry::CSegment1D *
0x18002b609  mov     r10d, dword ptr [rbp+var_10+0Ch]
0x18002b60d  mov     [rbp+arg_18], eax
0x18002b610  mov     eax, [r14+0Ch]
0x18002b614  mov     [rbp+arg_1C], eax
0x18002b617  mov     [rbp+arg_10], r11d
0x18002b61b  mov     [rbp+arg_14], r10d
0x18002b61f  call    ?GetSegmentOffset@@YAJAEBUCSegment1D@Geometry@@0@Z; GetSegmentOffset(Geometry::CSegment1D const &,Geometry::CSegment1D const &)
0x18002b624  add     r10d, eax
0x18002b627  add     r11d, eax
0x18002b62a  mov     dword ptr [rbp+var_10+0Ch], r10d
0x18002b62e  mov     dword ptr [rbp+var_10+4], r11d
0x18002b632  movups  xmm0, [rbp+var_10]
0x18002b636  movdqu  xmmword ptr [r15], xmm0
0x18002b63b  jmp     loc_18002B76A
0x18002b640  cmp     dword ptr [rbx], 1
0x18002b643  mov     eax, [r14+4]
0x18002b647  mov     ecx, [r14+0Ch]
0x18002b64b  jnz     short loc_18002B69A
0x18002b64d  cmp     dword ptr [rbp+var_10+4], eax
0x18002b650  jl      short loc_18002B657
0x18002b652  cmp     dword ptr [rbp+var_10+0Ch], ecx
0x18002b655  jle     short loc_18002B660
0x18002b657  add     rbx, 0Ch
0x18002b65b  jmp     loc_18002B5B7
0x18002b660  mov     eax, [r14]
0x18002b663  lea     rdx, [rbp+arg_10]; struct Geometry::CSegment1D *
0x18002b667  mov     r10d, dword ptr [rbp+var_10]
0x18002b66b  lea     rcx, [rbp+arg_18]; struct Geometry::CSegment1D *
0x18002b66f  mov     r11d, dword ptr [rbp+var_10+8]
0x18002b673  mov     [rbp+arg_18], eax
0x18002b676  mov     eax, [r14+8]
0x18002b67a  mov     [rbp+arg_1C], eax
0x18002b67d  mov     [rbp+arg_10], r10d
0x18002b681  mov     [rbp+arg_14], r11d
0x18002b685  call    ?GetSegmentOffset@@YAJAEBUCSegment1D@Geometry@@0@Z; GetSegmentOffset(Geometry::CSegment1D const &,Geometry::CSegment1D const &)
0x18002b68a  add     r10d, eax
0x18002b68d  add     r11d, eax
0x18002b690  mov     dword ptr [rbp+var_10], r10d
0x18002b694  mov     dword ptr [rbp+var_10+8], r11d
0x18002b698  jmp     short loc_18002B632
0x18002b69a  mov     esi, dword ptr [rbp+var_10+4]
0x18002b69d  lea     rdx, [rbp+arg_10]; struct Geometry::CSegment1D *
0x18002b6a1  mov     edi, dword ptr [rbp+var_10+0Ch]
0x18002b6a4  mov     [rbp+arg_1C], ecx
0x18002b6a7  lea     rcx, [rbp+arg_18]; struct Geometry::CSegment1D *
0x18002b6ab  mov     [rbp+arg_10], esi
0x18002b6ae  mov     [rbp+arg_14], edi
0x18002b6b1  mov     [rbp+arg_18], eax
0x18002b6b4  call    ?GetSegmentOffset@@YAJAEBUCSegment1D@Geometry@@0@Z; GetSegmentOffset(Geometry::CSegment1D const &,Geometry::CSegment1D const &)
0x18002b6b9  mov     ebx, dword ptr [rbp+var_10]
0x18002b6bc  lea     rdx, [rbp+arg_10]; struct Geometry::CSegment1D *
0x18002b6c0  mov     r10d, dword ptr [rbp+var_10+8]
0x18002b6c4  lea     rcx, [rbp+arg_18]; struct Geometry::CSegment1D *
0x18002b6c8  mov     r11d, eax
0x18002b6cb  mov     [rbp+arg_10], ebx
0x18002b6ce  mov     eax, [r14]
0x18002b6d1  mov     [rbp+arg_18], eax
0x18002b6d4  mov     eax, [r14+8]
0x18002b6d8  mov     [rbp+arg_1C], eax
0x18002b6db  mov     [rbp+arg_14], r10d
0x18002b6df  call    ?GetSegmentOffset@@YAJAEBUCSegment1D@Geometry@@0@Z; GetSegmentOffset(Geometry::CSegment1D const &,Geometry::CSegment1D const &)
0x18002b6e4  lea     ecx, [r11+rsi]
0x18002b6e8  lea     r8d, [r11+rdi]
0x18002b6ec  lea     edx, [rax+r10]
0x18002b6f0  add     eax, ebx
0x18002b6f2  mov     [r15], eax
0x18002b6f5  mov     [r15+4], ecx
0x18002b6f9  mov     [r15+8], edx
0x18002b6fd  mov     [r15+0Ch], r8d
0x18002b701  jmp     short loc_18002B76A
0x18002b703  mov     rcx, [rbp+28h]; this
0x18002b707  lea     r8, aPcshellShellUx_1; "pcshell\\shell\\uxframe\\dll\\WindowPos"...
0x18002b70e  mov     edx, 316h; void *
0x18002b713  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002b719  mov     eax, r8d
0x18002b71c  mov     r8d, 2
0x18002b722  cdq
0x18002b723  idiv    r8d
0x18002b726  add     eax, ebx
0x18002b728  mov     [rbp+arg_10], eax
0x18002b72b  mov     eax, ecx
0x18002b72d  cdq
0x18002b72e  idiv    r8d
0x18002b731  mov     r8d, 4
0x18002b737  lea     rdx, [rbp+arg_10]
0x18002b73b  add     eax, r10d
0x18002b73e  mov     [rbp+arg_14], eax
0x18002b741  jmp     short loc_18002B75F
0x18002b743  neg     r9d
0x18002b746  lea     rcx, [rbp+arg_10]
0x18002b74a  mov     r8, r14
0x18002b74d  sbb     ebx, ebx
0x18002b74f  and     ebx, 2
0x18002b752  mov     edx, ebx
0x18002b754  call    ?GetAnchorPointOnRect@@YA?AUCPoint@Geometry@@W4AnchorPointType@@AEBUCRect@2@@Z; GetAnchorPointOnRect(AnchorPointType,Geometry::CRect const &)
0x18002b759  mov     rdx, rax
0x18002b75c  mov     r8d, ebx
0x18002b75f  mov     r9, rdi
0x18002b762  mov     rcx, r15
0x18002b765  call    ?AlignToAnchorPoint@@YA?AUCRect@Geometry@@AEBUCPoint@2@W4AnchorPointType@@AEBUCSize@2@@Z; AlignToAnchorPoint(Geometry::CPoint const &,AnchorPointType,Geometry::CSize const &)
0x18002b76a  mov     rbx, [rsp+30h+arg_0]
0x18002b76f  mov     rax, r15
0x18002b772  mov     rsi, [rsp+30h+arg_8]
0x18002b777  add     rsp, 30h
0x18002b77b  pop     r15
0x18002b77d  pop     r14
0x18002b77f  pop     r12
0x18002b781  pop     rdi
0x18002b782  pop     rbp
0x18002b783  retn
```
