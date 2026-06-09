# DdcDeviceInfoHelper::GetOemSerialNumber(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18001992c`
- end: `0x180019af7`
- name: `?GetOemSerialNumber@DdcDeviceInfoHelper@@CAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `459`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016aa4`

## callees

- `0x180004e10`
- `0x1800050b8`
- `0x18001992c`
- `0x180028638`
- `0x180028704`
- `0x1800287d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019ad7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019ae7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019ad7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019ae7`

## string_xrefs

- `0x18001997b`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x1800199c3`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180019a72`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetOemSerialNumber(__int64 a1, int a2)
{
  int SmBiosData; // ebx
  int v4; // edx
  int v5; // ecx
  int v6; // edx
  int v7; // ecx
  __int64 v8; // r8
  void *v9; // rdi
  int v10; // ecx
  __int64 v12; // [rsp+0h] [rbp-48h] BYREF
  int v13; // [rsp+20h] [rbp-28h]
  const char *v14; // [rsp+28h] [rbp-20h]
  struct TSmBiosTable *v15; // [rsp+50h] [rbp+8h] BYREF
  void *Block; // [rsp+58h] [rbp+10h] BYREF
  struct TSmBiosData *v17; // [rsp+60h] [rbp+18h] BYREF

  v17 = 0;
  v15 = 0;
  Block = 0;
  if ( !a1 )
  {
    SmBiosData = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        130,
        "CPR(pwstrSerialNumber)");
    return (unsigned int)SmBiosData;
  }
  SmBiosData = GetSmBiosData(&v17);
  if ( SmBiosData < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_23;
    v14 = "CHR(GetSmBiosData(&pSmBiosData))";
    v13 = 1155;
    goto LABEL_7;
  }
  SmBiosData = FindSmBiosTable(v17, v4, &v15);
  if ( SmBiosData >= 0 )
  {
    if ( !v15 )
    {
      SmBiosData = -2147467259;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          0,
          v4,
          -2147467259,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          135,
          "CBR(pSystemInfo != nullptr)");
      goto LABEL_23;
    }
    SmBiosData = GetSmBiosString(v15, *((_BYTE *)v15 + 7), (unsigned __int16 **)&Block);
    if ( SmBiosData < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          SmBiosData,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          138,
          "CHR(GetSmBiosString(pSystemInfo, pSystemInfo->SerialNumber, &pwszSerialNumber))");
LABEL_20:
      v9 = Block;
      goto LABEL_21;
    }
    v9 = Block;
    if ( !Block )
    {
      SmBiosData = -2147467259;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          -2147467259,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          139,
          "CBR(pwszSerialNumber != nullptr)");
      goto LABEL_23;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      std::wstring::assign(a1, (__int64)Block, v8);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        LODWORD(v15) = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v10,
            (unsigned int)&v12,
            -2147024882,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
            147,
            "CHR(((HRESULT)0x8007000EL))");
        SmBiosData = (int)v15;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180019AC6);
        goto LABEL_20;
      }
    }
LABEL_21:
    if ( v9 )
      free(v9);
    goto LABEL_23;
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v14 = "CHR(FindSmBiosTable(pSmBiosData, 1, (TSmBiosTable**)&pSystemInfo))";
    v13 = 1158;
LABEL_7:
    McTemplateU0dsqs_EventWriteTransfer(
      v5,
      v4,
      SmBiosData,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      v13,
      v14);
  }
LABEL_23:
  if ( v17 )
    free(v17);
  return (unsigned int)SmBiosData;
}

```

## disassembly

```asm
0x18001992c  mov     r11, rsp
0x18001992f  push    rbx
0x180019930  push    rsi
0x180019931  push    rdi
0x180019932  sub     rsp, 30h
0x180019936  mov     rsi, rcx
0x180019939  mov     qword ptr [r11+18h], 0
0x180019941  mov     qword ptr [r11+8], 0
0x180019949  mov     qword ptr [r11+10h], 0
0x180019951  test    rcx, rcx
0x180019954  jnz     short loc_18001998F
0x180019956  mov     ebx, 80070057h
0x18001995b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019962  jz      loc_180019AED
0x180019968  lea     rax, aCprPwstrserial; "CPR(pwstrSerialNumber)"
0x18001996f  mov     [r11-20h], rax
0x180019973  mov     [rsp+48h+var_28], 482h
0x18001997b  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180019982  mov     r8d, ebx
0x180019985  call    McTemplateU0dsqs_EventWriteTransfer
0x18001998a  jmp     loc_180019AED
0x18001998f  lea     rcx, [rsp+48h+arg_10]; struct TSmBiosData **
0x180019994  call    ?GetSmBiosData@@YAJPEAPEAUTSmBiosData@@@Z; GetSmBiosData(TSmBiosData * *)
0x180019999  mov     ebx, eax
0x18001999b  test    eax, eax
0x18001999d  jns     short loc_1800199D4
0x18001999f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800199a6  jz      loc_180019ADD
0x1800199ac  lea     rax, aChrGetsmbiosda; "CHR(GetSmBiosData(&pSmBiosData))"
0x1800199b3  mov     [rsp+48h+var_20], rax
0x1800199b8  mov     [rsp+48h+var_28], 483h
0x1800199c0  mov     r8d, ebx
0x1800199c3  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800199ca  call    McTemplateU0dsqs_EventWriteTransfer
0x1800199cf  jmp     loc_180019ADD
0x1800199d4  lea     r8, [rsp+48h+arg_0]; struct TSmBiosTable **
0x1800199d9  mov     rcx, [rsp+48h+arg_10]; struct TSmBiosData *
0x1800199de  call    ?FindSmBiosTable@@YAJPEBUTSmBiosData@@EPEAPEAUTSmBiosTable@@@Z; FindSmBiosTable(TSmBiosData const *,uchar,TSmBiosTable * *)
0x1800199e3  mov     ebx, eax
0x1800199e5  test    eax, eax
0x1800199e7  jns     short loc_180019A0C
0x1800199e9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800199f0  jz      loc_180019ADD
0x1800199f6  lea     rax, aChrFindsmbiost; "CHR(FindSmBiosTable(pSmBiosData, 1, (TS"...
0x1800199fd  mov     [rsp+48h+var_20], rax
0x180019a02  mov     [rsp+48h+var_28], 486h
0x180019a0a  jmp     short loc_1800199C0
0x180019a0c  mov     rcx, [rsp+48h+arg_0]; struct TSmBiosTable *
0x180019a11  test    rcx, rcx
0x180019a14  jnz     short loc_180019A42
0x180019a16  mov     r8d, 80004005h
0x180019a1c  mov     ebx, r8d
0x180019a1f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019a26  jz      loc_180019ADD
0x180019a2c  lea     rax, aCbrPsysteminfo; "CBR(pSystemInfo != nullptr)"
0x180019a33  mov     [rsp+48h+var_20], rax
0x180019a38  mov     [rsp+48h+var_28], 487h
0x180019a40  jmp     short loc_1800199C3
0x180019a42  lea     r8, [rsp+48h+Block]; unsigned __int16 **
0x180019a47  mov     dl, [rcx+7]; unsigned __int8
0x180019a4a  call    ?GetSmBiosString@@YAJPEBUTSmBiosTable@@EPEAPEAG@Z; GetSmBiosString(TSmBiosTable const *,uchar,ushort * *)
0x180019a4f  mov     ebx, eax
0x180019a51  test    eax, eax
0x180019a53  jns     short loc_180019A83
0x180019a55  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019a5c  jz      short loc_180019ACA
0x180019a5e  lea     rax, aChrGetsmbiosst; "CHR(GetSmBiosString(pSystemInfo, pSyste"...
0x180019a65  mov     [rsp+48h+var_20], rax
0x180019a6a  mov     [rsp+48h+var_28], 48Ah
0x180019a72  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180019a79  mov     r8d, ebx
0x180019a7c  call    McTemplateU0dsqs_EventWriteTransfer
0x180019a81  jmp     short loc_180019ACA
0x180019a83  mov     rdi, [rsp+48h+Block]
0x180019a88  test    rdi, rdi
0x180019a8b  jnz     short loc_180019AB8
0x180019a8d  mov     r8d, 80004005h
0x180019a93  mov     ebx, r8d
0x180019a96  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019a9d  jz      short loc_180019ADD
0x180019a9f  lea     rax, aCbrPwszserialn; "CBR(pwszSerialNumber != nullptr)"
0x180019aa6  mov     [rsp+48h+var_20], rax
0x180019aab  mov     [rsp+48h+var_28], 48Bh
0x180019ab3  jmp     loc_1800199C3
0x180019ab8  mov     rdx, rdi
0x180019abb  mov     rcx, rsi
0x180019abe  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180019ac3  nop
0x180019ac4  jmp     short loc_180019ACF
0x180019ac6  mov     ebx, dword ptr [rsp+48h+arg_0]
0x180019aca  mov     rdi, [rsp+48h+Block]
0x180019acf  test    rdi, rdi
0x180019ad2  jz      short loc_180019ADD
0x180019ad4  mov     rcx, rdi; Block
0x180019ad7  call    cs:__imp_free
0x180019add  mov     rcx, [rsp+48h+arg_10]; Block
0x180019ae2  test    rcx, rcx
0x180019ae5  jz      short loc_180019AED
0x180019ae7  call    cs:__imp_free
0x180019aed  mov     eax, ebx
0x180019aef  add     rsp, 30h
0x180019af3  pop     rdi
0x180019af4  pop     rsi
0x180019af5  pop     rbx
0x180019af6  retn
```
