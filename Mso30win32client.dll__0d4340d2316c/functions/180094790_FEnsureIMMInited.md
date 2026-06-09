# FEnsureIMMInited

- ea: `0x180094790`
- end: `0x180094b6e`
- name: `FEnsureIMMInited`
- size: `990`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180094710`
- `0x1800b4520`
- `0x18018de20`
- `0x1804170f0`
- `0x1804172a0`
- `0x180417310`
- `0x1804173f0`
- `0x1804174a0`

## callees

- `0x180094790`
- `0x18018df70`
- `0x180192560`

## import_xrefs

- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1800947ae`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1800947ae`
- `Mso20Win32Client!__imp_?MsoAdjustRegSamForWow@@YAKK@Z` at `0x180094af9`
- `Mso20Win32Client!__imp_?MsoAdjustRegSamForWow@@YAKK@Z` at `0x180094af9`
- `Mso20Win32Client!__imp_TWCCoCreateInstance` at `0x180094833`
- `Mso20Win32Client!__imp_TWCCoCreateInstance` at `0x180094833`
- `ADVAPI32!RegOpenKeyExA` at `0x180094b1d`
- `ADVAPI32!RegOpenKeyExA` at `0x180094b1d`
- `ADVAPI32!RegCloseKey` at `0x180094b31`
- `ADVAPI32!RegCloseKey` at `0x180094b31`
- `IMM32!ImmSetStatusWindowPos` at `0x180094abc`
- `IMM32!ImmSetOpenStatus` at `0x180094aae`
- `IMM32!ImmSetConversionStatus` at `0x180094aa0`
- `IMM32!ImmSetCompositionWindow` at `0x180094a92`
- `IMM32!ImmSetCompositionStringW` at `0x180094a84`
- `IMM32!ImmSetCompositionStringA` at `0x180094a76`
- `IMM32!ImmSetCompositionFontW` at `0x180094a68`
- `IMM32!ImmSetCompositionFontA` at `0x180094a5a`
- `IMM32!ImmSetCandidateWindow` at `0x180094a4c`
- `IMM32!ImmRegisterWordW` at `0x180094a3e`
- `IMM32!ImmRegisterWordA` at `0x180094a30`
- `IMM32!ImmReleaseContext` at `0x180094a22`
- `IMM32!ImmNotifyIME` at `0x180094a14`
- `IMM32!ImmIsUIMessageW` at `0x180094a06`
- `IMM32!ImmIsUIMessageA` at `0x1800949f8`
- `IMM32!ImmIsIME` at `0x1800949ea`
- `IMM32!ImmGetVirtualKey` at `0x1800949dc`
- `IMM32!ImmGetProperty` at `0x1800949ce`
- `IMM32!ImmGetOpenStatus` at `0x1800949c0`
- `IMM32!ImmGetIMEFileNameW` at `0x1800949b2`
- `IMM32!ImmGetIMEFileNameA` at `0x1800949a4`
- `IMM32!ImmGetDescriptionW` at `0x180094996`
- `IMM32!ImmGetDescriptionA` at `0x180094988`
- `IMM32!ImmGetDefaultIMEWnd` at `0x18009497a`
- `IMM32!ImmGetConversionStatus` at `0x18009496c`
- `IMM32!ImmGetContext` at `0x18009495e`
- `IMM32!ImmGetCompositionWindow` at `0x180094950`
- `IMM32!ImmGetCompositionStringW` at `0x180094942`
- `IMM32!ImmGetCompositionStringA` at `0x180094934`
- `IMM32!ImmGetCompositionFontW` at `0x180094926`
- `IMM32!ImmGetCompositionFontA` at `0x180094918`
- `IMM32!ImmGetCandidateWindow` at `0x18009490a`
- `IMM32!ImmEscapeW` at `0x1800948fc`
- `IMM32!ImmEscapeA` at `0x1800948ee`
- `IMM32!ImmAssociateContext` at `0x1800948a8`
- `IMM32!ImmDestroyContext` at `0x1800948e0`
- `IMM32!ImmConfigureIMEA` at `0x1800948b6`
- `IMM32!ImmConfigureIMEW` at `0x1800948c4`
- `IMM32!ImmCreateContext` at `0x1800948d2`
- `ole32!CoUninitialize` at `0x180094b62`
- `ole32!CoUninitialize` at `0x180094b62`
- `ole32!CoInitialize` at `0x1800947f0`
- `ole32!CoInitialize` at `0x1800947f0`

## string_xrefs

- `0x180094b02`: `CLSID\{C1EE01F2-B3B6-4A6A-9DDD-E988C088EC82}`

## pseudocode

```c
__int64 FEnsureIMMInited()
{
  int v1; // eax
  GUID *v2; // r9
  GUID *v3; // rcx
  REGSAM v4; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( !fIMM_Inited )
  {
    if ( MsoDwRegGetDw((const struct _msoreg *)&OrapiData::Mso::c_msoridIMEUseAIMM12) )
    {
      v1 = 0;
      imm = 0;
    }
    else
    {
      v1 = imm;
    }
    qword_180F782E8 = 0;
    dword_180F782F0 = -1;
    if ( !v1 || !(unsigned int)MsoFUIMAvailableGrf(0) )
      goto LABEL_17;
    if ( CoInitialize(0) >= 0 )
      vfCoInitializeForIMMSucceeded = 1;
    if ( *(&imm + 1) )
    {
      hKey = 0;
      v4 = MsoAdjustRegSamForWow(0x20019u);
      RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID\\{C1EE01F2-B3B6-4A6A-9DDD-E988C088EC82}", 0, v4, &hKey);
      if ( !hKey )
      {
LABEL_15:
        if ( vfCoInitializeForIMMSucceeded )
        {
          vfCoInitializeForIMMSucceeded = 0;
          CoUninitialize();
        }
LABEL_17:
        off_180F78178 = (HIMC (__fastcall *)(HWND, HIMC))ImmAssociateContext;
        off_180F78180 = (__int64 (__fastcall *)(HKL, HWND, unsigned int, void *))ImmConfigureIMEA;
        off_180F78260 = (__int64 (__fastcall *)(HKL, HWND, unsigned int, void *))ImmConfigureIMEW;
        off_180F78188 = ImmCreateContext;
        off_180F78190 = (__int64 (__fastcall *)(HIMC))ImmDestroyContext;
        off_180F78198 = (__int64 (__fastcall *)(HKL, HIMC, unsigned int, void *))ImmEscapeA;
        off_180F78268 = (__int64 (__fastcall *)(HKL, HIMC, unsigned int, void *))ImmEscapeW;
        off_180F781A0 = (__int64 (__fastcall *)(HIMC, unsigned int, struct tagCANDIDATEFORM *))ImmGetCandidateWindow;
        off_180F781A8 = (__int64 (__fastcall *)(HIMC, struct tagLOGFONTA *))ImmGetCompositionFontA;
        off_180F78270 = (__int64 (__fastcall *)(HIMC, struct tagLOGFONTW *))ImmGetCompositionFontW;
        off_180F781B0 = (__int64 (__fastcall *)(HIMC, unsigned int, void *, unsigned int))ImmGetCompositionStringA;
        off_180F78278 = (__int64 (__fastcall *)(HIMC, unsigned int, void *, unsigned int))ImmGetCompositionStringW;
        off_180F781B8 = (__int64 (__fastcall *)(HIMC, struct tagCOMPOSITIONFORM *))ImmGetCompositionWindow;
        off_180F781C0 = (HIMC (__fastcall *)(HWND))ImmGetContext;
        off_180F781C8 = (__int64 (__fastcall *)(HIMC, unsigned int *, unsigned int *))ImmGetConversionStatus;
        off_180F781D0 = (HWND (__fastcall *)(HWND))ImmGetDefaultIMEWnd;
        off_180F781D8 = (unsigned int (__fastcall *)(HKL, char *, unsigned int))ImmGetDescriptionA;
        off_180F78280 = (unsigned int (__fastcall *)(HKL, wchar_t *, unsigned int))ImmGetDescriptionW;
        off_180F781E0 = (__int64 (__fastcall *)(HKL, char *, unsigned int))ImmGetIMEFileNameA;
        off_180F78288 = (__int64 (__fastcall *)(HKL, wchar_t *, unsigned int))ImmGetIMEFileNameW;
        off_180F781E8 = (__int64 (__fastcall *)(HIMC))ImmGetOpenStatus;
        off_180F781F0 = (unsigned int (__fastcall *)(HKL, unsigned int))ImmGetProperty;
        off_180F781F8 = (unsigned int (__fastcall *)(HWND))ImmGetVirtualKey;
        off_180F78200 = (__int64 (__fastcall *)(HKL))ImmIsIME;
        off_180F78208 = (__int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64))ImmIsUIMessageA;
        off_180F78290 = (__int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64))ImmIsUIMessageW;
        off_180F78210 = (__int64 (__fastcall *)(HIMC, unsigned int, unsigned int, unsigned int))ImmNotifyIME;
        off_180F78220 = (__int64 (__fastcall *)(HWND, HIMC))ImmReleaseContext;
        off_180F78218 = (__int64 (__fastcall *)(HKL, const char *, unsigned int, const char *))ImmRegisterWordA;
        off_180F78298 = (__int64 (__fastcall *)(HKL, const wchar_t *, unsigned int, const wchar_t *))ImmRegisterWordW;
        off_180F78228 = (__int64 (__fastcall *)(HIMC, struct tagCANDIDATEFORM *))ImmSetCandidateWindow;
        off_180F78230 = (__int64 (__fastcall *)(HIMC, struct tagLOGFONTA *))ImmSetCompositionFontA;
        off_180F782A0 = (__int64 (__fastcall *)(HIMC, struct tagLOGFONTW *))ImmSetCompositionFontW;
        off_180F78238 = (__int64 (__fastcall *)(HIMC, unsigned int, const void *, unsigned int, const void *, unsigned int))ImmSetCompositionStringA;
        off_180F782A8 = (__int64 (__fastcall *)(HIMC, unsigned int, const void *, unsigned int, const void *, unsigned int))ImmSetCompositionStringW;
        off_180F78240 = (__int64 (__fastcall *)(HIMC, struct tagCOMPOSITIONFORM *))ImmSetCompositionWindow;
        off_180F78248 = (__int64 (__fastcall *)(HIMC, unsigned int, unsigned int))ImmSetConversionStatus;
        off_180F78250 = (__int64 (__fastcall *)(HIMC, int))ImmSetOpenStatus;
        off_180F78258 = (__int64 (__fastcall *)(HIMC, struct tagPOINT *))ImmSetStatusWindowPos;
        imm = 0;
        fIMM_Inited = 1;
        dword_180F782F0 = -1;
        return 1;
      }
      RegCloseKey(hKey);
      v2 = &IID_IActiveIMMAppEx;
      v3 = &CLSID_CActiveIMM12;
    }
    else
    {
      v2 = &IID_IActiveIMMApp;
      v3 = (GUID *)&unk_180C1F778;
    }
    if ( !(unsigned int)TWCCoCreateInstance(v3, 0, 1, v2, &vpAIMM) )
    {
      if ( !(**(unsigned int (__fastcall ***)(struct IActiveIMMAppEx *, GUID *, struct IActiveIMMMessagePumpOwner **))vpAIMM)(
              vpAIMM,
              &GUID_b5cf2cfa_8aeb_11d1_9364_0060b067b86e,
              &vpAIMMMessagePump) )
      {
        qword_180F782E8 = (__int64)vpAIMM;
        fIMM_Inited = 1;
        return 1;
      }
      (*(void (__fastcall **)(struct IActiveIMMAppEx *))(*(_QWORD *)vpAIMM + 16LL))(vpAIMM);
      vpAIMM = 0;
    }
    goto LABEL_15;
  }
  return 1;
}

```

## disassembly

```asm
0x180094790  sub     rsp, 38h
0x180094794  cmp     cs:?fIMM_Inited@@3_NA, 0; bool fIMM_Inited
0x18009479b  jz      short loc_1800947A7
0x18009479d  mov     eax, 1
0x1800947a2  add     rsp, 38h
0x1800947a6  retn
0x1800947a7  lea     rcx, ?c_msoridIMEUseAIMM12@Mso@OrapiData@@3U_msoreg@@B; _msoreg const OrapiData::Mso::c_msoridIMEUseAIMM12
0x1800947ae  call    cs:__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1800947b4  test    eax, eax
0x1800947b6  jnz     loc_180094B4A
0x1800947bc  mov     eax, dword ptr cs:?imm@@3U_imm_data@@A; _imm_data imm
0x1800947c2  mov     cs:qword_180F782E8, 0
0x1800947cd  mov     cs:dword_180F782F0, 0FFFFFFFFh
0x1800947d7  test    eax, eax
0x1800947d9  jz      loc_1800948A8
0x1800947df  xor     ecx, ecx
0x1800947e1  call    MsoFUIMAvailableGrf
0x1800947e6  test    eax, eax
0x1800947e8  jz      loc_1800948A8
0x1800947ee  xor     ecx, ecx; pvReserved
0x1800947f0  call    cs:__imp_CoInitialize
0x1800947f6  test    eax, eax
0x1800947f8  js      short loc_180094804
0x1800947fa  mov     cs:?vfCoInitializeForIMMSucceeded@@3HA, 1; int vfCoInitializeForIMMSucceeded
0x180094804  cmp     dword ptr cs:?imm@@3U_imm_data@@A+4, 0; _imm_data imm
0x18009480b  jnz     loc_180094AEB
0x180094811  lea     r9, IID_IActiveIMMApp
0x180094818  lea     rcx, unk_180C1F778
0x18009481f  lea     rax, ?vpAIMM@@3PEAUIActiveIMMAppEx@@EA; IActiveIMMAppEx * vpAIMM
0x180094826  mov     r8d, 1
0x18009482c  xor     edx, edx
0x18009482e  mov     [rsp+38h+phkResult], rax
0x180094833  call    cs:__imp_TWCCoCreateInstance
0x180094839  test    eax, eax
0x18009483b  jnz     short loc_18009489B
0x18009483d  mov     rcx, cs:?vpAIMM@@3PEAUIActiveIMMAppEx@@EA; IActiveIMMAppEx * vpAIMM
0x180094844  lea     r8, ?vpAIMMMessagePump@@3PEAUIActiveIMMMessagePumpOwner@@EA; IActiveIMMMessagePumpOwner * vpAIMMMessagePump
0x18009484b  lea     rdx, _GUID_b5cf2cfa_8aeb_11d1_9364_0060b067b86e
0x180094852  mov     rax, [rcx]
0x180094855  mov     rax, [rax]
0x180094858  call    cs:__guard_dispatch_icall_fptr
0x18009485e  test    eax, eax
0x180094860  jnz     short loc_18009487C
0x180094862  mov     rax, cs:?vpAIMM@@3PEAUIActiveIMMAppEx@@EA; IActiveIMMAppEx * vpAIMM
0x180094869  mov     cs:qword_180F782E8, rax
0x180094870  mov     cs:?fIMM_Inited@@3_NA, 1; bool fIMM_Inited
0x180094877  jmp     loc_18009479D
0x18009487c  mov     rcx, cs:?vpAIMM@@3PEAUIActiveIMMAppEx@@EA; IActiveIMMAppEx * vpAIMM
0x180094883  mov     rax, [rcx]
0x180094886  mov     rax, [rax+10h]
0x18009488a  call    cs:__guard_dispatch_icall_fptr
0x180094890  mov     cs:?vpAIMM@@3PEAUIActiveIMMAppEx@@EA, 0; IActiveIMMAppEx * vpAIMM
0x18009489b  cmp     cs:?vfCoInitializeForIMMSucceeded@@3HA, 0; int vfCoInitializeForIMMSucceeded
0x1800948a2  jnz     loc_180094B58
0x1800948a8  mov     rax, cs:__imp_ImmAssociateContext
0x1800948af  mov     cs:off_180F78178, rax
0x1800948b6  mov     rax, cs:__imp_ImmConfigureIMEA
0x1800948bd  mov     cs:off_180F78180, rax
0x1800948c4  mov     rax, cs:__imp_ImmConfigureIMEW
0x1800948cb  mov     cs:off_180F78260, rax
0x1800948d2  mov     rax, cs:__imp_ImmCreateContext
0x1800948d9  mov     cs:off_180F78188, rax
0x1800948e0  mov     rax, cs:__imp_ImmDestroyContext
0x1800948e7  mov     cs:off_180F78190, rax
0x1800948ee  mov     rax, cs:__imp_ImmEscapeA
0x1800948f5  mov     cs:off_180F78198, rax
0x1800948fc  mov     rax, cs:__imp_ImmEscapeW
0x180094903  mov     cs:off_180F78268, rax
0x18009490a  mov     rax, cs:__imp_ImmGetCandidateWindow
0x180094911  mov     cs:off_180F781A0, rax
0x180094918  mov     rax, cs:__imp_ImmGetCompositionFontA
0x18009491f  mov     cs:off_180F781A8, rax
0x180094926  mov     rax, cs:__imp_ImmGetCompositionFontW
0x18009492d  mov     cs:off_180F78270, rax
0x180094934  mov     rax, cs:__imp_ImmGetCompositionStringA
0x18009493b  mov     cs:off_180F781B0, rax
0x180094942  mov     rax, cs:__imp_ImmGetCompositionStringW
0x180094949  mov     cs:off_180F78278, rax
0x180094950  mov     rax, cs:__imp_ImmGetCompositionWindow
0x180094957  mov     cs:off_180F781B8, rax
0x18009495e  mov     rax, cs:__imp_ImmGetContext
0x180094965  mov     cs:off_180F781C0, rax
0x18009496c  mov     rax, cs:__imp_ImmGetConversionStatus
0x180094973  mov     cs:off_180F781C8, rax
0x18009497a  mov     rax, cs:__imp_ImmGetDefaultIMEWnd
0x180094981  mov     cs:off_180F781D0, rax
0x180094988  mov     rax, cs:__imp_ImmGetDescriptionA
0x18009498f  mov     cs:off_180F781D8, rax
0x180094996  mov     rax, cs:__imp_ImmGetDescriptionW
0x18009499d  mov     cs:off_180F78280, rax
0x1800949a4  mov     rax, cs:__imp_ImmGetIMEFileNameA
0x1800949ab  mov     cs:off_180F781E0, rax
0x1800949b2  mov     rax, cs:__imp_ImmGetIMEFileNameW
0x1800949b9  mov     cs:off_180F78288, rax
0x1800949c0  mov     rax, cs:__imp_ImmGetOpenStatus
0x1800949c7  mov     cs:off_180F781E8, rax
0x1800949ce  mov     rax, cs:__imp_ImmGetProperty
0x1800949d5  mov     cs:off_180F781F0, rax
0x1800949dc  mov     rax, cs:__imp_ImmGetVirtualKey
0x1800949e3  mov     cs:off_180F781F8, rax
0x1800949ea  mov     rax, cs:__imp_ImmIsIME
0x1800949f1  mov     cs:off_180F78200, rax
0x1800949f8  mov     rax, cs:__imp_ImmIsUIMessageA
0x1800949ff  mov     cs:off_180F78208, rax
0x180094a06  mov     rax, cs:__imp_ImmIsUIMessageW
0x180094a0d  mov     cs:off_180F78290, rax
0x180094a14  mov     rax, cs:__imp_ImmNotifyIME
0x180094a1b  mov     cs:off_180F78210, rax
0x180094a22  mov     rax, cs:__imp_ImmReleaseContext
0x180094a29  mov     cs:off_180F78220, rax
0x180094a30  mov     rax, cs:__imp_ImmRegisterWordA
0x180094a37  mov     cs:off_180F78218, rax
0x180094a3e  mov     rax, cs:__imp_ImmRegisterWordW
0x180094a45  mov     cs:off_180F78298, rax
0x180094a4c  mov     rax, cs:__imp_ImmSetCandidateWindow
0x180094a53  mov     cs:off_180F78228, rax
0x180094a5a  mov     rax, cs:__imp_ImmSetCompositionFontA
0x180094a61  mov     cs:off_180F78230, rax
0x180094a68  mov     rax, cs:__imp_ImmSetCompositionFontW
0x180094a6f  mov     cs:off_180F782A0, rax
0x180094a76  mov     rax, cs:__imp_ImmSetCompositionStringA
0x180094a7d  mov     cs:off_180F78238, rax
0x180094a84  mov     rax, cs:__imp_ImmSetCompositionStringW
0x180094a8b  mov     cs:off_180F782A8, rax
0x180094a92  mov     rax, cs:__imp_ImmSetCompositionWindow
0x180094a99  mov     cs:off_180F78240, rax
0x180094aa0  mov     rax, cs:__imp_ImmSetConversionStatus
0x180094aa7  mov     cs:off_180F78248, rax
0x180094aae  mov     rax, cs:__imp_ImmSetOpenStatus
0x180094ab5  mov     cs:off_180F78250, rax
0x180094abc  mov     rax, cs:__imp_ImmSetStatusWindowPos
0x180094ac3  mov     cs:off_180F78258, rax
0x180094aca  mov     cs:?imm@@3U_imm_data@@A, 0; _imm_data imm
0x180094ad5  mov     cs:?fIMM_Inited@@3_NA, 1; bool fIMM_Inited
0x180094adc  mov     cs:dword_180F782F0, 0FFFFFFFFh
0x180094ae6  jmp     loc_18009479D
0x180094aeb  mov     ecx, 20019h
0x180094af0  mov     [rsp+38h+hKey], 0
0x180094af9  call    cs:__imp_?MsoAdjustRegSamForWow@@YAKK@Z; MsoAdjustRegSamForWow(ulong)
0x180094aff  xor     r8d, r8d; ulOptions
0x180094b02  lea     rdx, aClsidC1ee01f2B; "CLSID\\{C1EE01F2-B3B6-4A6A-9DDD-E988C08"...
0x180094b09  mov     r9d, eax; samDesired
0x180094b0c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180094b13  lea     rax, [rsp+38h+hKey]
0x180094b18  mov     [rsp+38h+phkResult], rax; phkResult
0x180094b1d  call    cs:__imp_RegOpenKeyExA
0x180094b23  mov     rcx, [rsp+38h+hKey]; hKey
0x180094b28  test    rcx, rcx
0x180094b2b  jz      loc_18009489B
0x180094b31  call    cs:__imp_RegCloseKey
0x180094b37  lea     r9, IID_IActiveIMMAppEx
0x180094b3e  lea     rcx, CLSID_CActiveIMM12
0x180094b45  jmp     loc_18009481F
0x180094b4a  xor     eax, eax
0x180094b4c  mov     cs:?imm@@3U_imm_data@@A, rax; _imm_data imm
0x180094b53  jmp     loc_1800947C2
0x180094b58  mov     cs:?vfCoInitializeForIMMSucceeded@@3HA, 0; int vfCoInitializeForIMMSucceeded
0x180094b62  call    cs:__imp_CoUninitialize
0x180094b68  jmp     loc_1800948A8
```
