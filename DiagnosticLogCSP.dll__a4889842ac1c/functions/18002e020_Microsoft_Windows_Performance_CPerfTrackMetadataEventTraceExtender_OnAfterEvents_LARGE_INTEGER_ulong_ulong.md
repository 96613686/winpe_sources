# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002e020`
- end: `0x18002e149`
- name: `?OnAfterEvents@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `297`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x1800063e0`
- `0x18002e020`
- `0x18002e7c0`
- `0x18002ed64`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18002e070`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18002e070`

## string_xrefs

- `0x18002e094`: `*.xml`
- `0x18002e0bb`: `*.ptxml`
- `0x18002e07a`: `\system32\wdi\PerfTrack\`

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
0x18002e020  push    rbx
0x18002e022  push    rbp
0x18002e023  push    rsi
0x18002e024  push    rdi
0x18002e025  sub     rsp, 258h
0x18002e02c  mov     rax, cs:__security_cookie
0x18002e033  xor     rax, rsp
0x18002e036  mov     [rsp+278h+var_38], rax
0x18002e03e  cmp     byte ptr [rcx+20h], 0
0x18002e042  mov     ebp, r9d
0x18002e045  mov     esi, r8d
0x18002e048  mov     rbx, rdx
0x18002e04b  mov     rdi, rcx
0x18002e04e  jnz     loc_18002E0F3
0x18002e054  xor     edx, edx; Val
0x18002e056  lea     rcx, [rsp+278h+Buffer]; void *
0x18002e05b  mov     r8d, 208h; Size
0x18002e061  call    memset_0
0x18002e066  mov     edx, 104h; uSize
0x18002e06b  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18002e070  call    cs:__imp_GetWindowsDirectoryW
0x18002e076  test    eax, eax
0x18002e078  jz      short loc_18002E0E2
0x18002e07a  lea     r8, aSystem32WdiPer; "\\system32\\wdi\\PerfTrack\\"
0x18002e081  mov     edx, 104h; unsigned __int64
0x18002e086  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18002e08b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e090  test    eax, eax
0x18002e092  js      short loc_18002E0E2
0x18002e094  lea     rax, aXml_1; "*.xml"
0x18002e09b  mov     r9d, ebp; unsigned int
0x18002e09e  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18002e0a3  mov     r8d, esi; unsigned int
0x18002e0a6  lea     rax, [rsp+278h+Buffer]
0x18002e0ab  mov     rdx, rbx; union _LARGE_INTEGER
0x18002e0ae  mov     rcx, rdi; this
0x18002e0b1  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18002e0b6  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18002e0bb  lea     rax, aPtxml; "*.ptxml"
0x18002e0c2  mov     r9d, ebp; unsigned int
0x18002e0c5  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18002e0ca  mov     r8d, esi; unsigned int
0x18002e0cd  lea     rax, [rsp+278h+Buffer]
0x18002e0d2  mov     rdx, rbx; union _LARGE_INTEGER
0x18002e0d5  mov     rcx, rdi; this
0x18002e0d8  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18002e0dd  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18002e0e2  mov     r9d, ebp; unsigned int
0x18002e0e5  mov     r8d, esi; unsigned int
0x18002e0e8  mov     rdx, rbx; union _LARGE_INTEGER
0x18002e0eb  mov     rcx, rdi; this
0x18002e0ee  call    ?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)
0x18002e0f3  mov     rcx, [rdi+8]
0x18002e0f7  test    rcx, rcx
0x18002e0fa  jz      short loc_18002E115
0x18002e0fc  mov     rax, [rcx]
0x18002e0ff  mov     r9d, ebp
0x18002e102  mov     r8d, esi
0x18002e105  mov     rdx, rbx
0x18002e108  mov     rax, [rax+60h]
0x18002e10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e111  mov     ecx, eax
0x18002e113  jmp     short loc_18002E11A
0x18002e115  mov     ecx, 1
0x18002e11a  cmp     byte ptr [rdi+20h], 0
0x18002e11e  jnz     short loc_18002E12B
0x18002e120  xor     eax, eax
0x18002e122  cmp     ecx, 80004001h
0x18002e128  cmovz   ecx, eax
0x18002e12b  mov     eax, ecx
0x18002e12d  mov     rcx, [rsp+278h+var_38]
0x18002e135  xor     rcx, rsp; StackCookie
0x18002e138  call    __security_check_cookie
0x18002e13d  add     rsp, 258h
0x18002e144  pop     rdi
0x18002e145  pop     rsi
0x18002e146  pop     rbp
0x18002e147  pop     rbx
0x18002e148  retn
```
