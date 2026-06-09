# winreGetStoredRecoveryDir(ushort *)

- ea: `0x18002bad4`
- end: `0x18002bc51`
- name: `?winreGetStoredRecoveryDir@@YAHPEAG@Z`
- size: `381`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002bfac`

## callees

- `0x1800059fc`
- `0x18000c658`
- `0x18000ff68`
- `0x18002bad4`
- `0x18002ca4c`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18002bb75`
- `ADVAPI32!RegQueryValueExW` at `0x18002bb75`
- `ADVAPI32!RegOpenKeyExW` at `0x18002bb29`
- `ADVAPI32!RegOpenKeyExW` at `0x18002bb29`
- `ADVAPI32!RegCloseKey` at `0x18002bc31`
- `ADVAPI32!RegCloseKey` at `0x18002bc31`

## string_xrefs

- `0x18002bb36`: `RegOpenKeyEx(RecEnv) failed: 0x%x`
- `0x18002bbb7`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002bbb0`: `Failed to drop file form path`
- `0x18002bc19`: `failed to concatenate recovery root directory`

## pseudocode

```c
__int64 __fastcall winreGetStoredRecoveryDir(unsigned __int16 *a1)
{
  unsigned int v2; // edi
  unsigned int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // r9
  const wchar_t *v6; // r8
  unsigned int v7; // eax
  int v8; // eax
  LPDWORD lpcbData; // [rsp+28h] [rbp-30h]
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-20h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-1Ch] BYREF

  hKey = 0;
  Type = 0;
  v2 = 0;
  cbData = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\RecoveryEnvironment", 0, 1u, &hKey);
  if ( v3 )
  {
    UnattendLogW(1, L"RegOpenKeyEx(RecEnv) failed: 0x%x", v3);
    return v2;
  }
  cbData = 604;
  if ( !RegQueryValueExW(hKey, L"TargetOS", 0, &Type, (LPBYTE)a1, &cbData) && Type == 1 && cbData >= 0xA )
  {
    v4 = winreDropFileFormPath(a1);
    v5 = v4;
    if ( v4 )
    {
      LODWORD(lpcbData) = 87;
      v6 = L"Failed to drop file form path";
LABEL_8:
      UnattendLogW(
        2,
        L"winreGetStoredRecoveryDir %s (0x%x) in file %S line %d",
        v6,
        v5,
        "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
        lpcbData);
      goto LABEL_14;
    }
    v7 = winreAddTrailingBackslash(a1);
    v5 = v7;
    if ( v7 )
    {
      LODWORD(lpcbData) = 89;
      v6 = L"failed to add trailing back slash";
      goto LABEL_8;
    }
    v8 = StringCchCatW(a1, 0x12Eu, L"Recovery");
    v5 = (unsigned int)v8;
    if ( v8 < 0 )
    {
      LODWORD(lpcbData) = 91;
      v6 = L"failed to concatenate recovery root directory";
      goto LABEL_8;
    }
    v2 = 1;
  }
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18002bad4  mov     r11, rsp
0x18002bad7  mov     [r11+10h], rbx
0x18002badb  push    rdi
0x18002badc  sub     rsp, 50h
0x18002bae0  mov     rax, cs:__security_cookie
0x18002bae7  xor     rax, rsp
0x18002baea  mov     [rsp+58h+var_18], rax
0x18002baef  mov     rbx, rcx
0x18002baf2  mov     qword ptr [r11-28h], 0
0x18002bafa  lea     rax, [r11-28h]
0x18002bafe  mov     [rsp+58h+Type], 0
0x18002bb06  xor     edi, edi
0x18002bb08  mov     [rsp+58h+cbData], 0
0x18002bb10  xor     r8d, r8d; ulOptions
0x18002bb13  mov     [r11-38h], rax
0x18002bb17  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x18002bb1e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bb25  lea     r9d, [rdi+1]; samDesired
0x18002bb29  call    cs:__imp_RegOpenKeyExW
0x18002bb2f  test    eax, eax
0x18002bb31  jz      short loc_18002BB4A
0x18002bb33  mov     r8d, eax
0x18002bb36  lea     rdx, aRegopenkeyexRe; "RegOpenKeyEx(RecEnv) failed: 0x%x"
0x18002bb3d  lea     ecx, [rdi+1]
0x18002bb40  call    UnattendLogW
0x18002bb45  jmp     loc_18002BC37
0x18002bb4a  mov     rcx, [rsp+58h+hKey]; hKey
0x18002bb4f  lea     rax, [rsp+58h+cbData]
0x18002bb54  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18002bb59  lea     r9, [rsp+58h+Type]; lpType
0x18002bb5e  xor     r8d, r8d; lpReserved
0x18002bb61  mov     [rsp+58h+lpData], rbx; lpData
0x18002bb66  lea     rdx, aTargetos_0; "TargetOS"
0x18002bb6d  mov     [rsp+58h+cbData], 25Ch
0x18002bb75  call    cs:__imp_RegQueryValueExW
0x18002bb7b  test    eax, eax
0x18002bb7d  jnz     loc_18002BC27
0x18002bb83  cmp     [rsp+58h+Type], 1
0x18002bb88  jnz     loc_18002BC27
0x18002bb8e  cmp     [rsp+58h+cbData], 0Ah
0x18002bb93  jb      loc_18002BC27
0x18002bb99  mov     rcx, rbx
0x18002bb9c  call    winreDropFileFormPath
0x18002bba1  mov     r9d, eax
0x18002bba4  test    eax, eax
0x18002bba6  jz      short loc_18002BBD6
0x18002bba8  mov     dword ptr [rsp+58h+lpcbData], 57h ; 'W'
0x18002bbb0  lea     r8, aFailedToDropFi; "Failed to drop file form path"
0x18002bbb7  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002bbbe  mov     ecx, 2
0x18002bbc3  lea     rdx, aWinregetstored; "winreGetStoredRecoveryDir %s (0x%x) in "...
0x18002bbca  mov     [rsp+58h+lpData], rax
0x18002bbcf  call    UnattendLogW
0x18002bbd4  jmp     short loc_18002BC27
0x18002bbd6  mov     rcx, rbx
0x18002bbd9  call    winreAddTrailingBackslash
0x18002bbde  mov     r9d, eax
0x18002bbe1  test    eax, eax
0x18002bbe3  jz      short loc_18002BBF6
0x18002bbe5  mov     dword ptr [rsp+58h+lpcbData], 59h ; 'Y'
0x18002bbed  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x18002bbf4  jmp     short loc_18002BBB7
0x18002bbf6  lea     r8, AppName; "Recovery"
0x18002bbfd  mov     edx, 12Eh; unsigned __int64
0x18002bc02  mov     rcx, rbx; unsigned __int16 *
0x18002bc05  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002bc0a  mov     r9d, eax
0x18002bc0d  test    eax, eax
0x18002bc0f  jns     short loc_18002BC22
0x18002bc11  mov     dword ptr [rsp+58h+lpcbData], 5Bh ; '['
0x18002bc19  lea     r8, aFailedToConcat_4; "failed to concatenate recovery root dir"...
0x18002bc20  jmp     short loc_18002BBB7
0x18002bc22  mov     edi, 1
0x18002bc27  mov     rcx, [rsp+58h+hKey]; hKey
0x18002bc2c  test    rcx, rcx
0x18002bc2f  jz      short loc_18002BC37
0x18002bc31  call    cs:__imp_RegCloseKey
0x18002bc37  mov     eax, edi
0x18002bc39  mov     rcx, [rsp+58h+var_18]
0x18002bc3e  xor     rcx, rsp; StackCookie
0x18002bc41  call    __security_check_cookie
0x18002bc46  mov     rbx, [rsp+58h+arg_8]
0x18002bc4b  add     rsp, 50h
0x18002bc4f  pop     rdi
0x18002bc50  retn
```
