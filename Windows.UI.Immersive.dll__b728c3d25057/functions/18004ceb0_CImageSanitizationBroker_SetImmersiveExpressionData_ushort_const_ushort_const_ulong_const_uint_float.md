# CImageSanitizationBroker::SetImmersiveExpressionData(ushort const *,ushort const *,ulong const *,uint,float)

- ea: `0x18004ceb0`
- end: `0x18004d1ab`
- name: `?SetImmersiveExpressionData@CImageSanitizationBroker@@UEAAJPEBG0PEBKIM@Z`
- size: `763`
- prototype: `int(CImageSanitizationBroker *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned int *, unsigned int, float)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000d2b8`
- `0x18002d8a4`
- `0x18003e23c`
- `0x18003e4d0`
- `0x18003e59c`
- `0x18003e688`
- `0x18004ceb0`
- `0x180050ba0`
- `0x180078db8`
- `0x180078ecc`
- `0x180078fa0`
- `0x180079338`
- `0x18007ac08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d10d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d120`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d10d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d120`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004cfdc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004d041`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004cfdc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004d041`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004d0a3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004d0a3`

## pseudocode

```c
__int64 __fastcall CImageSanitizationBroker::SetImmersiveExpressionData(
        CImageSanitizationBroker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned int *a4,
        unsigned int a5,
        float a6)
{
  CImageSanitizationBroker *v9; // rcx
  CImageSanitizationBroker *v10; // rcx
  signed int v11; // ebx
  int v12; // edi
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  int v15; // eax
  LSTATUS v16; // eax
  unsigned int v18[2]; // [rsp+58h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-A0h] BYREF
  const unsigned __int16 *v21; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v22[42]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 v23[20]; // [rsp+1C8h] [rbp+C0h] BYREF

  v21 = a2;
  wil::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v22,
    "SetImmersiveExpressionData");
  v22[0] = &ImageSanitizationTelemetry::SetImmersiveExpressionData::`vftable';
  ImageSanitizationTelemetry::SetImmersiveExpressionData::StartActivity((ImageSanitizationTelemetry::SetImmersiveExpressionData *)v22);
  v18[0] = CImageSanitizationBroker::_ValidateExpressionId(v9, a2, 0);
  v11 = v18[0];
  if ( (v18[0] & 0x80000000) != 0 )
  {
    ImageSanitizationTelemetry::SetImmersiveExpressionData::InvalidExpressionId<long &>(v22, v18);
    v12 = v11;
    goto LABEL_29;
  }
  v18[0] = 0;
  v18[0] = CImageSanitizationBroker::_ValidateExpressionDataXML(v10, a3, v18);
  v11 = v18[0];
  if ( (v18[0] & 0x80000000) != 0 )
  {
    ImageSanitizationTelemetry::SetImmersiveExpressionData::ExpressionDataXMLValidationFailure<long &>(
      (__int64)v22,
      (int *)v18);
    v12 = v11;
LABEL_27:
    ImageSanitizationTelemetry::SetImmersiveExpressionData::SetCustomColorsetInRegistryFailure<unsigned short const * &,long &>(
      v22,
      &v21,
      v18);
    goto LABEL_29;
  }
  v11 = -2147024809;
  v18[0] = -2147024809;
  v12 = -2147024809;
  if ( a5 == 210 && a6 >= 0.0 && a6 <= 1.0 )
  {
    hKey = 0;
    v13 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Accent",
            0,
            0,
            0,
            0x2001Fu,
            0,
            &hKey,
            0);
    v11 = v13;
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
    v18[0] = v11;
    if ( v11 >= 0 )
    {
      phkResult = 0;
      v14 = RegCreateKeyExW(hKey, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
      v11 = v14;
      if ( v14 > 0 )
        v11 = (unsigned __int16)v14 | 0x80070000;
      v18[0] = v11;
      if ( v11 < 0 )
      {
        v12 = v11;
        goto LABEL_22;
      }
      v15 = SHRegSetString(phkResult, 0, L"ExpressionData", a3);
      v18[0] = v15;
      v11 = v15;
      if ( v15 >= 0 )
      {
        v16 = RegSetKeyValueW(phkResult, 0, L"CustomColorSet_Version4", 3u, a4, 0x348u);
        v11 = v16;
        if ( v16 > 0 )
          v11 = (unsigned __int16)v16 | 0x80070000;
        v18[0] = v11;
        if ( v11 < 0 )
        {
          v12 = v11;
          goto LABEL_19;
        }
        v15 = StringCchPrintfW(v23, 0x14u, L"%.4f", a6);
        v18[0] = v15;
        v11 = v15;
        if ( v15 >= 0 )
        {
          v15 = SHRegSetString(phkResult, 0, L"TopRatio", v23);
          v11 = v15;
          v18[0] = v15;
        }
      }
      v12 = v15;
LABEL_19:
      RegCloseKey(phkResult);
LABEL_22:
      RegCloseKey(hKey);
      goto LABEL_24;
    }
    v12 = v11;
  }
LABEL_24:
  if ( v12 < 0 )
    goto LABEL_27;
LABEL_29:
  wil::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v22, (unsigned int)v11);
  ImageSanitizationTelemetry::SetImmersiveExpressionData::~SetImmersiveExpressionData((ImageSanitizationTelemetry::SetImmersiveExpressionData *)v22);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004ceb0  mov     rax, rsp
0x18004ceb3  mov     [rax+8], rbx
0x18004ceb7  push    rbp
0x18004ceb8  push    rsi
0x18004ceb9  push    rdi
0x18004ceba  push    r14
0x18004cebc  push    r15
0x18004cebe  lea     rbp, [rax-128h]
0x18004cec5  sub     rsp, 200h
0x18004cecc  movaps  xmmword ptr [rax-38h], xmm6
0x18004ced0  mov     rax, cs:__security_cookie
0x18004ced7  xor     rax, rsp
0x18004ceda  mov     [rbp+120h+var_38], rax
0x18004cee1  mov     r14, rdx
0x18004cee4  mov     [rsp+220h+var_1B8], rdx
0x18004cee9  lea     rdx, aSetimmersiveex; "SetImmersiveExpressionData"
0x18004cef0  mov     r15, r9
0x18004cef3  lea     rcx, [rsp+220h+var_1B0]
0x18004cef8  mov     rsi, r8
0x18004cefb  call    ??0?$ActivityBase@VImageSanitizationLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004cf00  lea     rax, ??_7SetImmersiveExpressionData@ImageSanitizationTelemetry@@6B@; const ImageSanitizationTelemetry::SetImmersiveExpressionData::`vftable'
0x18004cf07  lea     rcx, [rsp+220h+var_1B0]; this
0x18004cf0c  mov     [rsp+220h+var_1B0], rax
0x18004cf11  call    ?StartActivity@SetImmersiveExpressionData@ImageSanitizationTelemetry@@QEAAXXZ; ImageSanitizationTelemetry::SetImmersiveExpressionData::StartActivity(void)
0x18004cf16  xor     r8d, r8d; unsigned int *
0x18004cf19  mov     rdx, r14; unsigned __int16 *
0x18004cf1c  call    ?_ValidateExpressionId@CImageSanitizationBroker@@AEAAJPEBGPEAI@Z; CImageSanitizationBroker::_ValidateExpressionId(ushort const *,uint *)
0x18004cf21  mov     [rsp+220h+var_1D0], eax
0x18004cf25  mov     ebx, eax
0x18004cf27  test    eax, eax
0x18004cf29  js      loc_18004D157
0x18004cf2f  lea     r8, [rsp+220h+var_1D0]; unsigned int *
0x18004cf34  mov     [rsp+220h+var_1D0], 0
0x18004cf3c  mov     rdx, rsi; unsigned __int16 *
0x18004cf3f  call    ?_ValidateExpressionDataXML@CImageSanitizationBroker@@AEAAJPEBGPEAI@Z; CImageSanitizationBroker::_ValidateExpressionDataXML(ushort const *,uint *)
0x18004cf44  mov     [rsp+220h+var_1D0], eax
0x18004cf48  mov     ebx, eax
0x18004cf4a  test    eax, eax
0x18004cf4c  js      loc_18004D130
0x18004cf52  cmp     [rbp+120h+arg_20], 0D2h
0x18004cf5c  mov     ebx, 80070057h
0x18004cf61  mov     [rsp+220h+var_1D0], ebx
0x18004cf65  mov     edi, ebx
0x18004cf67  jnz     loc_18004D12A
0x18004cf6d  movss   xmm6, [rbp+120h+arg_28]
0x18004cf75  comiss  xmm6, cs:__real@00000000
0x18004cf7c  jb      loc_18004D12A
0x18004cf82  movss   xmm0, cs:__real@3f800000
0x18004cf8a  comiss  xmm0, xmm6
0x18004cf8d  jb      loc_18004D12A
0x18004cf93  mov     [rsp+220h+lpdwDisposition], 0; lpdwDisposition
0x18004cf9c  lea     rax, [rsp+220h+hKey]
0x18004cfa1  mov     [rsp+220h+phkResult], rax; phkResult
0x18004cfa6  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004cfad  mov     [rsp+220h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004cfb6  xor     r9d, r9d; lpClass
0x18004cfb9  mov     [rsp+220h+samDesired], 2001Fh; samDesired
0x18004cfc1  xor     r8d, r8d; Reserved
0x18004cfc4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004cfcb  mov     [rsp+220h+dwOptions], 0; dwOptions
0x18004cfd3  mov     [rsp+220h+hKey], 0
0x18004cfdc  call    cs:__imp_RegCreateKeyExW
0x18004cfe2  mov     ebx, eax
0x18004cfe4  mov     edi, 80070000h
0x18004cfe9  test    eax, eax
0x18004cfeb  jle     short loc_18004CFF2
0x18004cfed  movzx   ebx, ax
0x18004cff0  or      ebx, edi
0x18004cff2  mov     [rsp+220h+var_1D0], ebx
0x18004cff6  test    ebx, ebx
0x18004cff8  js      loc_18004D128
0x18004cffe  mov     rcx, [rsp+220h+hKey]; hKey
0x18004d003  lea     rax, [rsp+220h+var_1C8]
0x18004d008  mov     [rsp+220h+lpdwDisposition], 0; lpdwDisposition
0x18004d011  xor     r9d, r9d; lpClass
0x18004d014  mov     [rsp+220h+phkResult], rax; phkResult
0x18004d019  xor     r8d, r8d; Reserved
0x18004d01c  mov     [rsp+220h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004d025  mov     rdx, r14; lpSubKey
0x18004d028  mov     [rsp+220h+samDesired], 2001Fh; samDesired
0x18004d030  mov     [rsp+220h+dwOptions], 0; dwOptions
0x18004d038  mov     [rsp+220h+var_1C8], 0
0x18004d041  call    cs:__imp_RegCreateKeyExW
0x18004d047  mov     ebx, eax
0x18004d049  test    eax, eax
0x18004d04b  jle     short loc_18004D052
0x18004d04d  movzx   ebx, ax
0x18004d050  or      ebx, edi
0x18004d052  mov     [rsp+220h+var_1D0], ebx
0x18004d056  test    ebx, ebx
0x18004d058  js      loc_18004D119
0x18004d05e  mov     rcx, [rsp+220h+var_1C8]; HKEY
0x18004d063  lea     r8, aExpressiondata; "ExpressionData"
0x18004d06a  mov     r9, rsi; unsigned __int16 *
0x18004d06d  xor     edx, edx; unsigned __int16 *
0x18004d06f  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18004d074  mov     [rsp+220h+var_1D0], eax
0x18004d078  mov     ebx, eax
0x18004d07a  test    eax, eax
0x18004d07c  js      loc_18004D106
0x18004d082  mov     rcx, [rsp+220h+var_1C8]; hKey
0x18004d087  lea     r8, aCustomcolorset; "CustomColorSet_Version4"
0x18004d08e  mov     [rsp+220h+samDesired], 348h; cbData
0x18004d096  mov     r9d, 3; dwType
0x18004d09c  xor     edx, edx; lpSubKey
0x18004d09e  mov     qword ptr [rsp+220h+dwOptions], r15; lpData
0x18004d0a3  call    cs:__imp_RegSetKeyValueW
0x18004d0a9  mov     ebx, eax
0x18004d0ab  test    eax, eax
0x18004d0ad  jle     short loc_18004D0B4
0x18004d0af  movzx   ebx, ax
0x18004d0b2  or      ebx, edi
0x18004d0b4  mov     [rsp+220h+var_1D0], ebx
0x18004d0b8  test    ebx, ebx
0x18004d0ba  js      short loc_18004D115
0x18004d0bc  cvtps2pd xmm3, xmm6
0x18004d0bf  lea     r8, a4f; "%.4f"
0x18004d0c6  mov     edx, 14h; unsigned __int64
0x18004d0cb  lea     rcx, [rbp+120h+var_60]; unsigned __int16 *
0x18004d0d2  movq    r9, xmm3
0x18004d0d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d0dc  mov     [rsp+220h+var_1D0], eax
0x18004d0e0  mov     ebx, eax
0x18004d0e2  test    eax, eax
0x18004d0e4  js      short loc_18004D106
0x18004d0e6  mov     rcx, [rsp+220h+var_1C8]; HKEY
0x18004d0eb  lea     r9, [rbp+120h+var_60]; unsigned __int16 *
0x18004d0f2  lea     r8, aTopratio; "TopRatio"
0x18004d0f9  xor     edx, edx; unsigned __int16 *
0x18004d0fb  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18004d100  mov     ebx, eax
0x18004d102  mov     [rsp+220h+var_1D0], eax
0x18004d106  mov     edi, eax
0x18004d108  mov     rcx, [rsp+220h+var_1C8]; hKey
0x18004d10d  call    cs:__imp_RegCloseKey
0x18004d113  jmp     short loc_18004D11B
0x18004d115  mov     edi, ebx
0x18004d117  jmp     short loc_18004D108
0x18004d119  mov     edi, ebx
0x18004d11b  mov     rcx, [rsp+220h+hKey]; hKey
0x18004d120  call    cs:__imp_RegCloseKey
0x18004d126  jmp     short loc_18004D12A
0x18004d128  mov     edi, ebx
0x18004d12a  test    edi, edi
0x18004d12c  jns     short loc_18004D168
0x18004d12e  jmp     short loc_18004D141
0x18004d130  lea     rdx, [rsp+220h+var_1D0]
0x18004d135  lea     rcx, [rsp+220h+var_1B0]
0x18004d13a  call    ??$ExpressionDataXMLValidationFailure@AEAJ@SetImmersiveExpressionData@ImageSanitizationTelemetry@@QEAAXAEAJ@Z; ImageSanitizationTelemetry::SetImmersiveExpressionData::ExpressionDataXMLValidationFailure<long &>(long &)
0x18004d13f  mov     edi, ebx
0x18004d141  lea     r8, [rsp+220h+var_1D0]
0x18004d146  lea     rdx, [rsp+220h+var_1B8]
0x18004d14b  lea     rcx, [rsp+220h+var_1B0]
0x18004d150  call    ??$SetCustomColorsetInRegistryFailure@AEAPEBGAEAJ@SetImmersiveExpressionData@ImageSanitizationTelemetry@@QEAAXAEAPEBGAEAJ@Z; ImageSanitizationTelemetry::SetImmersiveExpressionData::SetCustomColorsetInRegistryFailure<ushort const * &,long &>(ushort const * &,long &)
0x18004d155  jmp     short loc_18004D168
0x18004d157  lea     rdx, [rsp+220h+var_1D0]
0x18004d15c  lea     rcx, [rsp+220h+var_1B0]
0x18004d161  call    ??$InvalidExpressionId@AEAJ@SetImmersiveExpressionData@ImageSanitizationTelemetry@@QEAAXAEAJ@Z; ImageSanitizationTelemetry::SetImmersiveExpressionData::InvalidExpressionId<long &>(long &)
0x18004d166  mov     edi, ebx
0x18004d168  mov     edx, ebx
0x18004d16a  lea     rcx, [rsp+220h+var_1B0]
0x18004d16f  call    ?Stop@?$ActivityBase@VImageSanitizationLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004d174  lea     rcx, [rsp+220h+var_1B0]; this
0x18004d179  call    ??1SetImmersiveExpressionData@ImageSanitizationTelemetry@@QEAA@XZ; ImageSanitizationTelemetry::SetImmersiveExpressionData::~SetImmersiveExpressionData(void)
0x18004d17e  mov     eax, edi
0x18004d180  mov     rcx, [rbp+120h+var_38]
0x18004d187  xor     rcx, rsp; StackCookie
0x18004d18a  call    __security_check_cookie
0x18004d18f  lea     r11, [rsp+220h+var_20]
0x18004d197  mov     rbx, [r11+30h]
0x18004d19b  movaps  xmm6, xmmword ptr [r11-10h]
0x18004d1a0  mov     rsp, r11
0x18004d1a3  pop     r15
0x18004d1a5  pop     r14
0x18004d1a7  pop     rdi
0x18004d1a8  pop     rsi
0x18004d1a9  pop     rbp
0x18004d1aa  retn
```
