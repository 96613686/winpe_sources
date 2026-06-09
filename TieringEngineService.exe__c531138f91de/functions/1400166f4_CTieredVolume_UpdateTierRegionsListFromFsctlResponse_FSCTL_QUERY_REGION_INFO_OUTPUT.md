# CTieredVolume::UpdateTierRegionsListFromFsctlResponse(_FSCTL_QUERY_REGION_INFO_OUTPUT *)

- ea: `0x1400166f4`
- end: `0x140016a3e`
- name: `?UpdateTierRegionsListFromFsctlResponse@CTieredVolume@@AEAAXPEAU_FSCTL_QUERY_REGION_INFO_OUTPUT@@@Z`
- size: `842`
- prototype: `void __fastcall(CTieredVolume *__hidden this, struct _FSCTL_QUERY_REGION_INFO_OUTPUT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140016d18`

## callees

- `0x140001a00`
- `0x140001a18`
- `0x140004e44`
- `0x140014e28`
- `0x1400166f4`
- `0x140017824`
- `0x1400181a0`
- `0x14001822c`

## import_xrefs

- `msvcrt!malloc` at `0x1400168fd`
- `msvcrt!malloc` at `0x1400168fd`
- `ntdll!RtlCompareMemory` at `0x14001678a`
- `ntdll!RtlCompareMemory` at `0x14001678a`

## pseudocode

```c
void __fastcall CTieredVolume::UpdateTierRegionsListFromFsctlResponse(
        CTieredVolume *this,
        struct _FSCTL_QUERY_REGION_INFO_OUTPUT *a2)
{
  char v4; // di
  int v5; // r8d
  unsigned int v6; // r9d
  _QWORD *v7; // rcx
  unsigned int i; // r13d
  _QWORD *v9; // rax
  int *v10; // rdi
  _QWORD *v11; // r14
  __int64 v12; // rbp
  __int64 v13; // rsi
  int v14; // r14d
  bool v15; // r12
  _DWORD *v16; // rax
  __int64 v17; // rdi
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // r8d
  __int64 v22; // rbp
  _DWORD *v23; // rsi
  unsigned __int64 v24; // rcx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // r8
  _QWORD *v28; // rcx
  __int64 *v29; // rcx
  __int64 v30; // rax
  __int64 **v31; // rax
  char v32; // [rsp+80h] [rbp+8h]

  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  v4 = 0;
  *(_QWORD *)((char *)this + 564) = 0;
  v32 = 0;
  ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll((__int64 *)this + 10);
  v6 = *((_DWORD *)a2 + 7);
  v7 = WPP_GLOBAL_Control;
  for ( i = 0; i < v6; ++i )
  {
    v9 = (_QWORD *)*((_QWORD *)this + 4);
    if ( !v9 )
    {
      v12 = (int)i;
      goto LABEL_32;
    }
    while ( 1 )
    {
      v10 = (int *)v9[2];
      v11 = (_QWORD *)*v9;
      v12 = (int)i;
      v13 = 32LL * (int)i;
      if ( RtlCompareMemory(v10 + 129, (char *)a2 + v13 + 32, 0x10u) == 16 )
        break;
      v9 = v11;
      if ( !v11 )
      {
        v7 = WPP_GLOBAL_Control;
        v4 = v32;
LABEL_32:
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 2u )
        {
          WPP_SF_Z_guid_(v7[2], 145, v5, (_DWORD)this + 672, (__int64)a2 + 32 * v12 + 32);
          goto LABEL_36;
        }
        goto LABEL_37;
      }
    }
    v14 = *v10;
    v15 = *v10 == 2;
    v16 = operator new(0x28u);
    v17 = (__int64)v16;
    if ( v16 )
      v16[8] = 0;
    else
      v17 = 0;
    v18 = *(_QWORD *)((char *)a2 + v13 + 48) / (unsigned __int64)*((unsigned int *)this + 79);
    *(_QWORD *)(v17 + 16) = v18;
    v19 = v18 + *(_QWORD *)((char *)a2 + v13 + 56) / (unsigned __int64)*((unsigned int *)this + 79) - 1;
    *(_QWORD *)(v17 + 24) = v19;
    v20 = *((_QWORD *)this + 72);
    if ( v20 > 0 && v19 >= v20 )
      *(_QWORD *)(v17 + 24) = v20 - 1;
    v21 = *(_DWORD *)(v17 + 24) - *(_DWORD *)(v17 + 16) + 1;
    *(_BYTE *)(v17 + 36) = v15;
    if ( v14 == 2 )
    {
      *((_QWORD *)this + 35) += v21;
      ++*((_DWORD *)this + 141);
    }
    else
    {
      *((_QWORD *)this + 36) += v21;
      ++*((_DWORD *)this + 142);
    }
    *(_DWORD *)(v17 + 32) = v21;
    *(_OWORD *)v17 = *((_OWORD *)a2 + 2 * (int)i + 2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Z_guid_ii(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v21,
        v21,
        (_DWORD)this + 672,
        v17,
        *(_QWORD *)(v17 + 16),
        v21);
    }
    v22 = *((_QWORD *)this + 11);
    if ( !*((_QWORD *)this + 14) )
    {
      v23 = (_DWORD *)((char *)this + 120);
      v24 = *((unsigned int *)this + 30);
      if ( *((_DWORD *)this + 30) )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v24 < 0x18 )
          goto LABEL_43;
        v25 = 24 * v24;
        v23 = (_DWORD *)((char *)this + 120);
      }
      else
      {
        v25 = 0;
      }
      v26 = malloc(v25 + 8);
      if ( !v26 )
LABEL_43:
        ATL::AtlThrowImpl(-2147024882);
      *v26 = *((_QWORD *)this + 13);
      *((_QWORD *)this + 13) = v26;
      v27 = (unsigned int)(*v23 - 1);
      v28 = &v26[2 * v27 + 1 + v27];
      if ( *v23 - 1 >= 0 )
      {
        do
        {
          *v28 = *((_QWORD *)this + 14);
          *((_QWORD *)this + 14) = v28;
          v28 -= 3;
          LODWORD(v27) = v27 - 1;
        }
        while ( (int)v27 >= 0 );
      }
    }
    v29 = (__int64 *)*((_QWORD *)this + 14);
    v30 = *v29;
    v29[2] = v17;
    *((_QWORD *)this + 14) = v30;
    v29[1] = v22;
    *v29 = 0;
    ++*((_QWORD *)this + 12);
    v31 = (__int64 **)*((_QWORD *)this + 11);
    if ( v31 )
      *v31 = v29;
    else
      *((_QWORD *)this + 10) = v29;
    v4 = v32 + 1;
    *((_QWORD *)this + 11) = v29;
    ++v32;
    operator delete(0);
LABEL_36:
    v7 = WPP_GLOBAL_Control;
LABEL_37:
    v6 = *((_DWORD *)a2 + 7);
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
    WPP_SF_DDZ(v7[2], 147, (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, v6, v4, (__int64)this + 672);
}

```

## disassembly

```asm
0x1400166f4  mov     [rsp+arg_10], rbx
0x1400166f9  push    rbp
0x1400166fa  push    rsi
0x1400166fb  push    rdi
0x1400166fc  push    r12
0x1400166fe  push    r13
0x140016700  push    r14
0x140016702  push    r15
0x140016704  sub     rsp, 40h
0x140016708  xor     r12d, r12d
0x14001670b  mov     rbx, rcx
0x14001670e  mov     [rcx+118h], r12
0x140016715  mov     r15, rdx
0x140016718  mov     [rcx+120h], r12
0x14001671f  mov     edi, r12d
0x140016722  mov     [rcx+234h], r12
0x140016729  add     rcx, 50h ; 'P'
0x14001672d  mov     [rsp+78h+arg_0], r12d
0x140016735  call    ?RemoveAll@?$CAtlList@V?$CAutoPtr@VCTierRegion@@@ATL@@V?$CAutoPtrElementTraits@VCTierRegion@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll(void)
0x14001673a  mov     r9d, [r15+1Ch]
0x14001673e  lea     rdx, WPP_GLOBAL_Control
0x140016745  mov     rcx, cs:WPP_GLOBAL_Control
0x14001674c  mov     r13d, r12d
0x14001674f  test    r9d, r9d
0x140016752  jz      loc_1400169E5
0x140016758  mov     rax, [rbx+20h]
0x14001675c  test    rax, rax
0x14001675f  jz      loc_14001698E
0x140016765  mov     rdi, [rax+10h]
0x140016769  lea     rdx, [r15+20h]
0x14001676d  mov     r14, [rax]
0x140016770  mov     r8d, 10h; Length
0x140016776  movsxd  rbp, r13d
0x140016779  mov     rsi, rbp
0x14001677c  shl     rsi, 5
0x140016780  lea     rcx, [rdi+204h]; Source1
0x140016787  add     rdx, rsi; Source2
0x14001678a  call    cs:__imp_RtlCompareMemory
0x140016790  cmp     rax, 10h
0x140016794  jz      short loc_1400167B8
0x140016796  mov     rax, r14
0x140016799  test    r14, r14
0x14001679c  jnz     short loc_140016765
0x14001679e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400167a5  lea     rdx, WPP_GLOBAL_Control
0x1400167ac  mov     edi, [rsp+78h+arg_0]
0x1400167b3  jmp     loc_140016991
0x1400167b8  mov     r14d, [rdi]
0x1400167bb  mov     ecx, 28h ; '('; Size
0x1400167c0  cmp     r14d, 2
0x1400167c4  setz    r12b
0x1400167c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400167cd  mov     [rsp+78h+arg_8], rax
0x1400167d5  mov     rdi, rax
0x1400167d8  test    rax, rax
0x1400167db  jz      short loc_1400167E6
0x1400167dd  mov     dword ptr [rax+20h], 0
0x1400167e4  jmp     short loc_1400167E8
0x1400167e6  xor     edi, edi
0x1400167e8  mov     ecx, [rbx+13Ch]
0x1400167ee  xor     edx, edx
0x1400167f0  mov     rax, [rsi+r15+30h]
0x1400167f5  div     rcx
0x1400167f8  xor     edx, edx
0x1400167fa  mov     r8, rax
0x1400167fd  mov     [rdi+10h], rax
0x140016801  mov     ecx, [rbx+13Ch]
0x140016807  mov     rax, [rsi+r15+38h]
0x14001680c  div     rcx
0x14001680f  lea     rcx, [rax-1]
0x140016813  add     rcx, r8
0x140016816  mov     [rdi+18h], rcx
0x14001681a  mov     rax, [rbx+240h]
0x140016821  test    rax, rax
0x140016824  jle     short loc_140016832
0x140016826  cmp     rcx, rax
0x140016829  jb      short loc_140016832
0x14001682b  dec     rax
0x14001682e  mov     [rdi+18h], rax
0x140016832  mov     r8d, [rdi+18h]
0x140016836  sub     r8d, [rdi+10h]
0x14001683a  inc     r8d
0x14001683d  mov     [rdi+24h], r12b
0x140016841  mov     edx, r8d
0x140016844  cmp     r14d, 2
0x140016848  jnz     short loc_140016859
0x14001684a  add     [rbx+118h], rdx
0x140016851  inc     dword ptr [rbx+234h]
0x140016857  jmp     short loc_140016866
0x140016859  add     [rbx+120h], rdx
0x140016860  inc     dword ptr [rbx+238h]
0x140016866  lea     rax, [rbp+1]
0x14001686a  mov     [rdi+20h], r8d
0x14001686e  shl     rax, 5
0x140016872  movups  xmm0, xmmword ptr [rax+r15]
0x140016877  movdqu  xmmword ptr [rdi], xmm0
0x14001687b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016882  lea     rax, WPP_GLOBAL_Control
0x140016889  cmp     rcx, rax
0x14001688c  jz      short loc_1400168BD
0x14001688e  test    byte ptr [rcx+1Ch], 1
0x140016892  jz      short loc_1400168BD
0x140016894  cmp     byte ptr [rcx+19h], 4
0x140016898  jb      short loc_1400168BD
0x14001689a  mov     rax, [rdi+10h]
0x14001689e  lea     r9, [rbx+2A0h]
0x1400168a5  mov     rcx, [rcx+10h]
0x1400168a9  mov     [rsp+78h+var_48], rdx
0x1400168ae  mov     [rsp+78h+var_50], rax
0x1400168b3  mov     [rsp+78h+var_58], rdi
0x1400168b8  call    WPP_SF_Z_guid_ii
0x1400168bd  mov     rbp, [rbx+58h]
0x1400168c1  xor     r12d, r12d
0x1400168c4  cmp     [rbx+70h], r12
0x1400168c8  jnz     short loc_140016945
0x1400168ca  lea     rsi, [rbx+78h]
0x1400168ce  mov     ecx, [rsi]
0x1400168d0  test    rcx, rcx
0x1400168d3  jnz     short loc_1400168DA
0x1400168d5  mov     ecx, r12d
0x1400168d8  jmp     short loc_1400168F9
0x1400168da  xor     edx, edx
0x1400168dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400168e0  div     rcx
0x1400168e3  cmp     rax, 18h
0x1400168e7  jb      loc_140016A33
0x1400168ed  lea     rcx, [rcx+rcx*2]
0x1400168f1  shl     rcx, 3
0x1400168f5  lea     rsi, [rbx+78h]
0x1400168f9  add     rcx, 8; Size
0x1400168fd  call    cs:__imp_malloc
0x140016903  test    rax, rax
0x140016906  jz      loc_140016A33
0x14001690c  mov     rcx, [rbx+68h]
0x140016910  mov     [rax], rcx
0x140016913  mov     [rbx+68h], rax
0x140016917  mov     r8d, [rsi]
0x14001691a  sub     r8d, 1
0x14001691e  lea     rcx, ds:1[r8*2]
0x140016926  lea     rcx, [rcx+r8]
0x14001692a  lea     rcx, [rax+rcx*8]
0x14001692e  js      short loc_140016945
0x140016930  mov     rax, [rbx+70h]
0x140016934  mov     [rcx], rax
0x140016937  mov     [rbx+70h], rcx
0x14001693b  sub     rcx, 18h
0x14001693f  sub     r8d, 1
0x140016943  jns     short loc_140016930
0x140016945  mov     rcx, [rbx+70h]
0x140016949  mov     rax, [rcx]
0x14001694c  mov     [rcx+10h], rdi
0x140016950  mov     [rbx+70h], rax
0x140016954  mov     [rcx+8], rbp
0x140016958  mov     [rcx], r12
0x14001695b  inc     qword ptr [rbx+60h]
0x14001695f  mov     rax, [rbx+58h]
0x140016963  test    rax, rax
0x140016966  jz      short loc_14001696D
0x140016968  mov     [rax], rcx
0x14001696b  jmp     short loc_140016971
0x14001696d  mov     [rbx+50h], rcx
0x140016971  mov     edi, [rsp+78h+arg_0]
0x140016978  inc     edi
0x14001697a  mov     [rbx+58h], rcx
0x14001697e  xor     ecx, ecx; Block
0x140016980  mov     [rsp+78h+arg_0], edi
0x140016987  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001698c  jmp     short loc_1400169C7
0x14001698e  movsxd  rbp, r13d
0x140016991  cmp     rcx, rdx
0x140016994  jz      short loc_1400169D5
0x140016996  test    byte ptr [rcx+1Ch], 1
0x14001699a  jz      short loc_1400169D5
0x14001699c  cmp     byte ptr [rcx+19h], 2
0x1400169a0  jb      short loc_1400169D5
0x1400169a2  mov     rcx, [rcx+10h]
0x1400169a6  lea     rax, [rbp+1]
0x1400169aa  shl     rax, 5
0x1400169ae  lea     r9, [rbx+2A0h]
0x1400169b5  add     rax, r15
0x1400169b8  mov     edx, 91h
0x1400169bd  mov     [rsp+78h+var_58], rax
0x1400169c2  call    WPP_SF_Z_guid_
0x1400169c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400169ce  lea     rdx, WPP_GLOBAL_Control
0x1400169d5  mov     r9d, [r15+1Ch]
0x1400169d9  inc     r13d
0x1400169dc  cmp     r13d, r9d
0x1400169df  jb      loc_140016758
0x1400169e5  cmp     rcx, rdx
0x1400169e8  jz      short loc_140016A1B
0x1400169ea  test    byte ptr [rcx+1Ch], 1
0x1400169ee  jz      short loc_140016A1B
0x1400169f0  cmp     byte ptr [rcx+19h], 4
0x1400169f4  jb      short loc_140016A1B
0x1400169f6  mov     rcx, [rcx+10h]
0x1400169fa  lea     rax, [rbx+2A0h]
0x140016a01  mov     [rsp+78h+var_50], rax
0x140016a06  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140016a0d  mov     edx, 93h
0x140016a12  mov     dword ptr [rsp+78h+var_58], edi
0x140016a16  call    WPP_SF_DDZ
0x140016a1b  mov     rbx, [rsp+78h+arg_10]
0x140016a23  add     rsp, 40h
0x140016a27  pop     r15
0x140016a29  pop     r14
0x140016a2b  pop     r13
0x140016a2d  pop     r12
0x140016a2f  pop     rdi
0x140016a30  pop     rsi
0x140016a31  pop     rbp
0x140016a32  retn
0x140016a33  mov     ecx, 8007000Eh; int
0x140016a38  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
