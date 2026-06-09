# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002f450`
- end: `0x18002f580`
- name: `?OnAfterEvents@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `304`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001b90`
- `0x18000265c`
- `0x180006360`
- `0x18002f450`
- `0x18002fc74`
- `0x1800301f4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18002f4a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18002f4a0`

## string_xrefs

- `0x18002f4ca`: `*.xml`
- `0x18002f4f1`: `*.ptxml`
- `0x18002f4b0`: `\system32\wdi\PerfTrack\`

## pseudocode

```c
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
0x18002f450  push    rbx
0x18002f452  push    rbp
0x18002f453  push    rsi
0x18002f454  push    rdi
0x18002f455  sub     rsp, 258h
0x18002f45c  mov     rax, cs:__security_cookie
0x18002f463  xor     rax, rsp
0x18002f466  mov     [rsp+278h+var_38], rax
0x18002f46e  cmp     byte ptr [rcx+20h], 0
0x18002f472  mov     ebp, r9d
0x18002f475  mov     esi, r8d
0x18002f478  mov     rbx, rdx
0x18002f47b  mov     rdi, rcx
0x18002f47e  jnz     loc_18002F529
0x18002f484  xor     edx, edx; Val
0x18002f486  lea     rcx, [rsp+278h+Buffer]; void *
0x18002f48b  mov     r8d, 208h; Size
0x18002f491  call    memset_0
0x18002f496  mov     edx, 104h; uSize
0x18002f49b  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18002f4a0  call    cs:__imp_GetWindowsDirectoryW
0x18002f4a7  nop     dword ptr [rax+rax+00h]
0x18002f4ac  test    eax, eax
0x18002f4ae  jz      short loc_18002F518
0x18002f4b0  lea     r8, aSystem32WdiPer; "\\system32\\wdi\\PerfTrack\\"
0x18002f4b7  mov     edx, 104h; unsigned __int64
0x18002f4bc  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18002f4c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f4c6  test    eax, eax
0x18002f4c8  js      short loc_18002F518
0x18002f4ca  lea     rax, aXml_1; "*.xml"
0x18002f4d1  mov     r9d, ebp; unsigned int
0x18002f4d4  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18002f4d9  mov     r8d, esi; unsigned int
0x18002f4dc  lea     rax, [rsp+278h+Buffer]
0x18002f4e1  mov     rdx, rbx; union _LARGE_INTEGER
0x18002f4e4  mov     rcx, rdi; this
0x18002f4e7  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18002f4ec  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18002f4f1  lea     rax, aPtxml; "*.ptxml"
0x18002f4f8  mov     r9d, ebp; unsigned int
0x18002f4fb  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18002f500  mov     r8d, esi; unsigned int
0x18002f503  lea     rax, [rsp+278h+Buffer]
0x18002f508  mov     rdx, rbx; union _LARGE_INTEGER
0x18002f50b  mov     rcx, rdi; this
0x18002f50e  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18002f513  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18002f518  mov     r9d, ebp; unsigned int
0x18002f51b  mov     r8d, esi; unsigned int
0x18002f51e  mov     rdx, rbx; union _LARGE_INTEGER
0x18002f521  mov     rcx, rdi; this
0x18002f524  call    ?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)
0x18002f529  mov     rcx, [rdi+8]
0x18002f52d  test    rcx, rcx
0x18002f530  jz      short loc_18002F54B
0x18002f532  mov     rax, [rcx]
0x18002f535  mov     r9d, ebp
0x18002f538  mov     r8d, esi
0x18002f53b  mov     rdx, rbx
0x18002f53e  mov     rax, [rax+60h]
0x18002f542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f547  mov     ecx, eax
0x18002f549  jmp     short loc_18002F550
0x18002f54b  mov     ecx, 1
0x18002f550  cmp     byte ptr [rdi+20h], 0
0x18002f554  jnz     short loc_18002F561
0x18002f556  xor     eax, eax
0x18002f558  cmp     ecx, 80004001h
0x18002f55e  cmovz   ecx, eax
0x18002f561  mov     eax, ecx
0x18002f563  mov     rcx, [rsp+278h+var_38]
0x18002f56b  xor     rcx, rsp; StackCookie
0x18002f56e  call    __security_check_cookie
0x18002f573  add     rsp, 258h
0x18002f57a  pop     rdi
0x18002f57b  pop     rsi
0x18002f57c  pop     rbp
0x18002f57d  pop     rbx
0x18002f57e  retn
```
