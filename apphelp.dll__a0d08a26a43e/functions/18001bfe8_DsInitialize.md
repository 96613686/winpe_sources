# DsInitialize

- ea: `0x18001bfe8`
- end: `0x18001c318`
- name: `DsInitialize`
- size: `816`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b8a0`
- `0x18001bb20`
- `0x18001bdd0`
- `0x180033310`
- `0x1800541d0`
- `0x1800552d0`
- `0x1800559a0`
- `0x180055db0`

## callees

- `0x18000f114`
- `0x180017794`
- `0x180018a14`
- `0x18001bfe8`
- `0x18001c320`
- `0x18001c370`
- `0x18001c48c`
- `0x18001df70`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x18001c113`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001c113`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001c144`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001c144`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c0c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c0c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001c0e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001c0e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c300`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c192`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c192`

## string_xrefs

- `0x18001c0b4`: `Created ShortRunApp telemetry`
- `0x18001c08b`: `Created MessageBoxError telemetry`
- `0x18001c306`: `Failed to get the executable path [%d]`

## pseudocode

```c
__int64 DsInitialize()
{
  unsigned int v0; // ebx
  HMODULE ModuleHandleW; // rax
  HMODULE v3; // rbx
  __int64 v4; // rsi
  __int64 *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 *v8; // rcx
  ULONGLONG *p_TickCount64; // rax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int64 v20; // rax
  DWORD LastError; // eax
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  __int64 v26; // rcx
  bool v27; // zf
  __int64 *v28; // [rsp+30h] [rbp-D0h] BYREF
  char v29[8]; // [rsp+38h] [rbp-C8h] BYREF
  ULONGLONG TickCount64; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE v31; // [rsp+48h] [rbp-B8h]
  WCHAR Filename[260]; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+258h] [rbp+158h]
  STRSAFE_LPWSTR v34; // [rsp+260h] [rbp+160h]
  int v35; // [rsp+274h] [rbp+174h]

  if ( dword_1800810D0 )
    return 0;
  v0 = dword_1800810D4;
  if ( dword_1800810D4 )
  {
LABEL_24:
    dword_1800810D4 = v0;
    return v0;
  }
  memset_0(&TickCount64, 0, 0x238u);
  AslLogCreate(&g_TraceLog, (__int64)"DetectorsTrace", 0x400u);
  if ( !g_MbTelemetry )
  {
    AslTelemetryCreate(&g_MbTelemetry, "MessageBoxError");
    DsTracePrintf("Created MessageBoxError telemetry");
  }
  if ( !g_SrTelemetry )
  {
    AslTelemetryCreate(&g_SrTelemetry, "ShortRunApp");
    DsTracePrintf("Created ShortRunApp telemetry");
  }
  ModuleHandleW = GetModuleHandleW(0);
  v31 = ModuleHandleW;
  if ( !ModuleHandleW )
  {
    LastError = GetLastError();
    v22 = "GetModuleHandle(NULL) failed [%d]";
    v23 = 194;
    goto LABEL_23;
  }
  if ( GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    v22 = "Failed to get the executable path [%d]";
    v23 = 204;
LABEL_23:
    v0 = LastError;
    AslLogCallPrintf(1, "DsInitialize", v23, v22, LastError);
    if ( !v0 )
      return v0;
    goto LABEL_24;
  }
  v3 = v31;
  v28 = 0;
  v4 = *(_QWORD *)(g_Engine + 40);
  RtlAcquireSRWLockShared(v4);
  SepModuleTrackerFindModule(&v28, v29, v4, v3);
  v5 = v28;
  if ( v28 )
  {
    v0 = 0;
    v33 = *((_DWORD *)v28 + 2);
    v5 = (__int64 *)*v28;
  }
  else
  {
    v0 = -1073741515;
  }
  RtlReleaseSRWLockShared(v4);
  if ( v0 )
  {
    v24 = "SeModuleTrackerLookup failed [%d]";
    v25 = 213;
    v26 = 1;
LABEL_28:
    AslLogCallPrintf(v26, "DsInitialize", v25, v24, v0);
    goto LABEL_24;
  }
  if ( (unsigned int)DsIsExcluded(Filename) )
  {
    v0 = 50;
    v24 = "Excluded from monitoring [%d]";
    v25 = 225;
    v26 = 2;
    goto LABEL_28;
  }
  v6 = RtlpImageNtHeader(v5[6]);
  if ( !v6 )
  {
    AslLogCallPrintf(1, "DsInitialize", 235, "Bad header");
    return v0;
  }
  if ( *(_BYTE *)(v6 + 26) != 83 || (v27 = *(_BYTE *)(v6 + 27) == 82, v35 = 1, !v27) )
    v35 = 0;
  TickCount64 = GetTickCount64();
  v7 = 4;
  v8 = &g_DsSharedData;
  v34 = g_CompatLayers;
  p_TickCount64 = &TickCount64;
  do
  {
    v10 = *((_OWORD *)p_TickCount64 + 1);
    *(_OWORD *)v8 = *(_OWORD *)p_TickCount64;
    v11 = *((_OWORD *)p_TickCount64 + 2);
    *((_OWORD *)v8 + 1) = v10;
    v12 = *((_OWORD *)p_TickCount64 + 3);
    *((_OWORD *)v8 + 2) = v11;
    v13 = *((_OWORD *)p_TickCount64 + 4);
    *((_OWORD *)v8 + 3) = v12;
    v14 = *((_OWORD *)p_TickCount64 + 5);
    *((_OWORD *)v8 + 4) = v13;
    v15 = *((_OWORD *)p_TickCount64 + 6);
    *((_OWORD *)v8 + 5) = v14;
    v16 = *((_OWORD *)p_TickCount64 + 7);
    p_TickCount64 += 16;
    *((_OWORD *)v8 + 6) = v15;
    *((_OWORD *)v8 + 7) = v16;
    v8 += 16;
    --v7;
  }
  while ( v7 );
  v17 = *(_OWORD *)p_TickCount64;
  dword_1800810D0 = 1;
  v18 = *((_OWORD *)p_TickCount64 + 1);
  *(_OWORD *)v8 = v17;
  v19 = *((_OWORD *)p_TickCount64 + 2);
  v20 = p_TickCount64[6];
  *((_OWORD *)v8 + 1) = v18;
  *((_OWORD *)v8 + 2) = v19;
  v8[6] = v20;
  return 0;
}

```

## disassembly

```asm
0x18001bfe8  push    rbp
0x18001bfea  push    rbx
0x18001bfeb  push    rsi
0x18001bfec  push    rdi
0x18001bfed  lea     rbp, [rsp-198h]
0x18001bff5  sub     rsp, 298h
0x18001bffc  mov     rax, cs:__security_cookie
0x18001c003  xor     rax, rsp
0x18001c006  mov     [rbp+1B0h+var_30], rax
0x18001c00d  cmp     cs:dword_1800810D0, 0
0x18001c014  jz      short loc_18001C035
0x18001c016  xor     ebx, ebx
0x18001c018  mov     eax, ebx
0x18001c01a  mov     rcx, [rbp+1B0h+var_30]
0x18001c021  xor     rcx, rsp; StackCookie
0x18001c024  call    __security_check_cookie
0x18001c029  add     rsp, 298h
0x18001c030  pop     rdi
0x18001c031  pop     rsi
0x18001c032  pop     rbx
0x18001c033  pop     rbp
0x18001c034  retn
0x18001c035  mov     ebx, cs:dword_1800810D4
0x18001c03b  test    ebx, ebx
0x18001c03d  jnz     loc_18001C28C
0x18001c043  xor     edx, edx; Val
0x18001c045  lea     rcx, [rsp+2B0h+var_270]; void *
0x18001c04a  mov     r8d, 238h; Size
0x18001c050  call    memset_0
0x18001c055  mov     r8d, 400h
0x18001c05b  lea     rdx, aDetectorstrace; "DetectorsTrace"
0x18001c062  lea     rcx, g_TraceLog
0x18001c069  call    AslLogCreate
0x18001c06e  cmp     cs:g_MbTelemetry, 0
0x18001c076  jnz     short loc_18001C097
0x18001c078  lea     rdx, aMessageboxerro; "MessageBoxError"
0x18001c07f  lea     rcx, g_MbTelemetry
0x18001c086  call    AslTelemetryCreate
0x18001c08b  lea     rcx, aCreatedMessage; "Created MessageBoxError telemetry"
0x18001c092  call    DsTracePrintf
0x18001c097  cmp     cs:g_SrTelemetry, 0
0x18001c09f  jnz     short loc_18001C0C0
0x18001c0a1  lea     rdx, aShortrunapp; "ShortRunApp"
0x18001c0a8  lea     rcx, g_SrTelemetry
0x18001c0af  call    AslTelemetryCreate
0x18001c0b4  lea     rcx, aCreatedShortru; "Created ShortRunApp telemetry"
0x18001c0bb  call    DsTracePrintf
0x18001c0c0  xor     ecx, ecx; lpModuleName
0x18001c0c2  call    cs:__imp_GetModuleHandleW
0x18001c0c8  mov     [rsp+2B0h+var_268], rax
0x18001c0cd  test    rax, rax
0x18001c0d0  jz      loc_18001C297
0x18001c0d6  mov     r8d, 104h; nSize
0x18001c0dc  lea     rdx, [rsp+2B0h+Filename]; lpFilename
0x18001c0e1  mov     rcx, rax; hModule
0x18001c0e4  call    cs:__imp_GetModuleFileNameW
0x18001c0ea  dec     eax
0x18001c0ec  cmp     eax, 102h
0x18001c0f1  ja      loc_18001C300
0x18001c0f7  mov     rax, cs:g_Engine
0x18001c0fe  mov     rbx, [rsp+2B0h+var_268]
0x18001c103  mov     [rsp+2B0h+var_280], 0
0x18001c10c  mov     rsi, [rax+28h]
0x18001c110  mov     rcx, rsi
0x18001c113  call    cs:__imp_RtlAcquireSRWLockShared
0x18001c119  mov     r9, rbx
0x18001c11c  lea     rdx, [rsp+2B0h+var_278]
0x18001c121  mov     r8, rsi
0x18001c124  lea     rcx, [rsp+2B0h+var_280]
0x18001c129  call    SepModuleTrackerFindModule
0x18001c12e  mov     rdi, [rsp+2B0h+var_280]
0x18001c133  test    rdi, rdi
0x18001c136  jnz     loc_18001C237
0x18001c13c  mov     ebx, 0C0000135h
0x18001c141  mov     rcx, rsi
0x18001c144  call    cs:__imp_RtlReleaseSRWLockShared
0x18001c14a  test    ebx, ebx
0x18001c14c  jnz     loc_18001C2AC
0x18001c152  mov     r8d, [rdi+40h]
0x18001c156  lea     rcx, [rsp+2B0h+Filename]; Str
0x18001c15b  mov     rdx, [rdi+30h]
0x18001c15f  call    DsIsExcluded
0x18001c164  test    eax, eax
0x18001c166  jnz     loc_18001C2C0
0x18001c16c  mov     rcx, [rdi+30h]
0x18001c170  call    RtlpImageNtHeader
0x18001c175  test    rax, rax
0x18001c178  jz      loc_18001C24A
0x18001c17e  cmp     byte ptr [rax+1Ah], 53h ; 'S'
0x18001c182  jz      loc_18001C2E7
0x18001c188  mov     [rbp+1B0h+var_3C], 0
0x18001c192  call    cs:__imp_GetTickCount64
0x18001c198  mov     [rsp+2B0h+var_270], rax
0x18001c19d  mov     edx, 4
0x18001c1a2  mov     rax, cs:g_CompatLayers
0x18001c1a9  lea     rcx, g_DsSharedData
0x18001c1b0  mov     [rbp+1B0h+var_50], rax
0x18001c1b7  lea     rax, [rsp+2B0h+var_270]
0x18001c1bc  lea     r8d, [rdx+7Ch]
0x18001c1c0  movups  xmm0, xmmword ptr [rax]
0x18001c1c3  movups  xmm1, xmmword ptr [rax+10h]
0x18001c1c7  movups  xmmword ptr [rcx], xmm0
0x18001c1ca  movups  xmm0, xmmword ptr [rax+20h]
0x18001c1ce  movups  xmmword ptr [rcx+10h], xmm1
0x18001c1d2  movups  xmm1, xmmword ptr [rax+30h]
0x18001c1d6  movups  xmmword ptr [rcx+20h], xmm0
0x18001c1da  movups  xmm0, xmmword ptr [rax+40h]
0x18001c1de  movups  xmmword ptr [rcx+30h], xmm1
0x18001c1e2  movups  xmm1, xmmword ptr [rax+50h]
0x18001c1e6  movups  xmmword ptr [rcx+40h], xmm0
0x18001c1ea  movups  xmm0, xmmword ptr [rax+60h]
0x18001c1ee  movups  xmmword ptr [rcx+50h], xmm1
0x18001c1f2  movups  xmm1, xmmword ptr [rax+70h]
0x18001c1f6  add     rax, r8
0x18001c1f9  movups  xmmword ptr [rcx+60h], xmm0
0x18001c1fd  movups  xmmword ptr [rcx+70h], xmm1
0x18001c201  add     rcx, r8
0x18001c204  sub     rdx, 1
0x18001c208  jnz     short loc_18001C1C0
0x18001c20a  movups  xmm0, xmmword ptr [rax]
0x18001c20d  mov     cs:dword_1800810D0, 1
0x18001c217  movups  xmm1, xmmword ptr [rax+10h]
0x18001c21b  movups  xmmword ptr [rcx], xmm0
0x18001c21e  movups  xmm0, xmmword ptr [rax+20h]
0x18001c222  mov     rax, [rax+30h]
0x18001c226  movups  xmmword ptr [rcx+10h], xmm1
0x18001c22a  movups  xmmword ptr [rcx+20h], xmm0
0x18001c22e  mov     [rcx+30h], rax
0x18001c232  jmp     loc_18001C016
0x18001c237  mov     eax, [rdi+8]
0x18001c23a  xor     ebx, ebx
0x18001c23c  mov     [rbp+1B0h+var_58], eax
0x18001c242  mov     rdi, [rdi]
0x18001c245  jmp     loc_18001C141
0x18001c24a  lea     r9, aBadHeader; "Bad header"
0x18001c251  mov     r8d, 0EBh
0x18001c257  lea     rdx, aDsinitialize; "DsInitialize"
0x18001c25e  mov     ecx, 1
0x18001c263  call    AslLogCallPrintf
0x18001c268  jmp     loc_18001C018
0x18001c26d  lea     rdx, aDsinitialize; "DsInitialize"
0x18001c274  mov     [rsp+2B0h+var_290], eax
0x18001c278  mov     ecx, 1
0x18001c27d  mov     ebx, eax
0x18001c27f  call    AslLogCallPrintf
0x18001c284  test    ebx, ebx
0x18001c286  jz      loc_18001C018
0x18001c28c  mov     cs:dword_1800810D4, ebx
0x18001c292  jmp     loc_18001C018
0x18001c297  call    cs:__imp_GetLastError
0x18001c29d  lea     r9, aGetmodulehandl; "GetModuleHandle(NULL) failed [%d]"
0x18001c2a4  mov     r8d, 0C2h
0x18001c2aa  jmp     short loc_18001C26D
0x18001c2ac  lea     r9, aSemoduletracke; "SeModuleTrackerLookup failed [%d]"
0x18001c2b3  mov     r8d, 0D5h
0x18001c2b9  mov     ecx, 1
0x18001c2be  jmp     short loc_18001C2D5
0x18001c2c0  mov     ebx, 32h ; '2'
0x18001c2c5  lea     r9, aExcludedFromMo; "Excluded from monitoring [%d]"
0x18001c2cc  mov     r8d, 0E1h
0x18001c2d2  lea     ecx, [rbx-30h]
0x18001c2d5  lea     rdx, aDsinitialize; "DsInitialize"
0x18001c2dc  mov     [rsp+2B0h+var_290], ebx
0x18001c2e0  call    AslLogCallPrintf
0x18001c2e5  jmp     short loc_18001C28C
0x18001c2e7  cmp     byte ptr [rax+1Bh], 52h ; 'R'
0x18001c2eb  mov     [rbp+1B0h+var_3C], 1
0x18001c2f5  jz      loc_18001C192
0x18001c2fb  jmp     loc_18001C188
0x18001c300  call    cs:__imp_GetLastError
0x18001c306  lea     r9, aFailedToGetThe_3; "Failed to get the executable path [%d]"
0x18001c30d  mov     r8d, 0CCh
0x18001c313  jmp     loc_18001C26D
```
