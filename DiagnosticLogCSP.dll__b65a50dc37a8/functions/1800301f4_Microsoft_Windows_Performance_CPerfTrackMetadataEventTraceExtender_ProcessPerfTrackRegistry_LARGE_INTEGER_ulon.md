# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)

- ea: `0x1800301f4`
- end: `0x18003040c`
- name: `?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `536`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f450`

## callees

- `0x180001b90`
- `0x18001629c`
- `0x18002f704`
- `0x18002f9f8`
- `0x1800301f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800303bb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800303bb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800302c7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800302c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030399`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800303d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030399`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800303d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030263`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030318`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030263`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030318`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        int a3,
        int a4)
{
  DWORD LowPart; // ebx
  int v7; // r15d
  LSTATUS v8; // eax
  HKEY v9; // rdi
  DWORD v10; // esi
  LSTATUS v11; // r14d
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+58h] [rbp-A8h]
  HKEY v17[3]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v18; // [rsp+78h] [rbp-88h]
  __int64 v19; // [rsp+80h] [rbp-80h]
  __int64 v20; // [rsp+88h] [rbp-78h]
  WCHAR Name[128]; // [rsp+90h] [rbp-70h] BYREF

  LowPart = a2.LowPart;
  v7 = (int)this;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  hKey = 0;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\PerfTrack\\InteractionClasses",
         0,
         0x20019u,
         &hKey);
  if ( v8 )
    return ATL::AtlHresultFromWin32(v8);
  v9 = hKey;
  v18 = hKey;
  Block = 0;
  v16 = 0;
  v10 = 0;
  do
  {
    LODWORD(hKey) = 128;
    ftLastWriteTime = 0;
    v11 = RegEnumKeyExW(v9, v10, Name, (LPDWORD)&hKey, 0, 0, 0, &ftLastWriteTime);
    if ( !v11 && (unsigned int)hKey < 0x80 )
    {
      v17[1] = 0;
      v17[2] = 0;
      ftLastWriteTime = 0;
      if ( !RegOpenKeyExW(v9, Name, 0, 0x20019u, (PHKEY)&ftLastWriteTime) )
      {
        v17[0] = (HKEY)ftLastWriteTime;
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV0(
          v7,
          LowPart,
          a3,
          a4,
          (ATL::CRegKey *)v17,
          (__int64)Name,
          (__int64)&Block);
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(
          v7,
          LowPart,
          a3,
          a4,
          (__int64)v17,
          (__int64)Name,
          (__int64)&Block);
        if ( v17[0] )
          RegCloseKey(v17[0]);
      }
    }
    ++v10;
  }
  while ( v11 != 259 );
  free(Block);
  if ( v9 )
    RegCloseKey(v9);
  return 0;
}

```

## disassembly

```asm
0x1800301f4  push    rbp
0x1800301f6  push    rbx
0x1800301f7  push    rsi
0x1800301f8  push    rdi
0x1800301f9  push    r12
0x1800301fb  push    r13
0x1800301fd  push    r14
0x1800301ff  push    r15
0x180030201  lea     rbp, [rsp-0A8h]
0x180030209  sub     rsp, 1A8h
0x180030210  mov     rax, cs:__security_cookie
0x180030217  xor     rax, rsp
0x18003021a  mov     [rbp+0E0h+var_50], rax
0x180030221  mov     r13d, r9d
0x180030224  mov     r12d, r8d
0x180030227  mov     rbx, rdx
0x18003022a  mov     r15, rcx
0x18003022d  xor     r14d, r14d
0x180030230  mov     [rsp+1E0h+var_168], r14
0x180030235  mov     [rbp+0E0h+var_160], r14
0x180030239  mov     [rbp+0E0h+var_158], r14
0x18003023d  mov     [rsp+1E0h+hKey], r14
0x180030242  lea     rax, [rsp+1E0h+hKey]
0x180030247  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18003024c  mov     r9d, 20019h; samDesired
0x180030252  xor     r8d, r8d; ulOptions
0x180030255  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003025c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030263  call    cs:__imp_RegOpenKeyExW
0x18003026a  nop     dword ptr [rax+rax+00h]
0x18003026f  test    eax, eax
0x180030271  jnz     loc_1800303E0
0x180030277  mov     rdi, [rsp+1E0h+hKey]
0x18003027c  mov     [rsp+1E0h+var_168], rdi
0x180030281  mov     [rsp+1E0h+Block], r14
0x180030286  mov     [rsp+1E0h+var_188], r14d
0x18003028b  mov     esi, r14d
0x18003028e  jmp     short loc_180030293
0x180030290  xor     r14d, r14d
0x180030293  mov     dword ptr [rsp+1E0h+hKey], 80h
0x18003029b  mov     qword ptr [rsp+1E0h+ftLastWriteTime.dwLowDateTime], r14
0x1800302a0  lea     rax, [rsp+1E0h+ftLastWriteTime]
0x1800302a5  mov     [rsp+1E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800302aa  mov     [rsp+1E0h+lpcchClass], r14; lpcchClass
0x1800302af  mov     [rsp+1E0h+lpClass], r14; lpClass
0x1800302b4  mov     [rsp+1E0h+phkResult], r14; lpReserved
0x1800302b9  lea     r9, [rsp+1E0h+hKey]; lpcchName
0x1800302be  lea     r8, [rbp+0E0h+Name]; lpName
0x1800302c2  mov     edx, esi; dwIndex
0x1800302c4  mov     rcx, rdi; hKey
0x1800302c7  call    cs:__imp_RegEnumKeyExW
0x1800302ce  nop     dword ptr [rax+rax+00h]
0x1800302d3  mov     r14d, eax
0x1800302d6  xor     eax, eax
0x1800302d8  test    r14d, r14d
0x1800302db  jnz     loc_1800303A7
0x1800302e1  cmp     dword ptr [rsp+1E0h+hKey], 80h
0x1800302e9  jnb     loc_1800303A7
0x1800302ef  mov     [rsp+1E0h+var_178], rax
0x1800302f4  mov     [rsp+1E0h+var_170], rax
0x1800302f9  mov     qword ptr [rsp+1E0h+ftLastWriteTime.dwLowDateTime], rax
0x1800302fe  lea     rax, [rsp+1E0h+ftLastWriteTime]
0x180030303  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180030308  mov     r9d, 20019h; samDesired
0x18003030e  xor     r8d, r8d; ulOptions
0x180030311  lea     rdx, [rbp+0E0h+Name]; lpSubKey
0x180030315  mov     rcx, rdi; hKey
0x180030318  call    cs:__imp_RegOpenKeyExW
0x18003031f  nop     dword ptr [rax+rax+00h]
0x180030324  test    eax, eax
0x180030326  jnz     short loc_1800303A7
0x180030328  mov     rax, qword ptr [rsp+1E0h+ftLastWriteTime.dwLowDateTime]
0x18003032d  mov     [rsp+1E0h+var_180], rax
0x180030332  lea     rax, [rsp+1E0h+Block]
0x180030337  mov     [rsp+1E0h+lpcchClass], rax; __int64
0x18003033c  lea     rax, [rbp+0E0h+Name]
0x180030340  mov     [rsp+1E0h+lpClass], rax; __int64
0x180030345  lea     rax, [rsp+1E0h+var_180]
0x18003034a  mov     [rsp+1E0h+phkResult], rax; ATL::CRegKey *
0x18003034f  mov     r9d, r13d; int
0x180030352  mov     r8d, r12d; int
0x180030355  mov     rdx, rbx; int
0x180030358  mov     rcx, r15; int
0x18003035b  call    ?ProcessInteractionClassV0@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV0(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x180030360  lea     rax, [rsp+1E0h+Block]
0x180030365  mov     [rsp+1E0h+lpcchClass], rax
0x18003036a  lea     rax, [rbp+0E0h+Name]
0x18003036e  mov     [rsp+1E0h+lpClass], rax
0x180030373  lea     rax, [rsp+1E0h+var_180]
0x180030378  mov     [rsp+1E0h+phkResult], rax
0x18003037d  mov     r9d, r13d
0x180030380  mov     r8d, r12d
0x180030383  mov     rdx, rbx
0x180030386  mov     rcx, r15
0x180030389  call    ?ProcessInteractionClassV1@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x18003038e  nop
0x18003038f  mov     rcx, [rsp+1E0h+var_180]; hKey
0x180030394  test    rcx, rcx
0x180030397  jz      short loc_1800303A7
0x180030399  call    cs:__imp_RegCloseKey
0x1800303a0  nop     dword ptr [rax+rax+00h]
0x1800303a5  jmp     short $+2
0x1800303a7  inc     esi
0x1800303a9  cmp     r14d, 103h
0x1800303b0  jnz     loc_180030290
0x1800303b6  mov     rcx, [rsp+1E0h+Block]; Block
0x1800303bb  call    cs:__imp_free
0x1800303c2  nop     dword ptr [rax+rax+00h]
0x1800303c7  nop
0x1800303c8  test    rdi, rdi
0x1800303cb  jz      short loc_1800303DC
0x1800303cd  mov     rcx, rdi; hKey
0x1800303d0  call    cs:__imp_RegCloseKey
0x1800303d7  nop     dword ptr [rax+rax+00h]
0x1800303dc  xor     eax, eax
0x1800303de  jmp     short loc_1800303E8
0x1800303e0  mov     ecx, eax; unsigned int
0x1800303e2  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800303e7  nop
0x1800303e8  mov     rcx, [rbp+0E0h+var_50]
0x1800303ef  xor     rcx, rsp; StackCookie
0x1800303f2  call    __security_check_cookie
0x1800303f7  add     rsp, 1A8h
0x1800303fe  pop     r15
0x180030400  pop     r14
0x180030402  pop     r13
0x180030404  pop     r12
0x180030406  pop     rdi
0x180030407  pop     rsi
0x180030408  pop     rbx
0x180030409  pop     rbp
0x18003040a  retn
```
