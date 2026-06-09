# AcmEngineApply(void *)

- ea: `0x18004d1e0`
- end: `0x18004d4c6`
- name: `?AcmEngineApply@@YAJPEAX@Z`
- size: `742`
- prototype: `__int64 __fastcall(struct _ACM_ENGINE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000aa70`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000a654`
- `0x18004d1e0`
- `0x18004e6e4`
- `0x18004eadc`
- `0x1800543c0`
- `0x180059fac`

## import_xrefs

- `KERNEL32!FindNextFileW` at `0x18004d409`
- `KERNEL32!FindNextFileW` at `0x18004d409`
- `KERNEL32!FindFirstFileW` at `0x18004d32c`
- `KERNEL32!FindFirstFileW` at `0x18004d32c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18004d297`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18004d297`
- `KERNEL32!GetLastError` at `0x18004d2a1`
- `KERNEL32!GetLastError` at `0x18004d33b`
- `KERNEL32!GetLastError` at `0x18004d417`
- `KERNEL32!GetLastError` at `0x18004d2a1`
- `KERNEL32!GetLastError` at `0x18004d33b`
- `KERNEL32!GetLastError` at `0x18004d417`
- `ntdll!RtlDoesFileExists_U` at `0x18004d2cb`
- `ntdll!RtlDoesFileExists_U` at `0x18004d2cb`
- `ADVAPI32!RegDeleteKeyW` at `0x18004d453`
- `ADVAPI32!RegDeleteKeyW` at `0x18004d453`

## string_xrefs

- `0x18004d45f`: `Failed to make full file path [%x]`

## pseudocode

```c
__int64 __fastcall AcmEngineApply(struct _ACM_ENGINE *a1)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 v6; // r8
  HRESULT v7; // eax
  HANDLE FirstFileW; // rsi
  HRESULT v9; // eax
  int v10; // eax
  signed int v11; // eax
  __int64 v12; // [rsp+20h] [rbp-E0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR SubKey[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t pszDest[264]; // [rsp+490h] [rbp+390h] BYREF
  wchar_t v16[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  memset_0(SubKey, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(pszDest, 0, 0x208u);
  memset_0(v16, 0, 0x208u);
  if ( !a1 )
  {
    AslLogCallPrintf(1, "AcmEngineApply", 946, "Invalid inputs");
    return 2147942487LL;
  }
  if ( !ExpandEnvironmentStringsW(L"%windir%\\Panther\\MigrationShims", (LPWSTR)a1, 0x104u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = "Failed to make migration shim dir string [%x]";
    v6 = 958;
LABEL_32:
    LODWORD(v12) = v4;
    AslLogCallPrintf(1, "AcmEngineApply", v6, v5, v12);
    return v4;
  }
  if ( RtlDoesFileExists_U((PCWSTR)a1) )
  {
    v7 = StringCchPrintfW(pszDest, 0x104u, L"%s\\%s*", a1, L"MigShim");
    v4 = v7;
    if ( v7 < 0 )
    {
      LODWORD(v12) = v7;
      AslLogCallPrintf(1, "AcmEngineApply", 978, "Failed to make find string [%x]", v12);
      return v4;
    }
    FirstFileW = FindFirstFileW(pszDest, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) != 0
          && (FindFileData.cFileName[0] != 46
           || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2])) )
        {
          v9 = StringCchPrintfW(v16, 0x104u, L"%s\\%s", a1, FindFileData.cFileName);
          v4 = v9;
          if ( v9 < 0 )
          {
            LODWORD(v12) = v9;
            AslLogCallPrintf(1, "AcmEngineApply", 1015, "Failed to make full file path [%x]", v12);
            return v4;
          }
          v10 = AcmpApplyShim(a1, v16);
          if ( v10 < 0 )
            AslLogCallPrintf(1, "AcmEngineApply", 1021, "Failed to apply shim [%x]", v10);
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      v11 = GetLastError();
      v4 = v11;
      if ( v11 == 18 )
      {
        v4 = 0;
        AslPathRemoveDirectory((const WCHAR *)a1);
        AcmEngineGetShimKey(SubKey);
        if ( SubKey[0] )
          RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
        return v4;
      }
      if ( v11 > 0 )
        v4 = (unsigned __int16)v11 | 0x80070000;
      v5 = "FindNextFile failed [%x]";
      v6 = 1036;
      goto LABEL_32;
    }
    v4 = GetLastError();
    if ( v4 - 2 > 1 )
    {
      if ( (int)v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      v5 = "FindFirstFile failed [%x]";
      v6 = 996;
      goto LABEL_32;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004d1e0  mov     [rsp-8+arg_8], rbx
0x18004d1e5  mov     [rsp-8+arg_10], rsi
0x18004d1ea  push    rbp
0x18004d1eb  push    rdi
0x18004d1ec  push    r14
0x18004d1ee  lea     rbp, [rsp-7C0h]
0x18004d1f6  sub     rsp, 8C0h
0x18004d1fd  mov     rax, cs:__security_cookie
0x18004d204  xor     rax, rsp
0x18004d207  mov     [rbp+7D0h+var_20], rax
0x18004d20e  mov     rdi, rcx
0x18004d211  mov     ebx, 208h
0x18004d216  mov     r8d, ebx; Size
0x18004d219  lea     rcx, [rbp+7D0h+SubKey]; void *
0x18004d220  xor     edx, edx; Val
0x18004d222  call    memset_0
0x18004d227  xor     edx, edx; Val
0x18004d229  lea     r8d, [rbx+48h]; Size
0x18004d22d  lea     rcx, [rsp+8D0h+FindFileData]; void *
0x18004d232  call    memset_0
0x18004d237  mov     r8d, ebx; Size
0x18004d23a  lea     rcx, [rbp+7D0h+pszDest]; void *
0x18004d241  xor     edx, edx; Val
0x18004d243  call    memset_0
0x18004d248  mov     r8d, ebx; Size
0x18004d24b  lea     rcx, [rbp+7D0h+var_230]; void *
0x18004d252  xor     edx, edx; Val
0x18004d254  call    memset_0
0x18004d259  xor     r14d, r14d
0x18004d25c  test    rdi, rdi
0x18004d25f  jnz     short loc_18004D287
0x18004d261  lea     r9, aInvalidInputs; "Invalid inputs"
0x18004d268  mov     r8d, 3B2h
0x18004d26e  lea     rdx, aAcmengineapply_0; "AcmEngineApply"
0x18004d275  lea     ecx, [rdi+1]
0x18004d278  call    AslLogCallPrintf
0x18004d27d  mov     eax, 80070057h
0x18004d282  jmp     loc_18004D49F
0x18004d287  mov     r8d, 104h; nSize
0x18004d28d  lea     rcx, aWindirPantherM; "%windir%\\Panther\\MigrationShims"
0x18004d294  mov     rdx, rdi; lpDst
0x18004d297  call    cs:__imp_ExpandEnvironmentStringsW
0x18004d29d  test    eax, eax
0x18004d29f  jnz     short loc_18004D2C8
0x18004d2a1  call    cs:__imp_GetLastError
0x18004d2a7  mov     ebx, eax
0x18004d2a9  test    eax, eax
0x18004d2ab  jle     short loc_18004D2B6
0x18004d2ad  movzx   ebx, ax
0x18004d2b0  or      ebx, 80070000h
0x18004d2b6  lea     r9, aFailedToMakeMi; "Failed to make migration shim dir strin"...
0x18004d2bd  mov     r8d, 3BEh
0x18004d2c3  jmp     loc_18004D488
0x18004d2c8  mov     rcx, rdi; FileName
0x18004d2cb  call    cs:__imp_RtlDoesFileExists_U
0x18004d2d1  test    al, al
0x18004d2d3  jnz     short loc_18004D2DD
0x18004d2d5  mov     ebx, r14d
0x18004d2d8  jmp     loc_18004D49D
0x18004d2dd  lea     rax, aMigshim; "MigShim"
0x18004d2e4  mov     r9, rdi
0x18004d2e7  lea     r8, aSS_1; "%s\\%s*"
0x18004d2ee  mov     [rsp+8D0h+var_8B0], rax
0x18004d2f3  mov     edx, 104h; cchDest
0x18004d2f8  lea     rcx, [rbp+7D0h+pszDest]; pszDest
0x18004d2ff  call    StringCchPrintfW
0x18004d304  mov     ebx, eax
0x18004d306  test    eax, eax
0x18004d308  jns     short loc_18004D320
0x18004d30a  mov     dword ptr [rsp+8D0h+var_8B0], eax
0x18004d30e  lea     r9, aFailedToMakeFi; "Failed to make find string [%x]"
0x18004d315  mov     r8d, 3D2h
0x18004d31b  jmp     loc_18004D48C
0x18004d320  lea     rdx, [rsp+8D0h+FindFileData]; lpFindFileData
0x18004d325  lea     rcx, [rbp+7D0h+pszDest]; lpFileName
0x18004d32c  call    cs:__imp_FindFirstFileW
0x18004d332  mov     rsi, rax
0x18004d335  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004d339  jnz     short loc_18004D36A
0x18004d33b  call    cs:__imp_GetLastError
0x18004d341  mov     ebx, eax
0x18004d343  add     eax, 0FFFFFFFEh
0x18004d346  cmp     eax, 1
0x18004d349  jbe     short loc_18004D2D5
0x18004d34b  test    ebx, ebx
0x18004d34d  jle     short loc_18004D358
0x18004d34f  movzx   ebx, bx
0x18004d352  or      ebx, 80070000h
0x18004d358  lea     r9, aFindfirstfileF; "FindFirstFile failed [%x]"
0x18004d35f  mov     r8d, 3E4h
0x18004d365  jmp     loc_18004D488
0x18004d36a  test    byte ptr [rsp+8D0h+FindFileData.dwFileAttributes], 10h
0x18004d36f  jz      loc_18004D401
0x18004d375  cmp     [rsp+8D0h+FindFileData.cFileName], 2Eh ; '.'
0x18004d37b  movzx   eax, [rsp+8D0h+FindFileData.cFileName+2]
0x18004d380  jnz     short loc_18004D39D
0x18004d382  test    ax, ax
0x18004d385  jz      short loc_18004D401
0x18004d387  cmp     [rsp+8D0h+FindFileData.cFileName], 2Eh ; '.'
0x18004d38d  jnz     short loc_18004D39D
0x18004d38f  cmp     ax, 2Eh ; '.'
0x18004d393  jnz     short loc_18004D39D
0x18004d395  cmp     [rsp+8D0h+FindFileData.cFileName+4], r14w
0x18004d39b  jz      short loc_18004D401
0x18004d39d  lea     rax, [rsp+8D0h+FindFileData.cFileName]
0x18004d3a2  mov     r9, rdi
0x18004d3a5  lea     r8, aSS_0; "%s\\%s"
0x18004d3ac  mov     [rsp+8D0h+var_8B0], rax
0x18004d3b1  mov     edx, 104h; cchDest
0x18004d3b6  lea     rcx, [rbp+7D0h+var_230]; pszDest
0x18004d3bd  call    StringCchPrintfW
0x18004d3c2  mov     ebx, eax
0x18004d3c4  test    eax, eax
0x18004d3c6  js      loc_18004D45B
0x18004d3cc  lea     rdx, [rbp+7D0h+var_230]; unsigned __int16 *
0x18004d3d3  mov     rcx, rdi; struct _ACM_ENGINE *
0x18004d3d6  call    ?AcmpApplyShim@@YAJPEAU_ACM_ENGINE@@PEBG@Z; AcmpApplyShim(_ACM_ENGINE *,ushort const *)
0x18004d3db  test    eax, eax
0x18004d3dd  jns     short loc_18004D401
0x18004d3df  lea     r9, aFailedToApplyS; "Failed to apply shim [%x]"
0x18004d3e6  mov     dword ptr [rsp+8D0h+var_8B0], eax
0x18004d3ea  mov     r8d, 3FDh
0x18004d3f0  lea     rdx, aAcmengineapply_0; "AcmEngineApply"
0x18004d3f7  mov     ecx, 1
0x18004d3fc  call    AslLogCallPrintf
0x18004d401  lea     rdx, [rsp+8D0h+FindFileData]; lpFindFileData
0x18004d406  mov     rcx, rsi; hFindFile
0x18004d409  call    cs:__imp_FindNextFileW
0x18004d40f  test    eax, eax
0x18004d411  jnz     loc_18004D36A
0x18004d417  call    cs:__imp_GetLastError
0x18004d41d  mov     ebx, eax
0x18004d41f  cmp     eax, 12h
0x18004d422  jnz     short loc_18004D46E
0x18004d424  mov     rcx, rdi
0x18004d427  mov     ebx, r14d
0x18004d42a  call    AslPathRemoveDirectory
0x18004d42f  lea     rcx, [rbp+7D0h+SubKey]; pszDest
0x18004d436  call    ?AcmEngineGetShimKey@@YAJPEAG@Z; AcmEngineGetShimKey(ushort *)
0x18004d43b  cmp     r14w, [rbp+7D0h+SubKey]
0x18004d443  jz      short loc_18004D49D
0x18004d445  lea     rdx, [rbp+7D0h+SubKey]; lpSubKey
0x18004d44c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004d453  call    cs:__imp_RegDeleteKeyW
0x18004d459  jmp     short loc_18004D49D
0x18004d45b  mov     dword ptr [rsp+8D0h+var_8B0], eax
0x18004d45f  lea     r9, aFailedToMakeFu; "Failed to make full file path [%x]"
0x18004d466  mov     r8d, 3F7h
0x18004d46c  jmp     short loc_18004D48C
0x18004d46e  test    eax, eax
0x18004d470  jle     short loc_18004D47B
0x18004d472  movzx   ebx, ax
0x18004d475  or      ebx, 80070000h
0x18004d47b  lea     r9, aFindnextfileFa; "FindNextFile failed [%x]"
0x18004d482  mov     r8d, 40Ch
0x18004d488  mov     dword ptr [rsp+8D0h+var_8B0], ebx
0x18004d48c  lea     rdx, aAcmengineapply_0; "AcmEngineApply"
0x18004d493  mov     ecx, 1
0x18004d498  call    AslLogCallPrintf
0x18004d49d  mov     eax, ebx
0x18004d49f  mov     rcx, [rbp+7D0h+var_20]
0x18004d4a6  xor     rcx, rsp; StackCookie
0x18004d4a9  call    __security_check_cookie
0x18004d4ae  lea     r11, [rsp+8D0h+var_10]
0x18004d4b6  mov     rbx, [r11+28h]
0x18004d4ba  mov     rsi, [r11+30h]
0x18004d4be  mov     rsp, r11
0x18004d4c1  pop     r14
0x18004d4c3  pop     rdi
0x18004d4c4  pop     rbp
0x18004d4c5  retn
```
