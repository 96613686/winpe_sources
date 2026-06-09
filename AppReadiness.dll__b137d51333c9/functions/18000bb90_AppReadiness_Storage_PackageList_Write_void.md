# AppReadiness::Storage::PackageList::Write(void)

- ea: `0x18000bb90`
- end: `0x18000bff8`
- name: `?Write@PackageList@Storage@AppReadiness@@QEAAXXZ`
- size: `1128`
- prototype: `void __fastcall(AppReadiness::Storage::PackageList *__hidden this)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180010afc`
- `0x180018e7c`
- `0x180028114`

## callees

- `0x180009d60`
- `0x180009e10`
- `0x18000aac0`
- `0x18000bb90`
- `0x18000c000`
- `0x180027a4c`
- `0x18002c40c`
- `0x18003235c`
- `0x180033d30`
- `0x180038f14`
- `0x18003e210`
- `0x18003e234`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bbe6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bbe6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000be9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000be9a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000beed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bf34`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000beed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bf34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf15`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000be00`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000be00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bc58`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bc58`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000bcc4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000bcc4`

## string_xrefs

- `0x18000bf43`: `onecoreuap\shell\appreadiness\src\core\packagelist.cpp`
- `0x18000bf4f`: `AppReadiness::Storage::WriteRegistryValue`
- `0x18000bf56`: `SHRegSetDWORD(root, subKey, valueName, static_cast<DWORD>(value))`

## pseudocode

```c
void __fastcall AppReadiness::Storage::PackageList::Write(AppReadiness::Storage::PackageList *this)
{
  int v2; // edi
  __int64 (__fastcall *v3)(LPCWCH, LPCWCH); // r13
  __int64 v4; // rbx
  __int64 v5; // r14
  const WCHAR *v6; // rdx
  HKEY v7; // rsi
  HKEY v8; // rcx
  bool v9; // sf
  HKEY v10; // r12
  const WCHAR *v11; // rsi
  HKEY v12; // r14
  const WCHAR *v13; // rdx
  __int64 v14; // r8
  __int128 *p_pExceptionObject; // rdx
  __int64 v16; // rdi
  __int64 i; // rbx
  int v18; // ebx
  const WCHAR *v19; // rdx
  _QWORD *v20; // rbx
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  int v23; // eax
  int LastError; // eax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  void **v27; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h]
  __int64 (__fastcall *v29)(LPCWCH, LPCWCH); // [rsp+70h] [rbp-90h] BYREF
  __int128 v30; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h]
  unsigned __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v33)(LPCWCH, LPCWCH); // [rsp+A0h] [rbp-60h]
  DWORD v34; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v35)(LPCWCH, LPCWCH); // [rsp+B0h] [rbp-50h]
  void *v36; // [rsp+B8h] [rbp-48h] BYREF
  HKEY v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  __int128 pExceptionObject; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v40; // [rsp+E0h] [rbp-20h]

  v2 = 0;
  AppReadiness::Storage::PackageList::OpenUserQueueRoot(&v27, *(_QWORD *)this, 983103);
  v3 = (__int64 (__fastcall *)(LPCWCH, LPCWCH))hSemaphore;
  v33 = (__int64 (__fastcall *)(LPCWCH, LPCWCH))hSemaphore;
  v34 = WaitForSingleObjectEx(hSemaphore, 0xFFFFFFFF, 0);
  v35 = v3;
  v4 = *((_QWORD *)this + 1);
  v5 = *((_QWORD *)this + 2);
  while ( v4 != v5 )
  {
    if ( *(int *)(v4 + 32) > 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( *(_QWORD *)(v4 + 24) <= 7u )
      v6 = (const WCHAR *)v4;
    else
      v6 = *(const WCHAR **)v4;
    v7 = hKey;
    *(_DWORD *)Data = *(_DWORD *)(v4 + 32);
    phkResult = 0;
    if ( v6 && *v6 )
    {
      v2 = RegCreateKeyExW(hKey, v6, 0, 0, 0, 2u, 0, &phkResult, 0);
      if ( v2 )
        goto LABEL_11;
      v8 = phkResult;
    }
    else
    {
      v8 = hKey;
      phkResult = hKey;
    }
    v2 = RegSetValueExW(v8, L"Operation", 0, 4u, Data, 4u);
    if ( phkResult != v7 )
      RegCloseKey(phkResult);
LABEL_11:
    v9 = v2 < 0;
    if ( v2 > 0 )
    {
      v2 = (unsigned __int16)v2 | 0x80070000;
      v9 = v2 < 0;
    }
    if ( v9 )
      goto LABEL_64;
    v4 += 40;
    v2 = 0;
  }
  AppReadiness::Storage::PackageList::GetSubkeys(&v36, hKey);
  v10 = (HKEY)v36;
  v11 = (const WCHAR *)v36;
  v12 = v37;
  if ( v36 == v37 )
    goto LABEL_42;
  v3 = AppReadiness::Storage::MatchPackageFamilyName;
LABEL_21:
  if ( *((_QWORD *)v11 + 3) > 7u )
  {
    v13 = *(const WCHAR **)v11;
    goto LABEL_23;
  }
  while ( 1 )
  {
    v13 = v11;
LABEL_23:
    pExceptionObject = 0;
    v40 = 0;
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject);
    v29 = v3;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    p_pExceptionObject = &pExceptionObject;
    if ( *((_QWORD *)&v40 + 1) > 7u )
      p_pExceptionObject = (__int128 *)pExceptionObject;
    std::wstring::_Construct<2,unsigned short const *>(&v30, p_pExceptionObject, v40);
    phkResult = (HKEY)&v29;
    v16 = *((_QWORD *)this + 2);
    for ( i = *((_QWORD *)this + 1); i != v16; i += 40 )
    {
      if ( (unsigned __int8)v29((LPCWCH)&v30, (LPCWCH)i) )
        break;
    }
    if ( v32 > 7 )
      std::_Deallocate<16>(v30, 2 * v32 + 2);
    v2 = 0;
    v31 = 0;
    v32 = 7;
    LOWORD(v30) = 0;
    if ( i == *((_QWORD *)this + 2) )
      v18 = 0;
    else
      v18 = *(_DWORD *)(i + 32);
    if ( *((_QWORD *)&v40 + 1) > 7u )
      std::_Deallocate<16>(pExceptionObject, 2LL * *((_QWORD *)&v40 + 1) + 2);
    if ( !v18 )
    {
      if ( *((_QWORD *)v11 + 3) <= 7u )
        v19 = v11;
      else
        v19 = *(const WCHAR **)v11;
      RegDeleteTreeW(hKey, v19);
    }
    v11 += 16;
    if ( v11 != (const WCHAR *)v12 )
      goto LABEL_21;
    v3 = v33;
LABEL_42:
    if ( v10 )
    {
      v20 = v10;
      if ( v10 != v12 )
      {
        do
        {
          v21 = v20[3];
          if ( v21 > 7 )
            std::_Deallocate<16>(*v20, 2 * v21 + 2);
          v20[2] = 0;
          v20[3] = 7;
          *(_WORD *)v20 = 0;
          v20 += 4;
        }
        while ( v20 != (_QWORD *)v12 );
      }
      v22 = (v38 - (_QWORD)v10) & 0xFFFFFFFFFFFFFFE0uLL;
      *(_QWORD *)Data = v22;
      phkResult = v10;
      if ( v22 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned((void **)&phkResult, (unsigned __int64 *)Data);
        v10 = phkResult;
        v22 = *(_QWORD *)Data;
      }
      operator delete(v10, v22);
    }
    if ( v3 && (v34 & 0xFFFFFF7F) == 0 && !ReleaseSemaphore(v3, 1, 0) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RaiseException(LastError, 1u, 0, 0);
LABEL_64:
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v2,
        "SHRegSetDWORD(root, subKey, valueName, static_cast<DWORD>(value))",
        "AppReadiness::Storage::WriteRegistryValue",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packagelist.cpp",
        126);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    v27 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
    if ( !hKey
      || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v27) )
    {
      break;
    }
    v23 = GetLastError();
    if ( v23 > 0 )
      v23 = (unsigned __int16)v23 | 0x80070000;
    RaiseException(v23, 1u, 0, 0);
  }
}

```

## disassembly

```asm
0x18000bb90  push    rbp
0x18000bb92  push    rbx
0x18000bb93  push    rsi
0x18000bb94  push    rdi
0x18000bb95  push    r12
0x18000bb97  push    r13
0x18000bb99  push    r14
0x18000bb9b  push    r15
0x18000bb9d  lea     rbp, [rsp-8]
0x18000bba2  sub     rsp, 108h
0x18000bba9  mov     rax, cs:__security_cookie
0x18000bbb0  xor     rax, rsp
0x18000bbb3  mov     [rbp+40h+var_48], rax
0x18000bbb7  mov     r15, rcx
0x18000bbba  xor     edi, edi
0x18000bbbc  mov     r8d, 0F003Fh
0x18000bbc2  mov     rdx, [rcx]
0x18000bbc5  lea     rcx, [rsp+140h+var_E0]
0x18000bbca  call    ?OpenUserQueueRoot@PackageList@Storage@AppReadiness@@SA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@PEBVUser@3@K@Z; AppReadiness::Storage::PackageList::OpenUserQueueRoot(AppReadiness::User const *,ulong)
0x18000bbcf  nop
0x18000bbd0  mov     r13, cs:hSemaphore
0x18000bbd7  mov     [rbp+40h+var_A0], r13
0x18000bbdb  xor     r8d, r8d; bAlertable
0x18000bbde  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000bbe3  mov     rcx, r13; hHandle
0x18000bbe6  call    cs:__imp_WaitForSingleObjectEx
0x18000bbec  mov     [rbp+40h+var_98], eax
0x18000bbef  mov     [rbp+40h+var_90], r13
0x18000bbf3  mov     rbx, [r15+8]
0x18000bbf7  mov     r14, [r15+10h]
0x18000bbfb  cmp     rbx, r14
0x18000bbfe  jz      loc_18000BCDA
0x18000bc04  cmp     dword ptr [rbx+20h], 2
0x18000bc08  jg      loc_18000BF0B
0x18000bc0e  mov     eax, [rbx+20h]
0x18000bc11  cmp     qword ptr [rbx+18h], 7
0x18000bc16  jbe     short loc_18000BC90
0x18000bc18  mov     rdx, [rbx]; lpSubKey
0x18000bc1b  mov     rsi, [rsp+140h+hKey]
0x18000bc20  mov     dword ptr [rsp+140h+Data], eax
0x18000bc24  mov     [rsp+140h+var_F0], rdi
0x18000bc29  test    rdx, rdx
0x18000bc2c  jnz     short loc_18000BC95
0x18000bc2e  mov     rcx, rsi; hKey
0x18000bc31  mov     [rsp+140h+var_F0], rcx
0x18000bc36  mov     [rsp+140h+cbData], 4; cbData
0x18000bc3e  lea     rax, [rsp+140h+Data]
0x18000bc43  mov     [rsp+140h+lpData], rax; lpData
0x18000bc48  mov     r9d, 4; dwType
0x18000bc4e  xor     r8d, r8d; Reserved
0x18000bc51  lea     rdx, ValueName; "Operation"
0x18000bc58  call    cs:__imp_RegSetValueExW
0x18000bc5e  mov     edi, eax
0x18000bc60  mov     rcx, [rsp+140h+var_F0]; hKey
0x18000bc65  cmp     rcx, rsi
0x18000bc68  jz      short loc_18000BC70
0x18000bc6a  call    cs:__imp_RegCloseKey
0x18000bc70  test    edi, edi
0x18000bc72  jle     short loc_18000BC7F
0x18000bc74  movzx   edi, di
0x18000bc77  or      edi, 80070000h
0x18000bc7d  test    edi, edi
0x18000bc7f  js      loc_18000BF3B
0x18000bc85  add     rbx, 28h ; '('
0x18000bc89  xor     edi, edi
0x18000bc8b  jmp     loc_18000BBFB
0x18000bc90  mov     rdx, rbx
0x18000bc93  jmp     short loc_18000BC1B
0x18000bc95  cmp     word ptr [rdx], 0
0x18000bc99  jz      short loc_18000BC2E
0x18000bc9b  mov     [rsp+140h+lpdwDisposition], rdi; lpdwDisposition
0x18000bca0  lea     rax, [rsp+140h+var_F0]
0x18000bca5  mov     [rsp+140h+phkResult], rax; phkResult
0x18000bcaa  mov     [rsp+140h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000bcaf  mov     [rsp+140h+cbData], 2; samDesired
0x18000bcb7  mov     dword ptr [rsp+140h+lpData], edi; dwOptions
0x18000bcbb  xor     r9d, r9d; lpClass
0x18000bcbe  xor     r8d, r8d; Reserved
0x18000bcc1  mov     rcx, rsi; hKey
0x18000bcc4  call    cs:__imp_RegCreateKeyExW
0x18000bcca  mov     edi, eax
0x18000bccc  test    eax, eax
0x18000bcce  jnz     short loc_18000BC70
0x18000bcd0  mov     rcx, [rsp+140h+var_F0]
0x18000bcd5  jmp     loc_18000BC36
0x18000bcda  mov     rdx, [rsp+140h+hKey]
0x18000bcdf  lea     rcx, [rbp+40h+var_88]
0x18000bce3  call    ?GetSubkeys@PackageList@Storage@AppReadiness@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; AppReadiness::Storage::PackageList::GetSubkeys(HKEY__ *,ushort const *)
0x18000bce8  nop
0x18000bce9  mov     r12, [rbp+40h+var_88]
0x18000bced  mov     rsi, r12
0x18000bcf0  mov     r14, [rbp+40h+var_80]
0x18000bcf4  cmp     r12, r14
0x18000bcf7  jz      loc_18000BE17
0x18000bcfd  lea     r13, AppReadiness__Storage__MatchPackageFamilyName
0x18000bd04  cmp     qword ptr [rsi+18h], 7
0x18000bd09  jbe     loc_18000BEF4
0x18000bd0f  mov     rdx, [rsi]
0x18000bd12  xorps   xmm0, xmm0
0x18000bd15  movups  [rbp+40h+pExceptionObject], xmm0
0x18000bd19  xorps   xmm1, xmm1
0x18000bd1c  movdqu  [rbp+40h+var_60], xmm1
0x18000bd21  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000bd28  nop     dword ptr [rax+rax+00000000h]
0x18000bd30  inc     r8
0x18000bd33  cmp     word ptr [rdx+r8*2], 0
0x18000bd39  jnz     short loc_18000BD30
0x18000bd3b  lea     rcx, [rbp+40h+pExceptionObject]
0x18000bd3f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000bd44  nop
0x18000bd45  mov     [rsp+140h+var_D0], r13
0x18000bd4a  xorps   xmm0, xmm0
0x18000bd4d  movups  [rbp+40h+var_C0], xmm0
0x18000bd51  mov     [rbp+40h+var_B0], rdi
0x18000bd55  mov     [rbp+40h+var_A8], rdi
0x18000bd59  lea     rdx, [rbp+40h+pExceptionObject]
0x18000bd5d  cmp     qword ptr [rbp+40h+var_60+8], 7
0x18000bd62  cmova   rdx, qword ptr [rbp+40h+pExceptionObject]
0x18000bd67  mov     r8, qword ptr [rbp+40h+var_60]
0x18000bd6b  lea     rcx, [rbp+40h+var_C0]
0x18000bd6f  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18000bd74  lea     rax, [rsp+140h+var_D0]
0x18000bd79  mov     [rsp+140h+var_F0], rax
0x18000bd7e  mov     rdi, [r15+10h]
0x18000bd82  mov     rbx, [r15+8]
0x18000bd86  cmp     rbx, rdi
0x18000bd89  jz      short loc_18000BDAE
0x18000bd8b  nop     dword ptr [rax+rax+00h]
0x18000bd90  mov     rdx, rbx
0x18000bd93  lea     rcx, [rbp+40h+var_C0]
0x18000bd97  mov     rax, [rsp+140h+var_D0]
0x18000bd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bda1  test    al, al
0x18000bda3  jnz     short loc_18000BDAE
0x18000bda5  add     rbx, 28h ; '('
0x18000bda9  cmp     rbx, rdi
0x18000bdac  jnz     short loc_18000BD90
0x18000bdae  mov     rdx, [rbp+40h+var_A8]
0x18000bdb2  cmp     rdx, 7
0x18000bdb6  ja      loc_18000BF79
0x18000bdbc  xor     edi, edi
0x18000bdbe  mov     [rbp+40h+var_B0], rdi
0x18000bdc2  mov     [rbp+40h+var_A8], 7
0x18000bdca  mov     word ptr [rbp+40h+var_C0], di
0x18000bdce  cmp     rbx, [r15+10h]
0x18000bdd2  jz      loc_18000BEFC
0x18000bdd8  mov     ebx, [rbx+20h]
0x18000bddb  mov     rdx, qword ptr [rbp+40h+var_60+8]
0x18000bddf  cmp     rdx, 7
0x18000bde3  ja      loc_18000BF8F
0x18000bde9  test    ebx, ebx
0x18000bdeb  jnz     short loc_18000BE06
0x18000bded  cmp     qword ptr [rsi+18h], 7
0x18000bdf2  jbe     loc_18000BF03
0x18000bdf8  mov     rdx, [rsi]; lpSubKey
0x18000bdfb  mov     rcx, [rsp+140h+hKey]; hKey
0x18000be00  call    cs:__imp_RegDeleteTreeW
0x18000be06  add     rsi, 20h ; ' '
0x18000be0a  cmp     rsi, r14
0x18000be0d  jnz     loc_18000BD04
0x18000be13  mov     r13, [rbp+40h+var_A0]
0x18000be17  test    r12, r12
0x18000be1a  jz      short loc_18000BE81
0x18000be1c  mov     rbx, r12
0x18000be1f  cmp     r12, r14
0x18000be22  jz      short loc_18000BE56
0x18000be24  nop     dword ptr [rax+00h]
0x18000be28  nop     dword ptr [rax+rax+00000000h]
0x18000be30  mov     rdx, [rbx+18h]
0x18000be34  cmp     rdx, 7
0x18000be38  ja      loc_18000BFA5
0x18000be3e  mov     [rbx+10h], rdi
0x18000be42  mov     qword ptr [rbx+18h], 7
0x18000be4a  mov     [rbx], di
0x18000be4d  add     rbx, 20h ; ' '
0x18000be51  cmp     rbx, r14
0x18000be54  jnz     short loc_18000BE30
0x18000be56  mov     rdx, [rbp+40h+var_78]
0x18000be5a  sub     rdx, r12
0x18000be5d  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x18000be61  mov     qword ptr [rsp+140h+Data], rdx
0x18000be66  mov     [rsp+140h+var_F0], r12
0x18000be6b  cmp     rdx, 1000h
0x18000be72  jnb     loc_18000BFBA
0x18000be78  mov     rcx, r12; void *
0x18000be7b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000be80  nop
0x18000be81  test    r13, r13
0x18000be84  jz      short loc_18000BEA4
0x18000be86  test    [rbp+40h+var_98], 0FFFFFF7Fh
0x18000be8d  jnz     short loc_18000BEA4
0x18000be8f  xor     r8d, r8d; lpPreviousCount
0x18000be92  mov     edx, 1; lReleaseCount
0x18000be97  mov     rcx, r13; hSemaphore
0x18000be9a  call    cs:__imp_ReleaseSemaphore
0x18000bea0  test    eax, eax
0x18000bea2  jz      short loc_18000BF15
0x18000bea4  lea     rax, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x18000beab  mov     [rsp+140h+var_E0], rax
0x18000beb0  cmp     [rsp+140h+hKey], 0
0x18000beb6  jz      loc_18000BFD8
0x18000bebc  lea     rcx, [rsp+140h+var_E0]
0x18000bec1  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x18000bec6  test    al, al
0x18000bec8  jnz     loc_18000BFD8
0x18000bece  call    cs:__imp_GetLastError
0x18000bed4  test    eax, eax
0x18000bed6  jle     short loc_18000BEE0
0x18000bed8  movzx   eax, ax
0x18000bedb  or      eax, 80070000h
0x18000bee0  xor     r9d, r9d; lpArguments
0x18000bee3  xor     r8d, r8d; nNumberOfArguments
0x18000bee6  mov     edx, 1; dwExceptionFlags
0x18000beeb  mov     ecx, eax; dwExceptionCode
0x18000beed  call    cs:__imp_RaiseException
0x18000bef3  nop
0x18000bef4  mov     rdx, rsi
0x18000bef7  jmp     loc_18000BD12
0x18000befc  mov     ebx, edi
0x18000befe  jmp     loc_18000BDDB
0x18000bf03  mov     rdx, rsi
0x18000bf06  jmp     loc_18000BDFB
0x18000bf0b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "iter.second <= PackageOperation::MaxPersisted")
0x18000bf10  jmp     loc_18000BC0E
0x18000bf15  call    cs:__imp_GetLastError
0x18000bf1b  test    eax, eax
0x18000bf1d  jle     short loc_18000BF27
0x18000bf1f  movzx   eax, ax
0x18000bf22  or      eax, 80070000h
0x18000bf27  xor     r9d, r9d; lpArguments
0x18000bf2a  xor     r8d, r8d; nNumberOfArguments
0x18000bf2d  mov     edx, 1; dwExceptionFlags
0x18000bf32  mov     ecx, eax; dwExceptionCode
0x18000bf34  call    cs:__imp_RaiseException
0x18000bf3a  nop
0x18000bf3b  mov     [rsp+140h+cbData], 7Eh ; '~'; int
0x18000bf43  lea     rax, aOnecoreuapShel_10; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18000bf4a  mov     [rsp+140h+lpData], rax; char *
0x18000bf4f  lea     r9, aAppreadinessSt_5; "AppReadiness::Storage::WriteRegistryVal"...
0x18000bf56  lea     r8, aShregsetdwordR; "SHRegSetDWORD(root, subKey, valueName, "...
0x18000bf5d  mov     edx, edi; int
0x18000bf5f  lea     rcx, [rbp+40h+pExceptionObject]; this
0x18000bf63  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18000bf68  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18000bf6f  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18000bf73  call    _CxxThrowException_0
0x18000bf79  lea     rdx, ds:2[rdx*2]
0x18000bf81  mov     rcx, qword ptr [rbp+40h+var_C0]
0x18000bf85  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000bf8a  jmp     loc_18000BDBC
0x18000bf8f  lea     rdx, ds:2[rdx*2]
0x18000bf97  mov     rcx, qword ptr [rbp+40h+pExceptionObject]
0x18000bf9b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000bfa0  jmp     loc_18000BDE9
0x18000bfa5  lea     rdx, ds:2[rdx*2]
0x18000bfad  mov     rcx, [rbx]
0x18000bfb0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000bfb5  jmp     loc_18000BE3E
0x18000bfba  lea     rdx, [rsp+140h+Data]; unsigned __int64 *
0x18000bfbf  lea     rcx, [rsp+140h+var_F0]; void **
0x18000bfc4  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000bfc9  mov     r12, [rsp+140h+var_F0]
0x18000bfce  mov     rdx, qword ptr [rsp+140h+Data]
0x18000bfd3  jmp     loc_18000BE78
0x18000bfd8  mov     rcx, [rbp+40h+var_48]
0x18000bfdc  xor     rcx, rsp; StackCookie
0x18000bfdf  call    __security_check_cookie
0x18000bfe4  add     rsp, 108h
0x18000bfeb  pop     r15
0x18000bfed  pop     r14
0x18000bfef  pop     r13
0x18000bff1  pop     r12
0x18000bff3  pop     rdi
0x18000bff4  pop     rsi
0x18000bff5  pop     rbx
0x18000bff6  pop     rbp
0x18000bff7  retn
```
