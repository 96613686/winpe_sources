# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)

- ea: `0x1800217d4`
- end: `0x1800219c6`
- name: `?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `498`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this, union _LARGE_INTEGER, int, __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020a90`

## callees

- `0x180001870`
- `0x1800023d8`
- `0x180004694`
- `0x180020d24`
- `0x180020fdc`
- `0x1800217d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800218a1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800218a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021967`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021991`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021967`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021991`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021843`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800218ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021843`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800218ec`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        int a3,
        __int16 a4)
{
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
          (__int64)this,
          a2.QuadPart,
          a3,
          a4,
          (ATL::CRegKey *)v17,
          (__int64)Name,
          (__int64)&Block);
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(
          (__int64)this,
          a2.QuadPart,
          a3,
          a4,
          v17,
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
0x1800217d4  push    rbp
0x1800217d6  push    rbx
0x1800217d7  push    rsi
0x1800217d8  push    rdi
0x1800217d9  push    r12
0x1800217db  push    r13
0x1800217dd  push    r14
0x1800217df  push    r15
0x1800217e1  lea     rbp, [rsp-0A8h]
0x1800217e9  sub     rsp, 1A8h
0x1800217f0  mov     rax, cs:__security_cookie
0x1800217f7  xor     rax, rsp
0x1800217fa  mov     [rbp+0E0h+var_50], rax
0x180021801  mov     r13d, r9d
0x180021804  mov     r12d, r8d
0x180021807  mov     rbx, rdx
0x18002180a  mov     r15, rcx
0x18002180d  xor     r14d, r14d
0x180021810  mov     [rsp+1E0h+var_168], r14
0x180021815  mov     [rbp+0E0h+var_160], r14
0x180021819  mov     [rbp+0E0h+var_158], r14
0x18002181d  mov     [rsp+1E0h+hKey], r14
0x180021822  lea     rax, [rsp+1E0h+hKey]
0x180021827  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18002182c  mov     r9d, 20019h; samDesired
0x180021832  xor     r8d, r8d; ulOptions
0x180021835  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002183c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021843  call    cs:__imp_RegOpenKeyExW
0x180021849  test    eax, eax
0x18002184b  jnz     loc_18002199B
0x180021851  mov     rdi, [rsp+1E0h+hKey]
0x180021856  mov     [rsp+1E0h+var_168], rdi
0x18002185b  mov     [rsp+1E0h+Block], r14
0x180021860  mov     [rsp+1E0h+var_188], r14d
0x180021865  mov     esi, r14d
0x180021868  jmp     short loc_18002186D
0x18002186a  xor     r14d, r14d
0x18002186d  mov     dword ptr [rsp+1E0h+hKey], 80h
0x180021875  mov     qword ptr [rsp+1E0h+ftLastWriteTime.dwLowDateTime], r14
0x18002187a  lea     rax, [rsp+1E0h+ftLastWriteTime]
0x18002187f  mov     [rsp+1E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180021884  mov     [rsp+1E0h+lpcchClass], r14; lpcchClass
0x180021889  mov     [rsp+1E0h+lpClass], r14; lpClass
0x18002188e  mov     [rsp+1E0h+phkResult], r14; lpReserved
0x180021893  lea     r9, [rsp+1E0h+hKey]; lpcchName
0x180021898  lea     r8, [rbp+0E0h+Name]; lpName
0x18002189c  mov     edx, esi; dwIndex
0x18002189e  mov     rcx, rdi; hKey
0x1800218a1  call    cs:__imp_RegEnumKeyExW
0x1800218a7  mov     r14d, eax
0x1800218aa  xor     eax, eax
0x1800218ac  test    r14d, r14d
0x1800218af  jnz     loc_18002196F
0x1800218b5  cmp     dword ptr [rsp+1E0h+hKey], 80h
0x1800218bd  jnb     loc_18002196F
0x1800218c3  mov     [rsp+1E0h+var_178], rax
0x1800218c8  mov     [rsp+1E0h+var_170], rax
0x1800218cd  mov     qword ptr [rsp+1E0h+ftLastWriteTime.dwLowDateTime], rax
0x1800218d2  lea     rax, [rsp+1E0h+ftLastWriteTime]
0x1800218d7  mov     [rsp+1E0h+phkResult], rax; phkResult
0x1800218dc  mov     r9d, 20019h; samDesired
0x1800218e2  xor     r8d, r8d; ulOptions
0x1800218e5  lea     rdx, [rbp+0E0h+Name]; lpSubKey
0x1800218e9  mov     rcx, rdi; hKey
0x1800218ec  call    cs:__imp_RegOpenKeyExW
0x1800218f2  test    eax, eax
0x1800218f4  jnz     short loc_18002196F
0x1800218f6  mov     rax, qword ptr [rsp+1E0h+ftLastWriteTime.dwLowDateTime]
0x1800218fb  mov     [rsp+1E0h+var_180], rax
0x180021900  lea     rax, [rsp+1E0h+Block]
0x180021905  mov     [rsp+1E0h+lpcchClass], rax; __int64
0x18002190a  lea     rax, [rbp+0E0h+Name]
0x18002190e  mov     [rsp+1E0h+lpClass], rax; __int64
0x180021913  lea     rax, [rsp+1E0h+var_180]
0x180021918  mov     [rsp+1E0h+phkResult], rax; ATL::CRegKey *
0x18002191d  mov     r9d, r13d; int
0x180021920  mov     r8d, r12d; int
0x180021923  mov     rdx, rbx; int
0x180021926  mov     rcx, r15; int
0x180021929  call    ?ProcessInteractionClassV0@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV0(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x18002192e  lea     rax, [rsp+1E0h+Block]
0x180021933  mov     [rsp+1E0h+lpcchClass], rax
0x180021938  lea     rax, [rbp+0E0h+Name]
0x18002193c  mov     [rsp+1E0h+lpClass], rax
0x180021941  lea     rax, [rsp+1E0h+var_180]
0x180021946  mov     [rsp+1E0h+phkResult], rax
0x18002194b  mov     r9d, r13d
0x18002194e  mov     r8d, r12d
0x180021951  mov     rdx, rbx
0x180021954  mov     rcx, r15
0x180021957  call    ?ProcessInteractionClassV1@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x18002195c  nop
0x18002195d  mov     rcx, [rsp+1E0h+var_180]; hKey
0x180021962  test    rcx, rcx
0x180021965  jz      short loc_18002196F
0x180021967  call    cs:__imp_RegCloseKey
0x18002196d  jmp     short $+2
0x18002196f  inc     esi
0x180021971  cmp     r14d, 103h
0x180021978  jnz     loc_18002186A
0x18002197e  mov     rcx, [rsp+1E0h+Block]; Block
0x180021983  call    free
0x180021988  nop
0x180021989  test    rdi, rdi
0x18002198c  jz      short loc_180021997
0x18002198e  mov     rcx, rdi; hKey
0x180021991  call    cs:__imp_RegCloseKey
0x180021997  xor     eax, eax
0x180021999  jmp     short loc_1800219A3
0x18002199b  mov     ecx, eax; unsigned int
0x18002199d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800219a2  nop
0x1800219a3  mov     rcx, [rbp+0E0h+var_50]
0x1800219aa  xor     rcx, rsp; StackCookie
0x1800219ad  call    __security_check_cookie
0x1800219b2  add     rsp, 1A8h
0x1800219b9  pop     r15
0x1800219bb  pop     r14
0x1800219bd  pop     r13
0x1800219bf  pop     r12
0x1800219c1  pop     rdi
0x1800219c2  pop     rsi
0x1800219c3  pop     rbx
0x1800219c4  pop     rbp
0x1800219c5  retn
```
