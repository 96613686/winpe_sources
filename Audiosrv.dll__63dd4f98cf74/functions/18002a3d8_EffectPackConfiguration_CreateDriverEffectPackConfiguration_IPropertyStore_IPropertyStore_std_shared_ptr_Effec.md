# EffectPackConfiguration::CreateDriverEffectPackConfiguration(IPropertyStore *,IPropertyStore *,std::shared_ptr<EffectPackConfiguration const> &)

- ea: `0x18002a3d8`
- end: `0x18002a98a`
- name: `?CreateDriverEffectPackConfiguration@EffectPackConfiguration@@SAJPEAUIPropertyStore@@0AEAV?$shared_ptr@$$CBUEffectPackConfiguration@@@std@@@Z`
- size: `1458`
- prototype: `__int64 __fastcall(struct IPropertyStore *, struct IPropertyStore *, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002a330`

## callees

- `0x18001280c`
- `0x1800237e0`
- `0x180025e34`
- `0x180026edc`
- `0x18002821c`
- `0x180029018`
- `0x180029660`
- `0x180029f20`
- `0x18002a1ec`
- `0x18002a3d8`
- `0x18002addc`
- `0x180032600`
- `0x1800cd8d0`
- `0x1800ce750`
- `0x1800ce75c`
- `0x18016c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002a67f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002a67f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a581`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a626`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a868`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a8f6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a92b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a581`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a626`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a868`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a8f6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a92b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a552`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a839`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a552`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a839`

## string_xrefs

- `0x18002a48c`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18002a56a`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18002a5ce`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18002a665`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18002a851`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18002a8df`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  if ( ((int (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v4->lpVtbl->GetValue)(
         v4,
         PKEY_Constrained_APO_ProcessingMode_List_For_Streaming,
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
    if ( !(unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add((__int64)v38, &pclsid) )
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
0x18002a3d8  push    rbx
0x18002a3da  push    rsi
0x18002a3db  push    rdi
0x18002a3dc  push    r12
0x18002a3de  push    r13
0x18002a3e0  push    r14
0x18002a3e2  push    r15
0x18002a3e4  sub     rsp, 0D0h
0x18002a3eb  mov     rax, cs:__security_cookie
0x18002a3f2  xor     rax, rsp
0x18002a3f5  mov     [rsp+108h+var_48], rax
0x18002a3fd  mov     [rsp+108h+var_80], r8
0x18002a405  mov     r14, rdx
0x18002a408  mov     [rsp+108h+var_A0], rdx
0x18002a40d  mov     rsi, rcx
0x18002a410  mov     [rsp+108h+var_A8], rcx
0x18002a415  mov     ecx, 818h; unsigned __int64
0x18002a41a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a41f  mov     rbx, rax
0x18002a422  mov     qword ptr [rsp+108h+pclsid.Data1], rax
0x18002a42a  mov     edi, 1
0x18002a42f  test    rax, rax
0x18002a432  jz      short loc_18002A467
0x18002a434  xorps   xmm0, xmm0
0x18002a437  movups  xmmword ptr [rax], xmm0
0x18002a43a  mov     [rax+8], edi
0x18002a43d  mov     [rax+0Ch], edi
0x18002a440  lea     rax, ??_7?$_Ref_count_obj2@UEffectPackConfiguration@@@std@@6B@; const std::_Ref_count_obj2<EffectPackConfiguration>::`vftable'
0x18002a447  mov     [rbx], rax
0x18002a44a  movups  xmm0, cs:DRIVER_APO_EFFECTPACK_ID
0x18002a451  movdqu  xmmword ptr [rsp+108h+var_98.Data1], xmm0
0x18002a457  lea     rcx, [rbx+10h]; this
0x18002a45b  lea     rdx, [rsp+108h+var_98]; struct _GUID
0x18002a460  call    ??0EffectPackConfiguration@@QEAA@U_GUID@@@Z; EffectPackConfiguration::EffectPackConfiguration(_GUID)
0x18002a465  jmp     short loc_18002A469
0x18002a467  xor     ebx, ebx
0x18002a469  lea     r13, [rbx+10h]
0x18002a46d  mov     qword ptr [rsp+108h+var_98.Data1], r13
0x18002a472  mov     qword ptr [rsp+108h+var_98.Data4], rbx
0x18002a477  test    r13, r13
0x18002a47a  jnz     short loc_18002A4B2
0x18002a47c  mov     rcx, [rsp+108h]; this
0x18002a484  mov     edi, 8007000Eh
0x18002a489  mov     r9d, edi; char *
0x18002a48c  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a493  mov     edx, 2BDh; void *
0x18002a498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a49d  nop
0x18002a49e  test    rbx, rbx
0x18002a4a1  jz      short loc_18002A4AB
0x18002a4a3  mov     rcx, rbx; this
0x18002a4a6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a4ab  mov     eax, edi
0x18002a4ad  jmp     loc_18002A966
0x18002a4b2  test    r14, r14
0x18002a4b5  jz      loc_18002A93C
0x18002a4bb  cmp     cs:?g_bIsGlobalDisableThirdPartyEnhancements@@3HA, 0; int g_bIsGlobalDisableThirdPartyEnhancements
0x18002a4c2  jnz     loc_18002A93C
0x18002a4c8  xor     r14d, r14d
0x18002a4cb  mov     [rsp+108h+var_B8], r14
0x18002a4d0  mov     [rsp+108h+var_B0], r14
0x18002a4d5  xor     r15b, r15b
0x18002a4d8  xorps   xmm0, xmm0
0x18002a4db  xor     eax, eax
0x18002a4dd  movups  xmmword ptr [rsp+108h+pvar], xmm0
0x18002a4e2  mov     [rsp+108h+var_C0], rax
0x18002a4e7  mov     rax, [rsi]
0x18002a4ea  lea     r8, [rsp+108h+pvar]
0x18002a4ef  lea     rdx, PKEY_Constrained_APO_ProcessingMode_List_For_Streaming
0x18002a4f6  mov     rcx, rsi
0x18002a4f9  mov     rax, [rax+28h]
0x18002a4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a502  test    eax, eax
0x18002a504  js      loc_18002A621
0x18002a50a  mov     r12d, 101Fh
0x18002a510  cmp     word ptr [rsp+108h+pvar], r12w
0x18002a516  jnz     loc_18002A621
0x18002a51c  mov     rax, [rsp+108h+pvar+8]
0x18002a521  test    eax, eax
0x18002a523  jz      loc_18002A621
0x18002a529  mov     r15b, dil
0x18002a52c  xor     esi, esi
0x18002a52e  cmp     esi, eax
0x18002a530  jnb     loc_18002A61C
0x18002a536  xorps   xmm0, xmm0
0x18002a539  movups  xmmword ptr [rsp+108h+pclsid.Data1], xmm0
0x18002a541  lea     rdx, [rsp+108h+pclsid]; pclsid
0x18002a549  mov     rcx, [rsp+108h+var_C0]
0x18002a54e  mov     rcx, [rcx+rsi*8]; lpsz
0x18002a552  call    cs:__imp_CLSIDFromString
0x18002a558  mov     r14d, eax
0x18002a55b  test    eax, eax
0x18002a55d  jns     short loc_18002A5A8
0x18002a55f  mov     rcx, [rsp+108h]; this
0x18002a567  mov     r9d, eax; char *
0x18002a56a  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a571  mov     edx, 2D0h; void *
0x18002a576  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a57b  nop
0x18002a57c  lea     rcx, [rsp+108h+pvar]; pvar
0x18002a581  call    cs:__imp_PropVariantClear
0x18002a587  nop
0x18002a588  lea     rcx, [rsp+108h+var_B8]; void *
0x18002a58d  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x18002a592  nop
0x18002a593  test    rbx, rbx
0x18002a596  jz      short loc_18002A5A0
0x18002a598  mov     rcx, rbx; this
0x18002a59b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a5a0  mov     eax, r14d
0x18002a5a3  jmp     loc_18002A966
0x18002a5a8  lea     rdx, [rsp+108h+pclsid]
0x18002a5b0  lea     rcx, [rsp+108h+var_B8]
0x18002a5b5  call    ?Add@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(_GUID const &)
0x18002a5ba  test    eax, eax
0x18002a5bc  jnz     short loc_18002A60B
0x18002a5be  mov     rcx, [rsp+108h]; this
0x18002a5c6  mov     edi, 8007000Eh
0x18002a5cb  mov     r9d, edi; char *
0x18002a5ce  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a5d5  mov     edx, 2D1h; void *
0x18002a5da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a5df  nop
0x18002a5e0  lea     rcx, [rsp+108h+pvar]; pvar
0x18002a5e5  call    cs:__imp_PropVariantClear
0x18002a5eb  nop
0x18002a5ec  lea     rcx, [rsp+108h+var_B8]; void *
0x18002a5f1  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x18002a5f6  nop
0x18002a5f7  test    rbx, rbx
0x18002a5fa  jz      short loc_18002A604
0x18002a5fc  mov     rcx, rbx; this
0x18002a5ff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a604  mov     eax, edi
0x18002a606  jmp     loc_18002A966
0x18002a60b  add     esi, edi
0x18002a60d  mov     r14, [rsp+108h+var_B8]
0x18002a612  mov     rax, [rsp+108h+pvar+8]
0x18002a617  jmp     loc_18002A52E
0x18002a61c  mov     rsi, [rsp+108h+var_A8]
0x18002a621  lea     rcx, [rsp+108h+pvar]; pvar
0x18002a626  call    cs:__imp_PropVariantClear
0x18002a62c  movzx   eax, r15b
0x18002a630  xor     eax, edi
0x18002a632  shl     eax, 6
0x18002a635  or      eax, 10789h
0x18002a63a  mov     [rsp+108h+var_E8], eax; int
0x18002a63e  mov     r9, rsi
0x18002a641  mov     r12, [rsp+108h+var_A0]
0x18002a646  mov     r8, r12
0x18002a649  mov     rdx, r12
0x18002a64c  mov     rcx, r13
0x18002a64f  call    ?ReadConfiguration@EffectPackConfiguration@@QEAAJPEAUIPropertyStore@@00W4ValidEffectPackConfigurationSettings@@@Z; EffectPackConfiguration::ReadConfiguration(IPropertyStore *,IPropertyStore *,IPropertyStore *,ValidEffectPackConfigurationSettings)
0x18002a654  mov     esi, eax
0x18002a656  test    eax, eax
0x18002a658  jns     short loc_18002A69A
0x18002a65a  mov     rcx, [rsp+108h]; this
0x18002a662  mov     r9d, eax; char *
0x18002a665  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a66c  mov     edx, 2ECh; void *
0x18002a671  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a676  nop
0x18002a677  test    r14, r14
0x18002a67a  jz      short loc_18002A686
0x18002a67c  mov     rcx, r14; Block
0x18002a67f  call    cs:__imp_free
0x18002a685  nop
0x18002a686  test    rbx, rbx
0x18002a689  jz      short loc_18002A693
0x18002a68b  mov     rcx, rbx; this
0x18002a68e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a693  mov     eax, esi
0x18002a695  jmp     loc_18002A966
0x18002a69a  test    r15b, r15b
0x18002a69d  jz      loc_18002A7C3
0x18002a6a3  mov     [rsp+108h+var_58], 0
0x18002a6ae  mov     [rsp+108h+var_54], edi
0x18002a6b5  mov     [rsp+108h+var_50], 3
0x18002a6c0  lea     r14, [rsp+108h+var_58]
0x18002a6c8  mov     [rsp+108h+var_68], 0
0x18002a6d3  mov     [rsp+108h+var_64], edi
0x18002a6da  mov     [rsp+108h+var_60], 2
0x18002a6e5  lea     r15, [rsp+108h+var_68]
0x18002a6ed  movsxd  rax, dword ptr [r14]
0x18002a6f0  lea     rax, [rax+rax*2]
0x18002a6f4  mov     qword ptr [rsp+108h+pclsid.Data1], rax
0x18002a6fc  mov     esi, [r15]
0x18002a6ff  add     rsi, rax
0x18002a702  shl     rsi, 5
0x18002a706  mov     r11d, [rsi+r13+530h]
0x18002a70e  mov     [rsp+108h+var_D8], r11d
0x18002a713  test    r11d, r11d
0x18002a716  jz      short loc_18002A794
0x18002a718  mov     rcx, [rsi+r13+538h]
0x18002a720  mov     [rsp+108h+var_88], rcx
0x18002a728  lea     r12d, [r11-1]
0x18002a72c  test    r12d, r12d
0x18002a72f  js      short loc_18002A78C
0x18002a731  mov     edx, r12d
0x18002a734  shl     rdx, 4
0x18002a738  add     rdx, rcx
0x18002a73b  mov     [rsp+108h+var_A8], rdx
0x18002a740  lea     rcx, [rsp+108h+var_B8]
0x18002a745  call    ?Find@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEBAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Find(_GUID const &)
0x18002a74a  cmp     eax, 0FFFFFFFFh
0x18002a74d  jnz     short loc_18002A777
0x18002a74f  mov     r8d, r11d
0x18002a752  sub     r8d, r12d
0x18002a755  sub     r8d, edi
0x18002a758  shl     r8, 4; Size
0x18002a75c  add     rdx, 10h; Src
0x18002a760  mov     rcx, [rsp+108h+var_A8]; void *
0x18002a765  call    memcpy_0
0x18002a76a  mov     r11d, [rsp+108h+var_D8]
0x18002a76f  dec     r11d
0x18002a772  mov     [rsp+108h+var_D8], r11d
0x18002a777  sub     r12d, edi
0x18002a77a  mov     rcx, [rsp+108h+var_88]
0x18002a782  jns     short loc_18002A731
0x18002a784  mov     rax, qword ptr [rsp+108h+pclsid.Data1]
0x18002a78c  mov     [rsi+r13+530h], r11d
0x18002a794  add     r15, 4
0x18002a798  lea     rcx, [rsp+108h+var_5C]
0x18002a7a0  cmp     r15, rcx
0x18002a7a3  jnz     loc_18002A6FC
0x18002a7a9  add     r14, 4
0x18002a7ad  lea     rax, [rsp+108h+var_4C]
0x18002a7b5  cmp     r14, rax
0x18002a7b8  jnz     loc_18002A6C8
0x18002a7be  mov     r12, [rsp+108h+var_A0]
0x18002a7c3  xorps   xmm0, xmm0
0x18002a7c6  xor     eax, eax
0x18002a7c8  movups  xmmword ptr [rsp+108h+pvar], xmm0
0x18002a7cd  mov     [rsp+108h+var_C0], rax
0x18002a7d2  mov     rax, [r12]
0x18002a7d6  lea     r8, [rsp+108h+pvar]
0x18002a7db  lea     rdx, PKEY_APO_SWFallback_ProcessingModes
0x18002a7e2  mov     rcx, r12
0x18002a7e5  mov     rax, [rax+28h]
0x18002a7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7ee  test    eax, eax
0x18002a7f0  js      loc_18002A926
0x18002a7f6  mov     eax, 101Fh
0x18002a7fb  cmp     word ptr [rsp+108h+pvar], ax
0x18002a800  jnz     loc_18002A926
0x18002a806  mov     rax, [rsp+108h+pvar+8]
0x18002a80b  test    eax, eax
0x18002a80d  jz      loc_18002A926
0x18002a813  xor     esi, esi
0x18002a815  cmp     esi, eax
0x18002a817  jnb     loc_18002A926
0x18002a81d  xorps   xmm0, xmm0
0x18002a820  movups  xmmword ptr [rsp+108h+pclsid.Data1], xmm0
0x18002a828  lea     rdx, [rsp+108h+pclsid]; pclsid
0x18002a830  mov     rcx, [rsp+108h+var_C0]
0x18002a835  mov     rcx, [rcx+rsi*8]; lpsz
0x18002a839  call    cs:__imp_CLSIDFromString
0x18002a83f  mov     r14d, eax
0x18002a842  test    eax, eax
0x18002a844  jns     short loc_18002A88F
0x18002a846  mov     rcx, [rsp+108h]; this
0x18002a84e  mov     r9d, eax; char *
0x18002a851  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a858  mov     edx, 312h; void *
0x18002a85d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a862  nop
0x18002a863  lea     rcx, [rsp+108h+pvar]; pvar
0x18002a868  call    cs:__imp_PropVariantClear
0x18002a86e  nop
0x18002a86f  lea     rcx, [rsp+108h+var_B8]; void *
0x18002a874  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x18002a879  nop
0x18002a87a  test    rbx, rbx
0x18002a87d  jz      short loc_18002A887
0x18002a87f  mov     rcx, rbx; this
0x18002a882  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a887  mov     eax, r14d
0x18002a88a  jmp     loc_18002A966
0x18002a88f  mov     r8d, 10h; Size
0x18002a895  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x18002a89c  lea     rcx, [rsp+108h+pclsid]; Buf1
0x18002a8a4  call    memcmp_0
0x18002a8a9  test    eax, eax
0x18002a8ab  jz      short loc_18002A91A
0x18002a8ad  lea     rcx, [r13+7F8h]
0x18002a8b4  xor     edx, edx
0x18002a8b6  call    ??A?$span@VCAudioSignalProcessingModeArray@@$0?0@gsl@@QEBAAEAVCAudioSignalProcessingModeArray@@_K@Z; gsl::span<CAudioSignalProcessingModeArray,-1>::operator[](unsigned __int64)
0x18002a8bb  lea     r8, [rsp+108h+pclsid]; struct _GUID *
0x18002a8c3  mov     edx, edi; unsigned int
0x18002a8c5  mov     rcx, rax; this
0x18002a8c8  call    ?AddMultiple@CAudioSignalProcessingModeArray@@QEAAJIPEBU_GUID@@@Z; CAudioSignalProcessingModeArray::AddMultiple(uint,_GUID const *)
0x18002a8cd  mov     r14d, eax
0x18002a8d0  test    eax, eax
0x18002a8d2  jns     short loc_18002A91A
0x18002a8d4  mov     rcx, [rsp+108h]; this
0x18002a8dc  mov     r9d, eax; char *
0x18002a8df  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002a8e6  mov     edx, 316h; void *
0x18002a8eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a8f0  nop
  ... truncated ...
```
