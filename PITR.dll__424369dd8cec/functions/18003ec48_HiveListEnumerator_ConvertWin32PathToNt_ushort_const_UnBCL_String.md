# HiveListEnumerator::ConvertWin32PathToNt(ushort const *,UnBCL::String * *)

- ea: `0x18003ec48`
- end: `0x18003ee8c`
- name: `?ConvertWin32PathToNt@HiveListEnumerator@@SA_NPEBGPEAPEAVString@UnBCL@@@Z`
- size: `580`
- prototype: `char __fastcall(const unsigned __int16 *, struct UnBCL::String **)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003f8bc`

## callees

- `0x180009e04`
- `0x18003ec48`
- `0x1800502c2`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18003eca9`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18003eca9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ed39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ee3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ed39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ee3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ecb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ecbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003edb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003edc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ecb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ecbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003edb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003edc0`
- `WDSCORE!CurrentIP` at `0x18003ecc7`
- `WDSCORE!CurrentIP` at `0x18003edc8`
- `WDSCORE!CurrentIP` at `0x18003ecc7`
- `WDSCORE!CurrentIP` at `0x18003edc8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003ed31`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003ee36`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003ed31`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003ee36`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18003ed5a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18003ed6c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18003ed5a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18003ed6c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18003ed93`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18003ed9e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18003ed93`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18003ed9e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18003ed79`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18003ed79`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003ed87`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003ed87`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003ee5d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003ee5d`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18003ee4d`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18003ee4d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18003eda9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18003eda9`

## string_xrefs

- `0x18003ed02`: `HiveListEnumerator::ConvertWin32PathToNt`
- `0x18003ee07`: `HiveListEnumerator::ConvertWin32PathToNt`
- `0x18003eddc`: `BuildPath failed for %s and %s. GLE: %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
char __fastcall HiveListEnumerator::ConvertWin32PathToNt(const unsigned __int16 *a1, struct UnBCL::String **a2)
{
  DWORD v4; // esi
  DWORD v5; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  const char *v9; // r14
  const struct UnBCL::String *v10; // rbx
  const struct UnBCL::String *v11; // rax
  struct UnBCL::String *v12; // rax
  DWORD LastError; // esi
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  char v17; // bl
  _BYTE v18[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[24]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v20[24]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR DeviceName; // [rsp+A0h] [rbp-60h] BYREF
  int v22; // [rsp+A2h] [rbp-5Eh]
  WCHAR TargetPath[264]; // [rsp+B0h] [rbp-50h] BYREF

  v22 = 58;
  DeviceName = *a1;
  memset_0(TargetPath, 0, 0x208u);
  if ( QueryDosDeviceW(&DeviceName, TargetPath, 0x104u) )
  {
    TargetPath[259] = 0;
    v9 = (const char *)(a1 + 2);
    v10 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v20, a1 + 2);
    v11 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v19, TargetPath);
    v12 = UnBCL::Path::Combine(v11, v10);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v18, v12);
    UnBCL::String::~String((UnBCL::String *)v19);
    UnBCL::String::~String((UnBCL::String *)v20);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v18) )
    {
      *a2 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::Steal(v18);
      v17 = 1;
    }
    else
    {
      LastError = GetLastError();
      v14 = GetLastError();
      v15 = CurrentIP();
      v16 = ConstructPartialMsgW(
              50331648,
              "BuildPath failed for %s and %s. GLE: %u",
              (const char *)TargetPath,
              v9,
              LastError);
      WdsSetupLogMessageW(
        v16,
        0,
        L"D",
        0,
        251,
        L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
        L"HiveListEnumerator::ConvertWin32PathToNt",
        v15,
        v14,
        0,
        0);
      SetLastError(LastError);
      v17 = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v18);
    return v17;
  }
  else
  {
    v4 = GetLastError();
    v5 = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(50331648, "QueryDosDevice failed for %s. GLE: %u", (const char *)&DeviceName, v4);
    WdsSetupLogMessageW(
      v7,
      0,
      L"D",
      0,
      239,
      L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
      L"HiveListEnumerator::ConvertWin32PathToNt",
      v6,
      v5,
      0,
      0);
    SetLastError(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x18003ec48  mov     [rsp-8+arg_10], rbx
0x18003ec4d  mov     [rsp-8+arg_18], rsi
0x18003ec52  push    rbp
0x18003ec53  push    rdi
0x18003ec54  push    r14
0x18003ec56  lea     rbp, [rsp-1D0h]
0x18003ec5e  sub     rsp, 2D0h
0x18003ec65  mov     rax, cs:__security_cookie
0x18003ec6c  xor     rax, rsp
0x18003ec6f  mov     [rbp+1E0h+var_20], rax
0x18003ec76  mov     rdi, rdx
0x18003ec79  mov     rbx, rcx
0x18003ec7c  mov     [rbp+1E0h+var_23E], 3Ah ; ':'
0x18003ec83  movzx   eax, word ptr [rcx]
0x18003ec86  mov     [rbp+1E0h+DeviceName], ax
0x18003ec8a  xor     edx, edx; Val
0x18003ec8c  mov     r8d, 208h; Size
0x18003ec92  lea     rcx, [rbp+1E0h+TargetPath]; void *
0x18003ec96  call    memset_0
0x18003ec9b  mov     r8d, 104h; ucchMax
0x18003eca1  lea     rdx, [rbp+1E0h+TargetPath]; lpTargetPath
0x18003eca5  lea     rcx, [rbp+1E0h+DeviceName]; lpDeviceName
0x18003eca9  call    cs:__imp_QueryDosDeviceW
0x18003ecaf  test    eax, eax
0x18003ecb1  jnz     loc_18003ED46
0x18003ecb7  call    cs:__imp_GetLastError
0x18003ecbd  mov     esi, eax
0x18003ecbf  call    cs:__imp_GetLastError
0x18003ecc5  mov     edi, eax
0x18003ecc7  call    cs:__imp_CurrentIP
0x18003eccd  mov     rbx, rax
0x18003ecd0  mov     r9d, esi
0x18003ecd3  lea     r8, [rbp+1E0h+DeviceName]
0x18003ecd7  lea     rdx, aQuerydosdevice; "QueryDosDevice failed for %s. GLE: %u"
0x18003ecde  mov     ecx, 3000000h; unsigned int
0x18003ece3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003ece8  mov     [rsp+2E0h+var_290], 0
0x18003ecf0  mov     [rsp+2E0h+var_298], 0
0x18003ecf9  mov     [rsp+2E0h+var_2A0], edi
0x18003ecfd  mov     [rsp+2E0h+var_2A8], rbx
0x18003ed02  lea     rcx, aHivelistenumer; "HiveListEnumerator::ConvertWin32PathToN"...
0x18003ed09  mov     [rsp+2E0h+var_2B0], rcx
0x18003ed0e  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003ed15  mov     [rsp+2E0h+var_2B8], rcx
0x18003ed1a  mov     [rsp+2E0h+var_2C0], 0EFh
0x18003ed22  xor     r9d, r9d
0x18003ed25  lea     r8, aD; "D"
0x18003ed2c  xor     edx, edx
0x18003ed2e  mov     rcx, rax
0x18003ed31  call    cs:__imp_WdsSetupLogMessageW
0x18003ed37  mov     ecx, esi; dwErrCode
0x18003ed39  call    cs:__imp_SetLastError
0x18003ed3f  xor     al, al
0x18003ed41  jmp     loc_18003EE65
0x18003ed46  xor     eax, eax
0x18003ed48  mov     [rbp+1E0h+var_2A], ax
0x18003ed4f  lea     r14, [rbx+4]
0x18003ed53  mov     rdx, r14
0x18003ed56  lea     rcx, [rbp+1E0h+var_258]
0x18003ed5a  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18003ed60  mov     rbx, rax
0x18003ed63  lea     rdx, [rbp+1E0h+TargetPath]
0x18003ed67  lea     rcx, [rsp+2E0h+var_270]
0x18003ed6c  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18003ed72  nop
0x18003ed73  mov     rdx, rbx
0x18003ed76  mov     rcx, rax
0x18003ed79  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18003ed7f  mov     rdx, rax
0x18003ed82  lea     rcx, [rsp+2E0h+var_280]
0x18003ed87  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003ed8d  nop
0x18003ed8e  lea     rcx, [rsp+2E0h+var_270]
0x18003ed93  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18003ed99  nop
0x18003ed9a  lea     rcx, [rbp+1E0h+var_258]
0x18003ed9e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18003eda4  lea     rcx, [rsp+2E0h+var_280]
0x18003eda9  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18003edaf  test    rax, rax
0x18003edb2  jnz     loc_18003EE48
0x18003edb8  call    cs:__imp_GetLastError
0x18003edbe  mov     esi, eax
0x18003edc0  call    cs:__imp_GetLastError
0x18003edc6  mov     edi, eax
0x18003edc8  call    cs:__imp_CurrentIP
0x18003edce  mov     rbx, rax
0x18003edd1  mov     [rsp+2E0h+var_2C0], esi
0x18003edd5  mov     r9, r14
0x18003edd8  lea     r8, [rbp+1E0h+TargetPath]
0x18003eddc  lea     rdx, aBuildpathFaile; "BuildPath failed for %s and %s. GLE: %u"
0x18003ede3  mov     ecx, 3000000h; unsigned int
0x18003ede8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003eded  mov     [rsp+2E0h+var_290], 0
0x18003edf5  mov     [rsp+2E0h+var_298], 0
0x18003edfe  mov     [rsp+2E0h+var_2A0], edi
0x18003ee02  mov     [rsp+2E0h+var_2A8], rbx
0x18003ee07  lea     rcx, aHivelistenumer; "HiveListEnumerator::ConvertWin32PathToN"...
0x18003ee0e  mov     [rsp+2E0h+var_2B0], rcx
0x18003ee13  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003ee1a  mov     [rsp+2E0h+var_2B8], rcx
0x18003ee1f  mov     [rsp+2E0h+var_2C0], 0FBh
0x18003ee27  xor     r9d, r9d
0x18003ee2a  lea     r8, aD; "D"
0x18003ee31  xor     edx, edx
0x18003ee33  mov     rcx, rax
0x18003ee36  call    cs:__imp_WdsSetupLogMessageW
0x18003ee3c  mov     ecx, esi; dwErrCode
0x18003ee3e  call    cs:__imp_SetLastError
0x18003ee44  xor     ebx, ebx
0x18003ee46  jmp     short loc_18003EE58
0x18003ee48  lea     rcx, [rsp+2E0h+var_280]
0x18003ee4d  call    cs:__imp_?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::Steal(void)
0x18003ee53  mov     [rdi], rax
0x18003ee56  mov     bl, 1
0x18003ee58  lea     rcx, [rsp+2E0h+var_280]
0x18003ee5d  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18003ee63  mov     al, bl
0x18003ee65  mov     rcx, [rbp+1E0h+var_20]
0x18003ee6c  xor     rcx, rsp; StackCookie
0x18003ee6f  call    __security_check_cookie
0x18003ee74  lea     r11, [rsp+2E0h+var_10]
0x18003ee7c  mov     rbx, [r11+30h]
0x18003ee80  mov     rsi, [r11+38h]
0x18003ee84  mov     rsp, r11
0x18003ee87  pop     r14
0x18003ee89  pop     rdi
0x18003ee8a  pop     rbp
0x18003ee8b  retn
```
