# UpdateReserveManager::DoesBuildHaveSuppressInheritanceSupport(bool *)

- ea: `0x180014e34`
- end: `0x18001502c`
- name: `?DoesBuildHaveSuppressInheritanceSupport@UpdateReserveManager@@AEAAJPEA_N@Z`
- size: `504`
- prototype: `__int64 __fastcall(HKEY *this, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180012bf0`
- `0x180021a28`

## callees

- `0x180003870`
- `0x180003c84`
- `0x1800042f4`
- `0x1800044e0`
- `0x18000fafc`
- `0x180011a20`
- `0x180014e34`
- `0x1800248e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014ea2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014f71`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014ea2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014f71`

## string_xrefs

- `0x180014eae`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014f7d`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014eb9`: `UpdateReserveManager::DoesBuildHaveSuppressInheritanceSupport`
- `0x180014f88`: `UpdateReserveManager::DoesBuildHaveSuppressInheritanceSupport`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::DoesBuildHaveSuppressInheritanceSupport(HKEY *this, bool *a2)
{
  int ValueW; // ebx
  DWORD v5; // ebx
  void *pvData; // rsi
  __int64 v7; // rcx
  NTSTATUS v8; // eax
  unsigned int v10; // [rsp+48h] [rbp-9h] BYREF
  void *v11; // [rsp+50h] [rbp-1h] BYREF
  const char *v12; // [rsp+58h] [rbp+7h] BYREF
  const char *v13; // [rsp+60h] [rbp+Fh]
  __int64 v14; // [rsp+68h] [rbp+17h]
  const char *v15; // [rsp+70h] [rbp+1Fh]
  __int64 v16; // [rsp+78h] [rbp+27h]
  DWORD pcbData; // [rsp+80h] [rbp+2Fh] BYREF

  v16 = -2;
  pcbData = 0;
  ValueW = RegGetValueW(this[13], L"Microsoft\\Windows NT\\CurrentVersion", L"CurrentBuildNumber", 2u, 0, 0, &pcbData);
  if ( ValueW )
  {
    v12 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v13 = "UpdateReserveManager::DoesBuildHaveSuppressInheritanceSupport";
    v14 = 4656;
    v15 = "RetValue";
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    RtlReportErrorOrigination(&v12, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
  }
  else
  {
    v5 = (pcbData >> 1) + 1;
    pvData = operator new[](saturated_mul(v5, 2u));
    v11 = pvData;
    pcbData = 2 * v5;
    memset_0(pvData, 0, 2 * v5);
    ValueW = RegGetValueW(
               this[13],
               L"Microsoft\\Windows NT\\CurrentVersion",
               L"CurrentBuildNumber",
               2u,
               0,
               pvData,
               &pcbData);
    if ( ValueW )
    {
      v12 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v13 = "UpdateReserveManager::DoesBuildHaveSuppressInheritanceSupport";
      v14 = 4673;
      v15 = "RetValue";
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      RtlReportErrorOrigination(&v12, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
    }
    else
    {
      v10 = 0;
      v8 = Windows::StringUtil::Rtl::ParsePositiveInteger<Windows::AutoNewArrayPtr<wchar_t>,unsigned long>(
             v7,
             &v11,
             &v10);
      if ( v8 >= 0 )
      {
        *a2 = v10 >= 0x4F0E;
        ValueW = 0;
      }
      else
      {
        ValueW = ConvertNtStatusToHResult(v8);
      }
    }
    operator delete(pvData);
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x180014e34  mov     r11, rsp
0x180014e37  push    rbp
0x180014e38  push    rdi
0x180014e39  push    r14
0x180014e3b  lea     rbp, [r11-5Fh]
0x180014e3f  sub     rsp, 90h
0x180014e46  mov     [rbp+57h+var_30], 0FFFFFFFFFFFFFFFEh
0x180014e4e  mov     [r11+18h], rbx
0x180014e52  mov     [r11+20h], rsi
0x180014e56  mov     rax, cs:__security_cookie
0x180014e5d  xor     rax, rsp
0x180014e60  mov     [rbp+57h+var_20], rax
0x180014e64  mov     rdi, rdx
0x180014e67  mov     r14, rcx
0x180014e6a  mov     [rbp+57h+var_28], 0
0x180014e71  lea     rax, [rbp+57h+var_28]
0x180014e75  mov     [r11-78h], rax
0x180014e79  mov     qword ptr [r11-80h], 0
0x180014e81  mov     [rsp+0A0h+pdwType], 0; pdwType
0x180014e8a  mov     r9d, 2; dwFlags
0x180014e90  lea     r8, aCurrentbuildnu; "CurrentBuildNumber"
0x180014e97  lea     rdx, aMicrosoftWindo_0; "Microsoft\\Windows NT\\CurrentVersion"
0x180014e9e  mov     rcx, [rcx+68h]; hkey
0x180014ea2  call    cs:__imp_RegGetValueW
0x180014ea8  mov     ebx, eax
0x180014eaa  test    eax, eax
0x180014eac  jz      short loc_180014EFC
0x180014eae  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180014eb5  mov     [rbp+57h+var_50], rax
0x180014eb9  lea     rax, aUpdatereservem_14; "UpdateReserveManager::DoesBuildHaveSupp"...
0x180014ec0  mov     [rbp+57h+var_48], rax
0x180014ec4  mov     [rbp+57h+var_40], 1230h
0x180014ecc  lea     rax, aRetvalue; "RetValue"
0x180014ed3  mov     [rbp+57h+var_38], rax
0x180014ed7  test    ebx, ebx
0x180014ed9  jle     short loc_180014EE4
0x180014edb  movzx   ebx, bx
0x180014ede  or      ebx, 80070000h
0x180014ee4  mov     r8d, ebx
0x180014ee7  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180014eee  lea     rcx, [rbp+57h+var_50]
0x180014ef2  call    RtlReportErrorOrigination
0x180014ef7  jmp     loc_180015006
0x180014efc  mov     ebx, [rbp+57h+var_28]
0x180014eff  shr     ebx, 1
0x180014f01  inc     ebx
0x180014f03  mov     [rbp+57h+var_58], 0
0x180014f0b  mov     ecx, ebx
0x180014f0d  mov     eax, 2
0x180014f12  mul     rcx
0x180014f15  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014f1c  cmovb   rax, rcx
0x180014f20  mov     rcx, rax; unsigned __int64
0x180014f23  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014f28  mov     rsi, rax
0x180014f2b  mov     [rbp+57h+var_58], rax
0x180014f2f  lea     ecx, [rbx+rbx]
0x180014f32  mov     [rbp+57h+var_28], ecx
0x180014f35  mov     r8d, ecx; Size
0x180014f38  xor     edx, edx; Val
0x180014f3a  mov     rcx, rax; void *
0x180014f3d  call    memset_0
0x180014f42  lea     rax, [rbp+57h+var_28]
0x180014f46  mov     [rsp+0A0h+pcbData], rax; pcbData
0x180014f4b  mov     [rsp+0A0h+pvData], rsi; pvData
0x180014f50  mov     [rsp+0A0h+pdwType], 0; pdwType
0x180014f59  mov     r9d, 2; dwFlags
0x180014f5f  lea     r8, aCurrentbuildnu; "CurrentBuildNumber"
0x180014f66  lea     rdx, aMicrosoftWindo_0; "Microsoft\\Windows NT\\CurrentVersion"
0x180014f6d  mov     rcx, [r14+68h]; hkey
0x180014f71  call    cs:__imp_RegGetValueW
0x180014f77  mov     ebx, eax
0x180014f79  test    eax, eax
0x180014f7b  jz      short loc_180014FC8
0x180014f7d  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180014f84  mov     [rbp+57h+var_50], rax
0x180014f88  lea     rax, aUpdatereservem_14; "UpdateReserveManager::DoesBuildHaveSupp"...
0x180014f8f  mov     [rbp+57h+var_48], rax
0x180014f93  mov     [rbp+57h+var_40], 1241h
0x180014f9b  lea     rax, aRetvalue; "RetValue"
0x180014fa2  mov     [rbp+57h+var_38], rax
0x180014fa6  test    ebx, ebx
0x180014fa8  jle     short loc_180014FB3
0x180014faa  movzx   ebx, bx
0x180014fad  or      ebx, 80070000h
0x180014fb3  mov     r8d, ebx
0x180014fb6  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180014fbd  lea     rcx, [rbp+57h+var_50]
0x180014fc1  call    RtlReportErrorOrigination
0x180014fc6  jmp     short loc_180014FE9
0x180014fc8  mov     [rbp+57h+var_60], 0
0x180014fcf  lea     r8, [rbp+57h+var_60]
0x180014fd3  lea     rdx, [rbp+57h+var_58]
0x180014fd7  call    ??$ParsePositiveInteger@V?$AutoNewArrayPtr@_W@Windows@@K@Rtl@StringUtil@Windows@@YAJKAEBV?$AutoNewArrayPtr@_W@2@PEAK@Z; Windows::StringUtil::Rtl::ParsePositiveInteger<Windows::AutoNewArrayPtr<wchar_t>,ulong>(ulong,Windows::AutoNewArrayPtr<wchar_t> const &,ulong *)
0x180014fdc  test    eax, eax
0x180014fde  jns     short loc_180014FEB
0x180014fe0  mov     ecx, eax; Status
0x180014fe2  call    ConvertNtStatusToHResult
0x180014fe7  mov     ebx, eax
0x180014fe9  jmp     short loc_180014FFE
0x180014feb  cmp     [rbp+57h+var_60], 4F0Eh
0x180014ff2  jnb     short loc_180014FF8
0x180014ff4  xor     al, al
0x180014ff6  jmp     short loc_180014FFA
0x180014ff8  mov     al, 1
0x180014ffa  mov     [rdi], al
0x180014ffc  xor     ebx, ebx
0x180014ffe  mov     rcx, rsi; void *
0x180015001  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015006  mov     eax, ebx
0x180015008  mov     rcx, [rbp+57h+var_20]
0x18001500c  xor     rcx, rsp; StackCookie
0x18001500f  call    __security_check_cookie
0x180015014  lea     r11, [rsp+0A0h+var_10]
0x18001501c  mov     rbx, [r11+30h]
0x180015020  mov     rsi, [r11+38h]
0x180015024  mov     rsp, r11
0x180015027  pop     r14
0x180015029  pop     rdi
0x18001502a  pop     rbp
0x18001502b  retn
```
