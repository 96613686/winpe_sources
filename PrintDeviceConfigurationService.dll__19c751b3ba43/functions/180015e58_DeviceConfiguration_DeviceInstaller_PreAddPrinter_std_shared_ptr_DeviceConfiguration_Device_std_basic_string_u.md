# DeviceConfiguration::DeviceInstaller::_PreAddPrinter(std::shared_ptr<DeviceConfiguration::Device>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180015e58`
- end: `0x1800160ba`
- name: `?_PreAddPrinter@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z`
- size: `610`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x180014e28`

## callees

- `0x1800020c0`
- `0x18000af54`
- `0x18000d868`
- `0x18000f9ec`
- `0x180011510`
- `0x1800115a0`
- `0x180011610`
- `0x180011b6c`
- `0x1800146a0`
- `0x1800146c4`
- `0x180014d38`
- `0x1800153bc`
- `0x18001596c`
- `0x180015e58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fdd`
- `WINSPOOL!EnumPortsW` at `0x180015fcf`
- `WINSPOOL!EnumPortsW` at `0x180016019`
- `WINSPOOL!EnumPortsW` at `0x180015fcf`
- `WINSPOOL!EnumPortsW` at `0x180016019`

## string_xrefs

- `0x180015f01`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x180016039`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x180016072`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_PreAddPrinter(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 PrinterName; // rbx
  char v6; // al
  __int64 v7; // rax
  __int64 v8; // rcx
  char IsPrinterNameUnique; // bl
  __int64 v10; // rax
  __int64 v11; // rcx
  bool v12; // bl
  BOOL v13; // eax
  const char *v14; // r9
  std::_Ref_count_base *v15; // rcx
  __int64 result; // rax
  std::_Ref_count_base *v17; // rcx
  const char *pcbNeeded; // [rsp+20h] [rbp-58h]
  const char *pcReturned; // [rsp+28h] [rbp-50h]
  const char *cbBuf; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-40h]
  LPBYTE pPort[4]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v21 = a2;
  try
  {
    PrinterName = DeviceConfiguration::Device::GetPrinterName(*a2, pPort);
    v6 = std::wstring::find(PrinterName, L",") != -1
      || std::wstring::find(PrinterName, L"\\") != -1
      || std::wstring::find(PrinterName, L"!") != -1
      || !*(_QWORD *)(PrinterName + 16)
      || *(_QWORD *)(PrinterName + 16) == 520;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x4B,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)0x80070709LL,
      v6,
      (bool)"Invalid printer name!",
      cbBuf);
    std::wstring::_Tidy_deallocate(pPort);
    v7 = DeviceConfiguration::Device::GetPrinterName(*a2, pPort);
    IsPrinterNameUnique = DeviceConfiguration::DeviceInstaller::_IsPrinterNameUnique(v8, v7, 0, 0);
    std::wstring::_Tidy_deallocate(pPort);
    if ( !IsPrinterNameUnique )
    {
      v10 = DeviceConfiguration::Device::GetPrinterName(*a2, pPort);
      DeviceConfiguration::DeviceInstaller::_CreateUniquePrinterName(v11, v10, a3);
      std::wstring::_Tidy_deallocate(pPort);
    }
    v12 = *(_QWORD *)(DeviceConfiguration::Device::GetUserSid(*a2, pPort) + 16) != 0;
    std::wstring::_Tidy_deallocate(pPort);
    if ( v12 )
      *(_DWORD *)(*a2 + 260LL) |= 0x400040u;
    cbBuf = 0;
    if ( EnumPortsW(0, 2u, 0, 0, (LPDWORD)&cbBuf, (LPDWORD)&cbBuf + 1) || GetLastError() != 122 )
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0x66,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
        "EnumPorts (no buffer) failed!",
        pcbNeeded);
    std::vector<unsigned char>::vector<unsigned char>(pPort, (unsigned int)cbBuf);
    v13 = EnumPortsW(0, 2u, pPort[0], (DWORD)cbBuf, (LPDWORD)&cbBuf, (LPDWORD)&cbBuf + 1);
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x62,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)!v13,
      (bool)"EnumPorts (with buffer) failed!",
      pcReturned);
    std::vector<unsigned char>::_Tidy(pPort);
    v15 = (std::_Ref_count_base *)a2[1];
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    result = 0;
  }
  catch ( ... )
  {
    HIDWORD(cbBuf) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x6B,
                       (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
                       v14);
    v17 = (std::_Ref_count_base *)v21[1];
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    return HIDWORD(cbBuf);
  }
  return result;
}

```

## disassembly

```asm
0x180015e58  mov     r11, rsp
0x180015e5b  mov     [r11+8], rbx
0x180015e5f  mov     [r11+20h], rsi
0x180015e63  push    rdi
0x180015e64  sub     rsp, 70h
0x180015e68  mov     rax, cs:__security_cookie
0x180015e6f  xor     rax, rsp
0x180015e72  mov     [rsp+78h+var_18], rax
0x180015e77  mov     rsi, r8
0x180015e7a  mov     rdi, rdx
0x180015e7d  mov     [r11-40h], rdx
0x180015e81  lea     rdx, [r11-38h]
0x180015e85  mov     rcx, [rdi]
0x180015e88  call    ?GetPrinterName@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetPrinterName(void)
0x180015e8d  mov     rbx, rax
0x180015e90  lea     rdx, asc_18001EAE4; ","
0x180015e97  mov     rcx, rax
0x180015e9a  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180015e9f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015ea3  jnz     short loc_180015EE4
0x180015ea5  lea     rdx, asc_180019E7C; "\\"
0x180015eac  mov     rcx, rbx
0x180015eaf  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180015eb4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015eb8  jnz     short loc_180015EE4
0x180015eba  lea     rdx, asc_18001E8A0; "!"
0x180015ec1  mov     rcx, rbx
0x180015ec4  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180015ec9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015ecd  jnz     short loc_180015EE4
0x180015ecf  cmp     qword ptr [rbx+10h], 0
0x180015ed4  jz      short loc_180015EE4
0x180015ed6  cmp     qword ptr [rbx+10h], 208h
0x180015ede  jz      short loc_180015EE4
0x180015ee0  xor     al, al
0x180015ee2  jmp     short loc_180015EE6
0x180015ee4  mov     al, 1
0x180015ee6  mov     rcx, [rsp+78h]; this
0x180015eeb  lea     rdx, aInvalidPrinter; "Invalid printer name!"
0x180015ef2  mov     [rsp+78h+pcReturned], rdx; bool
0x180015ef7  mov     byte ptr [rsp+78h+pcbNeeded], al; char
0x180015efb  mov     r9d, 80070709h; char *
0x180015f01  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015f08  mov     edx, 4Bh ; 'K'; void *
0x180015f0d  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015f12  nop
0x180015f13  lea     rcx, [rsp+78h+pPort]
0x180015f18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015f1d  lea     rdx, [rsp+78h+pPort]
0x180015f22  mov     rcx, [rdi]
0x180015f25  call    ?GetPrinterName@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetPrinterName(void)
0x180015f2a  nop
0x180015f2b  xor     r9d, r9d
0x180015f2e  xor     r8d, r8d
0x180015f31  mov     rdx, rax
0x180015f34  call    ?_IsPrinterNameUnique@DeviceInstaller@DeviceConfiguration@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEAU_PRINTER_INFO_2W@@@Z; DeviceConfiguration::DeviceInstaller::_IsPrinterNameUnique(std::wstring const &,ulong,_PRINTER_INFO_2W *)
0x180015f39  mov     bl, al
0x180015f3b  lea     rcx, [rsp+78h+pPort]
0x180015f40  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015f45  test    bl, bl
0x180015f47  jnz     short loc_180015F6D
0x180015f49  lea     rdx, [rsp+78h+pPort]
0x180015f4e  mov     rcx, [rdi]
0x180015f51  call    ?GetPrinterName@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetPrinterName(void)
0x180015f56  nop
0x180015f57  mov     r8, rsi
0x180015f5a  mov     rdx, rax
0x180015f5d  call    ?_CreateUniquePrinterName@DeviceInstaller@DeviceConfiguration@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; DeviceConfiguration::DeviceInstaller::_CreateUniquePrinterName(std::wstring const &,std::wstring &)
0x180015f62  nop
0x180015f63  lea     rcx, [rsp+78h+pPort]
0x180015f68  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015f6d  lea     rdx, [rsp+78h+pPort]
0x180015f72  mov     rcx, [rdi]
0x180015f75  call    ?GetUserSid@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetUserSid(void)
0x180015f7a  cmp     qword ptr [rax+10h], 0
0x180015f7f  setnz   bl
0x180015f82  lea     rcx, [rsp+78h+pPort]
0x180015f87  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015f8c  test    bl, bl
0x180015f8e  jz      short loc_180015F9D
0x180015f90  mov     rax, [rdi]
0x180015f93  or      dword ptr [rax+104h], 400040h
0x180015f9d  mov     [rsp+78h+cbBuf], 0
0x180015fa5  mov     [rsp+78h+var_44], 0
0x180015fad  lea     rax, [rsp+78h+var_44]
0x180015fb2  mov     [rsp+78h+pcReturned], rax; pcReturned
0x180015fb7  lea     rax, [rsp+78h+cbBuf]
0x180015fbc  mov     [rsp+78h+pcbNeeded], rax; char *
0x180015fc1  xor     r9d, r9d; cbBuf
0x180015fc4  xor     r8d, r8d; pPort
0x180015fc7  lea     ebx, [r9+2]
0x180015fcb  mov     edx, ebx; Level
0x180015fcd  xor     ecx, ecx; pName
0x180015fcf  call    cs:__imp_EnumPortsW
0x180015fd5  test    eax, eax
0x180015fd7  jnz     loc_180016066
0x180015fdd  call    cs:__imp_GetLastError
0x180015fe3  cmp     eax, 7Ah ; 'z'
0x180015fe6  jnz     short loc_180016066
0x180015fe8  mov     edx, [rsp+78h+cbBuf]
0x180015fec  lea     rcx, [rsp+78h+pPort]
0x180015ff1  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180015ff6  nop
0x180015ff7  lea     rax, [rsp+78h+var_44]
0x180015ffc  mov     [rsp+78h+pcReturned], rax; char *
0x180016001  lea     rax, [rsp+78h+cbBuf]
0x180016006  mov     [rsp+78h+pcbNeeded], rax; pcbNeeded
0x18001600b  mov     r9d, [rsp+78h+cbBuf]; cbBuf
0x180016010  mov     r8, [rsp+78h+pPort]; pPort
0x180016015  mov     edx, ebx; Level
0x180016017  xor     ecx, ecx; pName
0x180016019  call    cs:__imp_EnumPortsW
0x18001601f  test    eax, eax
0x180016021  setz    al
0x180016024  mov     rcx, [rsp+78h]; this
0x180016029  lea     rdx, aEnumportsWithB; "EnumPorts (with buffer) failed!"
0x180016030  mov     [rsp+78h+pcbNeeded], rdx; bool
0x180016035  movzx   r9d, al; char *
0x180016039  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180016040  lea     edx, [rbx+60h]; void *
0x180016043  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180016048  nop
0x180016049  lea     rcx, [rsp+78h+pPort]
0x18001604e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180016053  nop
0x180016054  mov     rcx, [rdi+8]; this
0x180016058  test    rcx, rcx
0x18001605b  jz      short loc_180016062
0x18001605d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016062  xor     eax, eax
0x180016064  jmp     short loc_18001609B
0x180016066  mov     rcx, [rsp+78h]; this
0x18001606b  lea     r9, aEnumportsNoBuf; "EnumPorts (no buffer) failed!"
0x180016072  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180016079  mov     edx, 66h ; 'f'; void *
0x18001607e  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180016084  mov     rax, [rsp+78h+var_40]
0x180016089  mov     rcx, [rax+8]; this
0x18001608d  test    rcx, rcx
0x180016090  jz      short loc_180016097
0x180016092  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016097  mov     eax, [rsp+78h+var_44]
0x18001609b  mov     rcx, [rsp+78h+var_18]
0x1800160a0  xor     rcx, rsp; StackCookie
0x1800160a3  call    __security_check_cookie
0x1800160a8  lea     r11, [rsp+78h+var_8]
0x1800160ad  mov     rbx, [r11+10h]
0x1800160b1  mov     rsi, [r11+28h]
0x1800160b5  mov     rsp, r11
0x1800160b8  pop     rdi
0x1800160b9  retn
```
