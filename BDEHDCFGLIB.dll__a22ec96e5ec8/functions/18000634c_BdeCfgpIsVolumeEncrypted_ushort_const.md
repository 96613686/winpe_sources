# BdeCfgpIsVolumeEncrypted(ushort const *)

- ea: `0x18000634c`
- end: `0x180006731`
- name: `?BdeCfgpIsVolumeEncrypted@@YAJPEBG@Z`
- size: `997`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180002460`
- `0x180002814`

## callees

- `0x18000634c`
- `0x180006c30`
- `0x180008b5c`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180006446`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180006446`
- `KERNEL32!GetLastError` at `0x180006450`
- `KERNEL32!GetLastError` at `0x180006450`
- `ole32!CoSetProxyBlanket` at `0x180006584`
- `ole32!CoSetProxyBlanket` at `0x180006584`
- `ole32!CoCreateInstance` at `0x1800064ef`
- `ole32!CoCreateInstance` at `0x1800064ef`
- `OLEAUT32!__imp_SysAllocString` at `0x1800064b9`
- `OLEAUT32!__imp_SysAllocString` at `0x180006506`
- `OLEAUT32!__imp_SysAllocString` at `0x18000659b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800064b9`
- `OLEAUT32!__imp_SysAllocString` at `0x180006506`
- `OLEAUT32!__imp_SysAllocString` at `0x18000659b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066e9`
- `OLEAUT32!__imp_VariantInit` at `0x180006402`
- `OLEAUT32!__imp_VariantInit` at `0x18000640c`
- `OLEAUT32!__imp_VariantInit` at `0x180006402`
- `OLEAUT32!__imp_VariantInit` at `0x18000640c`
- `OLEAUT32!__imp_VariantClear` at `0x1800066f4`
- `OLEAUT32!__imp_VariantClear` at `0x1800066fe`
- `OLEAUT32!__imp_VariantClear` at `0x1800066f4`
- `OLEAUT32!__imp_VariantClear` at `0x1800066fe`

## string_xrefs

- `0x1800064ff`: `\\.\root\CIMv2\Security\MicrosoftVolumeEncryption`

## pseudocode

```c
__int64 __fastcall BdeCfgpIsVolumeEncrypted(const unsigned __int16 *a1)
{
  OLECHAR *v2; // rdi
  OLECHAR *v3; // rsi
  OLECHAR *v4; // r14
  int lVal; // ebx
  signed int LastError; // eax
  BSTR v7; // rax
  BSTR v8; // rax
  IUnknown *pProxy; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG v14; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szVolumeMountPoint[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR szVolumeName[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v17[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  OLECHAR psz[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  ppv = 0;
  pProxy = 0;
  v11 = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v14, 0, sizeof(v14));
  memset_0(szVolumeMountPoint, 0, 0x208u);
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(v17, 0, 0x208u);
  memset_0(psz, 0, 0x208u);
  VariantInit(&pvarg);
  VariantInit(&v14);
  lVal = StringCchPrintfW(szVolumeMountPoint, 0x104u, L"%s\\", a1);
  if ( lVal >= 0 )
  {
    if ( GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, szVolumeName, 0x104u) )
    {
      lVal = BdeCfgpEscapePath(szVolumeName, v17);
      if ( lVal >= 0 )
      {
        lVal = StringCchPrintfW(psz, 0x104u, L"Win32_EncryptableVolume.DeviceID=\"%s\"", v17);
        if ( lVal >= 0 )
        {
          v3 = SysAllocString(psz);
          if ( !v3 )
            goto LABEL_8;
          lVal = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
          if ( lVal < 0 )
            goto LABEL_22;
          v7 = SysAllocString(L"\\\\.\\root\\CIMv2\\Security\\MicrosoftVolumeEncryption");
          v2 = v7;
          if ( !v7 )
            goto LABEL_8;
          lVal = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD, _QWORD, int, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   v7,
                   0,
                   0,
                   0,
                   128,
                   0,
                   0,
                   &pProxy);
          if ( lVal < 0 )
            goto LABEL_22;
          lVal = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, 0, 6u, 3u, 0, 0);
          if ( lVal < 0 )
            goto LABEL_22;
          v8 = SysAllocString(L"GetEncryptionMethod");
          v4 = v8;
          if ( !v8 )
          {
LABEL_8:
            lVal = -2147024882;
            goto LABEL_22;
          }
          lVal = ((__int64 (__fastcall *)(IUnknown *, OLECHAR *, BSTR, _QWORD, _QWORD, _QWORD, __int64 *, _QWORD))pProxy->lpVtbl[8].QueryInterface)(
                   pProxy,
                   v3,
                   v8,
                   0,
                   0,
                   0,
                   &v11,
                   0);
          if ( lVal >= 0 )
          {
            lVal = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v11 + 32LL))(
                     v11,
                     L"ReturnValue",
                     0,
                     &v14,
                     0,
                     0);
            if ( lVal >= 0 )
            {
              if ( v14.vt == 3 )
              {
                lVal = v14.lVal;
                if ( v14.lVal < 0 )
                  goto LABEL_22;
                lVal = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v11 + 32LL))(
                         v11,
                         L"EncryptionMethod",
                         0,
                         &pvarg,
                         0,
                         0);
                if ( lVal < 0 )
                  goto LABEL_22;
                if ( pvarg.vt == 3 )
                {
                  lVal = pvarg.lVal == 0;
                  goto LABEL_22;
                }
              }
              lVal = -1063256037;
            }
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      lVal = LastError;
      if ( LastError > 0 )
        lVal = (unsigned __int16)LastError | 0x80070000;
    }
  }
LABEL_22:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( pProxy )
  {
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    pProxy = 0;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v2 )
    SysFreeString(v2);
  if ( v3 )
    SysFreeString(v3);
  if ( v4 )
    SysFreeString(v4);
  VariantClear(&pvarg);
  VariantClear(&v14);
  return (unsigned int)lVal;
}

```

## disassembly

```asm
0x18000634c  mov     [rsp-8+arg_8], rbx
0x180006351  mov     [rsp-8+arg_10], rsi
0x180006356  push    rbp
0x180006357  push    rdi
0x180006358  push    r12
0x18000635a  push    r14
0x18000635c  push    r15
0x18000635e  lea     rbp, [rsp-7F0h]
0x180006366  sub     rsp, 8F0h
0x18000636d  mov     rax, cs:__security_cookie
0x180006374  xor     rax, rsp
0x180006377  mov     [rbp+810h+var_30], rax
0x18000637e  xor     r12d, r12d
0x180006381  xor     eax, eax
0x180006383  mov     rbx, rcx
0x180006386  mov     [rsp+910h+var_8B0], r12
0x18000638b  xorps   xmm0, xmm0
0x18000638e  mov     [rsp+910h+pProxy], r12
0x180006393  xorps   xmm1, xmm1
0x180006396  mov     [rsp+910h+var_8B8], r12
0x18000639b  mov     r15d, 208h
0x1800063a1  mov     qword ptr [rsp+910h+pvarg+10h], rax
0x1800063a6  mov     r8d, r15d; Size
0x1800063a9  mov     qword ptr [rbp+810h+var_890+10h], rax
0x1800063ad  xor     edx, edx; Val
0x1800063af  lea     rcx, [rbp+810h+szVolumeMountPoint]; void *
0x1800063b3  mov     edi, r12d
0x1800063b6  mov     esi, r12d
0x1800063b9  mov     r14d, r12d
0x1800063bc  movups  xmmword ptr [rsp+910h+pvarg], xmm0
0x1800063c1  movups  xmmword ptr [rbp+810h+var_890], xmm1
0x1800063c5  call    memset_0
0x1800063ca  mov     r8d, r15d; Size
0x1800063cd  lea     rcx, [rbp+810h+szVolumeName]; void *
0x1800063d4  xor     edx, edx; Val
0x1800063d6  call    memset_0
0x1800063db  mov     r8d, r15d; Size
0x1800063de  lea     rcx, [rbp+810h+var_450]; void *
0x1800063e5  xor     edx, edx; Val
0x1800063e7  call    memset_0
0x1800063ec  mov     r8d, r15d; Size
0x1800063ef  lea     rcx, [rbp+810h+psz]; void *
0x1800063f6  xor     edx, edx; Val
0x1800063f8  call    memset_0
0x1800063fd  lea     rcx, [rsp+910h+pvarg]; pvarg
0x180006402  call    cs:__imp_VariantInit
0x180006408  lea     rcx, [rbp+810h+var_890]; pvarg
0x18000640c  call    cs:__imp_VariantInit
0x180006412  mov     r15d, 104h
0x180006418  lea     r8, aS; "%s\\"
0x18000641f  mov     edx, r15d; unsigned __int64
0x180006422  lea     rcx, [rbp+810h+szVolumeMountPoint]; unsigned __int16 *
0x180006426  mov     r9, rbx
0x180006429  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000642e  mov     ebx, eax
0x180006430  test    eax, eax
0x180006432  js      loc_180006674
0x180006438  mov     r8d, r15d; cchBufferLength
0x18000643b  lea     rdx, [rbp+810h+szVolumeName]; lpszVolumeName
0x180006442  lea     rcx, [rbp+810h+szVolumeMountPoint]; lpszVolumeMountPoint
0x180006446  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000644c  test    eax, eax
0x18000644e  jnz     short loc_18000646E
0x180006450  call    cs:__imp_GetLastError
0x180006456  mov     ebx, eax
0x180006458  test    eax, eax
0x18000645a  jle     loc_180006674
0x180006460  movzx   ebx, ax
0x180006463  or      ebx, 80070000h
0x180006469  jmp     loc_180006674
0x18000646e  lea     rdx, [rbp+810h+var_450]; unsigned __int16 *
0x180006475  lea     rcx, [rbp+810h+szVolumeName]; unsigned __int16 *
0x18000647c  call    ?BdeCfgpEscapePath@@YAJPEBGPEAGK@Z; BdeCfgpEscapePath(ushort const *,ushort *,ulong)
0x180006481  mov     ebx, eax
0x180006483  test    eax, eax
0x180006485  js      loc_180006674
0x18000648b  lea     r9, [rbp+810h+var_450]
0x180006492  mov     rdx, r15; unsigned __int64
0x180006495  lea     r8, aWin32Encryptab; "Win32_EncryptableVolume.DeviceID=\"%s\""
0x18000649c  lea     rcx, [rbp+810h+psz]; unsigned __int16 *
0x1800064a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800064a8  mov     ebx, eax
0x1800064aa  test    eax, eax
0x1800064ac  js      loc_180006674
0x1800064b2  lea     rcx, [rbp+810h+psz]; psz
0x1800064b9  call    cs:__imp_SysAllocString
0x1800064bf  mov     rsi, rax
0x1800064c2  test    rax, rax
0x1800064c5  jnz     short loc_1800064D1
0x1800064c7  mov     ebx, 8007000Eh
0x1800064cc  jmp     loc_180006674
0x1800064d1  xor     edx, edx; pUnkOuter
0x1800064d3  lea     rax, [rsp+910h+var_8B0]
0x1800064d8  lea     r9, IID_IWbemLocator; riid
0x1800064df  mov     [rsp+910h+ppv], rax; ppv
0x1800064e4  lea     rcx, CLSID_WbemLocator; rclsid
0x1800064eb  lea     r8d, [rdx+1]; dwClsContext
0x1800064ef  call    cs:__imp_CoCreateInstance
0x1800064f5  mov     ebx, eax
0x1800064f7  test    eax, eax
0x1800064f9  js      loc_180006674
0x1800064ff  lea     rcx, psz; "\\\\.\\root\\CIMv2\\Security\\Microsoft"...
0x180006506  call    cs:__imp_SysAllocString
0x18000650c  mov     rdi, rax
0x18000650f  test    rax, rax
0x180006512  jz      short loc_1800064C7
0x180006514  mov     rcx, [rsp+910h+var_8B0]
0x180006519  lea     rdx, [rsp+910h+pProxy]
0x18000651e  mov     [rsp+910h+var_8D0], rdx
0x180006523  xor     r9d, r9d
0x180006526  mov     qword ptr [rsp+910h+dwCapabilities], r12
0x18000652b  xor     r8d, r8d
0x18000652e  mov     [rsp+910h+pAuthInfo], r12
0x180006533  mov     rdx, rdi
0x180006536  mov     rax, [rcx]
0x180006539  mov     [rsp+910h+dwImpLevel], 80h
0x180006541  mov     [rsp+910h+ppv], r12
0x180006546  mov     rax, [rax+18h]
0x18000654a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000654f  mov     ebx, eax
0x180006551  test    eax, eax
0x180006553  js      loc_180006674
0x180006559  mov     rcx, [rsp+910h+pProxy]; pProxy
0x18000655e  mov     r15d, 3
0x180006564  mov     [rsp+910h+dwCapabilities], r12d; dwCapabilities
0x180006569  xor     r9d, r9d; pServerPrincName
0x18000656c  mov     [rsp+910h+pAuthInfo], r12; pAuthInfo
0x180006571  xor     r8d, r8d; dwAuthzSvc
0x180006574  mov     [rsp+910h+dwImpLevel], r15d; dwImpLevel
0x180006579  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000657c  mov     dword ptr [rsp+910h+ppv], 6; dwAuthnLevel
0x180006584  call    cs:__imp_CoSetProxyBlanket
0x18000658a  mov     ebx, eax
0x18000658c  test    eax, eax
0x18000658e  js      loc_180006674
0x180006594  lea     rcx, aGetencryptionm; "GetEncryptionMethod"
0x18000659b  call    cs:__imp_SysAllocString
0x1800065a1  mov     r14, rax
0x1800065a4  test    rax, rax
0x1800065a7  jz      loc_1800064C7
0x1800065ad  mov     rcx, [rsp+910h+pProxy]
0x1800065b2  lea     rdx, [rsp+910h+var_8B8]
0x1800065b7  mov     qword ptr [rsp+910h+dwCapabilities], r12
0x1800065bc  xor     r9d, r9d
0x1800065bf  mov     [rsp+910h+pAuthInfo], rdx
0x1800065c4  mov     r8, r14
0x1800065c7  mov     qword ptr [rsp+910h+dwImpLevel], r12
0x1800065cc  mov     rdx, rsi
0x1800065cf  mov     rax, [rcx]
0x1800065d2  mov     [rsp+910h+ppv], r12
0x1800065d7  mov     rax, [rax+0C0h]
0x1800065de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065e3  mov     ebx, eax
0x1800065e5  test    eax, eax
0x1800065e7  js      loc_180006674
0x1800065ed  mov     rcx, [rsp+910h+var_8B8]
0x1800065f2  lea     r9, [rbp+810h+var_890]
0x1800065f6  mov     qword ptr [rsp+910h+dwImpLevel], r12
0x1800065fb  lea     rdx, aReturnvalue; "ReturnValue"
0x180006602  xor     r8d, r8d
0x180006605  mov     [rsp+910h+ppv], r12
0x18000660a  mov     rax, [rcx]
0x18000660d  mov     rax, [rax+20h]
0x180006611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006616  mov     ebx, eax
0x180006618  test    eax, eax
0x18000661a  js      short loc_180006674
0x18000661c  cmp     word ptr [rbp+810h+var_890], r15w
0x180006621  jz      short loc_18000662A
0x180006623  mov     ebx, 0C0A0001Bh
0x180006628  jmp     short loc_180006674
0x18000662a  mov     ebx, dword ptr [rbp+810h+var_890+8]
0x18000662d  test    ebx, ebx
0x18000662f  js      short loc_180006674
0x180006631  mov     rcx, [rsp+910h+var_8B8]
0x180006636  lea     r9, [rsp+910h+pvarg]
0x18000663b  mov     qword ptr [rsp+910h+dwImpLevel], r12
0x180006640  lea     rdx, aEncryptionmeth; "EncryptionMethod"
0x180006647  xor     r8d, r8d
0x18000664a  mov     [rsp+910h+ppv], r12
0x18000664f  mov     rax, [rcx]
0x180006652  mov     rax, [rax+20h]
0x180006656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000665b  mov     ebx, eax
0x18000665d  test    eax, eax
0x18000665f  js      short loc_180006674
0x180006661  cmp     word ptr [rsp+910h+pvarg], r15w
0x180006667  jnz     short loc_180006623
0x180006669  cmp     dword ptr [rsp+910h+pvarg+8], r12d
0x18000666e  mov     ebx, r12d
0x180006671  setz    bl
0x180006674  mov     rcx, [rsp+910h+var_8B0]
0x180006679  test    rcx, rcx
0x18000667c  jz      short loc_18000668F
0x18000667e  mov     rax, [rcx]
0x180006681  mov     rax, [rax+10h]
0x180006685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000668a  mov     [rsp+910h+var_8B0], r12
0x18000668f  mov     rcx, [rsp+910h+pProxy]
0x180006694  test    rcx, rcx
0x180006697  jz      short loc_1800066AA
0x180006699  mov     rax, [rcx]
0x18000669c  mov     rax, [rax+10h]
0x1800066a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a5  mov     [rsp+910h+pProxy], r12
0x1800066aa  mov     rcx, [rsp+910h+var_8B8]
0x1800066af  test    rcx, rcx
0x1800066b2  jz      short loc_1800066C5
0x1800066b4  mov     rax, [rcx]
0x1800066b7  mov     rax, [rax+10h]
0x1800066bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066c0  mov     [rsp+910h+var_8B8], r12
0x1800066c5  test    rdi, rdi
0x1800066c8  jz      short loc_1800066D3
0x1800066ca  mov     rcx, rdi; bstrString
0x1800066cd  call    cs:__imp_SysFreeString
0x1800066d3  test    rsi, rsi
0x1800066d6  jz      short loc_1800066E1
0x1800066d8  mov     rcx, rsi; bstrString
0x1800066db  call    cs:__imp_SysFreeString
0x1800066e1  test    r14, r14
0x1800066e4  jz      short loc_1800066EF
0x1800066e6  mov     rcx, r14; bstrString
0x1800066e9  call    cs:__imp_SysFreeString
0x1800066ef  lea     rcx, [rsp+910h+pvarg]; pvarg
0x1800066f4  call    cs:__imp_VariantClear
0x1800066fa  lea     rcx, [rbp+810h+var_890]; pvarg
0x1800066fe  call    cs:__imp_VariantClear
0x180006704  mov     eax, ebx
0x180006706  mov     rcx, [rbp+810h+var_30]
0x18000670d  xor     rcx, rsp; StackCookie
0x180006710  call    __security_check_cookie
0x180006715  lea     r11, [rsp+910h+var_20]
0x18000671d  mov     rbx, [r11+38h]
0x180006721  mov     rsi, [r11+40h]
0x180006725  mov     rsp, r11
0x180006728  pop     r15
0x18000672a  pop     r14
0x18000672c  pop     r12
0x18000672e  pop     rdi
0x18000672f  pop     rbp
0x180006730  retn
```
