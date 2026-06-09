# AiInitializeDirectories(void)

- ea: `0x18001cd78`
- end: `0x18001ce14`
- name: `?AiInitializeDirectories@@YAKXZ`
- size: `156`
- prototype: `DWORD(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180028270`

## callees

- `0x18001cd78`
- `0x180040164`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cda1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001cdb1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001cdb1`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18001cdd9`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18001cdd9`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001cd8c`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001cd8c`

## pseudocode

```c
DWORD AiInitializeDirectories(void)
{
  UINT SystemDirectoryW; // eax
  UINT SystemWow64DirectoryW; // eax

  g_cchTempDir = GetTempPath2W(260, &g_wszTempDir);
  if ( !g_cchTempDir )
    return GetLastError();
  SystemDirectoryW = GetSystemDirectoryW(&g_wszSystemDir, 0x104u);
  LODWORD(g_cchSystemDir) = SystemDirectoryW;
  if ( !SystemDirectoryW )
    return GetLastError();
  if ( SystemDirectoryW > 0x104 )
    return 122;
  SystemWow64DirectoryW = GetSystemWow64DirectoryW(&g_wszWow64Dir, 0x104u);
  g_cchWow64Dir = SystemWow64DirectoryW;
  if ( !SystemWow64DirectoryW )
    return GetLastError();
  if ( SystemWow64DirectoryW > 0x104 )
    return 122;
  g_cchDiff = SystemWow64DirectoryW - g_cchSystemDir;
  if ( SystemWow64DirectoryW - (unsigned int)g_cchSystemDir > SystemWow64DirectoryW )
    g_cchDiff = 0;
  return AipInitializeSecureDirectories();
}

```

## disassembly

```asm
0x18001cd78  push    rbx
0x18001cd7a  sub     rsp, 20h
0x18001cd7e  mov     ebx, 104h
0x18001cd83  lea     rdx, ?g_wszTempDir@@3PAGA; ushort near * g_wszTempDir
0x18001cd8a  mov     ecx, ebx
0x18001cd8c  call    cs:__imp_GetTempPath2W
0x18001cd92  mov     cs:?g_cchTempDir@@3KA, eax; ulong g_cchTempDir
0x18001cd98  test    eax, eax
0x18001cd9a  jnz     short loc_18001CDA8
0x18001cd9c  add     rsp, 20h
0x18001cda0  pop     rbx
0x18001cda1  jmp     cs:__imp_GetLastError
0x18001cda8  mov     edx, ebx; uSize
0x18001cdaa  lea     rcx, ?g_wszSystemDir@@3PAGA; lpBuffer
0x18001cdb1  call    cs:__imp_GetSystemDirectoryW
0x18001cdb7  mov     cs:?g_cchSystemDir@@3KA, eax; ulong g_cchSystemDir
0x18001cdbd  test    eax, eax
0x18001cdbf  jz      short loc_18001CD9C
0x18001cdc1  cmp     eax, ebx
0x18001cdc3  jbe     short loc_18001CDD0
0x18001cdc5  mov     eax, 7Ah ; 'z'
0x18001cdca  add     rsp, 20h
0x18001cdce  pop     rbx
0x18001cdcf  retn
0x18001cdd0  mov     edx, ebx; uSize
0x18001cdd2  lea     rcx, ?g_wszWow64Dir@@3PAGA; lpBuffer
0x18001cdd9  call    cs:__imp_GetSystemWow64DirectoryW
0x18001cddf  mov     cs:?g_cchWow64Dir@@3KA, eax; ulong g_cchWow64Dir
0x18001cde5  mov     ecx, eax
0x18001cde7  test    eax, eax
0x18001cde9  jz      short loc_18001CD9C
0x18001cdeb  cmp     eax, ebx
0x18001cded  ja      short loc_18001CDC5
0x18001cdef  sub     eax, cs:?g_cchSystemDir@@3KA; ulong g_cchSystemDir
0x18001cdf5  mov     cs:?g_cchDiff@@3KA, eax; ulong g_cchDiff
0x18001cdfb  cmp     eax, ecx
0x18001cdfd  jbe     short loc_18001CE09
0x18001cdff  mov     cs:?g_cchDiff@@3KA, 0; ulong g_cchDiff
0x18001ce09  call    ?AipInitializeSecureDirectories@@YAKXZ; AipInitializeSecureDirectories(void)
0x18001ce0e  add     rsp, 20h
0x18001ce12  pop     rbx
0x18001ce13  retn
```
