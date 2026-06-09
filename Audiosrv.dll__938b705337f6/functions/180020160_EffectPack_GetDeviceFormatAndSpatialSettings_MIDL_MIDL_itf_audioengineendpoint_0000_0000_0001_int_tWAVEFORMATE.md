# EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)

- ea: `0x180020160`
- end: `0x180020590`
- name: `?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z`
- size: `1072`
- prototype: `__int64 __fastcall(EffectPack *__hidden this, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, int, struct tWAVEFORMATEX **, struct SpatialAudioSettings **, unsigned int *, struct SpatialAudioEncoderDescriptor **pv)`
- caller_count: `8`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e5f0`
- `0x18001e6f0`
- `0x180040d50`
- `0x18008a5f4`
- `0x18008b9c8`
- `0x1801098dc`
- `0x1801440cc`
- `0x180147c8c`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x1800200e8`
- `0x180020160`
- `0x18002088c`
- `0x1800226b0`
- `0x18002644c`
- `0x180027620`
- `0x1800d0764`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800202f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002052a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800202f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002052a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800203cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002043b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020445`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800203cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002043b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020445`

## string_xrefs

- `0x1800203f2`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020421`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020479`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1800204af`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18002050a`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020548`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
    v31 = 8698;
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
      v31 = 8709;
      goto LABEL_58;
    }
  }
  v12 = pv;
  if ( pv )
  {
    *pv = 0;
    if ( !v10 )
    {
      v31 = 8715;
      goto LABEL_58;
    }
    if ( !v11 )
    {
      v31 = 8716;
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
        (void *)0x221B,
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
          (void *)0x2222,
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
        (void *)0x1C3D,
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
        (void *)0x1C48,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)0x8007007ALL,
        v33);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v36);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2229,
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
    v31 = 8721;
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
0x180020160  mov     [rsp-38h+arg_8], rbx
0x180020165  mov     [rsp-38h+arg_0], rcx
0x18002016a  push    rbp
0x18002016b  push    rsi
0x18002016c  push    rdi
0x18002016d  push    r12
0x18002016f  push    r13
0x180020171  push    r14
0x180020173  push    r15
0x180020175  mov     rbp, rsp
0x180020178  sub     rsp, 70h
0x18002017c  mov     rbx, r9
0x18002017f  mov     edi, r8d
0x180020182  mov     r12d, edx
0x180020185  mov     r14, rcx
0x180020188  xor     eax, eax
0x18002018a  test    r9, r9
0x18002018d  jz      loc_1800204BD
0x180020193  mov     [r9], rax
0x180020196  mov     r15, [rbp+arg_20]
0x18002019a  test    r15, r15
0x18002019d  jz      short loc_1800201A2
0x18002019f  mov     [r15], rax
0x1800201a2  mov     r13, [rbp+arg_28]
0x1800201a6  test    r13, r13
0x1800201a9  jnz     loc_1800204D0
0x1800201af  mov     rsi, [rbp+pv]
0x1800201b3  test    rsi, rsi
0x1800201b6  jnz     loc_1800204E4
0x1800201bc  mov     rcx, [rcx+630h]; this
0x1800201c3  call    ?HasHardwareAudioEngine@CEndpointCharacteristics@@QEAAHXZ; CEndpointCharacteristics::HasHardwareAudioEngine(void)
0x1800201c8  test    eax, eax
0x1800201ca  setnz   byte ptr [rbp+arg_18]
0x1800201ce  test    edi, edi
0x1800201d0  setnz   dil
0x1800201d4  lea     eax, [r12-2]
0x1800201d9  and     eax, 0FFFFFFFDh
0x1800201dc  neg     eax
0x1800201de  sbb     edx, edx
0x1800201e0  and     edx, r12d
0x1800201e3  mov     r9d, 1
0x1800201e9  xor     r8d, r8d
0x1800201ec  mov     rcx, r14
0x1800201ef  call    ?GetSupportedConnectorModesInternal@EffectPack@@AEAAPEAVCAudioSignalProcessingModeArray@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4FXEnablementConsideration@@W4SED_RESOLVEOPT@@@Z; EffectPack::GetSupportedConnectorModesInternal(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,FXEnablementConsideration,SED_RESOLVEOPT)
0x1800201f4  mov     r8, rax
0x1800201f7  mov     r9d, [rax+8]
0x1800201fb  test    r9d, r9d
0x1800201fe  jz      short loc_18002026F
0x180020200  xor     ecx, ecx
0x180020202  cmp     ecx, r9d
0x180020205  jge     short loc_18002023A
0x180020207  movsxd  rdx, ecx
0x18002020a  shl     rdx, 4
0x18002020e  add     rdx, [r8]
0x180020211  mov     rax, [rdx]
0x180020214  sub     rax, qword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x18002021b  jnz     short loc_180020228
0x18002021d  mov     rax, [rdx+8]
0x180020221  sub     rax, qword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data4
0x180020228  test    rax, rax
0x18002022b  jz      short loc_180020231
0x18002022d  inc     ecx
0x18002022f  jmp     short loc_180020202
0x180020231  cmp     ecx, 0FFFFFFFFh
0x180020234  jnz     loc_1800202E7
0x18002023a  xor     eax, eax
0x18002023c  cmp     eax, r9d
0x18002023f  jge     loc_1800203D9
0x180020245  movsxd  rdx, eax
0x180020248  shl     rdx, 4
0x18002024c  add     rdx, [r8]
0x18002024f  mov     rcx, [rdx]
0x180020252  sub     rcx, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180020259  jnz     short loc_180020266
0x18002025b  mov     rcx, [rdx+8]
0x18002025f  sub     rcx, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x180020266  test    rcx, rcx
0x180020269  jz      short loc_1800202D5
0x18002026b  inc     eax
0x18002026d  jmp     short loc_18002023C
0x18002026f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180020276  mov     qword ptr [rbp+var_20], r14
0x18002027a  mov     [rbp+var_18], r12d
0x18002027e  movups  [rbp+var_14], xmm0
0x180020282  mov     eax, [rbp+var_4]
0x180020285  mov     [rbp+var_4], eax
0x180020288  mov     [rsp+70h+var_48], rbx
0x18002028d  lea     rax, [rbp+var_20]
0x180020291  mov     qword ptr [rsp+70h+var_50], rax; int
0x180020296  mov     r9d, r12d
0x180020299  mov     r8b, byte ptr [rbp+arg_18]
0x18002029d  mov     dl, dil
0x1800202a0  mov     rcx, [r14+630h]
0x1800202a7  call    CEndpointCharacteristics__GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___
0x1800202ac  mov     ebx, eax
0x1800202ae  test    eax, eax
0x1800202b0  js      loc_180020496
0x1800202b6  test    r15, r15
0x1800202b9  jnz     short loc_1800202F0
0x1800202bb  xor     eax, eax
0x1800202bd  mov     rbx, [rsp+70h+arg_8]
0x1800202c5  add     rsp, 70h
0x1800202c9  pop     r15
0x1800202cb  pop     r14
0x1800202cd  pop     r13
0x1800202cf  pop     r12
0x1800202d1  pop     rdi
0x1800202d2  pop     rsi
0x1800202d3  pop     rbp
0x1800202d4  retn
0x1800202d5  cmp     eax, 0FFFFFFFFh
0x1800202d8  jz      loc_1800203D9
0x1800202de  movaps  xmm0, xmmword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x1800202e5  jmp     short loc_180020276
0x1800202e7  movaps  xmm0, xmmword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x1800202ee  jmp     short loc_180020276
0x1800202f0  xor     edi, edi
0x1800202f2  mov     [rbp+var_30], rdi
0x1800202f6  lea     ecx, [rdi+48h]; cb
0x1800202f9  call    cs:__imp_CoTaskMemAlloc
0x1800202ff  mov     r14, rax
0x180020302  mov     [rbp+var_28], rax
0x180020306  test    rax, rax
0x180020309  jz      loc_1800204FE
0x18002030f  test    rsi, rsi
0x180020312  jnz     loc_180020521
0x180020318  xor     r12d, r12d
0x18002031b  mov     rdx, [rbp+arg_0]
0x18002031f  mov     rdx, [rdx+630h]
0x180020326  mov     [rbp+var_38], 0
0x18002032e  lea     r8, [rbp+var_38]
0x180020332  mov     rdx, [rdx+48h]
0x180020336  xor     ecx, ecx
0x180020338  call    Create_SpatialAudioDevicePropertyReader
0x18002033d  mov     ebx, eax
0x18002033f  test    eax, eax
0x180020341  js      loc_1800203EB
0x180020347  mov     [rbp+var_40], 0
0x18002034e  mov     [rbp+arg_18], 0
0x180020355  mov     rcx, [rbp+var_38]
0x180020359  mov     rax, [rcx]
0x18002035c  lea     rdx, [rbp+arg_18]
0x180020360  mov     rax, [rax+60h]
0x180020364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020369  mov     ebx, [rbp+arg_18]
0x18002036c  test    eax, eax
0x18002036e  jns     loc_180020452
0x180020374  mov     rcx, [rbp+var_38]
0x180020378  mov     rax, [rcx]
0x18002037b  mov     r9d, [rbp+var_40]
0x18002037f  mov     r8, rsi
0x180020382  mov     rdx, r14
0x180020385  mov     rax, [rax+68h]
0x180020389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002038e  test    eax, eax
0x180020390  js      loc_180020567
0x180020396  mov     rcx, [rbp+var_38]
0x18002039a  test    rcx, rcx
0x18002039d  jz      short loc_1800203AC
0x18002039f  mov     rax, [rcx]
0x1800203a2  mov     rax, [rax+10h]
0x1800203a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203ab  nop
0x1800203ac  mov     [r15], r14
0x1800203af  mov     rax, [rbp+pv]
0x1800203b3  test    rax, rax
0x1800203b6  jnz     loc_18002057C
0x1800203bc  test    r13, r13
0x1800203bf  jnz     loc_180020586
0x1800203c5  test    rsi, rsi
0x1800203c8  jz      short loc_1800203D4
0x1800203ca  mov     rcx, rsi; pv
0x1800203cd  call    cs:__imp_CoTaskMemFree
0x1800203d3  nop
0x1800203d4  jmp     loc_1800202BB
0x1800203d9  xor     edx, edx
0x1800203db  mov     rcx, r8
0x1800203de  call    ??A?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAAEAU_GUID@@H@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator[](int)
0x1800203e3  movups  xmm0, xmmword ptr [rax]
0x1800203e6  jmp     loc_180020276
0x1800203eb  mov     rcx, [rbp+38h]; this
0x1800203ef  mov     r9d, eax; char *
0x1800203f2  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800203f9  mov     edx, 1C3Dh; void *
0x1800203fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020403  nop
0x180020404  mov     rcx, [rbp+var_38]
0x180020408  test    rcx, rcx
0x18002040b  jz      short loc_18002041A
0x18002040d  mov     rax, [rcx]
0x180020410  mov     rax, [rax+10h]
0x180020414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020419  nop
0x18002041a  mov     rcx, [rbp+38h]; this
0x18002041e  mov     r9d, ebx; char *
0x180020421  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020428  mov     edx, 2229h; void *
0x18002042d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020432  nop
0x180020433  test    rdi, rdi
0x180020436  jz      short loc_180020442
0x180020438  mov     rcx, rdi; pv
0x18002043b  call    cs:__imp_CoTaskMemFree
0x180020441  nop
0x180020442  mov     rcx, r14; pv
0x180020445  call    cs:__imp_CoTaskMemFree
0x18002044b  mov     eax, ebx
0x18002044d  jmp     loc_1800202BD
0x180020452  test    rsi, rsi
0x180020455  jz      loc_180020374
0x18002045b  imul    eax, ebx, 342h
0x180020461  mov     [rbp+var_40], eax
0x180020464  cmp     r12, rax
0x180020467  jnb     loc_180020374
0x18002046d  mov     rcx, [rbp+38h]; this
0x180020471  mov     ebx, 8007007Ah
0x180020476  mov     r9d, ebx; char *
0x180020479  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020480  mov     edx, 1C48h; void *
0x180020485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002048a  nop
0x18002048b  lea     rcx, [rbp+var_38]
0x18002048f  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180020494  jmp     short loc_18002041A
0x180020496  mov     eax, 88890004h
0x18002049b  cmp     ebx, eax
0x18002049d  jz      loc_1800202BD
0x1800204a3  mov     edx, 2211h; void *
0x1800204a8  mov     rcx, [rbp+38h]; this
0x1800204ac  mov     r9d, ebx; char *
0x1800204af  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800204b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800204bb  jmp     short loc_18002044B
0x1800204bd  mov     edx, 21FAh
0x1800204c2  jmp     short loc_1800204C9
0x1800204c4  mov     edx, 220Ch
0x1800204c9  mov     ebx, 80004003h
0x1800204ce  jmp     short loc_1800204A8
0x1800204d0  mov     [r13+0], eax
0x1800204d4  test    r15, r15
0x1800204d7  jnz     loc_1800201AF
0x1800204dd  mov     edx, 2205h
0x1800204e2  jmp     short loc_1800204C9
0x1800204e4  mov     [rsi], rax
0x1800204e7  test    r15, r15
0x1800204ea  jnz     short loc_1800204F3
0x1800204ec  mov     edx, 220Bh
0x1800204f1  jmp     short loc_1800204C9
0x1800204f3  test    r13, r13
0x1800204f6  jnz     loc_1800201BC
0x1800204fc  jmp     short loc_1800204C4
0x1800204fe  mov     rcx, [rbp+38h]; this
0x180020502  mov     ebx, 8007000Eh
0x180020507  mov     r9d, ebx; char *
0x18002050a  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020511  mov     edx, 221Bh; void *
0x180020516  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002051b  nop
0x18002051c  jmp     loc_18002044B
0x180020521  mov     r12d, 1D52h
0x180020527  mov     ecx, r12d; cb
0x18002052a  call    cs:__imp_CoTaskMemAlloc
0x180020530  mov     rdi, rax
0x180020533  mov     [rbp+var_30], rax
0x180020537  test    rax, rax
0x18002053a  jnz     short loc_18002055F
0x18002053c  mov     rcx, [rbp+38h]; this
0x180020540  mov     ebx, 8007000Eh
0x180020545  mov     r9d, ebx; char *
0x180020548  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18002054f  mov     edx, 2222h; void *
0x180020554  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020559  nop
0x18002055a  jmp     loc_180020442
0x18002055f  mov     rsi, rax
0x180020562  jmp     loc_18002031B
0x180020567  xor     edx, edx; Val
0x180020569  lea     r8d, [rdx+48h]; Size
0x18002056d  mov     rcx, r14; void *
0x180020570  call    memset_0
0x180020575  xor     ebx, ebx
0x180020577  jmp     loc_180020396
0x18002057c  mov     [rax], rdi
0x18002057f  xor     esi, esi
0x180020581  jmp     loc_1800203BC
0x180020586  mov     [r13+0], ebx
0x18002058a  jmp     loc_1800203C5
```
