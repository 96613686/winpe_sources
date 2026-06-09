# EffectPack::FixupProcessingModeSupport(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)

- ea: `0x180027994`
- end: `0x180028058`
- name: `?FixupProcessingModeSupport@EffectPack@@AEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z`
- size: `1732`
- prototype: `__int64 __fastcall(EffectPack *__hidden this, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x1800b22e0`

## callees

- `0x18001280c`
- `0x180027780`
- `0x180027858`
- `0x180027994`
- `0x180028264`
- `0x180028870`
- `0x180028eb8`
- `0x180029018`
- `0x180029660`
- `0x180029f20`
- `0x18003f090`
- `0x1801527c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d24`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d38`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027e1b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027e3c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027e5c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d24`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027d38`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027e1b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027e3c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027e5c`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18002804a`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180028051`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18002804a`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180028051`

## string_xrefs

- `0x180027dd8`: `avcore\audiocore\server\lib\audioserviceutil\systemeffect.cpp`
- `0x180027a45`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027ab9`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027b6e`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027b86`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027c27`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027c3f`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027ce1`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027cf9`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027def`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027efd`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027f6d`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027fde`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EffectPack::FixupProcessingModeSupport(EffectPack *this, __int64 a2)
{
  unsigned __int64 v2; // rdi
  __int64 v4; // rsi
  int v5; // edx
  SystemEffectDescriptor *v6; // rax
  __int64 v7; // r8
  int v8; // eax
  unsigned int v9; // edi
  SystemEffectDescriptor *v11; // rax
  __int64 v12; // r8
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rsi
  __int64 v16; // rax
  unsigned int v17; // r15d
  __int64 v18; // r12
  unsigned int v19; // r14d
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  char v23; // r12
  __int64 v24; // rax
  unsigned int v25; // r15d
  __int64 v26; // r14
  unsigned int i; // esi
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rax
  unsigned int v31; // r14d
  __int64 v32; // r15
  unsigned int j; // esi
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  int v37; // r14d
  int v38; // esi
  __int64 v39; // rdx
  int k; // eax
  int m; // eax
  int n; // eax
  SystemEffectDescriptor *v43; // rax
  int v44; // eax
  __int64 v45; // rdx
  SystemEffectDescriptor *v46; // rax
  unsigned int ii; // esi
  __int64 v48; // rax
  _OWORD *v49; // rax
  SystemEffectDescriptor *v50; // rax
  int OverridingChain; // eax
  int v52; // [rsp+20h] [rbp-89h]
  int v53; // [rsp+20h] [rbp-89h]
  int v54; // [rsp+20h] [rbp-89h]
  int v55; // [rsp+20h] [rbp-89h]
  int v56; // [rsp+20h] [rbp-89h]
  int v57; // [rsp+20h] [rbp-89h]
  int v58; // [rsp+20h] [rbp-89h]
  void *v59; // [rsp+40h] [rbp-69h] BYREF
  __int64 v60; // [rsp+48h] [rbp-61h]
  void *v61; // [rsp+50h] [rbp-59h] BYREF
  __int64 v62; // [rsp+58h] [rbp-51h]
  void *Block; // [rsp+60h] [rbp-49h] BYREF
  __int64 v64; // [rsp+68h] [rbp-41h]
  struct _GUID v65; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v66[56]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v67; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v2 = (int)a2;
  v4 = (int)a2;
  if ( (unsigned __int64)(int)a2 >= *((_QWORD *)this + 202) )
    goto LABEL_84;
  if ( !*(_DWORD *)(*((_QWORD *)this + 203) + 4LL * (int)a2) )
  {
    if ( (_DWORD)a2 != 3
      && EffectPackConfiguration::AposRegisteredAsLfxGfx(*((EffectPackConfiguration **)this + 196))
      && !v5 )
    {
      v6 = (SystemEffectDescriptor *)gsl::span<SystemEffectDescriptor,-1>::operator[]((char *)this + 1440, v2);
      v7 = *((_QWORD *)this + 196);
      v65 = GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3;
      v8 = SystemEffectDescriptor::SetDefaultEffectChain(
             v6,
             &v65,
             *(_DWORD *)(v7 + 1792),
             *(const struct _GUID **)(v7 + 1800));
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD8D,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v8,
          v52);
        return v9;
      }
      v11 = (SystemEffectDescriptor *)gsl::span<SystemEffectDescriptor,-1>::operator[]((char *)this + 1456, v4);
      v12 = *((_QWORD *)this + 196);
      v65 = GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3;
      v13 = SystemEffectDescriptor::SetDefaultEffectChain(
              v11,
              &v65,
              *(_DWORD *)(v12 + 1808),
              *(const struct _GUID **)(v12 + 1816));
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD8E,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v13,
          v52);
        return v14;
      }
    }
    return 0;
  }
  if ( (a2 & 0xFFFFFFFC) != 0 || (_DWORD)a2 == 2 )
    return 0;
  v59 = 0;
  v60 = 0;
  v15 = 96LL * (int)a2;
  v16 = *((_QWORD *)this + 196);
  v17 = *(_DWORD *)(v16 + v15 + 1328);
  v18 = *(_QWORD *)(v16 + v15 + 1336);
  v19 = 0;
  v20 = *(_QWORD *)GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4;
  v21 = *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1;
  while ( v19 < v17 )
  {
    a2 = v18 + 16LL * v19;
    v22 = *(_QWORD *)a2 - v21;
    if ( *(_QWORD *)a2 == v21 )
      v22 = *(_QWORD *)(a2 + 8) - v20;
    if ( v22 )
    {
      if ( !(unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add((__int64)&v59, (_OWORD *)a2) )
      {
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E0,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x8007000ELL,
          v52);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD99,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x8007000ELL,
          v53);
LABEL_22:
        ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&v59);
        return v14;
      }
      v20 = *(_QWORD *)GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4;
      v21 = *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1;
    }
    ++v19;
  }
  v61 = 0;
  v62 = 0;
  v23 = *((_BYTE *)this + 1592);
  v24 = *((_QWORD *)this + 196);
  v25 = *(_DWORD *)(v24 + v15 + 1360);
  v26 = *(_QWORD *)(v24 + v15 + 1368);
  for ( i = 0; i < v25; ++i )
  {
    if ( v23 )
      goto LABEL_29;
    v28 = *(_QWORD *)(v26 + 16LL * i) - v21;
    if ( !v28 )
      v28 = *(_QWORD *)(v26 + 16LL * i + 8) - v20;
    if ( v28 )
    {
LABEL_29:
      if ( !(unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(
                            (__int64)&v61,
                            (_OWORD *)(v26 + 16LL * i)) )
      {
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E0,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x8007000ELL,
          v52);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD9D,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x8007000ELL,
          v54);
        ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&v61);
        goto LABEL_22;
      }
      v20 = *(_QWORD *)GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4;
      v21 = *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1;
    }
  }
  Block = 0;
  v64 = 0;
  v29 = 96 * v2;
  v30 = *((_QWORD *)this + 196);
  v31 = *(_DWORD *)(96 * v2 + v30 + 1392);
  v32 = *(_QWORD *)(96 * v2 + v30 + 1400);
  for ( j = 0; ; ++j )
  {
    if ( j >= v31 )
    {
      if ( v2 < *((_QWORD *)this + 180) )
      {
        v35 = *((_QWORD *)this + 196);
        v36 = *(unsigned int *)(96 * v2 + v35 + 1312);
        v37 = v60;
        if ( (int)v60 <= 0 )
        {
          v56 = *(_QWORD *)(96 * v2 + v35 + 1320);
          v38 = SystemEffectChainDescriptor::CreateEffectChain(&v59, 0, 0, (unsigned int)v36);
          if ( v38 < 0 )
          {
            v39 = 166;
            goto LABEL_53;
          }
        }
        else
        {
          v56 = 0;
          v38 = SystemEffectChainDescriptor::CreateEffectChain(&v59, v36, *(_QWORD *)(96 * v2 + v35 + 1320), 0);
          if ( v38 < 0 )
          {
            v39 = 161;
LABEL_53:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v39,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\systemeffect.cpp",
              (const char *)(unsigned int)v38,
              v56);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xDA6,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
              (const char *)(unsigned int)v38,
              v57);
            if ( Block )
            {
              for ( k = 0; k < (int)v64; ++k )
                ;
              free(Block);
            }
            if ( v61 )
            {
              for ( m = 0; m < (int)v62; ++m )
                ;
              free(v61);
            }
            if ( v59 )
            {
              for ( n = 0; n < v37; ++n )
                ;
              free(v59);
            }
            return (unsigned int)v38;
          }
        }
        v43 = (SystemEffectDescriptor *)gsl::span<SystemEffectDescriptor,-1>::operator[]((char *)this + 1456, v2);
        v44 = SystemEffectDescriptor::SetDefaultEffectChain(
                v43,
                (struct CAudioSignalProcessingModeArray *)&v61,
                *(_DWORD *)(96 * (v2 + 14) + *((_QWORD *)this + 196)),
                *(const struct _GUID **)(96 * v2 + *((_QWORD *)this + 196) + 1352));
        v38 = v44;
        if ( v44 < 0 )
        {
          v45 = 3498;
LABEL_70:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v45,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
            (const char *)(unsigned int)v44,
            v56);
LABEL_80:
          ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&Block);
          ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&v61);
          ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&v59);
          return (unsigned int)v38;
        }
        v46 = (SystemEffectDescriptor *)gsl::span<SystemEffectDescriptor,-1>::operator[]((char *)this + 1472, v2);
        v44 = SystemEffectDescriptor::SetDefaultEffectChain(
                v46,
                (struct CAudioSignalProcessingModeArray *)&Block,
                *(_DWORD *)(96 * v2 + *((_QWORD *)this + 196) + 1376),
                *(const struct _GUID **)(96 * v2 + *((_QWORD *)this + 196) + 1384));
        v38 = v44;
        if ( v44 < 0 )
        {
          v45 = 3502;
          goto LABEL_70;
        }
        *(_QWORD *)&v65.Data1 = 0;
        *(_QWORD *)v65.Data4 = 0;
        for ( ii = 0; (int)ii < v37; ++ii )
        {
          v48 = ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator[](&v59, ii);
          if ( (unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Find(&v61, v48) == -1 )
          {
            v49 = (_OWORD *)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator[](&v59, ii);
            if ( !(unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add((__int64)&v65, v49) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xDBF,
                (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
                (const char *)0x8007000ELL,
                v56);
              ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&v65);
              v38 = -2147024882;
              goto LABEL_80;
            }
          }
        }
        if ( *(int *)v65.Data4 > 0 )
        {
          v50 = (SystemEffectDescriptor *)gsl::span<SystemEffectDescriptor,-1>::operator[]((char *)this + 1456, v2);
          v67 = 0;
          OverridingChain = SystemEffectDescriptor::CreateOverridingChain(
                              v50,
                              (struct CAudioSignalProcessingModeArray *)&v65,
                              2,
                              1,
                              (__int64)v66);
          v38 = OverridingChain;
          if ( OverridingChain < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xDC6,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
              (const char *)(unsigned int)OverridingChain,
              v58);
            ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&v65);
            goto LABEL_80;
          }
        }
        ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&v65);
        ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&Block);
        ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&v61);
        ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(&v59);
        return 0;
      }
      _o_terminate(v29, a2);
LABEL_84:
      _o_terminate(this, a2);
      JUMPOUT(0x180028057LL);
    }
    a2 = v32 + 16LL * j;
    v34 = *(_QWORD *)a2 - v21;
    if ( *(_QWORD *)a2 == v21 )
      v34 = *(_QWORD *)(a2 + 8) - v20;
    if ( v34 )
      break;
LABEL_40:
    ;
  }
  if ( (unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add((__int64)&Block, (_OWORD *)a2) )
  {
    v20 = *(_QWORD *)GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4;
    v21 = *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1;
    goto LABEL_40;
  }
  v14 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4E0,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
    (const char *)0x8007000ELL,
    v52);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDA1,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
    (const char *)0x8007000ELL,
    v55);
  if ( Block )
    free(Block);
  if ( v61 )
    free(v61);
  if ( v59 )
    free(v59);
  return v14;
}

```

## disassembly

```asm
0x180027994  push    rbp
0x180027996  push    rbx
0x180027997  push    rsi
0x180027998  push    rdi
0x180027999  push    r12
0x18002799b  push    r13
0x18002799d  push    r14
0x18002799f  push    r15
0x1800279a1  lea     rbp, [rsp-1Fh]
0x1800279a6  sub     rsp, 0C8h
0x1800279ad  movsxd  rdi, edx
0x1800279b0  mov     rbx, rcx
0x1800279b3  mov     rsi, rdi
0x1800279b6  cmp     rdi, [rcx+650h]
0x1800279bd  jnb     loc_180028051
0x1800279c3  mov     rax, [rcx+658h]
0x1800279ca  xor     r13d, r13d
0x1800279cd  cmp     [rax+rdi*4], r13d
0x1800279d1  jnz     loc_180027ACE
0x1800279d7  cmp     edi, 3
0x1800279da  jz      loc_180028043
0x1800279e0  mov     rcx, [rcx+620h]; this
0x1800279e7  call    ?AposRegisteredAsLfxGfx@EffectPackConfiguration@@QEBA_NXZ; EffectPackConfiguration::AposRegisteredAsLfxGfx(void)
0x1800279ec  test    al, al
0x1800279ee  jz      loc_180028043
0x1800279f4  test    edx, edx
0x1800279f6  jnz     loc_180028043
0x1800279fc  lea     rcx, [rbx+5A0h]
0x180027a03  mov     rdx, rdi
0x180027a06  call    ??A?$span@VSystemEffectDescriptor@@$0?0@gsl@@QEBAAEAVSystemEffectDescriptor@@_K@Z; gsl::span<SystemEffectDescriptor,-1>::operator[](unsigned __int64)
0x180027a0b  mov     r8, [rbx+620h]
0x180027a12  movaps  xmm0, xmmword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x180027a19  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x180027a1e  mov     r9, [r8+708h]; struct _GUID *
0x180027a25  mov     r8d, [r8+700h]; unsigned int
0x180027a2c  lea     rdx, [rbp+57h+var_90]; struct _GUID
0x180027a30  mov     rcx, rax; this
0x180027a33  call    ?SetDefaultEffectChain@SystemEffectDescriptor@@QEAAJU_GUID@@IPEBU2@@Z; SystemEffectDescriptor::SetDefaultEffectChain(_GUID,uint,_GUID const *)
0x180027a38  mov     edi, eax
0x180027a3a  test    eax, eax
0x180027a3c  jns     short loc_180027A6C
0x180027a3e  mov     rcx, [rbp+5Fh]; this
0x180027a42  mov     r9d, eax; char *
0x180027a45  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027a4c  mov     edx, 0D8Dh; void *
0x180027a51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a56  mov     eax, edi
0x180027a58  add     rsp, 0C8h
0x180027a5f  pop     r15
0x180027a61  pop     r14
0x180027a63  pop     r13
0x180027a65  pop     r12
0x180027a67  pop     rdi
0x180027a68  pop     rsi
0x180027a69  pop     rbx
0x180027a6a  pop     rbp
0x180027a6b  retn
0x180027a6c  lea     rcx, [rbx+5B0h]
0x180027a73  mov     rdx, rsi
0x180027a76  call    ??A?$span@VSystemEffectDescriptor@@$0?0@gsl@@QEBAAEAVSystemEffectDescriptor@@_K@Z; gsl::span<SystemEffectDescriptor,-1>::operator[](unsigned __int64)
0x180027a7b  mov     r8, [rbx+620h]
0x180027a82  movaps  xmm0, xmmword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x180027a89  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x180027a8e  mov     r9, [r8+718h]; struct _GUID *
0x180027a95  mov     r8d, [r8+710h]; unsigned int
0x180027a9c  lea     rdx, [rbp+57h+var_90]; struct _GUID
0x180027aa0  mov     rcx, rax; this
0x180027aa3  call    ?SetDefaultEffectChain@SystemEffectDescriptor@@QEAAJU_GUID@@IPEBU2@@Z; SystemEffectDescriptor::SetDefaultEffectChain(_GUID,uint,_GUID const *)
0x180027aa8  mov     ebx, eax
0x180027aaa  test    eax, eax
0x180027aac  jns     loc_180028043
0x180027ab2  mov     rcx, [rbp+5Fh]; this
0x180027ab6  mov     r9d, eax; char *
0x180027ab9  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027ac0  mov     edx, 0D8Eh; void *
0x180027ac5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027aca  mov     eax, ebx
0x180027acc  jmp     short loc_180027A58
0x180027ace  test    edi, 0FFFFFFFCh
0x180027ad4  jnz     loc_180028043
0x180027ada  cmp     edi, 2
0x180027add  jz      loc_180028043
0x180027ae3  mov     [rbp+57h+var_C0], r13
0x180027ae7  mov     [rbp+57h+var_B8], r13
0x180027aeb  lea     rsi, [rdi+rdi*2]
0x180027aef  shl     rsi, 5
0x180027af3  mov     rax, [rcx+620h]
0x180027afa  mov     r15d, [rax+rsi+530h]
0x180027b02  mov     r12, [rax+rsi+538h]
0x180027b0a  mov     r14d, r13d
0x180027b0d  mov     r8, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x180027b14  mov     r9, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180027b1b  cmp     r14d, r15d
0x180027b1e  jnb     loc_180027BA6
0x180027b24  mov     edx, r14d
0x180027b27  shl     rdx, 4
0x180027b2b  add     rdx, r12
0x180027b2e  mov     rax, [rdx]
0x180027b31  sub     rax, r9
0x180027b34  jnz     short loc_180027B3D
0x180027b36  mov     rax, [rdx+8]
0x180027b3a  sub     rax, r8
0x180027b3d  test    rax, rax
0x180027b40  jz      short loc_180027B5D
0x180027b42  lea     rcx, [rbp+57h+var_C0]
0x180027b46  call    ?Add@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(_GUID const &)
0x180027b4b  test    eax, eax
0x180027b4d  jz      short loc_180027B62
0x180027b4f  mov     r8, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x180027b56  mov     r9, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180027b5d  inc     r14d
0x180027b60  jmp     short loc_180027B1B
0x180027b62  mov     rcx, [rbp+5Fh]; this
0x180027b66  mov     ebx, 8007000Eh
0x180027b6b  mov     r9d, ebx; char *
0x180027b6e  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027b75  mov     edx, 4E0h; void *
0x180027b7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027b7f  mov     rcx, [rbp+5Fh]; this
0x180027b83  mov     r9d, ebx; char *
0x180027b86  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027b8d  mov     edx, 0D99h; void *
0x180027b92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027b97  nop
0x180027b98  lea     rcx, [rbp+57h+var_C0]; void *
0x180027b9c  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x180027ba1  jmp     loc_180027ACA
0x180027ba6  mov     [rbp+57h+var_B0], r13
0x180027baa  mov     [rbp+57h+var_A8], r13
0x180027bae  mov     r12b, [rbx+638h]
0x180027bb5  mov     rax, [rbx+620h]
0x180027bbc  mov     r15d, [rax+rsi+550h]
0x180027bc4  mov     r14, [rax+rsi+558h]
0x180027bcc  mov     esi, r13d
0x180027bcf  cmp     esi, r15d
0x180027bd2  jnb     loc_180027C5F
0x180027bd8  mov     eax, esi
0x180027bda  add     rax, rax
0x180027bdd  test    r12b, r12b
0x180027be0  jnz     short loc_180027BF8
0x180027be2  mov     rcx, [r14+rax*8]
0x180027be6  sub     rcx, r9
0x180027be9  jnz     short loc_180027BF3
0x180027beb  mov     rcx, [r14+rax*8+8]
0x180027bf0  sub     rcx, r8
0x180027bf3  test    rcx, rcx
0x180027bf6  jz      short loc_180027C17
0x180027bf8  lea     rdx, [r14+rax*8]
0x180027bfc  lea     rcx, [rbp+57h+var_B0]
0x180027c00  call    ?Add@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(_GUID const &)
0x180027c05  test    eax, eax
0x180027c07  jz      short loc_180027C1B
0x180027c09  mov     r8, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x180027c10  mov     r9, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180027c17  inc     esi
0x180027c19  jmp     short loc_180027BCF
0x180027c1b  mov     rcx, [rbp+5Fh]; this
0x180027c1f  mov     ebx, 8007000Eh
0x180027c24  mov     r9d, ebx; char *
0x180027c27  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027c2e  mov     edx, 4E0h; void *
0x180027c33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c38  mov     rcx, [rbp+5Fh]; this
0x180027c3c  mov     r9d, ebx; char *
0x180027c3f  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027c46  mov     edx, 0D9Dh; void *
0x180027c4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c50  nop
0x180027c51  lea     rcx, [rbp+57h+var_B0]; void *
0x180027c55  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x180027c5a  jmp     loc_180027B98
0x180027c5f  mov     [rbp+57h+Block], r13
0x180027c63  mov     [rbp+57h+var_98], r13
0x180027c67  lea     rcx, [rdi+rdi*2]
0x180027c6b  shl     rcx, 5
0x180027c6f  mov     rax, [rbx+620h]
0x180027c76  mov     r14d, [rcx+rax+570h]
0x180027c7e  mov     r15, [rcx+rax+578h]
0x180027c86  mov     esi, r13d
0x180027c89  mov     r12d, 1
0x180027c8f  cmp     esi, r14d
0x180027c92  jnb     loc_180027D43
0x180027c98  mov     edx, esi
0x180027c9a  shl     rdx, 4
0x180027c9e  add     rdx, r15
0x180027ca1  mov     rax, [rdx]
0x180027ca4  sub     rax, r9
0x180027ca7  jnz     short loc_180027CB0
0x180027ca9  mov     rax, [rdx+8]
0x180027cad  sub     rax, r8
0x180027cb0  test    rax, rax
0x180027cb3  jz      short loc_180027CD0
0x180027cb5  lea     rcx, [rbp+57h+Block]
0x180027cb9  call    ?Add@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(_GUID const &)
0x180027cbe  test    eax, eax
0x180027cc0  jz      short loc_180027CD5
0x180027cc2  mov     r8, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x180027cc9  mov     r9, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180027cd0  add     esi, r12d
0x180027cd3  jmp     short loc_180027C8F
0x180027cd5  mov     rcx, [rbp+5Fh]; this
0x180027cd9  mov     ebx, 8007000Eh
0x180027cde  mov     r9d, ebx; char *
0x180027ce1  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027ce8  mov     edx, 4E0h; void *
0x180027ced  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027cf2  mov     rcx, [rbp+5Fh]; this
0x180027cf6  mov     r9d, ebx; char *
0x180027cf9  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027d00  mov     edx, 0DA1h; void *
0x180027d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027d0a  nop
0x180027d0b  mov     rcx, [rbp+57h+Block]; Block
0x180027d0f  test    rcx, rcx
0x180027d12  jz      short loc_180027D1B
0x180027d14  call    cs:__imp_free
0x180027d1a  nop
0x180027d1b  mov     rcx, [rbp+57h+var_B0]; Block
0x180027d1f  test    rcx, rcx
0x180027d22  jz      short loc_180027D2B
0x180027d24  call    cs:__imp_free
0x180027d2a  nop
0x180027d2b  mov     rcx, [rbp+57h+var_C0]; Block
0x180027d2f  test    rcx, rcx
0x180027d32  jz      loc_180027ACA
0x180027d38  call    cs:__imp_free
0x180027d3e  jmp     loc_180027ACA
0x180027d43  cmp     rdi, [rbx+5A0h]
0x180027d4a  jnb     loc_18002804A
0x180027d50  lea     rcx, [rdi+rdi*2]
0x180027d54  shl     rcx, 5
0x180027d58  mov     rax, [rbx+620h]
0x180027d5f  mov     r8, [rcx+rax+528h]
0x180027d67  mov     edx, [rcx+rax+520h]
0x180027d6e  lea     r9, [rdi+rdi*2]
0x180027d72  shl     r9, 5
0x180027d76  mov     rax, [rbx+5A8h]
0x180027d7d  add     rax, 10h
0x180027d81  add     r9, rax
0x180027d84  mov     r14d, dword ptr [rbp+57h+var_B8]
0x180027d88  mov     [rsp+100h+var_D8], r9
0x180027d8d  lea     rcx, [rbp+57h+var_C0]
0x180027d91  test    r14d, r14d
0x180027d94  jle     short loc_180027DB4
0x180027d96  mov     qword ptr [rsp+100h+var_E0], r13; int
0x180027d9b  xor     r9d, r9d
0x180027d9e  call    ?CreateEffectChain@SystemEffectChainDescriptor@@KAJAEAVCAudioSignalProcessingModeArray@@IPEBU_GUID@@I1AEAV?$shared_ptr@VSystemEffectChainDescriptor@@@std@@@Z; SystemEffectChainDescriptor::CreateEffectChain(CAudioSignalProcessingModeArray &,uint,_GUID const *,uint,_GUID const *,std::shared_ptr<SystemEffectChainDescriptor> &)
0x180027da3  mov     esi, eax
0x180027da5  test    eax, eax
0x180027da7  jns     loc_180027E69
0x180027dad  mov     edx, 0A1h
0x180027db2  jmp     short loc_180027DD5
0x180027db4  mov     qword ptr [rsp+100h+var_E0], r8; int
0x180027db9  mov     r9d, edx
0x180027dbc  xor     r8d, r8d
0x180027dbf  xor     edx, edx
0x180027dc1  call    ?CreateEffectChain@SystemEffectChainDescriptor@@KAJAEAVCAudioSignalProcessingModeArray@@IPEBU_GUID@@I1AEAV?$shared_ptr@VSystemEffectChainDescriptor@@@std@@@Z; SystemEffectChainDescriptor::CreateEffectChain(CAudioSignalProcessingModeArray &,uint,_GUID const *,uint,_GUID const *,std::shared_ptr<SystemEffectChainDescriptor> &)
0x180027dc6  mov     esi, eax
0x180027dc8  test    eax, eax
0x180027dca  jns     loc_180027E69
0x180027dd0  mov     edx, 0A6h; void *
0x180027dd5  mov     r9d, esi; char *
0x180027dd8  lea     r8, aAvcoreAudiocor_31; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027ddf  mov     rcx, [rbp+5Fh]; this
0x180027de3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027de8  mov     rcx, [rbp+5Fh]; this
0x180027dec  mov     r9d, esi; char *
0x180027def  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027df6  mov     edx, 0DA6h; void *
0x180027dfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027e00  nop
0x180027e01  mov     rcx, [rbp+57h+Block]; Block
0x180027e05  test    rcx, rcx
0x180027e08  jz      short loc_180027E22
0x180027e0a  mov     eax, r13d
0x180027e0d  mov     edx, dword ptr [rbp+57h+var_98]
0x180027e10  test    edx, edx
0x180027e12  jle     short loc_180027E1B
0x180027e14  add     eax, r12d
0x180027e17  cmp     eax, edx
0x180027e19  jl      short loc_180027E14
0x180027e1b  call    cs:__imp_free
0x180027e21  nop
0x180027e22  mov     rcx, [rbp+57h+var_B0]; Block
0x180027e26  test    rcx, rcx
0x180027e29  jz      short loc_180027E43
0x180027e2b  mov     eax, r13d
0x180027e2e  mov     edx, dword ptr [rbp+57h+var_A8]
0x180027e31  test    edx, edx
0x180027e33  jle     short loc_180027E3C
0x180027e35  add     eax, r12d
0x180027e38  cmp     eax, edx
0x180027e3a  jl      short loc_180027E35
0x180027e3c  call    cs:__imp_free
0x180027e42  nop
0x180027e43  mov     rcx, [rbp+57h+var_C0]; Block
0x180027e47  test    rcx, rcx
0x180027e4a  jz      short loc_180027E62
0x180027e4c  mov     eax, r13d
0x180027e4f  test    r14d, r14d
  ... truncated ...
```
