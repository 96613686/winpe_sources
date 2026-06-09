# Microsoft::Resources::Runtime::CResourceIndexInternal::GetSubtree(ushort const *,Microsoft::Resources::Runtime::CResourceIndexInternal * *)

- ea: `0x180030168`
- end: `0x1800304fe`
- name: `?GetSubtree@CResourceIndexInternal@Runtime@Resources@Microsoft@@QEBAJPEBGPEAPEAV1234@@Z`
- size: `918`
- prototype: `__int64 __fastcall(Microsoft::Resources::Runtime::CResourceIndexInternal *__hidden this, const unsigned __int16 *, struct Microsoft::Resources::Runtime::CResourceIndexInternal **)`
- caller_count: `3`
- callee_count: `15`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180030168`
- `0x180031e40`
- `0x180059fb0`

## callees

- `0x1800204c0`
- `0x180024464`
- `0x1800263cc`
- `0x180026850`
- `0x1800277d8`
- `0x18002c8d0`
- `0x18002eef0`
- `0x180030168`
- `0x180030888`
- `0x180032148`
- `0x18003830c`
- `0x180069bbc`
- `0x18007c310`
- `0x1800867dc`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003020b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003020b`
- `OLEAUT32!__imp_SysFreeString` at `0x180030345`
- `OLEAUT32!__imp_SysFreeString` at `0x18003034f`
- `OLEAUT32!__imp_SysFreeString` at `0x180030359`
- `OLEAUT32!__imp_SysFreeString` at `0x180030345`
- `OLEAUT32!__imp_SysFreeString` at `0x18003034f`
- `OLEAUT32!__imp_SysFreeString` at `0x180030359`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::CResourceIndexInternal::GetSubtree(
        Microsoft::Resources::Runtime::CResourceIndexInternal *this,
        const unsigned __int16 *a2,
        struct Microsoft::Resources::Runtime::CResourceIndexInternal **a3)
{
  int v5; // eax
  unsigned int v6; // edi
  const unsigned __int16 *v7; // rbx
  LPCWCH v8; // rdi
  __int64 v9; // rax
  const WCHAR *v10; // rax
  __int64 v11; // rbx
  char v12; // al
  int v13; // r12d
  const struct Microsoft::Resources::IResourceMapBase *v14; // rbx
  Microsoft::Resources::ResourceMapSubtree *v15; // rax
  Microsoft::Resources::ResourceMapSubtree *v16; // rsi
  int inited; // eax
  unsigned int v18; // ebx
  Microsoft::Resources::Runtime::CResourceIndexInternal *v19; // rax
  Microsoft::Resources::Runtime::CResourceIndexInternal *v20; // rbx
  int v21; // eax
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  Microsoft::Resources::Runtime::CResourceManagerInternal *v25; // rcx
  int ResourceIndex; // eax
  unsigned int v27; // edx
  int bIgnoreCase; // [rsp+20h] [rbp-50h]
  int *bIgnoreCasea; // [rsp+20h] [rbp-50h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-50h]
  void **v31; // [rsp+30h] [rbp-40h] BYREF
  Microsoft::Resources::ResourceMapSubtree *v32; // [rsp+38h] [rbp-38h]
  LPCWCH lpString1[2]; // [rsp+40h] [rbp-30h] BYREF
  char v34; // [rsp+50h] [rbp-20h]
  __int64 v35; // [rsp+58h] [rbp-18h]
  BSTR bstrString[2]; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  Microsoft::Resources::Runtime::CResourceIndexInternal *v38; // [rsp+B0h] [rbp+40h] BYREF
  int v39; // [rsp+C0h] [rbp+50h] BYREF

  *a3 = 0;
  if ( (*((_BYTE *)this + 16) & 4) == 0 )
    return 2147942421LL;
  if ( (*((_BYTE *)this + 16) & 8) == 0 )
  {
    v35 = *((_QWORD *)this + 10);
    *(_OWORD *)lpString1 = 0;
    v34 = 0;
    *(_OWORD *)bstrString = 0;
    v5 = Microsoft::Resources::Runtime::CMrtUriParser::Normalize(
           (Microsoft::Resources::Runtime::CMrtUriParser *)lpString1,
           a2);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A1,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
        (const char *)(unsigned int)v5,
        bIgnoreCase);
      goto LABEL_21;
    }
    v7 = lpString1[0];
    v8 = lpString1[1];
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
    v10 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( CompareStringOrdinal(v7, -1, v10, -1, 1) == 2 )
    {
      v11 = *((_QWORD *)this + 7);
      if ( !v8[1] )
      {
        v16 = (Microsoft::Resources::ResourceMapSubtree *)((v11 + 16) & -(__int64)(v11 != 0));
        goto LABEL_15;
      }
      LODWORD(v38) = -1;
      v39 = -1;
      if ( !v8 || !*v8 )
        goto LABEL_22;
      bIgnoreCasea = &v39;
      v12 = (*(__int64 (__fastcall **)(_QWORD, LPCWCH, _QWORD, Microsoft::Resources::Runtime::CResourceIndexInternal **))(**(_QWORD **)(v11 + 32) + 96LL))(
              *(_QWORD *)(v11 + 32),
              v8,
              *(unsigned int *)(v11 + 40),
              &v38);
      v6 = -2147009761;
      if ( !v12 )
        goto LABEL_21;
      v13 = (int)v38;
      if ( (int)v38 < 0 )
        goto LABEL_21;
      v14 = *(const struct Microsoft::Resources::IResourceMapBase **)(v11 + 24);
      if ( v14 )
      {
        v15 = (Microsoft::Resources::ResourceMapSubtree *)Microsoft::Resources::DefObject::operator new[](0x68u);
        if ( v15 )
          v16 = (Microsoft::Resources::ResourceMapSubtree *)Microsoft::Resources::ResourceMapSubtree::ResourceMapSubtree(v15);
        else
          v16 = 0;
        v32 = v16;
        v31 = (void **)&Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UserLanguageProfileQVProvider>::`vftable';
        if ( v16 )
        {
          inited = Microsoft::Resources::ResourceMapSubtree::InitResourceMapSubtree(v16, v14, v13);
          v18 = inited;
          if ( inited >= 0 )
          {
LABEL_15:
            v19 = (Microsoft::Resources::Runtime::CResourceIndexInternal *)operator new(
                                                                             0x60u,
                                                                             (const struct std::nothrow_t *)&unk_1800DDC30);
            if ( v19 )
              v20 = (Microsoft::Resources::Runtime::CResourceIndexInternal *)Microsoft::Resources::Runtime::CResourceIndexInternal::CResourceIndexInternal(v19);
            else
              v20 = 0;
            v32 = v20;
            v31 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceIndexInternal>::`vftable';
            if ( v20 )
            {
              v21 = Microsoft::Resources::Runtime::CResourceIndexInternal::Initialize(
                      v20,
                      *(struct Microsoft::Resources::Runtime::CResourceManagerInternal **)this,
                      *((const struct Microsoft::Resources::ManagedResourceMap **)this + 7),
                      v16,
                      *((const struct Microsoft::Resources::Runtime::CContext **)this + 1));
              v6 = v21;
              if ( v21 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5B6,
                  (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
                  (const char *)(unsigned int)v21,
                  bIgnoreCaseb);
                Microsoft::Resources::Runtime::CResourceIndexInternal::`scalar deleting destructor'(v20, v27);
                goto LABEL_21;
              }
              *a3 = v20;
              goto LABEL_20;
            }
            v18 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5B4,
              (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
              (const char *)0x8007000ELL,
              (int)bIgnoreCasea);
            Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceIndexInternal>::~AutoDeletePtr<Microsoft::Resources::Runtime::CResourceIndexInternal>(&v31);
            goto LABEL_25;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3AE,
            (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\resourcemap.cpp",
            (const char *)(unsigned int)inited,
            (int)&v39);
          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::EnvironmentReferenceBuilder>::~AutoDeletePtr<Microsoft::Resources::Build::EnvironmentReferenceBuilder>(&v31);
          if ( v18 == -2147009761 )
            goto LABEL_21;
        }
        else
        {
          v18 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3AC,
            (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\resourcemap.cpp",
            (const char *)0x8007000ELL,
            (int)&v39);
        }
      }
      else
      {
LABEL_22:
        v18 = -2147024809;
      }
      v23 = v18;
      v24 = 1456;
    }
    else
    {
      v25 = *(Microsoft::Resources::Runtime::CResourceManagerInternal **)this;
      v38 = 0;
      ResourceIndex = Microsoft::Resources::Runtime::CResourceManagerInternal::GetResourceIndex(v25, v7, &v38);
      v18 = ResourceIndex;
      if ( ResourceIndex >= 0 )
      {
        ResourceIndex = Microsoft::Resources::Runtime::CResourceIndexInternal::GetSubtree(v38, v8, a3);
        v18 = ResourceIndex;
        if ( ResourceIndex >= 0 )
        {
LABEL_20:
          v6 = 0;
LABEL_21:
          SysFreeString(bstrString[0]);
          SysFreeString((BSTR)lpString1[1]);
          SysFreeString((BSTR)lpString1[0]);
          return v6;
        }
        if ( ResourceIndex == -2147009761 || ResourceIndex == -2147009737 )
          goto LABEL_25;
        v24 = 1475;
      }
      else
      {
        v6 = -2147009761;
        if ( ResourceIndex == -2147009761 )
          goto LABEL_21;
        v24 = 1470;
      }
      v23 = (unsigned int)ResourceIndex;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)v23,
      (int)bIgnoreCasea);
LABEL_25:
    Microsoft::Resources::Runtime::CMrtUriParser::~CMrtUriParser((Microsoft::Resources::Runtime::CMrtUriParser *)lpString1);
    return v18;
  }
  return 2147957535LL;
}

```

## disassembly

```asm
0x180030168  mov     [rsp-38h+arg_8], rbx
0x18003016d  push    rbp
0x18003016e  push    rsi
0x18003016f  push    rdi
0x180030170  push    r12
0x180030172  push    r13
0x180030174  push    r14
0x180030176  push    r15
0x180030178  mov     rbp, rsp
0x18003017b  sub     rsp, 70h
0x18003017f  xor     r13d, r13d
0x180030182  mov     r15, r8
0x180030185  mov     [r8], r13
0x180030188  mov     r14, rcx
0x18003018b  test    byte ptr [rcx+10h], 4
0x18003018f  jz      loc_180030477
0x180030195  test    byte ptr [rcx+10h], 8
0x180030199  jnz     loc_180030481
0x18003019f  mov     rax, [rcx+50h]
0x1800301a3  xorps   xmm0, xmm0
0x1800301a6  lea     rcx, [rbp+lpString1]; this
0x1800301aa  mov     [rbp+var_18], rax
0x1800301ae  movdqu  xmmword ptr [rbp+lpString1], xmm0
0x1800301b3  mov     [rbp+var_20], r13b
0x1800301b7  movdqu  xmmword ptr [rbp+bstrString], xmm0
0x1800301bc  call    ?Normalize@CMrtUriParser@Runtime@Resources@Microsoft@@QEAAJPEBG@Z; Microsoft::Resources::Runtime::CMrtUriParser::Normalize(ushort const *)
0x1800301c1  mov     edi, eax
0x1800301c3  test    eax, eax
0x1800301c5  js      loc_1800303A3
0x1800301cb  mov     rcx, [r14+38h]
0x1800301cf  mov     rbx, [rbp+lpString1]
0x1800301d3  mov     rdi, [rbp+lpString1+8]
0x1800301d7  mov     rax, [rcx]
0x1800301da  mov     rax, [rax+8]
0x1800301de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301e3  mov     rdx, rax
0x1800301e6  mov     rcx, [rax]
0x1800301e9  mov     rax, [rcx+10h]
0x1800301ed  mov     rcx, rdx
0x1800301f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301f5  or      esi, 0FFFFFFFFh
0x1800301f8  mov     [rsp+70h+bIgnoreCase], 1; int
0x180030200  mov     r9d, esi; cchCount2
0x180030203  mov     edx, esi; cchCount1
0x180030205  mov     r8, rax; lpString2
0x180030208  mov     rcx, rbx; lpString1
0x18003020b  call    cs:__imp_CompareStringOrdinal
0x180030211  cmp     eax, 2
0x180030214  jnz     loc_1800303BD
0x18003021a  mov     rbx, [r14+38h]
0x18003021e  cmp     [rdi+2], r13w
0x180030223  jz      loc_18003048B
0x180030229  mov     dword ptr [rbp+arg_0], esi
0x18003022c  mov     [rbp+arg_10], esi
0x18003022f  test    rdi, rdi
0x180030232  jz      loc_180030379
0x180030238  cmp     [rdi], r13w
0x18003023c  jz      loc_180030379
0x180030242  mov     rcx, [rbx+20h]
0x180030246  lea     rdx, [rbp+arg_10]
0x18003024a  mov     r8d, [rbx+28h]
0x18003024e  lea     r9, [rbp+arg_0]
0x180030252  mov     qword ptr [rsp+70h+bIgnoreCase], rdx; int
0x180030257  mov     rdx, rdi
0x18003025a  mov     rax, [rcx]
0x18003025d  mov     rax, [rax+60h]
0x180030261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030266  mov     edi, 80073B1Fh
0x18003026b  test    al, al
0x18003026d  jz      loc_180030341
0x180030273  mov     r12d, dword ptr [rbp+arg_0]
0x180030277  test    r12d, r12d
0x18003027a  js      loc_180030341
0x180030280  mov     rbx, [rbx+18h]
0x180030284  test    rbx, rbx
0x180030287  jz      loc_180030379
0x18003028d  lea     ecx, [rsi+69h]; unsigned __int64
0x180030290  call    ??_UDefObject@Resources@Microsoft@@SAPEAX_K@Z; Microsoft::Resources::DefObject::operator new[](unsigned __int64)
0x180030295  test    rax, rax
0x180030298  jz      loc_180030412
0x18003029e  mov     rcx, rax; this
0x1800302a1  call    ??0ResourceMapSubtree@Resources@Microsoft@@IEAA@XZ; Microsoft::Resources::ResourceMapSubtree::ResourceMapSubtree(void)
0x1800302a6  mov     rsi, rax
0x1800302a9  mov     [rbp+var_38], rsi
0x1800302ad  lea     rax, ??_7?$AutoDeletePtr@VUserLanguageProfileQVProvider@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UserLanguageProfileQVProvider>::`vftable'
0x1800302b4  mov     [rbp+var_40], rax
0x1800302b8  test    rsi, rsi
0x1800302bb  jz      loc_180030455
0x1800302c1  mov     r8d, r12d; int
0x1800302c4  mov     rdx, rbx; struct Microsoft::Resources::IResourceMapBase *
0x1800302c7  mov     rcx, rsi; this
0x1800302ca  call    ?InitResourceMapSubtree@ResourceMapSubtree@Resources@Microsoft@@IEAAJPEBVIResourceMapBase@23@H@Z; Microsoft::Resources::ResourceMapSubtree::InitResourceMapSubtree(Microsoft::Resources::IResourceMapBase const *,int)
0x1800302cf  mov     ebx, eax
0x1800302d1  test    eax, eax
0x1800302d3  js      loc_18003049D
0x1800302d9  lea     rdx, unk_1800DDC30; struct std::nothrow_t *
0x1800302e0  mov     ecx, 60h ; '`'; unsigned __int64
0x1800302e5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800302ea  test    rax, rax
0x1800302ed  jz      loc_1800304CB
0x1800302f3  mov     rcx, rax; this
0x1800302f6  call    ??0CResourceIndexInternal@Runtime@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::Runtime::CResourceIndexInternal::CResourceIndexInternal(void)
0x1800302fb  mov     rbx, rax
0x1800302fe  mov     [rbp+var_38], rbx
0x180030302  lea     rax, ??_7?$AutoDeletePtr@VCResourceIndexInternal@Runtime@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceIndexInternal>::`vftable'
0x180030309  mov     [rbp+var_40], rax
0x18003030d  test    rbx, rbx
0x180030310  jz      loc_1800304D3
0x180030316  mov     rax, [r14+8]
0x18003031a  mov     r9, rsi; struct Microsoft::Resources::ResourceMapSubtree *
0x18003031d  mov     r8, [r14+38h]; struct Microsoft::Resources::ManagedResourceMap *
0x180030321  mov     rcx, rbx; this
0x180030324  mov     rdx, [r14]; struct Microsoft::Resources::Runtime::CResourceManagerInternal *
0x180030327  mov     qword ptr [rsp+70h+bIgnoreCase], rax; int
0x18003032c  call    ?Initialize@CResourceIndexInternal@Runtime@Resources@Microsoft@@QEAAJPEAVCResourceManagerInternal@234@PEBVManagedResourceMap@34@PEBVResourceMapSubtree@34@PEBVCContext@234@@Z; Microsoft::Resources::Runtime::CResourceIndexInternal::Initialize(Microsoft::Resources::Runtime::CResourceManagerInternal *,Microsoft::Resources::ManagedResourceMap const *,Microsoft::Resources::ResourceMapSubtree const *,Microsoft::Resources::Runtime::CContext const *)
0x180030331  mov     edi, eax
0x180030333  test    eax, eax
0x180030335  js      loc_1800303ED
0x18003033b  mov     [r15], rbx
0x18003033e  mov     edi, r13d
0x180030341  mov     rcx, [rbp+bstrString]; bstrString
0x180030345  call    cs:__imp_SysFreeString
0x18003034b  mov     rcx, [rbp+lpString1+8]; bstrString
0x18003034f  call    cs:__imp_SysFreeString
0x180030355  mov     rcx, [rbp+lpString1]; bstrString
0x180030359  call    cs:__imp_SysFreeString
0x18003035f  mov     eax, edi
0x180030361  mov     rbx, [rsp+70h+arg_8]
0x180030369  add     rsp, 70h
0x18003036d  pop     r15
0x18003036f  pop     r14
0x180030371  pop     r13
0x180030373  pop     r12
0x180030375  pop     rdi
0x180030376  pop     rsi
0x180030377  pop     rbp
0x180030378  retn
0x180030379  mov     ebx, 80070057h
0x18003037e  mov     r9d, ebx; char *
0x180030381  mov     edx, 5B0h; void *
0x180030386  mov     rcx, [rbp+38h]; this
0x18003038a  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180030391  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030396  lea     rcx, [rbp+lpString1]; this
0x18003039a  call    ??1CMrtUriParser@Runtime@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::Runtime::CMrtUriParser::~CMrtUriParser(void)
0x18003039f  mov     eax, ebx
0x1800303a1  jmp     short loc_180030361
0x1800303a3  mov     rcx, [rbp+38h]; this
0x1800303a7  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x1800303ae  mov     r9d, eax; char *
0x1800303b1  mov     edx, 5A1h; void *
0x1800303b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800303bb  jmp     short loc_180030341
0x1800303bd  mov     rcx, [r14]; this
0x1800303c0  lea     r8, [rbp+arg_0]; struct Microsoft::Resources::Runtime::CResourceIndexInternal **
0x1800303c4  mov     rdx, rbx; unsigned __int16 *
0x1800303c7  mov     [rbp+arg_0], r13
0x1800303cb  call    ?GetResourceIndex@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJPEBGPEAPEAVCResourceIndexInternal@234@@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::GetResourceIndex(ushort const *,Microsoft::Resources::Runtime::CResourceIndexInternal * *)
0x1800303d0  mov     ebx, eax
0x1800303d2  test    eax, eax
0x1800303d4  jns     short loc_18003041A
0x1800303d6  mov     edi, 80073B1Fh
0x1800303db  cmp     eax, edi
0x1800303dd  jz      loc_180030341
0x1800303e3  mov     edx, 5BEh
0x1800303e8  jmp     loc_1800C19D8
0x1800303ed  mov     rcx, [rbp+38h]; this
0x1800303f1  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x1800303f8  mov     r9d, eax; char *
0x1800303fb  mov     edx, 5B6h; void *
0x180030400  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030405  mov     rcx, rbx; this
0x180030408  call    ??_GCResourceIndexInternal@Runtime@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::Runtime::CResourceIndexInternal::`scalar deleting destructor'(uint)
0x18003040d  jmp     loc_180030341
0x180030412  mov     rsi, r13
0x180030415  jmp     loc_1800302A9
0x18003041a  mov     rcx, [rbp+arg_0]; this
0x18003041e  mov     r8, r15; struct Microsoft::Resources::Runtime::CResourceIndexInternal **
0x180030421  mov     rdx, rdi; unsigned __int16 *
0x180030424  call    ?GetSubtree@CResourceIndexInternal@Runtime@Resources@Microsoft@@QEBAJPEBGPEAPEAV1234@@Z; Microsoft::Resources::Runtime::CResourceIndexInternal::GetSubtree(ushort const *,Microsoft::Resources::Runtime::CResourceIndexInternal * *)
0x180030429  mov     ebx, eax
0x18003042b  test    eax, eax
0x18003042d  jns     loc_18003033E
0x180030433  mov     edi, 80073B1Fh
0x180030438  cmp     eax, edi
0x18003043a  jz      loc_180030396
0x180030440  cmp     eax, 80073B37h
0x180030445  jz      loc_180030396
0x18003044b  mov     edx, 5C3h
0x180030450  jmp     loc_1800C19D8
0x180030455  mov     rcx, [rbp+38h]; this
0x180030459  lea     r8, aMinkernelMrtMr_20; "minkernel\\mrt\\mrm\\mrmmin\\resourcema"...
0x180030460  mov     ebx, 8007000Eh
0x180030465  mov     edx, 3ACh; void *
0x18003046a  mov     r9d, ebx; char *
0x18003046d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030472  jmp     loc_18003037E
0x180030477  mov     eax, 80070015h
0x18003047c  jmp     loc_180030361
0x180030481  mov     eax, 80073B1Fh
0x180030486  jmp     loc_180030361
0x18003048b  lea     rax, [rbx+10h]
0x18003048f  neg     rbx
0x180030492  sbb     rsi, rsi
0x180030495  and     rsi, rax
0x180030498  jmp     loc_1800302D9
0x18003049d  mov     rcx, [rbp+38h]; this
0x1800304a1  lea     r8, aMinkernelMrtMr_20; "minkernel\\mrt\\mrm\\mrmmin\\resourcema"...
0x1800304a8  mov     r9d, ebx; char *
0x1800304ab  mov     edx, 3AEh; void *
0x1800304b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304b5  lea     rcx, [rbp+var_40]
0x1800304b9  call    ??1?$AutoDeletePtr@VEnvironmentReferenceBuilder@Build@Resources@Microsoft@@@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::EnvironmentReferenceBuilder>::~AutoDeletePtr<Microsoft::Resources::Build::EnvironmentReferenceBuilder>(void)
0x1800304be  cmp     ebx, edi
0x1800304c0  jz      loc_180030341
0x1800304c6  jmp     loc_18003037E
0x1800304cb  mov     rbx, r13
0x1800304ce  jmp     loc_1800302FE
0x1800304d3  mov     rcx, [rbp+38h]; this
0x1800304d7  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x1800304de  mov     ebx, 8007000Eh
0x1800304e3  mov     edx, 5B4h; void *
0x1800304e8  mov     r9d, ebx; char *
0x1800304eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304f0  lea     rcx, [rbp+var_40]
0x1800304f4  call    ??1?$AutoDeletePtr@VCResourceIndexInternal@Runtime@Resources@Microsoft@@@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceIndexInternal>::~AutoDeletePtr<Microsoft::Resources::Runtime::CResourceIndexInternal>(void)
0x1800304f9  jmp     loc_180030396
0x1800c19d8  mov     r9d, eax
0x1800c19db  jmp     loc_180030386
```
