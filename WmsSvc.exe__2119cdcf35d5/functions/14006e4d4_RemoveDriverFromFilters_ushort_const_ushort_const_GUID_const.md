# RemoveDriverFromFilters(ushort const *,ushort const *,_GUID const *)

- ea: `0x14006e4d4`
- end: `0x14006e6c9`
- name: `?RemoveDriverFromFilters@@YAJPEBG0PEBU_GUID@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(wchar_t *String2, HKEY lpValueName, GUID *ClassGuid)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14006e81c`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140062418`
- `0x14006e4d4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14006e6b2`
- `ADVAPI32!RegCloseKey` at `0x14006e6b2`
- `KERNEL32!GetLastError` at `0x14006e5e4`
- `KERNEL32!GetLastError` at `0x14006e5e4`
- `KERNEL32!IsDebuggerPresent` at `0x14006e538`
- `KERNEL32!IsDebuggerPresent` at `0x14006e63f`
- `KERNEL32!IsDebuggerPresent` at `0x14006e538`
- `KERNEL32!IsDebuggerPresent` at `0x14006e63f`
- `SETUPAPI!SetupDiOpenClassRegKey` at `0x14006e5d1`
- `SETUPAPI!SetupDiOpenClassRegKey` at `0x14006e5d1`

## string_xrefs

- `0x14006e518`: `termsrv\wms\src\common\srcutils\srcdriverinstaller.cpp`
- `0x14006e614`: `termsrv\wms\src\common\srcutils\srcdriverinstaller.cpp`
- `0x14006e505`: `RemoveDriverFromFilters`
- `0x14006e607`: `RemoveDriverFromFilters`

## pseudocode

```c
__int64 __fastcall RemoveDriverFromFilters(wchar_t *String2, const WCHAR *lpValueName, GUID *ClassGuid)
{
  const unsigned __int16 *v5; // r12
  unsigned int v6; // r15d
  unsigned int v7; // ebx
  HKEY v8; // rax
  const unsigned __int16 *v9; // r9
  HKEY v10; // r14
  signed int LastError; // eax

  if ( String2 )
  {
    if ( lpValueName )
    {
      if ( ClassGuid )
      {
        v8 = SetupDiOpenClassRegKey(ClassGuid, 0xF003Fu);
        v10 = v8;
        if ( v8 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( (v7 & 0x80000000) == 0 )
            v7 = -2147467259;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
            0xA9u,
            L"RemoveDriverFromFilters",
            L"CBRAEx",
            L"hSetupClassRegKey != ((HANDLE)(LONG_PTR)-1)",
            v7);
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
              169,
              L"RemoveDriverFromFilters",
              L"CBRAEx",
              L"hSetupClassRegKey != ((HANDLE)(LONG_PTR)-1)",
              v7);
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
              169,
              L"RemoveDriverFromFilters",
              L"CBRAEx",
              L"hSetupClassRegKey != ((HANDLE)(LONG_PTR)-1)",
              v7);
        }
        else
        {
          v7 = 0;
          RegUtil::RemoveFromRegMultiSz(v8, lpValueName, String2, v9);
          if ( !v10 )
            return v7;
        }
        RegCloseKey(v10);
        return v7;
      }
      v5 = L"setupClass != 0";
      v6 = 162;
    }
    else
    {
      v5 = L"pszFilterType != 0";
      v6 = 161;
    }
  }
  else
  {
    v5 = L"pszDriverName != 0";
    v6 = 160;
  }
  v7 = -2147024809;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
    v6,
    L"RemoveDriverFromFilters",
    L"CBRAEx",
    v5,
    -2147024809);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
      v6,
      L"RemoveDriverFromFilters",
      L"CBRAEx",
      v5,
      -2147024809);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
      v6,
      L"RemoveDriverFromFilters",
      L"CBRAEx",
      v5,
      -2147024809);
  return v7;
}

```

## disassembly

```asm
0x14006e4d4  push    rbx
0x14006e4d6  push    rbp
0x14006e4d7  push    rsi
0x14006e4d8  push    rdi
0x14006e4d9  push    r12
0x14006e4db  push    r14
0x14006e4dd  push    r15
0x14006e4df  sub     rsp, 40h
0x14006e4e3  mov     rdi, rdx
0x14006e4e6  mov     rsi, rcx
0x14006e4e9  test    rcx, rcx
0x14006e4ec  jnz     loc_14006E59B
0x14006e4f2  lea     r12, aPszdrivername0; "pszDriverName != 0"
0x14006e4f9  mov     r15d, 0A0h
0x14006e4ff  mov     r14d, 80070057h
0x14006e505  lea     rsi, aRemovedriverfr; "RemoveDriverFromFilters"
0x14006e50c  lea     rbp, aCbraex; "CBRAEx"
0x14006e513  mov     [rsp+78h+var_50], r14d; int
0x14006e518  lea     rdi, aTermsrvWmsSrcC_27; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14006e51f  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x14006e524  mov     r8, rsi; unsigned __int16 *
0x14006e527  mov     r9, rbp; unsigned __int16 *
0x14006e52a  mov     rcx, rdi; unsigned __int16 *
0x14006e52d  mov     edx, r15d; unsigned int
0x14006e530  mov     ebx, r14d
0x14006e533  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006e538  call    cs:__imp_IsDebuggerPresent
0x14006e53e  test    eax, eax
0x14006e540  jz      short loc_14006E572
0x14006e542  mov     [rsp+78h+var_40], r14d
0x14006e547  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006e54e  mov     [rsp+78h+var_48], r12
0x14006e553  mov     r9d, r15d
0x14006e556  mov     qword ptr [rsp+78h+var_50], rbp
0x14006e55b  mov     r8, rdi
0x14006e55e  mov     ecx, 2; unsigned __int8
0x14006e563  mov     [rsp+78h+var_58], rsi
0x14006e568  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006e56d  jmp     loc_14006E6B8
0x14006e572  mov     dword ptr [rsp+78h+var_48], r14d
0x14006e577  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006e57e  mov     qword ptr [rsp+78h+var_50], r12
0x14006e583  mov     r9, rsi
0x14006e586  mov     r8d, r15d
0x14006e589  mov     [rsp+78h+var_58], rbp
0x14006e58e  mov     rdx, rdi
0x14006e591  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006e596  jmp     loc_14006E6B8
0x14006e59b  test    rdi, rdi
0x14006e59e  jnz     short loc_14006E5B2
0x14006e5a0  lea     r12, aPszfiltertype0; "pszFilterType != 0"
0x14006e5a7  mov     r15d, 0A1h
0x14006e5ad  jmp     loc_14006E4FF
0x14006e5b2  test    r8, r8
0x14006e5b5  jnz     short loc_14006E5C9
0x14006e5b7  lea     r12, aSetupclass0; "setupClass != 0"
0x14006e5be  mov     r15d, 0A2h
0x14006e5c4  jmp     loc_14006E4FF
0x14006e5c9  mov     edx, 0F003Fh; samDesired
0x14006e5ce  mov     rcx, r8; ClassGuid
0x14006e5d1  call    cs:__imp_SetupDiOpenClassRegKey
0x14006e5d7  mov     r14, rax
0x14006e5da  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006e5de  jnz     loc_14006E69A
0x14006e5e4  call    cs:__imp_GetLastError
0x14006e5ea  mov     ebx, eax
0x14006e5ec  test    eax, eax
0x14006e5ee  jle     short loc_14006E5F9
0x14006e5f0  movzx   ebx, ax
0x14006e5f3  or      ebx, 80070000h
0x14006e5f9  mov     eax, 80004005h
0x14006e5fe  lea     rbp, aCbraex; "CBRAEx"
0x14006e605  test    ebx, ebx
0x14006e607  lea     rsi, aRemovedriverfr; "RemoveDriverFromFilters"
0x14006e60e  mov     r15d, 0A9h
0x14006e614  lea     rdi, aTermsrvWmsSrcC_27; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14006e61b  cmovns  ebx, eax
0x14006e61e  lea     r12, aHsetupclassreg; "hSetupClassRegKey != ((HANDLE)(LONG_PTR"...
0x14006e625  mov     [rsp+78h+var_50], ebx; int
0x14006e629  mov     r9, rbp; unsigned __int16 *
0x14006e62c  mov     r8, rsi; unsigned __int16 *
0x14006e62f  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x14006e634  mov     edx, r15d; unsigned int
0x14006e637  mov     rcx, rdi; unsigned __int16 *
0x14006e63a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006e63f  call    cs:__imp_IsDebuggerPresent
0x14006e645  test    eax, eax
0x14006e647  jz      short loc_14006E675
0x14006e649  mov     [rsp+78h+var_40], ebx
0x14006e64d  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006e654  mov     [rsp+78h+var_48], r12
0x14006e659  mov     r9d, r15d
0x14006e65c  mov     qword ptr [rsp+78h+var_50], rbp
0x14006e661  mov     r8, rdi
0x14006e664  mov     ecx, 2; unsigned __int8
0x14006e669  mov     [rsp+78h+var_58], rsi
0x14006e66e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006e673  jmp     short loc_14006E6AF
0x14006e675  mov     dword ptr [rsp+78h+var_48], ebx
0x14006e679  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006e680  mov     qword ptr [rsp+78h+var_50], r12
0x14006e685  mov     r9, rsi
0x14006e688  mov     r8d, r15d
0x14006e68b  mov     [rsp+78h+var_58], rbp
0x14006e690  mov     rdx, rdi
0x14006e693  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006e698  jmp     short loc_14006E6AF
0x14006e69a  xor     ebx, ebx
0x14006e69c  mov     r8, rsi; String2
0x14006e69f  mov     rdx, rdi; lpValueName
0x14006e6a2  mov     rcx, r14; hKey
0x14006e6a5  call    ?RemoveFromRegMultiSz@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z; RegUtil::RemoveFromRegMultiSz(HKEY__ *,ushort const *,ushort const *)
0x14006e6aa  test    r14, r14
0x14006e6ad  jz      short loc_14006E6B8
0x14006e6af  mov     rcx, r14; hKey
0x14006e6b2  call    cs:__imp_RegCloseKey
0x14006e6b8  mov     eax, ebx
0x14006e6ba  add     rsp, 40h
0x14006e6be  pop     r15
0x14006e6c0  pop     r14
0x14006e6c2  pop     r12
0x14006e6c4  pop     rdi
0x14006e6c5  pop     rsi
0x14006e6c6  pop     rbp
0x14006e6c7  pop     rbx
0x14006e6c8  retn
```
