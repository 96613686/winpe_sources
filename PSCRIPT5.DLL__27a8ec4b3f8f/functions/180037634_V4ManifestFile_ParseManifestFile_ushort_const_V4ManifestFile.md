# V4ManifestFile::ParseManifestFile(ushort const *,V4ManifestFile * *)

- ea: `0x180037634`
- end: `0x180037742`
- name: `?ParseManifestFile@V4ManifestFile@@SAJPEBGPEAPEAU1@@Z`
- size: `270`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct V4ManifestFile **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800355d0`

## callees

- `0x1800024d8`
- `0x1800029ec`
- `0x180037634`
- `0x180037748`
- `0x1800381f4`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180037656`
- `KERNEL32!GetFileAttributesW` at `0x180037656`

## string_xrefs

- `0x1800376cb`: `DriverConfig`
- `0x18003766a`: `Driver manifest file not found: %ws`
- `0x180037671`: `V4ManifestFile::ParseManifestFile`

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
        (wchar_t *)L"Driver manifest file not found: %ws",
        lpFileName);
      return (unsigned int)-2147024894;
    }
    else
    {
      v5 = (struct V4ManifestFile *)operator new(0xA0u, (const struct std::nothrow_t *)byte_18006E400);
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
0x180037634  push    rbx
0x180037636  push    rbp
0x180037637  push    rsi
0x180037638  push    rdi
0x180037639  push    r14
0x18003763b  push    r15
0x18003763d  sub     rsp, 28h
0x180037641  mov     r14, rdx
0x180037644  mov     rbx, rcx
0x180037647  test    rdx, rdx
0x18003764a  jnz     short loc_180037656
0x18003764c  mov     esi, 80070057h
0x180037651  jmp     loc_180037732
0x180037656  call    cs:__imp_GetFileAttributesW
0x18003765d  nop     dword ptr [rax+rax+00h]
0x180037662  cmp     eax, 0FFFFFFFFh
0x180037665  jnz     short loc_180037687
0x180037667  mov     r8, rbx
0x18003766a  lea     rdx, aDriverManifest; "Driver manifest file not found: %ws"
0x180037671  lea     rcx, aV4manifestfile; "V4ManifestFile::ParseManifestFile"
0x180037678  call    ?WriteDbgTraceWarning@PrintUtilTelemetry@@SAXPEBDPEBGZZ; PrintUtilTelemetry::WriteDbgTraceWarning(char const *,ushort const *,...)
0x18003767d  mov     esi, 80070002h
0x180037682  jmp     loc_180037732
0x180037687  lea     rdx, byte_18006E400; struct std::nothrow_t *
0x18003768e  mov     ecx, 0A0h; unsigned __int64
0x180037693  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180037698  mov     rdi, rax
0x18003769b  test    rax, rax
0x18003769e  jz      loc_18003772D
0x1800376a4  xor     ecx, ecx
0x1800376a6  lea     r15, ?s_manifestFields@V4ManifestFile@@0QBUManifestFieldToParse@1@B; V4ManifestFile::ManifestFieldToParse const near * const V4ManifestFile::s_manifestFields
0x1800376ad  movsxd  rax, ecx
0x1800376b0  inc     ecx
0x1800376b2  lea     rax, [rax+rax*2]
0x1800376b6  mov     rax, [r15+rax*8+10h]
0x1800376bb  mov     qword ptr [rdi+rax], 0
0x1800376c3  cmp     ecx, 14h
0x1800376c6  jb      short loc_1800376AD
0x1800376c8  mov     r8, rdi; struct V4ManifestFile *
0x1800376cb  lea     rcx, aDriverconfig; "DriverConfig"
0x1800376d2  mov     rdx, rbx; lpFileName
0x1800376d5  call    ?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z; V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)
0x1800376da  mov     esi, eax
0x1800376dc  test    eax, eax
0x1800376de  js      short loc_1800376FD
0x1800376e0  mov     r8, rdi; struct V4ManifestFile *
0x1800376e3  lea     rcx, aBidifiles; "BidiFiles"
0x1800376ea  mov     rdx, rbx; lpFileName
0x1800376ed  call    ?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z; V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)
0x1800376f2  mov     esi, eax
0x1800376f4  test    eax, eax
0x1800376f6  js      short loc_1800376FD
0x1800376f8  mov     [r14], rdi
0x1800376fb  jmp     short loc_180037732
0x1800376fd  xor     ebp, ebp
0x1800376ff  movsxd  rax, ebp
0x180037702  lea     rdx, [rax+rax*2]
0x180037706  mov     rbx, [r15+rdx*8+10h]
0x18003770b  mov     rcx, [rbx+rdi]; Block
0x18003770f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037714  inc     ebp
0x180037716  mov     qword ptr [rbx+rdi], 0
0x18003771e  cmp     ebp, 14h
0x180037721  jb      short loc_1800376FF
0x180037723  mov     rcx, rdi; Block
0x180037726  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003772b  jmp     short loc_180037732
0x18003772d  mov     esi, 8007000Eh
0x180037732  mov     eax, esi
0x180037734  add     rsp, 28h
0x180037738  pop     r15
0x18003773a  pop     r14
0x18003773c  pop     rdi
0x18003773d  pop     rsi
0x18003773e  pop     rbp
0x18003773f  pop     rbx
0x180037740  retn
```
