# InitCfgWriterThread(void *)

- ea: `0x180007120`
- end: `0x180007373`
- name: `?InitCfgWriterThread@@YAKPEAX@Z`
- size: `595`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180007120`
- `0x18000737c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007155`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007155`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007360`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007360`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800071be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007213`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800071be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007213`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007185`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007185`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800071dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000722c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800071dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000722c`
- `iisutil!PuDbgPrint` at `0x18000729b`
- `iisutil!PuDbgPrint` at `0x18000735a`
- `iisutil!PuDbgPrint` at `0x18000729b`
- `iisutil!PuDbgPrint` at `0x18000735a`

## string_xrefs

- `0x18000728f`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\cfgwriter.cxx`
- `0x180007353`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\cfgwriter.cxx`
- `0x18000733a`: `Error on creating the writer object, out of memory\n`
- `0x180007288`: `InitCfgWriterThread`
- `0x180007341`: `InitCfgWriterThread`
- `0x180007274`: `Error on initializing the writer object\n`
- `0x180007308`: `Error on subscribing the writer object\n`

## pseudocode

```c
__int64 __fastcall InitCfgWriterThread(PVOID Parameter)
{
  HRESULT v1; // ebx
  HKEY v2; // rax
  __int64 v3; // rcx
  BYTE v5[8]; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+18h] BYREF
  DWORD Type; // [rsp+70h] [rbp+20h] BYREF
  int Data; // [rsp+78h] [rbp+28h] BYREF

  hKey[0] = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  *(_DWORD *)v5 = 0;
  v1 = CoInitializeEx(0, 0);
  if ( v1 >= 0 )
  {
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 1u, hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey[0], L"SystemSetupInProgress", 0, &Type, (LPBYTE)&Data, &cbData)
        && Type == 4
        && cbData == 4
        && Data
        || (cbData = 4, !RegQueryValueExW(hKey[0], L"UpgradeInProgress", 0, &Type, v5, &cbData))
        && Type == 4
        && *(_DWORD *)v5 )
      {
        RegCloseKey(hKey[0]);
        goto LABEL_26;
      }
      RegCloseKey(hKey[0]);
    }
    v2 = (HKEY)operator new(0x10u);
    hKey[1] = v2;
    if ( !v2 )
    {
      v1 = -2147024888;
      g_pIISCfgVssWriter = 0;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\cfgwriter.cxx",
          592,
          "InitCfgWriterThread",
          "Error on creating the writer object, out of memory\n");
      goto LABEL_26;
    }
    *((_QWORD *)v2 + 1) = 0;
    *(_QWORD *)v2 = &CIISCfgVssWriter::`vftable';
    g_pIISCfgVssWriter = (struct CIISCfgVssWriter *)v2;
    if ( !(unsigned int)CIISCfgVssWriter::Initialize((CIISCfgVssWriter *)&CIISCfgVssWriter::`vftable') )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\cfgwriter.cxx",
          606,
          "InitCfgWriterThread",
          "Error on initializing the writer object\n");
LABEL_16:
      if ( g_pIISCfgVssWriter )
        (**(void (__fastcall ***)(struct CIISCfgVssWriter *, __int64))g_pIISCfgVssWriter)(g_pIISCfgVssWriter, 1);
      g_pIISCfgVssWriter = 0;
      goto LABEL_26;
    }
    v3 = *((_QWORD *)g_pIISCfgVssWriter + 1);
    if ( !v3 || (*(int (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v3 + 32LL))(v3, 0, 6) < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\cfgwriter.cxx",
          622,
          "InitCfgWriterThread",
          "Error on subscribing the writer object\n");
      goto LABEL_16;
    }
    g_fCfgWriterSubscribed = 1;
LABEL_26:
    CoUninitialize();
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180007120  mov     [rsp-8+arg_0], rbx
0x180007125  push    rbp
0x180007126  mov     rbp, rsp
0x180007129  sub     rsp, 50h
0x18000712d  xor     edx, edx; dwCoInit
0x18000712f  mov     [rbp+hKey], 0
0x180007137  xor     ecx, ecx; pvReserved
0x180007139  mov     [rbp+Type], 0
0x180007140  mov     [rbp+cbData], 0
0x180007147  mov     [rbp+Data], 0
0x18000714e  mov     dword ptr [rbp+var_20], 0
0x180007155  call    cs:__imp_CoInitializeEx
0x18000715b  mov     ebx, eax
0x18000715d  test    eax, eax
0x18000715f  js      loc_180007366
0x180007165  lea     rax, [rbp+hKey]
0x180007169  mov     r9d, 1; samDesired
0x18000716f  xor     r8d, r8d; ulOptions
0x180007172  mov     [rsp+50h+phkResult], rax; phkResult
0x180007177  lea     rdx, SubKey; "SYSTEM\\Setup"
0x18000717e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007185  call    cs:__imp_RegOpenKeyExW
0x18000718b  test    eax, eax
0x18000718d  jnz     loc_180007232
0x180007193  mov     rcx, [rbp+hKey]; hKey
0x180007197  lea     rax, [rbp+cbData]
0x18000719b  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800071a0  lea     r9, [rbp+Type]; lpType
0x1800071a4  lea     rax, [rbp+Data]
0x1800071a8  mov     [rbp+cbData], 4
0x1800071af  xor     r8d, r8d; lpReserved
0x1800071b2  mov     [rsp+50h+phkResult], rax; lpData
0x1800071b7  lea     rdx, ValueName; "SystemSetupInProgress"
0x1800071be  call    cs:__imp_RegQueryValueExW
0x1800071c4  test    eax, eax
0x1800071c6  jnz     short loc_1800071E8
0x1800071c8  cmp     [rbp+Type], 4
0x1800071cc  jnz     short loc_1800071E8
0x1800071ce  cmp     [rbp+cbData], 4
0x1800071d2  jnz     short loc_1800071E8
0x1800071d4  cmp     [rbp+Data], eax
0x1800071d7  jz      short loc_1800071E8
0x1800071d9  mov     rcx, [rbp+hKey]; hKey
0x1800071dd  call    cs:__imp_RegCloseKey
0x1800071e3  jmp     loc_180007360
0x1800071e8  mov     rcx, [rbp+hKey]; hKey
0x1800071ec  lea     rax, [rbp+cbData]
0x1800071f0  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800071f5  lea     r9, [rbp+Type]; lpType
0x1800071f9  lea     rax, [rbp+var_20]
0x1800071fd  mov     [rbp+cbData], 4
0x180007204  xor     r8d, r8d; lpReserved
0x180007207  mov     [rsp+50h+phkResult], rax; lpData
0x18000720c  lea     rdx, aUpgradeinprogr; "UpgradeInProgress"
0x180007213  call    cs:__imp_RegQueryValueExW
0x180007219  test    eax, eax
0x18000721b  jnz     short loc_180007228
0x18000721d  cmp     [rbp+Type], 4
0x180007221  jnz     short loc_180007228
0x180007223  cmp     dword ptr [rbp+var_20], eax
0x180007226  jnz     short loc_1800071D9
0x180007228  mov     rcx, [rbp+hKey]; hKey
0x18000722c  call    cs:__imp_RegCloseKey
0x180007232  mov     ecx, 10h; Size
0x180007237  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000723c  mov     [rbp+var_10], rax
0x180007240  test    rax, rax
0x180007243  jz      loc_18000731A
0x180007249  lea     rcx, ??_7CIISCfgVssWriter@@6B@; this
0x180007250  mov     qword ptr [rax+8], 0
0x180007258  mov     [rax], rcx
0x18000725b  mov     cs:?g_pIISCfgVssWriter@@3PEAVCIISCfgVssWriter@@EA, rax; CIISCfgVssWriter * g_pIISCfgVssWriter
0x180007262  call    ?Initialize@CIISCfgVssWriter@@QEAAHXZ; CIISCfgVssWriter::Initialize(void)
0x180007267  test    eax, eax
0x180007269  jnz     short loc_1800072CD
0x18000726b  test    byte ptr cs:g_dwDebugFlags, 3
0x180007272  jz      short loc_1800072A1
0x180007274  lea     rax, aErrorOnInitial; "Error on initializing the writer object"...
0x18000727b  mov     r8d, 25Eh
0x180007281  mov     rcx, cs:g_pDebug
0x180007288  lea     r9, aInitcfgwritert; "InitCfgWriterThread"
0x18000728f  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007296  mov     [rsp+50h+phkResult], rax
0x18000729b  call    cs:__imp_PuDbgPrint
0x1800072a1  mov     rcx, cs:?g_pIISCfgVssWriter@@3PEAVCIISCfgVssWriter@@EA; CIISCfgVssWriter * g_pIISCfgVssWriter
0x1800072a8  test    rcx, rcx
0x1800072ab  jz      short loc_1800072BD
0x1800072ad  mov     rax, [rcx]
0x1800072b0  mov     edx, 1
0x1800072b5  mov     rax, [rax]
0x1800072b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072bd  mov     cs:?g_pIISCfgVssWriter@@3PEAVCIISCfgVssWriter@@EA, 0; CIISCfgVssWriter * g_pIISCfgVssWriter
0x1800072c8  jmp     loc_180007360
0x1800072cd  mov     rax, cs:?g_pIISCfgVssWriter@@3PEAVCIISCfgVssWriter@@EA; CIISCfgVssWriter * g_pIISCfgVssWriter
0x1800072d4  mov     rcx, [rax+8]
0x1800072d8  test    rcx, rcx
0x1800072db  jz      short loc_1800072FF
0x1800072dd  mov     rax, [rcx]
0x1800072e0  xor     edx, edx
0x1800072e2  mov     rax, [rax+20h]
0x1800072e6  lea     r8d, [rdx+6]
0x1800072ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072ef  test    eax, eax
0x1800072f1  js      short loc_1800072FF
0x1800072f3  mov     cs:?g_fCfgWriterSubscribed@@3HA, 1; int g_fCfgWriterSubscribed
0x1800072fd  jmp     short loc_180007360
0x1800072ff  test    byte ptr cs:g_dwDebugFlags, 3
0x180007306  jz      short loc_1800072A1
0x180007308  lea     rax, aErrorOnSubscri; "Error on subscribing the writer object"...
0x18000730f  mov     r8d, 26Eh
0x180007315  jmp     loc_180007281
0x18000731a  test    byte ptr cs:g_dwDebugFlags, 3
0x180007321  mov     ebx, 80070008h
0x180007326  mov     cs:?g_pIISCfgVssWriter@@3PEAVCIISCfgVssWriter@@EA, 0; CIISCfgVssWriter * g_pIISCfgVssWriter
0x180007331  jz      short loc_180007360
0x180007333  mov     rcx, cs:g_pDebug
0x18000733a  lea     rax, aErrorOnCreatin; "Error on creating the writer object, ou"...
0x180007341  lea     r9, aInitcfgwritert; "InitCfgWriterThread"
0x180007348  mov     [rsp+50h+phkResult], rax
0x18000734d  mov     r8d, 250h
0x180007353  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000735a  call    cs:__imp_PuDbgPrint
0x180007360  call    cs:__imp_CoUninitialize
0x180007366  mov     eax, ebx
0x180007368  mov     rbx, [rsp+50h+arg_0]
0x18000736d  add     rsp, 50h
0x180007371  pop     rbp
0x180007372  retn
```
