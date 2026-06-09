# SensorGroupId::InternalLoadPropertiesFromRegistry(ushort const *)

- ea: `0x18000de78`
- end: `0x18000e4d5`
- name: `?InternalLoadPropertiesFromRegistry@SensorGroupId@@IEAAJPEBG@Z`
- size: `1629`
- prototype: `__int64 __fastcall(SensorGroupId *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18000d270`
- `0x18004fa60`

## callees

- `0x180003ff4`
- `0x180005fa0`
- `0x18000c8b0`
- `0x18000c94c`
- `0x18000de78`
- `0x18000ee30`
- `0x18000fb44`
- `0x180010674`
- `0x180015efc`
- `0x180044f30`
- `0x1800505b4`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000e223`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000e29d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000e2df`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000e223`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000e29d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000e2df`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18000e2f0`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18000e333`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18000e2f0`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18000e333`

## pseudocode

```c
__int64 __fastcall SensorGroupId::InternalLoadPropertiesFromRegistry(SensorGroupId *this, const unsigned __int16 *a2)
{
  unsigned int i; // r14d
  unsigned __int64 v5; // rsi
  const WCHAR *v6; // rdx
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  char v10; // bl
  int v11; // eax
  int v12; // eax
  signed int v13; // ebx
  const unsigned __int16 *v14; // rax
  __int64 v15; // r9
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 j; // r10
  __int64 v21; // rcx
  __int64 v22; // r8
  char v23; // al
  DEVPROPGUID v24; // xmm0
  DEVPROPID k; // esi
  unsigned __int64 v26; // rbx
  const unsigned __int16 *v27; // rax
  const WCHAR *v28; // rcx
  CONFIGRET Device_Interface_PropertyW; // eax
  ULONG v30; // r14d
  char *v31; // r13
  const WCHAR *v32; // r15
  DEVPROPTYPE v33; // r14d
  BYTE *v34; // rbx
  CONFIGRET v35; // eax
  signed int v36; // eax
  signed int v37; // eax
  bool v38; // sf
  const unsigned __int16 *v40; // rax
  __int64 v41; // rdx
  int PropertyBufferSize; // [rsp+20h] [rbp-50h]
  DEVPROPTYPE PropertyType; // [rsp+40h] [rbp-30h] BYREF
  ULONG v44; // [rsp+44h] [rbp-2Ch] BYREF
  DEVPROPKEY PropertyKey; // [rsp+48h] [rbp-28h] BYREF

  if ( a2 )
  {
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        256,
        (unsigned int)&WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
        (_DWORD)this,
        (__int64)a2);
  }
  else
  {
    if ( !*((_QWORD *)this + 141) )
    {
      v13 = -1072875850;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          254,
          &WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
          this,
          -1072875850);
      goto LABEL_84;
    }
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        255,
        (unsigned int)&WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
        (_DWORD)this,
        *((_QWORD *)this + 141));
  }
  for ( i = 0; i < 0x1A; ++i )
  {
    v5 = (unsigned __int64)i << 6;
    if ( *((_BYTE *)this + v5 + 284) && *(_DWORD *)((char *)this + v5 + 280) )
    {
      v6 = *(const WCHAR **)((char *)this + v5 + 272);
      v44 = 0;
      PropertyType = 0;
      v7 = SensorGroupId::LoadFromReg(a2, v6, 0, 0, &PropertyType, &v44);
      v10 = v7;
      if ( v7 < 0 )
      {
        if ( (unsigned __int8)byte_18008D62D >= 8u )
        {
          v14 = SensorGroupProperty::TraceSz((SensorGroupId *)((char *)this + v5 + 256));
          WPP_SF_qDS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            257,
            (unsigned int)&WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
            (_DWORD)this,
            v10,
            (__int64)v14);
        }
      }
      else
      {
        v11 = *(_DWORD *)((char *)this + v5 + 280);
        if ( v44 == v11 )
        {
          v12 = SensorGroupProperty::Allocate((SensorGroupId *)((char *)this + v5 + 256), PropertyType);
          v13 = v12;
          if ( v12 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_83;
            v16 = 259;
            goto LABEL_82;
          }
          v12 = SensorGroupId::LoadFromReg(
                  a2,
                  *(LPCWSTR *)((char *)this + v5 + 272),
                  *(LPBYTE *)((char *)this + v5 + 296),
                  *(_DWORD *)((char *)this + v5 + 292),
                  &PropertyType,
                  0);
          v13 = v12;
          if ( v12 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_83;
            v16 = 260;
LABEL_82:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v16,
              &WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
              this,
              v12);
            goto LABEL_83;
          }
          if ( (unsigned __int8)byte_18008D62D >= 8u )
          {
            v27 = SensorGroupProperty::TraceSz((SensorGroupId *)((char *)this + v5 + 256));
            WPP_SF_qS(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              261,
              (unsigned int)&WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
              (_DWORD)this,
              (__int64)v27);
          }
        }
        else if ( byte_18008D62D )
        {
          WPP_SF_qDSDD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v8,
            v9,
            (_DWORD)this,
            PropertyBufferSize,
            *(_QWORD *)((char *)this + v5 + 272),
            v11,
            v44);
        }
      }
    }
  }
  if ( *((_QWORD *)this + 141) )
    goto LABEL_33;
  v12 = SensorGroupProperty::Allocate((SensorGroupId *)((char *)this + 1088), 0x82u);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_83;
    v16 = 262;
    goto LABEL_82;
  }
  v15 = *((_QWORD *)this + 8) + 8LL;
  if ( *((_QWORD *)this + 8) == -8 )
  {
    v13 = -2147024809;
    goto LABEL_78;
  }
  v17 = *((_DWORD *)this + 281) >> 1;
  v18 = *((_QWORD *)this + 141);
  if ( v17 )
  {
    if ( v17 >= 0x41 )
    {
      LODWORD(v19) = 0;
      for ( j = 0; j != 32; ++j )
      {
        v21 = (unsigned int)v19;
        v22 = (unsigned int)(v19 + 1);
        *(_WORD *)(v18 + 2 * v21) = a0123456789abcd[(unsigned __int64)*(unsigned __int8 *)(v15 + j) >> 4];
        v23 = *(_BYTE *)(v15 + j);
        *(_WORD *)(v18 + 2 * v22) = a0123456789abcd[v23 & 0xF];
        v19 = (unsigned int)(v22 + 1);
      }
      *(_WORD *)(v18 + 2 * v19) = 0;
      goto LABEL_33;
    }
LABEL_77:
    v13 = -1072860816;
LABEL_78:
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 263, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v13);
    goto LABEL_83;
  }
  if ( v18 )
    goto LABEL_77;
LABEL_33:
  v13 = SensorGroupId::ValidateSensorGroupProperties(this);
  if ( v13 < 0 )
    goto LABEL_83;
  v24 = (DEVPROPGUID)SensorGroupFMTGUID;
  for ( k = 0; k < 0x1A; ++k )
  {
    v26 = (unsigned __int64)k << 6;
    if ( *((_BYTE *)this + v26 + 284) )
    {
      if ( !*(_DWORD *)((char *)this + v26 + 280) )
      {
        if ( *(_DWORD *)((char *)this + v26 + 268) )
        {
          v28 = (const WCHAR *)*((_QWORD *)this + 69);
          PropertyKey.pid = k;
          PropertyType = 0;
          v44 = 0;
          PropertyKey.fmtid = v24;
          if ( v28 )
          {
            Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(v28, &PropertyKey, &PropertyType, 0, &v44, 0);
            v30 = v44;
            if ( Device_Interface_PropertyW == 26 || !Device_Interface_PropertyW )
              goto LABEL_90;
            v37 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0xDu);
            v38 = v37 < 0;
            if ( v37 > 0 )
              v38 = 1;
            if ( !v38 )
            {
LABEL_90:
              if ( v30 )
              {
                v31 = (char *)this + v26;
                if ( SensorGroupProperty::Allocate((SensorGroupId *)((char *)this + v26 + 256), v30) >= 0 )
                {
                  v32 = (const WCHAR *)*((_QWORD *)this + 69);
                  v44 = 0;
                  PropertyType = 0;
                  if ( !v32 )
                  {
                    v13 = -2147024809;
                    goto LABEL_72;
                  }
                  v33 = *(_DWORD *)((char *)this + v26 + 292);
                  v34 = *(BYTE **)((char *)this + v26 + 296);
                  v35 = CM_Get_Device_Interface_PropertyW(v32, &PropertyKey, &v44, 0, &PropertyType, 0);
                  if ( v35 == 26 )
                  {
                    if ( v34 && v33 )
                    {
                      if ( PropertyType > v33 )
                      {
                        v13 = -1072860816;
LABEL_72:
                        v12 = v13;
LABEL_66:
                        if ( !g_wppLevels )
                          goto LABEL_83;
                        v16 = 264;
                        goto LABEL_82;
                      }
                      PropertyType = v33;
                      v35 = CM_Get_Device_Interface_PropertyW(v32, &PropertyKey, &v44, v34, &PropertyType, 0);
                      goto LABEL_54;
                    }
                  }
                  else
                  {
LABEL_54:
                    if ( v35 )
                    {
                      v36 = CM_MapCrToWin32Err(v35, 0xDu);
                      v13 = v36;
                      if ( v36 > 0 )
                        v13 = (unsigned __int16)v36 | 0x80070000;
                      v12 = v13;
                      if ( v13 < 0 )
                        goto LABEL_66;
                    }
                  }
                  if ( (unsigned __int8)byte_18008D62D >= 8u )
                  {
                    v40 = SensorGroupProperty::TraceSz((SensorGroupProperty *)(v31 + 256));
                    WPP_SF_qS(
                      *((_QWORD *)WPP_GLOBAL_Control + 27),
                      265,
                      (unsigned int)&WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
                      (_DWORD)this,
                      (__int64)v40);
                  }
                }
              }
            }
            v24 = (DEVPROPGUID)SensorGroupFMTGUID;
            continue;
          }
        }
      }
    }
  }
  v12 = SensorGroupId::InternalParseDeviceNames(this);
  v13 = v12;
  if ( v12 >= 0 )
    goto LABEL_69;
  if ( g_wppLevels )
  {
    v16 = 266;
    goto LABEL_82;
  }
LABEL_83:
  if ( v13 == -1072875818 )
  {
LABEL_69:
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      v41 = 268;
LABEL_87:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v41, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v13);
    }
  }
  else
  {
LABEL_84:
    if ( byte_18008D62D )
    {
      v41 = 267;
      goto LABEL_87;
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000de78  mov     [rsp-28h+arg_10], rbx
0x18000de7d  mov     [rsp-28h+arg_18], rsi
0x18000de82  push    rbp
0x18000de83  push    rdi
0x18000de84  push    r13
0x18000de86  push    r14
0x18000de88  push    r15
0x18000de8a  mov     rbp, rsp
0x18000de8d  sub     rsp, 70h
0x18000de91  mov     rax, cs:__security_cookie
0x18000de98  xor     rax, rsp
0x18000de9b  mov     [rbp+var_10], rax
0x18000de9f  xor     r13d, r13d
0x18000dea2  mov     r15, rdx
0x18000dea5  mov     rdi, rcx
0x18000dea8  test    rdx, rdx
0x18000deab  jz      loc_18000E084
0x18000deb1  cmp     cs:byte_18008D62D, 8
0x18000deb8  jnb     loc_18000E410
0x18000debe  mov     r14d, r13d
0x18000dec1  cmp     r14d, 1Ah
0x18000dec5  jnb     loc_18000DFF0
0x18000decb  mov     esi, r14d
0x18000dece  shl     rsi, 6
0x18000ded2  cmp     [rsi+rdi+11Ch], r13b
0x18000deda  jz      loc_18000DFA3
0x18000dee0  cmp     [rsi+rdi+118h], r13d
0x18000dee8  jz      loc_18000DFA3
0x18000deee  mov     rdx, [rsi+rdi+110h]; lpValueName
0x18000def6  lea     rax, [rbp+var_2C]
0x18000defa  mov     qword ptr [rsp+70h+ulFlags], rax; unsigned int *
0x18000deff  xor     r9d, r9d; unsigned int
0x18000df02  lea     rax, [rbp+PropertyType]
0x18000df06  mov     [rbp+var_2C], r13d
0x18000df0a  xor     r8d, r8d; lpData
0x18000df0d  mov     [rsp+70h+PropertyBufferSize], rax; unsigned int *
0x18000df12  mov     rcx, r15; unsigned __int16 *
0x18000df15  mov     [rbp+PropertyType], r13d
0x18000df19  call    ?LoadFromReg@SensorGroupId@@SAJPEBG0PEAEKPEAK2@Z; SensorGroupId::LoadFromReg(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x18000df1e  mov     ebx, eax
0x18000df20  test    eax, eax
0x18000df22  js      loc_18000DFAB
0x18000df28  mov     eax, [rsi+rdi+118h]
0x18000df2f  mov     ecx, [rbp+var_2C]
0x18000df32  cmp     ecx, eax
0x18000df34  jnz     loc_18000E030
0x18000df3a  mov     edx, [rbp+PropertyType]; unsigned int
0x18000df3d  lea     r13, [rsi+rdi]
0x18000df41  lea     rcx, [r13+100h]; this
0x18000df48  call    ?Allocate@SensorGroupProperty@@QEAAJK@Z; SensorGroupProperty::Allocate(ulong)
0x18000df4d  mov     ebx, eax
0x18000df4f  test    eax, eax
0x18000df51  js      loc_18000E1C9
0x18000df57  mov     r9d, [rsi+rdi+124h]; unsigned int
0x18000df5f  lea     rax, [rbp+PropertyType]
0x18000df63  mov     r8, [rsi+rdi+128h]; lpData
0x18000df6b  mov     rcx, r15; unsigned __int16 *
0x18000df6e  mov     rdx, [rsi+rdi+110h]; lpValueName
0x18000df76  mov     qword ptr [rsp+70h+ulFlags], 0; unsigned int *
0x18000df7f  mov     [rsp+70h+PropertyBufferSize], rax; unsigned int *
0x18000df84  call    ?LoadFromReg@SensorGroupId@@SAJPEBG0PEAEKPEAK2@Z; SensorGroupId::LoadFromReg(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x18000df89  mov     ebx, eax
0x18000df8b  test    eax, eax
0x18000df8d  js      loc_18000E06D
0x18000df93  cmp     cs:byte_18008D62D, 8
0x18000df9a  jnb     loc_18000E191
0x18000dfa0  xor     r13d, r13d
0x18000dfa3  inc     r14d
0x18000dfa6  jmp     loc_18000DEC1
0x18000dfab  cmp     cs:byte_18008D62D, 8
0x18000dfb2  jb      short loc_18000DFA3
0x18000dfb4  lea     rcx, [rdi+100h]
0x18000dfbb  add     rcx, rsi; this
0x18000dfbe  call    ?TraceSz@SensorGroupProperty@@QEAAPEBGXZ; SensorGroupProperty::TraceSz(void)
0x18000dfc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfca  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18000dfd1  mov     qword ptr [rsp+70h+ulFlags], rax
0x18000dfd6  mov     edx, 101h
0x18000dfdb  mov     r9, rdi
0x18000dfde  mov     dword ptr [rsp+70h+PropertyBufferSize], ebx
0x18000dfe2  mov     rcx, [rcx+0D8h]
0x18000dfe9  call    WPP_SF_qDS
0x18000dfee  jmp     short loc_18000DFA3
0x18000dff0  cmp     [rdi+468h], r13
0x18000dff7  jnz     loc_18000E134
0x18000dffd  lea     rcx, [rdi+440h]; this
0x18000e004  mov     edx, 82h; unsigned int
0x18000e009  call    ?Allocate@SensorGroupProperty@@QEAAJK@Z; SensorGroupProperty::Allocate(ulong)
0x18000e00e  mov     ebx, eax
0x18000e010  test    eax, eax
0x18000e012  js      loc_18000E17A
0x18000e018  mov     r9, [rdi+40h]
0x18000e01c  add     r9, 8
0x18000e020  jnz     loc_18000E0CE
0x18000e026  mov     ebx, 80070057h
0x18000e02b  jmp     loc_18000E44A
0x18000e030  cmp     cs:byte_18008D62D, 1
0x18000e037  jb      loc_18000DFA3
0x18000e03d  mov     [rsp+70h+var_38], ecx
0x18000e041  mov     r9, rdi
0x18000e044  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e04b  mov     [rsp+70h+var_40], eax
0x18000e04f  mov     rax, [rsi+rdi+110h]
0x18000e057  mov     qword ptr [rsp+70h+ulFlags], rax
0x18000e05c  mov     rcx, [rcx+0D8h]
0x18000e063  call    WPP_SF_qDSDD
0x18000e068  jmp     loc_18000DFA3
0x18000e06d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000e074  jb      loc_18000E48A
0x18000e07a  mov     edx, 104h
0x18000e07f  jmp     loc_18000E46C
0x18000e084  mov     rax, [rcx+468h]
0x18000e08b  test    rax, rax
0x18000e08e  jnz     loc_18000E3F7
0x18000e094  mov     ebx, 0C00D36B6h
0x18000e099  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000e0a0  jb      loc_18000E496
0x18000e0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0ad  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18000e0b4  mov     edx, 0FEh
0x18000e0b9  mov     dword ptr [rsp+70h+PropertyBufferSize], ebx
0x18000e0bd  mov     r9, rdi
0x18000e0c0  mov     rcx, [rcx+10h]
0x18000e0c4  call    WPP_SF_qD
0x18000e0c9  jmp     loc_18000E496
0x18000e0ce  mov     eax, [rdi+464h]
0x18000e0d4  shr     eax, 1
0x18000e0d6  mov     rdx, [rdi+468h]
0x18000e0dd  jz      loc_18000E43C
0x18000e0e3  cmp     eax, 41h ; 'A'
0x18000e0e6  jb      loc_18000E445
0x18000e0ec  mov     r8d, r13d
0x18000e0ef  lea     r11, a0123456789abcd; "0123456789ABCDEF"
0x18000e0f6  mov     r10, r13
0x18000e0f9  movzx   eax, byte ptr [r9+r10]
0x18000e0fe  shr     rax, 4
0x18000e102  mov     ecx, r8d
0x18000e105  inc     r8d
0x18000e108  movzx   eax, word ptr [r11+rax*2]
0x18000e10d  mov     [rdx+rcx*2], ax
0x18000e111  movzx   eax, byte ptr [r9+r10]
0x18000e116  inc     r10
0x18000e119  and     eax, 0Fh
0x18000e11c  movzx   eax, word ptr [r11+rax*2]
0x18000e121  mov     [rdx+r8*2], ax
0x18000e126  inc     r8d
0x18000e129  cmp     r10, 20h ; ' '
0x18000e12d  jnz     short loc_18000E0F9
0x18000e12f  mov     [rdx+r8*2], r13w
0x18000e134  mov     rcx, rdi; this
0x18000e137  call    ?ValidateSensorGroupProperties@SensorGroupId@@IEAAJXZ; SensorGroupId::ValidateSensorGroupProperties(void)
0x18000e13c  mov     ebx, eax
0x18000e13e  test    eax, eax
0x18000e140  js      loc_18000E48A
0x18000e146  movups  xmm0, cs:SensorGroupFMTGUID
0x18000e14d  mov     esi, r13d
0x18000e150  cmp     esi, 1Ah
0x18000e153  jnb     loc_18000E366
0x18000e159  mov     ebx, esi
0x18000e15b  shl     rbx, 6
0x18000e15f  cmp     [rbx+rdi+11Ch], r13b
0x18000e167  jz      short loc_18000E173
0x18000e169  cmp     [rbx+rdi+118h], r13d
0x18000e171  jz      short loc_18000E1E0
0x18000e173  inc     esi
0x18000e175  xor     r13d, r13d
0x18000e178  jmp     short loc_18000E150
0x18000e17a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000e181  jb      loc_18000E48A
0x18000e187  mov     edx, 106h
0x18000e18c  jmp     loc_18000E46C
0x18000e191  lea     rcx, [r13+100h]; this
0x18000e198  call    ?TraceSz@SensorGroupProperty@@QEAAPEBGXZ; SensorGroupProperty::TraceSz(void)
0x18000e19d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1a4  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18000e1ab  mov     edx, 105h
0x18000e1b0  mov     [rsp+70h+PropertyBufferSize], rax
0x18000e1b5  mov     r9, rdi
0x18000e1b8  mov     rcx, [rcx+0D8h]
0x18000e1bf  call    WPP_SF_qS
0x18000e1c4  jmp     loc_18000DFA0
0x18000e1c9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000e1d0  jb      loc_18000E48A
0x18000e1d6  mov     edx, 103h
0x18000e1db  jmp     loc_18000E46C
0x18000e1e0  cmp     [rbx+rdi+10Ch], r13d
0x18000e1e8  jz      short loc_18000E173
0x18000e1ea  mov     rcx, [rdi+228h]; pszDeviceInterface
0x18000e1f1  mov     [rbp+PropertyKey.pid], esi
0x18000e1f4  mov     [rbp+PropertyType], r13d
0x18000e1f8  mov     [rbp+var_2C], r13d
0x18000e1fc  movdqu  xmmword ptr [rbp+PropertyKey.fmtid.Data1], xmm0
0x18000e201  test    rcx, rcx
0x18000e204  jz      loc_18000E173
0x18000e20a  lea     rax, [rbp+var_2C]
0x18000e20e  mov     [rsp+70h+ulFlags], r13d; ulFlags
0x18000e213  xor     r9d, r9d; PropertyBuffer
0x18000e216  mov     [rsp+70h+PropertyBufferSize], rax; PropertyBufferSize
0x18000e21b  lea     r8, [rbp+PropertyType]; PropertyType
0x18000e21f  lea     rdx, [rbp+PropertyKey]; PropertyKey
0x18000e223  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x18000e229  mov     r14d, [rbp+var_2C]
0x18000e22d  cmp     eax, 1Ah
0x18000e230  jnz     loc_18000E324
0x18000e236  test    r14d, r14d
0x18000e239  jz      loc_18000E318
0x18000e23f  lea     r13, [rbx+rdi]
0x18000e243  mov     edx, r14d; unsigned int
0x18000e246  lea     rcx, [r13+100h]; this
0x18000e24d  call    ?Allocate@SensorGroupProperty@@QEAAJK@Z; SensorGroupProperty::Allocate(ulong)
0x18000e252  xor     ecx, ecx
0x18000e254  test    eax, eax
0x18000e256  js      loc_18000E318
0x18000e25c  mov     r15, [rdi+228h]
0x18000e263  mov     [rbp+var_2C], ecx
0x18000e266  mov     [rbp+PropertyType], ecx
0x18000e269  test    r15, r15
0x18000e26c  jz      loc_18000E3F0
0x18000e272  mov     r14d, [rbx+rdi+124h]
0x18000e27a  lea     rax, [rbp+PropertyType]
0x18000e27e  mov     rbx, [rbx+rdi+128h]
0x18000e286  lea     r8, [rbp+var_2C]; PropertyType
0x18000e28a  mov     [rsp+70h+ulFlags], ecx; ulFlags
0x18000e28e  lea     rdx, [rbp+PropertyKey]; PropertyKey
0x18000e292  mov     rcx, r15; pszDeviceInterface
0x18000e295  mov     [rsp+70h+PropertyBufferSize], rax; PropertyBufferSize
0x18000e29a  xor     r9d, r9d; PropertyBuffer
0x18000e29d  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x18000e2a3  cmp     eax, 1Ah
0x18000e2a6  jnz     short loc_18000E2E5
0x18000e2a8  test    rbx, rbx
0x18000e2ab  jz      short loc_18000E30B
0x18000e2ad  test    r14d, r14d
0x18000e2b0  jz      short loc_18000E30B
0x18000e2b2  cmp     [rbp+PropertyType], r14d
0x18000e2b6  ja      loc_18000E3E4
0x18000e2bc  lea     rax, [rbp+PropertyType]
0x18000e2c0  mov     [rsp+70h+ulFlags], 0; ulFlags
0x18000e2c8  mov     r9, rbx; PropertyBuffer
0x18000e2cb  mov     [rsp+70h+PropertyBufferSize], rax; PropertyBufferSize
0x18000e2d0  lea     r8, [rbp+var_2C]; PropertyType
0x18000e2d4  mov     [rbp+PropertyType], r14d
0x18000e2d8  lea     rdx, [rbp+PropertyKey]; PropertyKey
0x18000e2dc  mov     rcx, r15; pszDeviceInterface
0x18000e2df  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x18000e2e5  test    eax, eax
0x18000e2e7  jz      short loc_18000E30B
0x18000e2e9  mov     edx, 0Dh; DefaultErr
0x18000e2ee  mov     ecx, eax; CmReturnCode
0x18000e2f0  call    cs:__imp_CM_MapCrToWin32Err
0x18000e2f6  mov     ebx, eax
0x18000e2f8  test    eax, eax
0x18000e2fa  jle     short loc_18000E305
0x18000e2fc  movzx   ebx, ax
0x18000e2ff  or      ebx, 80070000h
0x18000e305  mov     eax, ebx
0x18000e307  test    ebx, ebx
0x18000e309  js      short loc_18000E34F
0x18000e30b  cmp     cs:byte_18008D62D, 8
0x18000e312  jnb     loc_18000E3AC
0x18000e318  movups  xmm0, cs:SensorGroupFMTGUID
0x18000e31f  jmp     loc_18000E173
0x18000e324  test    eax, eax
0x18000e326  jz      loc_18000E236
0x18000e32c  mov     edx, 0Dh; DefaultErr
0x18000e331  mov     ecx, eax; CmReturnCode
0x18000e333  call    cs:__imp_CM_MapCrToWin32Err
0x18000e339  test    eax, eax
0x18000e33b  jle     short loc_18000E347
0x18000e33d  movzx   eax, ax
0x18000e340  or      eax, 80070000h
0x18000e345  test    eax, eax
0x18000e347  jns     loc_18000E236
0x18000e34d  jmp     short loc_18000E318
0x18000e34f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000e356  jb      loc_18000E48A
0x18000e35c  mov     edx, 108h
0x18000e361  jmp     loc_18000E46C
0x18000e366  mov     rcx, rdi; this
0x18000e369  call    ?InternalParseDeviceNames@SensorGroupId@@IEAAJXZ; SensorGroupId::InternalParseDeviceNames(void)
0x18000e36e  mov     ebx, eax
0x18000e370  test    eax, eax
0x18000e372  js      loc_18000E45E
0x18000e378  cmp     cs:byte_18008D62D, 8
0x18000e37f  jnb     loc_18000E4AA
0x18000e385  mov     eax, ebx
0x18000e387  mov     rcx, [rbp+var_10]
0x18000e38b  xor     rcx, rsp; StackCookie
0x18000e38e  call    __security_check_cookie
0x18000e393  lea     r11, [rsp+70h+var_s0]
0x18000e398  mov     rbx, [r11+40h]
0x18000e39c  mov     rsi, [r11+48h]
0x18000e3a0  mov     rsp, r11
0x18000e3a3  pop     r15
0x18000e3a5  pop     r14
0x18000e3a7  pop     r13
0x18000e3a9  pop     rdi
0x18000e3aa  pop     rbp
0x18000e3ab  retn
0x18000e3ac  lea     rcx, [r13+100h]; this
  ... truncated ...
```
