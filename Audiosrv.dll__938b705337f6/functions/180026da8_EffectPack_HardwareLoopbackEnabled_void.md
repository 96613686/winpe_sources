# EffectPack::HardwareLoopbackEnabled(void)

- ea: `0x180026da8`
- end: `0x180026fb7`
- name: `?HardwareLoopbackEnabled@EffectPack@@QEAAHXZ`
- size: `527`
- prototype: `__int64 __fastcall(EffectPack *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b139c`
- `0x1800cb5ac`
- `0x1800fa67c`

## callees

- `0x18002088c`
- `0x1800226b0`
- `0x180022fb0`
- `0x180026da8`
- `0x180027620`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026df9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026f49`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026df9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026f49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EffectPack::HardwareLoopbackEnabled(EffectPack *this)
{
  __int64 SupportedConnectorModesInternal; // r8
  int v4; // r9d
  int i; // ecx
  _QWORD *v6; // rdx
  __int64 v7; // rax
  int j; // eax
  _QWORD *v9; // rdx
  __int64 v10; // rcx
  GUID v11; // xmm0
  bool v12; // bl
  struct tWAVEFORMATEX *v13; // [rsp+38h] [rbp-48h] BYREF
  char v14; // [rsp+40h] [rbp-40h]
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v16; // [rsp+58h] [rbp-28h]
  EffectPack *v17; // [rsp+60h] [rbp-20h] BYREF
  int v18; // [rsp+68h] [rbp-18h]
  GUID v19; // [rsp+6Ch] [rbp-14h]
  struct tWAVEFORMATEX *pv; // [rsp+90h] [rbp+10h]

  *(_OWORD *)pvar = 0;
  v16 = 0;
  if ( (*(int (__fastcall **)(_QWORD, void *, PROPVARIANT *))(**(_QWORD **)(*((_QWORD *)this + 198) + 72LL) + 40LL))(
         *(_QWORD *)(*((_QWORD *)this + 198) + 72LL),
         &PKEY_Endpoint_HWAudioEngine_Loopback_ConnectorId,
         pvar) < 0
    || LOWORD(pvar[0]) != 19 )
  {
LABEL_3:
    PropVariantClear(pvar);
    return 0;
  }
  pv = 0;
  v13 = 0;
  v14 = 1;
  SupportedConnectorModesInternal = EffectPack::GetSupportedConnectorModesInternal(this, 0, 0, 1);
  v4 = *(_DWORD *)(SupportedConnectorModesInternal + 8);
  if ( v4 )
  {
    for ( i = 0; i < v4; ++i )
    {
      v6 = (_QWORD *)(*(_QWORD *)SupportedConnectorModesInternal + 16LL * i);
      v7 = *v6 - *(_QWORD *)&GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1;
      if ( *v6 == *(_QWORD *)&GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1 )
        v7 = v6[1] - *(_QWORD *)GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data4;
      if ( !v7 )
      {
        if ( i != -1 )
        {
          v11 = GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3;
          goto LABEL_19;
        }
        break;
      }
    }
    for ( j = 0; j < v4; ++j )
    {
      v9 = (_QWORD *)(*(_QWORD *)SupportedConnectorModesInternal + 16LL * j);
      v10 = *v9 - *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1;
      if ( *v9 == *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1 )
        v10 = v9[1] - *(_QWORD *)GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4;
      if ( !v10 )
      {
        if ( j != -1 )
        {
          v11 = GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf;
          goto LABEL_19;
        }
        break;
      }
    }
    v11 = *(GUID *)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator[](
                     SupportedConnectorModesInternal,
                     0);
  }
  else
  {
    v11 = GUID_00000000_0000_0000_0000_000000000000;
  }
LABEL_19:
  v17 = this;
  v18 = 0;
  v19 = v11;
  v12 = (int)CEndpointCharacteristics::GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___(
               *((CEndpointCharacteristics **)this + 198),
               0,
               0,
               eHostProcessConnector,
               &v17,
               (LPVOID *)&v13) >= 0;
  if ( v14 )
    pv = v13;
  if ( v12 && (unsigned int)ValidateUncompressedWaveFormatEx(pv) == 1 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_3;
  }
  if ( pv )
    CoTaskMemFree(pv);
  PropVariantClear(pvar);
  return 1;
}

```

## disassembly

```asm
0x180026da8  mov     [rsp-8+arg_8], rbx
0x180026dad  push    rbp
0x180026dae  mov     rbp, rsp
0x180026db1  sub     rsp, 80h
0x180026db8  mov     rbx, rcx
0x180026dbb  xorps   xmm0, xmm0
0x180026dbe  xor     eax, eax
0x180026dc0  movups  xmmword ptr [rbp+pvar], xmm0
0x180026dc4  mov     [rbp+var_28], rax
0x180026dc8  mov     rax, [rcx+630h]
0x180026dcf  mov     rcx, [rax+48h]
0x180026dd3  mov     rax, [rcx]
0x180026dd6  lea     r8, [rbp+pvar]
0x180026dda  lea     rdx, PKEY_Endpoint_HWAudioEngine_Loopback_ConnectorId
0x180026de1  mov     rax, [rax+28h]
0x180026de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dea  test    eax, eax
0x180026dec  js      short loc_180026DF5
0x180026dee  cmp     word ptr [rbp+pvar], 13h
0x180026df3  jz      short loc_180026E12
0x180026df5  lea     rcx, [rbp+pvar]; pvar
0x180026df9  call    cs:__imp_PropVariantClear
0x180026dff  xor     eax, eax
0x180026e01  mov     rbx, [rsp+80h+arg_8]
0x180026e09  add     rsp, 80h
0x180026e10  pop     rbp
0x180026e11  retn
0x180026e12  mov     [rbp+pv], 0
0x180026e1a  lea     rax, [rbp+pv]
0x180026e1e  mov     [rbp+var_50], rax
0x180026e22  mov     [rbp+var_48], 0
0x180026e2a  mov     [rbp+var_40], 1
0x180026e2e  mov     r9d, 1
0x180026e34  xor     r8d, r8d
0x180026e37  xor     edx, edx
0x180026e39  mov     rcx, rbx
0x180026e3c  call    ?GetSupportedConnectorModesInternal@EffectPack@@AEAAPEAVCAudioSignalProcessingModeArray@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4FXEnablementConsideration@@W4SED_RESOLVEOPT@@@Z; EffectPack::GetSupportedConnectorModesInternal(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,FXEnablementConsideration,SED_RESOLVEOPT)
0x180026e41  mov     r8, rax
0x180026e44  mov     r9d, [rax+8]
0x180026e48  test    r9d, r9d
0x180026e4b  jz      short loc_180026EC0
0x180026e4d  xor     ecx, ecx
0x180026e4f  cmp     ecx, r9d
0x180026e52  jge     short loc_180026E87
0x180026e54  movsxd  rdx, ecx
0x180026e57  shl     rdx, 4
0x180026e5b  add     rdx, [r8]
0x180026e5e  mov     rax, [rdx]
0x180026e61  sub     rax, qword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x180026e68  jnz     short loc_180026E75
0x180026e6a  mov     rax, [rdx+8]
0x180026e6e  sub     rax, qword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data4
0x180026e75  test    rax, rax
0x180026e78  jz      short loc_180026E7E
0x180026e7a  inc     ecx
0x180026e7c  jmp     short loc_180026E4F
0x180026e7e  cmp     ecx, 0FFFFFFFFh
0x180026e81  jnz     loc_180026F98
0x180026e87  xor     eax, eax
0x180026e89  cmp     eax, r9d
0x180026e8c  jge     loc_180026FA4
0x180026e92  movsxd  rdx, eax
0x180026e95  shl     rdx, 4
0x180026e99  add     rdx, [r8]
0x180026e9c  mov     rcx, [rdx]
0x180026e9f  sub     rcx, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180026ea6  jnz     short loc_180026EB3
0x180026ea8  mov     rcx, [rdx+8]
0x180026eac  sub     rcx, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x180026eb3  test    rcx, rcx
0x180026eb6  jz      loc_180026F87
0x180026ebc  inc     eax
0x180026ebe  jmp     short loc_180026E89
0x180026ec0  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180026ec7  mov     [rbp+var_20], rbx
0x180026ecb  mov     [rbp+var_18], 0
0x180026ed2  movups  [rbp+var_14], xmm0
0x180026ed6  mov     eax, [rbp+var_4]
0x180026ed9  mov     [rbp+var_4], eax
0x180026edc  lea     rax, [rbp+var_48]
0x180026ee0  mov     [rsp+80h+var_58], rax
0x180026ee5  lea     rax, [rbp+var_20]
0x180026ee9  mov     [rsp+80h+var_60], rax
0x180026eee  xor     r9d, r9d
0x180026ef1  xor     r8d, r8d
0x180026ef4  xor     edx, edx
0x180026ef6  mov     rcx, [rbx+630h]
0x180026efd  call    CEndpointCharacteristics__GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___
0x180026f02  mov     ebx, eax
0x180026f04  shr     ebx, 1Fh
0x180026f07  xor     bl, 1
0x180026f0a  cmp     [rbp+var_40], 0
0x180026f0e  jz      short loc_180026F29
0x180026f10  mov     r8, [rbp+var_50]
0x180026f14  mov     rcx, [r8]; pv
0x180026f17  mov     rdx, [rbp+var_48]
0x180026f1b  mov     [r8], rdx
0x180026f1e  test    rcx, rcx
0x180026f21  jz      short loc_180026F29
0x180026f23  call    cs:__imp_CoTaskMemFree
0x180026f29  test    bl, bl
0x180026f2b  jnz     short loc_180026F59
0x180026f2d  mov     rcx, [rbp+pv]; pv
0x180026f31  mov     [rbp+pv], 0
0x180026f39  test    rcx, rcx
0x180026f3c  jz      short loc_180026F45
0x180026f3e  call    cs:__imp_CoTaskMemFree
0x180026f44  nop
0x180026f45  lea     rcx, [rbp+pvar]; pvar
0x180026f49  call    cs:__imp_PropVariantClear
0x180026f4f  mov     eax, 1
0x180026f54  jmp     loc_180026E01
0x180026f59  mov     rcx, [rbp+pv]; struct tWAVEFORMATEX *
0x180026f5d  call    ?ValidateUncompressedWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateUncompressedWaveFormatEx(tWAVEFORMATEX const *)
0x180026f62  cmp     eax, 1
0x180026f65  jnz     short loc_180026F2D
0x180026f67  mov     rcx, [rbp+pv]; pv
0x180026f6b  mov     [rbp+pv], 0
0x180026f73  test    rcx, rcx
0x180026f76  jz      loc_180026DF5
0x180026f7c  call    cs:__imp_CoTaskMemFree
0x180026f82  jmp     loc_180026DF5
0x180026f87  cmp     eax, 0FFFFFFFFh
0x180026f8a  jz      short loc_180026FA4
0x180026f8c  movaps  xmm0, xmmword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180026f93  jmp     loc_180026EC7
0x180026f98  movaps  xmm0, xmmword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x180026f9f  jmp     loc_180026EC7
0x180026fa4  xor     edx, edx
0x180026fa6  mov     rcx, r8
0x180026fa9  call    ??A?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAAEAU_GUID@@H@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator[](int)
0x180026fae  movups  xmm0, xmmword ptr [rax]
0x180026fb1  jmp     loc_180026EC7
```
