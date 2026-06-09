# IsDeviceAADDomainJoined(bool *,wchar_t * *)

- ea: `0x14003f0d8`
- end: `0x14003f440`
- name: `?IsDeviceAADDomainJoined@@YAJPEA_NPEAPEA_W@Z`
- size: `872`
- prototype: `__int64 __fastcall(bool *, wchar_t **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400364ac`

## callees

- `0x140003de4`
- `0x140008de4`
- `0x14000ce30`
- `0x1400116a4`
- `0x1400154b4`
- `0x1400177e0`
- `0x14003f0d8`
- `0x140044994`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003f415`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003f415`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003f1ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003f216`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003f1ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003f216`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003f1c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003f1c4`

## string_xrefs

- `0x14003f16d`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x14003f1bd`: `NetApi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall IsDeviceAADDomainJoined(bool *a1, wchar_t **a2)
{
  HMODULE v4; // rbx
  int v5; // edi
  __int64 v6; // rdx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rdi
  __int64 v9; // rax
  _WORD *v10; // rdx
  _WORD *v11; // rcx
  int v12; // eax
  int v14; // [rsp+20h] [rbp-49h]
  int v15; // [rsp+20h] [rbp-49h]
  __int64 v16; // [rsp+78h] [rbp+Fh] BYREF
  FARPROC v17; // [rsp+80h] [rbp+17h]
  unsigned int v18; // [rsp+88h] [rbp+1Fh]
  void *lpMem; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v18 = 0;
  v4 = 0;
  v16 = 0;
  v17 = 0;
  if ( !a1 )
  {
    v5 = -2147467261;
    v6 = 474;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\util.cpp",
      (const char *)(unsigned int)v5,
      v14);
    goto LABEL_32;
  }
  *a1 = 0;
  if ( a2 )
    *a2 = 0;
  if ( (unsigned int)AreTestKeysAllowed() )
  {
    LODWORD(lpMem) = 0;
    if ( (int)RegQueryDwordValue(
                -2147483646,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                L"IsDeviceAADDomainJoinedHROverride",
                &lpMem) >= 0 )
    {
      WUTrace(0, 0, 8, 4, 0, L"Test override for IsDeviceAADDomainJoined hr = 0x%08x");
      v5 = (int)lpMem;
      goto LABEL_32;
    }
  }
  Library = LoadLibraryExW(L"NetApi32.dll", 0, 0x800u);
  v4 = Library;
  if ( !Library )
  {
    v5 = -2145124297;
    v6 = 502;
    goto LABEL_18;
  }
  ProcAddress = GetProcAddress(Library, "NetGetAadJoinInformation");
  if ( !ProcAddress )
  {
    v5 = -2145124297;
    v6 = 506;
    goto LABEL_18;
  }
  v17 = GetProcAddress(v4, "NetFreeAadJoinInformation");
  if ( !v17 )
  {
    v5 = -2145124297;
    v6 = 510;
    goto LABEL_18;
  }
  v5 = ((__int64 (__fastcall *)(_QWORD, __int64 *))ProcAddress)(0, &v16);
  v18 = v5;
  if ( v5 < 0 )
  {
    WUTrace("IsDeviceAADDomainJoined", 513, 32, 3, 0, L"TelemetryAssert (%ws): %ws (0x%x, 0x%x)");
    WUTelemetryAssertTriggered(v18, 0);
    v5 = v18;
  }
  if ( v5 < 0 )
  {
    v6 = 514;
    goto LABEL_18;
  }
  v9 = v16;
  if ( !v16 || *(_DWORD *)v16 != 1 )
    goto LABEL_31;
  *a1 = 1;
  v10 = *(_WORD **)(v9 + 32);
  if ( !v10 || !*v10 )
  {
    WUTrace("IsDeviceAADDomainJoined", 523, 32, 3, 0, L"TelemetryAssert (%ws): %ws");
    WUTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
    v9 = v16;
  }
  if ( !a2 || (v11 = *(_WORD **)(v9 + 32)) == 0 || !*v11 )
  {
LABEL_31:
    WUTrace(0, 0, 32, 5, 0, L"AAD Joined is %d");
    v5 = 0;
    goto LABEL_32;
  }
  WUTrace(0, 0, 32, 5, 0, L"TenantId from NetGetAadJoinInformation: %ws");
  lpMem = 0;
  v12 = DuplicateString<wchar_t *,wchar_t *>(*(_QWORD *)(v16 + 32), &lpMem);
  v5 = v12;
  if ( v12 >= 0 )
  {
    *a2 = (wchar_t *)lpMem;
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x215,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\util.cpp",
    (const char *)(unsigned int)v12,
    v15);
  if ( lpMem )
    SusFree(lpMem);
LABEL_32:
  if ( (v18 & 0x80000000) == 0 && v17 )
    ((void (__fastcall *)(__int64))v17)(v16);
  if ( v4 )
    FreeLibrary(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14003f0d8  mov     [rsp-8+arg_10], rbx
0x14003f0dd  push    rbp
0x14003f0de  push    rsi
0x14003f0df  push    rdi
0x14003f0e0  push    r14
0x14003f0e2  push    r15
0x14003f0e4  lea     rbp, [rsp-37h]
0x14003f0e9  sub     rsp, 0A0h
0x14003f0f0  mov     rax, cs:__security_cookie
0x14003f0f7  xor     rax, rsp
0x14003f0fa  mov     [rbp+57h+var_28], rax
0x14003f0fe  mov     rsi, rdx
0x14003f101  mov     r14, rcx
0x14003f104  xor     r15d, r15d
0x14003f107  mov     [rbp+57h+var_38], r15d
0x14003f10b  mov     ebx, r15d
0x14003f10e  mov     [rbp+57h+var_70], rbx
0x14003f112  mov     [rbp+57h+var_48], r15
0x14003f116  mov     [rbp+57h+var_40], r15
0x14003f11a  lea     rax, [rbp+57h+var_38]
0x14003f11e  mov     [rbp+57h+var_68], rax
0x14003f122  lea     rax, [rbp+57h+var_40]
0x14003f126  mov     [rbp+57h+var_60], rax
0x14003f12a  lea     rax, [rbp+57h+var_48]
0x14003f12e  mov     [rbp+57h+var_58], rax
0x14003f132  mov     [rbp+57h+var_50], 1
0x14003f136  test    rcx, rcx
0x14003f139  jnz     short loc_14003F14A
0x14003f13b  mov     edi, 80004003h
0x14003f140  mov     edx, 1DAh
0x14003f145  jmp     loc_14003F2AB
0x14003f14a  mov     [rcx], r15b
0x14003f14d  test    rsi, rsi
0x14003f150  jz      short loc_14003F155
0x14003f152  mov     [rdx], r15
0x14003f155  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x14003f15a  test    eax, eax
0x14003f15c  jz      short loc_14003F1B5
0x14003f15e  mov     dword ptr [rbp+57h+lpMem], r15d
0x14003f162  lea     r9, [rbp+57h+lpMem]
0x14003f166  lea     r8, ?c_szIsDeviceAADDomainJoinedHROverride@@3QB_WB; "IsDeviceAADDomainJoinedHROverride"
0x14003f16d  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14003f174  mov     rcx, 0FFFFFFFF80000002h
0x14003f17b  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_W1PEAKW4RegistryHiveType@@@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,RegistryHiveType)
0x14003f180  test    eax, eax
0x14003f182  js      short loc_14003F1B5
0x14003f184  mov     eax, dword ptr [rbp+57h+lpMem]
0x14003f187  mov     dword ptr [rsp+0C0h+var_90], eax
0x14003f18b  lea     rax, aTestOverrideFo; "Test override for IsDeviceAADDomainJoin"...
0x14003f192  mov     [rsp+0C0h+var_98], rax
0x14003f197  mov     qword ptr [rsp+0C0h+var_A0], r15
0x14003f19c  xor     edx, edx
0x14003f19e  xor     ecx, ecx
0x14003f1a0  lea     r9d, [rdx+4]
0x14003f1a4  lea     r8d, [rdx+8]
0x14003f1a8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003f1ad  mov     edi, dword ptr [rbp+57h+lpMem]
0x14003f1b0  jmp     loc_14003F3F4
0x14003f1b5  xor     edx, edx; hFile
0x14003f1b7  mov     r8d, 800h; dwFlags
0x14003f1bd  lea     rcx, aNetapi32Dll; "NetApi32.dll"
0x14003f1c4  call    cs:__imp_LoadLibraryExW
0x14003f1ca  mov     rbx, rax
0x14003f1cd  mov     [rbp+57h+var_70], rax
0x14003f1d1  test    rax, rax
0x14003f1d4  jnz     short loc_14003F1E5
0x14003f1d6  mov     edi, 80240037h
0x14003f1db  mov     edx, 1F6h
0x14003f1e0  jmp     loc_14003F2AB
0x14003f1e5  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x14003f1ec  mov     rcx, rbx; hModule
0x14003f1ef  call    cs:__imp_GetProcAddress
0x14003f1f5  mov     rdi, rax
0x14003f1f8  test    rax, rax
0x14003f1fb  jnz     short loc_14003F20C
0x14003f1fd  mov     edi, 80240037h
0x14003f202  mov     edx, 1FAh
0x14003f207  jmp     loc_14003F2AB
0x14003f20c  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x14003f213  mov     rcx, rbx; hModule
0x14003f216  call    cs:__imp_GetProcAddress
0x14003f21c  mov     [rbp+57h+var_40], rax
0x14003f220  test    rax, rax
0x14003f223  jnz     short loc_14003F231
0x14003f225  mov     edi, 80240037h
0x14003f22a  mov     edx, 1FEh
0x14003f22f  jmp     short loc_14003F2AB
0x14003f231  lea     rdx, [rbp+57h+var_48]
0x14003f235  xor     ecx, ecx
0x14003f237  mov     rax, rdi
0x14003f23a  call    _guard_dispatch_icall
0x14003f23f  mov     edi, eax
0x14003f241  mov     [rbp+57h+var_38], eax
0x14003f244  test    eax, eax
0x14003f246  jns     short loc_14003F2A2
0x14003f248  mov     [rsp+0C0h+var_78], r15
0x14003f24d  mov     [rsp+0C0h+var_80], eax
0x14003f251  lea     rax, aNetgetaadjoini_0; "NetGetAadJoinInformation failed"
0x14003f258  mov     [rsp+0C0h+var_88], rax
0x14003f25d  lea     rax, aHresultHrgetaa; "(((HRESULT)(hrGetAADInfo)) >= 0)"
0x14003f264  mov     [rsp+0C0h+var_90], rax
0x14003f269  lea     rax, aTelemetryasser_0; "TelemetryAssert (%ws): %ws (0x%x, 0x%x)"
0x14003f270  mov     [rsp+0C0h+var_98], rax
0x14003f275  mov     qword ptr [rsp+0C0h+var_A0], r15; int
0x14003f27a  mov     edx, 201h
0x14003f27f  mov     r9d, 3
0x14003f285  lea     r8d, [r9+1Dh]
0x14003f289  lea     rcx, aIsdeviceaaddom; "IsDeviceAADDomainJoined"
0x14003f290  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003f295  xor     edx, edx; unsigned int
0x14003f297  mov     ecx, [rbp+57h+var_38]; unsigned int
0x14003f29a  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x14003f29f  mov     edi, [rbp+57h+var_38]
0x14003f2a2  test    edi, edi
0x14003f2a4  jns     short loc_14003F2C3
0x14003f2a6  mov     edx, 202h; void *
0x14003f2ab  mov     rcx, [rbp+5Fh]; this
0x14003f2af  mov     r9d, edi; char *
0x14003f2b2  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003f2b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f2be  jmp     loc_14003F3F4
0x14003f2c3  mov     rax, [rbp+57h+var_48]
0x14003f2c7  test    rax, rax
0x14003f2ca  jz      loc_14003F3C7
0x14003f2d0  cmp     dword ptr [rax], 1
0x14003f2d3  jnz     loc_14003F3C7
0x14003f2d9  mov     byte ptr [r14], 1
0x14003f2dd  mov     rdx, [rax+20h]
0x14003f2e1  test    rdx, rdx
0x14003f2e4  jz      short loc_14003F2EC
0x14003f2e6  cmp     [rdx], r15w
0x14003f2ea  jnz     short loc_14003F33E
0x14003f2ec  lea     rax, aEmptyTenantidF; "Empty tenantId for AAD joined device"
0x14003f2f3  mov     [rsp+0C0h+var_88], rax
0x14003f2f8  lea     rax, aIsstrnulloremp; "!IsStrNullOrEmpty(deviceJoinInfoPtr->ps"...
0x14003f2ff  mov     [rsp+0C0h+var_90], rax
0x14003f304  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x14003f30b  mov     [rsp+0C0h+var_98], rax
0x14003f310  mov     qword ptr [rsp+0C0h+var_A0], r15
0x14003f315  mov     edx, 20Bh
0x14003f31a  mov     r9d, 3
0x14003f320  lea     r8d, [r9+1Dh]
0x14003f324  lea     rcx, aIsdeviceaaddom; "IsDeviceAADDomainJoined"
0x14003f32b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003f330  or      ecx, 0FFFFFFFFh; unsigned int
0x14003f333  mov     edx, ecx; unsigned int
0x14003f335  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x14003f33a  mov     rax, [rbp+57h+var_48]
0x14003f33e  test    rsi, rsi
0x14003f341  jz      loc_14003F3C7
0x14003f347  mov     rcx, [rax+20h]
0x14003f34b  test    rcx, rcx
0x14003f34e  jz      short loc_14003F3C7
0x14003f350  cmp     [rcx], r15w
0x14003f354  jz      short loc_14003F3C7
0x14003f356  mov     [rsp+0C0h+var_90], rcx
0x14003f35b  lea     rax, aTenantidFromNe; "TenantId from NetGetAadJoinInformation:"...
0x14003f362  mov     [rsp+0C0h+var_98], rax
0x14003f367  mov     qword ptr [rsp+0C0h+var_A0], r15; int
0x14003f36c  xor     edx, edx
0x14003f36e  xor     ecx, ecx
0x14003f370  lea     r9d, [rdx+5]
0x14003f374  lea     r8d, [rdx+20h]
0x14003f378  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003f37d  mov     [rbp+57h+lpMem], r15
0x14003f381  lea     rdx, [rbp+57h+lpMem]
0x14003f385  mov     rcx, [rbp+57h+var_48]
0x14003f389  mov     rcx, [rcx+20h]
0x14003f38d  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x14003f392  mov     edi, eax
0x14003f394  test    eax, eax
0x14003f396  jns     short loc_14003F3C0
0x14003f398  mov     rcx, [rbp+5Fh]; this
0x14003f39c  mov     r9d, eax; char *
0x14003f39f  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003f3a6  mov     edx, 215h; void *
0x14003f3ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f3b0  mov     rcx, [rbp+57h+lpMem]; lpMem
0x14003f3b4  test    rcx, rcx
0x14003f3b7  jz      short loc_14003F3F4
0x14003f3b9  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14003f3be  jmp     short loc_14003F3F4
0x14003f3c0  mov     rax, [rbp+57h+lpMem]
0x14003f3c4  mov     [rsi], rax
0x14003f3c7  movzx   eax, byte ptr [r14]
0x14003f3cb  mov     dword ptr [rsp+0C0h+var_90], eax
0x14003f3cf  lea     rax, aAadJoinedIsD; "AAD Joined is %d"
0x14003f3d6  mov     [rsp+0C0h+var_98], rax
0x14003f3db  mov     qword ptr [rsp+0C0h+var_A0], r15
0x14003f3e0  xor     edx, edx
0x14003f3e2  xor     ecx, ecx
0x14003f3e4  lea     r9d, [rdx+5]
0x14003f3e8  lea     r8d, [rdx+20h]
0x14003f3ec  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003f3f1  mov     edi, r15d
0x14003f3f4  cmp     [rbp+57h+var_38], r15d
0x14003f3f8  jl      short loc_14003F40D
0x14003f3fa  mov     rax, [rbp+57h+var_40]
0x14003f3fe  test    rax, rax
0x14003f401  jz      short loc_14003F40D
0x14003f403  mov     rcx, [rbp+57h+var_48]
0x14003f407  call    _guard_dispatch_icall
0x14003f40c  nop
0x14003f40d  test    rbx, rbx
0x14003f410  jz      short loc_14003F41B
0x14003f412  mov     rcx, rbx; hLibModule
0x14003f415  call    cs:__imp_FreeLibrary
0x14003f41b  mov     eax, edi
0x14003f41d  mov     rcx, [rbp+57h+var_28]
0x14003f421  xor     rcx, rsp; StackCookie
0x14003f424  call    __security_check_cookie
0x14003f429  mov     rbx, [rsp+0C0h+arg_10]
0x14003f431  add     rsp, 0A0h
0x14003f438  pop     r15
0x14003f43a  pop     r14
0x14003f43c  pop     rdi
0x14003f43d  pop     rsi
0x14003f43e  pop     rbp
0x14003f43f  retn
```
