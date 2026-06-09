# pInitializeCOM(int &)

- ea: `0x180021140`
- end: `0x180021254`
- name: `?pInitializeCOM@@YAJAEAH@Z`
- size: `276`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a5f0`
- `0x18000b280`
- `0x18000bf00`
- `0x18000fab0`
- `0x180010310`
- `0x180012130`
- `0x1800131c4`
- `0x1800170f0`
- `0x18001ce50`

## callees

- `0x180009e04`
- `0x180021140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002116e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002116e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211d9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021156`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021156`
- `WDSCORE!CurrentIP` at `0x180021176`
- `WDSCORE!CurrentIP` at `0x1800211e1`
- `WDSCORE!CurrentIP` at `0x180021176`
- `WDSCORE!CurrentIP` at `0x1800211e1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002123c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002123c`

## string_xrefs

- `0x18002119b`: `pInitializeCOM`
- `0x1800211ff`: `pInitializeCOM`
- `0x1800211b9`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180021219`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800211e7`: `pInitializeCOM: COM is already initialized in apartment-threaded mode.`
- `0x18002117f`: `pInitializeCOM: Failed to initialize COM. hr = 0x%x`

## pseudocode

```c
__int64 __fastcall pInitializeCOM(int *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // esi
  DWORD v4; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  DWORD LastError; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax

  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 == -2147417850 )
  {
    v3 = 0;
    LastError = GetLastError();
    v8 = CurrentIP();
    v9 = ConstructPartialMsgW(0x4000000, "pInitializeCOM: COM is already initialized in apartment-threaded mode.");
    WdsSetupLogMessageW(
      v9,
      0,
      L"D",
      0,
      164,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"pInitializeCOM",
      v8,
      LastError,
      0,
      0);
  }
  else if ( v2 < 2 )
  {
    *a1 = 1;
  }
  else
  {
    v4 = GetLastError();
    v5 = CurrentIP();
    v6 = ConstructPartialMsgW(0x2000000, "pInitializeCOM: Failed to initialize COM. hr = 0x%x", v3);
    WdsSetupLogMessageW(
      v6,
      0,
      L"D",
      0,
      167,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"pInitializeCOM",
      v5,
      v4,
      0,
      0);
  }
  return v3;
}

```

## disassembly

```asm
0x180021140  mov     [rsp+arg_0], rbx
0x180021145  mov     [rsp+arg_8], rsi
0x18002114a  push    rdi
0x18002114b  sub     rsp, 60h
0x18002114f  mov     rbx, rcx
0x180021152  xor     edx, edx; dwCoInit
0x180021154  xor     ecx, ecx; pvReserved
0x180021156  call    cs:__imp_CoInitializeEx
0x18002115c  mov     esi, eax
0x18002115e  cmp     eax, 80010106h
0x180021163  jz      short loc_1800211D7
0x180021165  test    eax, eax
0x180021167  jz      short loc_1800211CF
0x180021169  cmp     eax, 1
0x18002116c  jz      short loc_1800211CF
0x18002116e  call    cs:__imp_GetLastError
0x180021174  mov     edi, eax
0x180021176  call    cs:__imp_CurrentIP
0x18002117c  mov     r8d, esi
0x18002117f  lea     rdx, aPinitializecom_1; "pInitializeCOM: Failed to initialize CO"...
0x180021186  mov     ecx, 2000000h; unsigned int
0x18002118b  mov     rbx, rax
0x18002118e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180021193  mov     [rsp+68h+var_18], 0
0x18002119b  lea     rcx, aPinitializecom; "pInitializeCOM"
0x1800211a2  mov     [rsp+68h+var_20], 0
0x1800211ab  mov     [rsp+68h+var_28], edi
0x1800211af  mov     [rsp+68h+var_30], rbx
0x1800211b4  mov     [rsp+68h+var_38], rcx
0x1800211b9  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800211c0  mov     [rsp+68h+var_40], rcx
0x1800211c5  mov     [rsp+68h+var_48], 0A7h
0x1800211cd  jmp     short loc_18002122D
0x1800211cf  mov     dword ptr [rbx], 1
0x1800211d5  jmp     short loc_180021242
0x1800211d7  xor     esi, esi
0x1800211d9  call    cs:__imp_GetLastError
0x1800211df  mov     edi, eax
0x1800211e1  call    cs:__imp_CurrentIP
0x1800211e7  lea     rdx, aPinitializecom_0; "pInitializeCOM: COM is already initiali"...
0x1800211ee  mov     ecx, 4000000h; unsigned int
0x1800211f3  mov     rbx, rax
0x1800211f6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800211fb  mov     [rsp+68h+var_18], esi
0x1800211ff  lea     rcx, aPinitializecom; "pInitializeCOM"
0x180021206  mov     [rsp+68h+var_20], rsi
0x18002120b  mov     [rsp+68h+var_28], edi
0x18002120f  mov     [rsp+68h+var_30], rbx
0x180021214  mov     [rsp+68h+var_38], rcx
0x180021219  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180021220  mov     [rsp+68h+var_40], rcx
0x180021225  mov     [rsp+68h+var_48], 0A4h
0x18002122d  xor     r9d, r9d
0x180021230  lea     r8, aD; "D"
0x180021237  xor     edx, edx
0x180021239  mov     rcx, rax
0x18002123c  call    cs:__imp_WdsSetupLogMessageW
0x180021242  mov     rbx, [rsp+68h+arg_0]
0x180021247  mov     eax, esi
0x180021249  mov     rsi, [rsp+68h+arg_8]
0x18002124e  add     rsp, 60h
0x180021252  pop     rdi
0x180021253  retn
```
