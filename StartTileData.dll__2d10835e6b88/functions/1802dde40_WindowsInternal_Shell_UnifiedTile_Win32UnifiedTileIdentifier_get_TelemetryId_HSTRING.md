# WindowsInternal::Shell::UnifiedTile::Win32UnifiedTileIdentifier::get_TelemetryId(HSTRING__ * *)

- ea: `0x1802dde40`
- end: `0x1802de005`
- name: `?get_TelemetryId@Win32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `453`
- prototype: `int(WindowsInternal::Shell::UnifiedTile::Win32UnifiedTileIdentifier *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001aca4`
- `0x1800385d0`
- `0x180073930`
- `0x1800c5b3c`
- `0x1800dd908`
- `0x1800e9690`
- `0x1802dde40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1802ddfc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1802ddfe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1802ddfc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1802ddfe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1802ddea4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1802ddeba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1802ddea4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1802ddeba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1802dde77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1802ddf97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1802dde77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1802ddf97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802dded4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ddfce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ddfec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802dded4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ddfce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ddfec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802ddf2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802ddf44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802ddf2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802ddf44`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1802ddf34`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1802ddf34`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1802ddf4d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1802ddf4d`

## string_xrefs

- `0x1802dde87`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifier.cpp`
- `0x1802ddef9`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifier.cpp`
- `0x1802ddfac`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifier.cpp`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::Win32UnifiedTileIdentifier::get_TelemetryId(
        HSTRING *this,
        HSTRING *a2)
{
  HSTRING *v4; // rdi
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int AppResolverAppId; // eax
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v10; // rax
  HRESULT v11; // eax
  __int64 v12; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+30h] BYREF
  PSRWLOCK v16; // [rsp+58h] [rbp+38h] BYREF
  HSTRING FileNameW; // [rsp+60h] [rbp+40h] BYREF

  *a2 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(&SRWLock, this + 13);
  v4 = this + 11;
  v5 = WindowsDuplicateString(this[11], a2);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifier.cpp",
      (const char *)(unsigned int)v5,
      savedregs);
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    return v6;
  }
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  if ( !*a2 )
  {
    SRWLock = 0;
    WindowsDeleteString(0);
    SRWLock = 0;
    AppResolverAppId = WindowsInternal::Shell::UnifiedTile::Win32UnifiedTileIdentifier::get_AppResolverAppId(
                         (WindowsInternal::Shell::UnifiedTile::Win32UnifiedTileIdentifier *)(this + 2),
                         (HSTRING *)&SRWLock);
    v6 = AppResolverAppId;
    if ( AppResolverAppId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifier.cpp",
        (const char *)(unsigned int)AppResolverAppId,
        savedregs);
LABEL_20:
      WindowsDeleteString((HSTRING)SRWLock);
      return v6;
    }
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v16, this + 13);
    if ( !*v4 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)SRWLock, 0);
      if ( PathIsFileSpecW(StringRawBuffer) )
      {
        FileNameW = this[10];
        v11 = Microsoft::WRL::Wrappers::HString::Set(this + 11, &FileNameW);
        v6 = v11;
        if ( v11 < 0 )
        {
          v12 = 528;
          goto LABEL_18;
        }
      }
      else
      {
        v10 = WindowsGetStringRawBuffer((HSTRING)SRWLock, 0);
        FileNameW = (HSTRING)PathFindFileNameW(v10);
        v11 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(this + 11);
        v6 = v11;
        if ( v11 < 0 )
        {
          v12 = 523;
          goto LABEL_18;
        }
      }
    }
    v11 = WindowsDuplicateString(*v4, a2);
    v6 = v11;
    if ( v11 < 0 )
    {
      v12 = 531;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifier.cpp",
        (const char *)(unsigned int)v11,
        savedregs);
      if ( v16 )
        ReleaseSRWLockExclusive(v16);
      goto LABEL_20;
    }
    if ( v16 )
      ReleaseSRWLockExclusive(v16);
    WindowsDeleteString((HSTRING)SRWLock);
  }
  return 0;
}

```

## disassembly

```asm
0x1802dde40  mov     [rsp-28h+arg_18], rbx
0x1802dde45  push    rbp
0x1802dde46  push    rsi
0x1802dde47  push    rdi
0x1802dde48  push    r14
0x1802dde4a  push    r15; int
0x1802dde4c  mov     rbp, rsp
0x1802dde4f  sub     rsp, 20h
0x1802dde53  mov     rsi, rdx
0x1802dde56  mov     qword ptr [rdx], 0
0x1802dde5d  lea     rdx, [rcx+68h]
0x1802dde61  mov     r14, rcx
0x1802dde64  lea     rcx, [rbp+SRWLock]
0x1802dde68  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1802dde6d  lea     rdi, [r14+58h]
0x1802dde71  mov     rdx, rsi; newString
0x1802dde74  mov     rcx, [rdi]; string
0x1802dde77  call    cs:__imp_WindowsDuplicateString
0x1802dde7d  mov     ebx, eax
0x1802dde7f  test    eax, eax
0x1802dde81  jns     short loc_1802DDEB1
0x1802dde83  mov     rcx, [rbp+28h]; this
0x1802dde87  lea     r8, aShellcommonShe_227; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1802dde8e  mov     r9d, eax; char *
0x1802dde91  mov     edx, 1FBh; void *
0x1802dde96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802dde9b  mov     rcx, [rbp+SRWLock]; SRWLock
0x1802dde9f  test    rcx, rcx
0x1802ddea2  jz      short loc_1802DDEAA
0x1802ddea4  call    cs:__imp_ReleaseSRWLockShared
0x1802ddeaa  mov     eax, ebx
0x1802ddeac  jmp     loc_1802DDFF4
0x1802ddeb1  mov     rcx, [rbp+SRWLock]; SRWLock
0x1802ddeb5  test    rcx, rcx
0x1802ddeb8  jz      short loc_1802DDEC0
0x1802ddeba  call    cs:__imp_ReleaseSRWLockShared
0x1802ddec0  cmp     qword ptr [rsi], 0
0x1802ddec4  jnz     loc_1802DDFF2
0x1802ddeca  xor     ecx, ecx; string
0x1802ddecc  mov     [rbp+SRWLock], 0
0x1802dded4  call    cs:__imp_WindowsDeleteString
0x1802ddeda  lea     rcx, [r14+10h]; this
0x1802ddede  mov     [rbp+SRWLock], 0
0x1802ddee6  lea     rdx, [rbp+SRWLock]; HSTRING *
0x1802ddeea  call    ?get_AppResolverAppId@Win32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAPEAUHSTRING__@@@Z; WindowsInternal::Shell::UnifiedTile::Win32UnifiedTileIdentifier::get_AppResolverAppId(HSTRING__ * *)
0x1802ddeef  mov     ebx, eax
0x1802ddef1  test    eax, eax
0x1802ddef3  jns     short loc_1802DDF12
0x1802ddef5  mov     rcx, [rbp+28h]; this
0x1802ddef9  lea     r8, aShellcommonShe_227; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1802ddf00  mov     r9d, eax; char *
0x1802ddf03  mov     edx, 202h; void *
0x1802ddf08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802ddf0d  jmp     loc_1802DDFCA
0x1802ddf12  lea     rdx, [r14+68h]
0x1802ddf16  lea     rcx, [rbp+arg_8]
0x1802ddf1a  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1802ddf1f  cmp     qword ptr [rdi], 0
0x1802ddf23  jnz     short loc_1802DDF91
0x1802ddf25  mov     rcx, [rbp+SRWLock]; string
0x1802ddf29  xor     edx, edx; length
0x1802ddf2b  call    cs:__imp_WindowsGetStringRawBuffer
0x1802ddf31  mov     rcx, rax; pszPath
0x1802ddf34  call    cs:__imp_PathIsFileSpecW
0x1802ddf3a  test    eax, eax
0x1802ddf3c  jnz     short loc_1802DDF70
0x1802ddf3e  mov     rcx, [rbp+SRWLock]; string
0x1802ddf42  xor     edx, edx; length
0x1802ddf44  call    cs:__imp_WindowsGetStringRawBuffer
0x1802ddf4a  mov     rcx, rax; pszPath
0x1802ddf4d  call    cs:__imp_PathFindFileNameW
0x1802ddf53  lea     rdx, [rbp+arg_10]
0x1802ddf57  mov     rcx, rdi; string
0x1802ddf5a  mov     [rbp+arg_10], rax
0x1802ddf5e  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802ddf63  mov     ebx, eax
0x1802ddf65  test    eax, eax
0x1802ddf67  jns     short loc_1802DDF91
0x1802ddf69  mov     edx, 20Bh
0x1802ddf6e  jmp     short loc_1802DDFA8
0x1802ddf70  mov     rax, [r14+50h]
0x1802ddf74  lea     rdx, [rbp+arg_10]; HSTRING *
0x1802ddf78  mov     rcx, rdi; newString
0x1802ddf7b  mov     [rbp+arg_10], rax
0x1802ddf7f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1802ddf84  mov     ebx, eax
0x1802ddf86  test    eax, eax
0x1802ddf88  jns     short loc_1802DDF91
0x1802ddf8a  mov     edx, 210h
0x1802ddf8f  jmp     short loc_1802DDFA8
0x1802ddf91  mov     rcx, [rdi]; string
0x1802ddf94  mov     rdx, rsi; newString
0x1802ddf97  call    cs:__imp_WindowsDuplicateString
0x1802ddf9d  mov     ebx, eax
0x1802ddf9f  test    eax, eax
0x1802ddfa1  jns     short loc_1802DDFD9
0x1802ddfa3  mov     edx, 213h; void *
0x1802ddfa8  mov     rcx, [rbp+28h]; this
0x1802ddfac  lea     r8, aShellcommonShe_227; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1802ddfb3  mov     r9d, eax; char *
0x1802ddfb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802ddfbb  mov     rcx, [rbp+arg_8]; SRWLock
0x1802ddfbf  test    rcx, rcx
0x1802ddfc2  jz      short loc_1802DDFCA
0x1802ddfc4  call    cs:__imp_ReleaseSRWLockExclusive
0x1802ddfca  mov     rcx, [rbp+SRWLock]; string
0x1802ddfce  call    cs:__imp_WindowsDeleteString
0x1802ddfd4  jmp     loc_1802DDEAA
0x1802ddfd9  mov     rcx, [rbp+arg_8]; SRWLock
0x1802ddfdd  test    rcx, rcx
0x1802ddfe0  jz      short loc_1802DDFE8
0x1802ddfe2  call    cs:__imp_ReleaseSRWLockExclusive
0x1802ddfe8  mov     rcx, [rbp+SRWLock]; string
0x1802ddfec  call    cs:__imp_WindowsDeleteString
0x1802ddff2  xor     eax, eax
0x1802ddff4  mov     rbx, [rsp+20h+arg_18]
0x1802ddff9  add     rsp, 20h
0x1802ddffd  pop     r15
0x1802ddfff  pop     r14
0x1802de001  pop     rdi
0x1802de002  pop     rsi
0x1802de003  pop     rbp
0x1802de004  retn
```
