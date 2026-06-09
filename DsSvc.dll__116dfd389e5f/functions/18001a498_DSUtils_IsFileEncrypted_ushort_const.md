# DSUtils::IsFileEncrypted(ushort const *)

- ea: `0x18001a498`
- end: `0x18001a511`
- name: `?IsFileEncrypted@DSUtils@@YAHPEBG@Z`
- size: `121`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ca4c`
- `0x18000d3e4`
- `0x18000f740`
- `0x180013d40`

## callees

- `0x180006f78`
- `0x18000c040`
- `0x18001a498`
- `0x18001afe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4c5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a4b2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a4b2`

## string_xrefs

- `0x18001a4db`: `Failed to get attributes for filepath %s. hr=0x%x`

## pseudocode

```c
__int64 __fastcall DSUtils::IsFileEncrypted(LPCWSTR lpFileName, const unsigned __int16 *a2)
{
  DWORD FileAttributesW; // eax
  __int64 v4; // rcx
  int *v5; // rdi
  signed int LastError; // eax

  if ( !lpFileName )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW != -1 )
    return (FileAttributesW >> 14) & 1;
  v5 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v4);
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  DSLogger::LogInformation(
    (DSLogger *)v5,
    L"DSUtils::IsFileEncrypted",
    262,
    L"Failed to get attributes for filepath %s. hr=0x%x",
    lpFileName,
    LastError);
  return 0;
}

```

## disassembly

```asm
0x18001a498  mov     [rsp+arg_0], rbx
0x18001a49d  push    rdi
0x18001a49e  sub     rsp, 30h
0x18001a4a2  mov     rbx, rcx
0x18001a4a5  test    rcx, rcx
0x18001a4a8  jnz     short loc_18001A4AF
0x18001a4aa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a4af  mov     rcx, rbx; lpFileName
0x18001a4b2  call    cs:__imp_GetFileAttributesW
0x18001a4b8  cmp     eax, 0FFFFFFFFh
0x18001a4bb  jnz     short loc_18001A500
0x18001a4bd  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001a4c2  mov     rdi, rax
0x18001a4c5  call    cs:__imp_GetLastError
0x18001a4cb  test    eax, eax
0x18001a4cd  jle     short loc_18001A4D7
0x18001a4cf  movzx   eax, ax
0x18001a4d2  or      eax, 80070000h
0x18001a4d7  mov     [rsp+38h+var_10], eax
0x18001a4db  lea     r9, aFailedToGetAtt; "Failed to get attributes for filepath %"...
0x18001a4e2  mov     r8d, 106h; unsigned int
0x18001a4e8  mov     [rsp+38h+var_18], rbx
0x18001a4ed  lea     rdx, aDsutilsIsfilee; "DSUtils::IsFileEncrypted"
0x18001a4f4  mov     rcx, rdi; this
0x18001a4f7  call    ?LogInformation@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)
0x18001a4fc  xor     eax, eax
0x18001a4fe  jmp     short loc_18001A506
0x18001a500  shr     eax, 0Eh
0x18001a503  and     eax, 1
0x18001a506  mov     rbx, [rsp+38h+arg_0]
0x18001a50b  add     rsp, 30h
0x18001a50f  pop     rdi
0x18001a510  retn
```
