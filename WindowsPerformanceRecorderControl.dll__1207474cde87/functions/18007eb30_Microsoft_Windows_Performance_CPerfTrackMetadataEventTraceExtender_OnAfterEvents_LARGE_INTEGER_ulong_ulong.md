# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18007eb30`
- end: `0x18007ec47`
- name: `?OnAfterEvents@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `279`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18004ece0`
- `0x18004f964`
- `0x1800556d0`
- `0x18005c460`
- `0x18007eb30`
- `0x18007f144`
- `0x18007f57c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18007eb80`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18007eb80`

## string_xrefs

- `0x18007eba4`: `*.xml`
- `0x18007ebcb`: `*.ptxml`
- `0x18007eb8a`: `\system32\wdi\PerfTrack\`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v8; // ecx
  unsigned int v9; // eax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( !*((_BYTE *)this + 32) )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( GetWindowsDirectoryW(Buffer, 0x104u) && StringCchCatW(Buffer, 0x104u, L"\\system32\\wdi\\PerfTrack\\") >= 0 )
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
  v8 = Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(this, a2, a3, a4);
  if ( !*((_BYTE *)this + 32) )
  {
    v9 = 0;
    if ( v8 != -2147467263 )
      return v8;
    return v9;
  }
  return v8;
}

```

## disassembly

```asm
0x18007eb30  push    rbx
0x18007eb32  push    rbp
0x18007eb33  push    rsi
0x18007eb34  push    rdi
0x18007eb35  sub     rsp, 258h
0x18007eb3c  mov     rax, cs:__security_cookie
0x18007eb43  xor     rax, rsp
0x18007eb46  mov     [rsp+278h+var_38], rax
0x18007eb4e  cmp     byte ptr [rcx+20h], 0
0x18007eb52  mov     ebp, r9d
0x18007eb55  mov     esi, r8d
0x18007eb58  mov     rbx, rdx
0x18007eb5b  mov     rdi, rcx
0x18007eb5e  jnz     loc_18007EC03
0x18007eb64  xor     edx, edx; Val
0x18007eb66  lea     rcx, [rsp+278h+Buffer]; void *
0x18007eb6b  mov     r8d, 208h; Size
0x18007eb71  call    memset_0
0x18007eb76  mov     edx, 104h; uSize
0x18007eb7b  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18007eb80  call    cs:__imp_GetWindowsDirectoryW
0x18007eb86  test    eax, eax
0x18007eb88  jz      short loc_18007EBF2
0x18007eb8a  lea     r8, aSystem32WdiPer; "\\system32\\wdi\\PerfTrack\\"
0x18007eb91  mov     edx, 104h; unsigned __int64
0x18007eb96  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18007eb9b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007eba0  test    eax, eax
0x18007eba2  js      short loc_18007EBF2
0x18007eba4  lea     rax, aXml; "*.xml"
0x18007ebab  mov     r9d, ebp; unsigned int
0x18007ebae  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18007ebb3  mov     r8d, esi; unsigned int
0x18007ebb6  lea     rax, [rsp+278h+Buffer]
0x18007ebbb  mov     rdx, rbx; union _LARGE_INTEGER
0x18007ebbe  mov     rcx, rdi; this
0x18007ebc1  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18007ebc6  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18007ebcb  lea     rax, aPtxml; "*.ptxml"
0x18007ebd2  mov     r9d, ebp; unsigned int
0x18007ebd5  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18007ebda  mov     r8d, esi; unsigned int
0x18007ebdd  lea     rax, [rsp+278h+Buffer]
0x18007ebe2  mov     rdx, rbx; union _LARGE_INTEGER
0x18007ebe5  mov     rcx, rdi; this
0x18007ebe8  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18007ebed  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18007ebf2  mov     r9d, ebp; unsigned int
0x18007ebf5  mov     r8d, esi; unsigned int
0x18007ebf8  mov     rdx, rbx; union _LARGE_INTEGER
0x18007ebfb  mov     rcx, rdi; this
0x18007ebfe  call    ?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)
0x18007ec03  mov     r9d, ebp; unsigned int
0x18007ec06  mov     r8d, esi; unsigned int
0x18007ec09  mov     rdx, rbx; union _LARGE_INTEGER
0x18007ec0c  mov     rcx, rdi; this
0x18007ec0f  call    ?OnAfterEvents@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)
0x18007ec14  cmp     byte ptr [rdi+20h], 0
0x18007ec18  mov     ecx, eax
0x18007ec1a  jnz     short loc_18007EC29
0x18007ec1c  xor     eax, eax
0x18007ec1e  cmp     ecx, 80004001h
0x18007ec24  cmovnz  eax, ecx
0x18007ec27  mov     ecx, eax
0x18007ec29  mov     eax, ecx
0x18007ec2b  mov     rcx, [rsp+278h+var_38]
0x18007ec33  xor     rcx, rsp; StackCookie
0x18007ec36  call    __security_check_cookie
0x18007ec3b  add     rsp, 258h
0x18007ec42  pop     rdi
0x18007ec43  pop     rsi
0x18007ec44  pop     rbp
0x18007ec45  pop     rbx
0x18007ec46  retn
```
