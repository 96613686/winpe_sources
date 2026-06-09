# RdVhd::Uvhd::CDirectoryHelper::GetFileSecurityW(ushort const *,ulong,void *,ulong,ulong *)

- ea: `0x1800191a0`
- end: `0x18001929d`
- name: `?GetFileSecurityW@CDirectoryHelper@Uvhd@RdVhd@@AEBAHPEBGKPEAXKPEAK@Z`
- size: `253`
- prototype: `int(RdVhd::Uvhd::CDirectoryHelper *__hidden this, const unsigned __int16 *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004f3d0`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x1800191a0`
- `0x180019b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800191df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001921c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800191df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001921c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800191cf`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180019280`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800191cf`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180019280`

## string_xrefs

- `0x180019246`: `GetFileSecurityW failed for path '%s'. Trying with long path`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::GetFileSecurityW(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2,
        __int64 a3,
        void *a4,
        DWORD nLength,
        unsigned int *lpnLengthNeeded)
{
  unsigned int FileSecurityW; // ebx
  signed int LastError; // eax
  const WCHAR *v10; // rax
  void **v12; // [rsp+30h] [rbp-58h] BYREF
  int v13; // [rsp+38h] [rbp-50h]
  __int64 v14; // [rsp+3Ch] [rbp-4Ch]
  int v15; // [rsp+44h] [rbp-44h]
  __int64 v16; // [rsp+48h] [rbp-40h]
  int v17; // [rsp+50h] [rbp-38h]

  FileSecurityW = GetFileSecurityW(a2, 4u, a4, nLength, lpnLengthNeeded);
  if ( !FileSecurityW && GetLastError() == 123 )
  {
    v14 = 128;
    v12 = &CPathString::`vftable';
    v16 = 0;
    v15 = 0;
    v17 = 0x8000000;
    v13 = 0;
    LastError = GetLastError();
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LastError = LastError & 0x8000FFFF | 0x502D0000;
    }
    _TraceNrmRdvVmEx(L"UVHD", (unsigned int)LastError, L"GetFileSecurityW failed for path '%s'. Trying with long path");
    v10 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a2, (struct CPathString *)&v12);
    FileSecurityW = GetFileSecurityW(v10, 4u, a4, nLength, lpnLengthNeeded);
    CPathString::~CPathString((CPathString *)&v12);
  }
  return FileSecurityW;
}

```

## disassembly

```asm
0x1800191a0  push    rbx
0x1800191a2  push    rbp
0x1800191a3  push    rsi
0x1800191a4  push    rdi
0x1800191a5  sub     rsp, 68h
0x1800191a9  mov     rsi, r9
0x1800191ac  mov     rdi, rdx
0x1800191af  mov     rbp, [rsp+88h+arg_28]
0x1800191b7  mov     r8, rsi; pSecurityDescriptor
0x1800191ba  mov     r9d, [rsp+88h+nLength]; nLength
0x1800191c2  mov     edx, 4; RequestedInformation
0x1800191c7  mov     rcx, rdi; lpFileName
0x1800191ca  mov     [rsp+88h+lpnLengthNeeded], rbp; lpnLengthNeeded
0x1800191cf  call    cs:__imp_GetFileSecurityW
0x1800191d5  mov     ebx, eax
0x1800191d7  test    eax, eax
0x1800191d9  jnz     loc_180019292
0x1800191df  call    cs:__imp_GetLastError
0x1800191e5  cmp     eax, 7Bh ; '{'
0x1800191e8  jnz     loc_180019292
0x1800191ee  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x1800191f5  mov     [rsp+88h+var_4C], 80h
0x1800191fe  mov     [rsp+88h+var_58], rax
0x180019203  mov     [rsp+88h+var_40], 0
0x18001920c  mov     [rsp+88h+var_44], ebx
0x180019210  mov     [rsp+88h+var_38], 8000000h
0x180019218  mov     [rsp+88h+var_50], ebx
0x18001921c  call    cs:__imp_GetLastError
0x180019222  test    eax, eax
0x180019224  jz      short loc_180019243
0x180019226  test    eax, 0FFFF0000h
0x18001922b  jnz     short loc_180019243
0x18001922d  test    eax, eax
0x18001922f  jle     short loc_180019239
0x180019231  movzx   eax, ax
0x180019234  or      eax, 80070000h
0x180019239  and     eax, 0D02DFFFFh
0x18001923e  or      eax, 502D0000h
0x180019243  mov     r9, rdi
0x180019246  lea     r8, aGetfilesecurit; "GetFileSecurityW failed for path '%s'. "...
0x18001924d  mov     edx, eax; int
0x18001924f  lea     rcx, aUvhd; "UVHD"
0x180019256  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18001925b  lea     rdx, [rsp+88h+var_58]; struct CPathString *
0x180019260  mov     rcx, rdi; unsigned __int16 *
0x180019263  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x180019268  mov     r9d, [rsp+88h+nLength]; nLength
0x180019270  mov     rcx, rax; lpFileName
0x180019273  mov     r8, rsi; pSecurityDescriptor
0x180019276  mov     [rsp+88h+lpnLengthNeeded], rbp; lpnLengthNeeded
0x18001927b  mov     edx, 4; RequestedInformation
0x180019280  call    cs:__imp_GetFileSecurityW
0x180019286  lea     rcx, [rsp+88h+var_58]; this
0x18001928b  mov     ebx, eax
0x18001928d  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180019292  mov     eax, ebx
0x180019294  add     rsp, 68h
0x180019298  pop     rdi
0x180019299  pop     rsi
0x18001929a  pop     rbp
0x18001929b  pop     rbx
0x18001929c  retn
```
