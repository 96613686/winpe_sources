# CClassAccess::EnumPackages(ushort const *,_GUID *,unsigned __int64 *,ulong,IEnumPackage * *)

- ea: `0x18001ddc0`
- end: `0x18001e0ef`
- name: `?EnumPackages@CClassAccess@@UEAAJPEBGPEAU_GUID@@PEA_KKPEAPEAUIEnumPackage@@@Z`
- size: `815`
- prototype: `__int64 __fastcall(CClassAccess *__hidden this, const unsigned __int16 *, struct _GUID *, unsigned __int64 *, unsigned int, struct IEnumPackage **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800016f4`
- `0x18001ddc0`
- `0x18001e2ec`
- `0x18002811c`
- `0x180028c90`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001de8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dfb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001de8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dfb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dec3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dfd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e010`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dec3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dfd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e010`

## pseudocode

```c
__int64 __fastcall CClassAccess::EnumPackages(
        CClassAccess *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        unsigned __int64 *a4,
        unsigned int a5,
        struct IEnumPackage **a6)
{
  int v6; // edi
  void *v7; // r12
  unsigned __int64 v9; // rax
  int UserClassStores; // eax
  unsigned int *v11; // rbx
  SIZE_T v12; // rax
  _QWORD *v13; // r15
  unsigned int v14; // ecx
  __int64 v15; // r14
  struct IClassAccess *NextValidClassStore; // rax
  struct IClassAccess *v17; // r13
  unsigned __int64 v18; // rcx
  _QWORD *v19; // rbx
  HLOCAL v20; // rax
  __int64 i; // r8
  __int64 (__fastcall **v22)(HLOCAL, GUID *, struct IEnumPackage **); // rax
  __int64 v23; // r12
  int v24; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v25; // [rsp+44h] [rbp-34h] BYREF
  int v26; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int64 *v27; // [rsp+50h] [rbp-28h]
  void *v28; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int64 v29; // [rsp+60h] [rbp-18h]
  unsigned __int64 v30; // [rsp+68h] [rbp-10h] BYREF

  v6 = 0;
  v7 = 0;
  v24 = 0;
  v30 = 0;
  v26 = 0;
  v28 = 0;
  if ( a5 != 1 && a5 != 2 && a5 != 3 && a5 != 4 && a5 - 5 >= 2 )
    return 2147942487LL;
  if ( a4 )
  {
    v9 = *a4;
    v27 = &v30;
    v30 = v9;
  }
  else
  {
    v27 = 0;
  }
  UserClassStores = 0;
  v11 = (unsigned int *)((char *)this + 16);
  if ( !*((_QWORD *)this + 1) )
  {
    UserClassStores = GetUserClassStores(
                        *((const unsigned __int16 **)this + 3),
                        (struct tagCLASSCONTAINER ***)this + 1,
                        v11,
                        &v26,
                        &v28);
    v7 = v28;
    v6 = UserClassStores;
    v24 = UserClassStores;
  }
  *a6 = 0;
  if ( UserClassStores )
  {
    if ( UserClassStores < 0 )
      goto LABEL_15;
  }
  else if ( !*v11 )
  {
    UserClassStores = -2147221144;
LABEL_15:
    v6 = UserClassStores;
    goto LABEL_16;
  }
  v12 = 8LL * *v11;
  if ( !is_mul_ok(*v11, 8u) )
    v12 = -1;
  v13 = LocalAlloc(0, v12);
  if ( !v13 )
  {
    v6 = -2147024882;
LABEL_16:
    if ( v7 )
      LocalFree(v7);
    return (unsigned int)v6;
  }
  v14 = *v11;
  v15 = 0;
  v29 = 0;
  v25 = 0;
  if ( !v14 )
  {
    v17 = 0;
LABEL_35:
    if ( v6 < 0 )
      goto LABEL_52;
    v19 = LocalAlloc(0, 0x20u);
    if ( v19 )
    {
      v19[1] = 0;
      *v19 = &CMergedEnumPackage::`vftable';
      v19[2] = 0;
      *((_DWORD *)v19 + 6) = 0;
      v20 = LocalAlloc(0, 8LL * (unsigned int)v15);
      v19[1] = v20;
      if ( v20 )
      {
        for ( i = 0; (unsigned int)i < (unsigned int)v15; i = (unsigned int)(i + 1) )
          *(_QWORD *)(v19[1] + 8 * i) = v13[i];
        v22 = (__int64 (__fastcall **)(HLOCAL, GUID *, struct IEnumPackage **))*v19;
        *((_DWORD *)v19 + 4) = v15;
        v6 = (*v22)(v19, &IID_IEnumPackage, a6);
        if ( v6 >= 0 )
          goto LABEL_49;
        goto LABEL_48;
      }
    }
    else
    {
      v19 = 0;
    }
    v6 = -2147024882;
    if ( (_DWORD)v15 )
    {
      v23 = 0;
      do
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[v23] + 16LL))(v13[v23]);
        v23 = (unsigned int)(v23 + 1);
      }
      while ( (unsigned int)v23 < (unsigned int)v15 );
      v7 = v28;
    }
    if ( !v19 )
      goto LABEL_49;
LABEL_48:
    CMergedEnumPackage::~CMergedEnumPackage((CMergedEnumPackage *)v19);
    operator delete(v19);
LABEL_49:
    if ( a4 && v29 > *a4 )
      *a4 = v29;
LABEL_52:
    if ( v7 )
      LocalFree(v7);
    LocalFree(v13);
    if ( v17 )
      (*(void (__fastcall **)(struct IClassAccess *))(*(_QWORD *)v17 + 16LL))(v17);
    return (unsigned int)v6;
  }
  while ( 1 )
  {
    NextValidClassStore = GetNextValidClassStore(
                            *((struct tagCLASSCONTAINER ***)this + 1),
                            v14,
                            v7,
                            *((void **)this + 4),
                            0,
                            v26,
                            &v25,
                            &v24);
    v17 = NextValidClassStore;
    if ( !NextValidClassStore )
      break;
    v24 = (*(__int64 (__fastcall **)(struct IClassAccess *, const unsigned __int16 *, struct _GUID *, unsigned __int64 *, unsigned int, _QWORD *))(*(_QWORD *)NextValidClassStore + 32LL))(
            NextValidClassStore,
            a2,
            a3,
            v27,
            a5,
            &v13[v15]);
    v6 = v24;
    if ( v24 >= 0 )
    {
      if ( v27 )
      {
        v18 = *v27;
        if ( v29 >= *v27 )
          v18 = v29;
        v29 = v18;
        *v27 = *a4;
      }
      v15 = (unsigned int)(v15 + 1);
      (*(void (__fastcall **)(struct IClassAccess *))(*(_QWORD *)v17 + 16LL))(v17);
      v17 = 0;
      v14 = *v11;
      if ( ++v25 < v14 )
        continue;
    }
    goto LABEL_35;
  }
  LocalFree(v13);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18001ddc0  mov     rax, rsp
0x18001ddc3  mov     [rax+20h], r9
0x18001ddc7  mov     [rax+18h], r8
0x18001ddcb  mov     [rax+10h], rdx
0x18001ddcf  mov     [rax+8], rcx
0x18001ddd3  push    rbp
0x18001ddd4  push    rbx
0x18001ddd5  push    rsi
0x18001ddd6  push    rdi
0x18001ddd7  push    r12
0x18001ddd9  push    r13
0x18001dddb  push    r14
0x18001dddd  push    r15
0x18001dddf  mov     rbp, rsp
0x18001dde2  sub     rsp, 78h
0x18001dde6  mov     eax, [rbp+arg_20]
0x18001dde9  xor     edi, edi
0x18001ddeb  xor     r12d, r12d
0x18001ddee  mov     [rbp+var_38], edi
0x18001ddf1  mov     [rbp+var_10], rdi
0x18001ddf5  mov     [rbp+var_30], edi
0x18001ddf8  mov     [rbp+var_20], r12
0x18001ddfc  sub     eax, 1
0x18001ddff  jz      short loc_18001DE21
0x18001de01  sub     eax, 1
0x18001de04  jz      short loc_18001DE21
0x18001de06  sub     eax, 1
0x18001de09  jz      short loc_18001DE21
0x18001de0b  sub     eax, 1
0x18001de0e  jz      short loc_18001DE21
0x18001de10  sub     eax, 1
0x18001de13  jz      short loc_18001DE21
0x18001de15  cmp     eax, 1
0x18001de18  jz      short loc_18001DE21
0x18001de1a  mov     eax, 80070057h
0x18001de1f  jmp     short loc_18001DE96
0x18001de21  test    r9, r9
0x18001de24  jz      short loc_18001DE37
0x18001de26  mov     rax, [r9]
0x18001de29  lea     rdx, [rbp+var_10]
0x18001de2d  mov     [rbp+var_28], rdx
0x18001de31  mov     [rbp+var_10], rax
0x18001de35  jmp     short loc_18001DE3B
0x18001de37  mov     [rbp+var_28], rdi
0x18001de3b  lea     rdx, [rcx+8]; struct tagCLASSCONTAINER ***
0x18001de3f  xor     eax, eax
0x18001de41  lea     rbx, [rcx+10h]
0x18001de45  cmp     [rdx], rax
0x18001de48  jnz     short loc_18001DE6C
0x18001de4a  mov     rcx, [rcx+18h]; unsigned __int16 *
0x18001de4e  lea     rax, [rbp+var_20]
0x18001de52  lea     r9, [rbp+var_30]; int *
0x18001de56  mov     [rsp+78h+var_58], rax; void **
0x18001de5b  mov     r8, rbx; unsigned int *
0x18001de5e  call    ?GetUserClassStores@@YAJPEBGPEAPEAPEAUtagCLASSCONTAINER@@PEAKPEAHPEAPEAX@Z; GetUserClassStores(ushort const *,tagCLASSCONTAINER * * *,ulong *,int *,void * *)
0x18001de63  mov     r12, [rbp+var_20]
0x18001de67  mov     edi, eax
0x18001de69  mov     [rbp+var_38], eax
0x18001de6c  mov     rcx, [rbp+arg_28]
0x18001de70  mov     qword ptr [rcx], 0
0x18001de77  test    eax, eax
0x18001de79  jnz     short loc_18001DEA7
0x18001de7b  cmp     [rbx], eax
0x18001de7d  jnz     short loc_18001DEA9
0x18001de7f  mov     eax, 80040168h
0x18001de84  mov     edi, eax
0x18001de86  test    r12, r12
0x18001de89  jz      short loc_18001DE94
0x18001de8b  mov     rcx, r12; hMem
0x18001de8e  call    cs:__imp_LocalFree
0x18001de94  mov     eax, edi
0x18001de96  add     rsp, 78h
0x18001de9a  pop     r15
0x18001de9c  pop     r14
0x18001de9e  pop     r13
0x18001dea0  pop     r12
0x18001dea2  pop     rdi
0x18001dea3  pop     rsi
0x18001dea4  pop     rbx
0x18001dea5  pop     rbp
0x18001dea6  retn
0x18001dea7  js      short loc_18001DE84
0x18001dea9  mov     ecx, [rbx]
0x18001deab  mov     eax, 8
0x18001deb0  mul     rcx
0x18001deb3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001deba  cmovb   rax, rcx
0x18001debe  xor     ecx, ecx; uFlags
0x18001dec0  mov     rdx, rax; uBytes
0x18001dec3  call    cs:__imp_LocalAlloc
0x18001dec9  mov     r15, rax
0x18001decc  test    rax, rax
0x18001decf  jnz     short loc_18001DED8
0x18001ded1  mov     edi, 8007000Eh
0x18001ded6  jmp     short loc_18001DE86
0x18001ded8  mov     ecx, [rbx]
0x18001deda  xor     r14d, r14d
0x18001dedd  mov     [rbp+var_18], r14
0x18001dee1  mov     rsi, r15
0x18001dee4  mov     [rbp+var_34], r14d
0x18001dee8  test    ecx, ecx
0x18001deea  jz      loc_18001DFC6
0x18001def0  lea     rax, [rbp+var_38]
0x18001def4  mov     edx, ecx; unsigned int
0x18001def6  mov     [rsp+78h+var_40], rax; int *
0x18001defb  mov     r8, r12; void *
0x18001defe  lea     rax, [rbp+var_34]
0x18001df02  mov     [rsp+78h+var_48], rax; unsigned int *
0x18001df07  mov     eax, [rbp+var_30]
0x18001df0a  mov     [rsp+78h+var_50], eax; int
0x18001df0e  mov     rax, [rbp+arg_0]
0x18001df12  mov     [rsp+78h+var_58], 0; struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *
0x18001df1b  mov     r9, [rax+20h]; void *
0x18001df1f  mov     rcx, [rax+8]; struct tagCLASSCONTAINER **
0x18001df23  call    ?GetNextValidClassStore@@YAPEAUIClassAccess@@PEAPEAUtagCLASSCONTAINER@@KPEAX1PEAU__MIDL___MIDL_itf_wtypes_0000_0001_0001@@HPEAKPEAJ@Z; GetNextValidClassStore(tagCLASSCONTAINER * *,ulong,void *,void *,__MIDL___MIDL_itf_wtypes_0000_0001_0001 *,int,ulong *,long *)
0x18001df28  mov     r13, rax
0x18001df2b  test    rax, rax
0x18001df2e  jz      loc_18001DFB5
0x18001df34  mov     rdx, [rax]
0x18001df37  lea     r8, [r15+r14*8]
0x18001df3b  mov     ecx, [rbp+arg_20]
0x18001df3e  mov     r9, [rbp+var_28]
0x18001df42  mov     qword ptr [rsp+78h+var_50], r8
0x18001df47  mov     rax, [rdx+20h]
0x18001df4b  mov     rdx, [rbp+arg_8]
0x18001df4f  mov     r8, [rbp+arg_10]
0x18001df53  mov     dword ptr [rsp+78h+var_58], ecx
0x18001df57  mov     rcx, r13
0x18001df5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df5f  mov     [rbp+var_38], eax
0x18001df62  mov     edi, eax
0x18001df64  test    eax, eax
0x18001df66  js      short loc_18001DFC9
0x18001df68  mov     rdx, [rbp+var_28]
0x18001df6c  test    rdx, rdx
0x18001df6f  jz      short loc_18001DF8B
0x18001df71  mov     rcx, [rdx]
0x18001df74  cmp     [rbp+var_18], rcx
0x18001df78  mov     rax, [rbp+arg_18]
0x18001df7c  cmovnb  rcx, [rbp+var_18]
0x18001df81  mov     [rbp+var_18], rcx
0x18001df85  mov     rax, [rax]
0x18001df88  mov     [rdx], rax
0x18001df8b  mov     rax, [r13+0]
0x18001df8f  mov     rcx, r13
0x18001df92  inc     r14d
0x18001df95  mov     rax, [rax+10h]
0x18001df99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df9e  mov     eax, [rbp+var_34]
0x18001dfa1  xor     r13d, r13d
0x18001dfa4  mov     ecx, [rbx]
0x18001dfa6  inc     eax
0x18001dfa8  mov     [rbp+var_34], eax
0x18001dfab  cmp     eax, ecx
0x18001dfad  jb      loc_18001DEF0
0x18001dfb3  jmp     short loc_18001DFC9
0x18001dfb5  mov     rcx, r15; hMem
0x18001dfb8  call    cs:__imp_LocalFree
0x18001dfbe  mov     eax, [rbp+var_38]
0x18001dfc1  jmp     loc_18001DE96
0x18001dfc6  xor     r13d, r13d
0x18001dfc9  test    edi, edi
0x18001dfcb  js      loc_18001E0BA
0x18001dfd1  mov     edx, 20h ; ' '; uBytes
0x18001dfd6  xor     ecx, ecx; uFlags
0x18001dfd8  call    cs:__imp_LocalAlloc
0x18001dfde  mov     rbx, rax
0x18001dfe1  test    rax, rax
0x18001dfe4  jz      short loc_18001E060
0x18001dfe6  lea     rax, ??_7CMergedEnumPackage@@6B@; const CMergedEnumPackage::`vftable'
0x18001dfed  mov     qword ptr [rbx+8], 0
0x18001dff5  mov     [rbx], rax
0x18001dff8  xor     ecx, ecx; uFlags
0x18001dffa  mov     qword ptr [rbx+10h], 0
0x18001e002  mov     edx, r14d
0x18001e005  shl     rdx, 3; uBytes
0x18001e009  mov     dword ptr [rbx+18h], 0
0x18001e010  call    cs:__imp_LocalAlloc
0x18001e016  mov     [rbx+8], rax
0x18001e01a  test    rax, rax
0x18001e01d  jz      short loc_18001E062
0x18001e01f  xor     r8d, r8d
0x18001e022  test    r14d, r14d
0x18001e025  jz      short loc_18001E03B
0x18001e027  mov     rax, [r15+r8*8]
0x18001e02b  mov     rcx, [rbx+8]
0x18001e02f  mov     [rcx+r8*8], rax
0x18001e033  inc     r8d
0x18001e036  cmp     r8d, r14d
0x18001e039  jb      short loc_18001E027
0x18001e03b  mov     rax, [rbx]
0x18001e03e  lea     rdx, IID_IEnumPackage
0x18001e045  mov     r8, [rbp+arg_28]
0x18001e049  mov     rcx, rbx
0x18001e04c  mov     [rbx+10h], r14d
0x18001e050  mov     rax, [rax]
0x18001e053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e058  mov     edi, eax
0x18001e05a  test    eax, eax
0x18001e05c  js      short loc_18001E090
0x18001e05e  jmp     short loc_18001E0A5
0x18001e060  xor     ebx, ebx
0x18001e062  mov     edi, 8007000Eh
0x18001e067  test    r14d, r14d
0x18001e06a  jz      short loc_18001E08B
0x18001e06c  xor     r12d, r12d
0x18001e06f  mov     rcx, [r15+r12*8]
0x18001e073  mov     rax, [rcx]
0x18001e076  mov     rax, [rax+10h]
0x18001e07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e07f  inc     r12d
0x18001e082  cmp     r12d, r14d
0x18001e085  jb      short loc_18001E06F
0x18001e087  mov     r12, [rbp+var_20]
0x18001e08b  test    rbx, rbx
0x18001e08e  jz      short loc_18001E0A5
0x18001e090  mov     rcx, rbx; this
0x18001e093  call    ??1CMergedEnumPackage@@QEAA@XZ; CMergedEnumPackage::~CMergedEnumPackage(void)
0x18001e098  mov     edx, 20h ; ' '; unsigned __int64
0x18001e09d  mov     rcx, rbx; void *
0x18001e0a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e0a5  mov     rax, [rbp+arg_18]
0x18001e0a9  test    rax, rax
0x18001e0ac  jz      short loc_18001E0BA
0x18001e0ae  mov     rcx, [rbp+var_18]
0x18001e0b2  cmp     rcx, [rax]
0x18001e0b5  jbe     short loc_18001E0BA
0x18001e0b7  mov     [rax], rcx
0x18001e0ba  test    r12, r12
0x18001e0bd  jz      short loc_18001E0C8
0x18001e0bf  mov     rcx, r12; hMem
0x18001e0c2  call    cs:__imp_LocalFree
0x18001e0c8  mov     rcx, rsi; hMem
0x18001e0cb  call    cs:__imp_LocalFree
0x18001e0d1  test    r13, r13
0x18001e0d4  jz      loc_18001DE94
0x18001e0da  mov     rax, [r13+0]
0x18001e0de  mov     rcx, r13
0x18001e0e1  mov     rax, [rax+10h]
0x18001e0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0ea  jmp     loc_18001DE94
```
