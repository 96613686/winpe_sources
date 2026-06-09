# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(void)

- ea: `0x180020508`
- end: `0x180020768`
- name: `??0CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `608`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800209b4`

## callees

- `0x180001870`
- `0x1800018a0`
- `0x1800023e4`
- `0x180002420`
- `0x180020508`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180020564`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180020564`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002060d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020636`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020675`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002069e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002060d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020636`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020675`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002069e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020659`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800206c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020659`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800206c1`

## string_xrefs

- `0x1800205f9`: `ntdll.dll`
- `0x1800206ba`: `RtlGetCompressionWorkSpaceSize`
- `0x180020652`: `RtlCompressBuffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  int v14; // ebx
  unsigned int (__fastcall *v15)(__int64, size_t *, int *); // rax
  size_t Size; // [rsp+20h] [rbp-178h] BYREF
  int v18; // [rsp+28h] [rbp-170h] BYREF
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v19; // [rsp+30h] [rbp-168h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-158h] BYREF

  v19 = (Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *)this;
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
    v18 = 0;
    v13 = this[12];
    if ( v13
      && !v13(258, &Size, &v18)
      && (v14 = Size,
          v15 = (unsigned int (__fastcall *)(__int64, size_t *, int *))o_malloc_0((unsigned int)Size),
          (this[14] = v15) != 0) )
    {
      *((_DWORD *)this + 30) = v14;
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
0x180020508  push    rbx
0x18002050a  push    rbp
0x18002050b  push    rsi
0x18002050c  push    rdi
0x18002050d  sub     rsp, 178h
0x180020514  mov     rax, cs:__security_cookie
0x18002051b  xor     rax, rsp
0x18002051e  mov     [rsp+198h+var_38], rax
0x180020526  mov     rdi, rcx
0x180020529  mov     [rsp+198h+var_168], rcx
0x18002052e  xor     ebp, ebp
0x180020530  mov     [rcx+18h], ebp
0x180020533  mov     [rcx+8], rbp
0x180020537  mov     [rcx+10h], rbp
0x18002053b  lea     rax, ??_7CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::`vftable'
0x180020542  mov     [rcx], rax
0x180020545  mov     [rsp+198h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18002054d  xor     edx, edx; Val
0x18002054f  mov     r8d, 118h; Size
0x180020555  lea     rcx, [rsp+198h+VersionInformation.dwMajorVersion]; void *
0x18002055a  call    memset_0
0x18002055f  lea     rcx, [rsp+198h+VersionInformation]; lpVersionInformation
0x180020564  call    cs:__imp_GetVersionExW
0x18002056a  test    eax, eax
0x18002056c  jz      short loc_180020583
0x18002056e  cmp     [rsp+198h+VersionInformation.dwMajorVersion], 6
0x180020573  ja      short loc_18002057E
0x180020575  jnz     short loc_180020583
0x180020577  cmp     [rsp+198h+VersionInformation.dwMinorVersion], 1
0x18002057c  jb      short loc_180020583
0x18002057e  mov     al, bpl
0x180020581  jmp     short loc_180020585
0x180020583  mov     al, 1
0x180020585  mov     [rdi+20h], al
0x180020588  mov     [rdi+28h], rbp
0x18002058c  mov     [rdi+30h], rbp
0x180020590  mov     esi, 30h ; '0'
0x180020595  mov     ecx, esi; Size
0x180020597  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002059c  mov     [rax], rax
0x18002059f  mov     [rax+8], rax
0x1800205a3  mov     [rax+10h], rax
0x1800205a7  mov     word ptr [rax+18h], 101h
0x1800205ad  mov     [rdi+28h], rax
0x1800205b1  mov     [rdi+38h], rbp
0x1800205b5  mov     [rdi+40h], rbp
0x1800205b9  mov     ecx, esi; Size
0x1800205bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800205c0  mov     [rax], rax
0x1800205c3  mov     [rax+8], rax
0x1800205c7  mov     [rax+10h], rax
0x1800205cb  mov     word ptr [rax+18h], 101h
0x1800205d1  mov     [rdi+38h], rax
0x1800205d5  mov     [rdi+48h], rbp
0x1800205d9  mov     [rdi+50h], rbp
0x1800205dd  mov     ecx, esi; Size
0x1800205df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800205e4  mov     [rax], rax
0x1800205e7  mov     [rax+8], rax
0x1800205eb  mov     [rax+10h], rax
0x1800205ef  mov     word ptr [rax+18h], 101h
0x1800205f5  mov     [rdi+48h], rax
0x1800205f9  lea     rbx, LibFileName; "ntdll.dll"
0x180020600  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180020606  test    al, al
0x180020608  jnz     short loc_180020623
0x18002060a  mov     rcx, rbx; lpModuleName
0x18002060d  call    cs:__imp_GetModuleHandleW
0x180020613  mov     cs:hModule, rax
0x18002061a  nop
0x18002061b  mov     al, 1
0x18002061d  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180020623  mov     rcx, cs:hModule
0x18002062a  test    rcx, rcx
0x18002062d  jz      short loc_180020661
0x18002062f  test    al, al
0x180020631  jnz     short loc_180020652
0x180020633  mov     rcx, rbx; lpModuleName
0x180020636  call    cs:__imp_GetModuleHandleW
0x18002063c  mov     cs:hModule, rax
0x180020643  nop
0x180020644  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002064b  mov     rcx, cs:hModule; hModule
0x180020652  lea     rdx, aRtlcompressbuf; "RtlCompressBuffer"
0x180020659  call    cs:__imp_GetProcAddress
0x18002065f  jmp     short loc_180020664
0x180020661  mov     rax, rbp
0x180020664  mov     [rdi+58h], rax
0x180020668  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002066e  test    al, al
0x180020670  jnz     short loc_18002068B
0x180020672  mov     rcx, rbx; lpModuleName
0x180020675  call    cs:__imp_GetModuleHandleW
0x18002067b  mov     cs:hModule, rax
0x180020682  nop
0x180020683  mov     al, 1
0x180020685  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002068b  mov     rcx, cs:hModule
0x180020692  test    rcx, rcx
0x180020695  jz      short loc_1800206C9
0x180020697  test    al, al
0x180020699  jnz     short loc_1800206BA
0x18002069b  mov     rcx, rbx; lpModuleName
0x18002069e  call    cs:__imp_GetModuleHandleW
0x1800206a4  mov     cs:hModule, rax
0x1800206ab  nop
0x1800206ac  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x1800206b3  mov     rcx, cs:hModule; hModule
0x1800206ba  lea     rdx, aRtlgetcompress; "RtlGetCompressionWorkSpaceSize"
0x1800206c1  call    cs:__imp_GetProcAddress
0x1800206c7  jmp     short loc_1800206CC
0x1800206c9  mov     rax, rbp
0x1800206cc  mov     [rdi+60h], rax
0x1800206d0  cmp     [rdi+20h], bpl
0x1800206d4  jnz     short loc_1800206E4
0x1800206d6  test    rax, rax
0x1800206d9  jz      short loc_1800206E4
0x1800206db  cmp     [rdi+58h], rbp
0x1800206df  mov     al, bpl
0x1800206e2  jnz     short loc_1800206E6
0x1800206e4  mov     al, 1
0x1800206e6  mov     [rdi+68h], al
0x1800206e9  mov     [rdi+70h], rbp
0x1800206ed  mov     [rdi+78h], ebp
0x1800206f0  mov     [rdi+80h], rbp
0x1800206f7  mov     [rdi+88h], ebp
0x1800206fd  cmp     [rdi+68h], bpl
0x180020701  jnz     short loc_180020749
0x180020703  mov     dword ptr [rsp+198h+Size], ebp
0x180020707  mov     [rsp+198h+var_170], ebp
0x18002070b  mov     rax, [rdi+60h]
0x18002070f  test    rax, rax
0x180020712  jz      short loc_180020745
0x180020714  mov     ecx, 102h
0x180020719  lea     r8, [rsp+198h+var_170]
0x18002071e  lea     rdx, [rsp+198h+Size]
0x180020723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020728  test    eax, eax
0x18002072a  jnz     short loc_180020745
0x18002072c  mov     ebx, dword ptr [rsp+198h+Size]
0x180020730  mov     ecx, ebx; Size
0x180020732  call    _o_malloc_0
0x180020737  mov     [rdi+70h], rax
0x18002073b  test    rax, rax
0x18002073e  jz      short loc_180020745
0x180020740  mov     [rdi+78h], ebx
0x180020743  jmp     short loc_180020749
0x180020745  mov     byte ptr [rdi+68h], 1
0x180020749  mov     rax, rdi
0x18002074c  mov     rcx, [rsp+198h+var_38]
0x180020754  xor     rcx, rsp; StackCookie
0x180020757  call    __security_check_cookie
0x18002075c  add     rsp, 178h
0x180020763  pop     rdi
0x180020764  pop     rsi
0x180020765  pop     rbp
0x180020766  pop     rbx
0x180020767  retn
```
