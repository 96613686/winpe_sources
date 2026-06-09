# _SaveTlKeys(_GUID &,HKEY__ *)

- ea: `0x180064db0`
- end: `0x180064f3c`
- name: `?_SaveTlKeys@@YAJAEAU_GUID@@PEAUHKEY__@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(struct _GUID *, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180063ad4`

## callees

- `0x180015ac0`
- `0x18001606c`
- `0x180059120`
- `0x18005b0d4`
- `0x1800646cc`
- `0x180064db0`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x180064e13`
- `KERNEL32!lstrlenA` at `0x180064e13`
- `USER32!wsprintfA` at `0x180064e09`
- `USER32!wsprintfA` at `0x180064e4b`
- `USER32!wsprintfA` at `0x180064e83`
- `USER32!wsprintfA` at `0x180064e09`
- `USER32!wsprintfA` at `0x180064e4b`
- `USER32!wsprintfA` at `0x180064e83`
- `ADVAPI32!RegSetValueA` at `0x180064e2c`
- `ADVAPI32!RegSetValueA` at `0x180064e2c`
- `ADVAPI32!RegOpenKeyA` at `0x180064e64`
- `ADVAPI32!RegOpenKeyA` at `0x180064e64`
- `ADVAPI32!RegCloseKey` at `0x180064ecc`
- `ADVAPI32!RegCloseKey` at `0x180064ee0`
- `ADVAPI32!RegCloseKey` at `0x180064ef5`
- `ADVAPI32!RegCloseKey` at `0x180064f04`
- `ADVAPI32!RegCloseKey` at `0x180064ecc`
- `ADVAPI32!RegCloseKey` at `0x180064ee0`
- `ADVAPI32!RegCloseKey` at `0x180064ef5`
- `ADVAPI32!RegCloseKey` at `0x180064f04`

## string_xrefs

- `0x180064dfe`: `DeleteTI\%s`
- `0x180064e78`: `Replace\Typelib\%s`

## pseudocode

```c
__int64 __fastcall _SaveTlKeys(struct _GUID *a1, HKEY a2)
{
  int v3; // esi
  DWORD cbData; // eax
  LSTATUS v5; // edi
  HKEY v6; // rbx
  HKEY v7; // rbx
  LSTATUS v8; // eax
  HKEY v9; // rcx
  unsigned int v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  HKEY hKey; // [rsp+30h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-61h] BYREF
  CHAR String[48]; // [rsp+40h] [rbp-59h] BYREF
  CHAR SubKey[80]; // [rsp+70h] [rbp-29h] BYREF

  v3 = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  StringFromGUID2Ansi(a1, String, 39);
  wsprintfA(SubKey, "DeleteTI\\%s", String);
  cbData = lstrlenA(String);
  v5 = RegSetValueA(a2, SubKey, 1u, String, cbData);
  if ( v5 )
  {
LABEL_11:
    if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(phkResult);
    goto LABEL_13;
  }
  wsprintfA(SubKey, "Typelib\\%s", String);
  v6 = phkResult;
  if ( RegOpenKeyA(HKEY_CLASSES_ROOT, SubKey, &phkResult) )
  {
    phkResult = v6;
    goto LABEL_11;
  }
  wsprintfA(SubKey, "Replace\\Typelib\\%s", String);
  v7 = hKey;
  v8 = FastRegCreateKey(a2, SubKey, &hKey);
  v9 = hKey;
  v5 = v8;
  if ( v8 )
    v9 = v7;
  hKey = v9;
  if ( v8 )
    goto LABEL_11;
  v10 = _ErrRegCopyTree(phkResult, v9);
  if ( v10 )
    v3 = _HrFromErr(v10);
  v11 = RegCloseKey(phkResult);
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v5 = v11;
  if ( !v11 )
  {
    v12 = RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    v5 = v12;
    goto LABEL_11;
  }
LABEL_13:
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  if ( v3 >= 0 )
    return (unsigned int)HrFromRegError(v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180064db0  mov     [rsp-8+arg_10], rbx
0x180064db5  push    rbp
0x180064db6  push    rsi
0x180064db7  push    rdi
0x180064db8  push    r14
0x180064dba  push    r15
0x180064dbc  lea     rbp, [rsp-37h]
0x180064dc1  mov     eax, 0D0h
0x180064dc6  call    _alloca_probe
0x180064dcb  sub     rsp, rax
0x180064dce  mov     rax, cs:__security_cookie
0x180064dd5  xor     rax, rsp
0x180064dd8  mov     [rbp+57h+var_30], rax
0x180064ddc  mov     r14, rdx
0x180064ddf  or      r15, 0FFFFFFFFFFFFFFFFh
0x180064de3  xor     esi, esi
0x180064de5  lea     r8d, [rsi+27h]; int
0x180064de9  lea     rdx, [rbp+57h+String]; char *
0x180064ded  mov     [rbp+57h+hKey], r15
0x180064df1  mov     [rbp+57h+phkResult], r15
0x180064df5  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x180064dfa  lea     r8, [rbp+57h+String]
0x180064dfe  lea     rdx, aDeletetiS; "DeleteTI\\%s"
0x180064e05  lea     rcx, [rbp+57h+SubKey]; LPSTR
0x180064e09  call    cs:__imp_wsprintfA
0x180064e0f  lea     rcx, [rbp+57h+String]; lpString
0x180064e13  call    cs:__imp_lstrlenA
0x180064e19  lea     r9, [rbp+57h+String]; lpData
0x180064e1d  lea     r8d, [rsi+1]; dwType
0x180064e21  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180064e25  mov     rcx, r14; hKey
0x180064e28  mov     [rsp+0F0h+cbData], eax; cbData
0x180064e2c  call    cs:__imp_RegSetValueA
0x180064e32  mov     edi, eax
0x180064e34  test    eax, eax
0x180064e36  jnz     loc_180064EEC
0x180064e3c  lea     r8, [rbp+57h+String]
0x180064e40  lea     rdx, aTypelibS; "Typelib\\%s"
0x180064e47  lea     rcx, [rbp+57h+SubKey]; LPSTR
0x180064e4b  call    cs:__imp_wsprintfA
0x180064e51  mov     rbx, [rbp+57h+phkResult]
0x180064e55  lea     r8, [rbp+57h+phkResult]; phkResult
0x180064e59  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180064e5d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180064e64  call    cs:__imp_RegOpenKeyA
0x180064e6a  test    eax, eax
0x180064e6c  jz      short loc_180064E74
0x180064e6e  mov     [rbp+57h+phkResult], rbx
0x180064e72  jmp     short loc_180064EEC
0x180064e74  lea     r8, [rbp+57h+String]
0x180064e78  lea     rdx, aReplaceTypelib; "Replace\\Typelib\\%s"
0x180064e7f  lea     rcx, [rbp+57h+SubKey]; LPSTR
0x180064e83  call    cs:__imp_wsprintfA
0x180064e89  mov     rbx, [rbp+57h+hKey]
0x180064e8d  lea     r8, [rbp+57h+hKey]; HKEY *
0x180064e91  lea     rdx, [rbp+57h+SubKey]; char *
0x180064e95  mov     rcx, r14; HKEY
0x180064e98  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180064e9d  mov     rcx, [rbp+57h+hKey]
0x180064ea1  test    eax, eax
0x180064ea3  mov     edi, eax
0x180064ea5  cmovnz  rcx, rbx
0x180064ea9  mov     [rbp+57h+hKey], rcx
0x180064ead  jnz     short loc_180064EEC
0x180064eaf  mov     rdx, rcx; HKEY
0x180064eb2  mov     rcx, [rbp+57h+phkResult]; HKEY
0x180064eb6  call    ?_ErrRegCopyTree@@YAIPEAUHKEY__@@0@Z; _ErrRegCopyTree(HKEY__ *,HKEY__ *)
0x180064ebb  test    eax, eax
0x180064ebd  jz      short loc_180064EC8
0x180064ebf  mov     ecx, eax; unsigned int
0x180064ec1  call    ?_HrFromErr@@YAJI@Z; _HrFromErr(uint)
0x180064ec6  mov     esi, eax
0x180064ec8  mov     rcx, [rbp+57h+phkResult]; hKey
0x180064ecc  call    cs:__imp_RegCloseKey
0x180064ed2  mov     [rbp+57h+phkResult], r15
0x180064ed6  mov     edi, eax
0x180064ed8  test    eax, eax
0x180064eda  jnz     short loc_180064EFB
0x180064edc  mov     rcx, [rbp+57h+hKey]; hKey
0x180064ee0  call    cs:__imp_RegCloseKey
0x180064ee6  mov     [rbp+57h+hKey], r15
0x180064eea  mov     edi, eax
0x180064eec  mov     rcx, [rbp+57h+phkResult]; hKey
0x180064ef0  cmp     rcx, r15
0x180064ef3  jz      short loc_180064EFB
0x180064ef5  call    cs:__imp_RegCloseKey
0x180064efb  mov     rcx, [rbp+57h+hKey]; hKey
0x180064eff  cmp     rcx, r15
0x180064f02  jz      short loc_180064F0A
0x180064f04  call    cs:__imp_RegCloseKey
0x180064f0a  test    esi, esi
0x180064f0c  js      short loc_180064F17
0x180064f0e  mov     ecx, edi; int
0x180064f10  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x180064f15  mov     esi, eax
0x180064f17  mov     eax, esi
0x180064f19  mov     rcx, [rbp+57h+var_30]
0x180064f1d  xor     rcx, rsp; StackCookie
0x180064f20  call    __security_check_cookie
0x180064f25  mov     rbx, [rsp+0F0h+arg_10]
0x180064f2d  add     rsp, 0D0h
0x180064f34  pop     r15
0x180064f36  pop     r14
0x180064f38  pop     rdi
0x180064f39  pop     rsi
0x180064f3a  pop     rbp
0x180064f3b  retn
```
