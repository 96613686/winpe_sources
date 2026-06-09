# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18001d4e0`
- end: `0x18001d60b`
- name: `?OnAfterEvents@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `299`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001c780`
- `0x18001cd84`
- `0x18001d4e0`
- `0x18001dd1c`
- `0x180026e30`
- `0x180026f6c`
- `0x180027910`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x18001d534`
- `KERNEL32!GetWindowsDirectoryW` at `0x18001d534`

## string_xrefs

- `0x18001d558`: `*.xml`
- `0x18001d57f`: `*.ptxml`
- `0x18001d53e`: `\system32\wdi\PerfTrack\`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // edi
  __int64 v9; // rcx
  __int64 result; // rax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF

  v4 = 0;
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
  v9 = *((_QWORD *)this + 1);
  if ( v9 )
    result = (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v9 + 96LL))(
               v9,
               a2,
               a3,
               a4);
  else
    result = 1;
  if ( !*((_BYTE *)this + 32) )
  {
    if ( (_DWORD)result != -2147467263 )
      return (unsigned int)result;
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18001d4e0  push    rbx
0x18001d4e2  push    rbp
0x18001d4e3  push    rsi
0x18001d4e4  push    rdi
0x18001d4e5  push    r14
0x18001d4e7  sub     rsp, 250h
0x18001d4ee  mov     rax, cs:__security_cookie
0x18001d4f5  xor     rax, rsp
0x18001d4f8  mov     [rsp+278h+var_38], rax
0x18001d500  xor     edi, edi
0x18001d502  mov     r14d, r9d
0x18001d505  mov     ebp, r8d
0x18001d508  mov     rbx, rdx
0x18001d50b  mov     rsi, rcx
0x18001d50e  cmp     [rcx+20h], dil
0x18001d512  jnz     loc_18001D5B7
0x18001d518  xor     edx, edx; Val
0x18001d51a  lea     rcx, [rsp+278h+Buffer]; void *
0x18001d51f  mov     r8d, 208h; Size
0x18001d525  call    memset_0
0x18001d52a  mov     edx, 104h; uSize
0x18001d52f  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18001d534  call    cs:__imp_GetWindowsDirectoryW
0x18001d53a  test    eax, eax
0x18001d53c  jz      short loc_18001D5A6
0x18001d53e  lea     r8, aSystem32WdiPer; "\\system32\\wdi\\PerfTrack\\"
0x18001d545  mov     edx, 104h; unsigned __int64
0x18001d54a  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18001d54f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001d554  test    eax, eax
0x18001d556  js      short loc_18001D5A6
0x18001d558  lea     rax, aXml; "*.xml"
0x18001d55f  mov     r9d, r14d; unsigned int
0x18001d562  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18001d567  mov     r8d, ebp; unsigned int
0x18001d56a  lea     rax, [rsp+278h+Buffer]
0x18001d56f  mov     rdx, rbx; union _LARGE_INTEGER
0x18001d572  mov     rcx, rsi; this
0x18001d575  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18001d57a  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18001d57f  lea     rax, aPtxml; "*.ptxml"
0x18001d586  mov     r9d, r14d; unsigned int
0x18001d589  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18001d58e  mov     r8d, ebp; unsigned int
0x18001d591  lea     rax, [rsp+278h+Buffer]
0x18001d596  mov     rdx, rbx; union _LARGE_INTEGER
0x18001d599  mov     rcx, rsi; this
0x18001d59c  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18001d5a1  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18001d5a6  mov     r9d, r14d; unsigned int
0x18001d5a9  mov     r8d, ebp; unsigned int
0x18001d5ac  mov     rdx, rbx; union _LARGE_INTEGER
0x18001d5af  mov     rcx, rsi; this
0x18001d5b2  call    ?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)
0x18001d5b7  mov     rcx, [rsi+8]
0x18001d5bb  test    rcx, rcx
0x18001d5be  jz      short loc_18001D5D8
0x18001d5c0  mov     rax, [rcx]
0x18001d5c3  mov     r9d, r14d
0x18001d5c6  mov     r8d, ebp
0x18001d5c9  mov     rdx, rbx
0x18001d5cc  mov     rax, [rax+60h]
0x18001d5d0  call    cs:__guard_dispatch_icall_fptr
0x18001d5d6  jmp     short loc_18001D5DD
0x18001d5d8  mov     eax, 1
0x18001d5dd  cmp     [rsi+20h], dil
0x18001d5e1  jnz     short loc_18001D5ED
0x18001d5e3  cmp     eax, 80004001h
0x18001d5e8  cmovnz  edi, eax
0x18001d5eb  mov     eax, edi
0x18001d5ed  mov     rcx, [rsp+278h+var_38]
0x18001d5f5  xor     rcx, rsp; StackCookie
0x18001d5f8  call    __security_check_cookie
0x18001d5fd  add     rsp, 250h
0x18001d604  pop     r14
0x18001d606  pop     rdi
0x18001d607  pop     rsi
0x18001d608  pop     rbp
0x18001d609  pop     rbx
0x18001d60a  retn
```
