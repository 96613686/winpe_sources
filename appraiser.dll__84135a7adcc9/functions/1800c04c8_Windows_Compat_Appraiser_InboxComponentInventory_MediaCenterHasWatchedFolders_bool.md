# Windows::Compat::Appraiser::InboxComponentInventory::MediaCenterHasWatchedFolders(bool &)

- ea: `0x1800c04c8`
- end: `0x1800c07b7`
- name: `?MediaCenterHasWatchedFolders@InboxComponentInventory@Appraiser@Compat@Windows@@CAJAEA_N@Z`
- size: `751`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800beb74`

## callees

- `0x180008570`
- `0x180008b20`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800c04c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c06cc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c06cc`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800c068d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800c068d`
- `KERNEL32!GetLastError` at `0x1800c0701`
- `KERNEL32!GetLastError` at `0x1800c0701`
- `ADVAPI32!RegQueryValueExW` at `0x1800c05e5`
- `ADVAPI32!RegQueryValueExW` at `0x1800c05e5`
- `ADVAPI32!RegCloseKey` at `0x1800c0781`
- `ADVAPI32!RegCloseKey` at `0x1800c0781`
- `ADVAPI32!RegOpenKeyExW` at `0x1800c0533`
- `ADVAPI32!RegOpenKeyExW` at `0x1800c0533`

## string_xrefs

- `0x1800c057c`: `onecore\base\appcompat\appraiser\inventory\inboxcomponentinventory.cpp`
- `0x1800c05af`: `onecore\base\appcompat\appraiser\inventory\inboxcomponentinventory.cpp`
- `0x1800c062e`: `onecore\base\appcompat\appraiser\inventory\inboxcomponentinventory.cpp`
- `0x1800c074a`: `onecore\base\appcompat\appraiser\inventory\inboxcomponentinventory.cpp`
- `0x1800c0571`: `Windows::Compat::Appraiser::InboxComponentInventory::MediaCenterHasWatchedFolders`
- `0x1800c05a3`: `Windows::Compat::Appraiser::InboxComponentInventory::MediaCenterHasWatchedFolders`
- `0x1800c0622`: `Windows::Compat::Appraiser::InboxComponentInventory::MediaCenterHasWatchedFolders`
- `0x1800c073f`: `Windows::Compat::Appraiser::InboxComponentInventory::MediaCenterHasWatchedFolders`
- `0x1800c0558`: `Registry operation failed: [0x%x].`
- `0x1800c052c`: `Software\Microsoft\Windows\CurrentVersion\Media Center\Service\Recording`
- `0x1800c0756`: `Registry returned unexpected value of Size %d, Type %d`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::InboxComponentInventory::MediaCenterHasWatchedFolders(bool *a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  char v4; // dl
  LSTATUS v5; // eax
  unsigned __int64 v6; // rcx
  DWORD v7; // r13d
  BYTE *v8; // rbx
  int v9; // ecx
  __int64 v10; // rax
  signed int LastError; // eax
  const char *phkResult; // [rsp+20h] [rbp-E0h]
  const char *lpcbData; // [rsp+28h] [rbp-D8h]
  char *v15; // [rsp+30h] [rbp-D0h]
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Dst[264]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[2]; // [rsp+260h] [rbp+160h] BYREF
  char v21; // [rsp+A7Eh] [rbp+97Eh] BYREF

  cbData = 2080;
  *a1 = 0;
  Type = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Media Center\\Service\\Recording",
         0,
         0x20119u,
         &hKey);
  v3 = v2;
  if ( v2 == 2 )
  {
LABEL_2:
    v3 = 0;
    *a1 = 0;
    goto LABEL_38;
  }
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 < 0 )
  {
    v4 = 34;
LABEL_7:
    LODWORD(v15) = v3;
    lpcbData = "Registry operation failed: [0x%x].";
LABEL_8:
    LODWORD(phkResult) = v3;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v4,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\inboxcomponentinventory.cpp",
      "Windows::Compat::Appraiser::InboxComponentInventory::MediaCenterHasWatchedFolders",
      phkResult,
      (int)lpcbData,
      v15);
    goto LABEL_38;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x422u,
      "onecore\\base\\appcompat\\appraiser\\inventory\\inboxcomponentinventory.cpp",
      "Windows::Compat::Appraiser::InboxComponentInventory::MediaCenterHasWatchedFolders",
      "Registry operation failed: [0x%x].",
      v3);
  v5 = RegQueryValueExW(hKey, L"WatchedFolders", 0, &Type, Data, &cbData);
  v3 = v5;
  if ( v5 == 2 )
    goto LABEL_2;
  if ( v5 > 0 )
    v3 = (unsigned __int16)v5 | 0x80070000;
  if ( v3 < 0 )
  {
    v4 = 50;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x432u,
      "onecore\\base\\appcompat\\appraiser\\inventory\\inboxcomponentinventory.cpp",
      "Windows::Compat::Appraiser::InboxComponentInventory::MediaCenterHasWatchedFolders",
      "Registry operation failed: [0x%x].",
      v3);
  if ( cbData && Type == 7 )
  {
    if ( cbData >= 0x40F )
    {
      v6 = 2078;
    }
    else
    {
      v6 = 2LL * cbData;
      if ( v6 >= 0x820 )
        _report_rangecheckfailure(v6, Type);
    }
    *(_WORD *)&Data[v6] = 0;
    v7 = ExpandEnvironmentStringsW(L"%PUBLIC%\\Recorded TV\\", Dst, 0x104u);
    if ( v7 - 1 > 0x103 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v15) = v7;
      if ( v3 >= 0 )
        v3 = -2147467259;
      lpcbData = "Expanding Environment String failed: Expanded size was %d.";
      v4 = 69;
      goto LABEL_8;
    }
    v8 = Data;
    if ( !*a1 )
    {
      do
      {
        if ( v8 >= (BYTE *)&v21 )
          break;
        if ( !*(_WORD *)Data )
          break;
        v9 = _o__wcsicmp(Dst, v8);
        *a1 = v9 != 0;
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)&Data[2 * v10] );
        v8 += 2 * v10 + 2;
      }
      while ( !v9 );
    }
    v3 = 0;
  }
  else
  {
    LODWORD(v15) = cbData;
    v3 = -2147467259;
    LODWORD(phkResult) = -2147467259;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      55,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\inboxcomponentinventory.cpp",
      "Windows::Compat::Appraiser::InboxComponentInventory::MediaCenterHasWatchedFolders",
      phkResult,
      (int)"Registry returned unexpected value of Size %d, Type %d",
      v15,
      Type);
  }
LABEL_38:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800c04c8  mov     [rsp-8+arg_8], rbx
0x1800c04cd  mov     [rsp-8+arg_10], rdi
0x1800c04d2  push    rbp
0x1800c04d3  push    r12
0x1800c04d5  push    r13
0x1800c04d7  lea     rbp, [rsp-990h]
0x1800c04df  sub     rsp, 0A90h
0x1800c04e6  mov     rax, cs:__security_cookie
0x1800c04ed  xor     rax, rsp
0x1800c04f0  mov     [rbp+9A0h+var_20], rax
0x1800c04f7  xor     r13d, r13d
0x1800c04fa  mov     [rsp+0AA0h+cbData], 820h
0x1800c0502  mov     [rcx], r13b
0x1800c0505  lea     rax, [rsp+0AA0h+hKey]
0x1800c050a  mov     rdi, rcx
0x1800c050d  mov     [rsp+0AA0h+Type], r13d
0x1800c0512  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c0519  mov     [rsp+0AA0h+hKey], r13
0x1800c051e  mov     r9d, 20119h; samDesired
0x1800c0524  mov     [rsp+0AA0h+phkResult], rax; phkResult
0x1800c0529  xor     r8d, r8d; ulOptions
0x1800c052c  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800c0533  call    cs:__imp_RegOpenKeyExW
0x1800c0539  mov     ebx, eax
0x1800c053b  cmp     eax, 2
0x1800c053e  jnz     short loc_1800C054B
0x1800c0540  mov     ebx, r13d
0x1800c0543  mov     [rdi], r13b
0x1800c0546  jmp     loc_1800C0777
0x1800c054b  test    eax, eax
0x1800c054d  jle     short loc_1800C0558
0x1800c054f  movzx   ebx, ax
0x1800c0552  or      ebx, 80070000h
0x1800c0558  lea     r12, aRegistryOperat; "Registry operation failed: [0x%x]."
0x1800c055f  test    ebx, ebx
0x1800c0561  jns     short loc_1800C0592
0x1800c0563  mov     edx, 422h; bool
0x1800c0568  mov     dword ptr [rsp+0AA0h+var_A70], ebx; char *
0x1800c056c  mov     [rsp+0AA0h+lpcbData], r12; int
0x1800c0571  lea     r9, aWindowsCompatA_285; "Windows::Compat::Appraiser::InboxCompon"...
0x1800c0578  mov     dword ptr [rsp+0AA0h+phkResult], ebx; char *
0x1800c057c  lea     r8, aOnecoreBaseApp_98; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c0583  mov     ecx, 1; this
0x1800c0588  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c058d  jmp     loc_1800C0777
0x1800c0592  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c0598  test    al, 1
0x1800c059a  jz      short loc_1800C05BB
0x1800c059c  mov     r9, r12; char *
0x1800c059f  mov     dword ptr [rsp+0AA0h+phkResult], ebx
0x1800c05a3  lea     r8, aWindowsCompatA_285; "Windows::Compat::Appraiser::InboxCompon"...
0x1800c05aa  mov     ecx, 422h; unsigned int
0x1800c05af  lea     rdx, aOnecoreBaseApp_98; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c05b6  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c05bb  mov     rcx, [rsp+0AA0h+hKey]; hKey
0x1800c05c0  lea     rax, [rsp+0AA0h+cbData]
0x1800c05c5  mov     [rsp+0AA0h+lpcbData], rax; lpcbData
0x1800c05ca  lea     r9, [rsp+0AA0h+Type]; lpType
0x1800c05cf  lea     rax, [rbp+9A0h+Data]
0x1800c05d6  xor     r8d, r8d; lpReserved
0x1800c05d9  lea     rdx, aWatchedfolders; "WatchedFolders"
0x1800c05e0  mov     [rsp+0AA0h+phkResult], rax; lpData
0x1800c05e5  call    cs:__imp_RegQueryValueExW
0x1800c05eb  mov     ebx, eax
0x1800c05ed  cmp     eax, 2
0x1800c05f0  jz      loc_1800C0540
0x1800c05f6  test    eax, eax
0x1800c05f8  jle     short loc_1800C0603
0x1800c05fa  movzx   ebx, ax
0x1800c05fd  or      ebx, 80070000h
0x1800c0603  test    ebx, ebx
0x1800c0605  jns     short loc_1800C0611
0x1800c0607  mov     edx, 432h
0x1800c060c  jmp     loc_1800C0568
0x1800c0611  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c0617  test    al, 1
0x1800c0619  jz      short loc_1800C063A
0x1800c061b  mov     r9, r12; char *
0x1800c061e  mov     dword ptr [rsp+0AA0h+phkResult], ebx
0x1800c0622  lea     r8, aWindowsCompatA_285; "Windows::Compat::Appraiser::InboxCompon"...
0x1800c0629  mov     ecx, 432h; unsigned int
0x1800c062e  lea     rdx, aOnecoreBaseApp_98; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c0635  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c063a  mov     eax, [rsp+0AA0h+cbData]
0x1800c063e  mov     edx, [rsp+0AA0h+Type]
0x1800c0642  test    eax, eax
0x1800c0644  jz      loc_1800C073B
0x1800c064a  cmp     edx, 7
0x1800c064d  jnz     loc_1800C073B
0x1800c0653  cmp     eax, 40Fh
0x1800c0658  jnb     short loc_1800C066D
0x1800c065a  lea     rcx, [rax+rax]
0x1800c065e  cmp     rcx, 820h
0x1800c0665  jnb     loc_1800C07B1
0x1800c066b  jmp     short loc_1800C0672
0x1800c066d  mov     ecx, 81Eh
0x1800c0672  mov     word ptr [rbp+rcx+9A0h+Data], r13w
0x1800c067b  lea     rdx, [rsp+0AA0h+Dst]; lpDst
0x1800c0680  lea     rcx, aPublicRecorded; "%PUBLIC%\\Recorded TV\\"
0x1800c0687  mov     r8d, 104h; nSize
0x1800c068d  call    cs:__imp_ExpandEnvironmentStringsW
0x1800c0693  mov     r13d, eax
0x1800c0696  dec     eax
0x1800c0698  cmp     eax, 103h
0x1800c069d  ja      short loc_1800C0701
0x1800c069f  xor     r13d, r13d
0x1800c06a2  lea     rbx, [rbp+9A0h+Data]
0x1800c06a9  cmp     [rdi], r13b
0x1800c06ac  jnz     short loc_1800C06FC
0x1800c06ae  lea     rax, [rbp+9A0h+var_22]
0x1800c06b5  cmp     rbx, rax
0x1800c06b8  jnb     short loc_1800C06FC
0x1800c06ba  cmp     r13w, word ptr [rbp+9A0h+Data]
0x1800c06c2  jz      short loc_1800C06FC
0x1800c06c4  mov     rdx, rbx
0x1800c06c7  lea     rcx, [rsp+0AA0h+Dst]
0x1800c06cc  call    cs:__imp__o__wcsicmp
0x1800c06d2  test    eax, eax
0x1800c06d4  lea     rdx, [rbp+9A0h+Data]
0x1800c06db  mov     ecx, eax
0x1800c06dd  setnz   al
0x1800c06e0  mov     [rdi], al
0x1800c06e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c06e6  inc     rax
0x1800c06e9  cmp     [rdx+rax*2], r13w
0x1800c06ee  jnz     short loc_1800C06E6
0x1800c06f0  lea     rbx, [rbx+rax*2]
0x1800c06f4  add     rbx, 2
0x1800c06f8  test    ecx, ecx
0x1800c06fa  jz      short loc_1800C06AE
0x1800c06fc  mov     ebx, r13d
0x1800c06ff  jmp     short loc_1800C0777
0x1800c0701  call    cs:__imp_GetLastError
0x1800c0707  mov     ebx, eax
0x1800c0709  test    eax, eax
0x1800c070b  jle     short loc_1800C0716
0x1800c070d  movzx   ebx, ax
0x1800c0710  or      ebx, 80070000h
0x1800c0716  test    ebx, ebx
0x1800c0718  mov     dword ptr [rsp+0AA0h+var_A70], r13d
0x1800c071d  mov     ecx, 80004005h
0x1800c0722  lea     rax, aExpandingEnvir; "Expanding Environment String failed: Ex"...
0x1800c0729  cmovns  ebx, ecx
0x1800c072c  mov     [rsp+0AA0h+lpcbData], rax
0x1800c0731  mov     edx, 445h
0x1800c0736  jmp     loc_1800C0571
0x1800c073b  mov     [rsp+0AA0h+var_A68], edx
0x1800c073f  lea     r9, aWindowsCompatA_285; "Windows::Compat::Appraiser::InboxCompon"...
0x1800c0746  mov     dword ptr [rsp+0AA0h+var_A70], eax; char *
0x1800c074a  lea     r8, aOnecoreBaseApp_98; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c0751  mov     ecx, 80004005h
0x1800c0756  lea     rax, aRegistryReturn; "Registry returned unexpected value of S"...
0x1800c075d  mov     [rsp+0AA0h+lpcbData], rax; int
0x1800c0762  mov     ebx, ecx
0x1800c0764  mov     dword ptr [rsp+0AA0h+phkResult], ecx; char *
0x1800c0768  mov     edx, 437h; bool
0x1800c076d  mov     ecx, 1; this
0x1800c0772  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c0777  mov     rcx, [rsp+0AA0h+hKey]; hKey
0x1800c077c  test    rcx, rcx
0x1800c077f  jz      short loc_1800C0787
0x1800c0781  call    cs:__imp_RegCloseKey
0x1800c0787  mov     eax, ebx
0x1800c0789  mov     rcx, [rbp+9A0h+var_20]
0x1800c0790  xor     rcx, rsp; StackCookie
0x1800c0793  call    __security_check_cookie
0x1800c0798  lea     r11, [rsp+0AA0h+var_10]
0x1800c07a0  mov     rbx, [r11+28h]
0x1800c07a4  mov     rdi, [r11+30h]
0x1800c07a8  mov     rsp, r11
0x1800c07ab  pop     r13
0x1800c07ad  pop     r12
0x1800c07af  pop     rbp
0x1800c07b0  retn
0x1800c07b1  call    __report_rangecheckfailure
```
