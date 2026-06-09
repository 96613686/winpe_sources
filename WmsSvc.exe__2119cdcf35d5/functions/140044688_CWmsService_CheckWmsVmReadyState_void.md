# CWmsService::CheckWmsVmReadyState(void)

- ea: `0x140044688`
- end: `0x140044938`
- name: `?CheckWmsVmReadyState@CWmsService@@AEAAJXZ`
- size: `688`
- prototype: `__int64 __fastcall(CWmsService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140045b90`

## callees

- `0x140044688`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140044853`
- `ADVAPI32!RegOpenKeyExW` at `0x140044853`
- `ADVAPI32!RegGetValueW` at `0x140044703`
- `ADVAPI32!RegGetValueW` at `0x1400447ee`
- `ADVAPI32!RegGetValueW` at `0x140044703`
- `ADVAPI32!RegGetValueW` at `0x1400447ee`
- `ADVAPI32!RegCloseKey` at `0x140044921`
- `ADVAPI32!RegCloseKey` at `0x140044921`
- `ADVAPI32!RegSetValueExW` at `0x140044881`
- `ADVAPI32!RegSetValueExW` at `0x140044881`
- `KERNEL32!IsDebuggerPresent` at `0x140044763`
- `KERNEL32!IsDebuggerPresent` at `0x1400448da`
- `KERNEL32!IsDebuggerPresent` at `0x140044763`
- `KERNEL32!IsDebuggerPresent` at `0x1400448da`

## string_xrefs

- `0x14004486f`: `VMReady`
- `0x140044742`: `termsrv\wms\src\devices\wmssvc\wmsservice.cpp`
- `0x1400448b6`: `termsrv\wms\src\devices\wmssvc\wmsservice.cpp`
- `0x14004472d`: `CWmsService::CheckWmsVmReadyState`
- `0x1400448a9`: `CWmsService::CheckWmsVmReadyState`
- `0x1400447b0`: `CWmsService::CheckWmsVmReadyState - SysPrep GeneralizationState %lu\n`
- `0x140044816`: `CWmsService::CheckWmsVmReadyState - StationVirtualMachine %lu\n`

## pseudocode

```c
__int64 __fastcall CWmsService::CheckWmsVmReadyState(CWmsService *this)
{
  LSTATUS ValueW; // eax
  unsigned int v2; // ebx
  unsigned int v3; // r13d
  LSTATUS v4; // eax
  int v5; // eax
  LSTATUS v6; // eax
  LPDWORD pcbData; // [rsp+30h] [rbp-20h]
  DWORD v9; // [rsp+40h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v11; // [rsp+90h] [rbp+40h] BYREF
  int v12; // [rsp+94h] [rbp+44h]
  unsigned int pvData; // [rsp+98h] [rbp+48h] BYREF
  DWORD v14; // [rsp+A0h] [rbp+50h] BYREF
  int Data; // [rsp+A8h] [rbp+58h] BYREF

  v12 = HIDWORD(this);
  pvData = 0;
  v14 = 0;
  v11 = 0;
  Data = 0;
  phkResult = 0;
  v9 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\Setup\\Status\\SysprepStatus",
             L"GeneralizationState",
             0x10u,
             0,
             &pvData,
             &v9);
  v2 = ValueW;
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    if ( ValueW > 0 )
      v2 = (unsigned __int16)ValueW | 0x80070000;
    v3 = 328;
LABEL_5:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
      v3,
      L"CWmsService::CheckWmsVmReadyState",
      L"CBRAEx",
      L"(lr == 0L) || (lr == 2L)",
      v2);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
        v3,
        L"CWmsService::CheckWmsVmReadyState",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        v2);
    }
    else
    {
      LODWORD(pcbData) = v2;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
        v3,
        L"CWmsService::CheckWmsVmReadyState",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        pcbData);
    }
    goto LABEL_24;
  }
  DEBUGMSG(L"CWmsService::CheckWmsVmReadyState - SysPrep GeneralizationState %lu\n", pvData);
  v14 = 4;
  v4 = RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows MultiPoint Server",
         L"StationVirtualMachine",
         0x10u,
         0,
         &v11,
         &v14);
  v2 = v4;
  if ( (v4 & 0xFFFFFFFD) != 0 )
  {
    if ( v4 > 0 )
      v2 = (unsigned __int16)v4 | 0x80070000;
    v3 = 334;
    goto LABEL_5;
  }
  DEBUGMSG(L"CWmsService::CheckWmsVmReadyState - StationVirtualMachine %lu\n", v11);
  v5 = 1;
  if ( v11 != 1 || pvData != 7 )
    v5 = 0;
  Data = v5;
  v2 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\Guest", 0, 0x20006u, &phkResult) )
  {
    v6 = RegSetValueExW(phkResult, L"VMReady", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v6 )
    {
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
      else
        v2 = v6;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
        0x159u,
        L"CWmsService::CheckWmsVmReadyState",
        L"CBRAEx",
        L"lr == 0L",
        v2);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
          345,
          L"CWmsService::CheckWmsVmReadyState",
          L"CBRAEx",
          L"lr == 0L",
          v2);
      }
      else
      {
        LODWORD(pcbData) = v2;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
          345,
          L"CWmsService::CheckWmsVmReadyState",
          L"CBRAEx",
          L"lr == 0L",
          pcbData);
      }
    }
  }
LABEL_24:
  if ( phkResult )
    RegCloseKey(phkResult);
  return v2;
}

```

## disassembly

```asm
0x140044688  mov     r11, rsp
0x14004468b  mov     [r11+8], rcx
0x14004468f  push    rbp
0x140044690  push    rbx
0x140044691  push    rsi
0x140044692  push    rdi
0x140044693  push    r13
0x140044695  push    r14
0x140044697  push    r15
0x140044699  mov     rbp, rsp
0x14004469c  sub     rsp, 50h
0x1400446a0  mov     edi, 4
0x1400446a5  mov     [rbp+arg_8], 0
0x1400446ac  lea     rax, [rbp+var_10]
0x1400446b0  mov     [rbp+arg_10], 0
0x1400446b7  mov     [r11-58h], rax
0x1400446bb  lea     r8, aGeneralization; "GeneralizationState"
0x1400446c2  lea     rax, [rbp+arg_8]
0x1400446c6  mov     [rbp+arg_0], 0
0x1400446cd  mov     [r11-60h], rax
0x1400446d1  lea     r14d, [rdi+0Ch]
0x1400446d5  mov     rsi, 0FFFFFFFF80000002h
0x1400446dc  mov     [rbp+Data], 0
0x1400446e3  mov     r9d, r14d; dwFlags
0x1400446e6  mov     [rbp+phkResult], 0
0x1400446ee  lea     rdx, aSystemSetupSta; "SYSTEM\\Setup\\Status\\SysprepStatus"
0x1400446f5  mov     [rbp+var_10], edi
0x1400446f8  mov     rcx, rsi; hkey
0x1400446fb  mov     qword ptr [r11-68h], 0
0x140044703  call    cs:__imp_RegGetValueW
0x140044709  mov     r15d, 0FFFFFFFDh
0x14004470f  mov     ebx, eax
0x140044711  test    r15d, eax
0x140044714  jz      loc_1400447AD
0x14004471a  test    eax, eax
0x14004471c  jle     short loc_140044727
0x14004471e  movzx   ebx, ax
0x140044721  or      ebx, 80070000h
0x140044727  mov     r13d, 148h
0x14004472d  lea     rsi, aCwmsserviceChe_0; "CWmsService::CheckWmsVmReadyState"
0x140044734  mov     dword ptr [rsp+50h+pvData], ebx; int
0x140044738  lea     r14, aCbraex; "CBRAEx"
0x14004473f  mov     r8, rsi; unsigned __int16 *
0x140044742  lea     rdi, aTermsrvWmsSrcD_6; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140044749  mov     r9, r14; unsigned __int16 *
0x14004474c  lea     r15, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x140044753  mov     rcx, rdi; unsigned __int16 *
0x140044756  mov     edx, r13d; unsigned int
0x140044759  mov     [rsp+50h+pdwType], r15; unsigned __int16 *
0x14004475e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140044763  call    cs:__imp_IsDebuggerPresent
0x140044769  test    eax, eax
0x14004476b  jz      short loc_14004479C
0x14004476d  mov     [rsp+50h+var_18], ebx
0x140044771  mov     r9d, r13d
0x140044774  mov     [rsp+50h+pcbData], r15
0x140044779  mov     [rsp+50h+pvData], r14
0x14004477e  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140044785  mov     r8, rdi
0x140044788  mov     [rsp+50h+pdwType], rsi
0x14004478d  mov     ecx, 2; unsigned __int8
0x140044792  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140044797  jmp     loc_140044918
0x14004479c  mov     dword ptr [rsp+50h+pcbData], ebx
0x1400447a0  mov     r8d, r13d
0x1400447a3  mov     [rsp+50h+pvData], r15
0x1400447a8  jmp     loc_140044901
0x1400447ad  mov     edx, [rbp+arg_8]
0x1400447b0  lea     rcx, aCwmsserviceChe_1; "CWmsService::CheckWmsVmReadyState - Sys"...
0x1400447b7  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400447bc  lea     rax, [rbp+arg_10]
0x1400447c0  mov     [rbp+arg_10], edi
0x1400447c3  mov     [rsp+50h+pcbData], rax; pcbData
0x1400447c8  lea     r8, aStationvirtual; "StationVirtualMachine"
0x1400447cf  lea     rax, [rbp+arg_0]
0x1400447d3  mov     r9d, r14d; dwFlags
0x1400447d6  mov     [rsp+50h+pvData], rax; pvData
0x1400447db  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows MultiPoint"...
0x1400447e2  mov     rcx, rsi; hkey
0x1400447e5  mov     [rsp+50h+pdwType], 0; pdwType
0x1400447ee  call    cs:__imp_RegGetValueW
0x1400447f4  mov     ebx, eax
0x1400447f6  test    r15d, eax
0x1400447f9  jz      short loc_140044813
0x1400447fb  test    eax, eax
0x1400447fd  jle     short loc_140044808
0x1400447ff  movzx   ebx, ax
0x140044802  or      ebx, 80070000h
0x140044808  mov     r13d, 14Eh
0x14004480e  jmp     loc_14004472D
0x140044813  mov     edx, [rbp+arg_0]
0x140044816  lea     rcx, aCwmsserviceChe; "CWmsService::CheckWmsVmReadyState - Sta"...
0x14004481d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140044822  mov     eax, 1
0x140044827  cmp     [rbp+arg_0], eax
0x14004482a  jnz     short loc_140044832
0x14004482c  cmp     [rbp+arg_8], 7
0x140044830  jz      short loc_140044834
0x140044832  xor     eax, eax
0x140044834  mov     [rbp+Data], eax
0x140044837  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Virtual Machine\\G"...
0x14004483e  lea     rax, [rbp+phkResult]
0x140044842  mov     r9d, 20006h; samDesired
0x140044848  xor     r8d, r8d; ulOptions
0x14004484b  mov     [rsp+50h+pdwType], rax; phkResult
0x140044850  mov     rcx, rsi; hKey
0x140044853  call    cs:__imp_RegOpenKeyExW
0x140044859  xor     ebx, ebx
0x14004485b  test    eax, eax
0x14004485d  jnz     loc_140044918
0x140044863  mov     rcx, [rbp+phkResult]; hKey
0x140044867  lea     rax, [rbp+Data]
0x14004486b  mov     dword ptr [rsp+50h+pvData], edi; cbData
0x14004486f  lea     rdx, aVmready; "VMReady"
0x140044876  mov     r9d, edi; dwType
0x140044879  mov     [rsp+50h+pdwType], rax; lpData
0x14004487e  xor     r8d, r8d; Reserved
0x140044881  call    cs:__imp_RegSetValueExW
0x140044887  test    eax, eax
0x140044889  jz      loc_140044918
0x14004488f  jg      short loc_140044895
0x140044891  mov     ebx, eax
0x140044893  jmp     short loc_14004489E
0x140044895  movzx   ebx, ax
0x140044898  or      ebx, 80070000h
0x14004489e  lea     r14, aCbraex; "CBRAEx"
0x1400448a5  mov     dword ptr [rsp+50h+pvData], ebx; int
0x1400448a9  lea     rsi, aCwmsserviceChe_0; "CWmsService::CheckWmsVmReadyState"
0x1400448b0  mov     r15d, 159h
0x1400448b6  lea     rdi, aTermsrvWmsSrcD_6; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x1400448bd  mov     r9, r14; unsigned __int16 *
0x1400448c0  lea     r13, aLr0l; "lr == 0L"
0x1400448c7  mov     r8, rsi; unsigned __int16 *
0x1400448ca  mov     edx, r15d; unsigned int
0x1400448cd  mov     [rsp+50h+pdwType], r13; unsigned __int16 *
0x1400448d2  mov     rcx, rdi; unsigned __int16 *
0x1400448d5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400448da  call    cs:__imp_IsDebuggerPresent
0x1400448e0  test    eax, eax
0x1400448e2  jz      short loc_1400448F5
0x1400448e4  mov     [rsp+50h+var_18], ebx
0x1400448e8  mov     r9d, r15d
0x1400448eb  mov     [rsp+50h+pcbData], r13
0x1400448f0  jmp     loc_140044779
0x1400448f5  mov     dword ptr [rsp+50h+pcbData], ebx
0x1400448f9  mov     r8d, r15d
0x1400448fc  mov     [rsp+50h+pvData], r13
0x140044901  mov     r9, rsi
0x140044904  mov     [rsp+50h+pdwType], r14
0x140044909  mov     rdx, rdi
0x14004490c  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140044913  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140044918  mov     rcx, [rbp+phkResult]; hKey
0x14004491c  test    rcx, rcx
0x14004491f  jz      short loc_140044927
0x140044921  call    cs:__imp_RegCloseKey
0x140044927  mov     eax, ebx
0x140044929  add     rsp, 50h
0x14004492d  pop     r15
0x14004492f  pop     r14
0x140044931  pop     r13
0x140044933  pop     rdi
0x140044934  pop     rsi
0x140044935  pop     rbx
0x140044936  pop     rbp
0x140044937  retn
```
