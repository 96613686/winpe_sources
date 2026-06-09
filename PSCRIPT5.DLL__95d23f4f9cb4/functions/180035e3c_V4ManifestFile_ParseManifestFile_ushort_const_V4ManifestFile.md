# V4ManifestFile::ParseManifestFile(ushort const *,V4ManifestFile * *)

- ea: `0x180035e3c`
- end: `0x180035f43`
- name: `?ParseManifestFile@V4ManifestFile@@SAJPEBGPEAPEAU1@@Z`
- size: `263`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct V4ManifestFile **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180033ecc`

## callees

- `0x180002498`
- `0x18000298c`
- `0x180035e3c`
- `0x180035f4c`
- `0x180036984`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180035e5e`
- `KERNEL32!GetFileAttributesW` at `0x180035e5e`

## string_xrefs

- `0x180035ecd`: `DriverConfig`
- `0x180035e6c`: `Driver manifest file not found: %ws`
- `0x180035e73`: `V4ManifestFile::ParseManifestFile`

## pseudocode

```c
__int64 __fastcall V4ManifestFile::ParseManifestFile(LPCWSTR lpFileName, struct V4ManifestFile **a2)
{
  int v4; // esi
  struct V4ManifestFile *v5; // rdi
  unsigned int i; // ecx
  __int64 v7; // rax
  unsigned int j; // ebp
  __int64 v9; // rbx

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
      v5 = (struct V4ManifestFile *)operator new(0xA0u, (const struct std::nothrow_t *)byte_18006C430);
      if ( v5 )
      {
        for ( i = 0; i < 0x14; ++i )
        {
          v7 = (int)i;
          *(_QWORD *)((char *)v5 + *((_QWORD *)&V4ManifestFile::s_manifestFields + 3 * v7 + 2)) = 0;
        }
        v4 = V4ManifestFile::ParseManifestSection(L"DriverConfig", lpFileName, v5);
        if ( v4 < 0 || (v4 = V4ManifestFile::ParseManifestSection(L"BidiFiles", lpFileName, v5), v4 < 0) )
        {
          for ( j = 0; j < 0x14; ++j )
          {
            v9 = *((_QWORD *)&V4ManifestFile::s_manifestFields + 3 * (int)j + 2);
            operator delete(*(void **)((char *)v5 + v9));
            *(_QWORD *)((char *)v5 + v9) = 0;
          }
          operator delete(v5);
        }
        else
        {
          *a2 = v5;
        }
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
0x180035e3c  push    rbx
0x180035e3e  push    rbp
0x180035e3f  push    rsi
0x180035e40  push    rdi
0x180035e41  push    r14
0x180035e43  push    r15
0x180035e45  sub     rsp, 28h
0x180035e49  mov     r14, rdx
0x180035e4c  mov     rbx, rcx
0x180035e4f  test    rdx, rdx
0x180035e52  jnz     short loc_180035E5E
0x180035e54  mov     esi, 80070057h
0x180035e59  jmp     loc_180035F34
0x180035e5e  call    cs:__imp_GetFileAttributesW
0x180035e64  cmp     eax, 0FFFFFFFFh
0x180035e67  jnz     short loc_180035E89
0x180035e69  mov     r8, rbx
0x180035e6c  lea     rdx, aDriverManifest; "Driver manifest file not found: %ws"
0x180035e73  lea     rcx, aV4manifestfile; "V4ManifestFile::ParseManifestFile"
0x180035e7a  call    ?WriteDbgTraceWarning@PrintUtilTelemetry@@SAXPEBDPEBGZZ; PrintUtilTelemetry::WriteDbgTraceWarning(char const *,ushort const *,...)
0x180035e7f  mov     esi, 80070002h
0x180035e84  jmp     loc_180035F34
0x180035e89  lea     rdx, byte_18006C430; struct std::nothrow_t *
0x180035e90  mov     ecx, 0A0h; unsigned __int64
0x180035e95  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035e9a  mov     rdi, rax
0x180035e9d  test    rax, rax
0x180035ea0  jz      loc_180035F2F
0x180035ea6  xor     ecx, ecx
0x180035ea8  lea     r15, ?s_manifestFields@V4ManifestFile@@0QBUManifestFieldToParse@1@B; V4ManifestFile::ManifestFieldToParse const near * const V4ManifestFile::s_manifestFields
0x180035eaf  movsxd  rax, ecx
0x180035eb2  inc     ecx
0x180035eb4  lea     rax, [rax+rax*2]
0x180035eb8  mov     rax, [r15+rax*8+10h]
0x180035ebd  mov     qword ptr [rdi+rax], 0
0x180035ec5  cmp     ecx, 14h
0x180035ec8  jb      short loc_180035EAF
0x180035eca  mov     r8, rdi; struct V4ManifestFile *
0x180035ecd  lea     rcx, aDriverconfig; "DriverConfig"
0x180035ed4  mov     rdx, rbx; lpFileName
0x180035ed7  call    ?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z; V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)
0x180035edc  mov     esi, eax
0x180035ede  test    eax, eax
0x180035ee0  js      short loc_180035EFF
0x180035ee2  mov     r8, rdi; struct V4ManifestFile *
0x180035ee5  lea     rcx, aBidifiles; "BidiFiles"
0x180035eec  mov     rdx, rbx; lpFileName
0x180035eef  call    ?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z; V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)
0x180035ef4  mov     esi, eax
0x180035ef6  test    eax, eax
0x180035ef8  js      short loc_180035EFF
0x180035efa  mov     [r14], rdi
0x180035efd  jmp     short loc_180035F34
0x180035eff  xor     ebp, ebp
0x180035f01  movsxd  rax, ebp
0x180035f04  lea     rdx, [rax+rax*2]
0x180035f08  mov     rbx, [r15+rdx*8+10h]
0x180035f0d  mov     rcx, [rbx+rdi]; Block
0x180035f11  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035f16  inc     ebp
0x180035f18  mov     qword ptr [rbx+rdi], 0
0x180035f20  cmp     ebp, 14h
0x180035f23  jb      short loc_180035F01
0x180035f25  mov     rcx, rdi; Block
0x180035f28  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035f2d  jmp     short loc_180035F34
0x180035f2f  mov     esi, 8007000Eh
0x180035f34  mov     eax, esi
0x180035f36  add     rsp, 28h
0x180035f3a  pop     r15
0x180035f3c  pop     r14
0x180035f3e  pop     rdi
0x180035f3f  pop     rsi
0x180035f40  pop     rbp
0x180035f41  pop     rbx
0x180035f42  retn
```
