# GetSystemCIPolicyPath(ushort *,uint)

- ea: `0x180003534`
- end: `0x18000359c`
- name: `?GetSystemCIPolicyPath@@YAKPEAGI@Z`
- size: `104`
- prototype: `unsigned int __fastcall(wchar_t *Destination, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003b90`
- `0x180003d30`

## callees

- `0x180003534`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000356b`
- `msvcrt!wcscat_s` at `0x18000356b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003550`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180003546`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180003546`

## string_xrefs

- `0x18000355a`: `\System32\CodeIntegrity\SiPolicy.p7b`

## pseudocode

```c
__int64 __fastcall GetSystemCIPolicyPath(wchar_t *Destination)
{
  unsigned int v2; // ebx
  errno_t v3; // eax

  if ( GetSystemWindowsDirectoryW(Destination, 0x104u) )
  {
    v2 = 0;
    v3 = wcscat_s(Destination, 0x104u, L"\\System32\\CodeIntegrity\\SiPolicy.p7b");
    if ( v3 )
    {
      if ( v3 == 22 )
      {
        return 160;
      }
      else
      {
        v2 = 122;
        if ( v3 != 34 )
          return 87;
      }
    }
  }
  else
  {
    return GetLastError();
  }
  return v2;
}

```

## disassembly

```asm
0x180003534  mov     [rsp+arg_0], rbx
0x180003539  push    rdi
0x18000353a  sub     rsp, 20h
0x18000353e  mov     edx, 104h; uSize
0x180003543  mov     rdi, rcx
0x180003546  call    cs:__imp_GetSystemWindowsDirectoryW
0x18000354c  test    eax, eax
0x18000354e  jnz     short loc_18000355A
0x180003550  call    cs:__imp_GetLastError
0x180003556  mov     ebx, eax
0x180003558  jmp     short loc_18000358F
0x18000355a  lea     r8, aSystem32Codein; "\\System32\\CodeIntegrity\\SiPolicy.p7b"
0x180003561  mov     edx, 104h; SizeInWords
0x180003566  mov     rcx, rdi; Destination
0x180003569  xor     ebx, ebx
0x18000356b  call    cs:__imp_wcscat_s
0x180003571  test    eax, eax
0x180003573  jz      short loc_18000358F
0x180003575  cmp     eax, 16h
0x180003578  jz      short loc_18000358A
0x18000357a  mov     ebx, 7Ah ; 'z'
0x18000357f  cmp     eax, 22h ; '"'
0x180003582  lea     ecx, [rbx-23h]
0x180003585  cmovnz  ebx, ecx
0x180003588  jmp     short loc_18000358F
0x18000358a  mov     ebx, 0A0h
0x18000358f  mov     eax, ebx
0x180003591  mov     rbx, [rsp+28h+arg_0]
0x180003596  add     rsp, 20h
0x18000359a  pop     rdi
0x18000359b  retn
```
