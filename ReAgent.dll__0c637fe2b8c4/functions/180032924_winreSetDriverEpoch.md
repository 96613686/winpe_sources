# winreSetDriverEpoch

- ea: `0x180032924`
- end: `0x180032c0b`
- name: `winreSetDriverEpoch`
- size: `743`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024800`

## callees

- `0x1800059fc`
- `0x180032924`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180032977`
- `KERNEL32!GetLastError` at `0x1800329ae`
- `KERNEL32!GetLastError` at `0x1800329d5`
- `KERNEL32!GetLastError` at `0x1800329fc`
- `KERNEL32!GetLastError` at `0x180032a26`
- `KERNEL32!GetLastError` at `0x180032a5c`
- `KERNEL32!GetLastError` at `0x180032a8a`
- `KERNEL32!GetLastError` at `0x180032ad5`
- `KERNEL32!GetLastError` at `0x180032977`
- `KERNEL32!GetLastError` at `0x1800329ae`
- `KERNEL32!GetLastError` at `0x1800329d5`
- `KERNEL32!GetLastError` at `0x1800329fc`
- `KERNEL32!GetLastError` at `0x180032a26`
- `KERNEL32!GetLastError` at `0x180032a5c`
- `KERNEL32!GetLastError` at `0x180032a8a`
- `KERNEL32!GetLastError` at `0x180032ad5`
- `KERNEL32!GetProcAddress` at `0x1800329a0`
- `KERNEL32!GetProcAddress` at `0x1800329c7`
- `KERNEL32!GetProcAddress` at `0x1800329ee`
- `KERNEL32!GetProcAddress` at `0x180032a18`
- `KERNEL32!GetProcAddress` at `0x1800329a0`
- `KERNEL32!GetProcAddress` at `0x1800329c7`
- `KERNEL32!GetProcAddress` at `0x1800329ee`
- `KERNEL32!GetProcAddress` at `0x180032a18`
- `KERNEL32!FreeLibrary` at `0x180032bdf`
- `KERNEL32!FreeLibrary` at `0x180032bdf`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180032a52`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180032a52`
- `KERNEL32!LoadLibraryExW` at `0x180032969`
- `KERNEL32!LoadLibraryExW` at `0x180032969`
- `ADVAPI32!RegSetValueExW` at `0x180032b89`
- `ADVAPI32!RegSetValueExW` at `0x180032b89`
- `ADVAPI32!RegCreateKeyExW` at `0x180032b3c`
- `ADVAPI32!RegCreateKeyExW` at `0x180032b3c`
- `ADVAPI32!RegCloseKey` at `0x180032bb3`
- `ADVAPI32!RegCloseKey` at `0x180032bb3`

## string_xrefs

- `0x180032953`: `drvstore.dll`
- `0x18003297d`: `winreSetDriverEpoch: Failed to load drvstore.dll: 0x%x`
- `0x180032996`: `DriverStoreOpenW`
- `0x1800329b4`: `winreSetDriverEpoch: Failed to load drvstore!DriverStoreOpenW: 0x%x`
- `0x180032b4d`: `winreSetDriverEpoch: Failed to create %s: 0x%x`

## pseudocode

```c
__int64 winreSetDriverEpoch()
{
  __int64 v0; // rsi
  unsigned int v1; // r13d
  FARPROC v2; // rdi
  HMODULE Library; // rax
  HMODULE v4; // rbx
  DWORD v5; // eax
  FARPROC ProcAddress; // r14
  DWORD v7; // eax
  DWORD v8; // eax
  FARPROC v9; // r15
  DWORD v10; // eax
  FARPROC v11; // r12
  DWORD v12; // eax
  DWORD v13; // eax
  __int64 v14; // rax
  DWORD v15; // eax
  DWORD LastError; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v21[5]; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[16]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF

  v0 = 0;
  hKey = 0;
  v1 = 0;
  v2 = 0;
  Library = LoadLibraryExW(L"drvstore.dll", 0, 0);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DriverStoreOpenW");
    if ( ProcAddress )
    {
      v2 = GetProcAddress(v4, "DriverStoreClose");
      if ( v2 )
      {
        v9 = GetProcAddress(v4, "DriverStoreEnumW");
        if ( v9 )
        {
          v11 = GetProcAddress(v4, "DriverStoreGetObjectPropertyW");
          if ( v11 )
          {
            memset_0(Buffer, 0, 0x20Au);
            if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
            {
              v14 = ((__int64 (__fastcall *)(WCHAR *, _QWORD, _QWORD, _QWORD))ProcAddress)(Buffer, 0, 0, 0);
              v0 = v14;
              if ( v14 )
              {
                v21[0] = 0;
                v21[2] = 0;
                v21[1] = ProcAddress;
                v21[3] = v9;
                v21[4] = v11;
                if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64 (__fastcall *)(), _QWORD *))v9)(
                       v14,
                       2,
                       winreGetLatestDriverImportDate,
                       v21) )
                {
                  *(_QWORD *)Data = v21[0];
                  UnattendLogW(0, L"winreSetDriverEpoch: Driver epoch: %llu", v21[0]);
                  v17 = RegCreateKeyExW(
                          HKEY_LOCAL_MACHINE,
                          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\PBR",
                          0,
                          0,
                          0,
                          0x2001Fu,
                          0,
                          &hKey,
                          0);
                  if ( v17 )
                  {
                    UnattendLogW(
                      1,
                      L"winreSetDriverEpoch: Failed to create %s: 0x%x",
                      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\PBR",
                      v17);
                  }
                  else
                  {
                    v18 = RegSetValueExW(hKey, L"DriverEpoch", 0, 0xBu, Data, 8u);
                    if ( v18 )
                      UnattendLogW(1, L"winreSetDriverEpoch: Failed to set %s: 0x%x", L"DriverEpoch", v18);
                    else
                      v1 = 1;
                  }
                }
                else
                {
                  LastError = GetLastError();
                  UnattendLogW(1, L"winreSetDriverEpoch: Failed to iterate over third-party drivers: 0x%x", LastError);
                }
              }
              else
              {
                v15 = GetLastError();
                UnattendLogW(1, L"winreSetDriverEpoch: Failed to get online driver store: 0x%x", v15);
              }
            }
            else
            {
              v13 = GetLastError();
              UnattendLogW(1, L"winreSetDriverEpoch: Failed to get system Windows dir: 0x%x", v13);
            }
          }
          else
          {
            v12 = GetLastError();
            UnattendLogW(1, L"winreSetDriverEpoch: Failed to load drvstore!DriverStoreGetObjectPropertyW: 0x%x", v12);
          }
        }
        else
        {
          v10 = GetLastError();
          UnattendLogW(1, L"winreSetDriverEpoch: Failed to load drvstore!DriverStoreEnumW: 0x%x", v10);
        }
      }
      else
      {
        v8 = GetLastError();
        UnattendLogW(1, L"winreSetDriverEpoch: Failed to load drvstore!DriverStoreClose: 0x%x", v8);
      }
    }
    else
    {
      v7 = GetLastError();
      UnattendLogW(1, L"winreSetDriverEpoch: Failed to load drvstore!DriverStoreOpenW: 0x%x", v7);
    }
  }
  else
  {
    v5 = GetLastError();
    UnattendLogW(1, L"winreSetDriverEpoch: Failed to load drvstore.dll: 0x%x", v5);
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v0 && v2 )
    ((void (__fastcall *)(__int64))v2)(v0);
  if ( v4 )
    FreeLibrary(v4);
  return v1;
}

```

## disassembly

```asm
0x180032924  push    rbp
0x180032926  push    rbx
0x180032927  push    rsi
0x180032928  push    rdi
0x180032929  push    r12
0x18003292b  push    r13
0x18003292d  push    r14
0x18003292f  push    r15
0x180032931  lea     rbp, [rsp-1B8h]
0x180032939  sub     rsp, 2B8h
0x180032940  mov     rax, cs:__security_cookie
0x180032947  xor     rax, rsp
0x18003294a  mov     [rbp+1F0h+var_50], rax
0x180032951  xor     esi, esi
0x180032953  lea     rcx, aDrvstoreDll; "drvstore.dll"
0x18003295a  xor     r8d, r8d; dwFlags
0x18003295d  mov     [rsp+2F0h+hKey], rsi
0x180032962  xor     edx, edx; hFile
0x180032964  xor     r13d, r13d
0x180032967  xor     edi, edi
0x180032969  call    cs:__imp_LoadLibraryExW
0x18003296f  mov     rbx, rax
0x180032972  test    rax, rax
0x180032975  jnz     short loc_180032996
0x180032977  call    cs:__imp_GetLastError
0x18003297d  lea     rdx, aWinresetdriver_5; "winreSetDriverEpoch: Failed to load drv"...
0x180032984  mov     r8d, eax
0x180032987  mov     ecx, 1
0x18003298c  call    UnattendLogW
0x180032991  jmp     loc_180032BA9
0x180032996  lea     rdx, aDriverstoreope; "DriverStoreOpenW"
0x18003299d  mov     rcx, rbx; hModule
0x1800329a0  call    cs:__imp_GetProcAddress
0x1800329a6  mov     r14, rax
0x1800329a9  test    rax, rax
0x1800329ac  jnz     short loc_1800329BD
0x1800329ae  call    cs:__imp_GetLastError
0x1800329b4  lea     rdx, aWinresetdriver_4; "winreSetDriverEpoch: Failed to load drv"...
0x1800329bb  jmp     short loc_180032984
0x1800329bd  lea     rdx, aDriverstoreclo; "DriverStoreClose"
0x1800329c4  mov     rcx, rbx; hModule
0x1800329c7  call    cs:__imp_GetProcAddress
0x1800329cd  mov     rdi, rax
0x1800329d0  test    rax, rax
0x1800329d3  jnz     short loc_1800329E4
0x1800329d5  call    cs:__imp_GetLastError
0x1800329db  lea     rdx, aWinresetdriver_9; "winreSetDriverEpoch: Failed to load drv"...
0x1800329e2  jmp     short loc_180032984
0x1800329e4  lea     rdx, aDriverstoreenu; "DriverStoreEnumW"
0x1800329eb  mov     rcx, rbx; hModule
0x1800329ee  call    cs:__imp_GetProcAddress
0x1800329f4  mov     r15, rax
0x1800329f7  test    rax, rax
0x1800329fa  jnz     short loc_180032A0E
0x1800329fc  call    cs:__imp_GetLastError
0x180032a02  lea     rdx, aWinresetdriver_2; "winreSetDriverEpoch: Failed to load drv"...
0x180032a09  jmp     loc_180032984
0x180032a0e  lea     rdx, aDriverstoreget; "DriverStoreGetObjectPropertyW"
0x180032a15  mov     rcx, rbx; hModule
0x180032a18  call    cs:__imp_GetProcAddress
0x180032a1e  mov     r12, rax
0x180032a21  test    rax, rax
0x180032a24  jnz     short loc_180032A38
0x180032a26  call    cs:__imp_GetLastError
0x180032a2c  lea     rdx, aWinresetdriver_0; "winreSetDriverEpoch: Failed to load drv"...
0x180032a33  jmp     loc_180032984
0x180032a38  xor     edx, edx; Val
0x180032a3a  lea     rcx, [rbp+1F0h+Buffer]; void *
0x180032a3e  mov     r8d, 20Ah; Size
0x180032a44  call    memset_0
0x180032a49  mov     edx, 104h; uSize
0x180032a4e  lea     rcx, [rbp+1F0h+Buffer]; lpBuffer
0x180032a52  call    cs:__imp_GetSystemWindowsDirectoryW
0x180032a58  test    eax, eax
0x180032a5a  jnz     short loc_180032A6E
0x180032a5c  call    cs:__imp_GetLastError
0x180032a62  lea     rdx, aWinresetdriver_8; "winreSetDriverEpoch: Failed to get syst"...
0x180032a69  jmp     loc_180032984
0x180032a6e  xor     r9d, r9d
0x180032a71  lea     rcx, [rbp+1F0h+Buffer]
0x180032a75  xor     r8d, r8d
0x180032a78  xor     edx, edx
0x180032a7a  mov     rax, r14
0x180032a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a82  mov     rsi, rax
0x180032a85  test    rax, rax
0x180032a88  jnz     short loc_180032A9C
0x180032a8a  call    cs:__imp_GetLastError
0x180032a90  lea     rdx, aWinresetdriver_3; "winreSetDriverEpoch: Failed to get onli"...
0x180032a97  jmp     loc_180032984
0x180032a9c  mov     rcx, rax
0x180032a9f  mov     [rsp+2F0h+var_298], r13
0x180032aa4  mov     rax, r15
0x180032aa7  mov     [rsp+2F0h+var_288], r13
0x180032aac  lea     r9, [rsp+2F0h+var_298]
0x180032ab1  mov     [rsp+2F0h+var_290], r14
0x180032ab6  lea     r8, winreGetLatestDriverImportDate
0x180032abd  mov     [rsp+2F0h+var_280], r15
0x180032ac2  mov     edx, 2
0x180032ac7  mov     [rsp+2F0h+var_278], r12
0x180032acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ad1  test    eax, eax
0x180032ad3  jnz     short loc_180032AE7
0x180032ad5  call    cs:__imp_GetLastError
0x180032adb  lea     rdx, aWinresetdriver; "winreSetDriverEpoch: Failed to iterate "...
0x180032ae2  jmp     loc_180032984
0x180032ae7  mov     eax, dword ptr [rsp+2F0h+var_298]
0x180032aeb  lea     rdx, aWinresetdriver_6; "winreSetDriverEpoch: Driver epoch: %llu"
0x180032af2  mov     dword ptr [rbp+1F0h+Data], eax
0x180032af5  xor     ecx, ecx
0x180032af7  mov     eax, dword ptr [rsp+2F0h+var_298+4]
0x180032afb  mov     dword ptr [rbp+1F0h+Data+4], eax
0x180032afe  mov     r8, qword ptr [rbp+1F0h+Data]
0x180032b02  call    UnattendLogW
0x180032b07  mov     [rsp+2F0h+lpdwDisposition], r13; lpdwDisposition
0x180032b0c  lea     rax, [rsp+2F0h+hKey]
0x180032b11  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180032b16  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180032b1d  mov     [rsp+2F0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180032b22  xor     r9d, r9d; lpClass
0x180032b25  mov     [rsp+2F0h+samDesired], 2001Fh; samDesired
0x180032b2d  xor     r8d, r8d; Reserved
0x180032b30  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032b37  mov     [rsp+2F0h+dwOptions], r13d; dwOptions
0x180032b3c  call    cs:__imp_RegCreateKeyExW
0x180032b42  test    eax, eax
0x180032b44  jz      short loc_180032B63
0x180032b46  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180032b4d  lea     rdx, aWinresetdriver_1; "winreSetDriverEpoch: Failed to create %"...
0x180032b54  mov     r9d, eax
0x180032b57  mov     ecx, 1
0x180032b5c  call    UnattendLogW
0x180032b61  jmp     short loc_180032BA9
0x180032b63  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180032b68  lea     rax, [rbp+1F0h+Data]
0x180032b6c  mov     [rsp+2F0h+samDesired], 8; cbData
0x180032b74  lea     rdx, aDriverepoch; "DriverEpoch"
0x180032b7b  mov     r9d, 0Bh; dwType
0x180032b81  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180032b86  xor     r8d, r8d; Reserved
0x180032b89  call    cs:__imp_RegSetValueExW
0x180032b8f  test    eax, eax
0x180032b91  jz      short loc_180032BA3
0x180032b93  lea     r8, aDriverepoch; "DriverEpoch"
0x180032b9a  lea     rdx, aWinresetdriver_7; "winreSetDriverEpoch: Failed to set %s: "...
0x180032ba1  jmp     short loc_180032B54
0x180032ba3  mov     r13d, 1
0x180032ba9  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180032bae  test    rcx, rcx
0x180032bb1  jz      short loc_180032BC2
0x180032bb3  call    cs:__imp_RegCloseKey
0x180032bb9  mov     [rsp+2F0h+hKey], 0
0x180032bc2  test    rsi, rsi
0x180032bc5  jz      short loc_180032BD7
0x180032bc7  test    rdi, rdi
0x180032bca  jz      short loc_180032BD7
0x180032bcc  mov     rcx, rsi
0x180032bcf  mov     rax, rdi
0x180032bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bd7  test    rbx, rbx
0x180032bda  jz      short loc_180032BE5
0x180032bdc  mov     rcx, rbx; hLibModule
0x180032bdf  call    cs:__imp_FreeLibrary
0x180032be5  mov     eax, r13d
0x180032be8  mov     rcx, [rbp+1F0h+var_50]
0x180032bef  xor     rcx, rsp; StackCookie
0x180032bf2  call    __security_check_cookie
0x180032bf7  add     rsp, 2B8h
0x180032bfe  pop     r15
0x180032c00  pop     r14
0x180032c02  pop     r13
0x180032c04  pop     r12
0x180032c06  pop     rdi
0x180032c07  pop     rsi
0x180032c08  pop     rbx
0x180032c09  pop     rbp
0x180032c0a  retn
```
