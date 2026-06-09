# BuildClassesList(void)

- ea: `0x180017894`
- end: `0x180017a26`
- name: `?BuildClassesList@@YAPEAU_class_entry@@XZ`
- size: `402`
- prototype: `struct _class_entry *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800169d4`

## callees

- `0x180017704`
- `0x180017894`
- `0x18001d66a`
- `0x18001d6c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180017993`
- `ADVAPI32!RegCloseKey` at `0x1800179f2`
- `ADVAPI32!RegCloseKey` at `0x180017a02`
- `ADVAPI32!RegCloseKey` at `0x180017993`
- `ADVAPI32!RegCloseKey` at `0x1800179f2`
- `ADVAPI32!RegCloseKey` at `0x180017a02`
- `ADVAPI32!RegEnumKeyExW` at `0x1800179da`
- `ADVAPI32!RegEnumKeyExW` at `0x1800179da`
- `ADVAPI32!RegOpenKeyExW` at `0x1800178f1`
- `ADVAPI32!RegOpenKeyExW` at `0x18001791e`
- `ADVAPI32!RegOpenKeyExW` at `0x180017961`
- `ADVAPI32!RegOpenKeyExW` at `0x1800178f1`
- `ADVAPI32!RegOpenKeyExW` at `0x18001791e`
- `ADVAPI32!RegOpenKeyExW` at `0x180017961`

## string_xrefs

- `0x180017917`: `Extensions`

## pseudocode

```c
struct _class_entry *BuildClassesList(void)
{
  struct _class_entry *v0; // rbx
  DWORD v1; // edi
  DWORD i; // edx
  struct _class_entry *v3; // rax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v7; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  phkResult = 0;
  v7 = 0;
  cchName = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\ADs\\Providers\\IIS", 0, 0x20019u, &hKey)
    && !RegOpenKeyExW(hKey, L"Extensions", 0, 0x20019u, &phkResult) )
  {
    v1 = 0;
    memset_0(SubKey, 0, 0x208u);
    for ( i = 0; ; i = v1 )
    {
      cchName = 260;
      if ( RegEnumKeyExW(phkResult, i, SubKey, &cchName, 0, 0, 0, 0)
        || RegOpenKeyExW(phkResult, SubKey, 0, 0x20019u, &v7) )
      {
        break;
      }
      v3 = BuildClassEntry(SubKey, v7);
      if ( v3 )
      {
        *((_QWORD *)v3 + 66) = v0;
        v0 = v3;
      }
      if ( v7 )
        RegCloseKey(v7);
      memset_0(SubKey, 0, 0x208u);
      ++v1;
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180017894  push    rbp
0x180017896  push    rbx
0x180017897  push    rsi
0x180017898  push    rdi
0x180017899  lea     rbp, [rsp-188h]
0x1800178a1  sub     rsp, 288h
0x1800178a8  mov     rax, cs:__security_cookie
0x1800178af  xor     rax, rsp
0x1800178b2  mov     [rbp+1A0h+var_30], rax
0x1800178b9  xor     esi, esi
0x1800178bb  lea     rax, [rsp+2A0h+hKey]
0x1800178c0  mov     r9d, 20019h; samDesired
0x1800178c6  mov     [rsp+2A0h+hKey], rsi
0x1800178cb  xor     r8d, r8d; ulOptions
0x1800178ce  mov     [rsp+2A0h+var_258], rsi
0x1800178d3  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\ADs\\Providers\\II"...
0x1800178da  mov     [rsp+2A0h+var_250], rsi
0x1800178df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800178e6  mov     [rsp+2A0h+cchName], esi
0x1800178ea  mov     ebx, esi
0x1800178ec  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800178f1  call    cs:__imp_RegOpenKeyExW
0x1800178f7  test    eax, eax
0x1800178f9  jnz     loc_1800179E8
0x1800178ff  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180017904  lea     rax, [rsp+2A0h+var_258]
0x180017909  mov     r9d, 20019h; samDesired
0x18001790f  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180017914  xor     r8d, r8d; ulOptions
0x180017917  lea     rdx, aExtensions; "Extensions"
0x18001791e  call    cs:__imp_RegOpenKeyExW
0x180017924  test    eax, eax
0x180017926  jnz     loc_1800179E8
0x18001792c  xor     edx, edx; Val
0x18001792e  lea     rcx, [rsp+2A0h+SubKey]; void *
0x180017933  mov     r8d, 208h; Size
0x180017939  mov     edi, esi
0x18001793b  call    memset_0
0x180017940  xor     edx, edx
0x180017942  jmp     short loc_1800179AF
0x180017944  mov     rcx, [rsp+2A0h+var_258]; hKey
0x180017949  lea     rax, [rsp+2A0h+var_250]
0x18001794e  mov     r9d, 20019h; samDesired
0x180017954  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180017959  xor     r8d, r8d; ulOptions
0x18001795c  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x180017961  call    cs:__imp_RegOpenKeyExW
0x180017967  test    eax, eax
0x180017969  jnz     short loc_1800179E8
0x18001796b  mov     rdx, [rsp+2A0h+var_250]; hKey
0x180017970  lea     rcx, [rsp+2A0h+SubKey]; Source
0x180017975  call    ?BuildClassEntry@@YAPEAU_class_entry@@PEAGPEAUHKEY__@@@Z; BuildClassEntry(ushort *,HKEY__ *)
0x18001797a  test    rax, rax
0x18001797d  jz      short loc_180017989
0x18001797f  mov     [rax+210h], rbx
0x180017986  mov     rbx, rax
0x180017989  mov     rcx, [rsp+2A0h+var_250]; hKey
0x18001798e  test    rcx, rcx
0x180017991  jz      short loc_180017999
0x180017993  call    cs:__imp_RegCloseKey
0x180017999  xor     edx, edx; Val
0x18001799b  lea     rcx, [rsp+2A0h+SubKey]; void *
0x1800179a0  mov     r8d, 208h; Size
0x1800179a6  call    memset_0
0x1800179ab  inc     edi
0x1800179ad  mov     edx, edi; dwIndex
0x1800179af  mov     rcx, [rsp+2A0h+var_258]; hKey
0x1800179b4  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x1800179b9  mov     [rsp+2A0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800179be  lea     r8, [rsp+2A0h+SubKey]; lpName
0x1800179c3  mov     [rsp+2A0h+lpcchClass], rsi; lpcchClass
0x1800179c8  mov     [rsp+2A0h+lpClass], rsi; lpClass
0x1800179cd  mov     [rsp+2A0h+phkResult], rsi; lpReserved
0x1800179d2  mov     [rsp+2A0h+cchName], 104h
0x1800179da  call    cs:__imp_RegEnumKeyExW
0x1800179e0  test    eax, eax
0x1800179e2  jz      loc_180017944
0x1800179e8  mov     rcx, [rsp+2A0h+var_258]; hKey
0x1800179ed  test    rcx, rcx
0x1800179f0  jz      short loc_1800179F8
0x1800179f2  call    cs:__imp_RegCloseKey
0x1800179f8  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800179fd  test    rcx, rcx
0x180017a00  jz      short loc_180017A08
0x180017a02  call    cs:__imp_RegCloseKey
0x180017a08  mov     rax, rbx
0x180017a0b  mov     rcx, [rbp+1A0h+var_30]
0x180017a12  xor     rcx, rsp; StackCookie
0x180017a15  call    __security_check_cookie
0x180017a1a  add     rsp, 288h
0x180017a21  pop     rdi
0x180017a22  pop     rsi
0x180017a23  pop     rbx
0x180017a24  pop     rbp
0x180017a25  retn
```
