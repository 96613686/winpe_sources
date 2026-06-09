# ReadRegMultiSZValue(HKEY__ *,ushort const *,ushort const *,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x140017c9c`
- end: `0x140017ea9`
- name: `?ReadRegMultiSZValue@@YAJPEAUHKEY__@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `525`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019054`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x140006750`
- `0x14000740c`
- `0x140017c9c`
- `0x14001873c`
- `0x14001a8aa`
- `0x14001a8d0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140017d08`
- `ADVAPI32!RegOpenKeyExW` at `0x140017d08`
- `ADVAPI32!RegCloseKey` at `0x140017e81`
- `ADVAPI32!RegCloseKey` at `0x140017e81`
- `ADVAPI32!RegQueryValueExW` at `0x140017d65`
- `ADVAPI32!RegQueryValueExW` at `0x140017de2`
- `ADVAPI32!RegQueryValueExW` at `0x140017d65`
- `ADVAPI32!RegQueryValueExW` at `0x140017de2`
- `KERNEL32!GetLastError` at `0x140017d25`
- `KERNEL32!GetLastError` at `0x140017d82`
- `KERNEL32!GetLastError` at `0x140017dff`
- `KERNEL32!GetLastError` at `0x140017d25`
- `KERNEL32!GetLastError` at `0x140017d82`
- `KERNEL32!GetLastError` at `0x140017dff`
- `msvcrt!free` at `0x140017e72`
- `msvcrt!free` at `0x140017e72`
- `msvcrt!malloc` at `0x140017d9d`
- `msvcrt!malloc` at `0x140017d9d`

## string_xrefs

- `0x140017d2e`: `RegOpenKeyExW for %1 failed with Status = %2!d!. GetLastError is 0x%3!x!`

## pseudocode

```c
__int64 __fastcall ReadRegMultiSZValue(__int64 a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  DWORD LastError; // eax
  LSTATUS v10; // eax
  unsigned int v11; // edi
  DWORD v12; // eax
  size_t v13; // rbx
  BYTE *v14; // rax
  BYTE *v15; // rdi
  LSTATUS v16; // eax
  unsigned int v17; // esi
  DWORD v18; // eax
  BYTE *i; // rsi
  __int64 v20; // rax
  __int64 v21; // rax
  DWORD cbData; // [rsp+30h] [rbp-40h] BYREF
  DWORD Type; // [rsp+34h] [rbp-3Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v26[4]; // [rsp+40h] [rbp-30h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 7;
  if ( a2 )
  {
    std::list<std::wstring>::clear(a4);
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x101u, &hKey);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      else
        v6 = v7;
      LastError = GetLastError();
      LogError(L"RegOpenKeyExW for %1 failed with Status = %2!d!. GetLastError is 0x%3!x!", a2, v8, LastError);
    }
    else
    {
      v10 = RegQueryValueExW(hKey, L"DownloadUrlList", 0, &Type, 0, &cbData);
      v11 = v10;
      if ( v10 )
      {
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        else
          v6 = v10;
        v12 = GetLastError();
        LogError(
          L"RegQueryValueEx for value %1 failed  with Status = %2!d!. GetLastError is 0x%3!x!",
          L"DownloadUrlList",
          v11,
          v12);
      }
      else
      {
        v13 = cbData;
        v14 = (BYTE *)malloc(cbData);
        v15 = v14;
        if ( v14 )
        {
          memset_0(v14, 0, v13);
          v16 = RegQueryValueExW(hKey, L"DownloadUrlList", 0, &Type, v15, &cbData);
          v17 = v16;
          if ( v16 )
          {
            if ( v16 > 0 )
              v6 = (unsigned __int16)v16 | 0x80070000;
            else
              v6 = v16;
            v18 = GetLastError();
            LogError(
              L"RegQueryValueEx for value %1 failed  with Status = %2!d!. GetLastError is 0x%3!x!",
              L"DownloadUrlList",
              v17,
              v18);
          }
          else
          {
            v6 = 0;
            for ( i = v15; *(_WORD *)i; i += 2 * v21 + 2 )
            {
              v20 = std::wstring::wstring((__int64)v26, (__int64)i);
              std::list<std::wstring>::push_back(a4, v20);
              std::wstring::_Tidy(v26, 1, 0);
              v21 = -1;
              do
                ++v21;
              while ( *(_WORD *)&i[2 * v21] );
            }
          }
          free(v15);
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x140017c9c  mov     [rsp-28h+arg_0], rbx
0x140017ca1  push    rbp
0x140017ca2  push    rsi
0x140017ca3  push    rdi
0x140017ca4  push    r14
0x140017ca6  push    r15
0x140017ca8  mov     rbp, rsp
0x140017cab  sub     rsp, 70h
0x140017caf  mov     rax, cs:__security_cookie
0x140017cb6  xor     rax, rsp
0x140017cb9  mov     [rbp+var_10], rax
0x140017cbd  mov     r14, r9
0x140017cc0  mov     rsi, rdx
0x140017cc3  xor     r15d, r15d
0x140017cc6  mov     [rbp+hKey], r15
0x140017cca  mov     [rbp+cbData], r15d
0x140017cce  mov     [rbp+Type], 7
0x140017cd5  test    rdx, rdx
0x140017cd8  jnz     short loc_140017CE4
0x140017cda  mov     ebx, 80070057h
0x140017cdf  jmp     loc_140017E87
0x140017ce4  mov     rcx, r14
0x140017ce7  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x140017cec  lea     rax, [rbp+hKey]
0x140017cf0  mov     [rsp+70h+phkResult], rax; phkResult
0x140017cf5  mov     r9d, 101h; samDesired
0x140017cfb  xor     r8d, r8d; ulOptions
0x140017cfe  mov     rdx, rsi; lpSubKey
0x140017d01  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140017d08  call    cs:__imp_RegOpenKeyExW
0x140017d0e  mov     edi, eax
0x140017d10  test    eax, eax
0x140017d12  jz      short loc_140017D45
0x140017d14  test    eax, eax
0x140017d16  jg      short loc_140017D1C
0x140017d18  mov     ebx, eax
0x140017d1a  jmp     short loc_140017D25
0x140017d1c  movzx   ebx, di
0x140017d1f  or      ebx, 80070000h
0x140017d25  call    cs:__imp_GetLastError
0x140017d2b  mov     rdx, rsi
0x140017d2e  lea     rcx, aRegopenkeyexwF_2; "RegOpenKeyExW for %1 failed with Status"...
0x140017d35  mov     r8d, edi
0x140017d38  mov     r9d, eax
0x140017d3b  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140017d40  jmp     loc_140017E78
0x140017d45  lea     rax, [rbp+cbData]
0x140017d49  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140017d4e  mov     [rsp+70h+phkResult], r15; lpData
0x140017d53  lea     r9, [rbp+Type]; lpType
0x140017d57  xor     r8d, r8d; lpReserved
0x140017d5a  lea     rdx, ValueName; "DownloadUrlList"
0x140017d61  mov     rcx, [rbp+hKey]; hKey
0x140017d65  call    cs:__imp_RegQueryValueExW
0x140017d6b  mov     edi, eax
0x140017d6d  test    eax, eax
0x140017d6f  jz      short loc_140017D98
0x140017d71  test    eax, eax
0x140017d73  jg      short loc_140017D79
0x140017d75  mov     ebx, eax
0x140017d77  jmp     short loc_140017D82
0x140017d79  movzx   ebx, di
0x140017d7c  or      ebx, 80070000h
0x140017d82  call    cs:__imp_GetLastError
0x140017d88  lea     rdx, ValueName; "DownloadUrlList"
0x140017d8f  lea     rcx, aRegqueryvaluee_0; "RegQueryValueEx for value %1 failed  wi"...
0x140017d96  jmp     short loc_140017D35
0x140017d98  mov     ebx, [rbp+cbData]
0x140017d9b  mov     ecx, ebx; Size
0x140017d9d  call    cs:__imp_malloc
0x140017da3  mov     rdi, rax
0x140017da6  test    rax, rax
0x140017da9  jnz     short loc_140017DB5
0x140017dab  mov     ebx, 8007000Eh
0x140017db0  jmp     loc_140017E78
0x140017db5  mov     r8, rbx; Size
0x140017db8  xor     edx, edx; Val
0x140017dba  mov     rcx, rdi; void *
0x140017dbd  call    memset_0
0x140017dc2  lea     rax, [rbp+cbData]
0x140017dc6  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140017dcb  mov     [rsp+70h+phkResult], rdi; lpData
0x140017dd0  lea     r9, [rbp+Type]; lpType
0x140017dd4  xor     r8d, r8d; lpReserved
0x140017dd7  lea     rdx, ValueName; "DownloadUrlList"
0x140017dde  mov     rcx, [rbp+hKey]; hKey
0x140017de2  call    cs:__imp_RegQueryValueExW
0x140017de8  mov     esi, eax
0x140017dea  test    eax, eax
0x140017dec  jz      short loc_140017E20
0x140017dee  test    eax, eax
0x140017df0  jg      short loc_140017DF6
0x140017df2  mov     ebx, eax
0x140017df4  jmp     short loc_140017DFF
0x140017df6  movzx   ebx, si
0x140017df9  or      ebx, 80070000h
0x140017dff  call    cs:__imp_GetLastError
0x140017e05  mov     r9d, eax
0x140017e08  mov     r8d, esi
0x140017e0b  lea     rdx, ValueName; "DownloadUrlList"
0x140017e12  lea     rcx, aRegqueryvaluee_0; "RegQueryValueEx for value %1 failed  wi"...
0x140017e19  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140017e1e  jmp     short loc_140017E6F
0x140017e20  mov     ebx, r15d
0x140017e23  mov     rsi, rdi
0x140017e26  cmp     r15w, [rdi]
0x140017e2a  jz      short loc_140017E6F
0x140017e2c  mov     rdx, rsi
0x140017e2f  lea     rcx, [rbp+var_30]
0x140017e33  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140017e38  nop
0x140017e39  mov     rdx, rax
0x140017e3c  mov     rcx, r14
0x140017e3f  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::list<std::wstring>::push_back(std::wstring &&)
0x140017e44  nop
0x140017e45  xor     r8d, r8d
0x140017e48  mov     dl, 1
0x140017e4a  lea     rcx, [rbp+var_30]
0x140017e4e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140017e53  or      rax, 0FFFFFFFFFFFFFFFFh
0x140017e57  inc     rax
0x140017e5a  cmp     [rsi+rax*2], r15w
0x140017e5f  jnz     short loc_140017E57
0x140017e61  lea     rsi, [rsi+rax*2]
0x140017e65  add     rsi, 2
0x140017e69  cmp     r15w, [rsi]
0x140017e6d  jnz     short loc_140017E2C
0x140017e6f  mov     rcx, rdi; Block
0x140017e72  call    cs:__imp_free
0x140017e78  mov     rcx, [rbp+hKey]; hKey
0x140017e7c  test    rcx, rcx
0x140017e7f  jz      short loc_140017E87
0x140017e81  call    cs:__imp_RegCloseKey
0x140017e87  mov     eax, ebx
0x140017e89  mov     rcx, [rbp+var_10]
0x140017e8d  xor     rcx, rsp; StackCookie
0x140017e90  call    __security_check_cookie
0x140017e95  mov     rbx, [rsp+70h+arg_0]
0x140017e9d  add     rsp, 70h
0x140017ea1  pop     r15
0x140017ea3  pop     r14
0x140017ea5  pop     rdi
0x140017ea6  pop     rsi
0x140017ea7  pop     rbp
0x140017ea8  retn
```
