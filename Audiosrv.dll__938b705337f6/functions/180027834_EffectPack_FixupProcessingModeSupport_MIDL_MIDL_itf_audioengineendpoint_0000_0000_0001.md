# EffectPack::FixupProcessingModeSupport(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)

- ea: `0x180027834`
- end: `0x180027ef8`
- name: `?FixupProcessingModeSupport@EffectPack@@AEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z`
- size: `1732`
- prototype: `__int64 __fastcall(EffectPack *__hidden this, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x1800b3fd0`

## callees

- `0x1800126bc`
- `0x180027620`
- `0x1800276f8`
- `0x180027834`
- `0x180028104`
- `0x180028710`
- `0x180028d58`
- `0x180028eb8`
- `0x180029500`
- `0x180029dc0`
- `0x18003ef20`
- `0x180151ab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027bb4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027bc4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027bd8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027cbb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027cdc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027cfc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027bb4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027bc4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027bd8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027cbb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027cdc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027cfc`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180027eea`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180027ef1`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180027eea`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180027ef1`

## string_xrefs

- `0x180027c78`: `avcore\audiocore\server\lib\audioserviceutil\systemeffect.cpp`
- `0x1800278e5`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027959`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027a0e`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027a26`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027ac7`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027adf`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027b81`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027b99`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027c8f`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027d9d`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027e0d`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180027e7e`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
  __int64 v49; // rax
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
          (void *)0xD8E,
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
          (void *)0xD8F,
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
      if ( !(unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(&v59, a2) )
      {
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E1,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x8007000ELL,
          v52);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD9A,
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
      if ( !(unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(&v61, v26 + 16LL * i) )
      {
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E1,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x8007000ELL,
          v52);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD9E,
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
              (void *)0xDA7,
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
          v45 = 3499;
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
          v45 = 3503;
          goto LABEL_70;
        }
        *(_QWORD *)&v65.Data1 = 0;
        *(_QWORD *)v65.Data4 = 0;
        for ( ii = 0; (int)ii < v37; ++ii )
        {
          v48 = ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator[](&v59, ii);
          if ( (unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Find(&v61, v48) == -1 )
          {
            v49 = ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator[](&v59, ii);
            if ( !(unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(&v65, v49) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xDC0,
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
              (void *)0xDC7,
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
      JUMPOUT(0x180027EF7LL);
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
  if ( (unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(&Block, a2) )
  {
    v20 = *(_QWORD *)GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4;
    v21 = *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1;
    goto LABEL_40;
  }
  v14 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4E1,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
    (const char *)0x8007000ELL,
    v52);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDA2,
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
0x180027834  push    rbp
0x180027836  push    rbx
0x180027837  push    rsi
0x180027838  push    rdi
0x180027839  push    r12
0x18002783b  push    r13
0x18002783d  push    r14
0x18002783f  push    r15
0x180027841  lea     rbp, [rsp-1Fh]
0x180027846  sub     rsp, 0C8h
0x18002784d  movsxd  rdi, edx
0x180027850  mov     rbx, rcx
0x180027853  mov     rsi, rdi
0x180027856  cmp     rdi, [rcx+650h]
0x18002785d  jnb     loc_180027EF1
0x180027863  mov     rax, [rcx+658h]
0x18002786a  xor     r13d, r13d
0x18002786d  cmp     [rax+rdi*4], r13d
0x180027871  jnz     loc_18002796E
0x180027877  cmp     edi, 3
0x18002787a  jz      loc_180027EE3
0x180027880  mov     rcx, [rcx+620h]; this
0x180027887  call    ?AposRegisteredAsLfxGfx@EffectPackConfiguration@@QEBA_NXZ; EffectPackConfiguration::AposRegisteredAsLfxGfx(void)
0x18002788c  test    al, al
0x18002788e  jz      loc_180027EE3
0x180027894  test    edx, edx
0x180027896  jnz     loc_180027EE3
0x18002789c  lea     rcx, [rbx+5A0h]
0x1800278a3  mov     rdx, rdi
0x1800278a6  call    ??A?$span@VSystemEffectDescriptor@@$0?0@gsl@@QEBAAEAVSystemEffectDescriptor@@_K@Z; gsl::span<SystemEffectDescriptor,-1>::operator[](unsigned __int64)
0x1800278ab  mov     r8, [rbx+620h]
0x1800278b2  movaps  xmm0, xmmword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x1800278b9  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x1800278be  mov     r9, [r8+708h]; struct _GUID *
0x1800278c5  mov     r8d, [r8+700h]; unsigned int
0x1800278cc  lea     rdx, [rbp+57h+var_90]; struct _GUID
0x1800278d0  mov     rcx, rax; this
0x1800278d3  call    ?SetDefaultEffectChain@SystemEffectDescriptor@@QEAAJU_GUID@@IPEBU2@@Z; SystemEffectDescriptor::SetDefaultEffectChain(_GUID,uint,_GUID const *)
0x1800278d8  mov     edi, eax
0x1800278da  test    eax, eax
0x1800278dc  jns     short loc_18002790C
0x1800278de  mov     rcx, [rbp+5Fh]; this
0x1800278e2  mov     r9d, eax; char *
0x1800278e5  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800278ec  mov     edx, 0D8Eh; void *
0x1800278f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800278f6  mov     eax, edi
0x1800278f8  add     rsp, 0C8h
0x1800278ff  pop     r15
0x180027901  pop     r14
0x180027903  pop     r13
0x180027905  pop     r12
0x180027907  pop     rdi
0x180027908  pop     rsi
0x180027909  pop     rbx
0x18002790a  pop     rbp
0x18002790b  retn
0x18002790c  lea     rcx, [rbx+5B0h]
0x180027913  mov     rdx, rsi
0x180027916  call    ??A?$span@VSystemEffectDescriptor@@$0?0@gsl@@QEBAAEAVSystemEffectDescriptor@@_K@Z; gsl::span<SystemEffectDescriptor,-1>::operator[](unsigned __int64)
0x18002791b  mov     r8, [rbx+620h]
0x180027922  movaps  xmm0, xmmword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x180027929  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x18002792e  mov     r9, [r8+718h]; struct _GUID *
0x180027935  mov     r8d, [r8+710h]; unsigned int
0x18002793c  lea     rdx, [rbp+57h+var_90]; struct _GUID
0x180027940  mov     rcx, rax; this
0x180027943  call    ?SetDefaultEffectChain@SystemEffectDescriptor@@QEAAJU_GUID@@IPEBU2@@Z; SystemEffectDescriptor::SetDefaultEffectChain(_GUID,uint,_GUID const *)
0x180027948  mov     ebx, eax
0x18002794a  test    eax, eax
0x18002794c  jns     loc_180027EE3
0x180027952  mov     rcx, [rbp+5Fh]; this
0x180027956  mov     r9d, eax; char *
0x180027959  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027960  mov     edx, 0D8Fh; void *
0x180027965  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002796a  mov     eax, ebx
0x18002796c  jmp     short loc_1800278F8
0x18002796e  test    edi, 0FFFFFFFCh
0x180027974  jnz     loc_180027EE3
0x18002797a  cmp     edi, 2
0x18002797d  jz      loc_180027EE3
0x180027983  mov     [rbp+57h+var_C0], r13
0x180027987  mov     [rbp+57h+var_B8], r13
0x18002798b  lea     rsi, [rdi+rdi*2]
0x18002798f  shl     rsi, 5
0x180027993  mov     rax, [rcx+620h]
0x18002799a  mov     r15d, [rax+rsi+530h]
0x1800279a2  mov     r12, [rax+rsi+538h]
0x1800279aa  mov     r14d, r13d
0x1800279ad  mov     r8, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x1800279b4  mov     r9, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x1800279bb  cmp     r14d, r15d
0x1800279be  jnb     loc_180027A46
0x1800279c4  mov     edx, r14d
0x1800279c7  shl     rdx, 4
0x1800279cb  add     rdx, r12
0x1800279ce  mov     rax, [rdx]
0x1800279d1  sub     rax, r9
0x1800279d4  jnz     short loc_1800279DD
0x1800279d6  mov     rax, [rdx+8]
0x1800279da  sub     rax, r8
0x1800279dd  test    rax, rax
0x1800279e0  jz      short loc_1800279FD
0x1800279e2  lea     rcx, [rbp+57h+var_C0]
0x1800279e6  call    ?Add@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(_GUID const &)
0x1800279eb  test    eax, eax
0x1800279ed  jz      short loc_180027A02
0x1800279ef  mov     r8, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x1800279f6  mov     r9, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x1800279fd  inc     r14d
0x180027a00  jmp     short loc_1800279BB
0x180027a02  mov     rcx, [rbp+5Fh]; this
0x180027a06  mov     ebx, 8007000Eh
0x180027a0b  mov     r9d, ebx; char *
0x180027a0e  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027a15  mov     edx, 4E1h; void *
0x180027a1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a1f  mov     rcx, [rbp+5Fh]; this
0x180027a23  mov     r9d, ebx; char *
0x180027a26  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027a2d  mov     edx, 0D9Ah; void *
0x180027a32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a37  nop
0x180027a38  lea     rcx, [rbp+57h+var_C0]; void *
0x180027a3c  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x180027a41  jmp     loc_18002796A
0x180027a46  mov     [rbp+57h+var_B0], r13
0x180027a4a  mov     [rbp+57h+var_A8], r13
0x180027a4e  mov     r12b, [rbx+638h]
0x180027a55  mov     rax, [rbx+620h]
0x180027a5c  mov     r15d, [rax+rsi+550h]
0x180027a64  mov     r14, [rax+rsi+558h]
0x180027a6c  mov     esi, r13d
0x180027a6f  cmp     esi, r15d
0x180027a72  jnb     loc_180027AFF
0x180027a78  mov     eax, esi
0x180027a7a  add     rax, rax
0x180027a7d  test    r12b, r12b
0x180027a80  jnz     short loc_180027A98
0x180027a82  mov     rcx, [r14+rax*8]
0x180027a86  sub     rcx, r9
0x180027a89  jnz     short loc_180027A93
0x180027a8b  mov     rcx, [r14+rax*8+8]
0x180027a90  sub     rcx, r8
0x180027a93  test    rcx, rcx
0x180027a96  jz      short loc_180027AB7
0x180027a98  lea     rdx, [r14+rax*8]
0x180027a9c  lea     rcx, [rbp+57h+var_B0]
0x180027aa0  call    ?Add@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(_GUID const &)
0x180027aa5  test    eax, eax
0x180027aa7  jz      short loc_180027ABB
0x180027aa9  mov     r8, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x180027ab0  mov     r9, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180027ab7  inc     esi
0x180027ab9  jmp     short loc_180027A6F
0x180027abb  mov     rcx, [rbp+5Fh]; this
0x180027abf  mov     ebx, 8007000Eh
0x180027ac4  mov     r9d, ebx; char *
0x180027ac7  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027ace  mov     edx, 4E1h; void *
0x180027ad3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ad8  mov     rcx, [rbp+5Fh]; this
0x180027adc  mov     r9d, ebx; char *
0x180027adf  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027ae6  mov     edx, 0D9Eh; void *
0x180027aeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027af0  nop
0x180027af1  lea     rcx, [rbp+57h+var_B0]; void *
0x180027af5  call    ?RemoveAll@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(void)
0x180027afa  jmp     loc_180027A38
0x180027aff  mov     [rbp+57h+Block], r13
0x180027b03  mov     [rbp+57h+var_98], r13
0x180027b07  lea     rcx, [rdi+rdi*2]
0x180027b0b  shl     rcx, 5
0x180027b0f  mov     rax, [rbx+620h]
0x180027b16  mov     r14d, [rcx+rax+570h]
0x180027b1e  mov     r15, [rcx+rax+578h]
0x180027b26  mov     esi, r13d
0x180027b29  mov     r12d, 1
0x180027b2f  cmp     esi, r14d
0x180027b32  jnb     loc_180027BE3
0x180027b38  mov     edx, esi
0x180027b3a  shl     rdx, 4
0x180027b3e  add     rdx, r15
0x180027b41  mov     rax, [rdx]
0x180027b44  sub     rax, r9
0x180027b47  jnz     short loc_180027B50
0x180027b49  mov     rax, [rdx+8]
0x180027b4d  sub     rax, r8
0x180027b50  test    rax, rax
0x180027b53  jz      short loc_180027B70
0x180027b55  lea     rcx, [rbp+57h+Block]
0x180027b59  call    ?Add@?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAHAEBU_GUID@@@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Add(_GUID const &)
0x180027b5e  test    eax, eax
0x180027b60  jz      short loc_180027B75
0x180027b62  mov     r8, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x180027b69  mov     r9, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180027b70  add     esi, r12d
0x180027b73  jmp     short loc_180027B2F
0x180027b75  mov     rcx, [rbp+5Fh]; this
0x180027b79  mov     ebx, 8007000Eh
0x180027b7e  mov     r9d, ebx; char *
0x180027b81  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027b88  mov     edx, 4E1h; void *
0x180027b8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027b92  mov     rcx, [rbp+5Fh]; this
0x180027b96  mov     r9d, ebx; char *
0x180027b99  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027ba0  mov     edx, 0DA2h; void *
0x180027ba5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027baa  nop
0x180027bab  mov     rcx, [rbp+57h+Block]; Block
0x180027baf  test    rcx, rcx
0x180027bb2  jz      short loc_180027BBB
0x180027bb4  call    cs:__imp_free
0x180027bba  nop
0x180027bbb  mov     rcx, [rbp+57h+var_B0]; Block
0x180027bbf  test    rcx, rcx
0x180027bc2  jz      short loc_180027BCB
0x180027bc4  call    cs:__imp_free
0x180027bca  nop
0x180027bcb  mov     rcx, [rbp+57h+var_C0]; Block
0x180027bcf  test    rcx, rcx
0x180027bd2  jz      loc_18002796A
0x180027bd8  call    cs:__imp_free
0x180027bde  jmp     loc_18002796A
0x180027be3  cmp     rdi, [rbx+5A0h]
0x180027bea  jnb     loc_180027EEA
0x180027bf0  lea     rcx, [rdi+rdi*2]
0x180027bf4  shl     rcx, 5
0x180027bf8  mov     rax, [rbx+620h]
0x180027bff  mov     r8, [rcx+rax+528h]
0x180027c07  mov     edx, [rcx+rax+520h]
0x180027c0e  lea     r9, [rdi+rdi*2]
0x180027c12  shl     r9, 5
0x180027c16  mov     rax, [rbx+5A8h]
0x180027c1d  add     rax, 10h
0x180027c21  add     r9, rax
0x180027c24  mov     r14d, dword ptr [rbp+57h+var_B8]
0x180027c28  mov     [rsp+100h+var_D8], r9
0x180027c2d  lea     rcx, [rbp+57h+var_C0]
0x180027c31  test    r14d, r14d
0x180027c34  jle     short loc_180027C54
0x180027c36  mov     qword ptr [rsp+100h+var_E0], r13; int
0x180027c3b  xor     r9d, r9d
0x180027c3e  call    ?CreateEffectChain@SystemEffectChainDescriptor@@KAJAEAVCAudioSignalProcessingModeArray@@IPEBU_GUID@@I1AEAV?$shared_ptr@VSystemEffectChainDescriptor@@@std@@@Z; SystemEffectChainDescriptor::CreateEffectChain(CAudioSignalProcessingModeArray &,uint,_GUID const *,uint,_GUID const *,std::shared_ptr<SystemEffectChainDescriptor> &)
0x180027c43  mov     esi, eax
0x180027c45  test    eax, eax
0x180027c47  jns     loc_180027D09
0x180027c4d  mov     edx, 0A1h
0x180027c52  jmp     short loc_180027C75
0x180027c54  mov     qword ptr [rsp+100h+var_E0], r8; int
0x180027c59  mov     r9d, edx
0x180027c5c  xor     r8d, r8d
0x180027c5f  xor     edx, edx
0x180027c61  call    ?CreateEffectChain@SystemEffectChainDescriptor@@KAJAEAVCAudioSignalProcessingModeArray@@IPEBU_GUID@@I1AEAV?$shared_ptr@VSystemEffectChainDescriptor@@@std@@@Z; SystemEffectChainDescriptor::CreateEffectChain(CAudioSignalProcessingModeArray &,uint,_GUID const *,uint,_GUID const *,std::shared_ptr<SystemEffectChainDescriptor> &)
0x180027c66  mov     esi, eax
0x180027c68  test    eax, eax
0x180027c6a  jns     loc_180027D09
0x180027c70  mov     edx, 0A6h; void *
0x180027c75  mov     r9d, esi; char *
0x180027c78  lea     r8, aAvcoreAudiocor_31; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027c7f  mov     rcx, [rbp+5Fh]; this
0x180027c83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c88  mov     rcx, [rbp+5Fh]; this
0x180027c8c  mov     r9d, esi; char *
0x180027c8f  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180027c96  mov     edx, 0DA7h; void *
0x180027c9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ca0  nop
0x180027ca1  mov     rcx, [rbp+57h+Block]; Block
0x180027ca5  test    rcx, rcx
0x180027ca8  jz      short loc_180027CC2
0x180027caa  mov     eax, r13d
0x180027cad  mov     edx, dword ptr [rbp+57h+var_98]
0x180027cb0  test    edx, edx
0x180027cb2  jle     short loc_180027CBB
0x180027cb4  add     eax, r12d
0x180027cb7  cmp     eax, edx
0x180027cb9  jl      short loc_180027CB4
0x180027cbb  call    cs:__imp_free
0x180027cc1  nop
0x180027cc2  mov     rcx, [rbp+57h+var_B0]; Block
0x180027cc6  test    rcx, rcx
0x180027cc9  jz      short loc_180027CE3
0x180027ccb  mov     eax, r13d
0x180027cce  mov     edx, dword ptr [rbp+57h+var_A8]
0x180027cd1  test    edx, edx
0x180027cd3  jle     short loc_180027CDC
0x180027cd5  add     eax, r12d
0x180027cd8  cmp     eax, edx
0x180027cda  jl      short loc_180027CD5
0x180027cdc  call    cs:__imp_free
0x180027ce2  nop
0x180027ce3  mov     rcx, [rbp+57h+var_C0]; Block
0x180027ce7  test    rcx, rcx
0x180027cea  jz      short loc_180027D02
0x180027cec  mov     eax, r13d
0x180027cef  test    r14d, r14d
  ... truncated ...
```
