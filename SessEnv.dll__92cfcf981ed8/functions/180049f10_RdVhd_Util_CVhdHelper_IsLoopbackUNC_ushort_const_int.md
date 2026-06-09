# RdVhd::Util::CVhdHelper::IsLoopbackUNC(ushort const *,int *)

- ea: `0x180049f10`
- end: `0x18004a239`
- name: `?IsLoopbackUNC@CVhdHelper@Util@RdVhd@@IEBAJPEBGPEAH@Z`
- size: `809`
- prototype: `__int64 __fastcall(RdVhd::Util::CVhdHelper *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004b0a4`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180019b38`
- `0x18001a280`
- `0x18001ad5c`
- `0x18003114c`
- `0x1800488e4`
- `0x180048ab0`
- `0x180048b28`
- `0x180049f10`
- `0x18004a240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a168`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a204`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a204`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a0a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a0a2`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18004a15a`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18004a15a`

## string_xrefs

- `0x180049fb0`: `szPath`
- `0x18004a0d6`: `Failed ::CreateFileW(%s)`

## pseudocode

```c
__int64 __fastcall RdVhd::Util::CVhdHelper::IsLoopbackUNC(
        RdVhd::Util::CVhdHelper *this,
        const unsigned __int16 *a2,
        int *a3)
{
  RdVhd::Uvhd::CUvhdDiskManager *v5; // rcx
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  int v8; // ebx
  const WCHAR *v9; // rax
  HANDLE FileW; // rsi
  signed int LastError; // eax
  int v12; // eax
  signed int v13; // eax
  int v14; // eax
  void **v16; // [rsp+40h] [rbp-79h] BYREF
  int v17; // [rsp+48h] [rbp-71h]
  __int64 v18; // [rsp+4Ch] [rbp-6Dh]
  int v19; // [rsp+54h] [rbp-65h]
  __int64 v20; // [rsp+58h] [rbp-61h]
  int v21; // [rsp+60h] [rbp-59h]
  _BYTE FileInformation[2]; // [rsp+70h] [rbp-49h] BYREF
  __int16 v23; // [rsp+72h] [rbp-47h]
  char v24; // [rsp+80h] [rbp-39h]

  v18 = 128;
  v20 = 0;
  v19 = 0;
  v21 = 0x8000000;
  v17 = 0;
  v16 = &CPathString::`vftable';
  memset_0(FileInformation, 0, 0x74u);
  v23 = 116;
  if ( !a2 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 131;
    v7 = L"szPath";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v5 + 2), v6, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, v7);
LABEL_7:
    v8 = -2147024809;
    goto LABEL_39;
  }
  if ( !a3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 132;
    v7 = L"pfLoopbackUNC";
    goto LABEL_6;
  }
  *a3 = 0;
  v8 = CBaseStringT<unsigned short>::Append((__int64)&v16, (__int64)a2);
  if ( v8 >= 0 )
  {
    if ( (unsigned int)CPathString::IsUNC((CPathString *)&v16) )
    {
      v9 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v16);
      FileW = CreateFileW(v9, 0, 1u, 0, 3u, 0, 0);
      if ( FileW != (HANDLE)-1LL )
        goto LABEL_42;
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      CBaseStringT<unsigned short>::PContents(&v16);
      _TraceNrmRdvVmEx(L"VHDHLP", (unsigned int)v8, L"Failed ::CreateFileW(%s)");
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = CBaseStringT<unsigned short>::PContents(&v16);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            134,
            (unsigned int)WPP_cd119b7af839377e03a1eca67cd76764_Traceguids,
            v12,
            v8);
        }
      }
      else
      {
LABEL_42:
        if ( GetFileInformationByHandleEx(FileW, FileRemoteProtocolInfo, FileInformation, 0x74u) )
          goto LABEL_35;
        v13 = GetLastError();
        v8 = v13;
        if ( v13 > 0 )
          v8 = (unsigned __int16)v13 | 0x80070000;
        CBaseStringT<unsigned short>::PContents(&v16);
        _TraceNrmRdvVmEx(L"VHDHLP", (unsigned int)v8, L"Failed ::GetFileInformationByHandleEx(%s)");
        if ( v8 >= 0 )
        {
LABEL_35:
          if ( (v24 & 1) != 0 )
            *a3 = 1;
        }
        else if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = CBaseStringT<unsigned short>::PContents(&v16);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            135,
            (unsigned int)WPP_cd119b7af839377e03a1eca67cd76764_Traceguids,
            v14,
            v8);
        }
        if ( FileW != (HANDLE)-1LL )
          CloseHandle(FileW);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      133,
      WPP_cd119b7af839377e03a1eca67cd76764_Traceguids,
      (unsigned int)v8);
  }
LABEL_39:
  CPathString::~CPathString((CPathString *)&v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180049f10  mov     [rsp-8+arg_0], rbx
0x180049f15  mov     [rsp-8+arg_18], rsi
0x180049f1a  push    rbp
0x180049f1b  push    rdi
0x180049f1c  push    r12
0x180049f1e  lea     rbp, [rsp-47h]
0x180049f23  sub     rsp, 100h
0x180049f2a  mov     rax, cs:__security_cookie
0x180049f31  xor     rax, rsp
0x180049f34  mov     [rbp+57h+var_20], rax
0x180049f38  mov     rdi, r8
0x180049f3b  mov     [rbp+57h+var_C4], 80h
0x180049f43  mov     rbx, rdx
0x180049f46  mov     [rbp+57h+var_B8], 0
0x180049f4e  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180049f55  mov     [rbp+57h+var_BC], 0
0x180049f5c  mov     r12d, 74h ; 't'
0x180049f62  mov     [rbp+57h+var_B0], 8000000h
0x180049f69  mov     r8d, r12d; Size
0x180049f6c  mov     [rbp+57h+var_C8], 0
0x180049f73  xor     edx, edx; Val
0x180049f75  mov     [rbp+57h+var_D0], rax
0x180049f79  lea     rcx, [rbp+57h+FileInformation]; void *
0x180049f7d  call    memset_0
0x180049f82  mov     [rbp+57h+var_9E], r12w
0x180049f87  test    rbx, rbx
0x180049f8a  jnz     short loc_180049FD1
0x180049f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f93  lea     rax, WPP_GLOBAL_Control
0x180049f9a  cmp     rcx, rax
0x180049f9d  jz      short loc_180049FC7
0x180049f9f  test    byte ptr [rcx+1Ch], 1
0x180049fa3  jz      short loc_180049FC7
0x180049fa5  cmp     byte ptr [rcx+19h], 2
0x180049fa9  jb      short loc_180049FC7
0x180049fab  lea     edx, [r12+0Fh]
0x180049fb0  lea     r9, aSzpath; "szPath"
0x180049fb7  mov     rcx, [rcx+10h]
0x180049fbb  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x180049fc2  call    WPP_SF_S
0x180049fc7  mov     ebx, 80070057h
0x180049fcc  jmp     loc_18004A20A
0x180049fd1  test    rdi, rdi
0x180049fd4  jnz     short loc_18004A003
0x180049fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180049fdd  lea     rax, WPP_GLOBAL_Control
0x180049fe4  cmp     rcx, rax
0x180049fe7  jz      short loc_180049FC7
0x180049fe9  test    byte ptr [rcx+1Ch], 1
0x180049fed  jz      short loc_180049FC7
0x180049fef  cmp     byte ptr [rcx+19h], 2
0x180049ff3  jb      short loc_180049FC7
0x180049ff5  mov     edx, 84h
0x180049ffa  lea     r9, aPfloopbackunc; "pfLoopbackUNC"
0x18004a001  jmp     short loc_180049FB7
0x18004a003  mov     rdx, rbx
0x18004a006  mov     dword ptr [rdi], 0
0x18004a00c  lea     rcx, [rbp+57h+var_D0]
0x18004a010  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x18004a015  mov     ebx, eax
0x18004a017  test    eax, eax
0x18004a019  jns     short loc_18004A063
0x18004a01b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a022  lea     rax, WPP_GLOBAL_Control
0x18004a029  cmp     rcx, rax
0x18004a02c  jz      loc_18004A20A
0x18004a032  test    byte ptr [rcx+1Ch], 1
0x18004a036  jz      loc_18004A20A
0x18004a03c  cmp     byte ptr [rcx+19h], 2
0x18004a040  jb      loc_18004A20A
0x18004a046  mov     rcx, [rcx+10h]
0x18004a04a  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004a051  mov     edx, 85h
0x18004a056  mov     r9d, ebx
0x18004a059  call    WPP_SF_d
0x18004a05e  jmp     loc_18004A20A
0x18004a063  lea     rcx, [rbp+57h+var_D0]; this
0x18004a067  call    ?IsUNC@CPathString@@QEAAHXZ; CPathString::IsUNC(void)
0x18004a06c  test    eax, eax
0x18004a06e  jz      loc_18004A20A
0x18004a074  lea     rcx, [rbp+57h+var_D0]
0x18004a078  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004a07d  xor     r9d, r9d; lpSecurityAttributes
0x18004a080  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x18004a089  mov     rcx, rax; lpFileName
0x18004a08c  mov     [rsp+110h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004a094  xor     edx, edx; dwDesiredAccess
0x18004a096  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x18004a09e  lea     r8d, [r9+1]; dwShareMode
0x18004a0a2  call    cs:__imp_CreateFileW
0x18004a0a8  mov     rsi, rax
0x18004a0ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a0af  jnz     loc_18004A14B
0x18004a0b5  call    cs:__imp_GetLastError
0x18004a0bb  mov     ebx, eax
0x18004a0bd  test    eax, eax
0x18004a0bf  jle     short loc_18004A0CA
0x18004a0c1  movzx   ebx, ax
0x18004a0c4  or      ebx, 80070000h
0x18004a0ca  lea     rcx, [rbp+57h+var_D0]
0x18004a0ce  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004a0d3  mov     r9, rax
0x18004a0d6  lea     r8, aFailedCreatefi; "Failed ::CreateFileW(%s)"
0x18004a0dd  mov     edx, ebx; int
0x18004a0df  lea     rcx, aVhdhlp; "VHDHLP"
0x18004a0e6  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18004a0eb  test    ebx, ebx
0x18004a0ed  jns     short loc_18004A14B
0x18004a0ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a0f6  lea     rax, WPP_GLOBAL_Control
0x18004a0fd  cmp     rcx, rax
0x18004a100  jz      loc_18004A20A
0x18004a106  test    byte ptr [rcx+1Ch], 1
0x18004a10a  jz      loc_18004A20A
0x18004a110  cmp     byte ptr [rcx+19h], 2
0x18004a114  jb      loc_18004A20A
0x18004a11a  lea     rcx, [rbp+57h+var_D0]
0x18004a11e  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004a123  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a12a  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004a131  mov     edx, 86h
0x18004a136  mov     [rsp+110h+dwCreationDisposition], ebx
0x18004a13a  mov     r9, rax
0x18004a13d  mov     rcx, [rcx+10h]
0x18004a141  call    WPP_SF_Sd
0x18004a146  jmp     loc_18004A20A
0x18004a14b  mov     r9d, r12d; dwBufferSize
0x18004a14e  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18004a152  mov     edx, 0Dh; FileInformationClass
0x18004a157  mov     rcx, rsi; hFile
0x18004a15a  call    cs:__imp_GetFileInformationByHandleEx
0x18004a160  test    eax, eax
0x18004a162  jnz     loc_18004A1EF
0x18004a168  call    cs:__imp_GetLastError
0x18004a16e  mov     ebx, eax
0x18004a170  test    eax, eax
0x18004a172  jle     short loc_18004A17D
0x18004a174  movzx   ebx, ax
0x18004a177  or      ebx, 80070000h
0x18004a17d  lea     rcx, [rbp+57h+var_D0]
0x18004a181  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004a186  mov     r9, rax
0x18004a189  lea     r8, aFailedGetfilei; "Failed ::GetFileInformationByHandleEx(%"...
0x18004a190  mov     edx, ebx; int
0x18004a192  lea     rcx, aVhdhlp; "VHDHLP"
0x18004a199  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18004a19e  test    ebx, ebx
0x18004a1a0  jns     short loc_18004A1EF
0x18004a1a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a1a9  lea     rax, WPP_GLOBAL_Control
0x18004a1b0  cmp     rcx, rax
0x18004a1b3  jz      short loc_18004A1FB
0x18004a1b5  test    byte ptr [rcx+1Ch], 1
0x18004a1b9  jz      short loc_18004A1FB
0x18004a1bb  cmp     byte ptr [rcx+19h], 2
0x18004a1bf  jb      short loc_18004A1FB
0x18004a1c1  lea     rcx, [rbp+57h+var_D0]
0x18004a1c5  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004a1ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a1d1  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004a1d8  mov     edx, 87h
0x18004a1dd  mov     [rsp+110h+dwCreationDisposition], ebx
0x18004a1e1  mov     r9, rax
0x18004a1e4  mov     rcx, [rcx+10h]
0x18004a1e8  call    WPP_SF_Sd
0x18004a1ed  jmp     short loc_18004A1FB
0x18004a1ef  test    [rbp+57h+var_90], 1
0x18004a1f3  jz      short loc_18004A1FB
0x18004a1f5  mov     dword ptr [rdi], 1
0x18004a1fb  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004a1ff  jz      short loc_18004A20A
0x18004a201  mov     rcx, rsi; hObject
0x18004a204  call    cs:__imp_CloseHandle
0x18004a20a  lea     rcx, [rbp+57h+var_D0]; this
0x18004a20e  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18004a213  mov     eax, ebx
0x18004a215  mov     rcx, [rbp+57h+var_20]
0x18004a219  xor     rcx, rsp; StackCookie
0x18004a21c  call    __security_check_cookie
0x18004a221  lea     r11, [rsp+110h+var_10]
0x18004a229  mov     rbx, [r11+20h]
0x18004a22d  mov     rsi, [r11+38h]
0x18004a231  mov     rsp, r11
0x18004a234  pop     r12
0x18004a236  pop     rdi
0x18004a237  pop     rbp
0x18004a238  retn
```
