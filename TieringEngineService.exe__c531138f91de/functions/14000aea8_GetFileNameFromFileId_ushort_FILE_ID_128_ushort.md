# GetFileNameFromFileId(ushort *,_FILE_ID_128 *,ushort *)

- ea: `0x14000aea8`
- end: `0x14000b0ca`
- name: `?GetFileNameFromFileId@@YAJPEAGPEAU_FILE_ID_128@@0@Z`
- size: `546`
- prototype: `__int64 __fastcall(unsigned __int16 *, union FILE_ID_DESCRIPTOR::$937871D590D7CF78B637FB7A33219D36 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path`

## callers

- `0x1400382e0`

## callees

- `0x140002db0`
- `0x140009c08`
- `0x14000aea8`
- `0x14000b880`
- `0x14000b8e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000af04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000af82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000af04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000af82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aff2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000aef8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000aef8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000afe8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000afe8`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x14000b072`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x14000b072`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x14000af76`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x14000af76`

## pseudocode

```c
__int64 __fastcall GetFileNameFromFileId(
        unsigned __int16 *a1,
        union FILE_ID_DESCRIPTOR::$937871D590D7CF78B637FB7A33219D36 *a2,
        unsigned __int16 *a3)
{
  union FILE_ID_DESCRIPTOR::$937871D590D7CF78B637FB7A33219D36 v3; // xmm0
  int v6; // esi
  HANDLE FileW; // rax
  DWORD LastError; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // r10
  int v11; // edx
  int v12; // r9d
  HANDLE v14; // rax
  DWORD v15; // eax
  unsigned int v16; // edi
  _QWORD *v17; // r8
  __int64 v18; // rdx
  DWORD FinalPathNameByHandleW; // eax
  __int64 v20; // r8
  DWORD v21; // eax
  FILE_ID_DESCRIPTOR FileId; // [rsp+40h] [rbp-28h] BYREF

  v3 = *a2;
  FileId.dwSize = 24;
  FileId.Type = ExtendedFileIdType;
  FileId.8 = v3;
  v6 = (int)a1;
  FileW = CreateFileW(a1, 0xC0000080, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = ATL::AtlHresultFromWin32(LastError);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v11 = 40;
    v12 = v6;
LABEL_6:
    WPP_SF_Sd(v10[2], v11, (unsigned int)&WPP_58242705c75132cdab80b446e38b4c82_Traceguids, v12, v9);
    return v9;
  }
  v14 = OpenFileById(FileW, &FileId, 0x80u, 0, 0, 0x80u);
  if ( v14 == (HANDLE)-1LL )
  {
    v15 = GetLastError();
    v16 = ATL::AtlHresultFromWin32(v15);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v16;
    }
    v18 = 41;
LABEL_13:
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_iid)(
      v17[2],
      v18,
      v17,
      *(_QWORD *)a2->ObjectId.Data4,
      (LARGE_INTEGER)a2->FileId.QuadPart,
      v16);
    return v16;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(v14, a3, 0x104u, 0);
  if ( !FinalPathNameByHandleW )
  {
    v21 = GetLastError();
    v16 = ATL::AtlHresultFromWin32(v21);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v16;
    }
    v18 = 42;
    goto LABEL_13;
  }
  if ( FinalPathNameByHandleW <= 0x104 )
  {
    v9 = PathCchStripPrefix(a3, 0x104u);
    if ( (v9 & 0x80000000) != 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v9;
      }
      v11 = 44;
      v12 = (int)a3;
      goto LABEL_6;
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_iidd)(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        WPP_GLOBAL_Control,
        v20,
        *(_QWORD *)a2->ObjectId.Data4,
        (LARGE_INTEGER)a2->FileId.QuadPart,
        FinalPathNameByHandleW);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14000aea8  mov     rax, rsp
0x14000aeab  mov     [rax+8], rbx
0x14000aeaf  mov     [rax+10h], rsi
0x14000aeb3  push    rdi
0x14000aeb4  sub     rsp, 60h
0x14000aeb8  movups  xmm0, xmmword ptr [rdx]
0x14000aebb  mov     qword ptr [rax-38h], 0
0x14000aec3  mov     rdi, r8
0x14000aec6  mov     rbx, rdx
0x14000aec9  mov     dword ptr [rax-40h], 0
0x14000aed0  mov     r8d, 3; dwShareMode
0x14000aed6  mov     dword ptr [rax-28h], 18h
0x14000aedd  xor     r9d, r9d; lpSecurityAttributes
0x14000aee0  mov     dword ptr [rax-24h], 2
0x14000aee7  mov     edx, 0C0000080h; dwDesiredAccess
0x14000aeec  mov     [rax-48h], r8d
0x14000aef0  movdqu  xmmword ptr [rax-20h], xmm0
0x14000aef5  mov     rsi, rcx
0x14000aef8  call    cs:__imp_CreateFileW
0x14000aefe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000af02  jnz     short loc_14000AF57
0x14000af04  call    cs:__imp_GetLastError
0x14000af0a  mov     ecx, eax; unsigned int
0x14000af0c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000af11  mov     ebx, eax
0x14000af13  mov     r10, cs:WPP_GLOBAL_Control
0x14000af1a  lea     rcx, WPP_GLOBAL_Control
0x14000af21  cmp     r10, rcx
0x14000af24  jz      short loc_14000AF50
0x14000af26  test    byte ptr [r10+1Ch], 1
0x14000af2b  jz      short loc_14000AF50
0x14000af2d  cmp     byte ptr [r10+19h], 2
0x14000af32  jb      short loc_14000AF50
0x14000af34  mov     edx, 28h ; '('
0x14000af39  mov     r9, rsi
0x14000af3c  mov     rcx, [r10+10h]
0x14000af40  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000af47  mov     dword ptr [rsp+68h+lpSecurityAttributes], ebx
0x14000af4b  call    WPP_SF_Sd
0x14000af50  mov     eax, ebx
0x14000af52  jmp     loc_14000B0BA
0x14000af57  mov     r8d, 80h; dwDesiredAccess
0x14000af5d  lea     rdx, [rsp+68h+FileId]; lpFileId
0x14000af62  mov     [rsp+68h+dwFlagsAndAttributes], r8d; dwFlagsAndAttributes
0x14000af67  xor     r9d, r9d; dwShareMode
0x14000af6a  mov     rcx, rax; hVolumeHint
0x14000af6d  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000af76  call    cs:__imp_OpenFileById
0x14000af7c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000af80  jnz     short loc_14000AFD7
0x14000af82  call    cs:__imp_GetLastError
0x14000af88  mov     ecx, eax; unsigned int
0x14000af8a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000af8f  mov     edi, eax
0x14000af91  mov     r8, cs:WPP_GLOBAL_Control
0x14000af98  lea     rcx, WPP_GLOBAL_Control
0x14000af9f  cmp     r8, rcx
0x14000afa2  jz      short loc_14000AFD0
0x14000afa4  test    byte ptr [r8+1Ch], 1
0x14000afa9  jz      short loc_14000AFD0
0x14000afab  cmp     byte ptr [r8+19h], 2
0x14000afb0  jb      short loc_14000AFD0
0x14000afb2  mov     edx, 29h ; ')'
0x14000afb7  mov     rax, [rbx]
0x14000afba  mov     r9, [rbx+8]
0x14000afbe  mov     rcx, [r8+10h]
0x14000afc2  mov     [rsp+68h+dwFlagsAndAttributes], edi
0x14000afc6  mov     [rsp+68h+lpSecurityAttributes], rax
0x14000afcb  call    WPP_SF_iid
0x14000afd0  mov     eax, edi
0x14000afd2  jmp     loc_14000B0BA
0x14000afd7  mov     esi, 104h
0x14000afdc  xor     r9d, r9d; dwFlags
0x14000afdf  mov     r8d, esi; cchFilePath
0x14000afe2  mov     rdx, rdi; lpszFilePath
0x14000afe5  mov     rcx, rax; hFile
0x14000afe8  call    cs:__imp_GetFinalPathNameByHandleW
0x14000afee  test    eax, eax
0x14000aff0  jnz     short loc_14000B029
0x14000aff2  call    cs:__imp_GetLastError
0x14000aff8  mov     ecx, eax; unsigned int
0x14000affa  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000afff  mov     edi, eax
0x14000b001  mov     r8, cs:WPP_GLOBAL_Control
0x14000b008  lea     rcx, WPP_GLOBAL_Control
0x14000b00f  cmp     r8, rcx
0x14000b012  jz      short loc_14000AFD0
0x14000b014  test    byte ptr [r8+1Ch], 1
0x14000b019  jz      short loc_14000AFD0
0x14000b01b  cmp     byte ptr [r8+19h], 2
0x14000b020  jb      short loc_14000AFD0
0x14000b022  mov     edx, 2Ah ; '*'
0x14000b027  jmp     short loc_14000AFB7
0x14000b029  cmp     eax, esi
0x14000b02b  jbe     short loc_14000B06C
0x14000b02d  mov     rdx, cs:WPP_GLOBAL_Control
0x14000b034  lea     rcx, WPP_GLOBAL_Control
0x14000b03b  cmp     rdx, rcx
0x14000b03e  jz      short loc_14000B065
0x14000b040  test    byte ptr [rdx+1Ch], 1
0x14000b044  jz      short loc_14000B065
0x14000b046  cmp     byte ptr [rdx+19h], 2
0x14000b04a  jb      short loc_14000B065
0x14000b04c  mov     r9, [rbx+8]
0x14000b050  mov     rcx, [rdx+10h]
0x14000b054  mov     [rsp+68h+dwFlagsAndAttributes], eax
0x14000b058  mov     rax, [rbx]
0x14000b05b  mov     [rsp+68h+lpSecurityAttributes], rax
0x14000b060  call    WPP_SF_iidd
0x14000b065  mov     eax, 80070057h
0x14000b06a  jmp     short loc_14000B0BA
0x14000b06c  mov     rdx, rsi; cchPath
0x14000b06f  mov     rcx, rdi; pszPath
0x14000b072  call    cs:__imp_PathCchStripPrefix
0x14000b078  mov     ebx, eax
0x14000b07a  test    eax, eax
0x14000b07c  jns     short loc_14000B0B8
0x14000b07e  mov     r10, cs:WPP_GLOBAL_Control
0x14000b085  lea     rcx, WPP_GLOBAL_Control
0x14000b08c  cmp     r10, rcx
0x14000b08f  jz      loc_14000AF50
0x14000b095  test    byte ptr [r10+1Ch], 1
0x14000b09a  jz      loc_14000AF50
0x14000b0a0  cmp     byte ptr [r10+19h], 2
0x14000b0a5  jb      loc_14000AF50
0x14000b0ab  mov     edx, 2Ch ; ','
0x14000b0b0  mov     r9, rdi
0x14000b0b3  jmp     loc_14000AF3C
0x14000b0b8  xor     eax, eax
0x14000b0ba  mov     rbx, [rsp+68h+arg_0]
0x14000b0bf  mov     rsi, [rsp+68h+arg_8]
0x14000b0c4  add     rsp, 60h
0x14000b0c8  pop     rdi
0x14000b0c9  retn
```
