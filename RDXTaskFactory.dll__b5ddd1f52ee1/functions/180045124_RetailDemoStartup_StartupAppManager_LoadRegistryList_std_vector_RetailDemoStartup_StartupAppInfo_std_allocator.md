# RetailDemoStartup::StartupAppManager::LoadRegistryList(std::vector<RetailDemoStartup::StartupAppInfo,std::allocator<RetailDemoStartup::StartupAppInfo>> &)

- ea: `0x180045124`
- end: `0x1800453a4`
- name: `?LoadRegistryList@StartupAppManager@RetailDemoStartup@@AEAAJAEAV?$vector@UStartupAppInfo@RetailDemoStartup@@V?$allocator@UStartupAppInfo@RetailDemoStartup@@@std@@@std@@@Z`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800453ac`

## callees

- `0x180003390`
- `0x18000db70`
- `0x1800438dc`
- `0x180043c9c`
- `0x1800440ec`
- `0x180045124`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004521a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180045351`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004521a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180045351`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800451c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800451c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045364`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045364`

## string_xrefs

- `0x18004516a`: `Win32-Registry-HKLM`
- `0x180045184`: `Win32-Registry-HKCU`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RetailDemoStartup::StartupAppManager::LoadRegistryList(__int64 a1, __int64 a2)
{
  HKEY *v3; // rbx
  __m128i si128; // xmm6
  int v5; // esi
  __int64 v6; // r8
  __int64 v7; // r8
  HKEY v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  DWORD v12; // edx
  DWORD cbData; // [rsp+48h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD cchValueName[2]; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v18[6]; // [rsp+60h] [rbp-A8h] BYREF
  char v19; // [rsp+90h] [rbp-78h] BYREF
  _OWORD v20[2]; // [rsp+98h] [rbp-70h] BYREF
  _OWORD v21[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v22; // [rsp+D8h] [rbp-30h]
  __m128i v23; // [rsp+E8h] [rbp-20h]
  _OWORD v24[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int16 v25; // [rsp+118h] [rbp+10h]
  __int64 v26; // [rsp+11Ch] [rbp+14h]
  WCHAR ValueName[256]; // [rsp+128h] [rbp+20h] BYREF
  _WORD Data[1024]; // [rsp+328h] [rbp+220h] BYREF

  v18[0] = -2147483646;
  v18[1] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Run";
  v18[2] = L"Win32-Registry-HKLM";
  v18[3] = -2147483647;
  v18[4] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Run";
  v18[5] = L"Win32-Registry-HKCU";
  v3 = (HKEY *)v18;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    hKey = 0;
    if ( !RegOpenKeyExW(*v3, (LPCWSTR)v3[1], 0, 0x20019u, &hKey) )
    {
      Type = 0;
      cchValueName[0] = 256;
      cbData = 2048;
      if ( !RegEnumValueW(hKey, 0, ValueName, cchValueName, 0, &Type, (LPBYTE)Data, &cbData) )
      {
        v5 = 1;
        do
        {
          if ( Type - 1 <= 1 )
          {
            v20[0] = 0;
            v20[1] = si128;
            LOWORD(v20[0]) = 0;
            v21[0] = 0;
            v21[1] = si128;
            LOWORD(v21[0]) = 0;
            v22 = 0;
            v23 = si128;
            LOWORD(v22) = 0;
            v24[0] = 0;
            v24[1] = si128;
            LOWORD(v24[0]) = 0;
            v6 = -1;
            do
              ++v6;
            while ( ValueName[v6] );
            std::wstring::_Assign<unsigned short>(v20, ValueName, v6);
            v7 = -1;
            do
              ++v7;
            while ( Data[v7] );
            std::wstring::_Assign<unsigned short>(v21, Data, v7);
            v8 = v3[2];
            v9 = -1;
            do
              ++v9;
            while ( *((_WORD *)v8 + v9) );
            std::wstring::_Assign<unsigned short>(v24, v8, v9);
            v25 = 257;
            v26 = 0;
            v11 = *(_QWORD *)(a2 + 8);
            if ( v11 == *(_QWORD *)(a2 + 16) )
            {
              std::vector<RetailDemoStartup::StartupAppInfo>::_Emplace_reallocate<RetailDemoStartup::StartupAppInfo const &>(
                a2,
                v11,
                v20);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<RetailDemoStartup::StartupAppInfo>>::construct<RetailDemoStartup::StartupAppInfo,RetailDemoStartup::StartupAppInfo const &>(
                v10,
                v11,
                v20);
              *(_QWORD *)(a2 + 8) += 144LL;
            }
            RetailDemoStartup::StartupAppInfo::~StartupAppInfo((RetailDemoStartup::StartupAppInfo *)v20);
          }
          cchValueName[0] = 256;
          cbData = 2048;
          v12 = v5++;
        }
        while ( !RegEnumValueW(hKey, v12, ValueName, cchValueName, 0, &Type, (LPBYTE)Data, &cbData) );
      }
      RegCloseKey(hKey);
    }
    v3 += 3;
  }
  while ( v3 != (HKEY *)&v19 );
  return 0;
}

```

## disassembly

```asm
0x180045124  mov     rax, rsp
0x180045127  push    rbp
0x180045128  push    rbx
0x180045129  push    rsi
0x18004512a  push    rdi
0x18004512b  push    r14
0x18004512d  push    r15
0x18004512f  lea     rbp, [rax-0A78h]
0x180045136  sub     rsp, 0B48h
0x18004513d  movaps  xmmword ptr [rax-48h], xmm6
0x180045141  mov     rax, cs:__security_cookie
0x180045148  xor     rax, rsp
0x18004514b  mov     [rbp+0A70h+var_50], rax
0x180045152  mov     rdi, rdx
0x180045155  mov     [rsp+0B70h+var_B18], 0FFFFFFFF80000002h
0x18004515e  lea     rcx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180045165  mov     [rsp+0B70h+var_B10], rcx
0x18004516a  lea     rax, S2; "Win32-Registry-HKLM"
0x180045171  mov     [rsp+0B70h+var_B08], rax
0x180045176  mov     [rsp+0B70h+var_B00], 0FFFFFFFF80000001h
0x18004517f  mov     [rsp+78h], rcx
0x180045184  lea     rax, aWin32RegistryH; "Win32-Registry-HKCU"
0x18004518b  mov     [rbp+0A70h+var_AF0], rax
0x18004518f  lea     rbx, [rsp+0B70h+var_B18]
0x180045194  xor     r14d, r14d
0x180045197  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004519b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800451a3  mov     [rsp+0B70h+hKey], r14
0x1800451a8  lea     rax, [rsp+0B70h+hKey]
0x1800451ad  mov     [rsp+0B70h+phkResult], rax; phkResult
0x1800451b2  mov     r9d, 20019h; samDesired
0x1800451b8  xor     r8d, r8d; ulOptions
0x1800451bb  mov     rdx, [rbx+8]; lpSubKey
0x1800451bf  mov     rcx, [rbx]; hKey
0x1800451c2  call    cs:__imp_RegOpenKeyExW
0x1800451c8  test    eax, eax
0x1800451ca  jnz     loc_18004536A
0x1800451d0  mov     [rsp+0B70h+Type], r14d
0x1800451d5  mov     [rsp+0B70h+cchValueName], 100h
0x1800451dd  mov     [rsp+0B70h+cbData], 800h
0x1800451e5  lea     rax, [rsp+0B70h+cbData]
0x1800451ea  mov     [rsp+0B70h+lpcbData], rax; lpcbData
0x1800451ef  lea     rax, [rbp+0A70h+Data]
0x1800451f6  mov     [rsp+0B70h+lpData], rax; lpData
0x1800451fb  lea     rax, [rsp+0B70h+Type]
0x180045200  mov     [rsp+0B70h+lpType], rax; lpType
0x180045205  mov     [rsp+0B70h+phkResult], r14; lpReserved
0x18004520a  lea     r9, [rsp+0B70h+cchValueName]; lpcchValueName
0x18004520f  lea     r8, [rbp+0A70h+ValueName]; lpValueName
0x180045213  xor     edx, edx; dwIndex
0x180045215  mov     rcx, [rsp+0B70h+hKey]; hKey
0x18004521a  call    cs:__imp_RegEnumValueW
0x180045220  test    eax, eax
0x180045222  jnz     loc_18004535F
0x180045228  lea     esi, [rax+1]
0x18004522b  mov     eax, [rsp+0B70h+Type]
0x18004522f  dec     eax
0x180045231  cmp     eax, 1
0x180045234  ja      loc_18004530A
0x18004523a  xorps   xmm0, xmm0
0x18004523d  movups  [rbp+0A70h+var_AE0], xmm0
0x180045241  movdqa  [rbp+0A70h+var_AD0], xmm6
0x180045246  mov     word ptr [rbp+0A70h+var_AE0], r14w
0x18004524b  movups  [rbp+0A70h+var_AC0], xmm0
0x18004524f  movdqa  [rbp+0A70h+var_AB0], xmm6
0x180045254  mov     word ptr [rbp+0A70h+var_AC0], r14w
0x180045259  movups  [rbp+0A70h+var_AA0], xmm0
0x18004525d  movdqa  [rbp+0A70h+var_A90], xmm6
0x180045262  mov     word ptr [rbp+0A70h+var_AA0], r14w
0x180045267  movups  [rbp+0A70h+var_A80], xmm0
0x18004526b  movdqa  [rbp+0A70h+var_A70], xmm6
0x180045270  mov     word ptr [rbp+0A70h+var_A80], r14w
0x180045275  lea     rax, [rbp+0A70h+ValueName]
0x180045279  mov     r8, r15
0x18004527c  inc     r8
0x18004527f  cmp     [rax+r8*2], r14w
0x180045284  jnz     short loc_18004527C
0x180045286  lea     rdx, [rbp+0A70h+ValueName]
0x18004528a  lea     rcx, [rbp+0A70h+var_AE0]
0x18004528e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180045293  lea     rax, [rbp+0A70h+Data]
0x18004529a  mov     r8, r15
0x18004529d  inc     r8
0x1800452a0  cmp     [rax+r8*2], r14w
0x1800452a5  jnz     short loc_18004529D
0x1800452a7  lea     rdx, [rbp+0A70h+Data]
0x1800452ae  lea     rcx, [rbp+0A70h+var_AC0]
0x1800452b2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800452b7  mov     rdx, [rbx+10h]
0x1800452bb  mov     r8, r15
0x1800452be  inc     r8
0x1800452c1  cmp     [rdx+r8*2], r14w
0x1800452c6  jnz     short loc_1800452BE
0x1800452c8  lea     rcx, [rbp+0A70h+var_A80]
0x1800452cc  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800452d1  mov     [rbp+0A70h+var_A60], 101h
0x1800452d7  mov     [rbp+0A70h+var_A5C], r14
0x1800452db  mov     rdx, [rdi+8]
0x1800452df  lea     r8, [rbp+0A70h+var_AE0]
0x1800452e3  cmp     rdx, [rdi+10h]
0x1800452e7  jz      short loc_1800452F8
0x1800452e9  call    ??$construct@UStartupAppInfo@RetailDemoStartup@@AEBU12@@?$_Default_allocator_traits@V?$allocator@UStartupAppInfo@RetailDemoStartup@@@std@@@std@@SAXAEAV?$allocator@UStartupAppInfo@RetailDemoStartup@@@1@QEAUStartupAppInfo@RetailDemoStartup@@AEBU34@@Z; std::_Default_allocator_traits<std::allocator<RetailDemoStartup::StartupAppInfo>>::construct<RetailDemoStartup::StartupAppInfo,RetailDemoStartup::StartupAppInfo const &>(std::allocator<RetailDemoStartup::StartupAppInfo> &,RetailDemoStartup::StartupAppInfo * const,RetailDemoStartup::StartupAppInfo const &)
0x1800452ee  add     qword ptr [rdi+8], 90h
0x1800452f6  jmp     short loc_180045301
0x1800452f8  mov     rcx, rdi
0x1800452fb  call    ??$_Emplace_reallocate@AEBUStartupAppInfo@RetailDemoStartup@@@?$vector@UStartupAppInfo@RetailDemoStartup@@V?$allocator@UStartupAppInfo@RetailDemoStartup@@@std@@@std@@AEAAPEAUStartupAppInfo@RetailDemoStartup@@QEAU23@AEBU23@@Z; std::vector<RetailDemoStartup::StartupAppInfo>::_Emplace_reallocate<RetailDemoStartup::StartupAppInfo const &>(RetailDemoStartup::StartupAppInfo * const,RetailDemoStartup::StartupAppInfo const &)
0x180045300  nop
0x180045301  lea     rcx, [rbp+0A70h+var_AE0]; this
0x180045305  call    ??1StartupAppInfo@RetailDemoStartup@@QEAA@XZ; RetailDemoStartup::StartupAppInfo::~StartupAppInfo(void)
0x18004530a  mov     [rsp+0B70h+cchValueName], 100h
0x180045312  mov     [rsp+0B70h+cbData], 800h
0x18004531a  mov     edx, esi; dwIndex
0x18004531c  inc     esi
0x18004531e  lea     rax, [rsp+0B70h+cbData]
0x180045323  mov     [rsp+0B70h+lpcbData], rax; lpcbData
0x180045328  lea     rax, [rbp+0A70h+Data]
0x18004532f  mov     [rsp+0B70h+lpData], rax; lpData
0x180045334  lea     rax, [rsp+0B70h+Type]
0x180045339  mov     [rsp+0B70h+lpType], rax; lpType
0x18004533e  mov     [rsp+0B70h+phkResult], r14; lpReserved
0x180045343  lea     r9, [rsp+0B70h+cchValueName]; lpcchValueName
0x180045348  lea     r8, [rbp+0A70h+ValueName]; lpValueName
0x18004534c  mov     rcx, [rsp+0B70h+hKey]; hKey
0x180045351  call    cs:__imp_RegEnumValueW
0x180045357  test    eax, eax
0x180045359  jz      loc_18004522B
0x18004535f  mov     rcx, [rsp+0B70h+hKey]; hKey
0x180045364  call    cs:__imp_RegCloseKey
0x18004536a  add     rbx, 18h
0x18004536e  lea     rax, [rbp+0A70h+var_AE8]
0x180045372  cmp     rbx, rax
0x180045375  jnz     loc_1800451A3
0x18004537b  xor     eax, eax
0x18004537d  mov     rcx, [rbp+0A70h+var_50]
0x180045384  xor     rcx, rsp; StackCookie
0x180045387  call    __security_check_cookie
0x18004538c  movaps  xmm6, [rsp+0B70h+var_48+8]
0x180045394  add     rsp, 0B48h
0x18004539b  pop     r15
0x18004539d  pop     r14
0x18004539f  pop     rdi
0x1800453a0  pop     rsi
0x1800453a1  pop     rbx
0x1800453a2  pop     rbp
0x1800453a3  retn
```
