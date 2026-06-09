# DeleteConnectionCache(ushort const *)

- ea: `0x18001290c`
- end: `0x180012e06`
- name: `?DeleteConnectionCache@@YAXPEBG@Z`
- size: `1274`
- prototype: `void __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180015554`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180004424`
- `0x1800060ec`
- `0x18000da28`
- `0x18000f380`
- `0x18000f590`
- `0x18001290c`
- `0x1800164a8`
- `0x180017118`
- `0x180017910`
- `0x180018314`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018bbc`
- `0x18003775c`
- `0x180038054`
- `0x1801513d8`
- `0x180152034`
- `0x180153110`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x180012b46`
- `KERNEL32!RemoveDirectoryW` at `0x180012b46`
- `KERNEL32!FreeLibrary` at `0x180012a30`
- `KERNEL32!FreeLibrary` at `0x180012c25`
- `KERNEL32!FreeLibrary` at `0x180012a30`
- `KERNEL32!FreeLibrary` at `0x180012c25`
- `ADVAPI32!RegCloseKey` at `0x180012996`
- `ADVAPI32!RegCloseKey` at `0x180012b8f`
- `ADVAPI32!RegCloseKey` at `0x180012c36`
- `ADVAPI32!RegCloseKey` at `0x180012996`
- `ADVAPI32!RegCloseKey` at `0x180012b8f`
- `ADVAPI32!RegCloseKey` at `0x180012c36`
- `ADVAPI32!RegDeleteKeyW` at `0x180012bd2`
- `ADVAPI32!RegDeleteKeyW` at `0x180012bd2`

## string_xrefs

- `0x180012bee`: `Failed to delete connection cache key for %ws. (hr=0x%x)`
- `0x180012bf5`: `RemoveConnectionRegistryKey`
- `0x180012a62`: `Connection Cache already deleted for %ws.`
- `0x180012a69`: `DeleteConnectionCache`
- `0x180012a84`: `DeleteConnectionCache`
- `0x180012b79`: `DeleteConnectionCache`
- `0x180012a90`: `Connection Cache for %ws has %u outstanding references. Not deleting.`
- `0x180012aa1`: `Connection Cache for %ws now has 0 references. Deleting.`
- `0x180012b72`: `Failed to delete connection cache directory (%ws) for %ws. (hr = 0x%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall DeleteConnectionCache(unsigned __int16 *lpValueName)
{
  unsigned __int16 *v1; // rdi
  int v2; // esi
  int v3; // esi
  int ConnectionSpecificDirectory; // esi
  int v5; // esi
  int v6; // esi
  unsigned __int64 v7; // r8
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // eax
  bool v11; // sf
  bool *v12; // [rsp+20h] [rbp-558h]
  int v13; // [rsp+30h] [rbp-548h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-540h] BYREF
  unsigned int v15; // [rsp+40h] [rbp-538h]
  unsigned __int16 *v16; // [rsp+48h] [rbp-530h]
  HMODULE hLibModule; // [rsp+50h] [rbp-528h] BYREF
  __int64 v18; // [rsp+58h] [rbp-520h]
  void (*v19)(void); // [rsp+60h] [rbp-518h]
  __int64 v20; // [rsp+68h] [rbp-510h]
  const hr_error *v21; // [rsp+70h] [rbp-508h] BYREF
  const PrintCore::WindowsError *v22; // [rsp+78h] [rbp-500h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+80h] [rbp-4F8h] BYREF
  _BYTE v24[32]; // [rsp+A0h] [rbp-4D8h] BYREF
  _BYTE v25[32]; // [rsp+C0h] [rbp-4B8h] BYREF
  _BYTE v26[32]; // [rsp+E0h] [rbp-498h] BYREF
  _BYTE v27[32]; // [rsp+100h] [rbp-478h] BYREF
  _OWORD v28[2]; // [rsp+120h] [rbp-458h] BYREF
  WCHAR PathName[264]; // [rsp+140h] [rbp-438h] BYREF
  WCHAR SubKey[264]; // [rsp+350h] [rbp-228h] BYREF

  v20 = -2;
  v1 = lpValueName;
  v16 = lpValueName;
  v13 = 0;
  hKey = 0;
  v15 = 0;
  memset_0(PathName, 0, 0x208u);
  try
  {
    StoreInitStateForThisUser(v1, 0);
    RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)&hLibModule, &v13);
    v2 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          49,
          WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
          (unsigned int)v13);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v2);
      throw (hr_error *)pExceptionObject;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v3 = OpenConnectionRegistryKey(v1, 0x2001Fu, 0, &hKey, 0);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          50,
          WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
          (unsigned int)v3);
      }
      hr_error::hr_error((hr_error *)v24, v3);
      throw (hr_error *)v24;
    }
    ConnectionSpecificDirectory = GetConnectionSpecificDirectory(hKey, PathName, 0x104u);
    if ( ConnectionSpecificDirectory < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          51,
          WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
          (unsigned int)ConnectionSpecificDirectory);
      }
      hr_error::hr_error((hr_error *)v25, ConnectionSpecificDirectory);
      throw (hr_error *)v25;
    }
    v15 = ReadConnectionReferenceCount((struct RegistryHandleRAII *)&hKey) - 1;
    WriteConnectionReferenceCount((struct RegistryHandleRAII *)&hKey, v15);
    if ( v19 && v18 )
    {
      v19();
      v19 = 0;
      v18 = 0;
    }
    if ( hLibModule )
      FreeLibrary(hLibModule);
  }
  catch ( std::bad_alloc )
  {
    v13 = -2147024882;
    v1 = v16;
    goto LABEL_12;
  }
  catch ( const hr_error *v21 )
  {
    v13 = *((_DWORD *)v21 + 6);
    v1 = v16;
  }
  catch ( const PrintCore::WindowsError *v22 )
  {
    v13 = *((_DWORD *)v22 + 6);
    v1 = v16;
  }
  catch ( std::exception )
  {
    v13 = -2147467259;
    v1 = v16;
    goto LABEL_12;
  }
  catch ( ... )
  {
    v13 = -2147418113;
    v1 = v16;
  }
  if ( v13 == -2147024894 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "DeleteConnectionCache",
      L"Connection Cache already deleted for %ws.",
      v1);
  }
  else
  {
LABEL_12:
    v5 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          52,
          WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
          (unsigned int)v13);
      }
      hr_error::hr_error((hr_error *)v26, v5);
      throw (hr_error *)v26;
    }
    if ( v15 )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "DeleteConnectionCache",
        L"Connection Cache for %ws has %u outstanding references. Not deleting.",
        v1);
    }
    else
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "DeleteConnectionCache",
        L"Connection Cache for %ws now has 0 references. Deleting.",
        v1);
      v13 = 0;
      RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)&hLibModule, &v13);
      v6 = v13;
      if ( v13 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            53,
            WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
            (unsigned int)v13);
        }
        hr_error::hr_error((hr_error *)v27, v6);
        throw (hr_error *)v27;
      }
      memset(v28, 0, sizeof(v28));
      v7 = -1;
      do
        ++v7;
      while ( PathName[v7] );
      std::wstring::_Construct<1,unsigned short const *>((char **)v28, PathName, v7);
      PrintConfig::LanguageDatabase::ClearResources(0, 0);
      std::wstring::~wstring(v28);
      RemoveAllConnectionFiles(hKey);
      if ( !RemoveDirectoryW(PathName) )
      {
        v8 = RenameAndDeleteOnReboot(PathName, 1);
        if ( v8 < 0 )
        {
          LODWORD(v12) = v8;
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
            "DeleteConnectionCache",
            L"Failed to delete connection cache directory (%ws) for %ws. (hr = 0x%x)",
            PathName,
            v1,
            v12);
        }
      }
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
        memset_0(SubKey, 0, 0x208u);
        v10 = AssembleRegistrySubkey(v1, SubKey, v9);
        if ( v10 < 0 )
          goto LABEL_29;
        v10 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
        v11 = v10 < 0;
        if ( v10 > 0 )
        {
          v10 = (unsigned __int16)v10 | 0x80070000;
          v11 = v10 < 0;
        }
        if ( v11 )
LABEL_29:
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
            "RemoveConnectionRegistryKey",
            L"Failed to delete connection cache key for %ws. (hr=0x%x)",
            v1,
            (unsigned int)v10);
      }
      if ( v19 && v18 )
        v19();
      if ( hLibModule )
        FreeLibrary(hLibModule);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18001290c  mov     r11, rsp
0x18001290f  push    rdi
0x180012910  sub     rsp, 570h
0x180012917  mov     [rsp+578h+var_510], 0FFFFFFFFFFFFFFFEh
0x180012920  mov     [r11+10h], rbx
0x180012924  mov     [r11+18h], rsi
0x180012928  mov     rax, cs:__security_cookie
0x18001292f  xor     rax, rsp
0x180012932  mov     [rsp+578h+var_18], rax
0x18001293a  mov     rdi, rcx
0x18001293d  mov     [rsp+578h+var_530], rcx
0x180012942  xor     ebx, ebx
0x180012944  mov     [rsp+578h+var_548], ebx
0x180012948  mov     [rsp+578h+hKey], rbx
0x18001294d  mov     [rsp+578h+var_538], ebx
0x180012951  xor     edx, edx; Val
0x180012953  mov     r8d, 208h; Size
0x180012959  lea     rcx, [r11-438h]; void *
0x180012960  call    memset_0
0x180012965  nop
0x180012966  xor     edx, edx; bool
0x180012968  mov     rcx, rdi; lpValueName
0x18001296b  call    ?StoreInitStateForThisUser@@YAXPEBG_N@Z; StoreInitStateForThisUser(ushort const *,bool)
0x180012970  lea     rdx, [rsp+578h+var_548]; int *
0x180012975  lea     rcx, [rsp+578h+hLibModule]; this
0x18001297a  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x18001297f  nop
0x180012980  mov     esi, [rsp+578h+var_548]
0x180012984  test    esi, esi
0x180012986  js      loc_180012C61
0x18001298c  mov     rcx, [rsp+578h+hKey]; hKey
0x180012991  test    rcx, rcx
0x180012994  jz      short loc_1800129A1
0x180012996  call    cs:__imp_RegCloseKey
0x18001299c  mov     [rsp+578h+hKey], rbx
0x1800129a1  mov     [rsp+578h+var_558], rbx; bool *
0x1800129a6  lea     r9, [rsp+578h+hKey]; HKEY *
0x1800129ab  xor     r8d, r8d; bool
0x1800129ae  mov     edx, 2001Fh; samDesired
0x1800129b3  mov     rcx, rdi; unsigned __int16 *
0x1800129b6  call    ?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z; OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)
0x1800129bb  mov     esi, eax
0x1800129bd  test    eax, eax
0x1800129bf  js      loc_180012CB3
0x1800129c5  mov     r8d, 104h; unsigned int
0x1800129cb  lea     rdx, [rsp+578h+PathName]; unsigned __int16 *
0x1800129d3  mov     rcx, [rsp+578h+hKey]; hkey
0x1800129d8  call    ?GetConnectionSpecificDirectory@@YAJPEAUHKEY__@@PEAGK@Z; GetConnectionSpecificDirectory(HKEY__ *,ushort *,ulong)
0x1800129dd  mov     esi, eax
0x1800129df  test    eax, eax
0x1800129e1  js      loc_180012D07
0x1800129e7  lea     rcx, [rsp+578h+hKey]; struct RegistryHandleRAII *
0x1800129ec  call    ?ReadConnectionReferenceCount@@YAKAEAVRegistryHandleRAII@@@Z; ReadConnectionReferenceCount(RegistryHandleRAII &)
0x1800129f1  lea     edx, [rax-1]; unsigned int
0x1800129f4  mov     [rsp+578h+var_538], edx
0x1800129f8  lea     rcx, [rsp+578h+hKey]; struct RegistryHandleRAII *
0x1800129fd  call    ?WriteConnectionReferenceCount@@YAXAEAVRegistryHandleRAII@@K@Z; WriteConnectionReferenceCount(RegistryHandleRAII &,ulong)
0x180012a02  nop
0x180012a03  mov     rax, [rsp+578h+var_518]
0x180012a08  test    rax, rax
0x180012a0b  jz      short loc_180012A26
0x180012a0d  mov     rcx, [rsp+578h+var_520]
0x180012a12  test    rcx, rcx
0x180012a15  jz      short loc_180012A26
0x180012a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a1c  mov     [rsp+578h+var_518], rbx
0x180012a21  mov     [rsp+578h+var_520], rbx
0x180012a26  mov     rcx, [rsp+578h+hLibModule]; hLibModule
0x180012a2b  test    rcx, rcx
0x180012a2e  jz      short loc_180012A37
0x180012a30  call    cs:__imp_FreeLibrary
0x180012a36  nop
0x180012a37  jmp     short loc_180012A55
0x180012a39  xor     ebx, ebx
0x180012a3b  mov     rdi, [rsp+578h+var_530]
0x180012a40  mov     esi, [rsp+578h+var_548]
0x180012a44  test    esi, esi
0x180012a46  js      loc_180012D5C
0x180012a4c  jmp     short loc_180012A7C
0x180012a4e  xor     ebx, ebx
0x180012a50  mov     rdi, [rsp+578h+var_530]
0x180012a55  cmp     [rsp+578h+var_548], 80070002h
0x180012a5d  jnz     short loc_180012A40
0x180012a5f  mov     r8, rdi
0x180012a62  lea     rdx, aConnectionCach_0; "Connection Cache already deleted for %w"...
0x180012a69  lea     rcx, aDeleteconnecti; "DeleteConnectionCache"
0x180012a70  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180012a75  jmp     loc_180012C2C
0x180012a7a  jmp     short loc_180012A4E
0x180012a7c  mov     r9d, [rsp+578h+var_538]
0x180012a81  mov     r8, rdi
0x180012a84  lea     rcx, aDeleteconnecti; "DeleteConnectionCache"
0x180012a8b  test    r9d, r9d
0x180012a8e  jz      short loc_180012AA1
0x180012a90  lea     rdx, aConnectionCach; "Connection Cache for %ws has %u outstan"...
0x180012a97  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180012a9c  jmp     loc_180012C2C
0x180012aa1  lea     rdx, aConnectionCach_1; "Connection Cache for %ws now has 0 refe"...
0x180012aa8  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180012aad  mov     [rsp+578h+var_548], ebx
0x180012ab1  lea     rdx, [rsp+578h+var_548]; int *
0x180012ab6  lea     rcx, [rsp+578h+hLibModule]; this
0x180012abb  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180012ac0  nop
0x180012ac1  mov     esi, [rsp+578h+var_548]
0x180012ac5  test    esi, esi
0x180012ac7  js      loc_180012DB1
0x180012acd  xorps   xmm0, xmm0
0x180012ad0  movups  [rsp+578h+var_458], xmm0
0x180012ad8  xorps   xmm1, xmm1
0x180012adb  movdqu  [rsp+578h+var_448], xmm1
0x180012ae4  lea     rax, [rsp+578h+PathName]
0x180012aec  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012af0  inc     r8
0x180012af3  cmp     [rax+r8*2], bx
0x180012af8  jnz     short loc_180012AF0
0x180012afa  lea     rdx, [rsp+578h+PathName]
0x180012b02  lea     rcx, [rsp+578h+var_458]
0x180012b0a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180012b0f  nop
0x180012b10  mov     byte ptr [rsp+578h+var_558], bl; char
0x180012b14  xor     r9d, r9d
0x180012b17  lea     rdx, [rsp+578h+var_458]
0x180012b1f  xor     ecx, ecx; hPrinter
0x180012b21  call    ?ClearResources@LanguageDatabase@PrintConfig@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N22@Z; PrintConfig::LanguageDatabase::ClearResources(void *,std::wstring const &,bool,bool,bool)
0x180012b26  nop
0x180012b27  lea     rcx, [rsp+578h+var_458]
0x180012b2f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012b34  mov     rcx, [rsp+578h+hKey]; hkey
0x180012b39  call    ?RemoveAllConnectionFiles@@YAXPEAUHKEY__@@@Z; RemoveAllConnectionFiles(HKEY__ *)
0x180012b3e  lea     rcx, [rsp+578h+PathName]; lpPathName
0x180012b46  call    cs:__imp_RemoveDirectoryW
0x180012b4c  test    eax, eax
0x180012b4e  jnz     short loc_180012B85
0x180012b50  mov     dl, 1; bool
0x180012b52  lea     rcx, [rsp+578h+PathName]; lpExistingFileName
0x180012b5a  call    ?RenameAndDeleteOnReboot@@YAJPEBG_N@Z; RenameAndDeleteOnReboot(ushort const *,bool)
0x180012b5f  test    eax, eax
0x180012b61  jns     short loc_180012B85
0x180012b63  mov     dword ptr [rsp+578h+var_558], eax
0x180012b67  mov     r9, rdi
0x180012b6a  lea     r8, [rsp+578h+PathName]
0x180012b72  lea     rdx, aFailedToDelete; "Failed to delete connection cache direc"...
0x180012b79  lea     rcx, aDeleteconnecti; "DeleteConnectionCache"
0x180012b80  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180012b85  mov     rcx, [rsp+578h+hKey]; hKey
0x180012b8a  test    rcx, rcx
0x180012b8d  jz      short loc_180012C02
0x180012b8f  call    cs:__imp_RegCloseKey
0x180012b95  mov     [rsp+578h+hKey], rbx
0x180012b9a  xor     edx, edx; Val
0x180012b9c  mov     r8d, 208h; Size
0x180012ba2  lea     rcx, [rsp+578h+SubKey]; void *
0x180012baa  call    memset_0
0x180012baf  lea     rdx, [rsp+578h+SubKey]; unsigned __int16 *
0x180012bb7  mov     rcx, rdi; unsigned __int16 *
0x180012bba  call    ?AssembleRegistrySubkey@@YAJPEBGPEAGK@Z; AssembleRegistrySubkey(ushort const *,ushort *,ulong)
0x180012bbf  test    eax, eax
0x180012bc1  js      short loc_180012BE8
0x180012bc3  lea     rdx, [rsp+578h+SubKey]; lpSubKey
0x180012bcb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012bd2  call    cs:__imp_RegDeleteKeyW
0x180012bd8  test    eax, eax
0x180012bda  jle     short loc_180012BE6
0x180012bdc  movzx   eax, ax
0x180012bdf  or      eax, 80070000h
0x180012be4  test    eax, eax
0x180012be6  jns     short loc_180012C02
0x180012be8  mov     r9d, eax
0x180012beb  mov     r8, rdi
0x180012bee  lea     rdx, aFailedToDelete_1; "Failed to delete connection cache key f"...
0x180012bf5  lea     rcx, aRemoveconnecti; "RemoveConnectionRegistryKey"
0x180012bfc  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180012c01  nop
0x180012c02  mov     rax, [rsp+578h+var_518]
0x180012c07  test    rax, rax
0x180012c0a  jz      short loc_180012C1B
0x180012c0c  mov     rcx, [rsp+578h+var_520]
0x180012c11  test    rcx, rcx
0x180012c14  jz      short loc_180012C1B
0x180012c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c1b  mov     rcx, [rsp+578h+hLibModule]; hLibModule
0x180012c20  test    rcx, rcx
0x180012c23  jz      short loc_180012C2C
0x180012c25  call    cs:__imp_FreeLibrary
0x180012c2b  nop
0x180012c2c  mov     rcx, [rsp+578h+hKey]; hKey
0x180012c31  test    rcx, rcx
0x180012c34  jz      short loc_180012C3C
0x180012c36  call    cs:__imp_RegCloseKey
0x180012c3c  mov     rcx, [rsp+578h+var_18]
0x180012c44  xor     rcx, rsp; StackCookie
0x180012c47  call    __security_check_cookie
0x180012c4c  lea     r11, [rsp+578h+var_8]
0x180012c54  mov     rbx, [r11+18h]
0x180012c58  mov     rsi, [r11+20h]
0x180012c5c  mov     rsp, r11
0x180012c5f  pop     rdi
0x180012c60  retn
0x180012c61  lea     rax, WPP_GLOBAL_Control
0x180012c68  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c6f  cmp     rcx, rax
0x180012c72  jz      short loc_180012C90
0x180012c74  test    byte ptr [rcx+44h], 1
0x180012c78  jz      short loc_180012C90
0x180012c7a  lea     edx, [rbx+31h]
0x180012c7d  mov     r9d, esi
0x180012c80  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180012c87  mov     rcx, [rcx+38h]
0x180012c8b  call    WPP_SF_d
0x180012c90  mov     edx, esi; int
0x180012c92  lea     rcx, [rsp+578h+pExceptionObject]; this
0x180012c9a  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012c9f  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012ca6  lea     rcx, [rsp+578h+pExceptionObject]; pExceptionObject
0x180012cae  call    _CxxThrowException_0
0x180012cb3  lea     rax, WPP_GLOBAL_Control
0x180012cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cc1  cmp     rcx, rax
0x180012cc4  jz      short loc_180012CE4
0x180012cc6  test    byte ptr [rcx+44h], 1
0x180012cca  jz      short loc_180012CE4
0x180012ccc  mov     edx, 32h ; '2'
0x180012cd1  mov     r9d, esi
0x180012cd4  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180012cdb  mov     rcx, [rcx+38h]
0x180012cdf  call    WPP_SF_d
0x180012ce4  mov     edx, esi; int
0x180012ce6  lea     rcx, [rsp+578h+var_4D8]; this
0x180012cee  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012cf3  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012cfa  lea     rcx, [rsp+578h+var_4D8]; pExceptionObject
0x180012d02  call    _CxxThrowException_0
0x180012d07  lea     rax, WPP_GLOBAL_Control
0x180012d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d15  cmp     rcx, rax
0x180012d18  jz      short loc_180012D38
0x180012d1a  test    byte ptr [rcx+44h], 1
0x180012d1e  jz      short loc_180012D38
0x180012d20  mov     edx, 33h ; '3'
0x180012d25  mov     r9d, esi
0x180012d28  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180012d2f  mov     rcx, [rcx+38h]
0x180012d33  call    WPP_SF_d
0x180012d38  mov     edx, esi; int
0x180012d3a  lea     rcx, [rsp+578h+var_4B8]; this
0x180012d42  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012d47  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012d4e  lea     rcx, [rsp+578h+var_4B8]; pExceptionObject
0x180012d56  call    _CxxThrowException_0
0x180012d5c  lea     rax, WPP_GLOBAL_Control
0x180012d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d6a  cmp     rcx, rax
0x180012d6d  jz      short loc_180012D8D
0x180012d6f  test    byte ptr [rcx+44h], 1
0x180012d73  jz      short loc_180012D8D
0x180012d75  mov     edx, 34h ; '4'
0x180012d7a  mov     r9d, esi
0x180012d7d  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180012d84  mov     rcx, [rcx+38h]
0x180012d88  call    WPP_SF_d
0x180012d8d  mov     edx, esi; int
0x180012d8f  lea     rcx, [rsp+578h+var_498]; this
0x180012d97  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012d9c  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012da3  lea     rcx, [rsp+578h+var_498]; pExceptionObject
0x180012dab  call    _CxxThrowException_0
0x180012db1  lea     rax, WPP_GLOBAL_Control
0x180012db8  mov     rcx, cs:WPP_GLOBAL_Control
0x180012dbf  cmp     rcx, rax
0x180012dc2  jz      short loc_180012DE2
0x180012dc4  test    byte ptr [rcx+44h], 1
0x180012dc8  jz      short loc_180012DE2
0x180012dca  mov     edx, 35h ; '5'
0x180012dcf  mov     r9d, esi
0x180012dd2  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180012dd9  mov     rcx, [rcx+38h]
0x180012ddd  call    WPP_SF_d
0x180012de2  mov     edx, esi; int
0x180012de4  lea     rcx, [rsp+578h+var_478]; this
0x180012dec  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012df1  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012df8  lea     rcx, [rsp+578h+var_478]; pExceptionObject
0x180012e00  call    _CxxThrowException_0
```
