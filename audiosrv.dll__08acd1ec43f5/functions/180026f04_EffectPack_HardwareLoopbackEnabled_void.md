# EffectPack::HardwareLoopbackEnabled(void)

- ea: `0x180026f04`
- end: `0x180027113`
- name: `?HardwareLoopbackEnabled@EffectPack@@QEAAHXZ`
- size: `527`
- prototype: `__int64 __fastcall(EffectPack *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800af6ac`
- `0x1800c95bc`
- `0x1800fa90c`

## callees

- `0x1800209dc`
- `0x180022800`
- `0x180023100`
- `0x180026f04`
- `0x180027780`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026f55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800270a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026f55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800270a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002707f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002709a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800270d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002707f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002709a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800270d8`

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
  if ( (*(int (__fastcall **)(_QWORD, __int64 *, PROPVARIANT *))(**(_QWORD **)(*((_QWORD *)this + 198) + 72LL) + 40LL))(
         *(_QWORD *)(*((_QWORD *)this + 198) + 72LL),
         PKEY_Endpoint_HWAudioEngine_Loopback_ConnectorId,
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
0x180026f04  mov     [rsp-8+arg_8], rbx
0x180026f09  push    rbp
0x180026f0a  mov     rbp, rsp
0x180026f0d  sub     rsp, 80h
0x180026f14  mov     rbx, rcx
0x180026f17  xorps   xmm0, xmm0
0x180026f1a  xor     eax, eax
0x180026f1c  movups  xmmword ptr [rbp+pvar], xmm0
0x180026f20  mov     [rbp+var_28], rax
0x180026f24  mov     rax, [rcx+630h]
0x180026f2b  mov     rcx, [rax+48h]
0x180026f2f  mov     rax, [rcx]
0x180026f32  lea     r8, [rbp+pvar]
0x180026f36  lea     rdx, PKEY_Endpoint_HWAudioEngine_Loopback_ConnectorId
0x180026f3d  mov     rax, [rax+28h]
0x180026f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f46  test    eax, eax
0x180026f48  js      short loc_180026F51
0x180026f4a  cmp     word ptr [rbp+pvar], 13h
0x180026f4f  jz      short loc_180026F6E
0x180026f51  lea     rcx, [rbp+pvar]; pvar
0x180026f55  call    cs:__imp_PropVariantClear
0x180026f5b  xor     eax, eax
0x180026f5d  mov     rbx, [rsp+80h+arg_8]
0x180026f65  add     rsp, 80h
0x180026f6c  pop     rbp
0x180026f6d  retn
0x180026f6e  mov     [rbp+pv], 0
0x180026f76  lea     rax, [rbp+pv]
0x180026f7a  mov     [rbp+var_50], rax
0x180026f7e  mov     [rbp+var_48], 0
0x180026f86  mov     [rbp+var_40], 1
0x180026f8a  mov     r9d, 1
0x180026f90  xor     r8d, r8d
0x180026f93  xor     edx, edx
0x180026f95  mov     rcx, rbx
0x180026f98  call    ?GetSupportedConnectorModesInternal@EffectPack@@AEAAPEAVCAudioSignalProcessingModeArray@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4FXEnablementConsideration@@W4SED_RESOLVEOPT@@@Z; EffectPack::GetSupportedConnectorModesInternal(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,FXEnablementConsideration,SED_RESOLVEOPT)
0x180026f9d  mov     r8, rax
0x180026fa0  mov     r9d, [rax+8]
0x180026fa4  test    r9d, r9d
0x180026fa7  jz      short loc_18002701C
0x180026fa9  xor     ecx, ecx
0x180026fab  cmp     ecx, r9d
0x180026fae  jge     short loc_180026FE3
0x180026fb0  movsxd  rdx, ecx
0x180026fb3  shl     rdx, 4
0x180026fb7  add     rdx, [r8]
0x180026fba  mov     rax, [rdx]
0x180026fbd  sub     rax, qword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x180026fc4  jnz     short loc_180026FD1
0x180026fc6  mov     rax, [rdx+8]
0x180026fca  sub     rax, qword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data4
0x180026fd1  test    rax, rax
0x180026fd4  jz      short loc_180026FDA
0x180026fd6  inc     ecx
0x180026fd8  jmp     short loc_180026FAB
0x180026fda  cmp     ecx, 0FFFFFFFFh
0x180026fdd  jnz     loc_1800270F4
0x180026fe3  xor     eax, eax
0x180026fe5  cmp     eax, r9d
0x180026fe8  jge     loc_180027100
0x180026fee  movsxd  rdx, eax
0x180026ff1  shl     rdx, 4
0x180026ff5  add     rdx, [r8]
0x180026ff8  mov     rcx, [rdx]
0x180026ffb  sub     rcx, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180027002  jnz     short loc_18002700F
0x180027004  mov     rcx, [rdx+8]
0x180027008  sub     rcx, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x18002700f  test    rcx, rcx
0x180027012  jz      loc_1800270E3
0x180027018  inc     eax
0x18002701a  jmp     short loc_180026FE5
0x18002701c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180027023  mov     [rbp+var_20], rbx
0x180027027  mov     [rbp+var_18], 0
0x18002702e  movups  [rbp+var_14], xmm0
0x180027032  mov     eax, [rbp+var_4]
0x180027035  mov     [rbp+var_4], eax
0x180027038  lea     rax, [rbp+var_48]
0x18002703c  mov     [rsp+80h+var_58], rax
0x180027041  lea     rax, [rbp+var_20]
0x180027045  mov     [rsp+80h+var_60], rax
0x18002704a  xor     r9d, r9d
0x18002704d  xor     r8d, r8d
0x180027050  xor     edx, edx
0x180027052  mov     rcx, [rbx+630h]
0x180027059  call    CEndpointCharacteristics__GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___
0x18002705e  mov     ebx, eax
0x180027060  shr     ebx, 1Fh
0x180027063  xor     bl, 1
0x180027066  cmp     [rbp+var_40], 0
0x18002706a  jz      short loc_180027085
0x18002706c  mov     r8, [rbp+var_50]
0x180027070  mov     rcx, [r8]; pv
0x180027073  mov     rdx, [rbp+var_48]
0x180027077  mov     [r8], rdx
0x18002707a  test    rcx, rcx
0x18002707d  jz      short loc_180027085
0x18002707f  call    cs:__imp_CoTaskMemFree
0x180027085  test    bl, bl
0x180027087  jnz     short loc_1800270B5
0x180027089  mov     rcx, [rbp+pv]; pv
0x18002708d  mov     [rbp+pv], 0
0x180027095  test    rcx, rcx
0x180027098  jz      short loc_1800270A1
0x18002709a  call    cs:__imp_CoTaskMemFree
0x1800270a0  nop
0x1800270a1  lea     rcx, [rbp+pvar]; pvar
0x1800270a5  call    cs:__imp_PropVariantClear
0x1800270ab  mov     eax, 1
0x1800270b0  jmp     loc_180026F5D
0x1800270b5  mov     rcx, [rbp+pv]; struct tWAVEFORMATEX *
0x1800270b9  call    ?ValidateUncompressedWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateUncompressedWaveFormatEx(tWAVEFORMATEX const *)
0x1800270be  cmp     eax, 1
0x1800270c1  jnz     short loc_180027089
0x1800270c3  mov     rcx, [rbp+pv]; pv
0x1800270c7  mov     [rbp+pv], 0
0x1800270cf  test    rcx, rcx
0x1800270d2  jz      loc_180026F51
0x1800270d8  call    cs:__imp_CoTaskMemFree
0x1800270de  jmp     loc_180026F51
0x1800270e3  cmp     eax, 0FFFFFFFFh
0x1800270e6  jz      short loc_180027100
0x1800270e8  movaps  xmm0, xmmword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x1800270ef  jmp     loc_180027023
0x1800270f4  movaps  xmm0, xmmword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x1800270fb  jmp     loc_180027023
0x180027100  xor     edx, edx
0x180027102  mov     rcx, r8
0x180027105  call    ??A?$CSimpleArray@U_GUID@@V?$CSimpleArrayEqualHelper@U_GUID@@@ATL@@@ATL@@QEAAAEAU_GUID@@H@Z; ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::operator[](int)
0x18002710a  movups  xmm0, xmmword ptr [rax]
0x18002710d  jmp     loc_180027023
```
