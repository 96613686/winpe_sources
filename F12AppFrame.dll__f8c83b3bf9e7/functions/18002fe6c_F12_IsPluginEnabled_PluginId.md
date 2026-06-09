# F12::IsPluginEnabled(PluginId)

- ea: `0x18002fe6c`
- end: `0x1800300b8`
- name: `?IsPluginEnabled@F12@@YA_NW4PluginId@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004120`
- `0x18002fac0`

## callees

- `0x180003858`
- `0x1800042a4`
- `0x18002fe6c`
- `0x180030314`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180030016`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003002a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180030016`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003002a`
- `ADVAPI32!RegCloseKey` at `0x18003005e`
- `ADVAPI32!RegCloseKey` at `0x180030091`
- `ADVAPI32!RegCloseKey` at `0x18003005e`
- `ADVAPI32!RegCloseKey` at `0x180030091`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ff1f`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ff1f`
- `ADVAPI32!RegQueryValueExW` at `0x18002ff58`
- `ADVAPI32!RegQueryValueExW` at `0x18002ff58`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall F12::IsPluginEnabled(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  const WCHAR *v8; // rbx
  HKEY v9; // rsi
  unsigned int v10; // r14d
  __int64 v11; // rax
  unsigned __int16 *v12; // rdi
  int v13; // eax
  __int64 v14; // rcx
  _QWORD v16[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int16 *cbData; // [rsp+88h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF

  v1 = a1 - 1;
  if ( !v1 )
  {
    v8 = L"EnableConsoleTool";
    goto LABEL_17;
  }
  v2 = v1 - 1;
  if ( !v2 )
  {
    v8 = L"EnableDomExplorerTool";
    goto LABEL_17;
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
    v8 = L"EnableDebuggerTool";
    goto LABEL_17;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v8 = L"EnableEmulationTool";
    goto LABEL_17;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v8 = L"EnableMemoryTool";
    goto LABEL_17;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v8 = L"EnableVisualProfilerTool";
    goto LABEL_17;
  }
  v7 = v6 - 3;
  if ( !v7 )
  {
    v8 = L"EnableNetworkTool";
LABEL_17:
    v9 = 0;
    v16[1] = 0;
    v16[2] = 0;
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\F12", 0, 0x20019u, &hKey) )
      goto LABEL_38;
    v9 = hKey;
    v16[0] = hKey;
    Type = 0;
    LODWORD(cbData) = 0;
    if ( RegQueryValueExW(hKey, v8, 0, &Type, 0, (LPDWORD)&cbData) || Type - 1 > 1 )
      goto LABEL_38;
    v10 = (unsigned int)cbData >> 1;
    Type = (unsigned int)cbData >> 1;
    v11 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
    v12 = (unsigned __int16 *)(v11 + 24);
    cbData = (unsigned __int16 *)(v11 + 24);
    if ( (((*(_DWORD *)(v11 + 12) - v10) | (1 - *(_DWORD *)(v11 + 16))) & 0x80000000) != 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&cbData);
      v12 = cbData;
    }
    v13 = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v16, v8, v12, &Type);
    if ( v12 )
    {
      v14 = -1;
      do
        ++v14;
      while ( v12[v14] );
      if ( (int)v14 < 0 )
        goto LABEL_41;
    }
    else
    {
      LODWORD(v14) = 0;
    }
    if ( (int)v14 <= *((_DWORD *)v12 - 3) )
    {
      *((_DWORD *)v12 - 4) = v14;
      v12[(unsigned int)v14] = 0;
      if ( !v13 && (!(unsigned int)_o__wcsicmp(v12, L"false") || !(unsigned int)_o__wcsicmp(v12, L"no")) )
      {
        if ( _InterlockedDecrement((volatile signed __int32 *)v12 - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
        if ( hKey )
          RegCloseKey(hKey);
        return 0;
      }
      if ( _InterlockedDecrement((volatile signed __int32 *)v12 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
LABEL_38:
      if ( v9 )
        RegCloseKey(v9);
      return 1;
    }
LABEL_41:
    ATL::AtlThrowImpl(-2147024809);
  }
  return v7 != 1;
}

```

## disassembly

```asm
0x18002fe6c  mov     [rsp-28h+arg_18], rbx
0x18002fe71  push    rbp
0x18002fe72  push    rsi
0x18002fe73  push    rdi
0x18002fe74  push    r14
0x18002fe76  push    r15
0x18002fe78  mov     rbp, rsp
0x18002fe7b  sub     rsp, 50h
0x18002fe7f  sub     ecx, 1
0x18002fe82  jz      short loc_18002FEE6
0x18002fe84  sub     ecx, 1
0x18002fe87  jz      short loc_18002FEDD
0x18002fe89  sub     ecx, 1
0x18002fe8c  jz      short loc_18002FED4
0x18002fe8e  sub     ecx, 1
0x18002fe91  jz      short loc_18002FECB
0x18002fe93  sub     ecx, 1
0x18002fe96  jz      short loc_18002FEC2
0x18002fe98  sub     ecx, 1
0x18002fe9b  jz      short loc_18002FEB9
0x18002fe9d  sub     ecx, 3
0x18002fea0  jz      short loc_18002FEB0
0x18002fea2  cmp     ecx, 1
0x18002fea5  jz      loc_180030064
0x18002feab  jmp     loc_180030097
0x18002feb0  lea     rbx, aEnablenetworkt; "EnableNetworkTool"
0x18002feb7  jmp     short loc_18002FEED
0x18002feb9  lea     rbx, aEnablevisualpr; "EnableVisualProfilerTool"
0x18002fec0  jmp     short loc_18002FEED
0x18002fec2  lea     rbx, aEnablememoryto; "EnableMemoryTool"
0x18002fec9  jmp     short loc_18002FEED
0x18002fecb  lea     rbx, aEnableemulatio; "EnableEmulationTool"
0x18002fed2  jmp     short loc_18002FEED
0x18002fed4  lea     rbx, aEnabledebugger; "EnableDebuggerTool"
0x18002fedb  jmp     short loc_18002FEED
0x18002fedd  lea     rbx, aEnabledomexplo; "EnableDomExplorerTool"
0x18002fee4  jmp     short loc_18002FEED
0x18002fee6  lea     rbx, aEnableconsolet; "EnableConsoleTool"
0x18002feed  xor     r15d, r15d
0x18002fef0  mov     esi, r15d
0x18002fef3  mov     [rbp+var_18], r15
0x18002fef7  mov     [rbp+var_10], r15
0x18002fefb  mov     [rbp+hKey], r15
0x18002feff  lea     rax, [rbp+hKey]
0x18002ff03  mov     [rsp+50h+phkResult], rax; phkResult
0x18002ff08  mov     r9d, 20019h; samDesired
0x18002ff0e  xor     r8d, r8d; ulOptions
0x18002ff11  lea     rdx, SubKey; "Software\\Microsoft\\F12"
0x18002ff18  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002ff1f  call    cs:__imp_RegOpenKeyExW
0x18002ff25  test    eax, eax
0x18002ff27  jnz     loc_180030089
0x18002ff2d  mov     rsi, [rbp+hKey]
0x18002ff31  mov     [rbp+var_20], rsi
0x18002ff35  mov     [rbp+Type], r15d
0x18002ff39  mov     dword ptr [rbp+cbData], r15d
0x18002ff3d  lea     rax, [rbp+cbData]
0x18002ff41  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002ff46  mov     [rsp+50h+phkResult], r15; lpData
0x18002ff4b  lea     r9, [rbp+Type]; lpType
0x18002ff4f  xor     r8d, r8d; lpReserved
0x18002ff52  mov     rdx, rbx; lpValueName
0x18002ff55  mov     rcx, rsi; hKey
0x18002ff58  call    cs:__imp_RegQueryValueExW
0x18002ff5e  test    eax, eax
0x18002ff60  jnz     loc_180030089
0x18002ff66  mov     eax, [rbp+Type]
0x18002ff69  dec     eax
0x18002ff6b  cmp     eax, 1
0x18002ff6e  ja      loc_180030089
0x18002ff74  mov     r14d, dword ptr [rbp+cbData]
0x18002ff78  shr     r14d, 1
0x18002ff7b  mov     [rbp+Type], r14d
0x18002ff7f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002ff86  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002ff8d  mov     rax, [rax+18h]
0x18002ff91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff96  lea     rdi, [rax+18h]
0x18002ff9a  mov     [rbp+cbData], rdi
0x18002ff9e  lea     ecx, [r15+1]
0x18002ffa2  sub     ecx, [rdi-8]
0x18002ffa5  mov     eax, [rdi-0Ch]
0x18002ffa8  sub     eax, r14d
0x18002ffab  or      ecx, eax
0x18002ffad  jge     short loc_18002FFBF
0x18002ffaf  mov     edx, r14d
0x18002ffb2  lea     rcx, [rbp+cbData]
0x18002ffb6  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002ffbb  mov     rdi, [rbp+cbData]
0x18002ffbf  lea     r9, [rbp+Type]; unsigned int *
0x18002ffc3  mov     r8, rdi; unsigned __int16 *
0x18002ffc6  mov     rdx, rbx; unsigned __int16 *
0x18002ffc9  lea     rcx, [rbp+var_20]; this
0x18002ffcd  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18002ffd2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002ffd6  test    rdi, rdi
0x18002ffd9  jnz     short loc_18002FFE0
0x18002ffdb  mov     ecx, r15d
0x18002ffde  jmp     short loc_18002FFF5
0x18002ffe0  mov     rcx, rbx
0x18002ffe3  inc     rcx
0x18002ffe6  cmp     [rdi+rcx*2], r15w
0x18002ffeb  jnz     short loc_18002FFE3
0x18002ffed  test    ecx, ecx
0x18002ffef  js      loc_1800300AD
0x18002fff5  cmp     ecx, [rdi-0Ch]
0x18002fff8  jg      loc_1800300AD
0x18002fffe  mov     [rdi-10h], ecx
0x180030001  mov     ecx, ecx
0x180030003  mov     [rdi+rcx*2], r15w
0x180030008  test    eax, eax
0x18003000a  jnz     short loc_180030068
0x18003000c  lea     rdx, aFalse; "false"
0x180030013  mov     rcx, rdi
0x180030016  call    cs:__imp__o__wcsicmp
0x18003001c  test    eax, eax
0x18003001e  jz      short loc_180030034
0x180030020  lea     rdx, aNo; "no"
0x180030027  mov     rcx, rdi
0x18003002a  call    cs:__imp__o__wcsicmp
0x180030030  test    eax, eax
0x180030032  jnz     short loc_180030068
0x180030034  lea     rdx, [rdi-18h]
0x180030038  mov     eax, ebx
0x18003003a  lock xadd [rdx+10h], eax
0x18003003f  add     eax, ebx
0x180030041  test    eax, eax
0x180030043  jg      short loc_180030055
0x180030045  mov     rcx, [rdx]
0x180030048  mov     rax, [rcx]
0x18003004b  mov     rax, [rax+8]
0x18003004f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030054  nop
0x180030055  mov     rcx, [rbp+hKey]; hKey
0x180030059  test    rcx, rcx
0x18003005c  jz      short loc_180030064
0x18003005e  call    cs:__imp_RegCloseKey
0x180030064  xor     al, al
0x180030066  jmp     short loc_180030099
0x180030068  lea     rdx, [rdi-18h]
0x18003006c  mov     eax, ebx
0x18003006e  lock xadd [rdx+10h], eax
0x180030073  add     eax, ebx
0x180030075  test    eax, eax
0x180030077  jg      short loc_180030089
0x180030079  mov     rcx, [rdx]
0x18003007c  mov     rax, [rcx]
0x18003007f  mov     rax, [rax+8]
0x180030083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030088  nop
0x180030089  test    rsi, rsi
0x18003008c  jz      short loc_180030097
0x18003008e  mov     rcx, rsi; hKey
0x180030091  call    cs:__imp_RegCloseKey
0x180030097  mov     al, 1
0x180030099  mov     rbx, [rsp+50h+arg_18]
0x1800300a1  add     rsp, 50h
0x1800300a5  pop     r15
0x1800300a7  pop     r14
0x1800300a9  pop     rdi
0x1800300aa  pop     rsi
0x1800300ab  pop     rbp
0x1800300ac  retn
0x1800300ad  mov     ecx, 80070057h; int
0x1800300b2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
