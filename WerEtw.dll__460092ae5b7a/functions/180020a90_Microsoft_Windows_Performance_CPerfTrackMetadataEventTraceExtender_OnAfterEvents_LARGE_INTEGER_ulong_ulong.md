# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180020a90`
- end: `0x180020bb9`
- name: `?OnAfterEvents@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `297`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001870`
- `0x180002420`
- `0x18001f020`
- `0x180020a90`
- `0x180021230`
- `0x1800217d4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180020ae0`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180020ae0`

## string_xrefs

- `0x180020b04`: `*.xml`
- `0x180020b2b`: `*.ptxml`
- `0x180020aea`: `\system32\wdi\PerfTrack\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rcx
  unsigned int v9; // ecx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( !*((_BYTE *)this + 32) )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( GetWindowsDirectoryW(Buffer, 0x104u)
      && (int)StringCchCatW(Buffer, 0x104u, L"\\system32\\wdi\\PerfTrack\\") >= 0 )
    {
      Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(
        this,
        a2,
        a3,
        a4,
        Buffer,
        L"*.xml");
      Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(
        this,
        a2,
        a3,
        a4,
        Buffer,
        L"*.ptxml");
    }
    Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(this, a2, a3, a4);
  }
  v8 = *((_QWORD *)this + 1);
  if ( v8 )
    v9 = (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v8 + 96LL))(
           v8,
           a2,
           a3,
           a4);
  else
    v9 = 1;
  if ( !*((_BYTE *)this + 32) && v9 == -2147467263 )
    return 0;
  return v9;
}

```

## disassembly

```asm
0x180020a90  push    rbx
0x180020a92  push    rbp
0x180020a93  push    rsi
0x180020a94  push    rdi
0x180020a95  sub     rsp, 258h
0x180020a9c  mov     rax, cs:__security_cookie
0x180020aa3  xor     rax, rsp
0x180020aa6  mov     [rsp+278h+var_38], rax
0x180020aae  cmp     byte ptr [rcx+20h], 0
0x180020ab2  mov     ebp, r9d
0x180020ab5  mov     esi, r8d
0x180020ab8  mov     rbx, rdx
0x180020abb  mov     rdi, rcx
0x180020abe  jnz     loc_180020B63
0x180020ac4  xor     edx, edx; Val
0x180020ac6  lea     rcx, [rsp+278h+Buffer]; void *
0x180020acb  mov     r8d, 208h; Size
0x180020ad1  call    memset_0
0x180020ad6  mov     edx, 104h; uSize
0x180020adb  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x180020ae0  call    cs:__imp_GetWindowsDirectoryW
0x180020ae6  test    eax, eax
0x180020ae8  jz      short loc_180020B52
0x180020aea  lea     r8, aSystem32WdiPer; "\\system32\\wdi\\PerfTrack\\"
0x180020af1  mov     edx, 104h; unsigned __int64
0x180020af6  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x180020afb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180020b00  test    eax, eax
0x180020b02  js      short loc_180020B52
0x180020b04  lea     rax, aXml; "*.xml"
0x180020b0b  mov     r9d, ebp; unsigned int
0x180020b0e  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x180020b13  mov     r8d, esi; unsigned int
0x180020b16  lea     rax, [rsp+278h+Buffer]
0x180020b1b  mov     rdx, rbx; union _LARGE_INTEGER
0x180020b1e  mov     rcx, rdi; this
0x180020b21  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x180020b26  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x180020b2b  lea     rax, aPtxml; "*.ptxml"
0x180020b32  mov     r9d, ebp; unsigned int
0x180020b35  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x180020b3a  mov     r8d, esi; unsigned int
0x180020b3d  lea     rax, [rsp+278h+Buffer]
0x180020b42  mov     rdx, rbx; union _LARGE_INTEGER
0x180020b45  mov     rcx, rdi; this
0x180020b48  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x180020b4d  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x180020b52  mov     r9d, ebp; unsigned int
0x180020b55  mov     r8d, esi; unsigned int
0x180020b58  mov     rdx, rbx; union _LARGE_INTEGER
0x180020b5b  mov     rcx, rdi; this
0x180020b5e  call    ?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)
0x180020b63  mov     rcx, [rdi+8]
0x180020b67  test    rcx, rcx
0x180020b6a  jz      short loc_180020B85
0x180020b6c  mov     rax, [rcx]
0x180020b6f  mov     r9d, ebp
0x180020b72  mov     r8d, esi
0x180020b75  mov     rdx, rbx
0x180020b78  mov     rax, [rax+60h]
0x180020b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b81  mov     ecx, eax
0x180020b83  jmp     short loc_180020B8A
0x180020b85  mov     ecx, 1
0x180020b8a  cmp     byte ptr [rdi+20h], 0
0x180020b8e  jnz     short loc_180020B9B
0x180020b90  xor     eax, eax
0x180020b92  cmp     ecx, 80004001h
0x180020b98  cmovz   ecx, eax
0x180020b9b  mov     eax, ecx
0x180020b9d  mov     rcx, [rsp+278h+var_38]
0x180020ba5  xor     rcx, rsp; StackCookie
0x180020ba8  call    __security_check_cookie
0x180020bad  add     rsp, 258h
0x180020bb4  pop     rdi
0x180020bb5  pop     rsi
0x180020bb6  pop     rbp
0x180020bb7  pop     rbx
0x180020bb8  retn
```
