# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(void)

- ea: `0x18002da58`
- end: `0x18002dcd3`
- name: `??0CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `635`
- prototype: `Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__fastcall(unsigned int (__fastcall **this)(__int64, size_t *, int *))`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002df44`

## callees

- `0x180001b60`
- `0x180001b84`
- `0x18000262c`
- `0x18002da58`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002dc90`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002dc90`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002db69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002db92`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002dbd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002dbfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002db69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002db92`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002dbd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002dbfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dbb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dc1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dbb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dc1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002dac0`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002dac0`

## string_xrefs

- `0x18002db55`: `ntdll.dll`
- `0x18002dc16`: `RtlGetCompressionWorkSpaceSize`
- `0x18002dbae`: `RtlCompressBuffer`

## pseudocode

```c
Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(
        unsigned int (__fastcall **this)(__int64, size_t *, int *))
{
  bool v2; // al
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  char v6; // al
  HMODULE v7; // rcx
  FARPROC ProcAddress; // rax
  char v9; // al
  HMODULE v10; // rcx
  FARPROC v11; // rax
  char v12; // al
  unsigned int (__fastcall *v13)(__int64, size_t *, int *); // rax
  unsigned int (__fastcall *v14)(__int64, size_t *, int *); // rax
  size_t Size; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+28h] [rbp-D8h] BYREF
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v18; // [rsp+30h] [rbp-D0h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-C0h] BYREF

  v18 = (Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *)this;
  *((_DWORD *)this + 6) = 0;
  this[1] = 0;
  this[2] = 0;
  *this = (unsigned int (__fastcall *)(__int64, size_t *, int *))&Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::`vftable';
  VersionInformation.dwOSVersionInfoSize = 284;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  v2 = !GetVersionExW(&VersionInformation)
    || VersionInformation.dwMajorVersion <= 6
    && (VersionInformation.dwMajorVersion != 6 || !VersionInformation.dwMinorVersion);
  *((_BYTE *)this + 32) = v2;
  this[5] = 0;
  this[6] = 0;
  v3 = operator new(0x30u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  this[5] = (unsigned int (__fastcall *)(__int64, size_t *, int *))v3;
  this[7] = 0;
  this[8] = 0;
  v4 = operator new(0x30u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  this[7] = (unsigned int (__fastcall *)(__int64, size_t *, int *))v4;
  this[9] = 0;
  this[10] = 0;
  v5 = operator new(0x30u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  this[9] = (unsigned int (__fastcall *)(__int64, size_t *, int *))v5;
  v6 = Performance::RtlCompression::g_hNtDllModule;
  if ( !Performance::RtlCompression::g_hNtDllModule )
  {
    hModule = GetModuleHandleW(L"ntdll.dll");
    v6 = 1;
    Performance::RtlCompression::g_hNtDllModule = 1;
  }
  v7 = hModule;
  if ( hModule )
  {
    if ( !v6 )
    {
      hModule = GetModuleHandleW(L"ntdll.dll");
      Performance::RtlCompression::g_hNtDllModule = 1;
      v7 = hModule;
    }
    ProcAddress = GetProcAddress(v7, "RtlCompressBuffer");
  }
  else
  {
    ProcAddress = 0;
  }
  this[11] = (unsigned int (__fastcall *)(__int64, size_t *, int *))ProcAddress;
  v9 = Performance::RtlCompression::g_hNtDllModule;
  if ( !Performance::RtlCompression::g_hNtDllModule )
  {
    hModule = GetModuleHandleW(L"ntdll.dll");
    v9 = 1;
    Performance::RtlCompression::g_hNtDllModule = 1;
  }
  v10 = hModule;
  if ( hModule )
  {
    if ( !v9 )
    {
      hModule = GetModuleHandleW(L"ntdll.dll");
      Performance::RtlCompression::g_hNtDllModule = 1;
      v10 = hModule;
    }
    v11 = GetProcAddress(v10, "RtlGetCompressionWorkSpaceSize");
  }
  else
  {
    v11 = 0;
  }
  this[12] = (unsigned int (__fastcall *)(__int64, size_t *, int *))v11;
  if ( *((_BYTE *)this + 32) || !v11 || (v12 = 0, !this[11]) )
    v12 = 1;
  *((_BYTE *)this + 104) = v12;
  this[14] = 0;
  *((_DWORD *)this + 30) = 0;
  this[16] = 0;
  *((_DWORD *)this + 34) = 0;
  if ( !*((_BYTE *)this + 104) )
  {
    LODWORD(Size) = 0;
    v17 = 0;
    v13 = this[12];
    if ( v13
      && !v13(258, &Size, &v17)
      && (v14 = (unsigned int (__fastcall *)(__int64, size_t *, int *))malloc((unsigned int)Size), (this[14] = v14) != 0) )
    {
      *((_DWORD *)this + 30) = Size;
    }
    else
    {
      *((_BYTE *)this + 104) = 1;
    }
  }
  return (Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *)this;
}

```

## disassembly

```asm
0x18002da58  mov     [rsp-8+arg_8], rbx
0x18002da5d  mov     [rsp-8+arg_10], rsi
0x18002da62  push    rbp
0x18002da63  push    rdi
0x18002da64  push    r14
0x18002da66  lea     rbp, [rsp-70h]
0x18002da6b  sub     rsp, 170h
0x18002da72  mov     rax, cs:__security_cookie
0x18002da79  xor     rax, rsp
0x18002da7c  mov     [rbp+80h+var_20], rax
0x18002da80  mov     rdi, rcx
0x18002da83  mov     [rsp+180h+var_150], rcx
0x18002da88  xor     r14d, r14d
0x18002da8b  mov     [rcx+18h], r14d
0x18002da8f  mov     [rcx+8], r14
0x18002da93  mov     [rcx+10h], r14
0x18002da97  lea     rax, ??_7CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::`vftable'
0x18002da9e  mov     [rcx], rax
0x18002daa1  mov     [rsp+180h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18002daa9  xor     edx, edx; Val
0x18002daab  mov     r8d, 118h; Size
0x18002dab1  lea     rcx, [rsp+180h+VersionInformation.dwMajorVersion]; void *
0x18002dab6  call    memset_0
0x18002dabb  lea     rcx, [rsp+180h+VersionInformation]; lpVersionInformation
0x18002dac0  call    cs:__imp_GetVersionExW
0x18002dac6  test    eax, eax
0x18002dac8  jz      short loc_18002DADF
0x18002daca  cmp     [rsp+180h+VersionInformation.dwMajorVersion], 6
0x18002dacf  ja      short loc_18002DADA
0x18002dad1  jnz     short loc_18002DADF
0x18002dad3  cmp     [rsp+180h+VersionInformation.dwMinorVersion], 1
0x18002dad8  jb      short loc_18002DADF
0x18002dada  mov     al, r14b
0x18002dadd  jmp     short loc_18002DAE1
0x18002dadf  mov     al, 1
0x18002dae1  mov     [rdi+20h], al
0x18002dae4  mov     [rdi+28h], r14
0x18002dae8  mov     [rdi+30h], r14
0x18002daec  mov     esi, 30h ; '0'
0x18002daf1  mov     ecx, esi; Size
0x18002daf3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002daf8  mov     [rax], rax
0x18002dafb  mov     [rax+8], rax
0x18002daff  mov     [rax+10h], rax
0x18002db03  mov     word ptr [rax+18h], 101h
0x18002db09  mov     [rdi+28h], rax
0x18002db0d  mov     [rdi+38h], r14
0x18002db11  mov     [rdi+40h], r14
0x18002db15  mov     ecx, esi; Size
0x18002db17  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002db1c  mov     [rax], rax
0x18002db1f  mov     [rax+8], rax
0x18002db23  mov     [rax+10h], rax
0x18002db27  mov     word ptr [rax+18h], 101h
0x18002db2d  mov     [rdi+38h], rax
0x18002db31  mov     [rdi+48h], r14
0x18002db35  mov     [rdi+50h], r14
0x18002db39  mov     ecx, esi; Size
0x18002db3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002db40  mov     [rax], rax
0x18002db43  mov     [rax+8], rax
0x18002db47  mov     [rax+10h], rax
0x18002db4b  mov     word ptr [rax+18h], 101h
0x18002db51  mov     [rdi+48h], rax
0x18002db55  lea     rbx, ModuleName; "ntdll.dll"
0x18002db5c  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002db62  test    al, al
0x18002db64  jnz     short loc_18002DB7F
0x18002db66  mov     rcx, rbx; lpModuleName
0x18002db69  call    cs:__imp_GetModuleHandleW
0x18002db6f  mov     cs:hModule, rax
0x18002db76  nop
0x18002db77  mov     al, 1
0x18002db79  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002db7f  mov     rcx, cs:hModule
0x18002db86  test    rcx, rcx
0x18002db89  jz      short loc_18002DBBD
0x18002db8b  test    al, al
0x18002db8d  jnz     short loc_18002DBAE
0x18002db8f  mov     rcx, rbx; lpModuleName
0x18002db92  call    cs:__imp_GetModuleHandleW
0x18002db98  mov     cs:hModule, rax
0x18002db9f  nop
0x18002dba0  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002dba7  mov     rcx, cs:hModule; hModule
0x18002dbae  lea     rdx, aRtlcompressbuf; "RtlCompressBuffer"
0x18002dbb5  call    cs:__imp_GetProcAddress
0x18002dbbb  jmp     short loc_18002DBC0
0x18002dbbd  mov     rax, r14
0x18002dbc0  mov     [rdi+58h], rax
0x18002dbc4  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002dbca  test    al, al
0x18002dbcc  jnz     short loc_18002DBE7
0x18002dbce  mov     rcx, rbx; lpModuleName
0x18002dbd1  call    cs:__imp_GetModuleHandleW
0x18002dbd7  mov     cs:hModule, rax
0x18002dbde  nop
0x18002dbdf  mov     al, 1
0x18002dbe1  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002dbe7  mov     rcx, cs:hModule
0x18002dbee  test    rcx, rcx
0x18002dbf1  jz      short loc_18002DC25
0x18002dbf3  test    al, al
0x18002dbf5  jnz     short loc_18002DC16
0x18002dbf7  mov     rcx, rbx; lpModuleName
0x18002dbfa  call    cs:__imp_GetModuleHandleW
0x18002dc00  mov     cs:hModule, rax
0x18002dc07  nop
0x18002dc08  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002dc0f  mov     rcx, cs:hModule; hModule
0x18002dc16  lea     rdx, aRtlgetcompress; "RtlGetCompressionWorkSpaceSize"
0x18002dc1d  call    cs:__imp_GetProcAddress
0x18002dc23  jmp     short loc_18002DC28
0x18002dc25  mov     rax, r14
0x18002dc28  mov     [rdi+60h], rax
0x18002dc2c  cmp     [rdi+20h], r14b
0x18002dc30  jnz     short loc_18002DC40
0x18002dc32  test    rax, rax
0x18002dc35  jz      short loc_18002DC40
0x18002dc37  cmp     [rdi+58h], r14
0x18002dc3b  mov     al, r14b
0x18002dc3e  jnz     short loc_18002DC42
0x18002dc40  mov     al, 1
0x18002dc42  mov     [rdi+68h], al
0x18002dc45  mov     [rdi+70h], r14
0x18002dc49  mov     [rdi+78h], r14d
0x18002dc4d  mov     [rdi+80h], r14
0x18002dc54  mov     [rdi+88h], r14d
0x18002dc5b  cmp     [rdi+68h], r14b
0x18002dc5f  jnz     short loc_18002DCAC
0x18002dc61  mov     dword ptr [rsp+180h+Size], r14d
0x18002dc66  mov     [rsp+180h+var_158], r14d
0x18002dc6b  mov     rax, [rdi+60h]
0x18002dc6f  test    rax, rax
0x18002dc72  jz      short loc_18002DCA8
0x18002dc74  mov     ecx, 102h
0x18002dc79  lea     r8, [rsp+180h+var_158]
0x18002dc7e  lea     rdx, [rsp+180h+Size]
0x18002dc83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc88  test    eax, eax
0x18002dc8a  jnz     short loc_18002DCA8
0x18002dc8c  mov     ecx, dword ptr [rsp+180h+Size]; Size
0x18002dc90  call    cs:__imp_malloc
0x18002dc96  mov     [rdi+70h], rax
0x18002dc9a  test    rax, rax
0x18002dc9d  jz      short loc_18002DCA8
0x18002dc9f  mov     eax, dword ptr [rsp+180h+Size]
0x18002dca3  mov     [rdi+78h], eax
0x18002dca6  jmp     short loc_18002DCAC
0x18002dca8  mov     byte ptr [rdi+68h], 1
0x18002dcac  mov     rax, rdi
0x18002dcaf  mov     rcx, [rbp+80h+var_20]
0x18002dcb3  xor     rcx, rsp; StackCookie
0x18002dcb6  call    __security_check_cookie
0x18002dcbb  lea     r11, [rsp+180h+var_10]
0x18002dcc3  mov     rbx, [r11+28h]
0x18002dcc7  mov     rsi, [r11+30h]
0x18002dccb  mov     rsp, r11
0x18002dcce  pop     r14
0x18002dcd0  pop     rdi
0x18002dcd1  pop     rbp
0x18002dcd2  retn
```
