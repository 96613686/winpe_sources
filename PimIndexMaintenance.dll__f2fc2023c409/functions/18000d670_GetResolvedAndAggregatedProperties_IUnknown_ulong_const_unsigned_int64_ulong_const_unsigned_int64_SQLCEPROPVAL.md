# GetResolvedAndAggregatedProperties(IUnknown *,ulong const *,unsigned __int64,ulong const *,unsigned __int64,_SQLCEPROPVAL * *,unsigned __int64 *)

- ea: `0x18000d670`
- end: `0x18000db02`
- name: `?GetResolvedAndAggregatedProperties@@YAJPEAUIUnknown@@PEBK_K12PEAPEAU_SQLCEPROPVAL@@PEA_K@Z`
- size: `1170`
- prototype: `__int64 __fastcall(struct IUnknown *, const unsigned int *, unsigned __int64, const unsigned int *, unsigned __int64, struct _SQLCEPROPVAL **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d3b0`
- `0x18001b5f0`

## callees

- `0x180003f0c`
- `0x18000428c`
- `0x18000b5f4`
- `0x18000d510`
- `0x18000d670`
- `0x18000db08`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d955`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d955`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d696`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d696`
- `PIMSTORE!CopyCEPROPVAL` at `0x18000d9a3`
- `PIMSTORE!CopyCEPROPVAL` at `0x18000da25`
- `PIMSTORE!CopyCEPROPVAL` at `0x18000d9a3`
- `PIMSTORE!CopyCEPROPVAL` at `0x18000da25`
- `UserDataTypeHelperUtil!GetPropMemSize` at `0x18000d779`
- `UserDataTypeHelperUtil!GetPropMemSize` at `0x18000d779`

## pseudocode

```c
__int64 __fastcall GetResolvedAndAggregatedProperties(
        struct IUnknown *a1,
        const unsigned int *a2,
        unsigned __int64 a3,
        const unsigned int *a4,
        unsigned __int64 a5,
        struct _SQLCEPROPVAL **a6,
        unsigned __int64 *a7)
{
  HANDLE ProcessHeap; // rax
  __int64 v11; // r8
  unsigned __int16 v12; // r14
  unsigned __int64 v13; // rsi
  HANDLE v14; // r13
  __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // r8
  unsigned int v18; // ebx
  __int64 v19; // r9
  __int64 v20; // rcx
  unsigned int v21; // ecx
  __int64 v22; // rbx
  int PropMemSize; // eax
  struct IUnknown *v24; // rbx
  struct IUnknown *v25; // rdi
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  _QWORD *v27; // rax
  int v28; // eax
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rcx
  struct IUnknown *v32; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  _QWORD *v34; // rax
  unsigned __int64 v35; // r14
  __int64 v36; // rdi
  __int64 v37; // rbx
  char *v38; // rax
  __int64 v39; // r8
  struct _SQLCEPROPVAL *v40; // rsi
  __int64 v41; // rbx
  unsigned __int64 i; // rdi
  int v43; // r15d
  __int64 v44; // r9
  unsigned __int64 j; // rdi
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // r9
  unsigned int v50; // [rsp+50h] [rbp-51h] BYREF
  struct IUnknown *v51; // [rsp+58h] [rbp-49h] BYREF
  struct IUnknown *v52; // [rsp+60h] [rbp-41h] BYREF
  void *v53; // [rsp+68h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-31h] BYREF
  __int64 v55; // [rsp+78h] [rbp-29h] BYREF
  char *v56; // [rsp+80h] [rbp-21h] BYREF
  int v57; // [rsp+88h] [rbp-19h] BYREF
  char *v58; // [rsp+90h] [rbp-11h] BYREF
  _QWORD v59[9]; // [rsp+98h] [rbp-9h] BYREF

  ProcessHeap = GetProcessHeap();
  v12 = a5;
  LODWORD(v13) = 0;
  v56 = 0;
  hMem = 0;
  v14 = ProcessHeap;
  v50 = 0;
  if ( a5 )
  {
    v15 = 0;
    v55 = 0;
    if ( a1 )
    {
      ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
        a1,
        &GUID_50911ab2_e54e_4d87_85ad_ca6ba91ab709,
        &v55);
      v15 = v55;
    }
    v57 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, const unsigned int *, __int64, _QWORD, HLOCAL *, unsigned int *, int *, HANDLE))(*(_QWORD *)v15 + 64LL))(
            v15,
            a4,
            1,
            v12,
            &hMem,
            &v50,
            &v57,
            v14);
    v18 = v16;
    if ( v16 < 0 )
    {
      v19 = 58;
      v20 = (unsigned int)v16;
LABEL_15:
      Log_HREvent_1(v20, 1, v17, v19);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
      goto LABEL_63;
    }
    v21 = v50;
    v13 = 24LL * v50;
    if ( v13 > 0xFFFFFFFF )
    {
      v19 = 63;
LABEL_14:
      v18 = -2147024362;
      v20 = 2147942934LL;
      goto LABEL_15;
    }
    v22 = 0;
    while ( (unsigned int)v22 < v21 )
    {
      PropMemSize = GetPropMemSize(*((_QWORD *)hMem + 3 * v22 + 2));
      if ( PropMemSize + (int)v13 < (unsigned int)v13 )
      {
        v19 = 68;
        goto LABEL_14;
      }
      LODWORD(v13) = PropMemSize + v13;
      v22 = (unsigned int)(v22 + 1);
      v21 = v50;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
  }
  if ( a3 )
  {
    v24 = 0;
    LODWORD(a5) = 0;
    v52 = 0;
    v51 = 0;
    if ( a1 )
    {
      if ( ATL::AtlComQIPtrAssign(&v52, a1, &GUID_7268d1d3_d871_4b70_b1c0_79aefc11c9df) )
      {
        v25 = v52;
        AddRef = v52->lpVtbl[1].AddRef;
        v27 = tlx::replace<_SQLCEPROPVAL,&void _LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(&v56);
        v28 = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned int *, __int64, _QWORD, _QWORD *, unsigned __int64 *, HANDLE))AddRef)(
                v25,
                a2,
                1,
                (unsigned __int16)a3,
                v27,
                &a5,
                v14);
        v18 = v28;
        if ( v28 < 0 )
        {
          v29 = 88;
LABEL_21:
          v30 = 1;
          v31 = (unsigned int)v28;
LABEL_22:
          Log_HREvent_1(v31, v30, v11, v29);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v51);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v52);
          goto LABEL_63;
        }
        goto LABEL_30;
      }
      v24 = v51;
    }
    if ( v24 == a1 )
    {
      v32 = v24;
    }
    else
    {
      v32 = ATL::AtlComQIPtrAssign(&v51, a1, &GUID_50911ab2_e54e_4d87_85ad_ca6ba91ab709);
      v24 = v51;
    }
    if ( !v32 )
    {
      v30 = 0;
      v18 = -2147418113;
      v29 = 102;
      goto LABEL_43;
    }
    QueryInterface = v24->lpVtbl[1].QueryInterface;
    v34 = tlx::replace<_SQLCEPROPVAL,&void _LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(&v56);
    v28 = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned int *, __int64, _QWORD, _QWORD *, unsigned __int64 *, HANDLE))QueryInterface)(
            v24,
            a2,
            1,
            (unsigned __int16)a3,
            v34,
            &a5,
            v14);
    v18 = v28;
    if ( v28 < 0 )
    {
      v29 = 98;
      goto LABEL_21;
    }
LABEL_30:
    if ( (int)v13 + (int)a5 >= (unsigned int)v13 )
    {
      LODWORD(v13) = v13 + a5;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v51);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v52);
      goto LABEL_32;
    }
    v29 = 106;
    v30 = 1;
    v18 = -2147024362;
LABEL_43:
    v31 = v18;
    goto LABEL_22;
  }
LABEL_32:
  if ( !(_DWORD)v13 )
  {
    *a7 = 0;
    *a6 = 0;
LABEL_62:
    v18 = 0;
    goto LABEL_63;
  }
  v35 = v50 + a3;
  if ( v35 < v50 )
  {
    v48 = 112;
    goto LABEL_59;
  }
  v58 = 0;
  v36 = 24 * v35;
  if ( !is_mul_ok(v35, 0x18u) )
  {
    v48 = 115;
LABEL_59:
    v18 = -2147024362;
    v47 = 1;
    goto LABEL_60;
  }
  v37 = (unsigned int)v13;
  if ( (unsigned int)v13 < 24 * v35 )
  {
    v47 = 0;
    v18 = -2147467259;
    v48 = 116;
LABEL_60:
    Log_HREvent_1(v18, v47, v11, v48);
    goto LABEL_63;
  }
  v38 = (char *)LocalAlloc(0, (unsigned int)v13);
  v53 = v38;
  v40 = (struct _SQLCEPROPVAL *)v38;
  if ( v38 )
  {
    v59[0] = v37 - v36;
    v41 = 0;
    v58 = &v38[v36];
    for ( i = 0; i < a3; ++i )
    {
      v43 = CopyCEPROPVAL(&v56[24 * i], (char *)v40 + 24 * v41, &v58, v59);
      if ( v43 < 0 )
      {
        v44 = 134;
LABEL_45:
        Log_HREvent_1((unsigned int)v43, 1, v39, v44);
        auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(&v53);
        v18 = v43;
        goto LABEL_63;
      }
      v41 = (unsigned int)(v41 + 1);
    }
    for ( j = 0; j < v50; ++j )
    {
      v43 = CopyCEPROPVAL(*((_QWORD *)hMem + 3 * j + 2), (char *)v40 + 24 * v41, &v58, v59);
      if ( v43 < 0 )
      {
        v44 = 140;
        goto LABEL_45;
      }
      v41 = (unsigned int)(v41 + 1);
    }
    if ( (unsigned int)v41 == v35 )
    {
      v53 = 0;
      *a7 = v35;
      *a6 = v40;
      auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(&v53);
      goto LABEL_62;
    }
    v18 = -2147418113;
    v46 = 143;
  }
  else
  {
    v18 = -2147024882;
    v46 = 119;
  }
  Log_HREvent_1(v18, 0, v39, v46);
  auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(&v53);
LABEL_63:
  auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(&hMem);
  auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&v56);
  return v18;
}

```

## disassembly

```asm
0x18000d670  mov     [rsp-8+arg_8], rdx
0x18000d675  push    rbp
0x18000d676  push    rbx
0x18000d677  push    rsi
0x18000d678  push    rdi
0x18000d679  push    r12
0x18000d67b  push    r13
0x18000d67d  push    r14
0x18000d67f  push    r15
0x18000d681  lea     rbp, [rsp-7]
0x18000d686  sub     rsp, 0A8h
0x18000d68d  mov     r15, r9
0x18000d690  mov     r12, r8
0x18000d693  mov     rdi, rcx
0x18000d696  call    cs:__imp_GetProcessHeap
0x18000d69c  mov     r14, [rbp+3Fh+arg_20]
0x18000d6a0  xor     ecx, ecx
0x18000d6a2  xor     esi, esi
0x18000d6a4  mov     [rbp+3Fh+var_60], 0
0x18000d6ac  mov     [rbp+3Fh+hMem], rcx
0x18000d6b0  mov     r13, rax
0x18000d6b3  mov     [rbp+3Fh+var_90], ecx
0x18000d6b6  test    r14, r14
0x18000d6b9  jz      loc_18000D7C6
0x18000d6bf  xor     ebx, ebx
0x18000d6c1  mov     [rbp+3Fh+var_68], rbx
0x18000d6c5  test    rdi, rdi
0x18000d6c8  jz      short loc_18000D6EB
0x18000d6ca  mov     rax, [rdi]
0x18000d6cd  lea     r8, [rbp+3Fh+var_68]
0x18000d6d1  lea     rdx, _GUID_50911ab2_e54e_4d87_85ad_ca6ba91ab709
0x18000d6d8  mov     rcx, rdi
0x18000d6db  mov     rax, [rax]
0x18000d6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6e3  mov     rcx, [rbp+3Fh+hMem]; hMem
0x18000d6e7  mov     rbx, [rbp+3Fh+var_68]
0x18000d6eb  mov     [rbp+3Fh+var_58], esi
0x18000d6ee  mov     rax, [rbx]
0x18000d6f1  mov     rsi, [rax+40h]
0x18000d6f5  test    rcx, rcx
0x18000d6f8  jz      short loc_18000D708
0x18000d6fa  call    cs:__imp_LocalFree
0x18000d700  mov     [rbp+3Fh+hMem], 0
0x18000d708  mov     [rsp+0E0h+var_A8], r13
0x18000d70d  lea     rax, [rbp+3Fh+var_58]
0x18000d711  mov     [rsp+0E0h+var_B0], rax
0x18000d716  movzx   r9d, r14w
0x18000d71a  lea     rax, [rbp+3Fh+var_90]
0x18000d71e  mov     r14d, 1
0x18000d724  mov     [rsp+0E0h+var_B8], rax
0x18000d729  mov     r8d, r14d
0x18000d72c  lea     rax, [rbp+3Fh+hMem]
0x18000d730  mov     rdx, r15
0x18000d733  mov     [rsp+0E0h+var_C0], rax
0x18000d738  mov     rcx, rbx
0x18000d73b  mov     rax, rsi
0x18000d73e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d743  mov     ebx, eax
0x18000d745  test    eax, eax
0x18000d747  jns     short loc_18000D751
0x18000d749  lea     r9d, [r14+39h]
0x18000d74d  mov     ecx, eax
0x18000d74f  jmp     short loc_18000D7B0
0x18000d751  mov     ecx, [rbp+3Fh+var_90]
0x18000d754  mov     eax, 0FFFFFFFFh
0x18000d759  lea     rsi, [rcx+rcx*2]
0x18000d75d  shl     rsi, 3
0x18000d761  cmp     rsi, rax
0x18000d764  ja      short loc_18000D7A3
0x18000d766  xor     ebx, ebx
0x18000d768  cmp     ebx, ecx
0x18000d76a  jnb     short loc_18000D798
0x18000d76c  mov     rcx, [rbp+3Fh+hMem]
0x18000d770  lea     rdx, [rbx+rbx*2]
0x18000d774  mov     rcx, [rcx+rdx*8+10h]
0x18000d779  call    cs:__imp_GetPropMemSize
0x18000d77f  lea     ecx, [rax+rsi]
0x18000d782  cmp     ecx, esi
0x18000d784  jb      short loc_18000D790
0x18000d786  mov     esi, ecx
0x18000d788  add     ebx, r14d
0x18000d78b  mov     ecx, [rbp+3Fh+var_90]
0x18000d78e  jmp     short loc_18000D768
0x18000d790  mov     r9d, 44h ; 'D'
0x18000d796  jmp     short loc_18000D7A9
0x18000d798  lea     rcx, [rbp+3Fh+var_68]
0x18000d79c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d7a1  jmp     short loc_18000D7CC
0x18000d7a3  mov     r9d, 3Fh ; '?'
0x18000d7a9  mov     ebx, 80070216h
0x18000d7ae  mov     ecx, ebx
0x18000d7b0  mov     edx, r14d
0x18000d7b3  call    Log_HREvent_1
0x18000d7b8  lea     rcx, [rbp+3Fh+var_68]
0x18000d7bc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d7c1  jmp     loc_18000DADA
0x18000d7c6  mov     r14d, 1
0x18000d7cc  test    r12, r12
0x18000d7cf  jz      loc_18000D912
0x18000d7d5  xor     ebx, ebx
0x18000d7d7  mov     dword ptr [rbp+3Fh+arg_20], 0
0x18000d7de  mov     [rbp+3Fh+var_80], 0
0x18000d7e6  mov     [rbp+3Fh+var_88], rbx
0x18000d7ea  test    rdi, rdi
0x18000d7ed  jz      loc_18000D87D
0x18000d7f3  lea     r8, _GUID_7268d1d3_d871_4b70_b1c0_79aefc11c9df; struct _GUID *
0x18000d7fa  mov     rdx, rdi; struct IUnknown *
0x18000d7fd  lea     rcx, [rbp+3Fh+var_80]; struct IUnknown **
0x18000d801  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x18000d806  test    rax, rax
0x18000d809  jz      short loc_18000D879
0x18000d80b  mov     rdi, [rbp+3Fh+var_80]
0x18000d80f  lea     rcx, [rbp+3Fh+var_60]
0x18000d813  mov     rax, [rdi]
0x18000d816  mov     rbx, [rax+20h]
0x18000d81a  call    ??$replace@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_SQLCEPROPVAL@@AEAV?$auto_array_ptr@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(tlx::auto_array_ptr<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)> &)
0x18000d81f  mov     rdx, [rbp+3Fh+arg_8]
0x18000d823  lea     rcx, [rbp+3Fh+arg_20]
0x18000d827  mov     [rsp+0E0h+var_B0], r13
0x18000d82c  movzx   r9d, r12w
0x18000d830  mov     [rsp+0E0h+var_B8], rcx
0x18000d835  mov     r8d, r14d
0x18000d838  mov     [rsp+0E0h+var_C0], rax
0x18000d83d  mov     rcx, rdi
0x18000d840  mov     rax, rbx
0x18000d843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d848  mov     ebx, eax
0x18000d84a  test    eax, eax
0x18000d84c  jns     loc_18000D8F1
0x18000d852  mov     r9d, 58h ; 'X'
0x18000d858  mov     edx, r14d
0x18000d85b  mov     ecx, eax
0x18000d85d  call    Log_HREvent_1
0x18000d862  lea     rcx, [rbp+3Fh+var_88]
0x18000d866  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d86b  lea     rcx, [rbp+3Fh+var_80]
0x18000d86f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d874  jmp     loc_18000DADA
0x18000d879  mov     rbx, [rbp+3Fh+var_88]
0x18000d87d  cmp     rbx, rdi
0x18000d880  jz      short loc_18000D89B
0x18000d882  lea     r8, _GUID_50911ab2_e54e_4d87_85ad_ca6ba91ab709; struct _GUID *
0x18000d889  mov     rdx, rdi; struct IUnknown *
0x18000d88c  lea     rcx, [rbp+3Fh+var_88]; struct IUnknown **
0x18000d890  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x18000d895  mov     rbx, [rbp+3Fh+var_88]
0x18000d899  jmp     short loc_18000D89E
0x18000d89b  mov     rax, rbx
0x18000d89e  test    rax, rax
0x18000d8a1  jz      loc_18000D9C8
0x18000d8a7  mov     rax, [rbx]
0x18000d8aa  lea     rcx, [rbp+3Fh+var_60]
0x18000d8ae  mov     rdi, [rax+18h]
0x18000d8b2  call    ??$replace@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_SQLCEPROPVAL@@AEAV?$auto_array_ptr@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(tlx::auto_array_ptr<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)> &)
0x18000d8b7  mov     rdx, [rbp+3Fh+arg_8]
0x18000d8bb  lea     rcx, [rbp+3Fh+arg_20]
0x18000d8bf  mov     [rsp+0E0h+var_B0], r13
0x18000d8c4  movzx   r9d, r12w
0x18000d8c8  mov     [rsp+0E0h+var_B8], rcx
0x18000d8cd  mov     r8d, r14d
0x18000d8d0  mov     [rsp+0E0h+var_C0], rax
0x18000d8d5  mov     rcx, rbx
0x18000d8d8  mov     rax, rdi
0x18000d8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8e0  mov     ebx, eax
0x18000d8e2  test    eax, eax
0x18000d8e4  jns     short loc_18000D8F1
0x18000d8e6  mov     r9d, 62h ; 'b'
0x18000d8ec  jmp     loc_18000D858
0x18000d8f1  mov     ecx, dword ptr [rbp+3Fh+arg_20]
0x18000d8f4  add     ecx, esi
0x18000d8f6  cmp     ecx, esi
0x18000d8f8  jb      loc_18000D9B8
0x18000d8fe  mov     esi, ecx
0x18000d900  lea     rcx, [rbp+3Fh+var_88]
0x18000d904  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d909  lea     rcx, [rbp+3Fh+var_80]
0x18000d90d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d912  test    esi, esi
0x18000d914  jz      loc_18000DAC2
0x18000d91a  mov     eax, [rbp+3Fh+var_90]
0x18000d91d  lea     r14, [rax+r12]
0x18000d921  cmp     r14, rax
0x18000d924  jb      loc_18000DAA9
0x18000d92a  mov     eax, 18h
0x18000d92f  mov     [rbp+3Fh+var_50], 0
0x18000d937  mul     r14
0x18000d93a  mov     rdi, rax
0x18000d93d  test    rdx, rdx
0x18000d940  jnz     loc_18000DAA1
0x18000d946  mov     ebx, esi
0x18000d948  cmp     rbx, rax
0x18000d94b  jb      loc_18000DA94
0x18000d951  mov     edx, ebx; uBytes
0x18000d953  xor     ecx, ecx; uFlags
0x18000d955  call    cs:__imp_LocalAlloc
0x18000d95b  mov     [rbp+3Fh+var_78], rax
0x18000d95f  mov     rsi, rax
0x18000d962  test    rax, rax
0x18000d965  jz      loc_18000DA75
0x18000d96b  sub     rbx, rdi
0x18000d96e  lea     rcx, [rax+rdi]
0x18000d972  mov     [rbp+3Fh+var_48], rbx
0x18000d976  xor     ebx, ebx
0x18000d978  mov     [rbp+3Fh+var_50], rcx
0x18000d97c  xor     edi, edi
0x18000d97e  lea     r13d, [rbx+1]
0x18000d982  cmp     rdi, r12
0x18000d985  jnb     short loc_18000D9FC
0x18000d987  mov     rax, [rbp+3Fh+var_60]
0x18000d98b  lea     rcx, [rbx+rbx*2]
0x18000d98f  lea     rdx, [rsi+rcx*8]
0x18000d993  lea     rcx, [rdi+rdi*2]
0x18000d997  lea     r9, [rbp+3Fh+var_48]
0x18000d99b  lea     rcx, [rax+rcx*8]
0x18000d99f  lea     r8, [rbp+3Fh+var_50]
0x18000d9a3  call    cs:__imp_CopyCEPROPVAL
0x18000d9a9  mov     r15d, eax
0x18000d9ac  test    eax, eax
0x18000d9ae  js      short loc_18000D9DA
0x18000d9b0  add     ebx, r13d
0x18000d9b3  add     rdi, r13
0x18000d9b6  jmp     short loc_18000D982
0x18000d9b8  mov     r9d, 6Ah ; 'j'
0x18000d9be  mov     edx, r14d
0x18000d9c1  mov     ebx, 80070216h
0x18000d9c6  jmp     short loc_18000D9D3
0x18000d9c8  xor     edx, edx
0x18000d9ca  mov     ebx, 8000FFFFh
0x18000d9cf  lea     r9d, [rdx+66h]
0x18000d9d3  mov     ecx, ebx
0x18000d9d5  jmp     loc_18000D85D
0x18000d9da  mov     r9d, 86h
0x18000d9e0  mov     edx, r13d
0x18000d9e3  mov     ecx, r15d
0x18000d9e6  call    Log_HREvent_1
0x18000d9eb  lea     rcx, [rbp+3Fh+var_78]
0x18000d9ef  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x18000d9f4  mov     ebx, r15d
0x18000d9f7  jmp     loc_18000DADA
0x18000d9fc  xor     edi, edi
0x18000d9fe  mov     eax, [rbp+3Fh+var_90]
0x18000da01  mov     ecx, ebx
0x18000da03  cmp     rdi, rax
0x18000da06  jnb     short loc_18000DA42
0x18000da08  mov     rcx, [rbp+3Fh+hMem]
0x18000da0c  lea     rax, [rbx+rbx*2]
0x18000da10  lea     rdx, [rsi+rax*8]
0x18000da14  lea     rax, [rdi+rdi*2]
0x18000da18  lea     r9, [rbp+3Fh+var_48]
0x18000da1c  mov     rcx, [rcx+rax*8+10h]
0x18000da21  lea     r8, [rbp+3Fh+var_50]
0x18000da25  call    cs:__imp_CopyCEPROPVAL
0x18000da2b  mov     r15d, eax
0x18000da2e  test    eax, eax
0x18000da30  js      short loc_18000DA3A
0x18000da32  add     ebx, r13d
0x18000da35  add     rdi, r13
0x18000da38  jmp     short loc_18000D9FE
0x18000da3a  mov     r9d, 8Ch
0x18000da40  jmp     short loc_18000D9E0
0x18000da42  cmp     rcx, r14
0x18000da45  jnz     short loc_18000DA68
0x18000da47  mov     rax, [rbp+3Fh+arg_30]
0x18000da4b  lea     rcx, [rbp+3Fh+var_78]
0x18000da4f  mov     [rbp+3Fh+var_78], 0
0x18000da57  mov     [rax], r14
0x18000da5a  mov     rax, [rbp+3Fh+arg_28]
0x18000da5e  mov     [rax], rsi
0x18000da61  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x18000da66  jmp     short loc_18000DAD8
0x18000da68  mov     ebx, 8000FFFFh
0x18000da6d  mov     r9d, 8Fh
0x18000da73  jmp     short loc_18000DA80
0x18000da75  mov     ebx, 8007000Eh
0x18000da7a  mov     r9d, 77h ; 'w'
0x18000da80  xor     edx, edx
0x18000da82  mov     ecx, ebx
0x18000da84  call    Log_HREvent_1
0x18000da89  lea     rcx, [rbp+3Fh+var_78]
0x18000da8d  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x18000da92  jmp     short loc_18000DADA
0x18000da94  xor     edx, edx
0x18000da96  mov     ebx, 80004005h
0x18000da9b  lea     r9d, [rdx+74h]
0x18000da9f  jmp     short loc_18000DAB9
0x18000daa1  mov     r9d, 73h ; 's'
0x18000daa7  jmp     short loc_18000DAAF
0x18000daa9  mov     r9d, 70h ; 'p'
0x18000daaf  mov     ebx, 80070216h
0x18000dab4  mov     edx, 1
0x18000dab9  mov     ecx, ebx
0x18000dabb  call    Log_HREvent_1
0x18000dac0  jmp     short loc_18000DADA
0x18000dac2  mov     rax, [rbp+3Fh+arg_30]
0x18000dac6  mov     qword ptr [rax], 0
0x18000dacd  mov     rax, [rbp+3Fh+arg_28]
0x18000dad1  mov     qword ptr [rax], 0
0x18000dad8  xor     ebx, ebx
0x18000dada  lea     rcx, [rbp+3Fh+hMem]
  ... truncated ...
```
