# RegSubKeyExists(HKEY__ *,ushort const *,ushort const *,int *)

- ea: `0x180034dbc`
- end: `0x180034ed2`
- name: `?RegSubKeyExists@@YAKPEAUHKEY__@@PEBG1PEAH@Z`
- size: `278`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004a414`

## callees

- `0x180034dbc`
- `0x18004aa08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034e3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034e89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034e3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034e89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034eaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034eba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034eaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034eba`

## string_xrefs

- `0x180034e10`: `%s: parentKeyPath should not be null.`
- `0x180034e52`: `RegOpenKeyExW`

## pseudocode

```c
__int64 __fastcall RegSubKeyExists(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int *a4)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !a4 )
  {
    Logger::TraceError(L"%s: pbExists should not be null.", L"RegSubKeyExists");
LABEL_3:
    v6 = 87;
    goto LABEL_15;
  }
  *a4 = 0;
  if ( !a2 )
  {
    Logger::TraceError(L"%s: parentKeyPath should not be null.", L"RegSubKeyExists");
    goto LABEL_3;
  }
  if ( !a3 )
  {
    Logger::TraceError((const unsigned __int16 *)&::hKey, L"RegSubKeyExists");
    goto LABEL_3;
  }
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v6 = v7;
  if ( v7 == 2 )
    goto LABEL_9;
  if ( v7 )
    goto LABEL_11;
  v7 = RegOpenKeyExW(hKey, a3, 0, 0x20019u, &phkResult);
  v6 = v7;
  if ( v7 == 2 )
  {
LABEL_9:
    v6 = 0;
    goto LABEL_15;
  }
  if ( v7 )
LABEL_11:
    Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"RegSubKeyExists", L"RegOpenKeyExW", v7);
  else
    *a4 = 1;
LABEL_15:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180034dbc  mov     rax, rsp
0x180034dbf  mov     [rax+8], rbx
0x180034dc3  mov     [rax+10h], rsi
0x180034dc7  push    rdi
0x180034dc8  sub     rsp, 40h
0x180034dcc  mov     qword ptr [rax+20h], 0
0x180034dd4  mov     rdi, r9
0x180034dd7  mov     qword ptr [rax-18h], 0
0x180034ddf  mov     rsi, r8
0x180034de2  test    r9, r9
0x180034de5  jnz     short loc_180034E04
0x180034de7  lea     rcx, aSPbexistsShoul; "%s: pbExists should not be null."
0x180034dee  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x180034df5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180034dfa  mov     ebx, 57h ; 'W'
0x180034dff  jmp     loc_180034EA0
0x180034e04  mov     dword ptr [r9], 0
0x180034e0b  test    rdx, rdx
0x180034e0e  jnz     short loc_180034E19
0x180034e10  lea     rcx, aSParentkeypath; "%s: parentKeyPath should not be null."
0x180034e17  jmp     short loc_180034DEE
0x180034e19  test    rsi, rsi
0x180034e1c  jnz     short loc_180034E27
0x180034e1e  lea     rcx, hKey; hKey
0x180034e25  jmp     short loc_180034DEE
0x180034e27  lea     rax, [rsp+48h+hKey]
0x180034e2c  mov     r9d, 20019h; samDesired
0x180034e32  xor     r8d, r8d; ulOptions
0x180034e35  mov     [rsp+48h+phkResult], rax; phkResult
0x180034e3a  call    cs:__imp_RegOpenKeyExW
0x180034e40  mov     ebx, eax
0x180034e42  cmp     eax, 2
0x180034e45  jnz     short loc_180034E4B
0x180034e47  xor     ebx, ebx
0x180034e49  jmp     short loc_180034EA0
0x180034e4b  test    eax, eax
0x180034e4d  jz      short loc_180034E6E
0x180034e4f  mov     r9d, eax
0x180034e52  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x180034e59  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x180034e60  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180034e67  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180034e6c  jmp     short loc_180034EA0
0x180034e6e  mov     rcx, [rsp+48h+hKey]; hKey
0x180034e73  lea     rax, [rsp+48h+var_18]
0x180034e78  mov     r9d, 20019h; samDesired
0x180034e7e  mov     [rsp+48h+phkResult], rax; phkResult
0x180034e83  xor     r8d, r8d; ulOptions
0x180034e86  mov     rdx, rsi; lpSubKey
0x180034e89  call    cs:__imp_RegOpenKeyExW
0x180034e8f  mov     ebx, eax
0x180034e91  cmp     eax, 2
0x180034e94  jz      short loc_180034E47
0x180034e96  test    eax, eax
0x180034e98  jnz     short loc_180034E4F
0x180034e9a  mov     dword ptr [rdi], 1
0x180034ea0  mov     rcx, [rsp+48h+var_18]; hKey
0x180034ea5  test    rcx, rcx
0x180034ea8  jz      short loc_180034EB0
0x180034eaa  call    cs:__imp_RegCloseKey
0x180034eb0  mov     rcx, [rsp+48h+hKey]; hKey
0x180034eb5  test    rcx, rcx
0x180034eb8  jz      short loc_180034EC0
0x180034eba  call    cs:__imp_RegCloseKey
0x180034ec0  mov     rsi, [rsp+48h+arg_8]
0x180034ec5  mov     eax, ebx
0x180034ec7  mov     rbx, [rsp+48h+arg_0]
0x180034ecc  add     rsp, 40h
0x180034ed0  pop     rdi
0x180034ed1  retn
```
