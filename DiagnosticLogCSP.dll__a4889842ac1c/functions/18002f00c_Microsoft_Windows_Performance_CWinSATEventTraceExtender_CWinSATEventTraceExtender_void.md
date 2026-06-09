# Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(void)

- ea: `0x18002f00c`
- end: `0x18002f1f9`
- name: `??0CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `493`
- prototype: `Microsoft::Windows::Performance::CWinSATEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f2e4`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x18002f00c`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f1b9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f1b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f097`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f0c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f107`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f134`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f097`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f0c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f107`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f134`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f0e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f157`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f0e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f157`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002f069`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002f069`

## string_xrefs

- `0x18002f090`: `ntdll.dll`
- `0x18002f0bd`: `ntdll.dll`
- `0x18002f100`: `ntdll.dll`
- `0x18002f12d`: `ntdll.dll`
- `0x18002f150`: `RtlGetCompressionWorkSpaceSize`
- `0x18002f0e0`: `RtlCompressBuffer`

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
  void *v9; // rax
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
     && (v9 = malloc(LODWORD(Size[0])), (*((_QWORD *)this + 7) = v9) != 0)) )
  {
    *((_DWORD *)this + 16) = Size[0];
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
0x18002f00c  mov     [rsp+arg_8], rbx
0x18002f011  push    rdi
0x18002f012  sub     rsp, 160h
0x18002f019  mov     rax, cs:__security_cookie
0x18002f020  xor     rax, rsp
0x18002f023  mov     [rsp+168h+var_18], rax
0x18002f02b  mov     rbx, rcx
0x18002f02e  mov     [rsp+168h+var_140], rcx
0x18002f033  xor     edi, edi
0x18002f035  mov     [rcx+18h], edi
0x18002f038  mov     [rcx+8], rdi
0x18002f03c  mov     [rcx+10h], rdi
0x18002f040  lea     rax, ??_7CWinSATEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CWinSATEventTraceExtender::`vftable'
0x18002f047  mov     [rcx], rax
0x18002f04a  mov     [rsp+168h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18002f052  xor     edx, edx; Val
0x18002f054  mov     r8d, 118h; Size
0x18002f05a  lea     rcx, [rsp+168h+VersionInformation.dwMajorVersion]; void *
0x18002f05f  call    memset_0
0x18002f064  lea     rcx, [rsp+168h+VersionInformation]; lpVersionInformation
0x18002f069  call    cs:__imp_GetVersionExW
0x18002f06f  test    eax, eax
0x18002f071  jz      short loc_18002F07D
0x18002f073  cmp     [rsp+168h+VersionInformation.dwMajorVersion], 6
0x18002f078  mov     al, dil
0x18002f07b  jnb     short loc_18002F07F
0x18002f07d  mov     al, 1
0x18002f07f  mov     [rbx+20h], al
0x18002f082  mov     [rbx+21h], di
0x18002f086  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002f08c  test    al, al
0x18002f08e  jnz     short loc_18002F0AD
0x18002f090  lea     rcx, ModuleName; "ntdll.dll"
0x18002f097  call    cs:__imp_GetModuleHandleW
0x18002f09d  mov     cs:hModule, rax
0x18002f0a4  nop
0x18002f0a5  mov     al, 1
0x18002f0a7  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002f0ad  mov     rcx, cs:hModule
0x18002f0b4  test    rcx, rcx
0x18002f0b7  jz      short loc_18002F0EF
0x18002f0b9  test    al, al
0x18002f0bb  jnz     short loc_18002F0E0
0x18002f0bd  lea     rcx, ModuleName; "ntdll.dll"
0x18002f0c4  call    cs:__imp_GetModuleHandleW
0x18002f0ca  mov     cs:hModule, rax
0x18002f0d1  nop
0x18002f0d2  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002f0d9  mov     rcx, cs:hModule; hModule
0x18002f0e0  lea     rdx, aRtlcompressbuf; "RtlCompressBuffer"
0x18002f0e7  call    cs:__imp_GetProcAddress
0x18002f0ed  jmp     short loc_18002F0F2
0x18002f0ef  mov     rax, rdi
0x18002f0f2  mov     [rbx+28h], rax
0x18002f0f6  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002f0fc  test    al, al
0x18002f0fe  jnz     short loc_18002F11D
0x18002f100  lea     rcx, ModuleName; "ntdll.dll"
0x18002f107  call    cs:__imp_GetModuleHandleW
0x18002f10d  mov     cs:hModule, rax
0x18002f114  nop
0x18002f115  mov     al, 1
0x18002f117  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002f11d  mov     rcx, cs:hModule
0x18002f124  test    rcx, rcx
0x18002f127  jz      short loc_18002F15F
0x18002f129  test    al, al
0x18002f12b  jnz     short loc_18002F150
0x18002f12d  lea     rcx, ModuleName; "ntdll.dll"
0x18002f134  call    cs:__imp_GetModuleHandleW
0x18002f13a  mov     cs:hModule, rax
0x18002f141  nop
0x18002f142  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002f149  mov     rcx, cs:hModule; hModule
0x18002f150  lea     rdx, aRtlgetcompress; "RtlGetCompressionWorkSpaceSize"
0x18002f157  call    cs:__imp_GetProcAddress
0x18002f15d  jmp     short loc_18002F162
0x18002f15f  mov     rax, rdi
0x18002f162  mov     [rbx+30h], rax
0x18002f166  mov     [rbx+38h], rdi
0x18002f16a  mov     [rbx+40h], edi
0x18002f16d  mov     [rbx+48h], rdi
0x18002f171  mov     [rbx+50h], edi
0x18002f174  mov     [rbx+58h], rdi
0x18002f178  mov     [rbx+60h], edi
0x18002f17b  cmp     [rbx+20h], dil
0x18002f17f  jnz     short loc_18002F1D1
0x18002f181  test    rax, rax
0x18002f184  jz      short loc_18002F1D1
0x18002f186  cmp     [rbx+28h], rdi
0x18002f18a  jz      short loc_18002F1D1
0x18002f18c  mov     [rbx+21h], dil
0x18002f190  mov     dword ptr [rsp+168h+Size], edi
0x18002f194  mov     dword ptr [rsp+168h+Size+4], edi
0x18002f198  test    rax, rax
0x18002f19b  jz      short loc_18002F1D1
0x18002f19d  mov     ecx, 102h
0x18002f1a2  lea     r8, [rsp+168h+Size+4]
0x18002f1a7  lea     rdx, [rsp+168h+Size]
0x18002f1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1b1  test    eax, eax
0x18002f1b3  jnz     short loc_18002F1D1
0x18002f1b5  mov     ecx, dword ptr [rsp+168h+Size]; Size
0x18002f1b9  call    cs:__imp_malloc
0x18002f1bf  mov     [rbx+38h], rax
0x18002f1c3  test    rax, rax
0x18002f1c6  jz      short loc_18002F1D1
0x18002f1c8  mov     eax, dword ptr [rsp+168h+Size]
0x18002f1cc  mov     [rbx+40h], eax
0x18002f1cf  jmp     short loc_18002F1D5
0x18002f1d1  mov     byte ptr [rbx+21h], 1
0x18002f1d5  mov     rax, rbx
0x18002f1d8  mov     rcx, [rsp+168h+var_18]
0x18002f1e0  xor     rcx, rsp; StackCookie
0x18002f1e3  call    __security_check_cookie
0x18002f1e8  mov     rbx, [rsp+168h+arg_8]
0x18002f1f0  add     rsp, 160h
0x18002f1f7  pop     rdi
0x18002f1f8  retn
```
