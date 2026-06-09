# Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,ulong)

- ea: `0x1800218b0`
- end: `0x180021c95`
- name: `?SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z`
- size: `997`
- prototype: `__int64 __fastcall(HKEY, __int64, _QWORD *, __int64 *, DWORD)`
- caller_count: `14`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e290`
- `0x18001eb58`
- `0x180096a44`
- `0x1800d3b20`
- `0x180128fc0`
- `0x18012b8b4`
- `0x1801350ac`
- `0x18014cffc`
- `0x1801ce074`
- `0x1801e02b4`
- `0x1801f035c`
- `0x180250a38`
- `0x18027afc0`
- `0x1803236d0`

## callees

- `0x180020db8`
- `0x1800218b0`
- `0x180021c9c`
- `0x180022570`
- `0x1800225a0`
- `0x18002be90`
- `0x18002df00`
- `0x180064e8c`
- `0x18010f8f4`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180021b1d`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180021b1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021b37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021ae7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021bfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021c52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021ae7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021bfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021c52`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800219ae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800219ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021a8a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021a8a`

## string_xrefs

- `0x180021b5d`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180021bba`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180021c12`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::Utils::Registry::SetString(
        HKEY a1,
        __int64 a2,
        _QWORD *a3,
        __int64 *a4,
        DWORD a5)
{
  HKEY v8; // rsi
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  unsigned int v11; // ebx
  HKEY v12; // rbx
  __int64 v13; // rsi
  const WCHAR *v14; // rdx
  int v15; // eax
  unsigned int v16; // ebx
  DWORD LastError; // ebx
  int dwOptions; // [rsp+20h] [rbp-F8h]
  int dwOptionsa; // [rsp+20h] [rbp-F8h]
  int dwOptionsb; // [rsp+20h] [rbp-F8h]
  char *v22; // [rsp+50h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-B0h] BYREF
  BYTE *lpData[2]; // [rsp+70h] [rbp-A8h] BYREF
  _QWORD v26[5]; // [rsp+80h] [rbp-98h] BYREF
  char v27; // [rsp+A8h] [rbp-70h]
  LPCWSTR lpSubKey[4]; // [rsp+B0h] [rbp-68h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+D0h] [rbp-48h] BYREF
  __int128 v30; // [rsp+E0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  hKey = a1;
  LODWORD(v22) = 0;
  phkResult = 0;
  v26[0] = &hKey;
  v26[1] = a2;
  v26[2] = a3;
  v26[3] = a4;
  v26[4] = &v22;
  v27 = 1;
  *(_OWORD *)lpData = *(_OWORD *)a2;
  Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName((LPCWSTR)lpSubKey);
  if ( *(_QWORD *)(a2 + 8) )
  {
    v8 = phkResult;
    if ( phkResult )
    {
      LastError = GetLastError();
      RegCloseKey(v8);
      SetLastError(LastError);
    }
    phkResult = 0;
    v9 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v9 = lpSubKey[0];
    v10 = RegCreateKeyExW(hKey, v9, 0, 0, a5, 2u, 0, &phkResult, 0);
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    LODWORD(v22) = v11;
    if ( (v11 & 0x80000000) == 0 )
    {
      v12 = phkResult;
      goto LABEL_10;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
      (const char *)v11,
      dwOptionsa);
    std::wstring::_Tidy_deallocate(lpSubKey);
    v27 = 0;
    `Microsoft::Diagnostics::Utils::Registry::SetString'::`2'::_lambda_1_::operator()(v26);
    if ( phkResult )
      RegCloseKey(phkResult);
    return v11;
  }
  else
  {
    v12 = hKey;
    if ( hKey )
    {
LABEL_10:
      v13 = *a4;
      gsl::details::extent_type<-1>::extent_type<-1>(lpData, a4[1]);
      if ( lpData[0] != (BYTE *)-1LL )
      {
        if ( v13 )
        {
          if ( lpData[0] < (BYTE *)0x7FFFFFFFFFFFFFFFLL )
          {
LABEL_13:
            gsl::span<enum gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(
              lpData,
              v13,
              2 * (__int64)lpData[0]);
            *(_OWORD *)lpValueName = 0;
            v30 = 0;
            std::wstring::_Construct<1,wchar_t *>(lpValueName, *a3, a3[1]);
            v14 = (const WCHAR *)lpValueName;
            if ( *((_QWORD *)&v30 + 1) > 7u )
              v14 = lpValueName[0];
            v15 = RegSetValueExW(v12, v14, 0, 1u, lpData[1], (DWORD)lpData[0]);
            if ( v15 > 0 )
              v15 = (unsigned __int16)v15 | 0x80070000;
            LODWORD(v22) = v15;
            std::wstring::_Tidy_deallocate(lpValueName);
            v16 = (unsigned int)v22;
            if ( (int)v22 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x106,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
                (const char *)(unsigned int)v22,
                dwOptionsb);
              std::wstring::_Tidy_deallocate(lpSubKey);
              v27 = 0;
              `Microsoft::Diagnostics::Utils::Registry::SetString'::`2'::_lambda_1_::operator()(v26);
              if ( phkResult )
                RegCloseKey(phkResult);
              return v16;
            }
            else
            {
              std::wstring::_Tidy_deallocate(lpSubKey);
              v27 = 0;
              `Microsoft::Diagnostics::Utils::Registry::SetString'::`2'::_lambda_1_::operator()(v26);
              if ( phkResult )
                RegCloseKey(phkResult);
              return 0;
            }
          }
        }
        else if ( !lpData[0] )
        {
          goto LABEL_13;
        }
      }
      _o_terminate();
      __debugbreak();
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
      (const char *)0x80070057LL,
      dwOptions);
    std::wstring::_Tidy_deallocate(lpSubKey);
    v27 = 0;
    `Microsoft::Diagnostics::Utils::Registry::SetString'::`2'::_lambda_1_::operator()(v26);
    if ( phkResult )
      RegCloseKey(phkResult);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800218b0  mov     r11, rsp
0x1800218b3  mov     [r11+20h], rbx
0x1800218b7  push    rsi
0x1800218b8  push    r14
0x1800218ba  push    r15
0x1800218bc  sub     rsp, 100h
0x1800218c3  mov     rax, cs:__security_cookie
0x1800218ca  xor     rax, rsp
0x1800218cd  mov     [rsp+118h+var_28], rax
0x1800218d5  mov     r14, r9
0x1800218d8  mov     r15, r8
0x1800218db  mov     rbx, rdx
0x1800218de  mov     [rsp+118h+hKey], rcx
0x1800218e3  mov     dword ptr [rsp+118h+var_C8], 0
0x1800218eb  mov     [rsp+118h+var_C0], 0
0x1800218f4  lea     rax, [rsp+118h+hKey]
0x1800218f9  mov     [r11-98h], rax
0x180021900  mov     [r11-90h], rdx
0x180021907  mov     [r11-88h], r8
0x18002190e  mov     [r11-80h], r9
0x180021912  lea     rax, [rsp+118h+var_C8]
0x180021917  mov     [r11-78h], rax
0x18002191b  mov     byte ptr [r11-70h], 1
0x180021920  movups  xmm0, xmmword ptr [rdx]
0x180021923  movdqu  xmmword ptr [rsp+118h+lpData], xmm0
0x180021929  lea     rdx, [rsp+118h+lpData]
0x18002192e  lea     rcx, [r11-68h]
0x180021932  call    ?TryExpandKeyName@Registry@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName(std::wstring_view)
0x180021937  nop
0x180021938  cmp     qword ptr [rbx+8], 0
0x18002193d  jz      loc_180021B42
0x180021943  mov     rsi, [rsp+118h+var_C0]
0x180021948  test    rsi, rsi
0x18002194b  jnz     loc_180021B24
0x180021951  mov     [rsp+118h+var_C0], 0
0x18002195a  lea     rdx, [rsp+118h+lpSubKey]
0x180021962  cmp     [rsp+118h+var_50], 7
0x18002196b  cmova   rdx, [rsp+118h+lpSubKey]; lpSubKey
0x180021974  mov     [rsp+118h+lpdwDisposition], 0; lpdwDisposition
0x18002197d  lea     rax, [rsp+118h+var_C0]
0x180021982  mov     [rsp+118h+phkResult], rax; phkResult
0x180021987  mov     [rsp+118h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180021990  mov     [rsp+118h+samDesired], 2; samDesired
0x180021998  mov     eax, [rsp+118h+arg_20]
0x18002199f  mov     [rsp+118h+dwOptions], eax; int
0x1800219a3  xor     r9d, r9d; lpClass
0x1800219a6  xor     r8d, r8d; Reserved
0x1800219a9  mov     rcx, [rsp+118h+hKey]; hKey
0x1800219ae  call    cs:__imp_RegCreateKeyExW
0x1800219b4  mov     ebx, eax
0x1800219b6  test    eax, eax
0x1800219b8  jle     short loc_1800219C3
0x1800219ba  movzx   ebx, ax
0x1800219bd  or      ebx, 80070000h
0x1800219c3  mov     dword ptr [rsp+118h+var_C8], ebx
0x1800219c7  test    ebx, ebx
0x1800219c9  js      loc_180021B52
0x1800219cf  mov     rbx, [rsp+118h+var_C0]
0x1800219d4  mov     rsi, [r14]
0x1800219d7  mov     rdx, [r14+8]
0x1800219db  lea     rcx, [rsp+118h+lpData]
0x1800219e0  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x1800219e5  mov     r8, [rsp+118h+lpData]
0x1800219ea  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800219ee  jz      loc_180021B1D
0x1800219f4  test    rsi, rsi
0x1800219f7  jz      loc_180021B14
0x1800219fd  mov     rax, 7FFFFFFFFFFFFFFFh
0x180021a07  cmp     r8, rax
0x180021a0a  jnb     loc_180021B1D
0x180021a10  add     r8, r8
0x180021a13  mov     rdx, rsi
0x180021a16  lea     rcx, [rsp+118h+lpData]
0x180021a1b  call    ??$?0_K@?$storage_type@V?$extent_type@$0?0@details@gsl@@@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEAA@PEBW4byte@2@_K@Z; gsl::span<gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(gsl::byte const *,unsigned __int64)
0x180021a20  xorps   xmm0, xmm0
0x180021a23  movups  xmmword ptr [rsp+118h+lpValueName], xmm0
0x180021a2b  xorps   xmm1, xmm1
0x180021a2e  movdqu  [rsp+118h+var_38], xmm1
0x180021a37  mov     r8, [r15+8]
0x180021a3b  mov     rdx, [r15]
0x180021a3e  lea     rcx, [rsp+118h+lpValueName]
0x180021a46  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180021a4b  lea     rdx, [rsp+118h+lpValueName]
0x180021a53  cmp     qword ptr [rsp+118h+var_38+8], 7
0x180021a5c  setnbe  al
0x180021a5f  mov     r8d, dword ptr [rsp+118h+lpData]
0x180021a64  mov     r10, [rsp+118h+lpData+8]
0x180021a69  test    al, al
0x180021a6b  cmovnz  rdx, [rsp+118h+lpValueName]; lpValueName
0x180021a74  mov     [rsp+118h+samDesired], r8d; cbData
0x180021a79  mov     qword ptr [rsp+118h+dwOptions], r10; int
0x180021a7e  mov     r9d, 1; dwType
0x180021a84  xor     r8d, r8d; Reserved
0x180021a87  mov     rcx, rbx; hKey
0x180021a8a  call    cs:__imp_RegSetValueExW
0x180021a90  test    eax, eax
0x180021a92  jle     short loc_180021A9C
0x180021a94  movzx   eax, ax
0x180021a97  or      eax, 80070000h
0x180021a9c  mov     dword ptr [rsp+118h+var_C8], eax
0x180021aa0  lea     rcx, [rsp+118h+lpValueName]
0x180021aa8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021aad  mov     ebx, dword ptr [rsp+118h+var_C8]
0x180021ab1  test    ebx, ebx
0x180021ab3  js      loc_180021C07
0x180021ab9  lea     rcx, [rsp+118h+lpSubKey]
0x180021ac1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021ac6  nop
0x180021ac7  mov     [rsp+118h+var_70], 0
0x180021acf  lea     rcx, [rsp+118h+var_98]
0x180021ad7  call    ??R_lambda_1_@?1??SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring_view,ulong)'::`2'::_lambda_1_::operator()(void)
0x180021adc  nop
0x180021add  mov     rcx, [rsp+118h+var_C0]; hKey
0x180021ae2  test    rcx, rcx
0x180021ae5  jz      short loc_180021AED
0x180021ae7  call    cs:__imp_RegCloseKey
0x180021aed  xor     eax, eax
0x180021aef  mov     rcx, [rsp+118h+var_28]
0x180021af7  xor     rcx, rsp; StackCookie
0x180021afa  call    __security_check_cookie
0x180021aff  mov     rbx, [rsp+118h+arg_18]
0x180021b07  add     rsp, 100h
0x180021b0e  pop     r15
0x180021b10  pop     r14
0x180021b12  pop     rsi
0x180021b13  retn
0x180021b14  test    r8, r8
0x180021b17  jz      loc_180021A10
0x180021b1d  call    cs:__imp__o_terminate
0x180021b23  int     3; Trap to Debugger
0x180021b24  call    cs:__imp_GetLastError
0x180021b2a  mov     ebx, eax
0x180021b2c  mov     rcx, rsi; hKey
0x180021b2f  call    cs:__imp_RegCloseKey
0x180021b35  mov     ecx, ebx; dwErrCode
0x180021b37  call    cs:__imp_SetLastError
0x180021b3d  jmp     loc_180021951
0x180021b42  mov     rbx, [rsp+118h+hKey]
0x180021b47  test    rbx, rbx
0x180021b4a  jnz     loc_1800219D4
0x180021b50  jmp     short loc_180021BAA
0x180021b52  mov     rcx, [rsp+118h]; this
0x180021b5a  mov     r9d, ebx; char *
0x180021b5d  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x180021b64  mov     edx, 0F5h; void *
0x180021b69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021b6e  nop
0x180021b6f  lea     rcx, [rsp+118h+lpSubKey]
0x180021b77  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021b7c  nop
0x180021b7d  mov     [rsp+118h+var_70], 0
0x180021b85  lea     rcx, [rsp+118h+var_98]
0x180021b8d  call    ??R_lambda_1_@?1??SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring_view,ulong)'::`2'::_lambda_1_::operator()(void)
0x180021b92  nop
0x180021b93  mov     rcx, [rsp+118h+var_C0]; hKey
0x180021b98  test    rcx, rcx
0x180021b9b  jz      short loc_180021BA3
0x180021b9d  call    cs:__imp_RegCloseKey
0x180021ba3  mov     eax, ebx
0x180021ba5  jmp     loc_180021AEF
0x180021baa  mov     rcx, [rsp+118h]; this
0x180021bb2  mov     ebx, 80070057h
0x180021bb7  mov     r9d, ebx; char *
0x180021bba  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x180021bc1  mov     edx, 0FBh; void *
0x180021bc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021bcb  nop
0x180021bcc  lea     rcx, [rsp+118h+lpSubKey]
0x180021bd4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021bd9  nop
0x180021bda  mov     [rsp+118h+var_70], 0
0x180021be2  lea     rcx, [rsp+118h+var_98]
0x180021bea  call    ??R_lambda_1_@?1??SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring_view,ulong)'::`2'::_lambda_1_::operator()(void)
0x180021bef  nop
0x180021bf0  mov     rcx, [rsp+118h+var_C0]; hKey
0x180021bf5  test    rcx, rcx
0x180021bf8  jz      short loc_180021C00
0x180021bfa  call    cs:__imp_RegCloseKey
0x180021c00  mov     eax, ebx
0x180021c02  jmp     loc_180021AEF
0x180021c07  mov     rcx, [rsp+118h]; this
0x180021c0f  mov     r9d, ebx; char *
0x180021c12  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x180021c19  mov     edx, 106h; void *
0x180021c1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021c23  nop
0x180021c24  lea     rcx, [rsp+118h+lpSubKey]
0x180021c2c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021c31  nop
0x180021c32  mov     [rsp+118h+var_70], 0
0x180021c3a  lea     rcx, [rsp+118h+var_98]
0x180021c42  call    ??R_lambda_1_@?1??SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring_view,ulong)'::`2'::_lambda_1_::operator()(void)
0x180021c47  nop
0x180021c48  mov     rcx, [rsp+118h+var_C0]; hKey
0x180021c4d  test    rcx, rcx
0x180021c50  jz      short loc_180021C58
0x180021c52  call    cs:__imp_RegCloseKey
0x180021c58  mov     eax, ebx
0x180021c5a  jmp     loc_180021AEF
0x180021c5f  mov     [rsp+118h+var_70], 0
0x180021c67  lea     rcx, [rsp+118h+var_98]
0x180021c6f  call    ??R_lambda_1_@?1??SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring_view,ulong)'::`2'::_lambda_1_::operator()(void)
0x180021c74  nop
0x180021c75  lea     rcx, [rsp+118h+var_C0]
0x180021c7a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180021c7f  mov     eax, [rsp+118h+var_B8]
0x180021c83  jmp     loc_180021AEF
0x180021c88  cmp     [rsp+118h+var_70], 0
0x180021c90  jnz     short loc_180021C5F
0x180021c92  jmp     short loc_180021C75
```
