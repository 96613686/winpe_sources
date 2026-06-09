# Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileForUser(HKEY__ * const,ushort const *,_FILETIME const &,Windows::Internal::WiFiCloudStore::ProfileModificationType)

- ea: `0x18003c0a8`
- end: `0x18003c168`
- name: `?StoreSyncNeededProfileForUser@WiFiCloudStore@Internal@Windows@@YAXQEAUHKEY__@@PEBGAEBU_FILETIME@@W4ProfileModificationType@123@@Z`
- size: `192`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003c170`

## callees

- `0x180006420`
- `0x1800079f0`
- `0x180007f90`
- `0x18002a030`
- `0x180031ce4`
- `0x18003c0a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c126`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c126`

## string_xrefs

- `0x18003c137`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileForUser(
        HKEY a1,
        __int64 a2,
        __int64 *a3,
        int a4)
{
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  unsigned int lpData; // [rsp+20h] [rbp-29h]
  BYTE Data[4]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v10; // [rsp+34h] [rbp-15h]
  int v11; // [rsp+3Ch] [rbp-Dh]
  LPCWSTR lpValueName[4]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v13[32]; // [rsp+60h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *(_DWORD *)Data = 1;
  v10 = *a3;
  v11 = a4;
  std::wstring::wstring(v13, a2);
  Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(lpValueName, v13);
  std::wstring::~wstring((__int64)v13);
  v5 = (const WCHAR *)lpValueName;
  if ( lpValueName[3] > (LPCWSTR)7 )
    v5 = lpValueName[0];
  v6 = RegSetValueExW(a1, v5, 0, 3u, Data, 0x10u);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
      (const char *)v6,
      lpData);
  return std::wstring::~wstring((__int64)lpValueName);
}

```

## disassembly

```asm
0x18003c0a8  push    rbp
0x18003c0aa  push    rbx
0x18003c0ab  lea     rbp, [rsp-4Fh]
0x18003c0b0  sub     rsp, 98h
0x18003c0b7  mov     rax, cs:__security_cookie
0x18003c0be  xor     rax, rsp
0x18003c0c1  mov     [rbp+57h+var_20], rax
0x18003c0c5  mov     rbx, rcx
0x18003c0c8  mov     dword ptr [rbp+57h+Data], 1
0x18003c0cf  mov     rax, [r8]
0x18003c0d2  mov     [rbp+57h+var_6C], rax
0x18003c0d6  mov     [rbp+57h+var_64], r9d
0x18003c0da  lea     rcx, [rbp+57h+var_40]
0x18003c0de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003c0e3  nop
0x18003c0e4  lea     rdx, [rbp+57h+var_40]
0x18003c0e8  lea     rcx, [rbp+57h+lpValueName]
0x18003c0ec  call    ?ProfileNameToCDSReferenceId@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(std::wstring const &)
0x18003c0f1  nop
0x18003c0f2  lea     rcx, [rbp+57h+var_40]
0x18003c0f6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c0fb  lea     rdx, [rbp+57h+lpValueName]
0x18003c0ff  cmp     [rbp+57h+var_48], 7
0x18003c104  cmova   rdx, [rbp+57h+lpValueName]; lpValueName
0x18003c109  mov     [rsp+0A0h+cbData], 10h; cbData
0x18003c111  lea     rax, [rbp+57h+Data]
0x18003c115  mov     [rsp+0A0h+lpData], rax; unsigned int
0x18003c11a  mov     r9d, 3; dwType
0x18003c120  xor     r8d, r8d; Reserved
0x18003c123  mov     rcx, rbx; hKey
0x18003c126  call    cs:__imp_RegSetValueExW
0x18003c12c  mov     rcx, [rbp+5Fh]; this
0x18003c130  test    eax, eax
0x18003c132  jz      short loc_18003C149
0x18003c134  mov     r9d, eax; char *
0x18003c137  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18003c13e  mov     edx, 15h; void *
0x18003c143  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c149  lea     rcx, [rbp+57h+lpValueName]
0x18003c14d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c152  mov     rcx, [rbp+57h+var_20]
0x18003c156  xor     rcx, rsp; StackCookie
0x18003c159  call    __security_check_cookie
0x18003c15e  add     rsp, 98h
0x18003c165  pop     rbx
0x18003c166  pop     rbp
0x18003c167  retn
```
