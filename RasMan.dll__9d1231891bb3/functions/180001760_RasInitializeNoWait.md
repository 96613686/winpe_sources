# RasInitializeNoWait

- ea: `0x180001760`
- end: `0x180001c5e`
- name: `RasInitializeNoWait`
- size: `1278`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18000b010`

## callees

- `0x180001760`
- `0x180001c70`
- `0x180020fd8`
- `0x180021000`
- `0x1800263ce`
- `0x180026400`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180001924`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180001924`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001a04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001ada`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001a04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001ada`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800019e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001abd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800019e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000193a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000193a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ae9`
- `WS2_32!__imp_WSAGetLastError` at `0x180001812`
- `WS2_32!__imp_WSAGetLastError` at `0x180001812`
- `WS2_32!__imp_WSAStartup` at `0x180001800`
- `WS2_32!__imp_WSAStartup` at `0x180001800`

## string_xrefs

- `0x180001917`: `rasmans.dll`
- `0x1800019dd`: `ServiceRequestInProcess`
- `0x180001ab6`: `ServiceInitialized`

## pseudocode

```c
__int64 RasInitializeNoWait()
{
  PVOID *v0; // rcx
  unsigned int Error; // eax
  unsigned int v2; // ebx
  PVOID *v3; // rcx
  __int64 v5; // rdx
  HMODULE Library; // rax
  DWORD v7; // eax
  PVOID *v8; // rcx
  __int64 v9; // rdx
  DWORD LastError; // eax
  DWORD v11; // eax
  WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  g_fRasmanService = IsRasmanProcess();
  if ( !g_fRasmanService )
  {
    v0 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
      v0 = (PVOID *)WPP_GLOBAL_Control;
    }
    hInstRasmans = 0;
    g_fnServiceRequest = 0;
    g_fnRasmanServiceInitialized = 0;
    if ( !g_fWinsockInitialized )
    {
      memset_0(&WSAData, 0, sizeof(WSAData));
      if ( WSAStartup(2u, &WSAData) )
      {
        Error = WSAGetLastError();
        v2 = Error;
        if ( Error )
        {
          v3 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v2;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_10:
            if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x40) != 0 && *((_BYTE *)v3 + 25) >= 6u )
              WPP_SF_d(v3[2], 65, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v2);
            return v2;
          }
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, Error);
        }
        v3 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_10;
      }
      v0 = (PVOID *)WPP_GLOBAL_Control;
      g_fWinsockInitialized = 1;
    }
    if ( v0 == &WPP_GLOBAL_Control || (*((_BYTE *)v0 + 28) & 0x40) == 0 || *((_BYTE *)v0 + 25) < 6u )
      return 0;
    v5 = 66;
    goto LABEL_21;
  }
  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hInstRasmans )
  {
LABEL_14:
    if ( v0 == &WPP_GLOBAL_Control || (*((_BYTE *)v0 + 28) & 0x40) == 0 || *((_BYTE *)v0 + 25) < 6u )
      return 0;
    v5 = 62;
LABEL_21:
    WPP_SF_d(v0[2], v5, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 0);
    return 0;
  }
  Library = LoadLibraryExA("rasmans.dll", 0, 0x800u);
  hInstRasmans = Library;
  if ( Library )
  {
    g_fnServiceRequest = (__int64)GetProcAddress(Library, "ServiceRequestInProcess");
    if ( !g_fnServiceRequest )
    {
      FreeLibrary(hInstRasmans);
      hInstRasmans = 0;
      LastError = GetLastError();
      if ( LastError )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return 711;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_49;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, LastError);
      }
      v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_49:
      if ( v8 == &WPP_GLOBAL_Control )
        return 711;
      if ( (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      {
        WPP_SF_d(v8[2], 57, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 711);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 0x40) == 0 || *((_BYTE *)v8 + 25) < 6u )
        return 711;
      v9 = 58;
      goto LABEL_72;
    }
    g_fnRasmanServiceInitialized = (__int64)GetProcAddress(hInstRasmans, "ServiceInitialized");
    if ( g_fnRasmanServiceInitialized )
    {
      v0 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_14;
    }
    FreeLibrary(hInstRasmans);
    hInstRasmans = 0;
    v11 = GetLastError();
    if ( v11 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return 711;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_64;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_64:
    if ( v8 == &WPP_GLOBAL_Control )
      return 711;
    if ( (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      WPP_SF_d(v8[2], 60, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 711);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 0x40) == 0 || *((_BYTE *)v8 + 25) < 6u )
      return 711;
    v9 = 61;
LABEL_72:
    WPP_SF_d(v8[2], v9, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 711);
    return 711;
  }
  v7 = GetLastError();
  if ( !v7 )
    goto LABEL_33;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_34:
      if ( v8 == &WPP_GLOBAL_Control )
        return 711;
      if ( (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      {
        WPP_SF_d(v8[2], 54, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 711);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 0x40) == 0 || *((_BYTE *)v8 + 25) < 6u )
        return 711;
      v9 = 55;
      goto LABEL_72;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
LABEL_33:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_34;
  }
  return 711;
}

```

## disassembly

```asm
0x180001760  push    rdi
0x180001762  sub     rsp, 1D0h
0x180001769  mov     rax, cs:__security_cookie
0x180001770  xor     rax, rsp
0x180001773  mov     [rsp+1D8h+var_18], rax
0x18000177b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001782  lea     rdi, WPP_GLOBAL_Control
0x180001789  cmp     rcx, rdi
0x18000178c  jz      short loc_180001798
0x18000178e  test    byte ptr [rcx+1Ch], 40h
0x180001792  jnz     loc_1800018BC
0x180001798  call    IsRasmanProcess
0x18000179d  mov     cs:g_fRasmanService, eax
0x1800017a3  test    eax, eax
0x1800017a5  jnz     loc_18000183E
0x1800017ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017b2  cmp     rcx, rdi
0x1800017b5  jz      short loc_1800017C1
0x1800017b7  test    byte ptr [rcx+1Ch], 40h
0x1800017bb  jnz     loc_180001BC1
0x1800017c1  xor     eax, eax
0x1800017c3  cmp     cs:g_fWinsockInitialized, eax
0x1800017c9  mov     cs:hInstRasmans, rax
0x1800017d0  mov     cs:g_fnServiceRequest, rax
0x1800017d7  mov     cs:g_fnRasmanServiceInitialized, rax
0x1800017de  jnz     loc_180001891
0x1800017e4  xor     edx, edx; Val
0x1800017e6  lea     rcx, [rsp+1D8h+WSAData]; void *
0x1800017eb  mov     r8d, 198h; Size
0x1800017f1  call    memset_0
0x1800017f6  mov     ecx, 2; wVersionRequested
0x1800017fb  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x180001800  call    cs:__imp_WSAStartup
0x180001806  test    eax, eax
0x180001808  jz      short loc_180001880
0x18000180a  mov     [rsp+1D8h+arg_0], rbx
0x180001812  call    cs:__imp_WSAGetLastError
0x180001818  mov     ebx, eax
0x18000181a  test    eax, eax
0x18000181c  jnz     loc_180001BEC
0x180001822  mov     rcx, cs:WPP_GLOBAL_Control
0x180001829  cmp     rcx, rdi
0x18000182c  jnz     loc_180001C2D
0x180001832  mov     eax, ebx
0x180001834  mov     rbx, [rsp+1D8h+arg_0]
0x18000183c  jmp     short loc_180001867
0x18000183e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001845  cmp     rcx, rdi
0x180001848  jnz     loc_1800018E0
0x18000184e  cmp     cs:hInstRasmans, 0
0x180001856  jz      loc_180001915
0x18000185c  cmp     rcx, rdi
0x18000185f  jnz     loc_180001BA3
0x180001865  xor     eax, eax
0x180001867  mov     rcx, [rsp+1D8h+var_18]
0x18000186f  xor     rcx, rsp; StackCookie
0x180001872  call    __security_check_cookie
0x180001877  add     rsp, 1D0h
0x18000187e  pop     rdi
0x18000187f  retn
0x180001880  mov     rcx, cs:WPP_GLOBAL_Control
0x180001887  mov     cs:g_fWinsockInitialized, 1
0x180001891  cmp     rcx, rdi
0x180001894  jz      short loc_180001865
0x180001896  test    byte ptr [rcx+1Ch], 40h
0x18000189a  jz      short loc_180001865
0x18000189c  cmp     byte ptr [rcx+19h], 6
0x1800018a0  jb      short loc_180001865
0x1800018a2  mov     edx, 42h ; 'B'
0x1800018a7  mov     rcx, [rcx+10h]
0x1800018ab  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800018b2  xor     r9d, r9d
0x1800018b5  call    WPP_SF_d
0x1800018ba  jmp     short loc_180001865
0x1800018bc  cmp     byte ptr [rcx+19h], 6
0x1800018c0  jb      loc_180001798
0x1800018c6  mov     rcx, [rcx+10h]
0x1800018ca  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800018d1  mov     edx, 33h ; '3'
0x1800018d6  call    WPP_SF_
0x1800018db  jmp     loc_180001798
0x1800018e0  test    byte ptr [rcx+1Ch], 40h
0x1800018e4  jz      loc_18000184E
0x1800018ea  cmp     byte ptr [rcx+19h], 5
0x1800018ee  jb      loc_18000184E
0x1800018f4  mov     rcx, [rcx+10h]
0x1800018f8  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800018ff  mov     edx, 34h ; '4'
0x180001904  call    WPP_SF_
0x180001909  mov     rcx, cs:WPP_GLOBAL_Control
0x180001910  jmp     loc_18000184E
0x180001915  xor     edx, edx; hFile
0x180001917  lea     rcx, LibFileName; "rasmans.dll"
0x18000191e  mov     r8d, 800h; dwFlags
0x180001924  call    cs:__imp_LoadLibraryExA
0x18000192a  mov     cs:hInstRasmans, rax
0x180001931  test    rax, rax
0x180001934  jnz     loc_1800019DD
0x18000193a  call    cs:__imp_GetLastError
0x180001940  test    eax, eax
0x180001942  jz      short loc_180001978
0x180001944  mov     rcx, cs:WPP_GLOBAL_Control
0x18000194b  cmp     rcx, rdi
0x18000194e  jz      loc_180001B8D
0x180001954  test    byte ptr [rcx+1Ch], 40h
0x180001958  jz      short loc_18000197F
0x18000195a  cmp     byte ptr [rcx+19h], 2
0x18000195e  jb      short loc_18000197F
0x180001960  mov     rcx, [rcx+10h]
0x180001964  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18000196b  mov     edx, 35h ; '5'
0x180001970  mov     r9d, eax
0x180001973  call    WPP_SF_d
0x180001978  mov     rcx, cs:WPP_GLOBAL_Control
0x18000197f  cmp     rcx, rdi
0x180001982  jz      loc_180001B8D
0x180001988  test    byte ptr [rcx+1Ch], 40h
0x18000198c  jz      short loc_1800019B6
0x18000198e  cmp     byte ptr [rcx+19h], 2
0x180001992  jb      short loc_1800019B6
0x180001994  mov     rcx, [rcx+10h]
0x180001998  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18000199f  mov     edx, 36h ; '6'
0x1800019a4  mov     r9d, 2C7h
0x1800019aa  call    WPP_SF_d
0x1800019af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019b6  cmp     rcx, rdi
0x1800019b9  jz      loc_180001B8D
0x1800019bf  test    byte ptr [rcx+1Ch], 40h
0x1800019c3  jz      loc_180001B8D
0x1800019c9  cmp     byte ptr [rcx+19h], 6
0x1800019cd  jb      loc_180001B8D
0x1800019d3  mov     edx, 37h ; '7'
0x1800019d8  jmp     loc_180001B77
0x1800019dd  lea     rdx, ProcName; "ServiceRequestInProcess"
0x1800019e4  mov     rcx, rax; hModule
0x1800019e7  call    cs:__imp_GetProcAddress
0x1800019ed  mov     rcx, cs:hInstRasmans; hModule
0x1800019f4  mov     cs:g_fnServiceRequest, rax
0x1800019fb  test    rax, rax
0x1800019fe  jnz     loc_180001AB6
0x180001a04  call    cs:__imp_FreeLibrary
0x180001a0a  xor     eax, eax
0x180001a0c  mov     cs:hInstRasmans, rax
0x180001a13  call    cs:__imp_GetLastError
0x180001a19  test    eax, eax
0x180001a1b  jz      short loc_180001A51
0x180001a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a24  cmp     rcx, rdi
0x180001a27  jz      loc_180001B8D
0x180001a2d  test    byte ptr [rcx+1Ch], 40h
0x180001a31  jz      short loc_180001A58
0x180001a33  cmp     byte ptr [rcx+19h], 2
0x180001a37  jb      short loc_180001A58
0x180001a39  mov     rcx, [rcx+10h]
0x180001a3d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001a44  mov     edx, 38h ; '8'
0x180001a49  mov     r9d, eax
0x180001a4c  call    WPP_SF_d
0x180001a51  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a58  cmp     rcx, rdi
0x180001a5b  jz      loc_180001B8D
0x180001a61  test    byte ptr [rcx+1Ch], 40h
0x180001a65  jz      short loc_180001A8F
0x180001a67  cmp     byte ptr [rcx+19h], 2
0x180001a6b  jb      short loc_180001A8F
0x180001a6d  mov     rcx, [rcx+10h]
0x180001a71  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001a78  mov     edx, 39h ; '9'
0x180001a7d  mov     r9d, 2C7h
0x180001a83  call    WPP_SF_d
0x180001a88  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a8f  cmp     rcx, rdi
0x180001a92  jz      loc_180001B8D
0x180001a98  test    byte ptr [rcx+1Ch], 40h
0x180001a9c  jz      loc_180001B8D
0x180001aa2  cmp     byte ptr [rcx+19h], 6
0x180001aa6  jb      loc_180001B8D
0x180001aac  mov     edx, 3Ah ; ':'
0x180001ab1  jmp     loc_180001B77
0x180001ab6  lea     rdx, aServiceinitial; "ServiceInitialized"
0x180001abd  call    cs:__imp_GetProcAddress
0x180001ac3  mov     cs:g_fnRasmanServiceInitialized, rax
0x180001aca  test    rax, rax
0x180001acd  jnz     loc_180001B97
0x180001ad3  mov     rcx, cs:hInstRasmans; hLibModule
0x180001ada  call    cs:__imp_FreeLibrary
0x180001ae0  xor     eax, eax
0x180001ae2  mov     cs:hInstRasmans, rax
0x180001ae9  call    cs:__imp_GetLastError
0x180001aef  test    eax, eax
0x180001af1  jz      short loc_180001B27
0x180001af3  mov     rcx, cs:WPP_GLOBAL_Control
0x180001afa  cmp     rcx, rdi
0x180001afd  jz      loc_180001B8D
0x180001b03  test    byte ptr [rcx+1Ch], 40h
0x180001b07  jz      short loc_180001B2E
0x180001b09  cmp     byte ptr [rcx+19h], 2
0x180001b0d  jb      short loc_180001B2E
0x180001b0f  mov     rcx, [rcx+10h]
0x180001b13  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001b1a  mov     edx, 3Bh ; ';'
0x180001b1f  mov     r9d, eax
0x180001b22  call    WPP_SF_d
0x180001b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b2e  cmp     rcx, rdi
0x180001b31  jz      short loc_180001B8D
0x180001b33  test    byte ptr [rcx+1Ch], 40h
0x180001b37  jz      short loc_180001B61
0x180001b39  cmp     byte ptr [rcx+19h], 2
0x180001b3d  jb      short loc_180001B61
0x180001b3f  mov     rcx, [rcx+10h]
0x180001b43  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001b4a  mov     edx, 3Ch ; '<'
0x180001b4f  mov     r9d, 2C7h
0x180001b55  call    WPP_SF_d
0x180001b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b61  cmp     rcx, rdi
0x180001b64  jz      short loc_180001B8D
0x180001b66  test    byte ptr [rcx+1Ch], 40h
0x180001b6a  jz      short loc_180001B8D
0x180001b6c  cmp     byte ptr [rcx+19h], 6
0x180001b70  jb      short loc_180001B8D
0x180001b72  mov     edx, 3Dh ; '='
0x180001b77  mov     rcx, [rcx+10h]
0x180001b7b  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001b82  mov     r9d, 2C7h
0x180001b88  call    WPP_SF_d
0x180001b8d  mov     eax, 2C7h
0x180001b92  jmp     loc_180001867
0x180001b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b9e  jmp     loc_18000185C
0x180001ba3  test    byte ptr [rcx+1Ch], 40h
0x180001ba7  jz      loc_180001865
0x180001bad  cmp     byte ptr [rcx+19h], 6
0x180001bb1  jb      loc_180001865
0x180001bb7  mov     edx, 3Eh ; '>'
0x180001bbc  jmp     loc_1800018A7
0x180001bc1  cmp     byte ptr [rcx+19h], 5
0x180001bc5  jb      loc_1800017C1
0x180001bcb  mov     rcx, [rcx+10h]
0x180001bcf  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001bd6  mov     edx, 3Fh ; '?'
0x180001bdb  call    WPP_SF_
0x180001be0  mov     rcx, cs:WPP_GLOBAL_Control
0x180001be7  jmp     loc_1800017C1
0x180001bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bf3  cmp     rcx, rdi
0x180001bf6  jz      loc_180001832
0x180001bfc  test    byte ptr [rcx+1Ch], 40h
0x180001c00  jz      loc_180001829
0x180001c06  cmp     byte ptr [rcx+19h], 2
0x180001c0a  jb      loc_180001829
0x180001c10  mov     rcx, [rcx+10h]
0x180001c14  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001c1b  mov     edx, 40h ; '@'
0x180001c20  mov     r9d, ebx
0x180001c23  call    WPP_SF_d
0x180001c28  jmp     loc_180001822
0x180001c2d  test    byte ptr [rcx+1Ch], 40h
0x180001c31  jz      loc_180001832
0x180001c37  cmp     byte ptr [rcx+19h], 6
0x180001c3b  jb      loc_180001832
0x180001c41  mov     rcx, [rcx+10h]
0x180001c45  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001c4c  mov     edx, 41h ; 'A'
0x180001c51  mov     r9d, ebx
0x180001c54  call    WPP_SF_d
0x180001c59  jmp     loc_180001832
```
