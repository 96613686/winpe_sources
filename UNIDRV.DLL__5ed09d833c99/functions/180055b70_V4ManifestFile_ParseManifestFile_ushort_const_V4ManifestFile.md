# V4ManifestFile::ParseManifestFile(ushort const *,V4ManifestFile * *)

- ea: `0x180055b70`
- end: `0x180055c31`
- name: `?ParseManifestFile@V4ManifestFile@@SAJPEBGPEAPEAU1@@Z`
- size: `193`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct V4ManifestFile **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18002d79c`

## callees

- `0x18003f67c`
- `0x18004a728`
- `0x180052f98`
- `0x180055b70`
- `0x180056e70`
- `0x180057e2c`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180055b8f`
- `KERNEL32!GetFileAttributesW` at `0x180055b8f`

## string_xrefs

- `0x180055be3`: `DriverConfig`
- `0x180055ba3`: `Driver manifest file not found: %ws`
- `0x180055baa`: `V4ManifestFile::ParseManifestFile`

## pseudocode

```c
__int64 __fastcall V4ManifestFile::ParseManifestFile(LPCWSTR lpFileName, struct V4ManifestFile **a2)
{
  int v4; // edi
  V4ManifestFile *v5; // rax
  struct V4ManifestFile *v6; // rbx

  if ( a2 )
  {
    if ( GetFileAttributesW(lpFileName) == -1 )
    {
      PrintUtilTelemetry::WriteDbgTraceWarning(
        "V4ManifestFile::ParseManifestFile",
        L"Driver manifest file not found: %ws",
        lpFileName);
      return (unsigned int)-2147024894;
    }
    else
    {
      v5 = (V4ManifestFile *)operator new(0xA0u, (const struct std::nothrow_t *)byte_180081401);
      v6 = v5;
      if ( v5 )
      {
        V4ManifestFile::ResetManifestFileStructure(v5, 0);
        v4 = V4ManifestFile::ParseManifestSection(L"DriverConfig", lpFileName, v6);
        if ( v4 < 0 || (v4 = V4ManifestFile::ParseManifestSection(L"BidiFiles", lpFileName, v6), v4 < 0) )
          V4ManifestFile::`scalar deleting destructor'(v6);
        else
          *a2 = v6;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180055b70  push    rbx
0x180055b72  push    rsi
0x180055b73  push    rdi
0x180055b74  push    r14
0x180055b76  sub     rsp, 28h
0x180055b7a  mov     r14, rdx
0x180055b7d  mov     rsi, rcx
0x180055b80  test    rdx, rdx
0x180055b83  jnz     short loc_180055B8F
0x180055b85  mov     edi, 80070057h
0x180055b8a  jmp     loc_180055C24
0x180055b8f  call    cs:__imp_GetFileAttributesW
0x180055b96  nop     dword ptr [rax+rax+00h]
0x180055b9b  cmp     eax, 0FFFFFFFFh
0x180055b9e  jnz     short loc_180055BBD
0x180055ba0  mov     r8, rsi
0x180055ba3  lea     rdx, aDriverManifest; "Driver manifest file not found: %ws"
0x180055baa  lea     rcx, aV4manifestfile; "V4ManifestFile::ParseManifestFile"
0x180055bb1  call    ?WriteDbgTraceWarning@PrintUtilTelemetry@@SAXPEBDPEBGZZ; PrintUtilTelemetry::WriteDbgTraceWarning(char const *,ushort const *,...)
0x180055bb6  mov     edi, 80070002h
0x180055bbb  jmp     short loc_180055C24
0x180055bbd  lea     rdx, byte_180081401; struct std::nothrow_t *
0x180055bc4  mov     ecx, 0A0h; unsigned __int64
0x180055bc9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180055bce  mov     rbx, rax
0x180055bd1  test    rax, rax
0x180055bd4  jz      short loc_180055C1F
0x180055bd6  xor     edx, edx; bool
0x180055bd8  mov     rcx, rax; this
0x180055bdb  call    ?ResetManifestFileStructure@V4ManifestFile@@AEAAX_N@Z; V4ManifestFile::ResetManifestFileStructure(bool)
0x180055be0  mov     r8, rbx; struct V4ManifestFile *
0x180055be3  lea     rcx, aDriverconfig; "DriverConfig"
0x180055bea  mov     rdx, rsi; lpFileName
0x180055bed  call    ?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z; V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)
0x180055bf2  mov     edi, eax
0x180055bf4  test    eax, eax
0x180055bf6  js      short loc_180055C15
0x180055bf8  mov     r8, rbx; struct V4ManifestFile *
0x180055bfb  lea     rcx, aBidifiles; "BidiFiles"
0x180055c02  mov     rdx, rsi; lpFileName
0x180055c05  call    ?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z; V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)
0x180055c0a  mov     edi, eax
0x180055c0c  test    eax, eax
0x180055c0e  js      short loc_180055C15
0x180055c10  mov     [r14], rbx
0x180055c13  jmp     short loc_180055C24
0x180055c15  mov     rcx, rbx; this
0x180055c18  call    ??_GV4ManifestFile@@QEAAPEAXI@Z; V4ManifestFile::`scalar deleting destructor'(uint)
0x180055c1d  jmp     short loc_180055C24
0x180055c1f  mov     edi, 8007000Eh
0x180055c24  mov     eax, edi
0x180055c26  add     rsp, 28h
0x180055c2a  pop     r14
0x180055c2c  pop     rdi
0x180055c2d  pop     rsi
0x180055c2e  pop     rbx
0x180055c2f  retn
```
