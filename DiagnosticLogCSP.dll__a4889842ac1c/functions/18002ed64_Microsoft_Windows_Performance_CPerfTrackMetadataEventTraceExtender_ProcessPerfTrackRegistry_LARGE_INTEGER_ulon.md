# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002ed64`
- end: `0x18002ef57`
- name: `?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `499`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e020`

## callees

- `0x180001b60`
- `0x180015734`
- `0x18002e2a8`
- `0x18002e568`
- `0x18002ed64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002ef13`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002ef13`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002ee31`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002ee31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eef7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ef22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eef7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ef22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002edd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ee7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002edd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ee7c`

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
0x18002ed64  push    rbp
0x18002ed66  push    rbx
0x18002ed67  push    rsi
0x18002ed68  push    rdi
0x18002ed69  push    r12
0x18002ed6b  push    r13
0x18002ed6d  push    r14
0x18002ed6f  push    r15
0x18002ed71  lea     rbp, [rsp-0A8h]
0x18002ed79  sub     rsp, 1A8h
0x18002ed80  mov     rax, cs:__security_cookie
0x18002ed87  xor     rax, rsp
0x18002ed8a  mov     [rbp+0E0h+var_50], rax
0x18002ed91  mov     r13d, r9d
0x18002ed94  mov     r12d, r8d
0x18002ed97  mov     rbx, rdx
0x18002ed9a  mov     r15, rcx
0x18002ed9d  xor     r14d, r14d
0x18002eda0  mov     [rsp+1E0h+var_168], r14
0x18002eda5  mov     [rbp+0E0h+var_160], r14
0x18002eda9  mov     [rbp+0E0h+var_158], r14
0x18002edad  mov     [rsp+1E0h+hKey], r14
0x18002edb2  lea     rax, [rsp+1E0h+hKey]
0x18002edb7  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18002edbc  mov     r9d, 20019h; samDesired
0x18002edc2  xor     r8d, r8d; ulOptions
0x18002edc5  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002edcc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002edd3  call    cs:__imp_RegOpenKeyExW
0x18002edd9  test    eax, eax
0x18002eddb  jnz     loc_18002EF2C
0x18002ede1  mov     rdi, [rsp+1E0h+hKey]
0x18002ede6  mov     [rsp+1E0h+var_168], rdi
0x18002edeb  mov     [rsp+1E0h+Block], r14
0x18002edf0  mov     [rsp+1E0h+var_188], r14d
0x18002edf5  mov     esi, r14d
0x18002edf8  jmp     short loc_18002EDFD
0x18002edfa  xor     r14d, r14d
0x18002edfd  mov     dword ptr [rsp+1E0h+hKey], 80h
0x18002ee05  mov     qword ptr [rsp+1E0h+ftLastWriteTime.dwLowDateTime], r14
0x18002ee0a  lea     rax, [rsp+1E0h+ftLastWriteTime]
0x18002ee0f  mov     [rsp+1E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18002ee14  mov     [rsp+1E0h+lpcchClass], r14; lpcchClass
0x18002ee19  mov     [rsp+1E0h+lpClass], r14; lpClass
0x18002ee1e  mov     [rsp+1E0h+phkResult], r14; lpReserved
0x18002ee23  lea     r9, [rsp+1E0h+hKey]; lpcchName
0x18002ee28  lea     r8, [rbp+0E0h+Name]; lpName
0x18002ee2c  mov     edx, esi; dwIndex
0x18002ee2e  mov     rcx, rdi; hKey
0x18002ee31  call    cs:__imp_RegEnumKeyExW
0x18002ee37  mov     r14d, eax
0x18002ee3a  xor     eax, eax
0x18002ee3c  test    r14d, r14d
0x18002ee3f  jnz     loc_18002EEFF
0x18002ee45  cmp     dword ptr [rsp+1E0h+hKey], 80h
0x18002ee4d  jnb     loc_18002EEFF
0x18002ee53  mov     [rsp+1E0h+var_178], rax
0x18002ee58  mov     [rsp+1E0h+var_170], rax
0x18002ee5d  mov     qword ptr [rsp+1E0h+ftLastWriteTime.dwLowDateTime], rax
0x18002ee62  lea     rax, [rsp+1E0h+ftLastWriteTime]
0x18002ee67  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18002ee6c  mov     r9d, 20019h; samDesired
0x18002ee72  xor     r8d, r8d; ulOptions
0x18002ee75  lea     rdx, [rbp+0E0h+Name]; lpSubKey
0x18002ee79  mov     rcx, rdi; hKey
0x18002ee7c  call    cs:__imp_RegOpenKeyExW
0x18002ee82  test    eax, eax
0x18002ee84  jnz     short loc_18002EEFF
0x18002ee86  mov     rax, qword ptr [rsp+1E0h+ftLastWriteTime.dwLowDateTime]
0x18002ee8b  mov     [rsp+1E0h+var_180], rax
0x18002ee90  lea     rax, [rsp+1E0h+Block]
0x18002ee95  mov     [rsp+1E0h+lpcchClass], rax; __int64
0x18002ee9a  lea     rax, [rbp+0E0h+Name]
0x18002ee9e  mov     [rsp+1E0h+lpClass], rax; __int64
0x18002eea3  lea     rax, [rsp+1E0h+var_180]
0x18002eea8  mov     [rsp+1E0h+phkResult], rax; ATL::CRegKey *
0x18002eead  mov     r9d, r13d; int
0x18002eeb0  mov     r8d, r12d; int
0x18002eeb3  mov     rdx, rbx; int
0x18002eeb6  mov     rcx, r15; int
0x18002eeb9  call    ?ProcessInteractionClassV0@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV0(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x18002eebe  lea     rax, [rsp+1E0h+Block]
0x18002eec3  mov     [rsp+1E0h+lpcchClass], rax
0x18002eec8  lea     rax, [rbp+0E0h+Name]
0x18002eecc  mov     [rsp+1E0h+lpClass], rax
0x18002eed1  lea     rax, [rsp+1E0h+var_180]
0x18002eed6  mov     [rsp+1E0h+phkResult], rax
0x18002eedb  mov     r9d, r13d
0x18002eede  mov     r8d, r12d
0x18002eee1  mov     rdx, rbx
0x18002eee4  mov     rcx, r15
0x18002eee7  call    ?ProcessInteractionClassV1@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x18002eeec  nop
0x18002eeed  mov     rcx, [rsp+1E0h+var_180]; hKey
0x18002eef2  test    rcx, rcx
0x18002eef5  jz      short loc_18002EEFF
0x18002eef7  call    cs:__imp_RegCloseKey
0x18002eefd  jmp     short $+2
0x18002eeff  inc     esi
0x18002ef01  cmp     r14d, 103h
0x18002ef08  jnz     loc_18002EDFA
0x18002ef0e  mov     rcx, [rsp+1E0h+Block]; Block
0x18002ef13  call    cs:__imp_free
0x18002ef19  nop
0x18002ef1a  test    rdi, rdi
0x18002ef1d  jz      short loc_18002EF28
0x18002ef1f  mov     rcx, rdi; hKey
0x18002ef22  call    cs:__imp_RegCloseKey
0x18002ef28  xor     eax, eax
0x18002ef2a  jmp     short loc_18002EF34
0x18002ef2c  mov     ecx, eax; unsigned int
0x18002ef2e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002ef33  nop
0x18002ef34  mov     rcx, [rbp+0E0h+var_50]
0x18002ef3b  xor     rcx, rsp; StackCookie
0x18002ef3e  call    __security_check_cookie
0x18002ef43  add     rsp, 1A8h
0x18002ef4a  pop     r15
0x18002ef4c  pop     r14
0x18002ef4e  pop     r13
0x18002ef50  pop     r12
0x18002ef52  pop     rdi
0x18002ef53  pop     rsi
0x18002ef54  pop     rbx
0x18002ef55  pop     rbp
0x18002ef56  retn
```
