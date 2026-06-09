# ApphelpNotifyPcaOfProblem

- ea: `0x18003bd90`
- end: `0x18003c152`
- name: `ApphelpNotifyPcaOfProblem`
- size: `962`
- prototype: `__int64 __fastcall(BYTE *lpData, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009e94`
- `0x18000f114`
- `0x18002bf3c`
- `0x18003988c`
- `0x18003bd90`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003bfd6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003bfd6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c066`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c0ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c0eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c066`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c0ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c0eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c119`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c119`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bf84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bf84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003be23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003be23`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18003c017`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18003c017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c00a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c00a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c021`
- `KERNEL32!QueryFullProcessImageNameW` at `0x18003be3a`
- `KERNEL32!QueryFullProcessImageNameW` at `0x18003be3a`

## string_xrefs

- `0x18003be8d`: `Exe full path %ws`
- `0x18003bf05`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\NotifyPca\`
- `0x18003bf23`: `StringCchCopyW failed %x`
- `0x18003bf9e`: `SubKeyPath already exists %ws`
- `0x18003bff0`: `RegCreateKeyEx failed %d, %ws`
- `0x18003c027`: `ProcessIdToSessionId failed %d`
- `0x18003c06c`: `RegSetValueEx failed %d`

## pseudocode

```c
__int64 __fastcall ApphelpNotifyPcaOfProblem(BYTE *lpData, int a2)
{
  unsigned int v3; // r15d
  __int64 v4; // r14
  HANDLE CurrentProcess; // rax
  const char *v6; // r9
  __int64 v7; // r8
  int v8; // esi
  __int64 v9; // rcx
  WCHAR v10; // ax
  int LastError; // eax
  size_t v12; // r11
  LSTATUS v13; // eax
  DWORD CurrentProcessId; // eax
  DWORD v15; // r14d
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  wchar_t *phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pSessionId; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwSize; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ExeName[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t pszSrc[264]; // [rsp+490h] [rbp+390h] BYREF

  *(_DWORD *)Data = a2;
  v3 = 0;
  memset_0(ExeName, 0, 0x208u);
  memset_0(pszSrc, 0, 0x208u);
  memset_0(pszDest, 0, 0x208u);
  v4 = -1;
  hKey = 0;
  pSessionId = 0;
  dwSize = 260;
  do
    ++v4;
  while ( *(_WORD *)&lpData[2 * v4] );
  CurrentProcess = GetCurrentProcess();
  if ( !QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize) )
  {
    LODWORD(phkResult) = GetLastError();
    v6 = "QueryFullProcessImageName failed %d";
    v7 = 208;
LABEL_5:
    AslLogCallPrintf(1, "ApphelpNotifyPcaOfProblem", v7, v6, phkResult);
    goto LABEL_30;
  }
  v8 = 0;
  AslLogCallPrintf(3, "ApphelpNotifyPcaOfProblem", 212, "Exe full path %ws", ExeName);
  if ( ExeName[0] )
  {
    do
    {
      if ( v8 >= 259 )
        break;
      v9 = v8;
      v10 = ExeName[v8];
      if ( v10 == 92 )
        v10 = 47;
      ++v8;
      pszSrc[v9] = v10;
    }
    while ( ExeName[v8] );
  }
  if ( (unsigned __int64)(2LL * v8) >= 0x208 )
    _report_rangecheckfailure();
  pszSrc[v8] = 0;
  LastError = StringCchCopyW(
                pszDest,
                0x104u,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\NotifyPca\\");
  if ( LastError < 0 )
  {
    v6 = "StringCchCopyW failed %x";
    v7 = (unsigned int)(v12 - 30);
LABEL_14:
    LODWORD(phkResult) = LastError;
    goto LABEL_5;
  }
  LastError = StringCchCatW(pszDest, v12, pszSrc);
  if ( LastError < 0 )
  {
    v6 = "StringCchCatW failed %x";
    v7 = 236;
    goto LABEL_14;
  }
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, pszDest, 0, 0xF003Fu, &hKey) )
  {
    v7 = 249;
    phkResult = pszDest;
    v6 = "SubKeyPath already exists %ws";
    goto LABEL_5;
  }
  v13 = RegCreateKeyExW(HKEY_CURRENT_USER, pszDest, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v13 )
  {
    LODWORD(phkResult) = v13;
    AslLogCallPrintf(1, "ApphelpNotifyPcaOfProblem", 263, "RegCreateKeyEx failed %d, %ws", phkResult, pszDest);
  }
  else
  {
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    {
      LastError = GetLastError();
      v6 = "ProcessIdToSessionId failed %d";
      v7 = 268;
      goto LABEL_14;
    }
    v15 = 2 * v4 + 2;
    v16 = RegSetValueExW(hKey, L"SessionId", 0, 4u, (const BYTE *)&pSessionId, 4u);
    if ( v16 )
      AslLogCallPrintf(1, "ApphelpNotifyPcaOfProblem", 279, "RegSetValueEx failed %d", v16);
    v17 = RegSetValueExW(hKey, L"DescriptionStringId", 0, 4u, Data, 4u);
    if ( v17 )
      AslLogCallPrintf(1, "ApphelpNotifyPcaOfProblem", 289, "RegSetValueEx failed %d", v17);
    v18 = RegSetValueExW(hKey, L"LayerName", 0, 1u, lpData, v15);
    if ( v18 )
      AslLogCallPrintf(1, "ApphelpNotifyPcaOfProblem", 299, "RegSetValueEx failed %d", v18);
    v3 = 1;
  }
LABEL_30:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18003bd90  mov     [rsp-8+arg_10], rbx
0x18003bd95  push    rbp
0x18003bd96  push    rsi
0x18003bd97  push    rdi
0x18003bd98  push    r12
0x18003bd9a  push    r13
0x18003bd9c  push    r14
0x18003bd9e  push    r15
0x18003bda0  lea     rbp, [rsp-5B0h]
0x18003bda8  sub     rsp, 6B0h
0x18003bdaf  mov     rax, cs:__security_cookie
0x18003bdb6  xor     rax, rsp
0x18003bdb9  mov     [rbp+5E0h+var_40], rax
0x18003bdc0  mov     r12, rcx
0x18003bdc3  mov     dword ptr [rsp+6E0h+Data], edx
0x18003bdc7  mov     ebx, 208h
0x18003bdcc  lea     rcx, [rbp+5E0h+ExeName]; void *
0x18003bdd3  xor     r13d, r13d
0x18003bdd6  mov     r8d, ebx; Size
0x18003bdd9  xor     edx, edx; Val
0x18003bddb  mov     r15d, r13d
0x18003bdde  call    memset_0
0x18003bde3  mov     r8d, ebx; Size
0x18003bde6  lea     rcx, [rbp+5E0h+pszSrc]; void *
0x18003bded  xor     edx, edx; Val
0x18003bdef  call    memset_0
0x18003bdf4  mov     r8d, ebx; Size
0x18003bdf7  lea     rcx, [rsp+6E0h+pszDest]; void *
0x18003bdfc  xor     edx, edx; Val
0x18003bdfe  call    memset_0
0x18003be03  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003be07  mov     [rsp+6E0h+hKey], r13
0x18003be0c  mov     [rsp+6E0h+pSessionId], r13d
0x18003be11  mov     [rsp+6E0h+dwSize], 104h
0x18003be19  inc     r14
0x18003be1c  cmp     [r12+r14*2], r13w
0x18003be21  jnz     short loc_18003BE19
0x18003be23  call    cs:__imp_GetCurrentProcess
0x18003be29  lea     r9, [rsp+6E0h+dwSize]; lpdwSize
0x18003be2e  xor     edx, edx; dwFlags
0x18003be30  mov     rcx, rax; hProcess
0x18003be33  lea     r8, [rbp+5E0h+ExeName]; lpExeName
0x18003be3a  call    cs:__imp_QueryFullProcessImageNameW
0x18003be40  test    eax, eax
0x18003be42  jnz     short loc_18003BE71
0x18003be44  call    cs:__imp_GetLastError
0x18003be4a  mov     dword ptr [rsp+6E0h+phkResult], eax
0x18003be4e  lea     r9, aQueryfullproce; "QueryFullProcessImageName failed %d"
0x18003be55  mov     r8d, 0D0h
0x18003be5b  lea     rdx, aApphelpnotifyp_0; "ApphelpNotifyPcaOfProblem"
0x18003be62  mov     ecx, 1
0x18003be67  call    AslLogCallPrintf
0x18003be6c  jmp     loc_18003C10F
0x18003be71  lea     rax, [rbp+5E0h+ExeName]
0x18003be78  mov     r8d, 0D4h
0x18003be7e  lea     rdi, aApphelpnotifyp_0; "ApphelpNotifyPcaOfProblem"
0x18003be85  mov     [rsp+6E0h+phkResult], rax
0x18003be8a  mov     rdx, rdi
0x18003be8d  lea     r9, aExeFullPathWs; "Exe full path %ws"
0x18003be94  mov     ecx, 3
0x18003be99  mov     esi, r13d
0x18003be9c  call    AslLogCallPrintf
0x18003bea1  mov     ebx, 1
0x18003bea6  cmp     [rbp+5E0h+ExeName], r13w
0x18003beae  jz      short loc_18003BEE8
0x18003beb0  cmp     esi, 103h
0x18003beb6  jge     short loc_18003BEE8
0x18003beb8  movsxd  rcx, esi
0x18003bebb  mov     edx, 5Ch ; '\'
0x18003bec0  movzx   eax, [rbp+rcx*2+5E0h+ExeName]
0x18003bec8  cmp     dx, ax
0x18003becb  jnz     short loc_18003BED0
0x18003becd  lea     eax, [rdx-2Dh]
0x18003bed0  add     esi, ebx
0x18003bed2  mov     [rbp+rcx*2+5E0h+pszSrc], ax
0x18003beda  movsxd  rax, esi
0x18003bedd  cmp     [rbp+rax*2+5E0h+ExeName], r13w
0x18003bee6  jnz     short loc_18003BEB0
0x18003bee8  movsxd  rax, esi
0x18003beeb  lea     rcx, [rax+rax]
0x18003beef  cmp     rcx, 208h
0x18003bef6  jnb     loc_18003C14C
0x18003befc  mov     [rbp+rcx+5E0h+pszSrc], r13w
0x18003bf05  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003bf0c  mov     r11d, 104h
0x18003bf12  lea     rcx, [rsp+6E0h+pszDest]; pszDest
0x18003bf17  mov     edx, r11d; cchDest
0x18003bf1a  call    StringCchCopyW
0x18003bf1f  test    eax, eax
0x18003bf21  jns     short loc_18003BF3C
0x18003bf23  lea     r9, aStringcchcopyw; "StringCchCopyW failed %x"
0x18003bf2a  lea     r8d, [r11-1Eh]
0x18003bf2e  mov     dword ptr [rsp+6E0h+phkResult], eax
0x18003bf32  mov     rdx, rdi
0x18003bf35  mov     ecx, ebx
0x18003bf37  jmp     loc_18003BE67
0x18003bf3c  lea     r8, [rbp+5E0h+pszSrc]; pszSrc
0x18003bf43  mov     rdx, r11; cchDest
0x18003bf46  lea     rcx, [rsp+6E0h+pszDest]; pszDest
0x18003bf4b  call    StringCchCatW
0x18003bf50  test    eax, eax
0x18003bf52  jns     short loc_18003BF63
0x18003bf54  lea     r9, aStringcchcatwF; "StringCchCatW failed %x"
0x18003bf5b  mov     r8d, 0ECh
0x18003bf61  jmp     short loc_18003BF2E
0x18003bf63  lea     rax, [rsp+6E0h+hKey]
0x18003bf68  mov     esi, 0F003Fh
0x18003bf6d  mov     r9d, esi; samDesired
0x18003bf70  mov     [rsp+6E0h+phkResult], rax; phkResult
0x18003bf75  xor     r8d, r8d; ulOptions
0x18003bf78  lea     rdx, [rsp+6E0h+pszDest]; lpSubKey
0x18003bf7d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003bf84  call    cs:__imp_RegOpenKeyExW
0x18003bf8a  test    eax, eax
0x18003bf8c  jnz     short loc_18003BFA7
0x18003bf8e  lea     rax, [rsp+6E0h+pszDest]
0x18003bf93  mov     r8d, 0F9h
0x18003bf99  mov     [rsp+6E0h+phkResult], rax
0x18003bf9e  lea     r9, aSubkeypathAlre; "SubKeyPath already exists %ws"
0x18003bfa5  jmp     short loc_18003BF32
0x18003bfa7  mov     [rsp+6E0h+lpdwDisposition], r13; lpdwDisposition
0x18003bfac  lea     rax, [rsp+6E0h+hKey]
0x18003bfb1  mov     [rsp+6E0h+var_6A8], rax; phkResult
0x18003bfb6  lea     rdx, [rsp+6E0h+pszDest]; lpSubKey
0x18003bfbb  mov     [rsp+6E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18003bfc0  xor     r9d, r9d; lpClass
0x18003bfc3  mov     [rsp+6E0h+samDesired], esi; samDesired
0x18003bfc7  xor     r8d, r8d; Reserved
0x18003bfca  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003bfd1  mov     dword ptr [rsp+6E0h+phkResult], r13d; dwOptions
0x18003bfd6  call    cs:__imp_RegCreateKeyExW
0x18003bfdc  test    eax, eax
0x18003bfde  jz      short loc_18003C00A
0x18003bfe0  lea     rcx, [rsp+6E0h+pszDest]
0x18003bfe5  mov     r8d, 107h
0x18003bfeb  mov     qword ptr [rsp+6E0h+samDesired], rcx
0x18003bff0  lea     r9, aRegcreatekeyex; "RegCreateKeyEx failed %d, %ws"
0x18003bff7  mov     ecx, ebx
0x18003bff9  mov     dword ptr [rsp+6E0h+phkResult], eax
0x18003bffd  mov     rdx, rdi
0x18003c000  call    AslLogCallPrintf
0x18003c005  jmp     loc_18003C10F
0x18003c00a  call    cs:__imp_GetCurrentProcessId
0x18003c010  mov     ecx, eax; dwProcessId
0x18003c012  lea     rdx, [rsp+6E0h+pSessionId]; pSessionId
0x18003c017  call    cs:__imp_ProcessIdToSessionId
0x18003c01d  test    eax, eax
0x18003c01f  jnz     short loc_18003C039
0x18003c021  call    cs:__imp_GetLastError
0x18003c027  lea     r9, aProcessidtoses; "ProcessIdToSessionId failed %d"
0x18003c02e  mov     r8d, 10Ch
0x18003c034  jmp     loc_18003BF2E
0x18003c039  mov     rcx, [rsp+6E0h+hKey]; hKey
0x18003c03e  lea     rax, [rsp+6E0h+pSessionId]
0x18003c043  mov     esi, 4
0x18003c048  lea     rdx, aSessionid; "SessionId"
0x18003c04f  mov     [rsp+6E0h+samDesired], esi; cbData
0x18003c053  lea     r14d, ds:2[r14*2]
0x18003c05b  mov     r9d, esi; dwType
0x18003c05e  mov     [rsp+6E0h+phkResult], rax; lpData
0x18003c063  xor     r8d, r8d; Reserved
0x18003c066  call    cs:__imp_RegSetValueExW
0x18003c06c  lea     r15, aRegsetvalueexF; "RegSetValueEx failed %d"
0x18003c073  test    eax, eax
0x18003c075  jz      short loc_18003C08E
0x18003c077  mov     r9, r15
0x18003c07a  mov     dword ptr [rsp+6E0h+phkResult], eax
0x18003c07e  mov     r8d, 117h
0x18003c084  mov     rdx, rdi
0x18003c087  mov     ecx, ebx
0x18003c089  call    AslLogCallPrintf
0x18003c08e  mov     rcx, [rsp+6E0h+hKey]; hKey
0x18003c093  lea     rax, [rsp+6E0h+Data]
0x18003c098  mov     [rsp+6E0h+samDesired], esi; cbData
0x18003c09c  lea     rdx, aDescriptionstr; "DescriptionStringId"
0x18003c0a3  mov     r9d, esi; dwType
0x18003c0a6  mov     [rsp+6E0h+phkResult], rax; lpData
0x18003c0ab  xor     r8d, r8d; Reserved
0x18003c0ae  call    cs:__imp_RegSetValueExW
0x18003c0b4  test    eax, eax
0x18003c0b6  jz      short loc_18003C0CF
0x18003c0b8  mov     r9, r15
0x18003c0bb  mov     dword ptr [rsp+6E0h+phkResult], eax
0x18003c0bf  mov     r8d, 121h
0x18003c0c5  mov     rdx, rdi
0x18003c0c8  mov     ecx, ebx
0x18003c0ca  call    AslLogCallPrintf
0x18003c0cf  mov     rcx, [rsp+6E0h+hKey]; hKey
0x18003c0d4  lea     rdx, aLayername; "LayerName"
0x18003c0db  mov     [rsp+6E0h+samDesired], r14d; cbData
0x18003c0e0  mov     r9d, ebx; dwType
0x18003c0e3  xor     r8d, r8d; Reserved
0x18003c0e6  mov     [rsp+6E0h+phkResult], r12; lpData
0x18003c0eb  call    cs:__imp_RegSetValueExW
0x18003c0f1  test    eax, eax
0x18003c0f3  jz      short loc_18003C10C
0x18003c0f5  mov     r9, r15
0x18003c0f8  mov     dword ptr [rsp+6E0h+phkResult], eax
0x18003c0fc  mov     r8d, 12Bh
0x18003c102  mov     rdx, rdi
0x18003c105  mov     ecx, ebx
0x18003c107  call    AslLogCallPrintf
0x18003c10c  mov     r15d, ebx
0x18003c10f  mov     rcx, [rsp+6E0h+hKey]; hKey
0x18003c114  test    rcx, rcx
0x18003c117  jz      short loc_18003C11F
0x18003c119  call    cs:__imp_RegCloseKey
0x18003c11f  mov     eax, r15d
0x18003c122  mov     rcx, [rbp+5E0h+var_40]
0x18003c129  xor     rcx, rsp; StackCookie
0x18003c12c  call    __security_check_cookie
0x18003c131  mov     rbx, [rsp+6E0h+arg_10]
0x18003c139  add     rsp, 6B0h
0x18003c140  pop     r15
0x18003c142  pop     r14
0x18003c144  pop     r13
0x18003c146  pop     r12
0x18003c148  pop     rdi
0x18003c149  pop     rsi
0x18003c14a  pop     rbp
0x18003c14b  retn
0x18003c14c  call    __report_rangecheckfailure
```
