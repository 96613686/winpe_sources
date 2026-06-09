# EffectPackConfiguration::CreateDriverEffectPackConfiguration(IPropertyStore *,IPropertyStore *,std::shared_ptr<EffectPackConfiguration const> &)

- ea: `0x18002a278`
- end: `0x18002a82a`
- name: `?CreateDriverEffectPackConfiguration@EffectPackConfiguration@@SAJPEAUIPropertyStore@@0AEAV?$shared_ptr@$$CBUEffectPackConfiguration@@@std@@@Z`
- size: `1458`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002a1d0`

## callees

- `0x1800126bc`
- `0x180023690`
- `0x180025ce4`
- `0x180026d80`
- `0x1800280bc`
- `0x180028eb8`
- `0x180029500`
- `0x180029dc0`
- `0x18002a08c`
- `0x18002a278`
- `0x18002ac7c`
- `0x1800324a0`
- `0x1800cf8c0`
- `0x1800d0740`
- `0x1800d074c`
- `0x18016b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002a51f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002a51f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a421`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a485`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a4c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a708`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a796`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a7cb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a421`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a485`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a4c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a708`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a796`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a7cb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a3f2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a6d9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a3f2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a6d9`

## string_xrefs

- `0x18002a32c`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18002a40a`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18002a46e`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18002a505`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18002a6f1`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18002a77f`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall EffectPackConfiguration::CreateDriverEffectPackConfiguration(
        struct IPropertyStore *a1,
        struct IPropertyStore *a2,
        __int64 a3)
{
  struct IPropertyStore *v4; // rsi
  char *v5; // rax
  std::_Ref_count_base *v6; // rbx
  char *v7; // r13
  void *v9; // r14
  unsigned __int8 v10; // r15
  unsigned int v11; // eax
  __int64 v12; // rsi
  HRESULT v13; // eax
  unsigned int v14; // r14d
  struct IPropertyStore *v15; // r12
  int Configuration; // eax
  unsigned int v17; // esi
  char *v18; // r14
  char *v19; // r15
  __int64 v20; // rax
  __int64 v21; // rsi
  int v22; // r11d
  __int64 v23; // rcx
  int v24; // r12d
  __int64 v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rsi
  HRESULT v28; // eax
  unsigned int v29; // r14d
  CAudioSignalProcessingModeArray *v30; // rax
  int v31; // eax
  unsigned int v32; // r14d
  int v33; // [rsp+20h] [rbp-E8h]
  int v34; // [rsp+20h] [rbp-E8h]
  int v35; // [rsp+30h] [rbp-D8h]
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+48h] [rbp-C0h]
  _QWORD v38[2]; // [rsp+50h] [rbp-B8h] BYREF
  void *v39; // [rsp+60h] [rbp-A8h]
  struct IPropertyStore *v40; // [rsp+68h] [rbp-A0h]
  struct _GUID v41; // [rsp+70h] [rbp-98h] BYREF
  __int64 v42; // [rsp+80h] [rbp-88h]
  __int64 v43; // [rsp+88h] [rbp-80h]
  GUID pclsid; // [rsp+90h] [rbp-78h] BYREF
  _DWORD v45[3]; // [rsp+A0h] [rbp-68h] BYREF
  char v46; // [rsp+ACh] [rbp-5Ch] BYREF
  _DWORD v47[3]; // [rsp+B0h] [rbp-58h] BYREF
  char v48; // [rsp+BCh] [rbp-4Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v43 = a3;
  v40 = a2;
  v4 = a1;
  v39 = a1;
  v5 = (char *)operator new(0x818u);
  v6 = (std::_Ref_count_base *)v5;
  *(_QWORD *)&pclsid.Data1 = v5;
  if ( v5 )
  {
    *(_OWORD *)v5 = 0;
    *((_DWORD *)v5 + 2) = 1;
    *((_DWORD *)v5 + 3) = 1;
    *(_QWORD *)v5 = &std::_Ref_count_obj2<EffectPackConfiguration>::`vftable';
    v41 = (struct _GUID)DRIVER_APO_EFFECTPACK_ID;
    EffectPackConfiguration::EffectPackConfiguration((EffectPackConfiguration *)(v5 + 16), &v41);
  }
  else
  {
    v6 = 0;
  }
  v7 = (char *)v6 + 16;
  *(_QWORD *)&v41.Data1 = (char *)v6 + 16;
  *(_QWORD *)v41.Data4 = v6;
  if ( v6 == (std::_Ref_count_base *)-16LL )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BD,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
      (const char *)0x8007000ELL,
      v33);
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)0xFFFFFFFFFFFFFFF0LL);
    return 2147942414LL;
  }
  if ( !a2 || g_bIsGlobalDisableThirdPartyEnhancements )
  {
LABEL_60:
    std::shared_ptr<std::function<void (void)>>::operator=(v43, &v41);
    if ( *(_QWORD *)v41.Data4 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v41.Data4);
    return 0;
  }
  v9 = 0;
  v38[0] = 0;
  v38[1] = 0;
  v10 = 0;
  *(_OWORD *)pvar = 0;
  v37 = 0;
  if ( ((int (__fastcall *)(struct IPropertyStore *, void *, PROPVARIANT *))v4->lpVtbl->GetValue)(
         v4,
         &PKEY_Constrained_APO_ProcessingMode_List_For_Streaming,
         pvar) < 0
    || LOWORD(pvar[0]) != 4127
    || (v11 = (unsigned int)pvar[1]) == 0 )
  {
LABEL_25:
    PropVariantClear(pvar);
    v15 = v40;
    Configuration = EffectPackConfiguration::ReadConfiguration(
                      (__int64)v6 + 16,
                      (__int64)v40,
                      v40,
                      v4,
                      ((v10 ^ 1) << 6) | 0x10789u);
    v17 = Configuration;
    if ( Configuration < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2EC,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
        (const char *)(unsigned int)Configuration,
        v34);
      if ( v9 )
        free(v9);
      if ( v6 )
        std::_Ref_count_base::_Decref(v6);
      return v17;
    }
    if ( v10 )
    {
      v47[0] = 0;
      v47[1] = 1;
      v47[2] = 3;
      v18 = (char *)v47;
      do
      {
        v45[0] = 0;
        v45[1] = 1;
        v45[2] = 2;
        v19 = (char *)v45;
        v20 = 3LL * *(int *)v18;
        *(_QWORD *)&pclsid.Data1 = v20;
        do
        {
          v21 = 32 * (v20 + *(unsigned int *)v19);
          v22 = *(_DWORD *)&v7[v21 + 1328];
          v35 = v22;
          if ( v22 )
          {
            v23 = *(_QWORD *)&v7[v21 + 1336];
            v42 = v23;
            v24 = v22 - 1;
            if ( v22 - 1 >= 0 )
            {
              do
              {
                v39 = (void *)(v23 + 16LL * (unsigned int)v24);
                if ( (unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Find(v38, v39) == -1 )
                {
                  memcpy_0(v39, (const void *)(v25 + 16), 16LL * (unsigned int)(v22 - v24 - 1));
                  v22 = --v35;
                }
                --v24;
                v23 = v42;
              }
              while ( v24 >= 0 );
              v20 = *(_QWORD *)&pclsid.Data1;
            }
            *(_DWORD *)&v7[v21 + 1328] = v22;
          }
          v19 += 4;
        }
        while ( v19 != &v46 );
        v18 += 4;
      }
      while ( v18 != &v48 );
      v15 = v40;
    }
    *(_OWORD *)pvar = 0;
    v37 = 0;
    if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v15->lpVtbl->GetValue)(
           v15,
           &PKEY_APO_SWFallback_ProcessingModes,
           pvar) >= 0
      && LOWORD(pvar[0]) == 4127 )
    {
      v26 = (unsigned int)pvar[1];
      if ( LODWORD(pvar[1]) )
      {
        v27 = 0;
        while ( (unsigned int)v27 < v26 )
        {
          pclsid = 0;
          v28 = CLSIDFromString(*(LPCOLESTR *)(v37 + 8 * v27), &pclsid);
          v29 = v28;
          if ( v28 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x312,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
              (const char *)(unsigned int)v28,
              v34);
            PropVariantClear(pvar);
            ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(v38);
            if ( v6 )
              std::_Ref_count_base::_Decref(v6);
            return v29;
          }
          if ( memcmp_0(&pclsid, &GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf, 0x10u) )
          {
            v30 = (CAudioSignalProcessingModeArray *)gsl::span<CAudioSignalProcessingModeArray,-1>::operator[](
                                                       (char *)v6 + 2056,
                                                       0);
            v31 = CAudioSignalProcessingModeArray::AddMultiple(v30, 1u, &pclsid);
            v32 = v31;
            if ( v31 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x316,
                (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
                (const char *)(unsigned int)v31,
                v34);
              PropVariantClear(pvar);
              ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(v38);
              if ( v6 )
                std::_Ref_count_base::_Decref(v6);
              return v32;
            }
          }
          v27 = (unsigned int)(v27 + 1);
          v26 = (unsigned int)pvar[1];
        }
      }
    }
    PropVariantClear(pvar);
    ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(v38);
    goto LABEL_60;
  }
  v10 = 1;
  v12 = 0;
  while ( 1 )
  {
    if ( (unsigned int)v12 >= v11 )
    {
      v4 = (struct IPropertyStore *)v39;
      goto LABEL_25;
    }
    pclsid = 0;
    v13 = CLSIDFromString(*(LPCOLESTR *)(v37 + 8 * v12), &pclsid);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D0,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
        (const char *)(unsigned int)v13,
        v33);
      PropVariantClear(pvar);
      ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(v38);
      if ( v6 )
        std::_Ref_count_base::_Decref(v6);
      return v14;
    }
    if ( !(unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(v38, &pclsid) )
      break;
    v12 = (unsigned int)(v12 + 1);
    v9 = (void *)v38[0];
    v11 = (unsigned int)pvar[1];
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2D1,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
    (const char *)0x8007000ELL,
    v33);
  PropVariantClear(pvar);
  ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(v38);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002a278  push    rbx
0x18002a27a  push    rsi
0x18002a27b  push    rdi
0x18002a27c  push    r12
0x18002a27e  push    r13
0x18002a280  push    r14
0x18002a282  push    r15
0x18002a284  sub     rsp, 0D0h
0x18002a28b  mov     rax, cs:__security_cookie
0x18002a292  xor     rax, rsp
0x18002a295  mov     [rsp+108h+var_48], rax
0x18002a29d  mov     [rsp+108h+var_80], r8
0x18002a2a5  mov     r14, rdx
0x18002a2a8  mov     [rsp+108h+var_A0], rdx
0x18002a2ad  mov     rsi, rcx
0x18002a2b0  mov     [rsp+108h+var_A8], rcx
0x18002a2b5  mov     ecx, 818h; unsigned __int64
0x18002a2ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a2bf  mov     rbx, rax
0x18002a2c2  mov     qword ptr [rsp+108h+pclsid.Data1], rax
0x18002a2ca  mov     edi, 1
0x18002a2cf  test    rax, rax
0x18002a2d2  jz      short loc_18002A307
0x18002a2d4  xorps   xmm0, xmm0
0x18002a2d7  movups  xmmword ptr [rax], xmm0
0x18002a2da  mov     [rax+8], edi
0x18002a2dd  mov     [rax+0Ch], edi
0x18002a2e0  lea     rax, ??_7?$_Ref_count_obj2@UEffectPackConfiguration@@@std@@6B@; const std::_Ref_count_obj2<EffectPackConfiguration>::`vftable'
0x18002a2e7  mov     [rbx], rax
0x18002a2ea  movups  xmm0, cs:DRIVER_APO_EFFECTPACK_ID
0x18002a2f1  movdqu  xmmword ptr [rsp+108h+var_98.Data1], xmm0
0x18002a2f7  lea     rcx, [rbx+10h]; this
0x18002a2fb  lea     rdx, [rsp+108h+var_98]; struct _GUID
0x18002a300  call    ??0EffectPackConfiguration@@QEAA@U_GUID@@@Z; EffectPackConfiguration::EffectPackConfiguration(_GUID)
0x18002a305  jmp     short loc_18002A309
0x18002a307  xor     ebx, ebx
0x18002a309  lea     r13, [rbx+10h]
0x18002a30d  mov     qword ptr [rsp+108h+var_98.Data1], r13
0x18002a312  mov     qword ptr [rsp+108h+var_98.Data4], rbx
0x18002a317  test    r13, r13
0x18002a31a  jnz     short loc_18002A352
0x18002a31c  mov     rcx, [rsp+108h]; this
0x18002a324  mov     edi, 8007000Eh
0x18002a329  mov     r9d, edi; char *
0x18002a32c  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a333  mov     edx, 2BDh; void *
0x18002a338  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a33d  nop
0x18002a33e  test    rbx, rbx
0x18002a341  jz      short loc_18002A34B
0x18002a343  mov     rcx, rbx; this
0x18002a346  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a34b  mov     eax, edi
0x18002a34d  jmp     loc_18002A806
0x18002a352  test    r14, r14
0x18002a355  jz      loc_18002A7DC
0x18002a35b  cmp     cs:?g_bIsGlobalDisableThirdPartyEnhancements@@3HA, 0; int g_bIsGlobalDisableThirdPartyEnhancements
0x18002a362  jnz     loc_18002A7DC
0x18002a368  xor     r14d, r14d
0x18002a36b  mov     [rsp+108h+var_B8], r14
0x18002a370  mov     [rsp+108h+var_B0], r14
0x18002a375  xor     r15b, r15b
0x18002a378  xorps   xmm0, xmm0
0x18002a37b  xor     eax, eax
0x18002a37d  movups  xmmword ptr [rsp+108h+pvar], xmm0
0x18002a382  mov     [rsp+108h+var_C0], rax
0x18002a387  mov     rax, [rsi]
0x18002a38a  lea     r8, [rsp+108h+pvar]
0x18002a38f  lea     rdx, PKEY_Constrained_APO_ProcessingMode_List_For_Streaming
0x18002a396  mov     rcx, rsi
0x18002a399  mov     rax, [rax+28h]
0x18002a39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3a2  test    eax, eax
0x18002a3a4  js      loc_18002A4C1
0x18002a3aa  mov     r12d, 101Fh
0x18002a3b0  cmp     word ptr [rsp+108h+pvar], r12w
0x18002a3b6  jnz     loc_18002A4C1
0x18002a3bc  mov     rax, [rsp+108h+pvar+8]
0x18002a3c1  test    eax, eax
0x18002a3c3  jz      loc_18002A4C1
0x18002a3c9  mov     r15b, dil
0x18002a3cc  xor     esi, esi
0x18002a3ce  cmp     esi, eax
0x18002a3d0  jnb     loc_18002A4BC
0x18002a3d6  xorps   xmm0, xmm0
0x18002a3d9  movups  xmmword ptr [rsp+108h+pclsid.Data1], xmm0
0x18002a3e1  lea     rdx, [rsp+108h+pclsid]; pclsid
0x18002a3e9  mov     rcx, [rsp+108h+var_C0]
0x18002a3ee  mov     rcx, [rcx+rsi*8]; lpsz
0x18002a3f2  call    cs:__imp_CLSIDFromString
0x18002a3f8  mov     r14d, eax
0x18002a3fb  test    eax, eax
0x18002a3fd  jns     short loc_18002A448
0x18002a3ff  mov     rcx, [rsp+108h]; this
0x18002a407  mov     r9d, eax; char *
0x18002a40a  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a411  mov     edx, 2D0h; void *
0x18002a416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a41b  nop
0x18002a41c  lea     rcx, [rsp+108h+pvar]; pvar
0x18002a421  call    cs:__imp_PropVariantClear
0x18002a427  nop
0x18002a428  lea     rcx, [rsp+108h+var_B8]; void *
0x18002a42d  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x18002a432  nop
0x18002a433  test    rbx, rbx
0x18002a436  jz      short loc_18002A440
0x18002a438  mov     rcx, rbx; this
0x18002a43b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a440  mov     eax, r14d
0x18002a443  jmp     loc_18002A806
0x18002a448  lea     rdx, [rsp+108h+pclsid]
0x18002a450  lea     rcx, [rsp+108h+var_B8]
0x18002a455  call    ?Add@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(_GUID const &)
0x18002a45a  test    eax, eax
0x18002a45c  jnz     short loc_18002A4AB
0x18002a45e  mov     rcx, [rsp+108h]; this
0x18002a466  mov     edi, 8007000Eh
0x18002a46b  mov     r9d, edi; char *
0x18002a46e  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a475  mov     edx, 2D1h; void *
0x18002a47a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a47f  nop
0x18002a480  lea     rcx, [rsp+108h+pvar]; pvar
0x18002a485  call    cs:__imp_PropVariantClear
0x18002a48b  nop
0x18002a48c  lea     rcx, [rsp+108h+var_B8]; void *
0x18002a491  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x18002a496  nop
0x18002a497  test    rbx, rbx
0x18002a49a  jz      short loc_18002A4A4
0x18002a49c  mov     rcx, rbx; this
0x18002a49f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a4a4  mov     eax, edi
0x18002a4a6  jmp     loc_18002A806
0x18002a4ab  add     esi, edi
0x18002a4ad  mov     r14, [rsp+108h+var_B8]
0x18002a4b2  mov     rax, [rsp+108h+pvar+8]
0x18002a4b7  jmp     loc_18002A3CE
0x18002a4bc  mov     rsi, [rsp+108h+var_A8]
0x18002a4c1  lea     rcx, [rsp+108h+pvar]; pvar
0x18002a4c6  call    cs:__imp_PropVariantClear
0x18002a4cc  movzx   eax, r15b
0x18002a4d0  xor     eax, edi
0x18002a4d2  shl     eax, 6
0x18002a4d5  or      eax, 10789h
0x18002a4da  mov     [rsp+108h+var_E8], eax; int
0x18002a4de  mov     r9, rsi
0x18002a4e1  mov     r12, [rsp+108h+var_A0]
0x18002a4e6  mov     r8, r12
0x18002a4e9  mov     rdx, r12
0x18002a4ec  mov     rcx, r13
0x18002a4ef  call    ?ReadConfiguration@EffectPackConfiguration@@QEAAJPEAUIPropertyStore@@00W4ValidEffectPackConfigurationSettings@@@Z; EffectPackConfiguration::ReadConfiguration(IPropertyStore *,IPropertyStore *,IPropertyStore *,ValidEffectPackConfigurationSettings)
0x18002a4f4  mov     esi, eax
0x18002a4f6  test    eax, eax
0x18002a4f8  jns     short loc_18002A53A
0x18002a4fa  mov     rcx, [rsp+108h]; this
0x18002a502  mov     r9d, eax; char *
0x18002a505  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a50c  mov     edx, 2ECh; void *
0x18002a511  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a516  nop
0x18002a517  test    r14, r14
0x18002a51a  jz      short loc_18002A526
0x18002a51c  mov     rcx, r14; Block
0x18002a51f  call    cs:__imp_free
0x18002a525  nop
0x18002a526  test    rbx, rbx
0x18002a529  jz      short loc_18002A533
0x18002a52b  mov     rcx, rbx; this
0x18002a52e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a533  mov     eax, esi
0x18002a535  jmp     loc_18002A806
0x18002a53a  test    r15b, r15b
0x18002a53d  jz      loc_18002A663
0x18002a543  mov     [rsp+108h+var_58], 0
0x18002a54e  mov     [rsp+108h+var_54], edi
0x18002a555  mov     [rsp+108h+var_50], 3
0x18002a560  lea     r14, [rsp+108h+var_58]
0x18002a568  mov     [rsp+108h+var_68], 0
0x18002a573  mov     [rsp+108h+var_64], edi
0x18002a57a  mov     [rsp+108h+var_60], 2
0x18002a585  lea     r15, [rsp+108h+var_68]
0x18002a58d  movsxd  rax, dword ptr [r14]
0x18002a590  lea     rax, [rax+rax*2]
0x18002a594  mov     qword ptr [rsp+108h+pclsid.Data1], rax
0x18002a59c  mov     esi, [r15]
0x18002a59f  add     rsi, rax
0x18002a5a2  shl     rsi, 5
0x18002a5a6  mov     r11d, [rsi+r13+530h]
0x18002a5ae  mov     [rsp+108h+var_D8], r11d
0x18002a5b3  test    r11d, r11d
0x18002a5b6  jz      short loc_18002A634
0x18002a5b8  mov     rcx, [rsi+r13+538h]
0x18002a5c0  mov     [rsp+108h+var_88], rcx
0x18002a5c8  lea     r12d, [r11-1]
0x18002a5cc  test    r12d, r12d
0x18002a5cf  js      short loc_18002A62C
0x18002a5d1  mov     edx, r12d
0x18002a5d4  shl     rdx, 4
0x18002a5d8  add     rdx, rcx
0x18002a5db  mov     [rsp+108h+var_A8], rdx
0x18002a5e0  lea     rcx, [rsp+108h+var_B8]
0x18002a5e5  call    ?Find@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEBAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Find(_GUID const &)
0x18002a5ea  cmp     eax, 0FFFFFFFFh
0x18002a5ed  jnz     short loc_18002A617
0x18002a5ef  mov     r8d, r11d
0x18002a5f2  sub     r8d, r12d
0x18002a5f5  sub     r8d, edi
0x18002a5f8  shl     r8, 4; Size
0x18002a5fc  add     rdx, 10h; Src
0x18002a600  mov     rcx, [rsp+108h+var_A8]; void *
0x18002a605  call    memcpy_0
0x18002a60a  mov     r11d, [rsp+108h+var_D8]
0x18002a60f  dec     r11d
0x18002a612  mov     [rsp+108h+var_D8], r11d
0x18002a617  sub     r12d, edi
0x18002a61a  mov     rcx, [rsp+108h+var_88]
0x18002a622  jns     short loc_18002A5D1
0x18002a624  mov     rax, qword ptr [rsp+108h+pclsid.Data1]
0x18002a62c  mov     [rsi+r13+530h], r11d
0x18002a634  add     r15, 4
0x18002a638  lea     rcx, [rsp+108h+var_5C]
0x18002a640  cmp     r15, rcx
0x18002a643  jnz     loc_18002A59C
0x18002a649  add     r14, 4
0x18002a64d  lea     rax, [rsp+108h+var_4C]
0x18002a655  cmp     r14, rax
0x18002a658  jnz     loc_18002A568
0x18002a65e  mov     r12, [rsp+108h+var_A0]
0x18002a663  xorps   xmm0, xmm0
0x18002a666  xor     eax, eax
0x18002a668  movups  xmmword ptr [rsp+108h+pvar], xmm0
0x18002a66d  mov     [rsp+108h+var_C0], rax
0x18002a672  mov     rax, [r12]
0x18002a676  lea     r8, [rsp+108h+pvar]
0x18002a67b  lea     rdx, PKEY_APO_SWFallback_ProcessingModes
0x18002a682  mov     rcx, r12
0x18002a685  mov     rax, [rax+28h]
0x18002a689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a68e  test    eax, eax
0x18002a690  js      loc_18002A7C6
0x18002a696  mov     eax, 101Fh
0x18002a69b  cmp     word ptr [rsp+108h+pvar], ax
0x18002a6a0  jnz     loc_18002A7C6
0x18002a6a6  mov     rax, [rsp+108h+pvar+8]
0x18002a6ab  test    eax, eax
0x18002a6ad  jz      loc_18002A7C6
0x18002a6b3  xor     esi, esi
0x18002a6b5  cmp     esi, eax
0x18002a6b7  jnb     loc_18002A7C6
0x18002a6bd  xorps   xmm0, xmm0
0x18002a6c0  movups  xmmword ptr [rsp+108h+pclsid.Data1], xmm0
0x18002a6c8  lea     rdx, [rsp+108h+pclsid]; pclsid
0x18002a6d0  mov     rcx, [rsp+108h+var_C0]
0x18002a6d5  mov     rcx, [rcx+rsi*8]; lpsz
0x18002a6d9  call    cs:__imp_CLSIDFromString
0x18002a6df  mov     r14d, eax
0x18002a6e2  test    eax, eax
0x18002a6e4  jns     short loc_18002A72F
0x18002a6e6  mov     rcx, [rsp+108h]; this
0x18002a6ee  mov     r9d, eax; char *
0x18002a6f1  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a6f8  mov     edx, 312h; void *
0x18002a6fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a702  nop
0x18002a703  lea     rcx, [rsp+108h+pvar]; pvar
0x18002a708  call    cs:__imp_PropVariantClear
0x18002a70e  nop
0x18002a70f  lea     rcx, [rsp+108h+var_B8]; void *
0x18002a714  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x18002a719  nop
0x18002a71a  test    rbx, rbx
0x18002a71d  jz      short loc_18002A727
0x18002a71f  mov     rcx, rbx; this
0x18002a722  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a727  mov     eax, r14d
0x18002a72a  jmp     loc_18002A806
0x18002a72f  mov     r8d, 10h; Size
0x18002a735  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x18002a73c  lea     rcx, [rsp+108h+pclsid]; Buf1
0x18002a744  call    memcmp_0
0x18002a749  test    eax, eax
0x18002a74b  jz      short loc_18002A7BA
0x18002a74d  lea     rcx, [r13+7F8h]
0x18002a754  xor     edx, edx
0x18002a756  call    ??A?$span@VCAudioSignalProcessingModeArray@@$0?0@gsl@@QEBAAEAVCAudioSignalProcessingModeArray@@_K@Z; gsl::span<CAudioSignalProcessingModeArray,-1>::operator[](unsigned __int64)
0x18002a75b  lea     r8, [rsp+108h+pclsid]; struct _GUID *
0x18002a763  mov     edx, edi; unsigned int
0x18002a765  mov     rcx, rax; this
0x18002a768  call    ?AddMultiple@CAudioSignalProcessingModeArray@@QEAAJIPEBU_GUID@@@Z; CAudioSignalProcessingModeArray::AddMultiple(uint,_GUID const *)
0x18002a76d  mov     r14d, eax
0x18002a770  test    eax, eax
0x18002a772  jns     short loc_18002A7BA
0x18002a774  mov     rcx, [rsp+108h]; this
0x18002a77c  mov     r9d, eax; char *
0x18002a77f  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a786  mov     edx, 316h; void *
0x18002a78b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a790  nop
  ... truncated ...
```
