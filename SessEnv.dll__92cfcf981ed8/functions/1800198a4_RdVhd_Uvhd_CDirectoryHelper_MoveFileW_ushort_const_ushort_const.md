# RdVhd::Uvhd::CDirectoryHelper::MoveFileW(ushort const *,ushort const *)

- ea: `0x1800198a4`
- end: `0x1800199b3`
- name: `?MoveFileW@CDirectoryHelper@Uvhd@RdVhd@@AEBAHPEBG0@Z`
- size: `271`
- prototype: `int(RdVhd::Uvhd::CDirectoryHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18004eb08`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x1800198a4`
- `0x180019b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019926`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800198c1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18001998b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800198c1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18001998b`

## string_xrefs

- `0x180019955`: `MoveFileW failed for paths '%s' '%s'. Trying with long path`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::MoveFileW(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  signed int LastError; // eax
  const WCHAR *v7; // rbx
  const WCHAR *v8; // rax
  void **v10; // [rsp+30h] [rbp-19h] BYREF
  int v11; // [rsp+38h] [rbp-11h]
  __int64 v12; // [rsp+3Ch] [rbp-Dh]
  int v13; // [rsp+44h] [rbp-5h]
  __int64 v14; // [rsp+48h] [rbp-1h]
  int v15; // [rsp+50h] [rbp+7h]
  void **v16; // [rsp+58h] [rbp+Fh] BYREF
  int v17; // [rsp+60h] [rbp+17h]
  __int64 v18; // [rsp+64h] [rbp+1Bh]
  int v19; // [rsp+6Ch] [rbp+23h]
  __int64 v20; // [rsp+70h] [rbp+27h]
  int v21; // [rsp+78h] [rbp+2Fh]

  v5 = MoveFileW(a2, a3);
  if ( !v5 && GetLastError() == 3 )
  {
    v18 = 128;
    v21 = 0x8000000;
    v16 = &CPathString::`vftable';
    v15 = 0x8000000;
    v10 = &CPathString::`vftable';
    v20 = 0;
    v19 = 0;
    v17 = 0;
    v12 = 128;
    v14 = 0;
    v13 = 0;
    v11 = 0;
    LastError = GetLastError();
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LastError = LastError & 0x8000FFFF | 0x50300000;
    }
    _TraceNrmRdvVmEx(L"UVHD", (unsigned int)LastError, L"MoveFileW failed for paths '%s' '%s'. Trying with long path");
    v7 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a3, (struct CPathString *)&v10);
    v8 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a2, (struct CPathString *)&v16);
    v5 = MoveFileW(v8, v7);
    CPathString::~CPathString((CPathString *)&v10);
    CPathString::~CPathString((CPathString *)&v16);
  }
  return v5;
}

```

## disassembly

```asm
0x1800198a4  push    rbp
0x1800198a6  push    rbx
0x1800198a7  push    rsi
0x1800198a8  push    rdi
0x1800198a9  lea     rbp, [rsp-3Fh]
0x1800198ae  sub     rsp, 88h
0x1800198b5  mov     rdi, r8
0x1800198b8  mov     rsi, rdx
0x1800198bb  mov     rdx, r8; lpNewFileName
0x1800198be  mov     rcx, rsi; lpExistingFileName
0x1800198c1  call    cs:__imp_MoveFileW
0x1800198c7  mov     ebx, eax
0x1800198c9  test    eax, eax
0x1800198cb  jnz     loc_1800199A5
0x1800198d1  call    cs:__imp_GetLastError
0x1800198d7  cmp     eax, 3
0x1800198da  jnz     loc_1800199A5
0x1800198e0  mov     ecx, 8000000h
0x1800198e5  mov     [rbp+57h+var_3C], 80h
0x1800198ed  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x1800198f4  mov     [rbp+57h+var_28], ecx
0x1800198f7  mov     [rbp+57h+var_48], rax
0x1800198fb  mov     [rbp+57h+var_50], ecx
0x1800198fe  mov     [rbp+57h+var_70], rax
0x180019902  mov     [rbp+57h+var_30], 0
0x18001990a  mov     [rbp+57h+var_34], ebx
0x18001990d  mov     [rbp+57h+var_40], ebx
0x180019910  mov     [rbp+57h+var_64], 80h
0x180019918  mov     [rbp+57h+var_58], 0
0x180019920  mov     [rbp+57h+var_5C], ebx
0x180019923  mov     [rbp+57h+var_68], ebx
0x180019926  call    cs:__imp_GetLastError
0x18001992c  test    eax, eax
0x18001992e  jz      short loc_18001994D
0x180019930  test    eax, 0FFFF0000h
0x180019935  jnz     short loc_18001994D
0x180019937  test    eax, eax
0x180019939  jle     short loc_180019943
0x18001993b  movzx   eax, ax
0x18001993e  or      eax, 80070000h
0x180019943  and     eax, 0D030FFFFh
0x180019948  or      eax, 50300000h
0x18001994d  mov     r9, rsi
0x180019950  mov     [rsp+0A0h+var_80], rdi
0x180019955  lea     r8, aMovefilewFaile; "MoveFileW failed for paths '%s' '%s'. T"...
0x18001995c  mov     edx, eax; int
0x18001995e  lea     rcx, aUvhd; "UVHD"
0x180019965  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18001996a  lea     rdx, [rbp+57h+var_70]; struct CPathString *
0x18001996e  mov     rcx, rdi; unsigned __int16 *
0x180019971  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x180019976  lea     rdx, [rbp+57h+var_48]; struct CPathString *
0x18001997a  mov     rcx, rsi; unsigned __int16 *
0x18001997d  mov     rbx, rax
0x180019980  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x180019985  mov     rdx, rbx; lpNewFileName
0x180019988  mov     rcx, rax; lpExistingFileName
0x18001998b  call    cs:__imp_MoveFileW
0x180019991  lea     rcx, [rbp+57h+var_70]; this
0x180019995  mov     ebx, eax
0x180019997  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18001999c  lea     rcx, [rbp+57h+var_48]; this
0x1800199a0  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800199a5  mov     eax, ebx
0x1800199a7  add     rsp, 88h
0x1800199ae  pop     rdi
0x1800199af  pop     rsi
0x1800199b0  pop     rbx
0x1800199b1  pop     rbp
0x1800199b2  retn
```
