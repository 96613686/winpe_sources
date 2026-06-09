# RdVhd::Uvhd::CDirectoryHelper::RemoveDirectoryW(ushort const *)

- ea: `0x180018bd8`
- end: `0x180018ca3`
- name: `?RemoveDirectoryW@CDirectoryHelper@Uvhd@RdVhd@@AEBAHPEBG@Z`
- size: `203`
- prototype: `int(RdVhd::Uvhd::CDirectoryHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18004dfe0`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180018bd8`
- `0x180019b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c35`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018be8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018c84`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018be8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018c84`

## string_xrefs

- `0x180018c5f`: `RemoveDirectoryW failed for path '%s'. Trying with long path`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::RemoveDirectoryW(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  signed int LastError; // eax
  const WCHAR *v5; // rax
  void **v7; // [rsp+20h] [rbp-38h] BYREF
  int v8; // [rsp+28h] [rbp-30h]
  __int64 v9; // [rsp+2Ch] [rbp-2Ch]
  int v10; // [rsp+34h] [rbp-24h]
  __int64 v11; // [rsp+38h] [rbp-20h]
  int v12; // [rsp+40h] [rbp-18h]

  v3 = RemoveDirectoryW(a2);
  if ( !v3 && GetLastError() == 3 )
  {
    v9 = 128;
    v7 = &CPathString::`vftable';
    v11 = 0;
    v10 = 0;
    v12 = 0x8000000;
    v8 = 0;
    LastError = GetLastError();
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LastError = LastError & 0x8000FFFF | 0x502F0000;
    }
    _TraceNrmRdvVmEx(L"UVHD", (unsigned int)LastError, L"RemoveDirectoryW failed for path '%s'. Trying with long path");
    v5 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a2, (struct CPathString *)&v7);
    v3 = RemoveDirectoryW(v5);
    CPathString::~CPathString((CPathString *)&v7);
  }
  return v3;
}

```

## disassembly

```asm
0x180018bd8  mov     [rsp+arg_0], rbx
0x180018bdd  push    rdi
0x180018bde  sub     rsp, 50h
0x180018be2  mov     rdi, rdx
0x180018be5  mov     rcx, rdx; lpPathName
0x180018be8  call    cs:__imp_RemoveDirectoryW
0x180018bee  mov     ebx, eax
0x180018bf0  test    eax, eax
0x180018bf2  jnz     loc_180018C96
0x180018bf8  call    cs:__imp_GetLastError
0x180018bfe  cmp     eax, 3
0x180018c01  jnz     loc_180018C96
0x180018c07  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180018c0e  mov     [rsp+58h+var_2C], 80h
0x180018c17  mov     [rsp+58h+var_38], rax
0x180018c1c  mov     [rsp+58h+var_20], 0
0x180018c25  mov     [rsp+58h+var_24], ebx
0x180018c29  mov     [rsp+58h+var_18], 8000000h
0x180018c31  mov     [rsp+58h+var_30], ebx
0x180018c35  call    cs:__imp_GetLastError
0x180018c3b  test    eax, eax
0x180018c3d  jz      short loc_180018C5C
0x180018c3f  test    eax, 0FFFF0000h
0x180018c44  jnz     short loc_180018C5C
0x180018c46  test    eax, eax
0x180018c48  jle     short loc_180018C52
0x180018c4a  movzx   eax, ax
0x180018c4d  or      eax, 80070000h
0x180018c52  and     eax, 0D02FFFFFh
0x180018c57  or      eax, 502F0000h
0x180018c5c  mov     r9, rdi
0x180018c5f  lea     r8, aRemovedirector_1; "RemoveDirectoryW failed for path '%s'. "...
0x180018c66  mov     edx, eax; int
0x180018c68  lea     rcx, aUvhd; "UVHD"
0x180018c6f  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180018c74  lea     rdx, [rsp+58h+var_38]; struct CPathString *
0x180018c79  mov     rcx, rdi; unsigned __int16 *
0x180018c7c  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x180018c81  mov     rcx, rax; lpPathName
0x180018c84  call    cs:__imp_RemoveDirectoryW
0x180018c8a  lea     rcx, [rsp+58h+var_38]; this
0x180018c8f  mov     ebx, eax
0x180018c91  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180018c96  mov     eax, ebx
0x180018c98  mov     rbx, [rsp+58h+arg_0]
0x180018c9d  add     rsp, 50h
0x180018ca1  pop     rdi
0x180018ca2  retn
```
