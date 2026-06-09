# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18001cd84`
- end: `0x18001cf95`
- name: `?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `529`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d4e0`

## callees

- `0x180006960`
- `0x18001cd84`
- `0x18001cf98`
- `0x18001d268`
- `0x180026e30`

## import_xrefs

- `msvcrt!free` at `0x18001cf47`
- `msvcrt!free` at `0x18001cf47`
- `ADVAPI32!RegEnumKeyExW` at `0x18001ce51`
- `ADVAPI32!RegEnumKeyExW` at `0x18001ce51`
- `ADVAPI32!RegOpenKeyExW` at `0x18001cdfe`
- `ADVAPI32!RegOpenKeyExW` at `0x18001cea1`
- `ADVAPI32!RegOpenKeyExW` at `0x18001cdfe`
- `ADVAPI32!RegOpenKeyExW` at `0x18001cea1`
- `ADVAPI32!RegCloseKey` at `0x18001cf1c`
- `ADVAPI32!RegCloseKey` at `0x18001cf65`
- `ADVAPI32!RegCloseKey` at `0x18001cf1c`
- `ADVAPI32!RegCloseKey` at `0x18001cf65`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        int a3,
        __int16 a4)
{
  HKEY v8; // rdi
  LSTATUS v9; // eax
  DWORD v10; // esi
  LSTATUS v11; // r14d
  unsigned int v12; // ebx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  HKEY v18[3]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v19; // [rsp+78h] [rbp-88h]
  __int64 v20; // [rsp+80h] [rbp-80h]
  __int64 v21; // [rsp+88h] [rbp-78h]
  __int64 v22; // [rsp+90h] [rbp-70h]
  struct _FILETIME ftLastWriteTime; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Name[128]; // [rsp+A0h] [rbp-60h] BYREF

  v22 = -2;
  v8 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  hKey = 0;
  v9 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\PerfTrack\\InteractionClasses",
         0,
         0x20019u,
         &hKey);
  if ( v9 )
  {
    v12 = ATL::AtlHresultFromWin32(v9);
  }
  else
  {
    v8 = hKey;
    v19 = hKey;
    Block = 0;
    v17 = 0;
    v10 = 0;
    do
    {
      LODWORD(hKey) = 128;
      v11 = RegEnumKeyExW(v8, v10, Name, (LPDWORD)&hKey, 0, 0, 0, &ftLastWriteTime);
      if ( !v11 && (unsigned int)hKey < 0x80 )
      {
        memset(v18, 0, sizeof(v18));
        phkResult = 0;
        if ( !RegOpenKeyExW(v8, Name, 0, 0x20019u, &phkResult) )
        {
          v18[0] = phkResult;
          Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV0(
            (__int64)this,
            a2.QuadPart,
            a3,
            a4,
            (ATL::CRegKey *)v18,
            (__int64)Name,
            (__int64)&Block);
          Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(
            (__int64)this,
            a2.QuadPart,
            a3,
            a4,
            v18,
            (__int64)Name,
            (__int64)&Block);
          if ( v18[0] )
          {
            RegCloseKey(v18[0]);
            v18[0] = 0;
          }
        }
      }
      ++v10;
    }
    while ( v11 != 259 );
    v12 = 0;
    free(Block);
    Block = 0;
  }
  if ( v8 )
  {
    RegCloseKey(v8);
    v19 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x18001cd84  push    rbp
0x18001cd86  push    rbx
0x18001cd87  push    rsi
0x18001cd88  push    rdi
0x18001cd89  push    r12
0x18001cd8b  push    r13
0x18001cd8d  push    r14
0x18001cd8f  push    r15
0x18001cd91  lea     rbp, [rsp-0B8h]
0x18001cd99  sub     rsp, 1B8h
0x18001cda0  mov     [rbp+0F0h+var_160], 0FFFFFFFFFFFFFFFEh
0x18001cda8  mov     rax, cs:__security_cookie
0x18001cdaf  xor     rax, rsp
0x18001cdb2  mov     [rbp+0F0h+var_50], rax
0x18001cdb9  mov     r13d, r9d
0x18001cdbc  mov     r12d, r8d
0x18001cdbf  mov     rbx, rdx
0x18001cdc2  mov     r15, rcx
0x18001cdc5  xor     r14d, r14d
0x18001cdc8  mov     edi, r14d
0x18001cdcb  mov     [rsp+1F0h+var_178], r14
0x18001cdd0  mov     [rbp+0F0h+var_170], r14
0x18001cdd4  mov     [rbp+0F0h+var_168], r14
0x18001cdd8  mov     [rsp+1F0h+hKey], r14
0x18001cddd  lea     rax, [rsp+1F0h+hKey]
0x18001cde2  mov     [rsp+1F0h+phkResult], rax; phkResult
0x18001cde7  mov     r9d, 20019h; samDesired
0x18001cded  xor     r8d, r8d; ulOptions
0x18001cdf0  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001cdf7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cdfe  call    cs:__imp_RegOpenKeyExW
0x18001ce04  test    eax, eax
0x18001ce06  jnz     loc_18001CF54
0x18001ce0c  mov     rdi, [rsp+1F0h+hKey]
0x18001ce11  mov     [rsp+1F0h+var_178], rdi
0x18001ce16  mov     [rsp+1F0h+Block], r14
0x18001ce1b  mov     [rsp+1F0h+var_198], r14d
0x18001ce20  mov     esi, r14d
0x18001ce23  mov     dword ptr [rsp+1F0h+hKey], 80h
0x18001ce2b  lea     rax, [rbp+0F0h+ftLastWriteTime]
0x18001ce2f  mov     [rsp+1F0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001ce34  mov     [rsp+1F0h+lpcchClass], r14; lpcchClass
0x18001ce39  mov     [rsp+1F0h+lpClass], r14; lpClass
0x18001ce3e  mov     [rsp+1F0h+phkResult], r14; lpReserved
0x18001ce43  lea     r9, [rsp+1F0h+hKey]; lpcchName
0x18001ce48  lea     r8, [rbp+0F0h+Name]; lpName
0x18001ce4c  mov     edx, esi; dwIndex
0x18001ce4e  mov     rcx, rdi; hKey
0x18001ce51  call    cs:__imp_RegEnumKeyExW
0x18001ce57  mov     r14d, eax
0x18001ce5a  xor     eax, eax
0x18001ce5c  test    r14d, r14d
0x18001ce5f  jnz     loc_18001CF2A
0x18001ce65  cmp     dword ptr [rsp+1F0h+hKey], 80h
0x18001ce6d  jnb     loc_18001CF2A
0x18001ce73  mov     [rsp+1F0h+var_190], rax
0x18001ce78  mov     [rsp+1F0h+var_188], rax
0x18001ce7d  mov     [rsp+1F0h+var_180], rax
0x18001ce82  mov     [rsp+1F0h+var_1A8], rax
0x18001ce87  lea     rax, [rsp+1F0h+var_1A8]
0x18001ce8c  mov     [rsp+1F0h+phkResult], rax; phkResult
0x18001ce91  mov     r9d, 20019h; samDesired
0x18001ce97  xor     r8d, r8d; ulOptions
0x18001ce9a  lea     rdx, [rbp+0F0h+Name]; lpSubKey
0x18001ce9e  mov     rcx, rdi; hKey
0x18001cea1  call    cs:__imp_RegOpenKeyExW
0x18001cea7  test    eax, eax
0x18001cea9  jnz     short loc_18001CF2A
0x18001ceab  mov     rax, [rsp+1F0h+var_1A8]
0x18001ceb0  mov     [rsp+1F0h+var_190], rax
0x18001ceb5  lea     rax, [rsp+1F0h+Block]
0x18001ceba  mov     [rsp+1F0h+lpcchClass], rax; __int64
0x18001cebf  lea     rax, [rbp+0F0h+Name]
0x18001cec3  mov     [rsp+1F0h+lpClass], rax; __int64
0x18001cec8  lea     rax, [rsp+1F0h+var_190]
0x18001cecd  mov     [rsp+1F0h+phkResult], rax; ATL::CRegKey *
0x18001ced2  mov     r9d, r13d; int
0x18001ced5  mov     r8d, r12d; int
0x18001ced8  mov     rdx, rbx; int
0x18001cedb  mov     rcx, r15; int
0x18001cede  call    ?ProcessInteractionClassV0@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV0(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x18001cee3  lea     rax, [rsp+1F0h+Block]
0x18001cee8  mov     [rsp+1F0h+lpcchClass], rax
0x18001ceed  lea     rax, [rbp+0F0h+Name]
0x18001cef1  mov     [rsp+1F0h+lpClass], rax
0x18001cef6  lea     rax, [rsp+1F0h+var_190]
0x18001cefb  mov     [rsp+1F0h+phkResult], rax
0x18001cf00  mov     r9d, r13d
0x18001cf03  mov     r8d, r12d
0x18001cf06  mov     rdx, rbx
0x18001cf09  mov     rcx, r15
0x18001cf0c  call    ?ProcessInteractionClassV1@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x18001cf11  nop
0x18001cf12  mov     rcx, [rsp+1F0h+var_190]; hKey
0x18001cf17  test    rcx, rcx
0x18001cf1a  jz      short loc_18001CF2A
0x18001cf1c  call    cs:__imp_RegCloseKey
0x18001cf22  and     [rsp+1F0h+var_190], 0
0x18001cf28  jmp     short $+2
0x18001cf2a  inc     esi
0x18001cf2c  cmp     r14d, 103h
0x18001cf33  mov     r14d, 0
0x18001cf39  jnz     loc_18001CE23
0x18001cf3f  mov     ebx, r14d
0x18001cf42  mov     rcx, [rsp+1F0h+Block]; Block
0x18001cf47  call    cs:__imp_free
0x18001cf4d  mov     [rsp+1F0h+Block], r14
0x18001cf52  jmp     short loc_18001CF5D
0x18001cf54  mov     ecx, eax; unsigned int
0x18001cf56  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001cf5b  mov     ebx, eax
0x18001cf5d  test    rdi, rdi
0x18001cf60  jz      short loc_18001CF70
0x18001cf62  mov     rcx, rdi; hKey
0x18001cf65  call    cs:__imp_RegCloseKey
0x18001cf6b  mov     [rsp+1F0h+var_178], r14
0x18001cf70  mov     eax, ebx
0x18001cf72  mov     rcx, [rbp+0F0h+var_50]
0x18001cf79  xor     rcx, rsp; StackCookie
0x18001cf7c  call    __security_check_cookie
0x18001cf81  add     rsp, 1B8h
0x18001cf88  pop     r15
0x18001cf8a  pop     r14
0x18001cf8c  pop     r13
0x18001cf8e  pop     r12
0x18001cf90  pop     rdi
0x18001cf91  pop     rsi
0x18001cf92  pop     rbx
0x18001cf93  pop     rbp
0x18001cf94  retn
```
