# RdVhd::Uvhd::CDirectoryHelper::CreateFileW(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x180018f8c`
- end: `0x1800190b2`
- name: `?CreateFileW@CDirectoryHelper@Uvhd@RdVhd@@AEBAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `294`
- prototype: `HANDLE __fastcall(RdVhd::Uvhd::CDirectoryHelper *this, const unsigned __int16 *, __int64, __int64, struct _SECURITY_ATTRIBUTES *lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004d1d0`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180018f8c`
- `0x180019b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019019`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018fc1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001908e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018fc1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001908e`

## string_xrefs

- `0x180019043`: `CreateFileW failed for path '%s'. Trying with long path`

## pseudocode

```c
HANDLE __fastcall RdVhd::Uvhd::CDirectoryHelper::CreateFileW(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes)
{
  HANDLE FileW; // rbx
  signed int LastError; // eax
  const WCHAR *v8; // rax
  void **v10; // [rsp+40h] [rbp-38h] BYREF
  int v11; // [rsp+48h] [rbp-30h]
  __int64 v12; // [rsp+4Ch] [rbp-2Ch]
  int v13; // [rsp+54h] [rbp-24h]
  __int64 v14; // [rsp+58h] [rbp-20h]
  int v15; // [rsp+60h] [rbp-18h]

  FileW = CreateFileW(a2, 0, 0, lpSecurityAttributes, 1u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL && GetLastError() == 3 )
  {
    v12 = 128;
    v10 = &CPathString::`vftable';
    v14 = 0;
    v13 = 0;
    v15 = 0x8000000;
    v11 = 0;
    LastError = GetLastError();
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LastError = LastError & 0x8000FFFF | 0x502B0000;
    }
    _TraceNrmRdvVmEx(L"UVHD", (unsigned int)LastError, L"CreateFileW failed for path '%s'. Trying with long path");
    v8 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a2, (struct CPathString *)&v10);
    FileW = CreateFileW(v8, 0, 0, lpSecurityAttributes, 1u, 0x80u, 0);
    CPathString::~CPathString((CPathString *)&v10);
  }
  return FileW;
}

```

## disassembly

```asm
0x180018f8c  mov     rax, rsp
0x180018f8f  mov     [rax+8], rbx
0x180018f93  push    rdi
0x180018f94  sub     rsp, 70h
0x180018f98  mov     rdi, rdx
0x180018f9b  mov     r9, [rsp+78h+lpSecurityAttributes]; lpSecurityAttributes
0x180018fa3  xor     r8d, r8d; dwShareMode
0x180018fa6  mov     qword ptr [rax-48h], 0
0x180018fae  xor     edx, edx; dwDesiredAccess
0x180018fb0  mov     dword ptr [rax-50h], 80h
0x180018fb7  mov     rcx, rdi; lpFileName
0x180018fba  mov     dword ptr [rax-58h], 1
0x180018fc1  call    cs:__imp_CreateFileW
0x180018fc7  mov     rbx, rax
0x180018fca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018fce  jnz     loc_1800190A1
0x180018fd4  call    cs:__imp_GetLastError
0x180018fda  cmp     eax, 3
0x180018fdd  jnz     loc_1800190A1
0x180018fe3  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180018fea  mov     [rsp+78h+var_2C], 80h
0x180018ff3  mov     [rsp+78h+var_38], rax
0x180018ff8  mov     [rsp+78h+var_20], 0
0x180019001  mov     [rsp+78h+var_24], 0
0x180019009  mov     [rsp+78h+var_18], 8000000h
0x180019011  mov     [rsp+78h+var_30], 0
0x180019019  call    cs:__imp_GetLastError
0x18001901f  test    eax, eax
0x180019021  jz      short loc_180019040
0x180019023  test    eax, 0FFFF0000h
0x180019028  jnz     short loc_180019040
0x18001902a  test    eax, eax
0x18001902c  jle     short loc_180019036
0x18001902e  movzx   eax, ax
0x180019031  or      eax, 80070000h
0x180019036  and     eax, 0D02BFFFFh
0x18001903b  or      eax, 502B0000h
0x180019040  mov     r9, rdi
0x180019043  lea     r8, aCreatefilewFai; "CreateFileW failed for path '%s'. Tryin"...
0x18001904a  mov     edx, eax; int
0x18001904c  lea     rcx, aUvhd; "UVHD"
0x180019053  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180019058  lea     rdx, [rsp+78h+var_38]; struct CPathString *
0x18001905d  mov     rcx, rdi; unsigned __int16 *
0x180019060  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x180019065  mov     r9, [rsp+78h+lpSecurityAttributes]; lpSecurityAttributes
0x18001906d  mov     rcx, rax; lpFileName
0x180019070  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180019079  xor     r8d, r8d; dwShareMode
0x18001907c  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180019084  xor     edx, edx; dwDesiredAccess
0x180019086  mov     [rsp+78h+dwCreationDisposition], 1; dwCreationDisposition
0x18001908e  call    cs:__imp_CreateFileW
0x180019094  lea     rcx, [rsp+78h+var_38]; this
0x180019099  mov     rbx, rax
0x18001909c  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800190a1  mov     rax, rbx
0x1800190a4  mov     rbx, [rsp+78h+arg_0]
0x1800190ac  add     rsp, 70h
0x1800190b0  pop     rdi
0x1800190b1  retn
```
