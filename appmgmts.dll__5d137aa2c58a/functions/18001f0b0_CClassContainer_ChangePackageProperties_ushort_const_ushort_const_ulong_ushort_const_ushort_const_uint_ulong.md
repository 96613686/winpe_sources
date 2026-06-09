# CClassContainer::ChangePackageProperties(ushort const *,ushort const *,ulong *,ushort const *,ushort const *,uint *,ulong *)

- ea: `0x18001f0b0`
- end: `0x18001f563`
- name: `?ChangePackageProperties@CClassContainer@@UEAAJPEBG0PEAK00PEAI1@Z`
- size: `1203`
- prototype: `__int64 __fastcall(CClassContainer *this, const unsigned __int16 *, unsigned __int16 *, unsigned int *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800016d0`
- `0x18001d130`
- `0x18001f0b0`
- `0x180021fa0`
- `0x180023448`
- `0x18002350c`
- `0x180024260`
- `0x18002435c`
- `0x180024458`
- `0x180026f3c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f1e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f24b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f2b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f52c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f1e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f24b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f2b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f52c`
- `adsldpc!ADSICloseDSObject` at `0x18001f4dd`
- `adsldpc!ADSICloseDSObject` at `0x18001f4dd`
- `adsldpc!ADSISetObjectAttributes` at `0x18001f4c9`
- `adsldpc!ADSISetObjectAttributes` at `0x18001f4c9`

## string_xrefs

- `0x18001f2dd`: `lastUpdateSequence`
- `0x18001f37c`: `msiScriptName`
- `0x18001f3b2`: `msiScriptPath`
- `0x18001f41b`: `installUiLevel`

## pseudocode

```c
__int64 __fastcall CClassContainer::ChangePackageProperties(
        CClassContainer *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned int *a8)
{
  int v10; // eax
  const unsigned __int16 *v11; // rdx
  int v12; // esi
  int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  int v17; // eax
  unsigned int v18; // ebx
  int ConsistentPackageFlags; // eax
  bool v20; // zf
  unsigned int v21; // ebx
  unsigned int i; // r14d
  unsigned int v23; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL v25; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v26; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int *v27; // [rsp+60h] [rbp-A0h]
  void *v28; // [rsp+68h] [rbp-98h] BYREF
  int v29; // [rsp+70h] [rbp-90h] BYREF
  CClassContainer *v30; // [rsp+78h] [rbp-88h]
  struct _ads_attr_info v31; // [rsp+80h] [rbp-80h] BYREF
  _ads_attr_info v32; // [rsp+A0h] [rbp-60h] BYREF
  struct _ads_attr_info v33; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v34; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v35[20]; // [rsp+1A8h] [rbp+A8h] BYREF

  v27 = a4;
  v30 = this;
  v26 = a7;
  v28 = 0;
  v25 = 0;
  v29 = 0;
  v23 = 0;
  if ( !a2 )
    return 2147942487LL;
  v10 = (*(__int64 (__fastcall **)(CClassContainer *, const unsigned __int16 *, HLOCAL *))(*(_QWORD *)this + 152LL))(
          this,
          a2,
          &v25);
  v11 = 0;
  v12 = v10;
  if ( v10 < 0 )
    goto LABEL_58;
  if ( v10 )
    return 2147746153LL;
  if ( a6 || a5 || v27 || a7 || a8 )
  {
    if ( a3 )
    {
      hMem = 0;
      if ( !a6 && !a5 && !v27 && !a7 && !a8 )
        goto LABEL_18;
      return 2147942487LL;
    }
    if ( (gCsOptions & 1) != 0 )
      v16 = GetADsOpenObjectFlags() | 0x21;
    else
      v16 = 101;
    v17 = DSServerOpenDSObject((CClassContainer *)((char *)this + 592), (const unsigned __int16 *)v25, v16, &v28);
    v11 = 0;
    v12 = v17;
    if ( v17 >= 0 )
    {
      if ( v25 )
        LocalFree(v25);
      v25 = 0;
LABEL_37:
      GetCurrentUsn(v35);
      hMem = v35;
      PackStrArrToAttr(&v31, L"lastUpdateSequence", (unsigned __int16 **)&hMem, 1u);
      v18 = 1;
      ConsistentPackageFlags = GetConsistentPackageFlags(v28, v27, 0, (unsigned int *)v26, 0, &v23, &v34);
      v11 = 0;
      v12 = ConsistentPackageFlags;
      if ( ConsistentPackageFlags >= 0 )
      {
        if ( v27 )
        {
          PackDWArrToAttr(&v32, L"packageFlags", &v23, 1u);
          v18 = 2;
          if ( v34 )
          {
            hMem = &v34;
            PackStrArrToAttr(&v33, L"msiScriptName", (unsigned __int16 **)&hMem, 1u);
            v18 = 3;
          }
        }
        if ( a6 )
        {
          hMem = a6;
          PackStrArrToAttr(&v31 + v18++, L"msiScriptPath", (unsigned __int16 **)&hMem, 1u);
        }
        if ( a5 )
        {
          v20 = ((unsigned __int64)a5 & -(__int64)(*a5 != 0)) == 0;
          hMem = (HLOCAL)((unsigned __int64)a5 & -(__int64)(*a5 != 0));
          PackStrArrToAttr(&v31 + v18++, L"url", (unsigned __int16 **)&hMem, !v20);
        }
        if ( v26 )
        {
          v23 = *(_DWORD *)v26;
          PackDWArrToAttr(&v31 + v18++, L"installUiLevel", &v23, 1u);
        }
        if ( a8 )
        {
          v23 = *a8;
          PackDWArrToAttr(&v31 + v18++, L"revision", &v23, 1u);
        }
        if ( a3 )
        {
          v26 = a3;
          PackStrArrToAttr(&v31 + v18, L"packageName", &v26, 1u);
          v21 = v18 + 1;
          v26 = a3;
          PackStrArrToAttr(&v31 + v21, L"displayName", &v26, 1u);
          v18 = v21 + 1;
        }
        v12 = ADSISetObjectAttributes(v28, &v31, v18, &v29);
        v11 = 0;
      }
      if ( v28 )
      {
        ADSICloseDSObject(v28, 0);
        v11 = 0;
      }
      for ( i = 0; i < v18; ++i )
        LocalFree(*((HLOCAL *)&v31.pADsValues + 4 * i));
      if ( v12 >= 0 )
        UpdateStoreUsn(*((void **)v30 + 69), v35);
    }
LABEL_58:
    if ( v25 )
      LocalFree(v25);
    return RemapErrorCode(v12, v11);
  }
  if ( a3 )
  {
    hMem = 0;
LABEL_18:
    v14 = (*(__int64 (__fastcall **)(CClassContainer *, unsigned __int16 *, HLOCAL *))(*(_QWORD *)this + 152LL))(
            this,
            a3,
            &hMem);
    v11 = 0;
    v12 = v14;
    if ( hMem )
    {
      LocalFree(hMem);
      v11 = 0;
    }
    hMem = 0;
    if ( v12 < 0 )
      goto LABEL_58;
    if ( !v12 )
      return 2147746154LL;
    if ( (gCsOptions & 1) != 0 )
      v15 = GetADsOpenObjectFlags() | 0x21;
    else
      v15 = 101;
    v12 = DSServerOpenDSObject((CClassContainer *)((char *)this + 592), (const unsigned __int16 *)v25, v15, &v28);
    if ( v25 )
      LocalFree(v25);
    v25 = 0;
    if ( v12 < 0 )
      return RemapErrorCode(v12, v11);
    goto LABEL_37;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001f0b0  push    rbp
0x18001f0b2  push    rbx
0x18001f0b3  push    rsi
0x18001f0b4  push    rdi
0x18001f0b5  push    r12
0x18001f0b7  push    r13
0x18001f0b9  push    r14
0x18001f0bb  push    r15
0x18001f0bd  lea     rbp, [rsp-0E8h]
0x18001f0c5  sub     rsp, 1E8h
0x18001f0cc  mov     rax, cs:__security_cookie
0x18001f0d3  xor     rax, rsp
0x18001f0d6  mov     [rbp+120h+var_50], rax
0x18001f0dd  mov     rdi, [rbp+120h+arg_30]
0x18001f0e4  xor     eax, eax
0x18001f0e6  mov     [rsp+220h+var_1C0], r9
0x18001f0eb  mov     r15, r8
0x18001f0ee  mov     [rsp+220h+var_1A8], rcx
0x18001f0f3  mov     rbx, rcx
0x18001f0f6  mov     [rsp+220h+var_1C8], rdi
0x18001f0fb  mov     [rsp+220h+var_1B8], rax
0x18001f100  mov     [rsp+220h+var_1D0], rax
0x18001f105  mov     [rsp+220h+var_1B0], eax
0x18001f109  mov     [rsp+220h+var_1E0], eax
0x18001f10d  test    rdx, rdx
0x18001f110  jz      loc_18001F53B
0x18001f116  mov     rax, [rcx]
0x18001f119  lea     r8, [rsp+220h+var_1D0]
0x18001f11e  mov     rax, [rax+98h]
0x18001f125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f12a  xor     edx, edx
0x18001f12c  mov     esi, eax
0x18001f12e  test    eax, eax
0x18001f130  js      loc_18001F522
0x18001f136  jz      short loc_18001F142
0x18001f138  mov     eax, 80040169h
0x18001f13d  jmp     loc_18001F540
0x18001f142  mov     r12, [rbp+120h+arg_28]
0x18001f149  mov     r13, [rbp+120h+arg_38]
0x18001f150  mov     r14, [rbp+120h+arg_20]
0x18001f157  mov     rax, [rsp+220h+var_1C0]
0x18001f15c  test    r12, r12
0x18001f15f  jnz     short loc_18001F185
0x18001f161  test    r14, r14
0x18001f164  jnz     short loc_18001F185
0x18001f166  test    rax, rax
0x18001f169  jnz     short loc_18001F185
0x18001f16b  test    rdi, rdi
0x18001f16e  jnz     short loc_18001F185
0x18001f170  test    r13, r13
0x18001f173  jnz     short loc_18001F185
0x18001f175  test    r15, r15
0x18001f178  jz      loc_18001F53B
0x18001f17e  mov     [rsp+220h+hMem], rdx
0x18001f183  jmp     short loc_18001F1C0
0x18001f185  test    r15, r15
0x18001f188  jz      loc_18001F264
0x18001f18e  mov     [rsp+220h+hMem], rdx
0x18001f193  test    r12, r12
0x18001f196  jnz     loc_18001F53B
0x18001f19c  test    r14, r14
0x18001f19f  jnz     loc_18001F53B
0x18001f1a5  test    rax, rax
0x18001f1a8  jnz     loc_18001F53B
0x18001f1ae  test    rdi, rdi
0x18001f1b1  jnz     loc_18001F53B
0x18001f1b7  test    r13, r13
0x18001f1ba  jnz     loc_18001F53B
0x18001f1c0  mov     rax, [rbx]
0x18001f1c3  lea     r8, [rsp+220h+hMem]
0x18001f1c8  mov     rdx, r15
0x18001f1cb  mov     rcx, rbx
0x18001f1ce  mov     rax, [rax+98h]
0x18001f1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1da  mov     rcx, [rsp+220h+hMem]; hMem
0x18001f1df  xor     edx, edx
0x18001f1e1  mov     esi, eax
0x18001f1e3  test    rcx, rcx
0x18001f1e6  jz      short loc_18001F1F0
0x18001f1e8  call    cs:__imp_LocalFree
0x18001f1ee  xor     edx, edx
0x18001f1f0  mov     [rsp+220h+hMem], rdx
0x18001f1f5  test    esi, esi
0x18001f1f7  js      loc_18001F522
0x18001f1fd  jnz     short loc_18001F209
0x18001f1ff  mov     eax, 8004016Ah
0x18001f204  jmp     loc_18001F540
0x18001f209  mov     edi, 1
0x18001f20e  test    byte ptr cs:?gCsOptions@@3KA, dil; ulong gCsOptions
0x18001f215  jz      short loc_18001F221
0x18001f217  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x18001f21c  or      eax, 21h
0x18001f21f  jmp     short loc_18001F226
0x18001f221  mov     eax, 65h ; 'e'
0x18001f226  mov     rdx, [rsp+220h+var_1D0]; unsigned __int16 *
0x18001f22b  lea     rcx, [rbx+250h]; struct CServerContext *
0x18001f232  lea     r9, [rsp+220h+var_1B8]; void **
0x18001f237  mov     r8d, eax; int
0x18001f23a  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x18001f23f  mov     rcx, [rsp+220h+var_1D0]; hMem
0x18001f244  mov     esi, eax
0x18001f246  test    rcx, rcx
0x18001f249  jz      short loc_18001F251
0x18001f24b  call    cs:__imp_LocalFree
0x18001f251  mov     [rsp+220h+var_1D0], 0
0x18001f25a  test    esi, esi
0x18001f25c  js      loc_18001F532
0x18001f262  jmp     short loc_18001F2BD
0x18001f264  mov     edi, 1
0x18001f269  test    byte ptr cs:?gCsOptions@@3KA, dil; ulong gCsOptions
0x18001f270  jz      short loc_18001F27C
0x18001f272  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x18001f277  or      eax, 21h
0x18001f27a  jmp     short loc_18001F281
0x18001f27c  mov     eax, 65h ; 'e'
0x18001f281  mov     rdx, [rsp+220h+var_1D0]; unsigned __int16 *
0x18001f286  lea     rcx, [rbx+250h]; struct CServerContext *
0x18001f28d  lea     r9, [rsp+220h+var_1B8]; void **
0x18001f292  mov     r8d, eax; int
0x18001f295  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x18001f29a  xor     edx, edx
0x18001f29c  mov     esi, eax
0x18001f29e  test    eax, eax
0x18001f2a0  js      loc_18001F522
0x18001f2a6  mov     rcx, [rsp+220h+var_1D0]; hMem
0x18001f2ab  test    rcx, rcx
0x18001f2ae  jz      short loc_18001F2B8
0x18001f2b0  call    cs:__imp_LocalFree
0x18001f2b6  xor     edx, edx
0x18001f2b8  mov     [rsp+220h+var_1D0], rdx
0x18001f2bd  lea     rcx, [rbp+120h+var_78]; unsigned __int16 *
0x18001f2c4  call    ?GetCurrentUsn@@YAXPEAG@Z; GetCurrentUsn(ushort *)
0x18001f2c9  lea     rax, [rbp+120h+var_78]
0x18001f2d0  mov     r9d, edi; unsigned int
0x18001f2d3  lea     r8, [rsp+220h+hMem]; unsigned __int16 **
0x18001f2d8  mov     [rsp+220h+hMem], rax
0x18001f2dd  lea     rdx, aLastupdatesequ; "lastUpdateSequence"
0x18001f2e4  lea     rcx, [rbp+120h+var_1A0]; struct _ads_attr_info *
0x18001f2e8  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x18001f2ed  mov     r9, [rsp+220h+var_1C8]; unsigned int *
0x18001f2f2  lea     rax, [rbp+120h+var_80]
0x18001f2f9  mov     rdx, [rsp+220h+var_1C0]; unsigned int *
0x18001f2fe  xor     r8d, r8d; unsigned int *
0x18001f301  mov     rcx, [rsp+220h+var_1B8]; void *
0x18001f306  mov     ebx, edi
0x18001f308  mov     [rsp+220h+var_1F0], rax; unsigned __int16 *
0x18001f30d  lea     rax, [rsp+220h+var_1E0]
0x18001f312  mov     [rsp+220h+var_1F8], rax; unsigned int *
0x18001f317  mov     [rsp+220h+var_200], 0; enum _CLASSPATHTYPE *
0x18001f320  call    ?GetConsistentPackageFlags@@YAJPEAXPEAKPEAI2PEAW4_CLASSPATHTYPE@@1PEAG@Z; GetConsistentPackageFlags(void *,ulong *,uint *,uint *,_CLASSPATHTYPE *,ulong *,ushort *)
0x18001f325  xor     edx, edx
0x18001f327  mov     esi, eax
0x18001f329  test    eax, eax
0x18001f32b  js      loc_18001F4D3
0x18001f331  cmp     [rsp+220h+var_1C0], rdx
0x18001f336  jz      short loc_18001F393
0x18001f338  mov     eax, [rsp+220h+var_1E0]
0x18001f33c  lea     r8, [rsp+220h+var_1E0]; unsigned int *
0x18001f341  mov     r9d, edi; unsigned int
0x18001f344  mov     [rsp+220h+var_1E0], eax
0x18001f348  lea     rdx, aPackageflags; "packageFlags"
0x18001f34f  lea     rcx, [rbp+120h+var_180]; struct _ads_attr_info *
0x18001f353  call    ?PackDWArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAKK@Z; PackDWArrToAttr(_ads_attr_info *,ushort const *,ulong *,ulong)
0x18001f358  xor     edx, edx
0x18001f35a  mov     ebx, 2
0x18001f35f  cmp     [rbp+120h+var_80], dx
0x18001f366  jz      short loc_18001F393
0x18001f368  lea     rax, [rbp+120h+var_80]
0x18001f36f  mov     r9d, edi; unsigned int
0x18001f372  lea     r8, [rsp+220h+hMem]; unsigned __int16 **
0x18001f377  mov     [rsp+220h+hMem], rax
0x18001f37c  lea     rdx, aMsiscriptname; "msiScriptName"
0x18001f383  lea     rcx, [rbp+120h+var_160]; struct _ads_attr_info *
0x18001f387  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x18001f38c  xor     edx, edx
0x18001f38e  mov     ebx, 3
0x18001f393  test    r12, r12
0x18001f396  jz      short loc_18001F3C2
0x18001f398  mov     eax, ebx
0x18001f39a  lea     rcx, [rbp+120h+var_1A0]
0x18001f39e  shl     rax, 5
0x18001f3a2  lea     r8, [rsp+220h+hMem]; unsigned __int16 **
0x18001f3a7  add     rcx, rax; struct _ads_attr_info *
0x18001f3aa  mov     [rsp+220h+hMem], r12
0x18001f3af  mov     r9d, edi; unsigned int
0x18001f3b2  lea     rdx, aMsiscriptpath; "msiScriptPath"
0x18001f3b9  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x18001f3be  add     ebx, edi
0x18001f3c0  xor     edx, edx
0x18001f3c2  test    r14, r14
0x18001f3c5  jz      short loc_18001F400
0x18001f3c7  movzx   eax, word ptr [r14]
0x18001f3cb  lea     r8, [rsp+220h+hMem]; unsigned __int16 **
0x18001f3d0  neg     ax
0x18001f3d3  mov     r9d, edx
0x18001f3d6  mov     eax, ebx
0x18001f3d8  lea     rdx, aUrl; "url"
0x18001f3df  sbb     rcx, rcx
0x18001f3e2  and     rcx, r14
0x18001f3e5  mov     [rsp+220h+hMem], rcx
0x18001f3ea  lea     rcx, [rbp+120h+var_1A0]
0x18001f3ee  setnz   r9b; unsigned int
0x18001f3f2  shl     rax, 5
0x18001f3f6  add     rcx, rax; struct _ads_attr_info *
0x18001f3f9  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x18001f3fe  add     ebx, edi
0x18001f400  mov     rax, [rsp+220h+var_1C8]
0x18001f405  test    rax, rax
0x18001f408  jz      short loc_18001F433
0x18001f40a  mov     eax, [rax]
0x18001f40c  lea     rcx, [rbp+120h+var_1A0]
0x18001f410  mov     [rsp+220h+var_1E0], eax
0x18001f414  lea     r8, [rsp+220h+var_1E0]; unsigned int *
0x18001f419  mov     eax, ebx
0x18001f41b  lea     rdx, aInstalluilevel; "installUiLevel"
0x18001f422  shl     rax, 5
0x18001f426  mov     r9d, edi; unsigned int
0x18001f429  add     rcx, rax; struct _ads_attr_info *
0x18001f42c  call    ?PackDWArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAKK@Z; PackDWArrToAttr(_ads_attr_info *,ushort const *,ulong *,ulong)
0x18001f431  add     ebx, edi
0x18001f433  test    r13, r13
0x18001f436  jz      short loc_18001F463
0x18001f438  mov     eax, [r13+0]
0x18001f43c  lea     rcx, [rbp+120h+var_1A0]
0x18001f440  mov     [rsp+220h+var_1E0], eax
0x18001f444  lea     r8, [rsp+220h+var_1E0]; unsigned int *
0x18001f449  mov     eax, ebx
0x18001f44b  lea     rdx, aRevision_0; "revision"
0x18001f452  shl     rax, 5
0x18001f456  mov     r9d, edi; unsigned int
0x18001f459  add     rcx, rax; struct _ads_attr_info *
0x18001f45c  call    ?PackDWArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAKK@Z; PackDWArrToAttr(_ads_attr_info *,ushort const *,ulong *,ulong)
0x18001f461  add     ebx, edi
0x18001f463  test    r15, r15
0x18001f466  jz      short loc_18001F4B8
0x18001f468  mov     eax, ebx
0x18001f46a  lea     rcx, [rbp+120h+var_1A0]
0x18001f46e  shl     rax, 5
0x18001f472  lea     r8, [rsp+220h+var_1C8]; unsigned __int16 **
0x18001f477  add     rcx, rax; struct _ads_attr_info *
0x18001f47a  mov     [rsp+220h+var_1C8], r15
0x18001f47f  mov     r9d, edi; unsigned int
0x18001f482  lea     rdx, aPackagename_0; "packageName"
0x18001f489  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x18001f48e  add     ebx, edi
0x18001f490  mov     [rsp+220h+var_1C8], r15
0x18001f495  mov     eax, ebx
0x18001f497  lea     rcx, [rbp+120h+var_1A0]
0x18001f49b  shl     rax, 5
0x18001f49f  lea     r8, [rsp+220h+var_1C8]; unsigned __int16 **
0x18001f4a4  add     rcx, rax; struct _ads_attr_info *
0x18001f4a7  lea     rdx, aDisplayname; "displayName"
0x18001f4ae  mov     r9d, edi; unsigned int
0x18001f4b1  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x18001f4b6  add     ebx, edi
0x18001f4b8  mov     rcx, [rsp+220h+var_1B8]
0x18001f4bd  lea     r9, [rsp+220h+var_1B0]
0x18001f4c2  mov     r8d, ebx
0x18001f4c5  lea     rdx, [rbp+120h+var_1A0]
0x18001f4c9  call    cs:__imp_ADSISetObjectAttributes
0x18001f4cf  mov     esi, eax
0x18001f4d1  xor     edx, edx
0x18001f4d3  mov     rcx, [rsp+220h+var_1B8]
0x18001f4d8  test    rcx, rcx
0x18001f4db  jz      short loc_18001F4E5
0x18001f4dd  call    cs:__imp_ADSICloseDSObject
0x18001f4e3  xor     edx, edx
0x18001f4e5  mov     r14d, edx
0x18001f4e8  test    ebx, ebx
0x18001f4ea  jz      short loc_18001F506
0x18001f4ec  mov     ecx, r14d
0x18001f4ef  shl     rcx, 5
0x18001f4f3  mov     rcx, [rbp+rcx+120h+var_1A0.pADsValues]; hMem
0x18001f4f8  call    cs:__imp_LocalFree
0x18001f4fe  add     r14d, edi
0x18001f501  cmp     r14d, ebx
0x18001f504  jb      short loc_18001F4EC
0x18001f506  test    esi, esi
0x18001f508  js      short loc_18001F522
0x18001f50a  mov     rcx, [rsp+220h+var_1A8]
0x18001f50f  lea     rdx, [rbp+120h+var_78]; unsigned __int16 *
0x18001f516  mov     rcx, [rcx+228h]; void *
0x18001f51d  call    ?UpdateStoreUsn@@YAJPEAXPEBG@Z; UpdateStoreUsn(void *,ushort const *)
0x18001f522  mov     rcx, [rsp+220h+var_1D0]; hMem
0x18001f527  test    rcx, rcx
0x18001f52a  jz      short loc_18001F532
0x18001f52c  call    cs:__imp_LocalFree
0x18001f532  mov     ecx, esi; int
0x18001f534  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x18001f539  jmp     short loc_18001F540
0x18001f53b  mov     eax, 80070057h
0x18001f540  mov     rcx, [rbp+120h+var_50]
0x18001f547  xor     rcx, rsp; StackCookie
0x18001f54a  call    __security_check_cookie
0x18001f54f  add     rsp, 1E8h
0x18001f556  pop     r15
0x18001f558  pop     r14
0x18001f55a  pop     r13
0x18001f55c  pop     r12
0x18001f55e  pop     rdi
  ... truncated ...
```
