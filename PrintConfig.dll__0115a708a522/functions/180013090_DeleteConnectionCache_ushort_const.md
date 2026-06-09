# DeleteConnectionCache(ushort const *)

- ea: `0x180013090`
- end: `0x1800135b5`
- name: `?DeleteConnectionCache@@YAXPEBG@Z`
- size: `1317`
- prototype: `void __fastcall(unsigned __int16 *lpValueName)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180015ee8`

## callees

- `0x180003400`
- `0x180004558`
- `0x180004564`
- `0x180006268`
- `0x18000de1c`
- `0x18000f830`
- `0x18000fa4c`
- `0x180013090`
- `0x180016e60`
- `0x180017b40`
- `0x1800183f8`
- `0x180018e74`
- `0x180018f00`
- `0x180018f58`
- `0x1800197b4`
- `0x180038c34`
- `0x180039584`
- `0x180158498`
- `0x180159114`
- `0x18015a2d4`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x1800132d6`
- `KERNEL32!RemoveDirectoryW` at `0x1800132d6`
- `KERNEL32!FreeLibrary` at `0x1800131ba`
- `KERNEL32!FreeLibrary` at `0x1800133c7`
- `KERNEL32!FreeLibrary` at `0x1800131ba`
- `KERNEL32!FreeLibrary` at `0x1800133c7`
- `ADVAPI32!RegCloseKey` at `0x18001311a`
- `ADVAPI32!RegCloseKey` at `0x180013325`
- `ADVAPI32!RegCloseKey` at `0x1800133de`
- `ADVAPI32!RegCloseKey` at `0x18001311a`
- `ADVAPI32!RegCloseKey` at `0x180013325`
- `ADVAPI32!RegCloseKey` at `0x1800133de`
- `ADVAPI32!RegDeleteKeyW` at `0x18001336e`
- `ADVAPI32!RegDeleteKeyW` at `0x18001336e`

## string_xrefs

- `0x180013390`: `Failed to delete connection cache key for %ws. (hr=0x%x)`
- `0x180013397`: `RemoveConnectionRegistryKey`
- `0x1800131f2`: `Connection Cache already deleted for %ws.`
- `0x1800131f9`: `DeleteConnectionCache`
- `0x180013214`: `DeleteConnectionCache`
- `0x18001330f`: `DeleteConnectionCache`
- `0x180013220`: `Connection Cache for %ws has %u outstanding references. Not deleting.`
- `0x180013231`: `Connection Cache for %ws now has 0 references. Deleting.`
- `0x180013308`: `Failed to delete connection cache directory (%ws) for %ws. (hr = 0x%x)`

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
  __int64 v8; // r8
  int v9; // eax
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
          0x31u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v13);
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
          0x32u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v3);
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
          0x33u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          ConnectionSpecificDirectory);
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
          0x34u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v13);
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
            0x35u,
            (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
            v13);
        }
        hr_error::hr_error((hr_error *)v27, v6);
        throw (hr_error *)v27;
      }
      memset(v28, 0, sizeof(v28));
      v7 = -1;
      do
        ++v7;
      while ( PathName[v7] );
      std::wstring::_Construct<1,unsigned short const *>(v28, PathName, v7);
      PrintConfig::LanguageDatabase::ClearResources(0, v28, v8, 0, 0);
      std::wstring::~wstring((char **)v28);
      RemoveAllConnectionFiles(hKey);
      if ( !RemoveDirectoryW(PathName) )
      {
        v9 = RenameAndDeleteOnReboot(PathName, 1);
        if ( v9 < 0 )
        {
          LODWORD(v12) = v9;
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
        v10 = AssembleRegistrySubkey(v1, SubKey);
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
0x180013090  mov     r11, rsp
0x180013093  push    rdi
0x180013094  sub     rsp, 570h
0x18001309b  mov     [rsp+578h+var_510], 0FFFFFFFFFFFFFFFEh
0x1800130a4  mov     [r11+10h], rbx
0x1800130a8  mov     [r11+18h], rsi
0x1800130ac  mov     rax, cs:__security_cookie
0x1800130b3  xor     rax, rsp
0x1800130b6  mov     [rsp+578h+var_18], rax
0x1800130be  mov     rdi, rcx
0x1800130c1  mov     [rsp+578h+var_530], rcx
0x1800130c6  xor     ebx, ebx
0x1800130c8  mov     [rsp+578h+var_548], ebx
0x1800130cc  mov     [rsp+578h+hKey], rbx
0x1800130d1  mov     [rsp+578h+var_538], ebx
0x1800130d5  xor     edx, edx; Val
0x1800130d7  mov     r8d, 208h; Size
0x1800130dd  lea     rcx, [r11-438h]; void *
0x1800130e4  call    memset_0
0x1800130e9  nop
0x1800130ea  xor     edx, edx; bool
0x1800130ec  mov     rcx, rdi; lpValueName
0x1800130ef  call    ?StoreInitStateForThisUser@@YAXPEBG_N@Z; StoreInitStateForThisUser(ushort const *,bool)
0x1800130f4  lea     rdx, [rsp+578h+var_548]; int *
0x1800130f9  lea     rcx, [rsp+578h+hLibModule]; this
0x1800130fe  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180013103  nop
0x180013104  mov     esi, [rsp+578h+var_548]
0x180013108  test    esi, esi
0x18001310a  js      loc_180013410
0x180013110  mov     rcx, [rsp+578h+hKey]; hKey
0x180013115  test    rcx, rcx
0x180013118  jz      short loc_18001312B
0x18001311a  call    cs:__imp_RegCloseKey
0x180013121  nop     dword ptr [rax+rax+00h]
0x180013126  mov     [rsp+578h+hKey], rbx
0x18001312b  mov     [rsp+578h+var_558], rbx; bool *
0x180013130  lea     r9, [rsp+578h+hKey]; HKEY *
0x180013135  xor     r8d, r8d; bool
0x180013138  mov     edx, 2001Fh; samDesired
0x18001313d  mov     rcx, rdi; unsigned __int16 *
0x180013140  call    ?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z; OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)
0x180013145  mov     esi, eax
0x180013147  test    eax, eax
0x180013149  js      loc_180013462
0x18001314f  mov     r8d, 104h; unsigned int
0x180013155  lea     rdx, [rsp+578h+PathName]; unsigned __int16 *
0x18001315d  mov     rcx, [rsp+578h+hKey]; hkey
0x180013162  call    ?GetConnectionSpecificDirectory@@YAJPEAUHKEY__@@PEAGK@Z; GetConnectionSpecificDirectory(HKEY__ *,ushort *,ulong)
0x180013167  mov     esi, eax
0x180013169  test    eax, eax
0x18001316b  js      loc_1800134B6
0x180013171  lea     rcx, [rsp+578h+hKey]; struct RegistryHandleRAII *
0x180013176  call    ?ReadConnectionReferenceCount@@YAKAEAVRegistryHandleRAII@@@Z; ReadConnectionReferenceCount(RegistryHandleRAII &)
0x18001317b  lea     edx, [rax-1]; unsigned int
0x18001317e  mov     [rsp+578h+var_538], edx
0x180013182  lea     rcx, [rsp+578h+hKey]; struct RegistryHandleRAII *
0x180013187  call    ?WriteConnectionReferenceCount@@YAXAEAVRegistryHandleRAII@@K@Z; WriteConnectionReferenceCount(RegistryHandleRAII &,ulong)
0x18001318c  nop
0x18001318d  mov     rax, [rsp+578h+var_518]
0x180013192  test    rax, rax
0x180013195  jz      short loc_1800131B0
0x180013197  mov     rcx, [rsp+578h+var_520]
0x18001319c  test    rcx, rcx
0x18001319f  jz      short loc_1800131B0
0x1800131a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131a6  mov     [rsp+578h+var_518], rbx
0x1800131ab  mov     [rsp+578h+var_520], rbx
0x1800131b0  mov     rcx, [rsp+578h+hLibModule]; hLibModule
0x1800131b5  test    rcx, rcx
0x1800131b8  jz      short loc_1800131C7
0x1800131ba  call    cs:__imp_FreeLibrary
0x1800131c1  nop     dword ptr [rax+rax+00h]
0x1800131c6  nop
0x1800131c7  jmp     short loc_1800131E5
0x1800131c9  xor     ebx, ebx
0x1800131cb  mov     rdi, [rsp+578h+var_530]
0x1800131d0  mov     esi, [rsp+578h+var_548]
0x1800131d4  test    esi, esi
0x1800131d6  js      loc_18001350B
0x1800131dc  jmp     short loc_18001320C
0x1800131de  xor     ebx, ebx
0x1800131e0  mov     rdi, [rsp+578h+var_530]
0x1800131e5  cmp     [rsp+578h+var_548], 80070002h
0x1800131ed  jnz     short loc_1800131D0
0x1800131ef  mov     r8, rdi
0x1800131f2  lea     rdx, aConnectionCach_0; "Connection Cache already deleted for %w"...
0x1800131f9  lea     rcx, aDeleteconnecti; "DeleteConnectionCache"
0x180013200  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180013205  jmp     loc_1800133D4
0x18001320a  jmp     short loc_1800131DE
0x18001320c  mov     r9d, [rsp+578h+var_538]
0x180013211  mov     r8, rdi
0x180013214  lea     rcx, aDeleteconnecti; "DeleteConnectionCache"
0x18001321b  test    r9d, r9d
0x18001321e  jz      short loc_180013231
0x180013220  lea     rdx, aConnectionCach; "Connection Cache for %ws has %u outstan"...
0x180013227  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001322c  jmp     loc_1800133D4
0x180013231  lea     rdx, aConnectionCach_1; "Connection Cache for %ws now has 0 refe"...
0x180013238  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001323d  mov     [rsp+578h+var_548], ebx
0x180013241  lea     rdx, [rsp+578h+var_548]; int *
0x180013246  lea     rcx, [rsp+578h+hLibModule]; this
0x18001324b  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180013250  nop
0x180013251  mov     esi, [rsp+578h+var_548]
0x180013255  test    esi, esi
0x180013257  js      loc_180013560
0x18001325d  xorps   xmm0, xmm0
0x180013260  movups  [rsp+578h+var_458], xmm0
0x180013268  xorps   xmm1, xmm1
0x18001326b  movdqu  [rsp+578h+var_448], xmm1
0x180013274  lea     rax, [rsp+578h+PathName]
0x18001327c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013280  inc     r8
0x180013283  cmp     [rax+r8*2], bx
0x180013288  jnz     short loc_180013280
0x18001328a  lea     rdx, [rsp+578h+PathName]
0x180013292  lea     rcx, [rsp+578h+var_458]
0x18001329a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001329f  nop
0x1800132a0  mov     byte ptr [rsp+578h+var_558], bl; char
0x1800132a4  xor     r9d, r9d
0x1800132a7  lea     rdx, [rsp+578h+var_458]
0x1800132af  xor     ecx, ecx; hPrinter
0x1800132b1  call    ?ClearResources@LanguageDatabase@PrintConfig@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N22@Z; PrintConfig::LanguageDatabase::ClearResources(void *,std::wstring const &,bool,bool,bool)
0x1800132b6  nop
0x1800132b7  lea     rcx, [rsp+578h+var_458]
0x1800132bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800132c4  mov     rcx, [rsp+578h+hKey]; hkey
0x1800132c9  call    ?RemoveAllConnectionFiles@@YAXPEAUHKEY__@@@Z; RemoveAllConnectionFiles(HKEY__ *)
0x1800132ce  lea     rcx, [rsp+578h+PathName]; lpPathName
0x1800132d6  call    cs:__imp_RemoveDirectoryW
0x1800132dd  nop     dword ptr [rax+rax+00h]
0x1800132e2  test    eax, eax
0x1800132e4  jnz     short loc_18001331B
0x1800132e6  mov     dl, 1; bool
0x1800132e8  lea     rcx, [rsp+578h+PathName]; lpExistingFileName
0x1800132f0  call    ?RenameAndDeleteOnReboot@@YAJPEBG_N@Z; RenameAndDeleteOnReboot(ushort const *,bool)
0x1800132f5  test    eax, eax
0x1800132f7  jns     short loc_18001331B
0x1800132f9  mov     dword ptr [rsp+578h+var_558], eax
0x1800132fd  mov     r9, rdi
0x180013300  lea     r8, [rsp+578h+PathName]
0x180013308  lea     rdx, aFailedToDelete; "Failed to delete connection cache direc"...
0x18001330f  lea     rcx, aDeleteconnecti; "DeleteConnectionCache"
0x180013316  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001331b  mov     rcx, [rsp+578h+hKey]; hKey
0x180013320  test    rcx, rcx
0x180013323  jz      short loc_1800133A4
0x180013325  call    cs:__imp_RegCloseKey
0x18001332c  nop     dword ptr [rax+rax+00h]
0x180013331  mov     [rsp+578h+hKey], rbx
0x180013336  xor     edx, edx; Val
0x180013338  mov     r8d, 208h; Size
0x18001333e  lea     rcx, [rsp+578h+SubKey]; void *
0x180013346  call    memset_0
0x18001334b  lea     rdx, [rsp+578h+SubKey]; unsigned __int16 *
0x180013353  mov     rcx, rdi; unsigned __int16 *
0x180013356  call    ?AssembleRegistrySubkey@@YAJPEBGPEAGK@Z; AssembleRegistrySubkey(ushort const *,ushort *,ulong)
0x18001335b  test    eax, eax
0x18001335d  js      short loc_18001338A
0x18001335f  lea     rdx, [rsp+578h+SubKey]; lpSubKey
0x180013367  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001336e  call    cs:__imp_RegDeleteKeyW
0x180013375  nop     dword ptr [rax+rax+00h]
0x18001337a  test    eax, eax
0x18001337c  jle     short loc_180013388
0x18001337e  movzx   eax, ax
0x180013381  or      eax, 80070000h
0x180013386  test    eax, eax
0x180013388  jns     short loc_1800133A4
0x18001338a  mov     r9d, eax
0x18001338d  mov     r8, rdi
0x180013390  lea     rdx, aFailedToDelete_1; "Failed to delete connection cache key f"...
0x180013397  lea     rcx, aRemoveconnecti; "RemoveConnectionRegistryKey"
0x18001339e  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800133a3  nop
0x1800133a4  mov     rax, [rsp+578h+var_518]
0x1800133a9  test    rax, rax
0x1800133ac  jz      short loc_1800133BD
0x1800133ae  mov     rcx, [rsp+578h+var_520]
0x1800133b3  test    rcx, rcx
0x1800133b6  jz      short loc_1800133BD
0x1800133b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133bd  mov     rcx, [rsp+578h+hLibModule]; hLibModule
0x1800133c2  test    rcx, rcx
0x1800133c5  jz      short loc_1800133D4
0x1800133c7  call    cs:__imp_FreeLibrary
0x1800133ce  nop     dword ptr [rax+rax+00h]
0x1800133d3  nop
0x1800133d4  mov     rcx, [rsp+578h+hKey]; hKey
0x1800133d9  test    rcx, rcx
0x1800133dc  jz      short loc_1800133EA
0x1800133de  call    cs:__imp_RegCloseKey
0x1800133e5  nop     dword ptr [rax+rax+00h]
0x1800133ea  mov     rcx, [rsp+578h+var_18]
0x1800133f2  xor     rcx, rsp; StackCookie
0x1800133f5  call    __security_check_cookie
0x1800133fa  lea     r11, [rsp+578h+var_8]
0x180013402  mov     rbx, [r11+18h]
0x180013406  mov     rsi, [r11+20h]
0x18001340a  mov     rsp, r11
0x18001340d  pop     rdi
0x18001340e  retn
0x180013410  lea     rax, WPP_GLOBAL_Control
0x180013417  mov     rcx, cs:WPP_GLOBAL_Control
0x18001341e  cmp     rcx, rax
0x180013421  jz      short loc_18001343F
0x180013423  test    byte ptr [rcx+44h], 1
0x180013427  jz      short loc_18001343F
0x180013429  lea     edx, [rbx+31h]
0x18001342c  mov     r9d, esi
0x18001342f  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180013436  mov     rcx, [rcx+38h]
0x18001343a  call    WPP_SF_d
0x18001343f  mov     edx, esi; int
0x180013441  lea     rcx, [rsp+578h+pExceptionObject]; this
0x180013449  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001344e  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180013455  lea     rcx, [rsp+578h+pExceptionObject]; pExceptionObject
0x18001345d  call    _CxxThrowException_0
0x180013462  lea     rax, WPP_GLOBAL_Control
0x180013469  mov     rcx, cs:WPP_GLOBAL_Control
0x180013470  cmp     rcx, rax
0x180013473  jz      short loc_180013493
0x180013475  test    byte ptr [rcx+44h], 1
0x180013479  jz      short loc_180013493
0x18001347b  mov     edx, 32h ; '2'
0x180013480  mov     r9d, esi
0x180013483  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18001348a  mov     rcx, [rcx+38h]
0x18001348e  call    WPP_SF_d
0x180013493  mov     edx, esi; int
0x180013495  lea     rcx, [rsp+578h+var_4D8]; this
0x18001349d  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800134a2  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800134a9  lea     rcx, [rsp+578h+var_4D8]; pExceptionObject
0x1800134b1  call    _CxxThrowException_0
0x1800134b6  lea     rax, WPP_GLOBAL_Control
0x1800134bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134c4  cmp     rcx, rax
0x1800134c7  jz      short loc_1800134E7
0x1800134c9  test    byte ptr [rcx+44h], 1
0x1800134cd  jz      short loc_1800134E7
0x1800134cf  mov     edx, 33h ; '3'
0x1800134d4  mov     r9d, esi
0x1800134d7  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x1800134de  mov     rcx, [rcx+38h]
0x1800134e2  call    WPP_SF_d
0x1800134e7  mov     edx, esi; int
0x1800134e9  lea     rcx, [rsp+578h+var_4B8]; this
0x1800134f1  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800134f6  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800134fd  lea     rcx, [rsp+578h+var_4B8]; pExceptionObject
0x180013505  call    _CxxThrowException_0
0x18001350b  lea     rax, WPP_GLOBAL_Control
0x180013512  mov     rcx, cs:WPP_GLOBAL_Control
0x180013519  cmp     rcx, rax
0x18001351c  jz      short loc_18001353C
0x18001351e  test    byte ptr [rcx+44h], 1
0x180013522  jz      short loc_18001353C
0x180013524  mov     edx, 34h ; '4'
0x180013529  mov     r9d, esi
0x18001352c  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180013533  mov     rcx, [rcx+38h]
0x180013537  call    WPP_SF_d
0x18001353c  mov     edx, esi; int
0x18001353e  lea     rcx, [rsp+578h+var_498]; this
0x180013546  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001354b  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180013552  lea     rcx, [rsp+578h+var_498]; pExceptionObject
0x18001355a  call    _CxxThrowException_0
0x180013560  lea     rax, WPP_GLOBAL_Control
0x180013567  mov     rcx, cs:WPP_GLOBAL_Control
0x18001356e  cmp     rcx, rax
0x180013571  jz      short loc_180013591
0x180013573  test    byte ptr [rcx+44h], 1
0x180013577  jz      short loc_180013591
0x180013579  mov     edx, 35h ; '5'
0x18001357e  mov     r9d, esi
0x180013581  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180013588  mov     rcx, [rcx+38h]
0x18001358c  call    WPP_SF_d
0x180013591  mov     edx, esi; int
0x180013593  lea     rcx, [rsp+578h+var_478]; this
0x18001359b  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800135a0  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800135a7  lea     rcx, [rsp+578h+var_478]; pExceptionObject
0x1800135af  call    _CxxThrowException_0
```
