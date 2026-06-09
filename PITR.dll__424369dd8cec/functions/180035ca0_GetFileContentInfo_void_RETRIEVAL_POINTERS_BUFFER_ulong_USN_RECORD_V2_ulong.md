# GetFileContentInfo(void *,RETRIEVAL_POINTERS_BUFFER *,ulong,USN_RECORD_V2 *,ulong)

- ea: `0x180035ca0`
- end: `0x180035ed6`
- name: `?GetFileContentInfo@@YAJPEAXPEAURETRIEVAL_POINTERS_BUFFER@@KPEAUUSN_RECORD_V2@@K@Z`
- size: `566`
- prototype: `__int64 __fastcall(HANDLE hDevice, struct RETRIEVAL_POINTERS_BUFFER *lpOutBuffer, DWORD nOutBufferSize, struct USN_RECORD_V2 *, DWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18002fd88`
- `0x180035ac0`

## callees

- `0x180009e04`
- `0x18001def0`
- `0x180035ca0`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e29`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180035cf5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180035de9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180035cf5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180035de9`
- `WDSCORE!CurrentIP` at `0x180035d2b`
- `WDSCORE!CurrentIP` at `0x180035e31`
- `WDSCORE!CurrentIP` at `0x180035d2b`
- `WDSCORE!CurrentIP` at `0x180035e31`
- `WDSCORE!WdsSetupLogMessageW` at `0x180035d91`
- `WDSCORE!WdsSetupLogMessageW` at `0x180035e97`
- `WDSCORE!WdsSetupLogMessageW` at `0x180035d91`
- `WDSCORE!WdsSetupLogMessageW` at `0x180035e97`

## string_xrefs

- `0x180035d7a`: `base\diagnosis\srt\pitr\dll\src\utils.cpp`
- `0x180035e80`: `base\diagnosis\srt\pitr\dll\src\utils.cpp`

## pseudocode

```c
__int64 __fastcall GetFileContentInfo(
        HANDLE hDevice,
        struct RETRIEVAL_POINTERS_BUFFER *lpOutBuffer,
        DWORD nOutBufferSize,
        struct USN_RECORD_V2 *a4,
        DWORD a5)
{
  unsigned int v5; // esi
  signed int v8; // eax
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  signed int LastError; // eax
  bool v13; // sf
  signed int v14; // eax
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  int InBuffer; // [rsp+60h] [rbp-48h] BYREF
  DWORD BytesReturned; // [rsp+64h] [rbp-44h] BYREF
  __int64 v21; // [rsp+68h] [rbp-40h] BYREF

  v5 = 0;
  v21 = 0;
  BytesReturned = 0;
  InBuffer = 0;
  if ( DeviceIoControl(hDevice, 0x90073u, &v21, 8u, lpOutBuffer, nOutBufferSize, &BytesReturned, 0)
    || (v8 = GetLastError(), v8 == 38)
    || (v8 > 0 ? (v5 = (unsigned __int16)v8 | 0x80070000) : (v5 = v8),
        v9 = GetLastError(),
        v10 = CurrentIP(),
        v11 = ConstructPartialMsgW(0x2000000, "Failed to get extends for file, error: 0x%08X", v5),
        WdsSetupLogMessageW(
          v11,
          0,
          L"D",
          0,
          462,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\utils.cpp",
          L"GetFileContentInfo",
          v10,
          v9,
          0,
          0),
        !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)) )
  {
    InBuffer = 196610;
    if ( !DeviceIoControl(hDevice, 0x900EBu, &InBuffer, 4u, a4, a5, &BytesReturned, 0) )
    {
      LastError = GetLastError();
      v13 = LastError < 0;
      if ( LastError > 0 )
        v13 = 1;
      if ( v13 )
      {
        v14 = GetLastError();
        v5 = v14;
        if ( v14 > 0 )
          v5 = (unsigned __int16)v14 | 0x80070000;
      }
      else
      {
        v5 = -2147467259;
      }
      v15 = GetLastError();
      v16 = CurrentIP();
      v17 = ConstructPartialMsgW(0x2000000, "Failed to get USN for file, error: 0x%08X", v5);
      WdsSetupLogMessageW(
        v17,
        0,
        L"D",
        0,
        484,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\utils.cpp",
        L"GetFileContentInfo",
        v16,
        v15,
        0,
        0);
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl);
    }
  }
  return wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) != 0
       ? v5
       : 0;
}

```

## disassembly

```asm
0x180035ca0  mov     r11, rsp
0x180035ca3  push    rbx
0x180035ca4  push    rbp
0x180035ca5  push    rsi
0x180035ca6  push    rdi
0x180035ca7  push    r14
0x180035ca9  sub     rsp, 80h
0x180035cb0  mov     rax, cs:__security_cookie
0x180035cb7  xor     rax, rsp
0x180035cba  mov     [rsp+0A8h+var_38], rax
0x180035cbf  xor     esi, esi
0x180035cc1  lea     rax, [r11-44h]
0x180035cc5  mov     [r11-70h], rsi
0x180035cc9  mov     r14, r9
0x180035ccc  mov     [r11-78h], rax
0x180035cd0  mov     rbp, rcx
0x180035cd3  mov     [r11-80h], r8d
0x180035cd7  lea     r8, [r11-40h]; lpInBuffer
0x180035cdb  mov     [rsp+0A8h+lpOutBuffer], rdx; lpOutBuffer
0x180035ce0  lea     r9d, [rsi+8]; nInBufferSize
0x180035ce4  mov     edx, 90073h; dwIoControlCode
0x180035ce9  mov     [r11-40h], rsi
0x180035ced  mov     [rsp+0A8h+BytesReturned], esi
0x180035cf1  mov     [rsp+0A8h+InBuffer], esi
0x180035cf5  call    cs:__imp_DeviceIoControl
0x180035cfb  test    eax, eax
0x180035cfd  jnz     loc_180035DAB
0x180035d03  call    cs:__imp_GetLastError
0x180035d09  cmp     eax, 26h ; '&'
0x180035d0c  jz      loc_180035DAB
0x180035d12  test    eax, eax
0x180035d14  jg      short loc_180035D1A
0x180035d16  mov     esi, eax
0x180035d18  jmp     short loc_180035D23
0x180035d1a  movzx   esi, ax
0x180035d1d  or      esi, 80070000h
0x180035d23  call    cs:__imp_GetLastError
0x180035d29  mov     edi, eax
0x180035d2b  call    cs:__imp_CurrentIP
0x180035d31  mov     r8d, esi
0x180035d34  lea     rdx, aFailedToGetExt_0; "Failed to get extends for file, error: "...
0x180035d3b  mov     ecx, 2000000h; unsigned int
0x180035d40  mov     rbx, rax
0x180035d43  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180035d48  mov     [rsp+0A8h+var_58], 0
0x180035d50  lea     rcx, aGetfilecontent; "GetFileContentInfo"
0x180035d57  mov     [rsp+0A8h+var_60], 0
0x180035d60  lea     r8, aD; "D"
0x180035d67  mov     [rsp+0A8h+var_68], edi
0x180035d6b  xor     r9d, r9d
0x180035d6e  mov     [rsp+0A8h+lpOverlapped], rbx
0x180035d73  xor     edx, edx
0x180035d75  mov     [rsp+0A8h+lpBytesReturned], rcx
0x180035d7a  lea     rcx, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\pitr\\dll\\src\\u"...
0x180035d81  mov     qword ptr [rsp+0A8h+nOutBufferSize], rcx
0x180035d86  mov     rcx, rax
0x180035d89  mov     dword ptr [rsp+0A8h+lpOutBuffer], 1CEh
0x180035d91  call    cs:__imp_WdsSetupLogMessageW
0x180035d97  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180035d9e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180035da3  test    al, al
0x180035da5  jnz     loc_180035EA9
0x180035dab  lea     rax, [rsp+0A8h+BytesReturned]
0x180035db0  mov     [rsp+0A8h+lpOverlapped], 0; lpOverlapped
0x180035db9  mov     [rsp+0A8h+lpBytesReturned], rax; lpBytesReturned
0x180035dbe  lea     r8, [rsp+0A8h+InBuffer]; lpInBuffer
0x180035dc3  mov     eax, [rsp+0A8h+arg_20]
0x180035dca  mov     r9d, 4; nInBufferSize
0x180035dd0  mov     [rsp+0A8h+nOutBufferSize], eax; nOutBufferSize
0x180035dd4  mov     edx, 900EBh; dwIoControlCode
0x180035dd9  mov     rcx, rbp; hDevice
0x180035ddc  mov     [rsp+0A8h+lpOutBuffer], r14; lpOutBuffer
0x180035de1  mov     [rsp+0A8h+InBuffer], 30002h
0x180035de9  call    cs:__imp_DeviceIoControl
0x180035def  test    eax, eax
0x180035df1  jnz     loc_180035EA9
0x180035df7  call    cs:__imp_GetLastError
0x180035dfd  test    eax, eax
0x180035dff  jle     short loc_180035E0B
0x180035e01  movzx   eax, ax
0x180035e04  or      eax, 80070000h
0x180035e09  test    eax, eax
0x180035e0b  jns     short loc_180035E24
0x180035e0d  call    cs:__imp_GetLastError
0x180035e13  mov     esi, eax
0x180035e15  test    eax, eax
0x180035e17  jle     short loc_180035E29
0x180035e19  movzx   esi, ax
0x180035e1c  or      esi, 80070000h
0x180035e22  jmp     short loc_180035E29
0x180035e24  mov     esi, 80004005h
0x180035e29  call    cs:__imp_GetLastError
0x180035e2f  mov     edi, eax
0x180035e31  call    cs:__imp_CurrentIP
0x180035e37  mov     r8d, esi
0x180035e3a  lea     rdx, aFailedToGetUsn; "Failed to get USN for file, error: 0x%0"...
0x180035e41  mov     ecx, 2000000h; unsigned int
0x180035e46  mov     rbx, rax
0x180035e49  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180035e4e  mov     [rsp+0A8h+var_58], 0
0x180035e56  lea     rcx, aGetfilecontent; "GetFileContentInfo"
0x180035e5d  mov     [rsp+0A8h+var_60], 0
0x180035e66  lea     r8, aD; "D"
0x180035e6d  mov     [rsp+0A8h+var_68], edi
0x180035e71  xor     r9d, r9d
0x180035e74  mov     [rsp+0A8h+lpOverlapped], rbx
0x180035e79  xor     edx, edx
0x180035e7b  mov     [rsp+0A8h+lpBytesReturned], rcx
0x180035e80  lea     rcx, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\pitr\\dll\\src\\u"...
0x180035e87  mov     qword ptr [rsp+0A8h+nOutBufferSize], rcx
0x180035e8c  mov     rcx, rax
0x180035e8f  mov     dword ptr [rsp+0A8h+lpOutBuffer], 1E4h
0x180035e97  call    cs:__imp_WdsSetupLogMessageW
0x180035e9d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180035ea4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180035ea9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180035eb0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180035eb5  neg     al
0x180035eb7  sbb     eax, eax
0x180035eb9  and     eax, esi
0x180035ebb  mov     rcx, [rsp+0A8h+var_38]
0x180035ec0  xor     rcx, rsp; StackCookie
0x180035ec3  call    __security_check_cookie
0x180035ec8  add     rsp, 80h
0x180035ecf  pop     r14
0x180035ed1  pop     rdi
0x180035ed2  pop     rsi
0x180035ed3  pop     rbp
0x180035ed4  pop     rbx
0x180035ed5  retn
```
