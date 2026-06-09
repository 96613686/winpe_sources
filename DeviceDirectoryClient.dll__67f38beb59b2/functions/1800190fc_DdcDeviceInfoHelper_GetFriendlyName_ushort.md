# DdcDeviceInfoHelper::GetFriendlyName(ushort * *)

- ea: `0x1800190fc`
- end: `0x1800193f8`
- name: `?GetFriendlyName@DdcDeviceInfoHelper@@CAJPEAPEAG@Z`
- size: `764`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800183c4`

## callees

- `0x1800024c0`
- `0x1800028d4`
- `0x180002fc0`
- `0x180003288`
- `0x1800050b8`
- `0x1800190fc`
- `0x18001ab0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180019205`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180019205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019383`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001925e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180019379`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001925e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180019379`

## string_xrefs

- `0x180019175`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180019230`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x1800193b0`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001927c`: `CBR(!GetComputerNameExW(ComputerNamePhysicalDnsHostname, nullptr, &cchFriendlyName))`
- `0x1800193a1`: `CBR(GetComputerNameExW(ComputerNamePhysicalDnsHostname, pwszFriendlyName, &cchFriendlyName))`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DdcDeviceInfoHelper::GetFriendlyName(unsigned __int16 **a1)
{
  int v2; // edx
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // r8d
  unsigned int v6; // ebx
  unsigned __int64 v7; // rax
  WCHAR *v8; // rsi
  int v9; // edx
  int v10; // ecx
  signed int v11; // eax
  unsigned __int64 v12; // rax
  WCHAR *v13; // rax
  signed int LastError; // eax
  int v15; // edx
  int v16; // ecx
  char v18; // [rsp+20h] [rbp-438h]
  const char *v19; // [rsp+28h] [rbp-430h]
  DWORD nSize; // [rsp+30h] [rbp-428h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-420h] BYREF
  _BYTE v22[1024]; // [rsp+40h] [rbp-418h] BYREF

  nSize = 0;
  memset_0(v22, 0, sizeof(v22));
  v21 = 0;
  if ( a1 )
  {
    if ( *a1 )
    {
      v6 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v3,
          v2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          226,
          "CBR(*ppwszFriendlyName == nullptr)");
      return v6;
    }
    v6 = DdcDeviceInfoHelper::QueryPhoneInformationWrapper(v3, v22, v4, &v21);
    if ( (v6 & 0x80000000) == 0 )
    {
      v7 = 2 * v21;
      if ( !is_mul_ok(v21, 2u) )
        v7 = -1;
      v8 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
      if ( (unsigned int)_o_wcscpy_s(v8, v21, v22) )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v10,
            v9,
            -2147418113,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
            233,
            "CBR(wcscpy_s(pwszFriendlyName, cchPhoneName, wszPhoneName) == 0)");
        v6 = -2147418113;
        if ( !v8 )
          return v6;
LABEL_40:
        operator delete(v8);
        return v6;
      }
      goto LABEL_41;
    }
    if ( GetComputerNameExW(ComputerNamePhysicalDnsHostname, 0, &nSize) )
    {
      v6 = -2147418113;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        return v6;
      v19 = "CBR(!GetComputerNameExW(ComputerNamePhysicalDnsHostname, nullptr, &cchFriendlyName))";
      v18 = -18;
LABEL_20:
      v5 = -2147418113;
      goto LABEL_4;
    }
    if ( GetLastError() == 234 )
    {
      if ( !nSize )
      {
        v6 = -2147418113;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          return v6;
        v19 = "CBR(cchFriendlyName > 0)";
        v18 = -16;
        goto LABEL_20;
      }
      v12 = 2LL * nSize;
      if ( !is_mul_ok(nSize, 2u) )
        v12 = -1;
      v13 = (WCHAR *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
      v8 = v13;
      if ( v13 )
      {
        if ( !GetComputerNameExW(ComputerNamePhysicalDnsHostname, v13, &nSize) )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v16,
              v15,
              v6,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              247,
              "CBR(GetComputerNameExW(ComputerNamePhysicalDnsHostname, pwszFriendlyName, &cchFriendlyName))");
          goto LABEL_40;
        }
LABEL_41:
        *a1 = v8;
        return v6;
      }
      v6 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        return v6;
      v19 = "CPR(pwszFriendlyName)";
      v18 = -12;
    }
    else
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        return v6;
      v19 = "CBR(GetLastError() == 234L)";
      v18 = -17;
    }
    v5 = v6;
    goto LABEL_4;
  }
  v5 = -2147024809;
  v6 = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v19 = "CPR(ppwszFriendlyName)";
    v18 = -31;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      v3,
      v2,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      v18,
      v19);
  }
  return v6;
}

```

## disassembly

```asm
0x1800190fc  mov     [rsp+arg_8], rbx
0x180019101  mov     [rsp+arg_10], rsi
0x180019106  push    rdi
0x180019107  sub     rsp, 450h
0x18001910e  mov     rax, cs:__security_cookie
0x180019115  xor     rax, rsp
0x180019118  mov     [rsp+458h+var_18], rax
0x180019120  mov     rdi, rcx
0x180019123  mov     [rsp+458h+nSize], 0
0x18001912b  lea     rcx, [rsp+458h+var_418]; void *
0x180019130  xor     edx, edx; Val
0x180019132  mov     r8d, 400h; Size
0x180019138  call    memset_0
0x18001913d  mov     [rsp+458h+var_420], 0
0x180019146  test    rdi, rdi
0x180019149  jnz     short loc_180019186
0x18001914b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019152  mov     r8d, 80070057h
0x180019158  mov     ebx, r8d
0x18001915b  jz      loc_1800193D1
0x180019161  lea     rax, aCprPpwszfriend; "CPR(ppwszFriendlyName)"
0x180019168  mov     [rsp+458h+var_430], rax
0x18001916d  mov     dword ptr [rsp+458h+var_438], 3E1h
0x180019175  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001917c  call    McTemplateU0dsqs_EventWriteTransfer
0x180019181  jmp     loc_1800193D1
0x180019186  cmp     qword ptr [rdi], 0
0x18001918a  jz      short loc_1800191B8
0x18001918c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019193  mov     r8d, 80070057h
0x180019199  mov     ebx, r8d
0x18001919c  jz      loc_1800193D1
0x1800191a2  lea     rax, aCbrPpwszfriend; "CBR(*ppwszFriendlyName == nullptr)"
0x1800191a9  mov     [rsp+458h+var_430], rax
0x1800191ae  mov     dword ptr [rsp+458h+var_438], 3E2h
0x1800191b6  jmp     short loc_180019175
0x1800191b8  lea     r9, [rsp+458h+var_420]
0x1800191bd  lea     rdx, [rsp+458h+var_418]
0x1800191c2  call    ?QueryPhoneInformationWrapper@DdcDeviceInfoHelper@@CAJW4_PHONE_INFORMATION_KEY@@PEAG_KPEA_K@Z; DdcDeviceInfoHelper::QueryPhoneInformationWrapper(_PHONE_INFORMATION_KEY,ushort *,unsigned __int64,unsigned __int64 *)
0x1800191c7  mov     ebx, eax
0x1800191c9  test    eax, eax
0x1800191cb  js      loc_180019254
0x1800191d1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800191d8  mov     eax, 2
0x1800191dd  mul     [rsp+458h+var_420]
0x1800191e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800191e9  cmovb   rax, rcx
0x1800191ed  mov     rcx, rax; unsigned __int64
0x1800191f0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800191f5  mov     rdx, [rsp+458h+var_420]
0x1800191fa  lea     r8, [rsp+458h+var_418]
0x1800191ff  mov     rcx, rax
0x180019202  mov     rsi, rax
0x180019205  call    cs:__imp__o_wcscpy_s
0x18001920b  test    eax, eax
0x18001920d  jz      loc_1800193CE
0x180019213  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001921a  mov     edi, 8000FFFFh
0x18001921f  jz      short loc_180019244
0x180019221  lea     rax, aCbrWcscpySPwsz; "CBR(wcscpy_s(pwszFriendlyName, cchPhone"...
0x180019228  mov     r8d, edi
0x18001922b  mov     [rsp+458h+var_430], rax
0x180019230  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180019237  mov     dword ptr [rsp+458h+var_438], 3E9h
0x18001923f  call    McTemplateU0dsqs_EventWriteTransfer
0x180019244  mov     ebx, edi
0x180019246  test    rsi, rsi
0x180019249  jz      loc_1800193D1
0x18001924f  jmp     loc_1800193C4
0x180019254  xor     edx, edx; lpBuffer
0x180019256  lea     r8, [rsp+458h+nSize]; nSize
0x18001925b  lea     ecx, [rdx+5]; NameType
0x18001925e  call    cs:__imp_GetComputerNameExW
0x180019264  test    eax, eax
0x180019266  jz      short loc_180019298
0x180019268  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001926f  mov     edi, 8000FFFFh
0x180019274  mov     ebx, edi
0x180019276  jz      loc_1800193D1
0x18001927c  lea     rax, aCbrGetcomputer; "CBR(!GetComputerNameExW(ComputerNamePhy"...
0x180019283  mov     [rsp+458h+var_430], rax
0x180019288  mov     dword ptr [rsp+458h+var_438], 3EEh
0x180019290  mov     r8d, edi
0x180019293  jmp     loc_180019175
0x180019298  call    cs:__imp_GetLastError
0x18001929e  cmp     eax, 0EAh
0x1800192a3  jz      short loc_1800192E3
0x1800192a5  call    cs:__imp_GetLastError
0x1800192ab  mov     ebx, eax
0x1800192ad  test    eax, eax
0x1800192af  jle     short loc_1800192BA
0x1800192b1  movzx   ebx, ax
0x1800192b4  or      ebx, 80070000h
0x1800192ba  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800192c1  jz      loc_1800193D1
0x1800192c7  lea     rax, aCbrGetlasterro; "CBR(GetLastError() == 234L)"
0x1800192ce  mov     [rsp+458h+var_430], rax
0x1800192d3  mov     dword ptr [rsp+458h+var_438], 3EFh
0x1800192db  mov     r8d, ebx
0x1800192de  jmp     loc_180019175
0x1800192e3  mov     eax, [rsp+458h+nSize]
0x1800192e7  test    eax, eax
0x1800192e9  jnz     short loc_180019318
0x1800192eb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800192f2  mov     edi, 8000FFFFh
0x1800192f7  mov     ebx, edi
0x1800192f9  jz      loc_1800193D1
0x1800192ff  lea     rax, aCbrCchfriendly; "CBR(cchFriendlyName > 0)"
0x180019306  mov     [rsp+458h+var_430], rax
0x18001930b  mov     dword ptr [rsp+458h+var_438], 3F0h
0x180019313  jmp     loc_180019290
0x180019318  mov     rcx, rax
0x18001931b  mov     eax, 2
0x180019320  mul     rcx
0x180019323  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001932a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019331  cmovb   rax, rcx
0x180019335  mov     rcx, rax; unsigned __int64
0x180019338  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001933d  mov     rsi, rax
0x180019340  test    rax, rax
0x180019343  jnz     short loc_18001936C
0x180019345  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001934c  mov     ebx, 8007000Eh
0x180019351  jz      short loc_1800193D1
0x180019353  lea     rax, aCprPwszfriendl; "CPR(pwszFriendlyName)"
0x18001935a  mov     [rsp+458h+var_430], rax
0x18001935f  mov     dword ptr [rsp+458h+var_438], 3F4h
0x180019367  jmp     loc_1800192DB
0x18001936c  lea     r8, [rsp+458h+nSize]; nSize
0x180019371  mov     rdx, rax; lpBuffer
0x180019374  mov     ecx, 5; NameType
0x180019379  call    cs:__imp_GetComputerNameExW
0x18001937f  test    eax, eax
0x180019381  jnz     short loc_1800193CE
0x180019383  call    cs:__imp_GetLastError
0x180019389  mov     ebx, eax
0x18001938b  test    eax, eax
0x18001938d  jle     short loc_180019398
0x18001938f  movzx   ebx, ax
0x180019392  or      ebx, 80070000h
0x180019398  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001939f  jz      short loc_1800193C4
0x1800193a1  lea     rax, aCbrGetcomputer_0; "CBR(GetComputerNameExW(ComputerNamePhys"...
0x1800193a8  mov     r8d, ebx
0x1800193ab  mov     [rsp+458h+var_430], rax
0x1800193b0  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800193b7  mov     dword ptr [rsp+458h+var_438], 3F7h
0x1800193bf  call    McTemplateU0dsqs_EventWriteTransfer
0x1800193c4  mov     rcx, rsi; Block
0x1800193c7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800193cc  jmp     short loc_1800193D1
0x1800193ce  mov     [rdi], rsi
0x1800193d1  mov     eax, ebx
0x1800193d3  mov     rcx, [rsp+458h+var_18]
0x1800193db  xor     rcx, rsp; StackCookie
0x1800193de  call    __security_check_cookie
0x1800193e3  lea     r11, [rsp+458h+var_8]
0x1800193eb  mov     rbx, [r11+18h]
0x1800193ef  mov     rsi, [r11+20h]
0x1800193f3  mov     rsp, r11
0x1800193f6  pop     rdi
0x1800193f7  retn
```
