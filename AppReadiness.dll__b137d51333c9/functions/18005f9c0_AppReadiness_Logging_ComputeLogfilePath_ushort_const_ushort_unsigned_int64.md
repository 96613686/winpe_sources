# AppReadiness::Logging::ComputeLogfilePath(ushort const *,ushort *,unsigned __int64)

- ea: `0x18005f9c0`
- end: `0x18005fa23`
- name: `?ComputeLogfilePath@Logging@AppReadiness@@YAJPEBGPEAG_K@Z`
- size: `99`
- prototype: `int __fastcall(PCWSTR pszMore, PWSTR pszPath, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18005fb48`
- `0x18005fd40`

## callees

- `0x18005f9c0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18005f9d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18005f9d8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18005f9f6`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18005fa0b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18005f9f6`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18005fa0b`

## pseudocode

```c
int __fastcall AppReadiness::Logging::ComputeLogfilePath(PCWSTR pszMore, PWSTR pszPath, unsigned __int16 *a3)
{
  int result; // eax

  if ( GetWindowsDirectoryW(pszPath, 0x104u) - 1 > 0x102 )
    return -2147024774;
  result = PathCchAppend(pszPath, 0x104u, L"Logs");
  if ( result >= 0 )
    return PathCchAppend(pszPath, 0x104u, pszMore);
  return result;
}

```

## disassembly

```asm
0x18005f9c0  mov     [rsp+arg_0], rbx
0x18005f9c5  push    rdi
0x18005f9c6  sub     rsp, 20h
0x18005f9ca  mov     rbx, rdx
0x18005f9cd  mov     rdi, rcx
0x18005f9d0  mov     rcx, rbx; lpBuffer
0x18005f9d3  mov     edx, 104h; uSize
0x18005f9d8  call    cs:__imp_GetWindowsDirectoryW
0x18005f9de  dec     eax
0x18005f9e0  cmp     eax, 102h
0x18005f9e5  ja      short loc_18005FA13
0x18005f9e7  lea     r8, aLogs; "Logs"
0x18005f9ee  mov     edx, 104h; cchPath
0x18005f9f3  mov     rcx, rbx; pszPath
0x18005f9f6  call    cs:__imp_PathCchAppend
0x18005f9fc  test    eax, eax
0x18005f9fe  js      short loc_18005FA18
0x18005fa00  mov     r8, rdi; pszMore
0x18005fa03  mov     edx, 104h; cchPath
0x18005fa08  mov     rcx, rbx; pszPath
0x18005fa0b  call    cs:__imp_PathCchAppend
0x18005fa11  jmp     short loc_18005FA18
0x18005fa13  mov     eax, 8007007Ah
0x18005fa18  mov     rbx, [rsp+28h+arg_0]
0x18005fa1d  add     rsp, 20h
0x18005fa21  pop     rdi
0x18005fa22  retn
```
