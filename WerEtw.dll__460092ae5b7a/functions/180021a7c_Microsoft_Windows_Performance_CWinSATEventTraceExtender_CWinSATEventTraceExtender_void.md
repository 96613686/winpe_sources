# Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(void)

- ea: `0x180021a7c`
- end: `0x180021c66`
- name: `??0CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `490`
- prototype: `Microsoft::Windows::Performance::CWinSATEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021d44`

## callees

- `0x180001870`
- `0x1800023e4`
- `0x180002420`
- `0x180021a7c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180021ade`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180021ade`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021b0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021b38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021b77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021ba0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021b0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021b38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021b77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021ba0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021b5b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021bc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021b5b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021bc3`

## string_xrefs

- `0x180021afb`: `ntdll.dll`
- `0x180021bbc`: `RtlGetCompressionWorkSpaceSize`
- `0x180021b54`: `RtlCompressBuffer`

## pseudocode

```c
Microsoft::Windows::Performance::CWinSATEventTraceExtender *__fastcall Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this)
{
  char v2; // al
  char v3; // al
  HMODULE v4; // rcx
  FARPROC ProcAddress; // rax
  char v6; // al
  HMODULE v7; // rcx
  FARPROC v8; // rax
  int v9; // edi
  void *v10; // rax
  size_t Size[2]; // [rsp+20h] [rbp-148h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+30h] [rbp-138h] BYREF

  Size[1] = (size_t)this;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CWinSATEventTraceExtender::`vftable';
  VersionInformation.dwOSVersionInfoSize = 284;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  if ( !GetVersionExW(&VersionInformation) || (v2 = 0, VersionInformation.dwMajorVersion < 6) )
    v2 = 1;
  *((_BYTE *)this + 32) = v2;
  *(_WORD *)((char *)this + 33) = 0;
  v3 = Performance::RtlCompression::g_hNtDllModule;
  if ( !Performance::RtlCompression::g_hNtDllModule )
  {
    hModule = GetModuleHandleW(L"ntdll.dll");
    v3 = 1;
    Performance::RtlCompression::g_hNtDllModule = 1;
  }
  v4 = hModule;
  if ( hModule )
  {
    if ( !v3 )
    {
      hModule = GetModuleHandleW(L"ntdll.dll");
      Performance::RtlCompression::g_hNtDllModule = 1;
      v4 = hModule;
    }
    ProcAddress = GetProcAddress(v4, "RtlCompressBuffer");
  }
  else
  {
    ProcAddress = 0;
  }
  *((_QWORD *)this + 5) = ProcAddress;
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
    v8 = GetProcAddress(v7, "RtlGetCompressionWorkSpaceSize");
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 6) = v8;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  if ( !*((_BYTE *)this + 32)
    && v8
    && *((_QWORD *)this + 5)
    && (*((_BYTE *)this + 33) = 0,
        Size[0] = 0,
        !((unsigned int (__fastcall *)(__int64, size_t *, char *))v8)(258, Size, (char *)Size + 4)
     && (v9 = Size[0], v10 = o_malloc_0(LODWORD(Size[0])), (*((_QWORD *)this + 7) = v10) != 0)) )
  {
    *((_DWORD *)this + 16) = v9;
  }
  else
  {
    *((_BYTE *)this + 33) = 1;
  }
  return this;
}

```

## disassembly

```asm
0x180021a7c  mov     [rsp+arg_8], rbx
0x180021a81  mov     [rsp+arg_10], rsi
0x180021a86  push    rdi
0x180021a87  sub     rsp, 160h
0x180021a8e  mov     rax, cs:__security_cookie
0x180021a95  xor     rax, rsp
0x180021a98  mov     [rsp+168h+var_18], rax
0x180021aa0  mov     rbx, rcx
0x180021aa3  mov     [rsp+168h+var_140], rcx
0x180021aa8  xor     esi, esi
0x180021aaa  mov     [rcx+18h], esi
0x180021aad  mov     [rcx+8], rsi
0x180021ab1  mov     [rcx+10h], rsi
0x180021ab5  lea     rax, ??_7CWinSATEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CWinSATEventTraceExtender::`vftable'
0x180021abc  mov     [rcx], rax
0x180021abf  mov     [rsp+168h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180021ac7  xor     edx, edx; Val
0x180021ac9  mov     r8d, 118h; Size
0x180021acf  lea     rcx, [rsp+168h+VersionInformation.dwMajorVersion]; void *
0x180021ad4  call    memset_0
0x180021ad9  lea     rcx, [rsp+168h+VersionInformation]; lpVersionInformation
0x180021ade  call    cs:__imp_GetVersionExW
0x180021ae4  test    eax, eax
0x180021ae6  jz      short loc_180021AF2
0x180021ae8  cmp     [rsp+168h+VersionInformation.dwMajorVersion], 6
0x180021aed  mov     al, sil
0x180021af0  jnb     short loc_180021AF4
0x180021af2  mov     al, 1
0x180021af4  mov     [rbx+20h], al
0x180021af7  mov     [rbx+21h], si
0x180021afb  lea     rdi, LibFileName; "ntdll.dll"
0x180021b02  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180021b08  test    al, al
0x180021b0a  jnz     short loc_180021B25
0x180021b0c  mov     rcx, rdi; lpModuleName
0x180021b0f  call    cs:__imp_GetModuleHandleW
0x180021b15  mov     cs:hModule, rax
0x180021b1c  nop
0x180021b1d  mov     al, 1
0x180021b1f  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180021b25  mov     rcx, cs:hModule
0x180021b2c  test    rcx, rcx
0x180021b2f  jz      short loc_180021B63
0x180021b31  test    al, al
0x180021b33  jnz     short loc_180021B54
0x180021b35  mov     rcx, rdi; lpModuleName
0x180021b38  call    cs:__imp_GetModuleHandleW
0x180021b3e  mov     cs:hModule, rax
0x180021b45  nop
0x180021b46  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180021b4d  mov     rcx, cs:hModule; hModule
0x180021b54  lea     rdx, aRtlcompressbuf; "RtlCompressBuffer"
0x180021b5b  call    cs:__imp_GetProcAddress
0x180021b61  jmp     short loc_180021B66
0x180021b63  mov     rax, rsi
0x180021b66  mov     [rbx+28h], rax
0x180021b6a  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180021b70  test    al, al
0x180021b72  jnz     short loc_180021B8D
0x180021b74  mov     rcx, rdi; lpModuleName
0x180021b77  call    cs:__imp_GetModuleHandleW
0x180021b7d  mov     cs:hModule, rax
0x180021b84  nop
0x180021b85  mov     al, 1
0x180021b87  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180021b8d  mov     rcx, cs:hModule
0x180021b94  test    rcx, rcx
0x180021b97  jz      short loc_180021BCB
0x180021b99  test    al, al
0x180021b9b  jnz     short loc_180021BBC
0x180021b9d  mov     rcx, rdi; lpModuleName
0x180021ba0  call    cs:__imp_GetModuleHandleW
0x180021ba6  mov     cs:hModule, rax
0x180021bad  nop
0x180021bae  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180021bb5  mov     rcx, cs:hModule; hModule
0x180021bbc  lea     rdx, aRtlgetcompress; "RtlGetCompressionWorkSpaceSize"
0x180021bc3  call    cs:__imp_GetProcAddress
0x180021bc9  jmp     short loc_180021BCE
0x180021bcb  mov     rax, rsi
0x180021bce  mov     [rbx+30h], rax
0x180021bd2  mov     [rbx+38h], rsi
0x180021bd6  mov     [rbx+40h], esi
0x180021bd9  mov     [rbx+48h], rsi
0x180021bdd  mov     [rbx+50h], esi
0x180021be0  mov     [rbx+58h], rsi
0x180021be4  mov     [rbx+60h], esi
0x180021be7  cmp     [rbx+20h], sil
0x180021beb  jnz     short loc_180021C3A
0x180021bed  test    rax, rax
0x180021bf0  jz      short loc_180021C3A
0x180021bf2  cmp     [rbx+28h], rsi
0x180021bf6  jz      short loc_180021C3A
0x180021bf8  mov     [rbx+21h], sil
0x180021bfc  mov     dword ptr [rsp+168h+Size], esi
0x180021c00  mov     dword ptr [rsp+168h+Size+4], esi
0x180021c04  test    rax, rax
0x180021c07  jz      short loc_180021C3A
0x180021c09  mov     ecx, 102h
0x180021c0e  lea     r8, [rsp+168h+Size+4]
0x180021c13  lea     rdx, [rsp+168h+Size]
0x180021c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c1d  test    eax, eax
0x180021c1f  jnz     short loc_180021C3A
0x180021c21  mov     edi, dword ptr [rsp+168h+Size]
0x180021c25  mov     ecx, edi; Size
0x180021c27  call    _o_malloc_0
0x180021c2c  mov     [rbx+38h], rax
0x180021c30  test    rax, rax
0x180021c33  jz      short loc_180021C3A
0x180021c35  mov     [rbx+40h], edi
0x180021c38  jmp     short loc_180021C3E
0x180021c3a  mov     byte ptr [rbx+21h], 1
0x180021c3e  mov     rax, rbx
0x180021c41  mov     rcx, [rsp+168h+var_18]
0x180021c49  xor     rcx, rsp; StackCookie
0x180021c4c  call    __security_check_cookie
0x180021c51  lea     r11, [rsp+168h+var_8]
0x180021c59  mov     rbx, [r11+18h]
0x180021c5d  mov     rsi, [r11+20h]
0x180021c61  mov     rsp, r11
0x180021c64  pop     rdi
0x180021c65  retn
```
