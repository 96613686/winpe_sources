# RdVhd::Uvhd::CDirectoryHelper::DeleteFileW(ushort const *)

- ea: `0x18004de00`
- end: `0x18004dfd7`
- name: `?DeleteFileW@CDirectoryHelper@Uvhd@RdVhd@@UEBAJPEBG@Z`
- size: `471`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CDirectoryHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18004cfd0`
- `0x18004da10`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x1800197c0`
- `0x180019b00`
- `0x1800488e4`
- `0x180048b28`
- `0x18004de00`
- `0x18004e6a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004deb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004deb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df48`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004df3e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004df3e`

## string_xrefs

- `0x18004de72`: `szFileToDelete`
- `0x18004df74`: `::DeleteFileW(%s)`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::DeleteFileW(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2)
{
  signed int v4; // ebx
  unsigned int FileAttributesW; // eax
  signed int LastError; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v7; // rcx
  __int64 v8; // rdx
  const WCHAR *v9; // rax
  signed int v10; // eax
  void **v12; // [rsp+20h] [rbp-38h] BYREF
  int v13; // [rsp+28h] [rbp-30h]
  __int64 v14; // [rsp+2Ch] [rbp-2Ch]
  int v15; // [rsp+34h] [rbp-24h]
  __int64 v16; // [rsp+38h] [rbp-20h]
  int v17; // [rsp+40h] [rbp-18h]

  v14 = 128;
  v16 = 0;
  v15 = 0;
  v17 = 0x8000000;
  v13 = 0;
  v12 = &CPathString::`vftable';
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids,
        L"szFileToDelete");
    }
    v4 = -2147024809;
    goto LABEL_32;
  }
  FileAttributesW = RdVhd::Uvhd::CDirectoryHelper::GetFileAttributesW(this, a2);
  if ( FileAttributesW == -1 )
  {
    v4 = 1;
    goto LABEL_32;
  }
  v4 = 0;
  if ( !RdVhd::Uvhd::CDirectoryHelper::SetFileAttributesW(this, a2, FileAttributesW & 0xFFFFFFF8) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v4 = v4 & 0x8000FFFF | 0x500A0000;
    }
    if ( v4 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_32;
      }
      v8 = 51;
LABEL_19:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, (unsigned int)v4);
      goto LABEL_32;
    }
  }
  v9 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a2, (struct CPathString *)&v12);
  if ( !DeleteFileW(v9) )
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 && (v10 & 0xFFFF0000) == 0 )
    {
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
      v4 = v4 & 0x8000FFFF | 0x500B0000;
    }
    _TraceNrmRdvVmEx(L"UVHD", (unsigned int)v4, L"::DeleteFileW(%s)");
    if ( v4 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 52;
        goto LABEL_19;
      }
    }
  }
LABEL_32:
  CPathString::~CPathString((CPathString *)&v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004de00  mov     rax, rsp
0x18004de03  mov     [rax+8], rbx
0x18004de07  mov     [rax+10h], rsi
0x18004de0b  push    rdi
0x18004de0c  sub     rsp, 50h
0x18004de10  mov     qword ptr [rax-2Ch], 80h
0x18004de18  mov     rdi, rdx
0x18004de1b  mov     qword ptr [rax-20h], 0
0x18004de23  mov     rsi, rcx
0x18004de26  mov     dword ptr [rax-24h], 0
0x18004de2d  mov     dword ptr [rax-18h], 8000000h
0x18004de34  mov     dword ptr [rax-30h], 0
0x18004de3b  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x18004de42  mov     [rsp+58h+var_38], rax
0x18004de47  test    rdx, rdx
0x18004de4a  jnz     short loc_18004DE8F
0x18004de4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004de53  lea     rax, WPP_GLOBAL_Control
0x18004de5a  cmp     rcx, rax
0x18004de5d  jz      short loc_18004DE85
0x18004de5f  test    byte ptr [rcx+1Ch], 4
0x18004de63  jz      short loc_18004DE85
0x18004de65  cmp     byte ptr [rcx+19h], 2
0x18004de69  jb      short loc_18004DE85
0x18004de6b  mov     rcx, [rcx+10h]
0x18004de6f  lea     edx, [rdi+32h]
0x18004de72  lea     r9, aSzfiletodelete; "szFileToDelete"
0x18004de79  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004de80  call    WPP_SF_S
0x18004de85  mov     ebx, 80070057h
0x18004de8a  jmp     loc_18004DFBB
0x18004de8f  call    ?GetFileAttributesW@CDirectoryHelper@Uvhd@RdVhd@@UEBAKPEBG@Z; RdVhd::Uvhd::CDirectoryHelper::GetFileAttributesW(ushort const *)
0x18004de94  cmp     eax, 0FFFFFFFFh
0x18004de97  jz      loc_18004DFB6
0x18004de9d  and     eax, 0FFFFFFF8h
0x18004dea0  mov     rdx, rdi; unsigned __int16 *
0x18004dea3  mov     r8d, eax; unsigned int
0x18004dea6  mov     rcx, rsi; this
0x18004dea9  xor     ebx, ebx
0x18004deab  call    ?SetFileAttributesW@CDirectoryHelper@Uvhd@RdVhd@@UEBAHPEBGK@Z; RdVhd::Uvhd::CDirectoryHelper::SetFileAttributesW(ushort const *,ulong)
0x18004deb0  mov     esi, 0FFFF0000h
0x18004deb5  test    eax, eax
0x18004deb7  jnz     short loc_18004DF2E
0x18004deb9  call    cs:__imp_GetLastError
0x18004debf  mov     ebx, eax
0x18004dec1  test    eax, eax
0x18004dec3  jz      short loc_18004DEE2
0x18004dec5  test    esi, eax
0x18004dec7  jnz     short loc_18004DEE2
0x18004dec9  test    eax, eax
0x18004decb  jle     short loc_18004DED6
0x18004decd  movzx   ebx, ax
0x18004ded0  or      ebx, 80070000h
0x18004ded6  and     ebx, 0D00AFFFFh
0x18004dedc  or      ebx, 500A0000h
0x18004dee2  test    ebx, ebx
0x18004dee4  jns     short loc_18004DF2E
0x18004dee6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004deed  lea     rax, WPP_GLOBAL_Control
0x18004def4  cmp     rcx, rax
0x18004def7  jz      loc_18004DFBB
0x18004defd  test    byte ptr [rcx+1Ch], 4
0x18004df01  jz      loc_18004DFBB
0x18004df07  cmp     byte ptr [rcx+19h], 2
0x18004df0b  jb      loc_18004DFBB
0x18004df11  mov     edx, 33h ; '3'
0x18004df16  mov     rcx, [rcx+10h]
0x18004df1a  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004df21  mov     r9d, ebx
0x18004df24  call    WPP_SF_d
0x18004df29  jmp     loc_18004DFBB
0x18004df2e  lea     rdx, [rsp+58h+var_38]; struct CPathString *
0x18004df33  mov     rcx, rdi; unsigned __int16 *
0x18004df36  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x18004df3b  mov     rcx, rax; lpFileName
0x18004df3e  call    cs:__imp_DeleteFileW
0x18004df44  test    eax, eax
0x18004df46  jnz     short loc_18004DFBB
0x18004df48  call    cs:__imp_GetLastError
0x18004df4e  mov     ebx, eax
0x18004df50  test    eax, eax
0x18004df52  jz      short loc_18004DF71
0x18004df54  test    esi, eax
0x18004df56  jnz     short loc_18004DF71
0x18004df58  test    eax, eax
0x18004df5a  jle     short loc_18004DF65
0x18004df5c  movzx   ebx, ax
0x18004df5f  or      ebx, 80070000h
0x18004df65  and     ebx, 0D00BFFFFh
0x18004df6b  or      ebx, 500B0000h
0x18004df71  mov     r9, rdi
0x18004df74  lea     r8, aDeletefilewS; "::DeleteFileW(%s)"
0x18004df7b  mov     edx, ebx; int
0x18004df7d  lea     rcx, aUvhd; "UVHD"
0x18004df84  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18004df89  test    ebx, ebx
0x18004df8b  jns     short loc_18004DFBB
0x18004df8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004df94  lea     rax, WPP_GLOBAL_Control
0x18004df9b  cmp     rcx, rax
0x18004df9e  jz      short loc_18004DFBB
0x18004dfa0  test    byte ptr [rcx+1Ch], 4
0x18004dfa4  jz      short loc_18004DFBB
0x18004dfa6  cmp     byte ptr [rcx+19h], 2
0x18004dfaa  jb      short loc_18004DFBB
0x18004dfac  mov     edx, 34h ; '4'
0x18004dfb1  jmp     loc_18004DF16
0x18004dfb6  mov     ebx, 1
0x18004dfbb  lea     rcx, [rsp+58h+var_38]; this
0x18004dfc0  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18004dfc5  mov     rsi, [rsp+58h+arg_8]
0x18004dfca  mov     eax, ebx
0x18004dfcc  mov     rbx, [rsp+58h+arg_0]
0x18004dfd1  add     rsp, 50h
0x18004dfd5  pop     rdi
0x18004dfd6  retn
```
