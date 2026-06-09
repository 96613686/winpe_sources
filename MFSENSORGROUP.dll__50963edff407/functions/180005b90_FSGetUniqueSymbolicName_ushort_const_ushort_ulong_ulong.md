# FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)

- ea: `0x180005b90`
- end: `0x180005f98`
- name: `?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z`
- size: `1032`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `12`
- callee_count: `4`
- tags: `reparse_path, registry_config`

## callers

- `0x180004610`
- `0x1800049b0`
- `0x180005820`
- `0x180006230`
- `0x18001291c`
- `0x18003c55c`
- `0x18003fadc`
- `0x18003fe70`
- `0x180051018`
- `0x180066ae0`
- `0x180070948`
- `0x180071e68`

## callees

- `0x180005b90`
- `0x180005fa0`
- `0x180044f30`
- `0x180045900`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180005c9d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180005c9d`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x180005c60`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x180005c60`

## pseudocode

```c
__int64 __fastcall FSGetUniqueSymbolicName(
        LPCWSTR pszDeviceInterface,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r13
  unsigned __int16 *v6; // rbx
  const WCHAR *v7; // rdi
  int i; // esi
  __int64 v9; // rcx
  WCHAR *v10; // rax
  unsigned int v11; // r14d
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // r8
  __int64 v14; // rax
  WCHAR *v15; // rdx
  __int64 v17; // rcx
  const WCHAR *v18; // rax
  unsigned __int64 v19; // r15
  unsigned __int64 v20; // rdx
  __int64 v21; // rax
  unsigned int v22; // ecx
  __int64 v23; // rdx
  BYTE PropertyBuffer[8]; // [rsp+30h] [rbp-D0h] BYREF
  ULONG pulLength[2]; // [rsp+38h] [rbp-C8h] BYREF
  ULONG PropertyBufferSize; // [rsp+40h] [rbp-C0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+44h] [rbp-BCh] BYREF
  _OWORD v28[3]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszAliasDeviceInterface[264]; // [rsp+80h] [rbp-80h] BYREF

  v4 = a3;
  v6 = a2;
  v7 = pszDeviceInterface;
  v28[0] = GUID_e5323777_f976_4f5b_9b55_b94699c46e44;
  v28[1] = GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca;
  v28[2] = GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8;
  if ( !pszDeviceInterface )
    return (unsigned int)-2147024809;
  if ( !a2 )
  {
    if ( !a4 )
      return (unsigned int)-2147467261;
    goto LABEL_49;
  }
  if ( a4 )
LABEL_49:
    *a4 = 0;
  for ( i = 0; (unsigned __int64)i < 3; ++i )
  {
    memset_0(pszAliasDeviceInterface, 0, 0x208u);
    *(_QWORD *)pulLength = 260;
    if ( !CM_Get_Device_Interface_AliasW(v7, (LPGUID)&v28[i], pszAliasDeviceInterface, pulLength, 0) )
    {
      PropertyType = 0;
      PropertyBuffer[0] = 0;
      PropertyBufferSize = 1;
      if ( !CM_Get_Device_Interface_PropertyW(
              pszAliasDeviceInterface,
              &DEVPKEY_DeviceInterface_Enabled,
              &PropertyType,
              PropertyBuffer,
              &PropertyBufferSize,
              0)
        && PropertyBuffer[0] == 0xFF )
      {
        v9 = 260;
        v10 = pszAliasDeviceInterface;
        do
        {
          if ( !*v10 )
            break;
          ++v10;
          --v9;
        }
        while ( v9 );
        v11 = -2147024809;
        if ( !v9 )
        {
          *(_QWORD *)pulLength = 0;
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
              0,
              -2147024809);
          return (unsigned int)-2147024809;
        }
        v12 = 260 - v9 + 1;
        *(_QWORD *)pulLength = v12;
        if ( a4 )
          *a4 = v12;
        if ( !v6 || !(_DWORD)v4 )
        {
          v11 = 0;
          if ( !a4 )
            return (unsigned int)-2147467261;
          return v11;
        }
        v13 = v4;
        if ( v4 >= v12 )
        {
          if ( v4 > 0x7FFFFFFF )
          {
            *v6 = 0;
          }
          else
          {
            v14 = 2147483646;
            v15 = pszAliasDeviceInterface;
            v11 = 0;
            while ( v14 && *v15 )
            {
              *v6++ = *v15++;
              --v14;
              if ( !--v13 )
              {
                --v6;
                v11 = -2147024774;
                break;
              }
            }
            *v6 = 0;
            if ( (v11 & 0x80000000) == 0 )
              return v11;
          }
          v22 = v11;
          if ( !g_wppLevels )
            return v11;
          v23 = 32;
LABEL_47:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v22);
          return v11;
        }
        return (unsigned int)-1072860816;
      }
    }
  }
  v17 = 260;
  v18 = v7;
  do
  {
    if ( !*v18 )
      break;
    ++v18;
    --v17;
  }
  while ( v17 );
  v11 = -2147024809;
  if ( !v17 )
  {
    *(_QWORD *)pulLength = 0;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
        0,
        -2147024809);
    return (unsigned int)-2147024809;
  }
  v19 = 260 - v17 + 1;
  *(_QWORD *)pulLength = v19;
  if ( a4 )
    *a4 = v19;
  if ( !v6 || !(_DWORD)v4 )
  {
    v11 = 0;
    if ( !a4 )
      return (unsigned int)-2147467261;
    return v11;
  }
  v20 = v4;
  if ( v4 < v19 )
    return (unsigned int)-1072860816;
  if ( v4 > 0x7FFFFFFF )
  {
    *v6 = 0;
LABEL_45:
    v22 = v11;
    if ( !g_wppLevels )
      return v11;
    v23 = 34;
    goto LABEL_47;
  }
  v21 = 2147483646;
  v11 = 0;
  while ( v21 && *v7 )
  {
    *v6++ = *v7++;
    --v21;
    if ( !--v20 )
    {
      --v6;
      v11 = -2147024774;
      break;
    }
  }
  *v6 = 0;
  if ( (v11 & 0x80000000) != 0 )
    goto LABEL_45;
  return v11;
}

```

## disassembly

```asm
0x180005b90  push    rbp
0x180005b92  push    rbx
0x180005b93  push    rdi
0x180005b94  push    r12
0x180005b96  push    r13
0x180005b98  push    r14
0x180005b9a  lea     rbp, [rsp-1A8h]
0x180005ba2  sub     rsp, 2A8h
0x180005ba9  mov     rax, cs:__security_cookie
0x180005bb0  xor     rax, rsp
0x180005bb3  mov     [rbp+1D0h+var_40], rax
0x180005bba  mov     r13d, r8d
0x180005bbd  mov     r12, r9
0x180005bc0  mov     rbx, rdx
0x180005bc3  mov     rdi, rcx
0x180005bc6  movups  xmm0, xmmword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data1
0x180005bcd  movups  xmm1, xmmword ptr cs:_GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca.Data1
0x180005bd4  movups  [rsp+2D0h+var_288], xmm0
0x180005bd9  movups  xmm0, xmmword ptr cs:_GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8.Data1
0x180005be0  movups  [rsp+2D0h+var_278], xmm1
0x180005be5  movups  [rsp+2D0h+var_268], xmm0
0x180005bea  test    rcx, rcx
0x180005bed  jz      loc_180005EDA
0x180005bf3  test    rdx, rdx
0x180005bf6  jz      loc_180005EAA
0x180005bfc  test    r9, r9
0x180005bff  jnz     loc_180005EAF
0x180005c05  mov     [rsp+2D0h+arg_10], rsi
0x180005c0d  xor     esi, esi
0x180005c0f  mov     [rsp+2D0h+var_30], r15
0x180005c17  mov     r15d, 104h
0x180005c1d  movsxd  r14, esi
0x180005c20  cmp     r14, 3
0x180005c24  jnb     loc_180005DBE
0x180005c2a  xor     edx, edx; Val
0x180005c2c  lea     rcx, [rbp+1D0h+pszAliasDeviceInterface]; void *
0x180005c30  mov     r8d, 208h; Size
0x180005c36  call    memset_0
0x180005c3b  lea     rdx, [rsp+2D0h+var_288]
0x180005c40  shl     r14, 4
0x180005c44  add     rdx, r14; AliasInterfaceGuid
0x180005c47  mov     qword ptr [rsp+2D0h+pulLength], r15
0x180005c4c  lea     r9, [rsp+2D0h+pulLength]; pulLength
0x180005c51  mov     [rsp+2D0h+ulFlags], 0; ulFlags
0x180005c59  lea     r8, [rbp+1D0h+pszAliasDeviceInterface]; pszAliasDeviceInterface
0x180005c5d  mov     rcx, rdi; pszDeviceInterface
0x180005c60  call    cs:__imp_CM_Get_Device_Interface_AliasW
0x180005c66  test    eax, eax
0x180005c68  jnz     short loc_180005CAE
0x180005c6a  mov     [rsp+2D0h+var_2A8], eax; ulFlags
0x180005c6e  lea     r9, [rsp+2D0h+PropertyBuffer]; PropertyBuffer
0x180005c73  mov     [rsp+2D0h+PropertyType], eax
0x180005c77  lea     r8, [rsp+2D0h+PropertyType]; PropertyType
0x180005c7c  mov     [rsp+2D0h+PropertyBuffer], al
0x180005c80  lea     rdx, DEVPKEY_DeviceInterface_Enabled; PropertyKey
0x180005c87  lea     rax, [rsp+2D0h+PropertyBufferSize]
0x180005c8c  mov     [rsp+2D0h+PropertyBufferSize], 1
0x180005c94  lea     rcx, [rbp+1D0h+pszAliasDeviceInterface]; pszDeviceInterface
0x180005c98  mov     qword ptr [rsp+2D0h+ulFlags], rax; PropertyBufferSize
0x180005c9d  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180005ca3  test    eax, eax
0x180005ca5  jnz     short loc_180005CAE
0x180005ca7  cmp     [rsp+2D0h+PropertyBuffer], 0FFh
0x180005cac  jz      short loc_180005CB5
0x180005cae  inc     esi
0x180005cb0  jmp     loc_180005C1D
0x180005cb5  mov     rcx, r15
0x180005cb8  lea     rax, [rbp+1D0h+pszAliasDeviceInterface]
0x180005cbc  nop     dword ptr [rax+00h]
0x180005cc0  cmp     word ptr [rax], 0
0x180005cc4  jz      short loc_180005CD0
0x180005cc6  add     rax, 2
0x180005cca  sub     rcx, 1
0x180005cce  jnz     short loc_180005CC0
0x180005cd0  xor     eax, eax
0x180005cd2  mov     r14d, 80070057h
0x180005cd8  test    rcx, rcx
0x180005cdb  mov     edi, r14d
0x180005cde  cmovnz  edi, eax
0x180005ce1  jz      loc_180005EC4
0x180005ce7  sub     r15, rcx
0x180005cea  inc     r15
0x180005ced  mov     qword ptr [rsp+2D0h+pulLength], r15
0x180005cf2  test    r12, r12
0x180005cf5  jnz     loc_180005DA5
0x180005cfb  test    rbx, rbx
0x180005cfe  jz      loc_180005DAE
0x180005d04  test    r13d, r13d
0x180005d07  jz      loc_180005DAE
0x180005d0d  mov     r8, r13
0x180005d10  cmp     r13, r15
0x180005d13  jb      loc_180005F6E
0x180005d19  cmp     r13, 7FFFFFFFh
0x180005d20  ja      loc_180005F29
0x180005d26  mov     eax, 7FFFFFFEh
0x180005d2b  lea     rdx, [rbp+1D0h+pszAliasDeviceInterface]
0x180005d2f  xor     r14d, r14d
0x180005d32  test    rax, rax
0x180005d35  jz      short loc_180005D64
0x180005d37  movzx   ecx, word ptr [rdx]
0x180005d3a  test    cx, cx
0x180005d3d  jz      short loc_180005D5F
0x180005d3f  mov     [rbx], cx
0x180005d42  add     rdx, 2
0x180005d46  add     rbx, 2
0x180005d4a  dec     rax
0x180005d4d  sub     r8, 1
0x180005d51  jnz     short loc_180005D32
0x180005d53  sub     rbx, 2
0x180005d57  mov     r14d, 8007007Ah
0x180005d5d  jmp     short loc_180005D64
0x180005d5f  test    r8, r8
0x180005d62  jz      short loc_180005D53
0x180005d64  xor     eax, eax
0x180005d66  mov     [rbx], ax
0x180005d69  test    r14d, r14d
0x180005d6c  js      loc_180005F2C
0x180005d72  mov     rsi, [rsp+2D0h+arg_10]
0x180005d7a  mov     r15, [rsp+2D0h+var_30]
0x180005d82  mov     eax, r14d
0x180005d85  mov     rcx, [rbp+1D0h+var_40]
0x180005d8c  xor     rcx, rsp; StackCookie
0x180005d8f  call    __security_check_cookie
0x180005d94  add     rsp, 2A8h
0x180005d9b  pop     r14
0x180005d9d  pop     r13
0x180005d9f  pop     r12
0x180005da1  pop     rdi
0x180005da2  pop     rbx
0x180005da3  pop     rbp
0x180005da4  retn
0x180005da5  mov     [r12], r15d
0x180005da9  jmp     loc_180005CFB
0x180005dae  mov     r14d, edi
0x180005db1  test    r12, r12
0x180005db4  jnz     short loc_180005D72
0x180005db6  mov     r14d, 80004003h
0x180005dbc  jmp     short loc_180005D72
0x180005dbe  mov     rcx, r15
0x180005dc1  mov     rax, rdi
0x180005dc4  cmp     word ptr [rax], 0
0x180005dc8  jz      short loc_180005DD4
0x180005dca  add     rax, 2
0x180005dce  sub     rcx, 1
0x180005dd2  jnz     short loc_180005DC4
0x180005dd4  xor     eax, eax
0x180005dd6  mov     r14d, 80070057h
0x180005ddc  test    rcx, rcx
0x180005ddf  mov     esi, r14d
0x180005de2  cmovnz  esi, eax
0x180005de5  jz      loc_180005EE5
0x180005deb  sub     r15, rcx
0x180005dee  inc     r15
0x180005df1  mov     qword ptr [rsp+2D0h+pulLength], r15
0x180005df6  test    r12, r12
0x180005df9  jnz     loc_180005EBB
0x180005dff  test    rbx, rbx
0x180005e02  jz      loc_180005F81
0x180005e08  test    r13d, r13d
0x180005e0b  jz      loc_180005F81
0x180005e11  mov     rdx, r13
0x180005e14  cmp     r13, r15
0x180005e17  jb      loc_180005F6E
0x180005e1d  cmp     rdx, 7FFFFFFFh
0x180005e24  ja      loc_180005F79
0x180005e2a  mov     eax, 7FFFFFFEh
0x180005e2f  xor     r14d, r14d
0x180005e32  test    rax, rax
0x180005e35  jz      short loc_180005E64
0x180005e37  movzx   ecx, word ptr [rdi]
0x180005e3a  test    cx, cx
0x180005e3d  jz      short loc_180005E5F
0x180005e3f  mov     [rbx], cx
0x180005e42  add     rdi, 2
0x180005e46  add     rbx, 2
0x180005e4a  dec     rax
0x180005e4d  sub     rdx, 1
0x180005e51  jnz     short loc_180005E32
0x180005e53  sub     rbx, 2
0x180005e57  mov     r14d, 8007007Ah
0x180005e5d  jmp     short loc_180005E64
0x180005e5f  test    rdx, rdx
0x180005e62  jz      short loc_180005E53
0x180005e64  xor     eax, eax
0x180005e66  mov     [rbx], ax
0x180005e69  test    r14d, r14d
0x180005e6c  jns     loc_180005D72
0x180005e72  mov     ecx, r14d
0x180005e75  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180005e7c  jb      loc_180005D72
0x180005e82  mov     edx, 22h ; '"'
0x180005e87  mov     [rsp+2D0h+ulFlags], ecx
0x180005e8b  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180005e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e99  xor     r9d, r9d
0x180005e9c  mov     rcx, [rcx+10h]
0x180005ea0  call    WPP_SF_qD
0x180005ea5  jmp     loc_180005D72
0x180005eaa  test    r12, r12
0x180005ead  jz      short loc_180005F1E
0x180005eaf  mov     dword ptr [r9], 0
0x180005eb6  jmp     loc_180005C05
0x180005ebb  mov     [r12], r15d
0x180005ebf  jmp     loc_180005DFF
0x180005ec4  mov     qword ptr [rsp+2D0h+pulLength], rax
0x180005ec9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180005ed0  jnb     short loc_180005F46
0x180005ed2  mov     r14d, edi
0x180005ed5  jmp     loc_180005D72
0x180005eda  mov     r14d, 80070057h
0x180005ee0  jmp     loc_180005D82
0x180005ee5  mov     qword ptr [rsp+2D0h+pulLength], rax
0x180005eea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180005ef1  jb      short loc_180005F16
0x180005ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005efa  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180005f01  mov     edx, 21h ; '!'
0x180005f06  mov     [rsp+2D0h+ulFlags], esi
0x180005f0a  xor     r9d, r9d
0x180005f0d  mov     rcx, [rcx+10h]
0x180005f11  call    WPP_SF_qD
0x180005f16  mov     r14d, esi
0x180005f19  jmp     loc_180005D72
0x180005f1e  mov     r14d, 80004003h
0x180005f24  jmp     loc_180005D82
0x180005f29  mov     [rbx], ax
0x180005f2c  mov     ecx, r14d
0x180005f2f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180005f36  jb      loc_180005D72
0x180005f3c  mov     edx, 20h ; ' '
0x180005f41  jmp     loc_180005E87
0x180005f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f4d  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180005f54  mov     edx, 1Fh
0x180005f59  mov     [rsp+2D0h+ulFlags], edi
0x180005f5d  xor     r9d, r9d
0x180005f60  mov     rcx, [rcx+10h]
0x180005f64  call    WPP_SF_qD
0x180005f69  jmp     loc_180005ED2
0x180005f6e  mov     r14d, 0C00D7170h
0x180005f74  jmp     loc_180005D72
0x180005f79  mov     [rbx], ax
0x180005f7c  jmp     loc_180005E72
0x180005f81  mov     r14d, esi
0x180005f84  test    r12, r12
0x180005f87  jnz     loc_180005D72
0x180005f8d  mov     r14d, 80004003h
0x180005f93  jmp     loc_180005D72
```
