# CreateFileWithUsnSourceInfo(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,ulong,void * *)

- ea: `0x180044f64`
- end: `0x18004520c`
- name: `?CreateFileWithUsnSourceInfo@@YAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXKKPEAPEAX@Z`
- size: `680`
- prototype: `__int64 __usercall@<rax>(wchar_t *Str@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, struct _SECURITY_ATTRIBUTES *@<r9>, unsigned int, DWORD, void *, unsigned int, unsigned int, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045214`
- `0x180046300`

## callees

- `0x18000b9b0`
- `0x18000c668`
- `0x180037780`
- `0x180044f64`
- `0x180045e00`
- `0x180046300`
- `0x180046588`
- `0x180046684`
- `0x180046a18`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800451db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800451db`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18004519a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18004519a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180044fd7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045048`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800450f4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180044fd7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045048`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800450f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateFileWithUsnSourceInfo(
        wchar_t *Str,
        DWORD a2,
        DWORD a3,
        struct _SECURITY_ATTRIBUTES *a4,
        signed int a5,
        DWORD dwFlagsAndAttributes,
        void *a7,
        char a8,
        unsigned int a9,
        void **a10)
{
  unsigned int v11; // r15d
  HANDLE FileW; // rax
  int v13; // edi
  unsigned int v14; // r8d
  int v15; // ebx
  HANDLE v16; // rax
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  HANDLE v19; // rax
  unsigned int v20; // r8d
  __int64 v21; // rax
  unsigned __int64 v22; // rax
  HANDLE v23; // rsi
  HANDLE hFile; // [rsp+40h] [rbp-59h] BYREF
  DWORD dwShareMode; // [rsp+48h] [rbp-51h]
  DWORD dwDesiredAccess; // [rsp+4Ch] [rbp-4Dh]
  unsigned __int16 *v28; // [rsp+50h] [rbp-49h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+58h] [rbp-41h]
  void **v30; // [rsp+60h] [rbp-39h]
  __int128 FileInformation; // [rsp+68h] [rbp-31h] BYREF
  __int128 v32; // [rsp+78h] [rbp-21h]
  __int64 v33; // [rsp+88h] [rbp-11h]

  lpSecurityAttributes = a4;
  dwShareMode = a3;
  dwDesiredAccess = a2;
  v30 = a10;
  *a10 = (void *)-1LL;
  v11 = a5 & 0x7FFFFFFF;
  hFile = 0;
  FileW = CreateFileW(Str, a2, a3, a4, a5 & 0x7FFFFFFF, dwFlagsAndAttributes, 0);
  v13 = SuccessResultFromWin32Handle(FileW, &hFile);
  v15 = v13;
  if ( v13 != -2147022976 )
    goto LABEL_10;
  if ( (dwFlagsAndAttributes & 0x200000) != 0 )
  {
LABEL_29:
    v15 = v13;
    goto LABEL_30;
  }
  if ( v11 == 1 )
  {
    v13 = -2147024816;
    goto LABEL_16;
  }
  if ( v11 == 2 || v11 == 5 )
  {
    if ( SetPlaceholderReparsePointAndAttributes(Str, 0, v14) >= 0 )
    {
      v16 = CreateFileW(
              Str,
              dwDesiredAccess,
              dwShareMode,
              lpSecurityAttributes,
              a5 & 0x7FFFFFFF,
              dwFlagsAndAttributes,
              0);
      v15 = SuccessResultFromWin32Handle(v16, &hFile);
      if ( v15 < 0 )
        SetPlaceholderReparsePointAndAttributes(Str, 1, v17);
    }
    v13 = v15;
LABEL_10:
    if ( v13 == -2147024891 )
    {
      if ( (a8 & 1) == 0 )
        goto LABEL_26;
      FileInformation = 0u;
      *(_QWORD *)&v32 = 0;
      v28 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&FileInformation);
      *((_QWORD *)&FileInformation + 1) = -1;
      *(_QWORD *)&v32 = -1;
      if ( (int)anonymous_namespace_::_GetPrimaryStreamPath(Str) >= 0
        && SetFileAttributesWithUsnSourceInfo(v28, 0, v18, a9) >= 0 )
      {
        v19 = CreateFileW(
                Str,
                dwDesiredAccess,
                dwShareMode,
                lpSecurityAttributes,
                a5 & 0x7FFFFFFF,
                dwFlagsAndAttributes,
                0);
        v13 = SuccessResultFromWin32Handle(v19, &hFile);
        v15 = v13;
        SetFileAttributesWithUsnSourceInfo(v28, 1u, v20, a9);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&FileInformation);
    }
  }
LABEL_16:
  if ( v13 >= 0 )
  {
    FileInformation = 0;
    v32 = 0;
    v33 = 0;
    v21 = 0;
    if ( (a8 & 2) != 0 )
      v21 = -1;
    *(_QWORD *)&v32 = v21;
    v22 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( (a8 & 4) != 0 )
      v22 = -1;
    *((_QWORD *)&FileInformation + 1) = v22;
    v23 = hFile;
    if ( (a8 & 6) != 0
      && (int)SetUsnSourceInfo(hFile, a9) >= 0
      && !SetFileInformationByHandle(v23, FileBasicInfo, &FileInformation, 0x28u) )
    {
      ResultFromKnownLastError();
    }
    hFile = 0;
    *v30 = v23;
  }
LABEL_26:
  if ( v15 >= 0 )
    v15 = a5 < 0 ? v15 : 0;
  if ( v13 < 0 )
    goto LABEL_29;
LABEL_30:
  if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hFile);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180044f64  push    rbp
0x180044f66  push    rbx
0x180044f67  push    rsi
0x180044f68  push    rdi
0x180044f69  push    r13
0x180044f6b  push    r14
0x180044f6d  push    r15
0x180044f6f  lea     rbp, [rsp-7]
0x180044f74  sub     rsp, 0A0h
0x180044f7b  mov     rax, cs:__security_cookie
0x180044f82  xor     rax, rsp
0x180044f85  mov     [rbp+37h+var_40], rax
0x180044f89  mov     [rbp+37h+lpSecurityAttributes], r9
0x180044f8d  mov     [rbp+37h+dwShareMode], r8d
0x180044f91  mov     [rbp+37h+dwDesiredAccess], edx
0x180044f94  mov     rsi, rcx
0x180044f97  mov     r14d, [rbp+37h+arg_20]
0x180044f9b  mov     r13d, [rbp+37h+arg_28]
0x180044f9f  mov     rcx, [rbp+37h+arg_48]
0x180044fa6  mov     [rbp+37h+var_70], rcx
0x180044faa  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180044fb1  mov     r15d, r14d
0x180044fb4  btr     r15d, 1Fh
0x180044fb9  mov     [rbp+37h+hFile], 0
0x180044fc1  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x180044fca  mov     [rsp+0D0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180044fcf  mov     [rsp+0D0h+dwCreationDisposition], r15d; dwCreationDisposition
0x180044fd4  mov     rcx, rsi; lpFileName
0x180044fd7  call    cs:__imp_CreateFileW
0x180044fdd  lea     rdx, [rbp+37h+hFile]; void **
0x180044fe1  mov     rcx, rax; void *
0x180044fe4  call    ?SuccessResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; SuccessResultFromWin32Handle(void *,void * *)
0x180044fe9  mov     edi, eax
0x180044feb  mov     ebx, eax
0x180044fed  cmp     eax, 80070780h
0x180044ff2  jnz     short loc_18004506C
0x180044ff4  bt      r13d, 15h
0x180044ff9  jb      loc_1800451CB
0x180044fff  mov     eax, r15d
0x180045002  sub     eax, 1
0x180045005  jz      loc_180045201
0x18004500b  sub     eax, 1
0x18004500e  jz      short loc_180045019
0x180045010  cmp     eax, 3
0x180045013  jnz     loc_180045128
0x180045019  xor     edx, edx; bool
0x18004501b  mov     rcx, rsi; unsigned __int16 *
0x18004501e  call    ?SetPlaceholderReparsePointAndAttributes@@YAJPEBG_NK@Z; SetPlaceholderReparsePointAndAttributes(ushort const *,bool,ulong)
0x180045023  test    eax, eax
0x180045025  js      short loc_18004506A
0x180045027  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x180045030  mov     [rsp+0D0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180045035  mov     [rsp+0D0h+dwCreationDisposition], r15d; dwCreationDisposition
0x18004503a  mov     r9, [rbp+37h+lpSecurityAttributes]; lpSecurityAttributes
0x18004503e  mov     r8d, [rbp+37h+dwShareMode]; dwShareMode
0x180045042  mov     edx, [rbp+37h+dwDesiredAccess]; dwDesiredAccess
0x180045045  mov     rcx, rsi; lpFileName
0x180045048  call    cs:__imp_CreateFileW
0x18004504e  lea     rdx, [rbp+37h+hFile]; void **
0x180045052  mov     rcx, rax; void *
0x180045055  call    ?SuccessResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; SuccessResultFromWin32Handle(void *,void * *)
0x18004505a  mov     ebx, eax
0x18004505c  test    eax, eax
0x18004505e  jns     short loc_18004506A
0x180045060  mov     dl, 1; bool
0x180045062  mov     rcx, rsi; unsigned __int16 *
0x180045065  call    ?SetPlaceholderReparsePointAndAttributes@@YAJPEBG_NK@Z; SetPlaceholderReparsePointAndAttributes(ushort const *,bool,ulong)
0x18004506a  mov     edi, ebx
0x18004506c  cmp     edi, 80070005h
0x180045072  jnz     loc_180045128
0x180045078  test    [rbp+37h+arg_38], 1
0x18004507c  jz      loc_1800451B8
0x180045082  xor     eax, eax
0x180045084  mov     qword ptr [rbp+37h+FileInformation], rax
0x180045088  mov     qword ptr [rbp+37h+FileInformation+8], rax
0x18004508c  mov     qword ptr [rbp+37h+var_58], rax
0x180045090  mov     [rbp+37h+var_80], rax
0x180045094  lea     rcx, [rbp+37h+FileInformation]
0x180045098  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004509d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800450a1  mov     qword ptr [rbp+37h+FileInformation+8], rax
0x1800450a5  mov     qword ptr [rbp+37h+var_58], rax
0x1800450a9  lea     r8, [rbp+37h+var_80]
0x1800450ad  lea     rdx, [rbp+37h+FileInformation]
0x1800450b1  mov     rcx, rsi; Str
0x1800450b4  call    _anonymous_namespace____GetPrimaryStreamPath
0x1800450b9  test    eax, eax
0x1800450bb  js      short loc_18004511F
0x1800450bd  mov     r9d, [rbp+37h+arg_40]; unsigned int
0x1800450c4  xor     edx, edx; unsigned int
0x1800450c6  mov     rcx, [rbp+37h+var_80]; unsigned __int16 *
0x1800450ca  call    ?SetFileAttributesWithUsnSourceInfo@@YAJPEBGKKK@Z; SetFileAttributesWithUsnSourceInfo(ushort const *,ulong,ulong,ulong)
0x1800450cf  test    eax, eax
0x1800450d1  js      short loc_18004511F
0x1800450d3  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x1800450dc  mov     [rsp+0D0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x1800450e1  mov     [rsp+0D0h+dwCreationDisposition], r15d; dwCreationDisposition
0x1800450e6  mov     r9, [rbp+37h+lpSecurityAttributes]; lpSecurityAttributes
0x1800450ea  mov     r8d, [rbp+37h+dwShareMode]; dwShareMode
0x1800450ee  mov     edx, [rbp+37h+dwDesiredAccess]; dwDesiredAccess
0x1800450f1  mov     rcx, rsi; lpFileName
0x1800450f4  call    cs:__imp_CreateFileW
0x1800450fa  lea     rdx, [rbp+37h+hFile]; void **
0x1800450fe  mov     rcx, rax; void *
0x180045101  call    ?SuccessResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; SuccessResultFromWin32Handle(void *,void * *)
0x180045106  mov     edi, eax
0x180045108  mov     ebx, eax
0x18004510a  mov     r9d, [rbp+37h+arg_40]; unsigned int
0x180045111  mov     edx, 1; unsigned int
0x180045116  mov     rcx, [rbp+37h+var_80]; unsigned __int16 *
0x18004511a  call    ?SetFileAttributesWithUsnSourceInfo@@YAJPEBGKKK@Z; SetFileAttributesWithUsnSourceInfo(ushort const *,ulong,ulong,ulong)
0x18004511f  lea     rcx, [rbp+37h+FileInformation]
0x180045123  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180045128  test    edi, edi
0x18004512a  js      loc_1800451B8
0x180045130  xorps   xmm0, xmm0
0x180045133  xor     eax, eax
0x180045135  movups  [rbp+37h+FileInformation], xmm0
0x180045139  movups  [rbp+37h+var_58], xmm0
0x18004513d  mov     [rbp+37h+var_48], rax
0x180045141  test    [rbp+37h+arg_38], 2
0x180045145  movq    rax, xmm0
0x18004514a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180045151  cmovnz  rax, rcx
0x180045155  mov     qword ptr [rbp+37h+var_58], rax
0x180045159  test    [rbp+37h+arg_38], 4
0x18004515d  psrldq  xmm0, 8
0x180045162  movq    rax, xmm0
0x180045167  cmovnz  rax, rcx
0x18004516b  mov     qword ptr [rbp+37h+FileInformation+8], rax
0x18004516f  mov     rsi, [rbp+37h+hFile]
0x180045173  test    [rbp+37h+arg_38], 6
0x180045177  jz      short loc_1800451A9
0x180045179  mov     edx, [rbp+37h+arg_40]; unsigned int
0x18004517f  mov     rcx, rsi; void *
0x180045182  call    ?SetUsnSourceInfo@@YAJPEAXK@Z; SetUsnSourceInfo(void *,ulong)
0x180045187  test    eax, eax
0x180045189  js      short loc_1800451A9
0x18004518b  mov     r9d, 28h ; '('; dwBufferSize
0x180045191  lea     r8, [rbp+37h+FileInformation]; lpFileInformation
0x180045195  xor     edx, edx; FileInformationClass
0x180045197  mov     rcx, rsi; hFile
0x18004519a  call    cs:__imp_SetFileInformationByHandle
0x1800451a0  test    eax, eax
0x1800451a2  jnz     short loc_1800451A9
0x1800451a4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800451a9  mov     [rbp+37h+hFile], 0
0x1800451b1  mov     rax, [rbp+37h+var_70]
0x1800451b5  mov     [rax], rsi
0x1800451b8  test    ebx, ebx
0x1800451ba  js      short loc_1800451C7
0x1800451bc  shr     r14d, 1Fh
0x1800451c0  neg     r14b
0x1800451c3  sbb     eax, eax
0x1800451c5  and     ebx, eax
0x1800451c7  test    edi, edi
0x1800451c9  jns     short loc_1800451CD
0x1800451cb  mov     ebx, edi
0x1800451cd  mov     rcx, [rbp+37h+hFile]; hObject
0x1800451d1  lea     rdx, [rcx-1]
0x1800451d5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800451d9  ja      short loc_1800451E1
0x1800451db  call    cs:__imp_CloseHandle
0x1800451e1  mov     eax, ebx
0x1800451e3  mov     rcx, [rbp+37h+var_40]
0x1800451e7  xor     rcx, rsp; StackCookie
0x1800451ea  call    __security_check_cookie
0x1800451ef  add     rsp, 0A0h
0x1800451f6  pop     r15
0x1800451f8  pop     r14
0x1800451fa  pop     r13
0x1800451fc  pop     rdi
0x1800451fd  pop     rsi
0x1800451fe  pop     rbx
0x1800451ff  pop     rbp
0x180045200  retn
0x180045201  mov     edi, 80070050h
0x180045206  jmp     loc_180045128
```
