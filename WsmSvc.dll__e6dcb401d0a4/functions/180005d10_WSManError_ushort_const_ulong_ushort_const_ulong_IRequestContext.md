# WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)

- ea: `0x180005d10`
- end: `0x18000602e`
- name: `?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z`
- size: `798`
- prototype: `void __fastcall(wchar_t *String1, __int64, const unsigned __int16 *, DWORD, struct IRequestContext *)`
- caller_count: `1808`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x180001288`
- `0x1800012e0`
- `0x1800015b4`
- `0x180001670`
- `0x180001c30`
- `0x180001db0`
- `0x180002524`
- `0x180002b38`
- `0x180002d30`
- `0x180002e50`
- `0x180003d70`
- `0x180003ed0`
- `0x180004240`
- `0x180004d30`
- `0x180005bf0`
- `0x180005c70`
- `0x180006040`
- `0x180007380`
- `0x180007fb0`
- `0x180008920`
- `0x180008990`
- `0x1800089e0`
- `0x180008a30`
- `0x180008d48`
- `0x1800092a0`
- `0x1800092f0`
- `0x1800095fc`
- `0x180009750`
- `0x180009ab0`
- `0x18000a170`
- `0x18000a294`
- `0x18000a9a0`
- `0x18000aa38`
- `0x18000ade0`
- `0x18000b510`
- `0x18000c530`
- `0x18000d260`
- `0x18000d780`
- `0x18000d7c8`
- `0x18000ea70`
- `0x18000eae0`
- `0x18000f138`
- `0x18000f700`
- `0x18000f7a0`
- `0x18000f994`
- `0x18000f9e0`
- `0x18000fb60`
- `0x18000fcb8`
- `0x18000fdc0`
- `0x18000ff18`

## callees

- `0x180005d10`
- `0x180010030`
- `0x180025d90`
- `0x180026310`
- `0x180046d70`
- `0x1800485f0`
- `0x18007a030`
- `0x1800870f0`
- `0x18011d8c0`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180005d7c`
- `msvcrt!_wcsnicmp` at `0x180005d7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ffe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ffe`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005eb7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005eca`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005edd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005ef0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005f03`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005eb7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005eca`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005edd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005ef0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005f03`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180005e8c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180005e8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005f65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005f65`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005dec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005dec`

## string_xrefs

- `0x180005e85`: `wer.dll`
- `0x180005ead`: `WerReportCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall WSManError(
        wchar_t *String1,
        __int64 a2,
        const unsigned __int16 *a3,
        DWORD a4,
        struct IRequestContext *a5)
{
  DWORD v5; // r15d
  const wchar_t *v8; // rdi
  _WORD *v9; // rsi
  ULONGLONG TickCount64; // rax
  struct CConfigManager *ConfigManager; // rsi
  struct IRequestContext *v13; // rdx
  HMODULE Library; // rax
  HMODULE v15; // rbx
  FARPROC ProcAddress; // rsi
  FARPROC v17; // r14
  FARPROC v18; // r15
  FARPROC v19; // r12
  FARPROC v20; // rax
  void (__fastcall *v21)(__int64); // rbx
  HANDLE CurrentProcess; // rax
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  HMODULE hModule[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[672]; // [rsp+60h] [rbp-A0h] BYREF

  v5 = a4;
  if ( String1 )
  {
    v8 = String1;
    while ( *v8 )
    {
      v9 = v8 + 1;
      if ( !_wcsnicmp(v8++, L"\\admin\\", 7u) )
      {
        if ( *v9 )
          goto LABEL_8;
        break;
      }
    }
    v8 = String1;
  }
  else
  {
    v8 = &Class;
  }
LABEL_8:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_3d40dc3671cd32fcfba845124bc001a1_Traceguids,
      (_DWORD)v8,
      (__int64)a3);
  if ( a5 )
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a5 + 88LL))(a5, 1077134251);
  TickCount64 = GetTickCount64();
  if ( !qword_180280C88 || TickCount64 - qword_180280C88 > 0x493E0 )
  {
    qword_180280C88 = TickCount64;
    ConfigManager = CConfigManager::GetConfigManager();
    hModule[0] = (HMODULE)ConfigManager;
    if ( ConfigManager )
    {
      CRequestContext::CRequestContext((CRequestContext *)v26);
      v13 = (struct IRequestContext *)v26;
      if ( a5 )
        v13 = a5;
      CConfigManager::GetBool(ConfigManager, v13, 6020, &dword_180280C90, 0);
      CRequestContext::~CRequestContext((CRequestContext *)v26);
    }
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(hModule);
  }
  if ( dword_180280C90 )
  {
    hModule[0] = 0;
    Library = LoadLibraryExW(L"wer.dll", 0, 0);
    AutoCleanup<AutoLibrary,HINSTANCE__ *>::operator=(hModule, Library);
    v15 = hModule[0];
    if ( hModule[0] )
    {
      ProcAddress = GetProcAddress(hModule[0], "WerReportCreate");
      v17 = GetProcAddress(v15, "WerReportSetParameter");
      v18 = GetProcAddress(v15, "WerReportAddDump");
      v19 = GetProcAddress(v15, "WerReportSubmit");
      v20 = GetProcAddress(v15, "WerReportCloseHandle");
      v21 = (void (__fastcall *)(__int64))v20;
      if ( ProcAddress )
      {
        if ( v18 )
        {
          if ( v17 )
          {
            if ( v19 )
            {
              if ( v20 )
              {
                v24 = 0;
                if ( !((unsigned int (__fastcall *)(const wchar_t *, _QWORD, _QWORD, __int64 *))ProcAddress)(
                        L"WinRMAssert",
                        0,
                        0,
                        &v24) )
                {
                  CurrentProcess = GetCurrentProcess();
                  ((void (__fastcall *)(__int64, HANDLE, _QWORD, __int64, _QWORD, _QWORD, _DWORD))v18)(
                    v24,
                    CurrentProcess,
                    0,
                    2,
                    0,
                    0,
                    0);
                  ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, const wchar_t *))v17)(v24, 0, L"Filename", v8);
                  ((void (__fastcall *)(__int64, __int64, const wchar_t *, const unsigned __int16 *))v17)(
                    v24,
                    1,
                    L"Line number",
                    a3);
                  ((void (__fastcall *)(__int64, __int64, __int64, _QWORD))v19)(v24, 2, 1152, 0);
                  v21(v24);
                }
              }
            }
          }
        }
      }
      v5 = a4;
    }
    AutoCleanup<AutoLibrary,HINSTANCE__ *>::ReleasePtr(hModule);
  }
  SetLastError(v5);
}

```

## disassembly

```asm
0x180005d10  mov     [rsp-8+arg_8], rbx
0x180005d15  push    rbp
0x180005d16  push    rsi
0x180005d17  push    rdi
0x180005d18  push    r12
0x180005d1a  push    r13
0x180005d1c  push    r14
0x180005d1e  push    r15
0x180005d20  lea     rbp, [rsp-210h]
0x180005d28  sub     rsp, 310h
0x180005d2f  mov     rax, cs:__security_cookie
0x180005d36  xor     rax, rsp
0x180005d39  mov     [rbp+240h+var_40], rax
0x180005d40  mov     r15d, r9d
0x180005d43  mov     [rsp+340h+var_300], r9d
0x180005d48  mov     r13, r8
0x180005d4b  mov     r14, rcx
0x180005d4e  mov     rbx, [rbp+240h+arg_20]
0x180005d55  xor     r12d, r12d
0x180005d58  test    rcx, rcx
0x180005d5b  jz      short loc_180005D96
0x180005d5d  mov     rdi, rcx
0x180005d60  movzx   eax, word ptr [rdi]
0x180005d63  test    ax, ax
0x180005d66  jz      short loc_180005D91
0x180005d68  lea     rsi, [rdi+2]
0x180005d6c  mov     r8d, 7; MaxCount
0x180005d72  lea     rdx, aAdmin; "\\admin\\"
0x180005d79  mov     rcx, rdi; String1
0x180005d7c  call    cs:__imp__wcsnicmp
0x180005d82  mov     rdi, rsi
0x180005d85  test    eax, eax
0x180005d87  jnz     short loc_180005D60
0x180005d89  movzx   eax, word ptr [rsi]
0x180005d8c  test    ax, ax
0x180005d8f  jnz     short loc_180005D9D
0x180005d91  mov     rdi, r14
0x180005d94  jmp     short loc_180005D9D
0x180005d96  lea     rdi, Class
0x180005d9d  lea     rax, WPP_GLOBAL_Control
0x180005da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dab  cmp     rcx, rax
0x180005dae  jz      short loc_180005DD3
0x180005db0  test    byte ptr [rcx+1Ch], 80h
0x180005db4  jz      short loc_180005DD3
0x180005db6  mov     edx, 0Ah
0x180005dbb  mov     [rsp+340h+var_320], r13
0x180005dc0  mov     r9, rdi
0x180005dc3  lea     r8, WPP_3d40dc3671cd32fcfba845124bc001a1_Traceguids
0x180005dca  mov     rcx, [rcx+10h]
0x180005dce  call    WPP_SF_SS
0x180005dd3  test    rbx, rbx
0x180005dd6  jz      short loc_180005DEC
0x180005dd8  mov     rax, [rbx]
0x180005ddb  mov     edx, 4033C3ABh
0x180005de0  mov     rcx, rbx
0x180005de3  mov     rax, [rax+58h]
0x180005de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dec  call    cs:__imp_GetTickCount64
0x180005df2  mov     rdx, cs:qword_180280C88
0x180005df9  test    rdx, rdx
0x180005dfc  jz      short loc_180005E0D
0x180005dfe  mov     rcx, rax
0x180005e01  sub     rcx, rdx
0x180005e04  cmp     rcx, 493E0h
0x180005e0b  jbe     short loc_180005E6E
0x180005e0d  mov     cs:qword_180280C88, rax
0x180005e14  call    ?GetConfigManager@CConfigManager@@SAPEAV1@XZ; CConfigManager::GetConfigManager(void)
0x180005e19  mov     rsi, rax
0x180005e1c  mov     [rsp+340h+hModule], rax
0x180005e21  test    rax, rax
0x180005e24  jz      short loc_180005E63
0x180005e26  lea     rcx, [rsp+340h+var_2E0]; this
0x180005e2b  call    ??0CRequestContext@@QEAA@XZ; CRequestContext::CRequestContext(void)
0x180005e30  nop
0x180005e31  lea     rdx, [rsp+340h+var_2E0]
0x180005e36  test    rbx, rbx
0x180005e39  cmovnz  rdx, rbx
0x180005e3d  mov     [rsp+340h+var_320], r12
0x180005e42  lea     r9, dword_180280C90
0x180005e49  mov     r8d, 1784h
0x180005e4f  mov     rcx, rsi
0x180005e52  call    ?GetBool@CConfigManager@@QEAAHPEAVIRequestContext@@W4ConfigSetting@@PEAHPEAW4WSManConfigSource@@@Z; CConfigManager::GetBool(IRequestContext *,ConfigSetting,int *,WSManConfigSource *)
0x180005e57  nop
0x180005e58  lea     rcx, [rsp+340h+var_2E0]; this
0x180005e5d  call    ??1CRequestContext@@UEAA@XZ; CRequestContext::~CRequestContext(void)
0x180005e62  nop
0x180005e63  lea     rcx, [rsp+340h+hModule]
0x180005e68  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180005e6d  nop
0x180005e6e  cmp     cs:dword_180280C90, r12d
0x180005e75  jz      loc_180005FFB
0x180005e7b  mov     [rsp+340h+hModule], r12
0x180005e80  xor     r8d, r8d; dwFlags
0x180005e83  xor     edx, edx; hFile
0x180005e85  lea     rcx, LibFileName; "wer.dll"
0x180005e8c  call    cs:__imp_LoadLibraryExW
0x180005e92  mov     rdx, rax
0x180005e95  lea     rcx, [rsp+340h+hModule]
0x180005e9a  call    ??4?$AutoCleanup@VAutoLibrary@@PEAUHINSTANCE__@@@@QEAAAEAVAutoLibrary@@PEAUHINSTANCE__@@@Z; AutoCleanup<AutoLibrary,HINSTANCE__ *>::operator=(HINSTANCE__ *)
0x180005e9f  mov     rbx, [rsp+340h+hModule]
0x180005ea4  test    rbx, rbx
0x180005ea7  jz      loc_180005FF1
0x180005ead  lea     rdx, ProcName; "WerReportCreate"
0x180005eb4  mov     rcx, rbx; hModule
0x180005eb7  call    cs:__imp_GetProcAddress
0x180005ebd  mov     rsi, rax
0x180005ec0  lea     rdx, aWerreportsetpa; "WerReportSetParameter"
0x180005ec7  mov     rcx, rbx; hModule
0x180005eca  call    cs:__imp_GetProcAddress
0x180005ed0  mov     r14, rax
0x180005ed3  lea     rdx, aWerreportadddu; "WerReportAddDump"
0x180005eda  mov     rcx, rbx; hModule
0x180005edd  call    cs:__imp_GetProcAddress
0x180005ee3  mov     r15, rax
0x180005ee6  lea     rdx, aWerreportsubmi; "WerReportSubmit"
0x180005eed  mov     rcx, rbx; hModule
0x180005ef0  call    cs:__imp_GetProcAddress
0x180005ef6  mov     r12, rax
0x180005ef9  lea     rdx, aWerreportclose; "WerReportCloseHandle"
0x180005f00  mov     rcx, rbx; hModule
0x180005f03  call    cs:__imp_GetProcAddress
0x180005f09  mov     rbx, rax
0x180005f0c  test    rsi, rsi
0x180005f0f  jz      loc_180005FEC
0x180005f15  test    r15, r15
0x180005f18  jz      loc_180005FEC
0x180005f1e  test    r14, r14
0x180005f21  jz      loc_180005FEC
0x180005f27  test    r12, r12
0x180005f2a  jz      loc_180005FEC
0x180005f30  test    rax, rax
0x180005f33  jz      loc_180005FEC
0x180005f39  mov     [rsp+340h+var_2F8], 0
0x180005f42  lea     r9, [rsp+340h+var_2F8]
0x180005f47  xor     r8d, r8d
0x180005f4a  xor     edx, edx
0x180005f4c  lea     rcx, aWinrmassert; "WinRMAssert"
0x180005f53  mov     rax, rsi
0x180005f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f5b  xor     esi, esi
0x180005f5d  test    eax, eax
0x180005f5f  jnz     loc_180005FEC
0x180005f65  call    cs:__imp_GetCurrentProcess
0x180005f6b  mov     [rsp+340h+var_310], esi
0x180005f6f  mov     [rsp+340h+var_318], rsi
0x180005f74  mov     [rsp+340h+var_320], rsi
0x180005f79  mov     esi, 2
0x180005f7e  mov     r9d, esi
0x180005f81  xor     r8d, r8d
0x180005f84  mov     rdx, rax
0x180005f87  mov     rcx, [rsp+340h+var_2F8]
0x180005f8c  mov     rax, r15
0x180005f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f94  mov     r9, rdi
0x180005f97  lea     r8, aFilename; "Filename"
0x180005f9e  xor     edx, edx
0x180005fa0  mov     rcx, [rsp+340h+var_2F8]
0x180005fa5  mov     rax, r14
0x180005fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fad  mov     r9, r13
0x180005fb0  lea     r8, aLineNumber; "Line number"
0x180005fb7  lea     edx, [rsi-1]
0x180005fba  mov     rcx, [rsp+340h+var_2F8]
0x180005fbf  mov     rax, r14
0x180005fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fc7  xor     r9d, r9d
0x180005fca  mov     r8d, 480h
0x180005fd0  mov     edx, esi
0x180005fd2  mov     rcx, [rsp+340h+var_2F8]
0x180005fd7  mov     rax, r12
0x180005fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fdf  mov     rcx, [rsp+340h+var_2F8]
0x180005fe4  mov     rax, rbx
0x180005fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fec  mov     r15d, [rsp+340h+var_300]
0x180005ff1  lea     rcx, [rsp+340h+hModule]
0x180005ff6  call    ?ReleasePtr@?$AutoCleanup@VAutoLibrary@@PEAUHINSTANCE__@@@@AEAAXXZ; AutoCleanup<AutoLibrary,HINSTANCE__ *>::ReleasePtr(void)
0x180005ffb  mov     ecx, r15d; dwErrCode
0x180005ffe  call    cs:__imp_SetLastError
0x180006004  mov     rcx, [rbp+240h+var_40]
0x18000600b  xor     rcx, rsp; StackCookie
0x18000600e  call    __security_check_cookie
0x180006013  mov     rbx, [rsp+340h+arg_8]
0x18000601b  add     rsp, 310h
0x180006022  pop     r15
0x180006024  pop     r14
0x180006026  pop     r13
0x180006028  pop     r12
0x18000602a  pop     rdi
0x18000602b  pop     rsi
0x18000602c  pop     rbp
0x18000602d  retn
```
