# V4ManifestFile::ParseManifestFile(ushort const *,V4ManifestFile * *)

- ea: `0x180054090`
- end: `0x18005414a`
- name: `?ParseManifestFile@V4ManifestFile@@SAJPEBGPEAPEAU1@@Z`
- size: `186`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct V4ManifestFile **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18002cf28`

## callees

- `0x18003e798`
- `0x1800491e8`
- `0x180051748`
- `0x180054090`
- `0x1800552f0`
- `0x180056360`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800540af`
- `KERNEL32!GetFileAttributesW` at `0x1800540af`

## string_xrefs

- `0x1800540fd`: `DriverConfig`
- `0x1800540bd`: `Driver manifest file not found: %ws`
- `0x1800540c4`: `V4ManifestFile::ParseManifestFile`

## pseudocode

```c
__int64 __fastcall V4ManifestFile::ParseManifestFile(LPCWSTR lpFileName, struct V4ManifestFile **a2)
{
  int v4; // edi
  V4ManifestFile *v5; // rax
  struct V4ManifestFile *v6; // rbx
  unsigned int v7; // edx

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
      v5 = (V4ManifestFile *)operator new(0xA0u, (const struct std::nothrow_t *)byte_18007F401);
      v6 = v5;
      if ( v5 )
      {
        V4ManifestFile::ResetManifestFileStructure(v5, 0);
        v4 = V4ManifestFile::ParseManifestSection(L"DriverConfig", lpFileName, v6);
        if ( v4 < 0 || (v4 = V4ManifestFile::ParseManifestSection(L"BidiFiles", lpFileName, v6), v4 < 0) )
          V4ManifestFile::`scalar deleting destructor'(v6, v7);
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
0x180054090  push    rbx
0x180054092  push    rsi
0x180054093  push    rdi
0x180054094  push    r14
0x180054096  sub     rsp, 28h
0x18005409a  mov     r14, rdx
0x18005409d  mov     rsi, rcx
0x1800540a0  test    rdx, rdx
0x1800540a3  jnz     short loc_1800540AF
0x1800540a5  mov     edi, 80070057h
0x1800540aa  jmp     loc_18005413E
0x1800540af  call    cs:__imp_GetFileAttributesW
0x1800540b5  cmp     eax, 0FFFFFFFFh
0x1800540b8  jnz     short loc_1800540D7
0x1800540ba  mov     r8, rsi
0x1800540bd  lea     rdx, aDriverManifest; "Driver manifest file not found: %ws"
0x1800540c4  lea     rcx, aV4manifestfile; "V4ManifestFile::ParseManifestFile"
0x1800540cb  call    ?WriteDbgTraceWarning@PrintUtilTelemetry@@SAXPEBDPEBGZZ; PrintUtilTelemetry::WriteDbgTraceWarning(char const *,ushort const *,...)
0x1800540d0  mov     edi, 80070002h
0x1800540d5  jmp     short loc_18005413E
0x1800540d7  lea     rdx, byte_18007F401; struct std::nothrow_t *
0x1800540de  mov     ecx, 0A0h; unsigned __int64
0x1800540e3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800540e8  mov     rbx, rax
0x1800540eb  test    rax, rax
0x1800540ee  jz      short loc_180054139
0x1800540f0  xor     edx, edx; bool
0x1800540f2  mov     rcx, rax; this
0x1800540f5  call    ?ResetManifestFileStructure@V4ManifestFile@@AEAAX_N@Z; V4ManifestFile::ResetManifestFileStructure(bool)
0x1800540fa  mov     r8, rbx; struct V4ManifestFile *
0x1800540fd  lea     rcx, aDriverconfig; "DriverConfig"
0x180054104  mov     rdx, rsi; lpFileName
0x180054107  call    ?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z; V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)
0x18005410c  mov     edi, eax
0x18005410e  test    eax, eax
0x180054110  js      short loc_18005412F
0x180054112  mov     r8, rbx; struct V4ManifestFile *
0x180054115  lea     rcx, aBidifiles; "BidiFiles"
0x18005411c  mov     rdx, rsi; lpFileName
0x18005411f  call    ?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z; V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)
0x180054124  mov     edi, eax
0x180054126  test    eax, eax
0x180054128  js      short loc_18005412F
0x18005412a  mov     [r14], rbx
0x18005412d  jmp     short loc_18005413E
0x18005412f  mov     rcx, rbx; this
0x180054132  call    ??_GV4ManifestFile@@QEAAPEAXI@Z; V4ManifestFile::`scalar deleting destructor'(uint)
0x180054137  jmp     short loc_18005413E
0x180054139  mov     edi, 8007000Eh
0x18005413e  mov     eax, edi
0x180054140  add     rsp, 28h
0x180054144  pop     r14
0x180054146  pop     rdi
0x180054147  pop     rsi
0x180054148  pop     rbx
0x180054149  retn
```
