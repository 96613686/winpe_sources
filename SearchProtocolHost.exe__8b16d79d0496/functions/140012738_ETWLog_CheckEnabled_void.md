# ETWLog::CheckEnabled(void)

- ea: `0x140012738`
- end: `0x1400128f2`
- name: `?CheckEnabled@ETWLog@@CAXXZ`
- size: `442`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014954`
- `0x14001fbbc`

## callees

- `0x140005240`
- `0x140012738`
- `0x14004ee84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400128c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400128c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400127ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400127ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012813`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001286e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012813`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001286e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400128b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400128b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012886`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012886`

## pseudocode

```c
void __fastcall ETWLog::CheckEnabled(const wchar_t *a1)
{
  bool v1; // bl
  bool v2; // al
  wchar_t *v3; // rdx
  unsigned int v4; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v10[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t v12[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( !g_fETWLoggingChecked && !g_fETWLoggingEnabled )
  {
    hKey = 0;
    v1 = 1;
    g_fETWLoggingChecked = 1;
    v2 = MapRegistryKeyPath(a1, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", v12, phkResult);
    v3 = v12;
    if ( !v2 )
      v3 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search";
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey) )
    {
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"ETWLogging", 0, &Type, Data, &cbData) || Type != 4 || !*(_DWORD *)Data )
        v1 = 0;
      g_fETWLoggingEnabled = v1;
      *(_DWORD *)v10 = 0;
      cbData = 4;
      if ( !dword_1400978F8 && !RegQueryValueExW(hKey, L"ETWBufferSize", 0, &Type, v10, &cbData) && Type == 4 )
      {
        v4 = *(_DWORD *)v10;
        if ( *(_DWORD *)v10 )
        {
          ProcessHeap = GetProcessHeap();
          dword_1400978F8 = v4 >> 11;
          ETWLog::s_etwBuf = ProcessHeap;
          dword_1400978FC = 0;
          qword_140097900 = (__int64)HeapAlloc(ProcessHeap, 8u, (unsigned __int64)(v4 >> 11) << 11);
        }
      }
      RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x140012738  mov     [rsp-8+arg_0], rbx
0x14001273d  mov     [rsp-8+arg_8], rdi
0x140012742  push    rbp
0x140012743  lea     rbp, [rsp-170h]
0x14001274b  sub     rsp, 270h
0x140012752  mov     rax, cs:__security_cookie
0x140012759  xor     rax, rsp
0x14001275c  mov     [rbp+170h+var_10], rax
0x140012763  cmp     cs:?g_fETWLoggingChecked@@3_NA, 0; bool g_fETWLoggingChecked
0x14001276a  jnz     loc_1400128CE
0x140012770  cmp     cs:?g_fETWLoggingEnabled@@3_NA, 0; bool g_fETWLoggingEnabled
0x140012777  jnz     loc_1400128CE
0x14001277d  lea     rdi, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows Search"
0x140012784  mov     [rsp+270h+hKey], 0
0x14001278d  mov     bl, 1
0x14001278f  lea     r9, [rsp+270h+var_220]; wchar_t *
0x140012794  mov     r8, rdi; wchar_t *
0x140012797  mov     cs:?g_fETWLoggingChecked@@3_NA, bl; bool g_fETWLoggingChecked
0x14001279d  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1400127a4  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x1400127a9  test    al, al
0x1400127ab  lea     rdx, [rsp+270h+var_220]
0x1400127b0  lea     rax, [rsp+270h+hKey]
0x1400127b5  mov     r9d, 20019h; samDesired
0x1400127bb  cmovz   rdx, rdi; lpSubKey
0x1400127bf  mov     [rsp+270h+phkResult], rax; phkResult
0x1400127c4  xor     r8d, r8d; ulOptions
0x1400127c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400127ce  call    cs:__imp_RegOpenKeyExW
0x1400127d4  test    eax, eax
0x1400127d6  jnz     loc_1400128CE
0x1400127dc  mov     rcx, [rsp+270h+hKey]; hKey
0x1400127e1  lea     edi, [rax+4]
0x1400127e4  mov     [rsp+270h+Type], eax
0x1400127e8  lea     r9, [rsp+270h+Type]; lpType
0x1400127ed  mov     dword ptr [rsp+270h+Data], eax
0x1400127f1  lea     rdx, ValueName; "ETWLogging"
0x1400127f8  lea     rax, [rsp+270h+cbData]
0x1400127fd  mov     [rsp+270h+cbData], edi
0x140012801  mov     [rsp+270h+lpcbData], rax; lpcbData
0x140012806  xor     r8d, r8d; lpReserved
0x140012809  lea     rax, [rsp+270h+Data]
0x14001280e  mov     [rsp+270h+phkResult], rax; lpData
0x140012813  call    cs:__imp_RegQueryValueExW
0x140012819  test    eax, eax
0x14001281b  jnz     short loc_140012829
0x14001281d  cmp     [rsp+270h+Type], edi
0x140012821  jnz     short loc_140012829
0x140012823  cmp     dword ptr [rsp+270h+Data], eax
0x140012827  ja      short loc_14001282B
0x140012829  xor     bl, bl
0x14001282b  cmp     cs:dword_1400978F8, 0
0x140012832  mov     cs:?g_fETWLoggingEnabled@@3_NA, bl; bool g_fETWLoggingEnabled
0x140012838  mov     dword ptr [rsp+270h+var_234], 0
0x140012840  mov     [rsp+270h+cbData], edi
0x140012844  ja      short loc_1400128C3
0x140012846  mov     rcx, [rsp+270h+hKey]; hKey
0x14001284b  lea     rax, [rsp+270h+cbData]
0x140012850  mov     [rsp+270h+lpcbData], rax; lpcbData
0x140012855  lea     r9, [rsp+270h+Type]; lpType
0x14001285a  lea     rax, [rsp+270h+var_234]
0x14001285f  xor     r8d, r8d; lpReserved
0x140012862  lea     rdx, aEtwbuffersize; "ETWBufferSize"
0x140012869  mov     [rsp+270h+phkResult], rax; lpData
0x14001286e  call    cs:__imp_RegQueryValueExW
0x140012874  test    eax, eax
0x140012876  jnz     short loc_1400128C3
0x140012878  cmp     [rsp+270h+Type], edi
0x14001287c  jnz     short loc_1400128C3
0x14001287e  mov     ebx, dword ptr [rsp+270h+var_234]
0x140012882  test    ebx, ebx
0x140012884  jz      short loc_1400128C3
0x140012886  call    cs:__imp_GetProcessHeap
0x14001288c  shr     ebx, 0Bh
0x14001288f  mov     edx, 8; dwFlags
0x140012894  mov     r8d, ebx
0x140012897  mov     rcx, rax; hHeap
0x14001289a  mov     cs:dword_1400978F8, r8d
0x1400128a1  shl     r8, 0Bh; dwBytes
0x1400128a5  mov     cs:?s_etwBuf@ETWLog@@0VETWBuffer@@A, rax; ETWBuffer ETWLog::s_etwBuf
0x1400128ac  mov     cs:dword_1400978FC, 0
0x1400128b6  call    cs:__imp_HeapAlloc
0x1400128bc  mov     cs:qword_140097900, rax
0x1400128c3  mov     rcx, [rsp+270h+hKey]; hKey
0x1400128c8  call    cs:__imp_RegCloseKey
0x1400128ce  mov     rcx, [rbp+170h+var_10]
0x1400128d5  xor     rcx, rsp; StackCookie
0x1400128d8  call    __security_check_cookie
0x1400128dd  lea     r11, [rsp+270h+var_s0]
0x1400128e5  mov     rbx, [r11+10h]
0x1400128e9  mov     rdi, [r11+18h]
0x1400128ed  mov     rsp, r11
0x1400128f0  pop     rbp
0x1400128f1  retn
```
