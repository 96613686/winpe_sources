# EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)

- ea: `0x1800202b0`
- end: `0x1800206e0`
- name: `?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z`
- size: `1072`
- prototype: `__int64 __fastcall(EffectPack *__hidden this, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, int, struct tWAVEFORMATEX **, struct SpatialAudioSettings **, unsigned int *, struct SpatialAudioEncoderDescriptor **pv)`
- caller_count: `8`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e740`
- `0x18001e840`
- `0x180040ec0`
- `0x18008a0f4`
- `0x18008ba74`
- `0x180109b3c`
- `0x180144adc`
- `0x18014899c`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x180020238`
- `0x1800202b0`
- `0x1800209dc`
- `0x180022800`
- `0x18002659c`
- `0x180027780`
- `0x1800ce774`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002067a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002067a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002051d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002058b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020595`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002051d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002058b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020595`

## string_xrefs

- `0x180020542`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020571`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1800205c9`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1800205ff`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18002065a`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020698`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EffectPack::GetDeviceFormatAndSpatialSettings(
        CEndpointCharacteristics **this,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a2,
        __int64 a3,
        struct tWAVEFORMATEX **a4,
        struct SpatialAudioSettings **a5,
        unsigned int *a6,
        struct SpatialAudioEncoderDescriptor **pv)
{
  struct SpatialAudioSettings **v10; // r15
  unsigned int *v11; // r13
  struct SpatialAudioEncoderDescriptor **v12; // rsi
  __int64 SupportedConnectorModesInternal; // r8
  int v14; // r9d
  int i; // ecx
  _QWORD *v16; // rdx
  __int64 v17; // rax
  int j; // eax
  _QWORD *v19; // rdx
  __int64 v20; // rcx
  GUID v21; // xmm0
  unsigned int DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02; // ebx
  __int64 result; // rax
  struct SpatialAudioEncoderDescriptor *v24; // rdi
  void *v25; // r14
  unsigned __int64 v26; // r12
  CEndpointCharacteristics *v27; // rdx
  int v28; // eax
  int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rdx
  struct SpatialAudioEncoderDescriptor *v32; // rax
  int v33; // [rsp+20h] [rbp-50h]
  int v34; // [rsp+20h] [rbp-50h]
  unsigned int v35; // [rsp+30h] [rbp-40h]
  __int64 v36; // [rsp+38h] [rbp-38h] BYREF
  struct SpatialAudioEncoderDescriptor *v37; // [rsp+40h] [rbp-30h]
  void *v38; // [rsp+48h] [rbp-28h]
  int v39[2]; // [rsp+50h] [rbp-20h] BYREF
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v40; // [rsp+58h] [rbp-18h]
  GUID v41; // [rsp+5Ch] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  unsigned int v44; // [rsp+C8h] [rbp+58h] BYREF

  if ( !a4 )
  {
    v31 = 8697;
LABEL_58:
    DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02 = -2147467261;
    goto LABEL_56;
  }
  *a4 = 0;
  v10 = a5;
  if ( a5 )
    *a5 = 0;
  v11 = a6;
  if ( a6 )
  {
    *a6 = 0;
    if ( !v10 )
    {
      v31 = 8708;
      goto LABEL_58;
    }
  }
  v12 = pv;
  if ( pv )
  {
    *pv = 0;
    if ( !v10 )
    {
      v31 = 8714;
      goto LABEL_58;
    }
    if ( !v11 )
    {
      v31 = 8715;
      goto LABEL_58;
    }
  }
  LOBYTE(v44) = (unsigned int)CEndpointCharacteristics::HasHardwareAudioEngine(this[198]) != 0;
  SupportedConnectorModesInternal = EffectPack::GetSupportedConnectorModesInternal(
                                      this,
                                      a2 & (unsigned int)-(((a2 - 2) & 0xFFFFFFFD) != 0),
                                      0,
                                      1);
  v14 = *(_DWORD *)(SupportedConnectorModesInternal + 8);
  if ( v14 )
  {
    for ( i = 0; i < v14; ++i )
    {
      v16 = (_QWORD *)(*(_QWORD *)SupportedConnectorModesInternal + 16LL * i);
      v17 = *v16 - *(_QWORD *)&GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1;
      if ( *v16 == *(_QWORD *)&GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1 )
        v17 = v16[1] - *(_QWORD *)GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data4;
      if ( !v17 )
      {
        if ( i != -1 )
        {
          v21 = GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3;
          goto LABEL_21;
        }
        break;
      }
    }
    for ( j = 0; j < v14; ++j )
    {
      v19 = (_QWORD *)(*(_QWORD *)SupportedConnectorModesInternal + 16LL * j);
      v20 = *v19 - *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1;
      if ( *v19 == *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1 )
        v20 = v19[1] - *(_QWORD *)GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4;
      if ( !v20 )
      {
        if ( j != -1 )
        {
          v21 = GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf;
          goto LABEL_21;
        }
        break;
      }
    }
    v21 = *(GUID *)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator[](
                     SupportedConnectorModesInternal,
                     0);
  }
  else
  {
    v21 = GUID_00000000_0000_0000_0000_000000000000;
  }
LABEL_21:
  *(_QWORD *)v39 = this;
  v40 = a2;
  v41 = v21;
  DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02 = CEndpointCharacteristics::GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___(
                                                                    this[198],
                                                                    (__int64)v39,
                                                                    (__int64)a4);
  if ( (DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02 & 0x80000000) == 0 )
  {
    if ( !v10 )
      return 0;
    v24 = 0;
    v37 = 0;
    v25 = CoTaskMemAlloc(0x48u);
    v38 = v25;
    if ( !v25 )
    {
      DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221A,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)0x8007000ELL,
        v33);
      return DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02;
    }
    if ( v12 )
    {
      v26 = 7506;
      v32 = (struct SpatialAudioEncoderDescriptor *)CoTaskMemAlloc(0x1D52u);
      v24 = v32;
      v37 = v32;
      if ( !v32 )
      {
        DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2221,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x8007000ELL,
          v33);
        goto LABEL_49;
      }
      v12 = (struct SpatialAudioEncoderDescriptor **)v32;
    }
    else
    {
      v26 = 0;
    }
    v27 = this[198];
    v36 = 0;
    v28 = Create_SpatialAudioDevicePropertyReader(0, *((_QWORD *)v27 + 9), &v36);
    DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C3C,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v28,
        v33);
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    else
    {
      v35 = 0;
      v44 = 0;
      v29 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v36 + 96LL))(v36, &v44);
      v30 = v44;
      if ( v29 < 0 || !v12 || (v35 = 834 * v44, v26 >= 834 * v44) )
      {
        if ( (*(int (__fastcall **)(__int64, void *, struct SpatialAudioEncoderDescriptor **, _QWORD))(*(_QWORD *)v36 + 104LL))(
               v36,
               v25,
               v12,
               v35) < 0 )
        {
          memset_0(v25, 0, 0x48u);
          v30 = 0;
        }
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        *v10 = (struct SpatialAudioSettings *)v25;
        if ( pv )
        {
          *pv = v24;
          v12 = 0;
        }
        if ( v11 )
          *v11 = v30;
        if ( v12 )
          CoTaskMemFree(v12);
        return 0;
      }
      DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02 = -2147024774;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C47,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)0x8007007ALL,
        v33);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v36);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2228,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02,
      v34);
    if ( v24 )
      CoTaskMemFree(v24);
LABEL_49:
    CoTaskMemFree(v25);
    return DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02;
  }
  result = 2290679812LL;
  if ( DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02 != -2004287484 )
  {
    v31 = 8720;
LABEL_56:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02,
      v33);
    return DeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02;
  }
  return result;
}

```

## disassembly

```asm
0x1800202b0  mov     [rsp-38h+arg_8], rbx
0x1800202b5  mov     [rsp-38h+arg_0], rcx
0x1800202ba  push    rbp
0x1800202bb  push    rsi
0x1800202bc  push    rdi
0x1800202bd  push    r12
0x1800202bf  push    r13
0x1800202c1  push    r14
0x1800202c3  push    r15
0x1800202c5  mov     rbp, rsp
0x1800202c8  sub     rsp, 70h
0x1800202cc  mov     rbx, r9
0x1800202cf  mov     edi, r8d
0x1800202d2  mov     r12d, edx
0x1800202d5  mov     r14, rcx
0x1800202d8  xor     eax, eax
0x1800202da  test    r9, r9
0x1800202dd  jz      loc_18002060D
0x1800202e3  mov     [r9], rax
0x1800202e6  mov     r15, [rbp+arg_20]
0x1800202ea  test    r15, r15
0x1800202ed  jz      short loc_1800202F2
0x1800202ef  mov     [r15], rax
0x1800202f2  mov     r13, [rbp+arg_28]
0x1800202f6  test    r13, r13
0x1800202f9  jnz     loc_180020620
0x1800202ff  mov     rsi, [rbp+pv]
0x180020303  test    rsi, rsi
0x180020306  jnz     loc_180020634
0x18002030c  mov     rcx, [rcx+630h]; this
0x180020313  call    ?HasHardwareAudioEngine@CEndpointCharacteristics@@QEAAHXZ; CEndpointCharacteristics::HasHardwareAudioEngine(void)
0x180020318  test    eax, eax
0x18002031a  setnz   byte ptr [rbp+arg_18]
0x18002031e  test    edi, edi
0x180020320  setnz   dil
0x180020324  lea     eax, [r12-2]
0x180020329  and     eax, 0FFFFFFFDh
0x18002032c  neg     eax
0x18002032e  sbb     edx, edx
0x180020330  and     edx, r12d
0x180020333  mov     r9d, 1
0x180020339  xor     r8d, r8d
0x18002033c  mov     rcx, r14
0x18002033f  call    ?GetSupportedConnectorModesInternal@EffectPack@@AEAAPEAVCAudioSignalProcessingModeArray@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4FXEnablementConsideration@@W4SED_RESOLVEOPT@@@Z; EffectPack::GetSupportedConnectorModesInternal(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,FXEnablementConsideration,SED_RESOLVEOPT)
0x180020344  mov     r8, rax
0x180020347  mov     r9d, [rax+8]
0x18002034b  test    r9d, r9d
0x18002034e  jz      short loc_1800203BF
0x180020350  xor     ecx, ecx
0x180020352  cmp     ecx, r9d
0x180020355  jge     short loc_18002038A
0x180020357  movsxd  rdx, ecx
0x18002035a  shl     rdx, 4
0x18002035e  add     rdx, [r8]
0x180020361  mov     rax, [rdx]
0x180020364  sub     rax, qword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x18002036b  jnz     short loc_180020378
0x18002036d  mov     rax, [rdx+8]
0x180020371  sub     rax, qword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data4
0x180020378  test    rax, rax
0x18002037b  jz      short loc_180020381
0x18002037d  inc     ecx
0x18002037f  jmp     short loc_180020352
0x180020381  cmp     ecx, 0FFFFFFFFh
0x180020384  jnz     loc_180020437
0x18002038a  xor     eax, eax
0x18002038c  cmp     eax, r9d
0x18002038f  jge     loc_180020529
0x180020395  movsxd  rdx, eax
0x180020398  shl     rdx, 4
0x18002039c  add     rdx, [r8]
0x18002039f  mov     rcx, [rdx]
0x1800203a2  sub     rcx, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x1800203a9  jnz     short loc_1800203B6
0x1800203ab  mov     rcx, [rdx+8]
0x1800203af  sub     rcx, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x1800203b6  test    rcx, rcx
0x1800203b9  jz      short loc_180020425
0x1800203bb  inc     eax
0x1800203bd  jmp     short loc_18002038C
0x1800203bf  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800203c6  mov     qword ptr [rbp+var_20], r14
0x1800203ca  mov     [rbp+var_18], r12d
0x1800203ce  movups  [rbp+var_14], xmm0
0x1800203d2  mov     eax, [rbp+var_4]
0x1800203d5  mov     [rbp+var_4], eax
0x1800203d8  mov     [rsp+70h+var_48], rbx
0x1800203dd  lea     rax, [rbp+var_20]
0x1800203e1  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800203e6  mov     r9d, r12d
0x1800203e9  mov     r8b, byte ptr [rbp+arg_18]
0x1800203ed  mov     dl, dil
0x1800203f0  mov     rcx, [r14+630h]
0x1800203f7  call    CEndpointCharacteristics__GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___
0x1800203fc  mov     ebx, eax
0x1800203fe  test    eax, eax
0x180020400  js      loc_1800205E6
0x180020406  test    r15, r15
0x180020409  jnz     short loc_180020440
0x18002040b  xor     eax, eax
0x18002040d  mov     rbx, [rsp+70h+arg_8]
0x180020415  add     rsp, 70h
0x180020419  pop     r15
0x18002041b  pop     r14
0x18002041d  pop     r13
0x18002041f  pop     r12
0x180020421  pop     rdi
0x180020422  pop     rsi
0x180020423  pop     rbp
0x180020424  retn
0x180020425  cmp     eax, 0FFFFFFFFh
0x180020428  jz      loc_180020529
0x18002042e  movaps  xmm0, xmmword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180020435  jmp     short loc_1800203C6
0x180020437  movaps  xmm0, xmmword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x18002043e  jmp     short loc_1800203C6
0x180020440  xor     edi, edi
0x180020442  mov     [rbp+var_30], rdi
0x180020446  lea     ecx, [rdi+48h]; cb
0x180020449  call    cs:__imp_CoTaskMemAlloc
0x18002044f  mov     r14, rax
0x180020452  mov     [rbp+var_28], rax
0x180020456  test    rax, rax
0x180020459  jz      loc_18002064E
0x18002045f  test    rsi, rsi
0x180020462  jnz     loc_180020671
0x180020468  xor     r12d, r12d
0x18002046b  mov     rdx, [rbp+arg_0]
0x18002046f  mov     rdx, [rdx+630h]
0x180020476  mov     [rbp+var_38], 0
0x18002047e  lea     r8, [rbp+var_38]
0x180020482  mov     rdx, [rdx+48h]
0x180020486  xor     ecx, ecx
0x180020488  call    Create_SpatialAudioDevicePropertyReader
0x18002048d  mov     ebx, eax
0x18002048f  test    eax, eax
0x180020491  js      loc_18002053B
0x180020497  mov     [rbp+var_40], 0
0x18002049e  mov     [rbp+arg_18], 0
0x1800204a5  mov     rcx, [rbp+var_38]
0x1800204a9  mov     rax, [rcx]
0x1800204ac  lea     rdx, [rbp+arg_18]
0x1800204b0  mov     rax, [rax+60h]
0x1800204b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204b9  mov     ebx, [rbp+arg_18]
0x1800204bc  test    eax, eax
0x1800204be  jns     loc_1800205A2
0x1800204c4  mov     rcx, [rbp+var_38]
0x1800204c8  mov     rax, [rcx]
0x1800204cb  mov     r9d, [rbp+var_40]
0x1800204cf  mov     r8, rsi
0x1800204d2  mov     rdx, r14
0x1800204d5  mov     rax, [rax+68h]
0x1800204d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204de  test    eax, eax
0x1800204e0  js      loc_1800206B7
0x1800204e6  mov     rcx, [rbp+var_38]
0x1800204ea  test    rcx, rcx
0x1800204ed  jz      short loc_1800204FC
0x1800204ef  mov     rax, [rcx]
0x1800204f2  mov     rax, [rax+10h]
0x1800204f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204fb  nop
0x1800204fc  mov     [r15], r14
0x1800204ff  mov     rax, [rbp+pv]
0x180020503  test    rax, rax
0x180020506  jnz     loc_1800206CC
0x18002050c  test    r13, r13
0x18002050f  jnz     loc_1800206D6
0x180020515  test    rsi, rsi
0x180020518  jz      short loc_180020524
0x18002051a  mov     rcx, rsi; pv
0x18002051d  call    cs:__imp_CoTaskMemFree
0x180020523  nop
0x180020524  jmp     loc_18002040B
0x180020529  xor     edx, edx
0x18002052b  mov     rcx, r8
0x18002052e  call    ??A?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAAEAU_GUID@@H@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator[](int)
0x180020533  movups  xmm0, xmmword ptr [rax]
0x180020536  jmp     loc_1800203C6
0x18002053b  mov     rcx, [rbp+38h]; this
0x18002053f  mov     r9d, eax; char *
0x180020542  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020549  mov     edx, 1C3Ch; void *
0x18002054e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020553  nop
0x180020554  mov     rcx, [rbp+var_38]
0x180020558  test    rcx, rcx
0x18002055b  jz      short loc_18002056A
0x18002055d  mov     rax, [rcx]
0x180020560  mov     rax, [rax+10h]
0x180020564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020569  nop
0x18002056a  mov     rcx, [rbp+38h]; this
0x18002056e  mov     r9d, ebx; char *
0x180020571  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020578  mov     edx, 2228h; void *
0x18002057d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020582  nop
0x180020583  test    rdi, rdi
0x180020586  jz      short loc_180020592
0x180020588  mov     rcx, rdi; pv
0x18002058b  call    cs:__imp_CoTaskMemFree
0x180020591  nop
0x180020592  mov     rcx, r14; pv
0x180020595  call    cs:__imp_CoTaskMemFree
0x18002059b  mov     eax, ebx
0x18002059d  jmp     loc_18002040D
0x1800205a2  test    rsi, rsi
0x1800205a5  jz      loc_1800204C4
0x1800205ab  imul    eax, ebx, 342h
0x1800205b1  mov     [rbp+var_40], eax
0x1800205b4  cmp     r12, rax
0x1800205b7  jnb     loc_1800204C4
0x1800205bd  mov     rcx, [rbp+38h]; this
0x1800205c1  mov     ebx, 8007007Ah
0x1800205c6  mov     r9d, ebx; char *
0x1800205c9  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800205d0  mov     edx, 1C47h; void *
0x1800205d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800205da  nop
0x1800205db  lea     rcx, [rbp+var_38]
0x1800205df  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800205e4  jmp     short loc_18002056A
0x1800205e6  mov     eax, 88890004h
0x1800205eb  cmp     ebx, eax
0x1800205ed  jz      loc_18002040D
0x1800205f3  mov     edx, 2210h; void *
0x1800205f8  mov     rcx, [rbp+38h]; this
0x1800205fc  mov     r9d, ebx; char *
0x1800205ff  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020606  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002060b  jmp     short loc_18002059B
0x18002060d  mov     edx, 21F9h
0x180020612  jmp     short loc_180020619
0x180020614  mov     edx, 220Bh
0x180020619  mov     ebx, 80004003h
0x18002061e  jmp     short loc_1800205F8
0x180020620  mov     [r13+0], eax
0x180020624  test    r15, r15
0x180020627  jnz     loc_1800202FF
0x18002062d  mov     edx, 2204h
0x180020632  jmp     short loc_180020619
0x180020634  mov     [rsi], rax
0x180020637  test    r15, r15
0x18002063a  jnz     short loc_180020643
0x18002063c  mov     edx, 220Ah
0x180020641  jmp     short loc_180020619
0x180020643  test    r13, r13
0x180020646  jnz     loc_18002030C
0x18002064c  jmp     short loc_180020614
0x18002064e  mov     rcx, [rbp+38h]; this
0x180020652  mov     ebx, 8007000Eh
0x180020657  mov     r9d, ebx; char *
0x18002065a  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020661  mov     edx, 221Ah; void *
0x180020666  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002066b  nop
0x18002066c  jmp     loc_18002059B
0x180020671  mov     r12d, 1D52h
0x180020677  mov     ecx, r12d; cb
0x18002067a  call    cs:__imp_CoTaskMemAlloc
0x180020680  mov     rdi, rax
0x180020683  mov     [rbp+var_30], rax
0x180020687  test    rax, rax
0x18002068a  jnz     short loc_1800206AF
0x18002068c  mov     rcx, [rbp+38h]; this
0x180020690  mov     ebx, 8007000Eh
0x180020695  mov     r9d, ebx; char *
0x180020698  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002069f  mov     edx, 2221h; void *
0x1800206a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800206a9  nop
0x1800206aa  jmp     loc_180020592
0x1800206af  mov     rsi, rax
0x1800206b2  jmp     loc_18002046B
0x1800206b7  xor     edx, edx; Val
0x1800206b9  lea     r8d, [rdx+48h]; Size
0x1800206bd  mov     rcx, r14; void *
0x1800206c0  call    memset_0
0x1800206c5  xor     ebx, ebx
0x1800206c7  jmp     loc_1800204E6
0x1800206cc  mov     [rax], rdi
0x1800206cf  xor     esi, esi
0x1800206d1  jmp     loc_18002050C
0x1800206d6  mov     [r13+0], ebx
0x1800206da  jmp     loc_180020515
```
