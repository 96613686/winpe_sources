# GetFirefoxSqliteDllPath(ushort *,ushort *,ulong)

- ea: `0x18001ed08`
- end: `0x18001ed52`
- name: `?GetFirefoxSqliteDllPath@@YAJPEAG0K@Z`
- size: `74`
- prototype: `int(unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000c3a0`
- `0x18001f30c`

## callees

- `0x18001ed08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed21`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ed46`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ed46`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ed17`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ed17`

## string_xrefs

- `0x18001ed37`: `nss3.dll`

## pseudocode

```c
int __fastcall GetFirefoxSqliteDllPath(unsigned __int16 *a1, unsigned __int16 *a2)
{
  int result; // eax
  bool v4; // sf

  if ( ExpandEnvironmentStringsW(a1, a2, 0x104u) )
    return PathCchAppend(a2, 0x104u, L"nss3.dll");
  result = GetLastError();
  v4 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v4 = result < 0;
  }
  if ( !v4 )
    return PathCchAppend(a2, 0x104u, L"nss3.dll");
  return result;
}

```

## disassembly

```asm
0x18001ed08  push    rbx
0x18001ed0a  sub     rsp, 20h
0x18001ed0e  mov     r8d, 104h; nSize
0x18001ed14  mov     rbx, rdx
0x18001ed17  call    cs:__imp_ExpandEnvironmentStringsW
0x18001ed1d  test    eax, eax
0x18001ed1f  jnz     short loc_18001ED37
0x18001ed21  call    cs:__imp_GetLastError
0x18001ed27  test    eax, eax
0x18001ed29  jle     short loc_18001ED35
0x18001ed2b  movzx   eax, ax
0x18001ed2e  or      eax, 80070000h
0x18001ed33  test    eax, eax
0x18001ed35  js      short loc_18001ED4C
0x18001ed37  lea     r8, aNss3Dll; "nss3.dll"
0x18001ed3e  mov     edx, 104h; cchPath
0x18001ed43  mov     rcx, rbx; pszPath
0x18001ed46  call    cs:__imp_PathCchAppend
0x18001ed4c  add     rsp, 20h
0x18001ed50  pop     rbx
0x18001ed51  retn
```
