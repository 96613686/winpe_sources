# FindSessionIDFromUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong &)

- ea: `0x140015b7c`
- end: `0x140015e33`
- name: `?FindSessionIDFromUserSid@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z`
- size: `695`
- prototype: `__int64 __fastcall(wchar_t *String2, DWORD *)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14000a39c`
- `0x140010a2c`
- `0x1400165f8`
- `0x1400168b4`

## callees

- `0x140003674`
- `0x140006480`
- `0x140006604`
- `0x1400068c8`
- `0x14000740c`
- `0x14000775c`
- `0x140011d58`
- `0x140015b7c`
- `0x140016a88`
- `0x14001817c`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140015bf8`
- `KERNEL32!GetLastError` at `0x140015dc2`
- `KERNEL32!GetLastError` at `0x140015bf8`
- `KERNEL32!GetLastError` at `0x140015dc2`
- `msvcrt!_wcsnicmp` at `0x140015d4d`
- `msvcrt!_wcsnicmp` at `0x140015d4d`
- `WTSAPI32!WTSFreeMemoryExW` at `0x140015db8`
- `WTSAPI32!WTSFreeMemoryExW` at `0x140015db8`
- `WTSAPI32!WTSEnumerateSessionsExW` at `0x140015bee`
- `WTSAPI32!WTSEnumerateSessionsExW` at `0x140015bee`

## string_xrefs

- `0x140015c27`: `FindSessionIDFromUserSid - No sessions are active`
- `0x140015d03`: `FindSessionIDFromUserSid - GetStringSIDFromUsername() failed with hr = 0x%1!x!.`
- `0x140015de1`: `FindSessionIDFromUserSid() failed hr=0x%1!x!`

## pseudocode

```c
__int64 __fastcall FindSessionIDFromUserSid(wchar_t *String2, DWORD *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  DWORD i; // edi
  __int64 v7; // rsi
  const unsigned __int16 *pDomainName; // rcx
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  const WCHAR *v11; // rax
  int StringSIDFromUsername; // eax
  wchar_t **v13; // rcx
  __int64 v14; // rax
  const wchar_t *v15; // rdx
  const wchar_t *v16; // rcx
  DWORD v17; // eax
  DWORD NumberOfEntries; // [rsp+30h] [rbp-89h] BYREF
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+38h] [rbp-81h] BYREF
  DWORD pLevel; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp-69h] BYREF
  wchar_t *v24; // [rsp+70h] [rbp-49h]
  wchar_t *String1[3]; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int64 v26; // [rsp+90h] [rbp-29h]
  _QWORD v27[4]; // [rsp+98h] [rbp-21h] BYREF
  _QWORD v28[4]; // [rsp+B8h] [rbp-1h] BYREF

  v24 = String2;
  pLevel = 1;
  ppSessionInfo = 0;
  NumberOfEntries = 0;
  v28[3] = 7;
  v28[2] = 0;
  LOWORD(v28[0]) = 0;
  if ( WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &NumberOfEntries) )
  {
    if ( NumberOfEntries )
    {
      v5 = 0;
      for ( i = 0; i < NumberOfEntries; ++i )
      {
        v26 = 7;
        String1[2] = 0;
        LOWORD(String1[0]) = 0;
        v7 = i;
        if ( ppSessionInfo[v7].pUserName )
        {
          v27[3] = 7;
          v27[2] = 0;
          LOWORD(v27[0]) = 0;
          v22 = 0;
          pDomainName = ppSessionInfo[v7].pDomainName;
          if ( pDomainName && (int)StringCchLengthW(pDomainName, 0xFFu, &v22) >= 0 && v22 )
          {
            v9 = std::char_traits<unsigned short>::length(ppSessionInfo[v7].pDomainName);
            std::wstring::assign(v27, v10, v9);
            std::wstring::append((__int64)v27, (__int64)L"\\");
          }
          std::wstring::append((__int64)v27, (__int64)ppSessionInfo[v7].pUserName);
          v11 = (const WCHAR *)std::wstring::wstring((__int64)v23, (__int64)v27);
          StringSIDFromUsername = GetStringSIDFromUsername(v11);
          if ( StringSIDFromUsername >= 0 )
          {
            v13 = String1;
            if ( v26 >= 8 )
              v13 = (wchar_t **)String1[0];
            v14 = -1;
            do
              ++v14;
            while ( *((_WORD *)v13 + v14) );
            if ( *((_QWORD *)String2 + 3) < 8u )
              v15 = String2;
            else
              v15 = *(const wchar_t **)String2;
            v16 = (const wchar_t *)String1;
            if ( v26 >= 8 )
              v16 = String1[0];
            if ( !_wcsnicmp(v16, v15, (unsigned int)v14) )
            {
              *a2 = ppSessionInfo[v7].SessionId;
              std::wstring::_Tidy(v27, 1, 0);
              std::wstring::_Tidy(String1, 1, 0);
              break;
            }
          }
          else
          {
            LogWarn(
              L"FindSessionIDFromUserSid - GetStringSIDFromUsername() failed with hr = 0x%1!x!.",
              (unsigned int)StringSIDFromUsername);
          }
          std::wstring::_Tidy(v27, 1, 0);
        }
        std::wstring::_Tidy(String1, 1, 0);
      }
    }
    else
    {
      LogError(L"FindSessionIDFromUserSid - No sessions are active");
      v5 = -2147418113;
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    LogError(L"::WTSEnumerateSessionsEx failed with error: 0x%1!x!", v5);
  }
  if ( ppSessionInfo )
  {
    if ( !WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, ppSessionInfo, NumberOfEntries) )
    {
      v17 = GetLastError();
      LogError(L"Failed to free memory : 0x%1!x!", v17);
    }
    ppSessionInfo = 0;
  }
  if ( (v5 & 0x80000000) != 0 )
    LogError(L"FindSessionIDFromUserSid() failed hr=0x%1!x!", v5);
  std::wstring::_Tidy(v28, 1, 0);
  std::wstring::_Tidy(String2, 1, 0);
  return v5;
}

```

## disassembly

```asm
0x140015b7c  mov     [rsp-8+arg_10], rbx
0x140015b81  push    rbp
0x140015b82  push    rsi
0x140015b83  push    rdi
0x140015b84  push    r12
0x140015b86  push    r13
0x140015b88  push    r14
0x140015b8a  push    r15
0x140015b8c  lea     rbp, [rsp-27h]
0x140015b91  sub     rsp, 0E0h
0x140015b98  mov     rax, cs:__security_cookie
0x140015b9f  xor     rax, rsp
0x140015ba2  mov     [rbp+57h+var_38], rax
0x140015ba6  mov     r15, rdx
0x140015ba9  mov     r14, rcx
0x140015bac  mov     [rbp+57h+var_A0], rcx
0x140015bb0  mov     [rbp+57h+pLevel], 1
0x140015bb7  xor     r12d, r12d
0x140015bba  mov     [rsp+110h+ppSessionInfo], r12
0x140015bbf  mov     [rsp+110h+NumberOfEntries], r12d
0x140015bc4  lea     r13d, [r12+7]
0x140015bc9  mov     [rbp+57h+var_40], r13
0x140015bcd  mov     [rbp+57h+var_48], r12
0x140015bd1  mov     [rbp+57h+var_58], r12w
0x140015bd6  lea     rax, [rsp+110h+NumberOfEntries]
0x140015bdb  mov     [rsp+110h+pCount], rax; pCount
0x140015be0  lea     r9, [rsp+110h+ppSessionInfo]; ppSessionInfo
0x140015be5  xor     r8d, r8d; Filter
0x140015be8  lea     rdx, [rbp+57h+pLevel]; pLevel
0x140015bec  xor     ecx, ecx; hServer
0x140015bee  call    cs:__imp_WTSEnumerateSessionsExW
0x140015bf4  test    eax, eax
0x140015bf6  jnz     short loc_140015C20
0x140015bf8  call    cs:__imp_GetLastError
0x140015bfe  mov     ebx, eax
0x140015c00  test    eax, eax
0x140015c02  jle     short loc_140015C0D
0x140015c04  movzx   ebx, ax
0x140015c07  or      ebx, 80070000h
0x140015c0d  mov     edx, ebx
0x140015c0f  lea     rcx, aWtsenumeratese; "::WTSEnumerateSessionsEx failed with er"...
0x140015c16  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140015c1b  jmp     loc_140015DA4
0x140015c20  cmp     [rsp+110h+NumberOfEntries], r12d
0x140015c25  jnz     short loc_140015C3D
0x140015c27  lea     rcx, aFindsessionidf_0; "FindSessionIDFromUserSid - No sessions "...
0x140015c2e  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140015c33  mov     ebx, 8000FFFFh
0x140015c38  jmp     loc_140015DA4
0x140015c3d  mov     ebx, r12d
0x140015c40  mov     edi, r12d
0x140015c43  cmp     edi, [rsp+110h+NumberOfEntries]
0x140015c47  jnb     loc_140015DA4
0x140015c4d  mov     [rbp+57h+var_80], r13
0x140015c51  mov     [rbp+57h+var_88], r12
0x140015c55  mov     word ptr [rbp+57h+String1], r12w
0x140015c5a  mov     eax, edi
0x140015c5c  imul    rsi, rax, 38h ; '8'
0x140015c60  mov     rcx, [rsp+110h+ppSessionInfo]
0x140015c65  cmp     [rsi+rcx+20h], r12
0x140015c6a  jz      loc_140015D66
0x140015c70  mov     [rbp+57h+var_60], r13
0x140015c74  mov     [rbp+57h+var_68], r12
0x140015c78  mov     [rbp+57h+var_78], r12w
0x140015c7d  mov     [rbp+57h+var_C8], r12
0x140015c81  mov     rcx, [rsi+rcx+28h]; unsigned __int16 *
0x140015c86  test    rcx, rcx
0x140015c89  jz      short loc_140015CD1
0x140015c8b  lea     r8, [rbp+57h+var_C8]; unsigned __int64 *
0x140015c8f  mov     edx, 0FFh; unsigned __int64
0x140015c94  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140015c99  test    eax, eax
0x140015c9b  js      short loc_140015CD1
0x140015c9d  cmp     [rbp+57h+var_C8], r12
0x140015ca1  jbe     short loc_140015CD1
0x140015ca3  mov     rax, [rsp+110h+ppSessionInfo]
0x140015ca8  mov     rcx, [rsi+rax+28h]
0x140015cad  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140015cb2  mov     r8, rax
0x140015cb5  mov     rdx, rcx
0x140015cb8  lea     rcx, [rbp+57h+var_78]
0x140015cbc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140015cc1  lea     rdx, asc_140020C3C; "\\"
0x140015cc8  lea     rcx, [rbp+57h+var_78]
0x140015ccc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x140015cd1  mov     rdx, [rsp+110h+ppSessionInfo]
0x140015cd6  mov     rdx, [rsi+rdx+20h]
0x140015cdb  lea     rcx, [rbp+57h+var_78]
0x140015cdf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x140015ce4  lea     rdx, [rbp+57h+var_78]
0x140015ce8  lea     rcx, [rbp+57h+var_C0]
0x140015cec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140015cf1  lea     rdx, [rbp+57h+String1]
0x140015cf5  mov     rcx, rax; lpAccountName
0x140015cf8  call    ?GetStringSIDFromUsername@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetStringSIDFromUsername(std::wstring,std::wstring &)
0x140015cfd  test    eax, eax
0x140015cff  jns     short loc_140015D11
0x140015d01  mov     edx, eax
0x140015d03  lea     rcx, aFindsessionidf_1; "FindSessionIDFromUserSid - GetStringSID"...
0x140015d0a  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x140015d0f  jmp     short loc_140015D57
0x140015d11  lea     rcx, [rbp+57h+String1]
0x140015d15  cmp     [rbp+57h+var_80], 8
0x140015d1a  cmovnb  rcx, [rbp+57h+String1]
0x140015d1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140015d23  inc     rax
0x140015d26  cmp     [rcx+rax*2], r12w
0x140015d2b  jnz     short loc_140015D23
0x140015d2d  cmp     qword ptr [r14+18h], 8
0x140015d32  jb      short loc_140015D39
0x140015d34  mov     rdx, [r14]
0x140015d37  jmp     short loc_140015D3C
0x140015d39  mov     rdx, r14; String2
0x140015d3c  lea     rcx, [rbp+57h+String1]
0x140015d40  cmp     [rbp+57h+var_80], 8
0x140015d45  cmovnb  rcx, [rbp+57h+String1]; String1
0x140015d4a  mov     r8d, eax; MaxCount
0x140015d4d  call    cs:__imp__wcsnicmp
0x140015d53  test    eax, eax
0x140015d55  jz      short loc_140015D7B
0x140015d57  xor     r8d, r8d
0x140015d5a  mov     dl, 1
0x140015d5c  lea     rcx, [rbp+57h+var_78]
0x140015d60  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140015d65  nop
0x140015d66  xor     r8d, r8d
0x140015d69  mov     dl, 1
0x140015d6b  lea     rcx, [rbp+57h+String1]
0x140015d6f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140015d74  inc     edi
0x140015d76  jmp     loc_140015C43
0x140015d7b  mov     rax, [rsp+110h+ppSessionInfo]
0x140015d80  mov     ecx, [rsi+rax+8]
0x140015d84  mov     [r15], ecx
0x140015d87  xor     r8d, r8d
0x140015d8a  mov     dl, 1
0x140015d8c  lea     rcx, [rbp+57h+var_78]
0x140015d90  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140015d95  nop
0x140015d96  xor     r8d, r8d
0x140015d99  mov     dl, 1
0x140015d9b  lea     rcx, [rbp+57h+String1]
0x140015d9f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140015da4  mov     rdx, [rsp+110h+ppSessionInfo]; pMemory
0x140015da9  test    rdx, rdx
0x140015dac  jz      short loc_140015DDB
0x140015dae  mov     r8d, [rsp+110h+NumberOfEntries]; NumberOfEntries
0x140015db3  mov     ecx, 2; WTSTypeClass
0x140015db8  call    cs:__imp_WTSFreeMemoryExW
0x140015dbe  test    eax, eax
0x140015dc0  jnz     short loc_140015DD6
0x140015dc2  call    cs:__imp_GetLastError
0x140015dc8  mov     edx, eax
0x140015dca  lea     rcx, aFailedToFreeMe; "Failed to free memory : 0x%1!x!"
0x140015dd1  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140015dd6  mov     [rsp+110h+ppSessionInfo], r12
0x140015ddb  test    ebx, ebx
0x140015ddd  jns     short loc_140015DEE
0x140015ddf  mov     edx, ebx
0x140015de1  lea     rcx, aFindsessionidf; "FindSessionIDFromUserSid() failed hr=0x"...
0x140015de8  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140015ded  nop
0x140015dee  xor     r8d, r8d
0x140015df1  mov     dl, 1
0x140015df3  lea     rcx, [rbp+57h+var_58]
0x140015df7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140015dfc  nop
0x140015dfd  xor     r8d, r8d
0x140015e00  mov     dl, 1
0x140015e02  mov     rcx, r14
0x140015e05  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140015e0a  mov     eax, ebx
0x140015e0c  mov     rcx, [rbp+57h+var_38]
0x140015e10  xor     rcx, rsp; StackCookie
0x140015e13  call    __security_check_cookie
0x140015e18  mov     rbx, [rsp+110h+arg_10]
0x140015e20  add     rsp, 0E0h
0x140015e27  pop     r15
0x140015e29  pop     r14
0x140015e2b  pop     r13
0x140015e2d  pop     r12
0x140015e2f  pop     rdi
0x140015e30  pop     rsi
0x140015e31  pop     rbp
0x140015e32  retn
```
