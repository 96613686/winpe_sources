# Microsoft::Applications::Events::FIFOFileStorage::Open(char const *,unsigned __int64,unsigned __int64)

- ea: `0x140154bd0`
- end: `0x140154e11`
- name: `?Open@FIFOFileStorage@Events@Applications@Microsoft@@UEAAHPEBD_K1@Z`
- size: `577`
- prototype: `__int64 __fastcall(Microsoft::Applications::Events::FIFOFileStorage *__hidden this, const char *, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400630b4`
- `0x140063430`
- `0x14008e9a8`
- `0x1400ff188`
- `0x140154bd0`
- `0x140155090`
- `0x14015516c`
- `0x1401554c4`
- `0x14015601c`

## string_xrefs

- `0x140154c7e`: `open file [%s], size = %d, block size = %u`
- `0x140154cbf`: `open file with size 0, use default size instead`
- `0x140154c03`: `open file failed, path passed is nullptr`
- `0x140154c1b`: `file already has been opened`
- `0x140154ddc`: `open file [%s] suc`

## pseudocode

```c
__int64 __fastcall Microsoft::Applications::Events::FIFOFileStorage::Open(
        Microsoft::Applications::Events::FIFOFileStorage *this,
        const char *a2,
        unsigned __int64 a3,
        __int64 a4)
{
  __int64 v5; // rsi
  const char *v9; // r14
  FILE *v10; // rax
  bool v11; // dl

  v5 = a3;
  if ( !a2 )
  {
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        1,
        "MATSDK",
        "open file failed, path passed is nullptr");
    return 0xFFFFFFFFLL;
  }
  if ( *((_DWORD *)this + 12) != 2 )
  {
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(1, "MATSDK", "file already has been opened");
    return 0xFFFFFFFFLL;
  }
  if ( a3 > 0x6400000 )
  {
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
    {
      _mm_lfence();
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        1,
        "MATSDK",
        "file size is too big, limit file size is = %u",
        a3);
    }
    return 0xFFFFFFFFLL;
  }
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
  {
    _mm_lfence();
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "MATSDK",
      "open file [%s], size = %d, block size = %u",
      a2,
      a3,
      a4);
  }
  v9 = (char *)this + 16;
  std::string::operator=((char *)this + 16);
  *((_QWORD *)this + 7) = a4;
  if ( !v5 )
  {
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        4,
        "MATSDK",
        "open file with size 0, use default size instead");
    v5 = 0x200000;
  }
  *((_QWORD *)this + 17) = v5;
  if ( *((_QWORD *)this + 5) > 0xFu )
    v9 = *(const char **)v9;
  v10 = fopen(v9, "r+b");
  *((_QWORD *)this + 1) = v10;
  if ( !v10 )
  {
    v11 = 0;
    return Microsoft::Applications::Events::FIFOFileStorage::RecreateFile(this, v11);
  }
  *((_DWORD *)this + 12) = 0;
  rewind(v10);
  if ( Microsoft::Applications::Events::FIFOFileStorage::Read(this, (char *)this + 104, 0x20u) )
  {
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
    {
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        1,
        "MATSDK",
        "wrie file header failed, headerLength=%d",
        32);
      goto LABEL_29;
    }
    goto LABEL_31;
  }
  if ( (unsigned int)Microsoft::Applications::Events::FIFOFileStorage::VerifyFileChecksum(this) )
  {
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
    {
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(1, "MATSDK", "VerifyFileChecksum failed");
LABEL_29:
      if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
        Microsoft::Applications::Events::PlatformAbstraction::detail::log(
          1,
          "MATSDK",
          "offline data file exist, but load file header failed, truncating...");
    }
LABEL_31:
    v11 = 1;
    return Microsoft::Applications::Events::FIFOFileStorage::RecreateFile(this, v11);
  }
  if ( (unsigned int)Microsoft::Applications::Events::FIFOFileStorage::ReadFileInfo(this) )
  {
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        1,
        "MATSDK",
        "offline data file exist, but load file info failed, truncating...");
    goto LABEL_31;
  }
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(4, "MATSDK", "open file [%s] suc", a2);
  return 0;
}

```

## disassembly

```asm
0x140154bd0  mov     rax, rsp
0x140154bd3  mov     [rax+8], rbp
0x140154bd7  mov     [rax+10h], rsi
0x140154bdb  mov     [rax+18h], rdi
0x140154bdf  mov     [rax+20h], r14
0x140154be3  push    r15
0x140154be5  sub     rsp, 30h
0x140154be9  mov     r15, r9
0x140154bec  mov     rsi, r8
0x140154bef  mov     rbp, rdx
0x140154bf2  mov     rdi, rcx
0x140154bf5  test    rdx, rdx
0x140154bf8  jnz     short loc_140154C0C
0x140154bfa  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 1; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140154c01  jl      short loc_140154C65
0x140154c03  lea     r8, aOpenFileFailed; "open file failed, path passed is nullpt"...
0x140154c0a  jmp     short loc_140154C22
0x140154c0c  cmp     dword ptr [rcx+30h], 2
0x140154c10  jz      short loc_140154C35
0x140154c12  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 1; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140154c19  jl      short loc_140154C65
0x140154c1b  lea     r8, aFileAlreadyHas; "file already has been opened"
0x140154c22  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x140154c29  mov     ecx, 1
0x140154c2e  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140154c33  jmp     short loc_140154C65
0x140154c35  cmp     rsi, 6400000h
0x140154c3c  jbe     short loc_140154C6D
0x140154c3e  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 1; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140154c45  jl      short loc_140154C65
0x140154c47  lfence
0x140154c4a  mov     r9, rsi
0x140154c4d  lea     r8, aFileSizeIsTooB; "file size is too big, limit file size i"...
0x140154c54  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x140154c5b  mov     ecx, 1
0x140154c60  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140154c65  or      eax, 0FFFFFFFFh
0x140154c68  jmp     loc_140154DF6
0x140154c6d  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 4; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140154c74  jl      short loc_140154C9E
0x140154c76  lfence
0x140154c79  mov     [rsp+38h+var_10], r15
0x140154c7e  lea     r8, aOpenFileSSizeD; "open file [%s], size = %d, block size ="...
0x140154c85  mov     r9, rbp
0x140154c88  mov     [rsp+38h+var_18], rsi
0x140154c8d  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x140154c94  mov     ecx, 4
0x140154c99  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140154c9e  lea     r14, [rdi+10h]
0x140154ca2  mov     rdx, rbp
0x140154ca5  mov     rcx, r14; void *
0x140154ca8  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator=(char const * const)
0x140154cad  mov     [rdi+38h], r15
0x140154cb1  test    rsi, rsi
0x140154cb4  jnz     short loc_140154CDA
0x140154cb6  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 4; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140154cbd  jl      short loc_140154CD5
0x140154cbf  lea     r8, aOpenFileWithSi; "open file with size 0, use default size"...
0x140154cc6  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x140154ccd  lea     ecx, [rsi+4]
0x140154cd0  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140154cd5  mov     esi, 200000h
0x140154cda  mov     [rdi+88h], rsi
0x140154ce1  cmp     qword ptr [r14+18h], 0Fh
0x140154ce6  jbe     short loc_140154CEB
0x140154ce8  mov     r14, [r14]
0x140154ceb  lea     rdx, Mode; "r+b"
0x140154cf2  mov     rcx, r14; FileName
0x140154cf5  call    fopen
0x140154cfa  mov     [rdi+8], rax
0x140154cfe  test    rax, rax
0x140154d01  jnz     short loc_140154D12
0x140154d03  xor     edx, edx; bool
0x140154d05  mov     rcx, rdi; this
0x140154d08  call    ?RecreateFile@FIFOFileStorage@Events@Applications@Microsoft@@AEAAH_N@Z; Microsoft::Applications::Events::FIFOFileStorage::RecreateFile(bool)
0x140154d0d  jmp     loc_140154DF6
0x140154d12  mov     rcx, rax; Stream
0x140154d15  mov     dword ptr [rdi+30h], 0
0x140154d1c  call    rewind
0x140154d21  mov     esi, 20h ; ' '
0x140154d26  lea     rdx, [rdi+68h]; char *
0x140154d2a  mov     r8d, esi; unsigned __int64
0x140154d2d  mov     rcx, rdi; this
0x140154d30  call    ?Read@FIFOFileStorage@Events@Applications@Microsoft@@AEAAHPEAD_K@Z; Microsoft::Applications::Events::FIFOFileStorage::Read(char *,unsigned __int64)
0x140154d35  test    eax, eax
0x140154d37  jz      short loc_140154D5D
0x140154d39  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 1; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140154d40  jl      short loc_140154DAB
0x140154d42  mov     r9d, esi
0x140154d45  lea     r8, aWrieFileHeader; "wrie file header failed, headerLength=%"...
0x140154d4c  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x140154d53  lea     ecx, [rsi-1Fh]
0x140154d56  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140154d5b  jmp     short loc_140154D8A
0x140154d5d  mov     rcx, rdi; this
0x140154d60  call    ?VerifyFileChecksum@FIFOFileStorage@Events@Applications@Microsoft@@AEAAHXZ; Microsoft::Applications::Events::FIFOFileStorage::VerifyFileChecksum(void)
0x140154d65  test    eax, eax
0x140154d67  jz      short loc_140154DB2
0x140154d69  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 1; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140154d70  jl      short loc_140154DAB
0x140154d72  lea     r8, aVerifyfilechec; "VerifyFileChecksum failed"
0x140154d79  mov     ecx, 1
0x140154d7e  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x140154d85  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140154d8a  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 1; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140154d91  jl      short loc_140154DAB
0x140154d93  lea     r8, aOfflineDataFil_0; "offline data file exist, but load file "...
0x140154d9a  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x140154da1  mov     ecx, 1
0x140154da6  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140154dab  mov     dl, 1
0x140154dad  jmp     loc_140154D05
0x140154db2  mov     rcx, rdi; this
0x140154db5  call    ?ReadFileInfo@FIFOFileStorage@Events@Applications@Microsoft@@AEAAHXZ; Microsoft::Applications::Events::FIFOFileStorage::ReadFileInfo(void)
0x140154dba  test    eax, eax
0x140154dbc  jz      short loc_140154DD0
0x140154dbe  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 1; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140154dc5  jl      short loc_140154DAB
0x140154dc7  lea     r8, aOfflineDataFil; "offline data file exist, but load file "...
0x140154dce  jmp     short loc_140154D9A
0x140154dd0  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 4; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140154dd7  jl      short loc_140154DF4
0x140154dd9  mov     r9, rbp
0x140154ddc  lea     r8, aOpenFileSSuc; "open file [%s] suc"
0x140154de3  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x140154dea  mov     ecx, 4
0x140154def  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140154df4  xor     eax, eax
0x140154df6  mov     rbp, [rsp+38h+arg_0]
0x140154dfb  mov     rsi, [rsp+38h+arg_8]
0x140154e00  mov     rdi, [rsp+38h+arg_10]
0x140154e05  mov     r14, [rsp+38h+arg_18]
0x140154e0a  add     rsp, 30h
0x140154e0e  pop     r15
0x140154e10  retn
```
