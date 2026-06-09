# WinREAgent::UpdateWinREHash(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x1800361f4`
- end: `0x18003642c`
- name: `?UpdateWinREHash@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `568`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18002a950`
- `0x18002abac`

## callees

- `0x180005c00`
- `0x180005cc0`
- `0x18000d6f0`
- `0x18000d900`
- `0x1800361f4`
- `0x18003717c`
- `0x180037344`
- `0x180054b24`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800362b0`
- `KERNEL32!LoadLibraryExW` at `0x1800362b0`
- `KERNEL32!GetProcAddress` at `0x180036354`
- `KERNEL32!GetProcAddress` at `0x180036354`
- `KERNEL32!GetLastError` at `0x1800362d2`
- `KERNEL32!GetLastError` at `0x180036314`
- `KERNEL32!GetLastError` at `0x180036362`
- `KERNEL32!GetLastError` at `0x1800363b2`
- `KERNEL32!GetLastError` at `0x1800362d2`
- `KERNEL32!GetLastError` at `0x180036314`
- `KERNEL32!GetLastError` at `0x180036362`
- `KERNEL32!GetLastError` at `0x1800363b2`

## string_xrefs

- `0x1800362a9`: `ReAgent.dll`
- `0x1800362e6`: `Failed to load ReAgent.dll`
- `0x180036376`: `Failed to load function from DLL`
- `0x180036285`: `base\diagnosis\srt\winreagent\lib\api\src\validation.cpp`
- `0x1800362fa`: `base\diagnosis\srt\winreagent\lib\api\src\validation.cpp`
- `0x18003621a`: `Update WinRE hash to config`
- `0x18003628c`: `WinREAgent::UpdateWinREHash`
- `0x180036301`: `WinREAgent::UpdateWinREHash`
- `0x18003634d`: `WinREUpdateWinREHash`
- `0x1800363c6`: `Failed to call WinREUpdateWinREHash`
- `0x1800363df`: `WinRE hash updated successfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WinREAgent::UpdateWinREHash(_QWORD *a1)
{
  __int64 v2; // rax
  int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  unsigned int v6; // edi
  HMODULE v7; // rax
  FARPROC ProcAddress; // rdi
  signed int v9; // eax
  __int64 v10; // rax
  signed int v11; // eax
  unsigned int v13; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14[2]; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v15[2]; // [rsp+48h] [rbp-18h] BYREF

  PushButtonReset::Logging::Trace(0, L"Update WinRE hash to config");
  PushButtonReset::Logging::Trace(0, L"Encoded hash: [%s]", *a1);
  v15[1] = 0;
  v15[0] = &RAII::CAutoPbrHeapFree<unsigned char *>::`vftable';
  v13 = 0;
  v2 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v15);
  v3 = PushButtonReset::Encode::DecodeBase64(a1, v2, &v13);
  if ( v3 >= 0 )
  {
    v14[1] = (__int64)LoadLibraryExW(L"ReAgent.dll", 0, 0);
    v14[0] = (__int64)&RAII::CAutoFreeLibrary::`vftable';
    if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(v14) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "WinREAgent::UpdateWinREHash",
        "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\validation.cpp",
        149,
        L"Failed to load ReAgent.dll");
    }
    else
    {
      v7 = (HMODULE)(*(__int64 (__fastcall **)(__int64 *))(v14[0] + 32))(v14);
      ProcAddress = GetProcAddress(v7, "WinREUpdateWinREHash");
      if ( ProcAddress )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD *))(v15[0] + 32LL))(v15);
        if ( ((unsigned int (__fastcall *)(__int64, _QWORD))ProcAddress)(v10, v13) )
        {
          PushButtonReset::Logging::Trace(0, L"WinRE hash updated successfully");
          v14[0] = (__int64)&RAII::CAutoFreeLibrary::`vftable';
          RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)v14);
          goto LABEL_19;
        }
        v11 = GetLastError();
        if ( v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v11,
          "WinREAgent::UpdateWinREHash",
          "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\validation.cpp",
          166,
          L"Failed to call WinREUpdateWinREHash");
      }
      else
      {
        v9 = GetLastError();
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v9,
          "WinREAgent::UpdateWinREHash",
          "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\validation.cpp",
          159,
          L"Failed to load function from DLL");
      }
    }
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v14[0] = (__int64)&RAII::CAutoFreeLibrary::`vftable';
    RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)v14);
    v3 = v6;
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v3,
      "WinREAgent::UpdateWinREHash",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\validation.cpp",
      143,
      L"Failed to decode hash");
  }
LABEL_19:
  v15[0] = &RAII::CAutoPbrHeapFree<unsigned char *>::`vftable';
  RAII::CAutoPbrHeapFree<unsigned short *>::Release(v15);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800361f4  mov     [rsp-18h+arg_8], rbx
0x1800361f9  mov     [rsp-18h+arg_10], rsi
0x1800361fe  push    rbp
0x1800361ff  push    rdi
0x180036200  push    r14
0x180036202  mov     rbp, rsp
0x180036205  sub     rsp, 60h
0x180036209  mov     rax, cs:__security_cookie
0x180036210  xor     rax, rsp
0x180036213  mov     [rbp+var_8], rax
0x180036217  mov     rbx, rcx
0x18003621a  lea     rdx, aUpdateWinreHas; "Update WinRE hash to config"
0x180036221  xor     ecx, ecx
0x180036223  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180036228  mov     r8, [rbx]
0x18003622b  lea     rdx, aEncodedHashS; "Encoded hash: [%s]"
0x180036232  xor     ecx, ecx
0x180036234  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180036239  mov     [rbp+var_10], 0
0x180036241  lea     r14, ??_7?$CAutoPbrHeapFree@PEAE@RAII@@6B@; const RAII::CAutoPbrHeapFree<uchar *>::`vftable'
0x180036248  mov     [rbp+var_18], r14
0x18003624c  mov     [rbp+var_30], 0
0x180036253  lea     rcx, [rbp+var_18]
0x180036257  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18003625c  mov     rdx, rax
0x18003625f  lea     r8, [rbp+var_30]
0x180036263  mov     rcx, rbx
0x180036266  call    ?DecodeBase64@Encode@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAEPEAK@Z; PushButtonReset::Encode::DecodeBase64(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uchar * *,ulong *)
0x18003626b  mov     ebx, eax
0x18003626d  test    eax, eax
0x18003626f  jns     short loc_1800362A4
0x180036271  lea     rax, aFailedToDecode_2; "Failed to decode hash"
0x180036278  mov     [rsp+60h+var_38], rax
0x18003627d  mov     [rsp+60h+var_40], 8Fh
0x180036285  lea     r9, aBaseDiagnosisS_13; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18003628c  lea     r8, aWinreagentUpda_1; "WinREAgent::UpdateWinREHash"
0x180036293  mov     edx, ebx
0x180036295  mov     ecx, 2
0x18003629a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003629f  jmp     loc_1800363FC
0x1800362a4  xor     r8d, r8d; dwFlags
0x1800362a7  xor     edx, edx; hFile
0x1800362a9  lea     rcx, LibFileName; "ReAgent.dll"
0x1800362b0  call    cs:__imp_LoadLibraryExW
0x1800362b6  mov     [rbp+var_20], rax
0x1800362ba  lea     rsi, ??_7CAutoFreeLibrary@RAII@@6B@; const RAII::CAutoFreeLibrary::`vftable'
0x1800362c1  mov     [rbp+var_28], rsi
0x1800362c5  lea     rcx, [rbp+var_28]
0x1800362c9  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x1800362ce  test    al, al
0x1800362d0  jz      short loc_180036339
0x1800362d2  call    cs:__imp_GetLastError
0x1800362d8  mov     ebx, 80070000h
0x1800362dd  test    eax, eax
0x1800362df  jle     short loc_1800362E6
0x1800362e1  movzx   eax, ax
0x1800362e4  or      eax, ebx
0x1800362e6  lea     rcx, aFailedToLoadRe; "Failed to load ReAgent.dll"
0x1800362ed  mov     [rsp+60h+var_38], rcx
0x1800362f2  mov     [rsp+60h+var_40], 95h
0x1800362fa  lea     r9, aBaseDiagnosisS_13; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180036301  lea     r8, aWinreagentUpda_1; "WinREAgent::UpdateWinREHash"
0x180036308  mov     edx, eax
0x18003630a  mov     ecx, 2
0x18003630f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180036314  call    cs:__imp_GetLastError
0x18003631a  test    eax, eax
0x18003631c  mov     edi, eax
0x18003631e  jle     short loc_180036325
0x180036320  movzx   edi, ax
0x180036323  or      edi, ebx
0x180036325  mov     [rbp+var_28], rsi
0x180036329  lea     rcx, [rbp+var_28]; this
0x18003632d  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x180036332  mov     ebx, edi
0x180036334  jmp     loc_1800363FC
0x180036339  mov     rax, [rbp+var_28]
0x18003633d  lea     rcx, [rbp+var_28]
0x180036341  mov     rax, [rax+20h]
0x180036345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003634a  mov     rcx, rax; hModule
0x18003634d  lea     rdx, aWinreupdatewin; "WinREUpdateWinREHash"
0x180036354  call    cs:__imp_GetProcAddress
0x18003635a  mov     rdi, rax
0x18003635d  test    rax, rax
0x180036360  jnz     short loc_18003638F
0x180036362  call    cs:__imp_GetLastError
0x180036368  mov     ebx, 80070000h
0x18003636d  test    eax, eax
0x18003636f  jle     short loc_180036376
0x180036371  movzx   eax, ax
0x180036374  or      eax, ebx
0x180036376  lea     rcx, aFailedToLoadFu; "Failed to load function from DLL"
0x18003637d  mov     [rsp+60h+var_38], rcx
0x180036382  mov     [rsp+60h+var_40], 9Fh
0x18003638a  jmp     loc_1800362FA
0x18003638f  mov     rax, [rbp+var_18]
0x180036393  lea     rcx, [rbp+var_18]
0x180036397  mov     rax, [rax+20h]
0x18003639b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363a0  mov     edx, [rbp+var_30]
0x1800363a3  mov     rcx, rax
0x1800363a6  mov     rax, rdi
0x1800363a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363ae  test    eax, eax
0x1800363b0  jnz     short loc_1800363DF
0x1800363b2  call    cs:__imp_GetLastError
0x1800363b8  mov     ebx, 80070000h
0x1800363bd  test    eax, eax
0x1800363bf  jle     short loc_1800363C6
0x1800363c1  movzx   eax, ax
0x1800363c4  or      eax, ebx
0x1800363c6  lea     rcx, aFailedToCallWi; "Failed to call WinREUpdateWinREHash"
0x1800363cd  mov     [rsp+60h+var_38], rcx
0x1800363d2  mov     [rsp+60h+var_40], 0A6h
0x1800363da  jmp     loc_1800362FA
0x1800363df  lea     rdx, aWinreHashUpdat; "WinRE hash updated successfully"
0x1800363e6  xor     ecx, ecx
0x1800363e8  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800363ed  nop
0x1800363ee  mov     [rbp+var_28], rsi
0x1800363f2  lea     rcx, [rbp+var_28]; this
0x1800363f6  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x1800363fb  nop
0x1800363fc  mov     [rbp+var_18], r14
0x180036400  lea     rcx, [rbp+var_18]
0x180036404  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180036409  mov     eax, ebx
0x18003640b  mov     rcx, [rbp+var_8]
0x18003640f  xor     rcx, rsp; StackCookie
0x180036412  call    __security_check_cookie
0x180036417  lea     r11, [rsp+60h+var_s0]
0x18003641c  mov     rbx, [r11+28h]
0x180036420  mov     rsi, [r11+30h]
0x180036424  mov     rsp, r11
0x180036427  pop     r14
0x180036429  pop     rdi
0x18003642a  pop     rbp
0x18003642b  retn
```
