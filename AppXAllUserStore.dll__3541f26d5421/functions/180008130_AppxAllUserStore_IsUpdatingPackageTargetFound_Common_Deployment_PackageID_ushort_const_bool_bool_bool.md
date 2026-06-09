# AppxAllUserStore::IsUpdatingPackageTargetFound(Common::Deployment::PackageID *,ushort const *,bool,bool,bool *)

- ea: `0x180008130`
- end: `0x180008542`
- name: `?IsUpdatingPackageTargetFound@AppxAllUserStore@@YAJPEAVPackageID@Deployment@Common@@PEBG_N2PEA_N@Z`
- size: `1042`
- prototype: `int(AppxAllUserStore *__hidden this, struct Common::Deployment::PackageID *, const unsigned __int16 *, bool, bool, bool *)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026b64`
- `0x180028528`
- `0x18002886c`
- `0x180029648`

## callees

- `0x180006870`
- `0x180008130`
- `0x180008550`
- `0x18000a600`
- `0x180017f50`
- `0x180018248`
- `0x18001a604`
- `0x18004c9d0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000839c`
- `ntdll!RtlFreeHeap` at `0x1800083b4`
- `ntdll!RtlFreeHeap` at `0x1800083cd`
- `ntdll!RtlFreeHeap` at `0x1800083e4`
- `ntdll!RtlFreeHeap` at `0x18000839c`
- `ntdll!RtlFreeHeap` at `0x1800083b4`
- `ntdll!RtlFreeHeap` at `0x1800083cd`
- `ntdll!RtlFreeHeap` at `0x1800083e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000832c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008357`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000832c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008357`

## string_xrefs

- `0x180008495`: `onecore\admin\appmodel\common\packagefullnameutilities.cpp`
- `0x1800084ba`: `onecore\admin\appmodel\common\packagefullnameutilities.cpp`
- `0x1800082bc`: `onecore\admin\appmodel\common\PackageID.inl`
- `0x180008414`: `onecore\admin\appmodel\common\PackageID.inl`
- `0x180008434`: `onecore\admin\appmodel\common\PackageID.inl`
- `0x180008475`: `onecore\admin\appmodel\common\PackageID.inl`
- `0x180008501`: `onecore\admin\appmodel\common\PackageID.inl`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::IsUpdatingPackageTargetFound(
        AppxAllUserStore *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        char a4,
        _BYTE *a5)
{
  char v5; // si
  char v6; // r14
  unsigned int v8; // eax
  unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // r8d
  int v12; // ebx
  unsigned __int16 *v13; // rsi
  int v14; // r14d
  unsigned __int16 *v15; // rdi
  int v16; // eax
  __int64 v17; // rcx
  unsigned __int16 *v18; // rax
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rcx
  unsigned __int16 *v22; // rax
  int v23; // eax
  WCHAR *v24; // rdi
  WCHAR *v25; // rbx
  int v27; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  char v30; // [rsp+31h] [rbp-CFh]
  unsigned int v31[3]; // [rsp+34h] [rbp-CCh] BYREF
  LPCWCH lpString2[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v34; // [rsp+58h] [rbp-A8h]
  PVOID v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+70h] [rbp-90h]
  int v37; // [rsp+78h] [rbp-88h]
  PVOID P[2]; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+90h] [rbp-70h]
  LPCWCH v40[2]; // [rsp+98h] [rbp-68h] BYREF
  int v41; // [rsp+A8h] [rbp-58h]
  char v42[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v43; // [rsp+B4h] [rbp-4Ch]
  unsigned __int64 v44; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *Src; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v46; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v47; // [rsp+D8h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v5 = a4;
  v30 = (char)a3;
  v6 = (char)a3;
  v33 = 0;
  v36 = 0;
  v39 = 0;
  v41 = 0;
  v34 = 0;
  v37 = 11;
  *(_OWORD *)lpString2 = 0;
  v31[0] = 240;
  *(_OWORD *)v35 = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)v40 = 0;
  v8 = ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageIdBasicFromFullName(
         a2,
         (__int64)a2,
         v31,
         (__int64)v42);
  if ( v8 )
  {
    v27 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x22,
            (unsigned int)"onecore\\admin\\appmodel\\common\\packagefullnameutilities.cpp",
            (const char *)v8,
            bIgnoreCase);
    v12 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\admin\\appmodel\\common\\packagefullnameutilities.cpp",
        (const char *)(unsigned int)v27,
        bIgnoreCase);
      goto LABEL_49;
    }
  }
  if ( !Src )
  {
    v12 = -2147024809;
LABEL_46:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x18,
      (int)"onecore\\admin\\appmodel\\common\\PackageID.inl",
      (const char *)(unsigned int)v12);
    goto LABEL_26;
  }
  v9 = Src;
  v10 = 0x3FFFFFFF;
  while ( *v9 )
  {
    ++v9;
    if ( !--v10 )
    {
      v11 = 0;
      v12 = -2147024809;
      goto LABEL_8;
    }
  }
  v12 = 0;
  v11 = 0x3FFFFFFF - v10;
LABEL_8:
  if ( v12 < 0 )
    goto LABEL_46;
  v13 = v47;
  v14 = v43;
  v15 = v46;
  v16 = Common::StringBuffer::SetValue((Common::StringBuffer *)lpString2, Src, v11);
  v12 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19,
      (int)"onecore\\admin\\appmodel\\common\\PackageID.inl",
      (const char *)(unsigned int)v16);
    goto LABEL_25;
  }
  v34 = v44;
  if ( v15 && *v15 )
  {
    v17 = 0x3FFFFFFF;
    v18 = v15;
    while ( *v18 )
    {
      ++v18;
      if ( !--v17 )
      {
        v19 = 31;
LABEL_23:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v19,
          (int)"onecore\\admin\\appmodel\\common\\PackageID.inl",
          (const char *)0x80070057LL);
        v12 = -2147024809;
        goto LABEL_51;
      }
    }
    v20 = Common::StringBuffer::SetValue((Common::StringBuffer *)v35, v15, 0x3FFFFFFF - (int)v17);
    v12 = v20;
    if ( v20 >= 0 )
      goto LABEL_17;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20,
      (int)"onecore\\admin\\appmodel\\common\\PackageID.inl",
      (const char *)(unsigned int)v20);
    v5 = a4;
    v6 = v30;
    goto LABEL_26;
  }
LABEL_17:
  v37 = v14;
  if ( !v13 || !*v13 )
    goto LABEL_25;
  v21 = 0x3FFFFFFF;
  v22 = v13;
  while ( *v22 )
  {
    ++v22;
    if ( !--v21 )
    {
      v19 = 45;
      goto LABEL_23;
    }
  }
  v23 = Common::StringBuffer::SetValue((Common::StringBuffer *)v40, v13, 0x3FFFFFFF - (int)v21);
  v12 = v23;
  if ( v23 >= 0 )
  {
LABEL_25:
    v5 = a4;
    v6 = v30;
    goto LABEL_26;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x2E,
    (int)"onecore\\admin\\appmodel\\common\\PackageID.inl",
    (const char *)(unsigned int)v23);
LABEL_51:
  v5 = a4;
  v6 = v30;
LABEL_26:
  if ( v12 >= 0 )
  {
    v24 = (WCHAR *)lpString2[1];
    if ( CompareStringOrdinal(*((LPCWCH *)this + 1), -1, lpString2[1], -1, 1) == 2
      && (v25 = (WCHAR *)v40[1], CompareStringOrdinal(*((LPCWCH *)this + 12), -1, v40[1], -1, 1) == 2)
      && (!v6 || *((_DWORD *)this + 14) == v37) )
    {
      if ( !v5 && *((_QWORD *)this + 3) <= v34 )
      {
        *a5 = 0;
        if ( v25 )
          RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v25);
        if ( P[1] )
          RtlFreeHeap(ReservedForLocalUse::g_heap, 0, P[1]);
        if ( v35[1] )
          RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v35[1]);
        if ( v24 )
          RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v24);
        return 0;
      }
      *a5 = 1;
    }
    else
    {
      *a5 = 0;
    }
    Common::Deployment::PackageID::~PackageID((Common::Deployment::PackageID *)lpString2);
    return 0;
  }
LABEL_49:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x22F,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
    (const char *)(unsigned int)v12,
    bIgnoreCase);
  Common::Deployment::PackageID::~PackageID((Common::Deployment::PackageID *)lpString2);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180008130  push    rbp
0x180008132  push    rbx
0x180008133  push    rsi
0x180008134  push    rdi
0x180008135  push    r12
0x180008137  push    r13
0x180008139  push    r14
0x18000813b  lea     rbp, [rsp-0B0h]
0x180008143  sub     rsp, 1B0h
0x18000814a  mov     rax, cs:__security_cookie
0x180008151  xor     rax, rsp
0x180008154  mov     [rbp+0E0h+var_40], rax
0x18000815b  mov     r12, qword ptr [rbp+0E0h+arg_20]
0x180008162  xorps   xmm0, xmm0
0x180008165  xor     edi, edi
0x180008167  mov     [rsp+1E0h+var_1B0], r9b
0x18000816c  movzx   esi, r9b
0x180008170  mov     [rsp+1E0h+var_1AF], r8b
0x180008175  movzx   r14d, r8b
0x180008179  mov     [rsp+1E0h+var_190], edi
0x18000817d  mov     r13, rcx
0x180008180  mov     [rsp+1E0h+var_170], edi
0x180008184  xor     eax, eax
0x180008186  mov     [rbp+0E0h+var_150], edi
0x180008189  lea     r9, [rbp+0E0h+var_130]
0x18000818d  mov     [rbp+0E0h+var_138], edi
0x180008190  lea     r8, [rsp+1E0h+var_1AC]
0x180008195  mov     [rsp+1E0h+var_188], rax
0x18000819a  mov     rcx, rdx; lpString1
0x18000819d  mov     [rsp+1E0h+var_168], 0Bh
0x1800081a5  movups  xmmword ptr [rsp+1E0h+lpString2], xmm0
0x1800081aa  mov     [rsp+1E0h+var_1AC], 0F0h
0x1800081b2  movups  xmmword ptr [rsp+1E0h+var_180], xmm0
0x1800081b7  movups  xmmword ptr [rbp+0E0h+P], xmm0
0x1800081bb  movups  xmmword ptr [rbp+0E0h+var_148], xmm0
0x1800081bf  call    ?PackageIdBasicFromFullName@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBGIPEAIPEAE@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageIdBasicFromFullName(ushort const *,uint,uint *,uchar *)
0x1800081c4  test    eax, eax
0x1800081c6  jnz     loc_18000848E
0x1800081cc  mov     rdx, [rbp+0E0h+Src]; Src
0x1800081d0  mov     [rsp+1E0h+arg_10], r15
0x1800081d8  test    rdx, rdx
0x1800081db  jz      loc_180008469
0x1800081e1  mov     r15d, 3FFFFFFFh
0x1800081e7  mov     rax, rdx
0x1800081ea  mov     ecx, r15d
0x1800081ed  nop     dword ptr [rax]
0x1800081f0  cmp     [rax], di
0x1800081f3  jz      short loc_180008209
0x1800081f5  add     rax, 2
0x1800081f9  sub     rcx, 1
0x1800081fd  jnz     short loc_1800081F0
0x1800081ff  mov     r8, rdi
0x180008202  mov     ebx, 80070057h
0x180008207  jmp     short loc_180008211
0x180008209  mov     r8, r15
0x18000820c  mov     ebx, edi
0x18000820e  sub     r8, rcx; unsigned int
0x180008211  test    ebx, ebx
0x180008213  js      loc_18000846E
0x180008219  mov     rsi, [rbp+0E0h+var_108]
0x18000821d  lea     rcx, [rsp+1E0h+lpString2]; this
0x180008222  mov     r14d, [rbp+0E0h+var_12C]
0x180008226  mov     rdi, [rbp+0E0h+var_110]
0x18000822a  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18000822f  mov     ebx, eax
0x180008231  test    eax, eax
0x180008233  js      loc_18000840D
0x180008239  mov     rax, [rbp+0E0h+var_128]
0x18000823d  mov     [rsp+1E0h+var_188], rax
0x180008242  test    rdi, rdi
0x180008245  jz      short loc_180008287
0x180008247  cmp     word ptr [rdi], 0
0x18000824b  jz      short loc_180008287
0x18000824d  mov     rcx, r15
0x180008250  mov     rax, rdi
0x180008253  cmp     word ptr [rax], 0
0x180008257  jz      short loc_18000826A
0x180008259  add     rax, 2
0x18000825d  sub     rcx, 1
0x180008261  jnz     short loc_180008253
0x180008263  mov     edx, 1Fh
0x180008268  jmp     short loc_1800082B5
0x18000826a  mov     r8d, r15d
0x18000826d  mov     rdx, rdi; Src
0x180008270  sub     r8d, ecx; unsigned int
0x180008273  lea     rcx, [rsp+1E0h+var_180]; this
0x180008278  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18000827d  mov     ebx, eax
0x18000827f  test    eax, eax
0x180008281  js      loc_18000842D
0x180008287  mov     [rsp+1E0h+var_168], r14d
0x18000828c  test    rsi, rsi
0x18000828f  jz      short loc_1800082F4
0x180008291  cmp     word ptr [rsi], 0
0x180008295  jz      short loc_1800082F4
0x180008297  mov     rcx, r15
0x18000829a  mov     rax, rsi
0x18000829d  nop     dword ptr [rax]
0x1800082a0  cmp     word ptr [rax], 0
0x1800082a4  jz      short loc_1800082D8
0x1800082a6  add     rax, 2
0x1800082aa  sub     rcx, 1
0x1800082ae  jnz     short loc_1800082A0
0x1800082b0  mov     edx, 2Dh ; '-'; void *
0x1800082b5  mov     rcx, [rbp+0E8h]; this
0x1800082bc  lea     r8, aOnecoreAdminAp_27; "onecore\\admin\\appmodel\\common\\Packa"...
0x1800082c3  mov     r9d, 80070057h; char *
0x1800082c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800082ce  mov     ebx, 80070057h
0x1800082d3  jmp     loc_180008515
0x1800082d8  sub     r15d, ecx
0x1800082db  mov     rdx, rsi; Src
0x1800082de  mov     r8d, r15d; unsigned int
0x1800082e1  lea     rcx, [rbp+0E0h+var_148]; this
0x1800082e5  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x1800082ea  mov     ebx, eax
0x1800082ec  test    eax, eax
0x1800082ee  js      loc_1800084FA
0x1800082f4  movzx   esi, [rsp+1E0h+var_1B0]
0x1800082f9  movzx   r14d, [rsp+1E0h+var_1AF]
0x1800082ff  mov     r15, [rsp+1E0h+arg_10]
0x180008307  test    ebx, ebx
0x180008309  js      loc_1800084CE
0x18000830f  mov     rdi, [rsp+1E0h+lpString2+8]
0x180008314  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000831a  mov     rcx, [r13+8]; lpString1
0x18000831e  mov     r8, rdi; lpString2
0x180008321  mov     edx, r9d; cchCount1
0x180008324  mov     [rsp+1E0h+bIgnoreCase], 1; bIgnoreCase
0x18000832c  call    cs:__imp_CompareStringOrdinal
0x180008332  cmp     eax, 2
0x180008335  jnz     loc_180008458
0x18000833b  mov     rbx, [rbp+0E0h+var_148+8]
0x18000833f  mov     r9d, 0FFFFFFFFh; cchCount2
0x180008345  mov     rcx, [r13+60h]; lpString1
0x180008349  mov     r8, rbx; lpString2
0x18000834c  mov     edx, r9d; cchCount1
0x18000834f  mov     [rsp+1E0h+bIgnoreCase], 1; bIgnoreCase
0x180008357  call    cs:__imp_CompareStringOrdinal
0x18000835d  cmp     eax, 2
0x180008360  jnz     loc_180008458
0x180008366  test    r14b, r14b
0x180008369  jnz     loc_180008525
0x18000836f  test    sil, sil
0x180008372  jnz     loc_180008538
0x180008378  mov     rax, [rsp+1E0h+var_188]
0x18000837d  cmp     [r13+18h], rax
0x180008381  ja      loc_180008538
0x180008387  mov     [r12], sil
0x18000838b  test    rbx, rbx
0x18000838e  jz      short loc_1800083A2
0x180008390  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x180008397  mov     r8, rbx; P
0x18000839a  xor     edx, edx; Flags
0x18000839c  call    cs:__imp_RtlFreeHeap
0x1800083a2  mov     r8, [rbp+0E0h+P+8]; P
0x1800083a6  test    r8, r8
0x1800083a9  jz      short loc_1800083BA
0x1800083ab  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x1800083b2  xor     edx, edx; Flags
0x1800083b4  call    cs:__imp_RtlFreeHeap
0x1800083ba  mov     r8, [rsp+1E0h+var_180+8]; P
0x1800083bf  test    r8, r8
0x1800083c2  jz      short loc_1800083D3
0x1800083c4  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x1800083cb  xor     edx, edx; Flags
0x1800083cd  call    cs:__imp_RtlFreeHeap
0x1800083d3  test    rdi, rdi
0x1800083d6  jz      short loc_1800083EA
0x1800083d8  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x1800083df  mov     r8, rdi; P
0x1800083e2  xor     edx, edx; Flags
0x1800083e4  call    cs:__imp_RtlFreeHeap
0x1800083ea  xor     eax, eax
0x1800083ec  mov     rcx, [rbp+0E0h+var_40]
0x1800083f3  xor     rcx, rsp; StackCookie
0x1800083f6  call    __security_check_cookie
0x1800083fb  add     rsp, 1B0h
0x180008402  pop     r14
0x180008404  pop     r13
0x180008406  pop     r12
0x180008408  pop     rdi
0x180008409  pop     rsi
0x18000840a  pop     rbx
0x18000840b  pop     rbp
0x18000840c  retn
0x18000840d  mov     rcx, [rbp+0E8h]; this
0x180008414  lea     r8, aOnecoreAdminAp_27; "onecore\\admin\\appmodel\\common\\Packa"...
0x18000841b  mov     r9d, eax; char *
0x18000841e  mov     edx, 19h; void *
0x180008423  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008428  jmp     loc_1800082F4
0x18000842d  mov     rcx, [rbp+0E8h]; this
0x180008434  lea     r8, aOnecoreAdminAp_27; "onecore\\admin\\appmodel\\common\\Packa"...
0x18000843b  mov     r9d, eax; char *
0x18000843e  mov     edx, 20h ; ' '; void *
0x180008443  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008448  movzx   esi, [rsp+1E0h+var_1B0]
0x18000844d  movzx   r14d, [rsp+1E0h+var_1AF]
0x180008453  jmp     loc_1800082FF
0x180008458  mov     byte ptr [r12], 0
0x18000845d  lea     rcx, [rsp+1E0h+lpString2]; this
0x180008462  call    ??1PackageID@Deployment@Common@@QEAA@XZ; Common::Deployment::PackageID::~PackageID(void)
0x180008467  jmp     short loc_1800083EA
0x180008469  mov     ebx, 80070057h
0x18000846e  mov     rcx, [rbp+0E8h]; this
0x180008475  lea     r8, aOnecoreAdminAp_27; "onecore\\admin\\appmodel\\common\\Packa"...
0x18000847c  mov     r9d, ebx; char *
0x18000847f  mov     edx, 18h; void *
0x180008484  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008489  jmp     loc_1800082FF
0x18000848e  mov     rcx, [rbp+0E8h]; this
0x180008495  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\common\\packa"...
0x18000849c  mov     r9d, eax; char *
0x18000849f  mov     edx, 22h ; '"'; void *
0x1800084a4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800084a9  mov     ebx, eax
0x1800084ab  test    eax, eax
0x1800084ad  jns     loc_1800081CC
0x1800084b3  mov     rcx, [rbp+0E8h]; this
0x1800084ba  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\common\\packa"...
0x1800084c1  mov     r9d, eax; char *
0x1800084c4  mov     edx, 5Dh ; ']'; void *
0x1800084c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084ce  mov     rcx, [rbp+0E8h]; this
0x1800084d5  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800084dc  mov     r9d, ebx; char *
0x1800084df  mov     edx, 22Fh; void *
0x1800084e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084e9  lea     rcx, [rsp+1E0h+lpString2]; this
0x1800084ee  call    ??1PackageID@Deployment@Common@@QEAA@XZ; Common::Deployment::PackageID::~PackageID(void)
0x1800084f3  mov     eax, ebx
0x1800084f5  jmp     loc_1800083EC
0x1800084fa  mov     rcx, [rbp+0E8h]; this
0x180008501  lea     r8, aOnecoreAdminAp_27; "onecore\\admin\\appmodel\\common\\Packa"...
0x180008508  mov     r9d, eax; char *
0x18000850b  mov     edx, 2Eh ; '.'; void *
0x180008510  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008515  movzx   esi, [rsp+1E0h+var_1B0]
0x18000851a  movzx   r14d, [rsp+1E0h+var_1AF]
0x180008520  jmp     loc_1800082FF
0x180008525  mov     eax, [rsp+1E0h+var_168]
0x180008529  cmp     [r13+38h], eax
0x18000852d  jnz     loc_180008458
0x180008533  jmp     loc_18000836F
0x180008538  mov     byte ptr [r12], 1
0x18000853d  jmp     loc_18000845D
```
