# GetRawFileVersion(wchar_t const *,ulong *,ulong *)

- ea: `0x14003a940`
- end: `0x14003ac7e`
- name: `?GetRawFileVersion@@YAJPEB_WPEAK1@Z`
- size: `830`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140022330`
- `0x14003a864`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x14000ce30`
- `0x14000ce9c`
- `0x14003a940`
- `0x14003ac84`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a9fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a9fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ac3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ac49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ac3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ac49`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14003ac0d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14003ac0d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x14003aabb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x14003aabb`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14003aa91`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14003aa91`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x14003ab20`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x14003ab20`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14003ab8f`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14003ab8f`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x14003ab6c`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x14003ab6c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003a9eb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003a9eb`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14003aa44`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14003aa44`

## pseudocode

```c
__int64 __fastcall GetRawFileVersion(LPCWSTR lpwstrFilename, unsigned int *a2, unsigned int *a3)
{
  void *v4; // rdi
  void *v5; // rbx
  __int64 v6; // rdx
  unsigned int v7; // esi
  HANDLE FileW; // rax
  void *v9; // r13
  signed int LastError; // eax
  __int64 v11; // rdx
  const char *v12; // r9
  __int64 v13; // rdx
  HANDLE FileMappingW; // rax
  unsigned __int64 v15; // rax
  int RawFileVersionFromModule; // r14d
  DWORD FileVersionInfoSize; // eax
  const char *v18; // r9
  DWORD v19; // r12d
  __int64 v20; // rdx
  __int64 v21; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-60h]
  LPCVOID lpBaseAddress; // [rsp+40h] [rbp-40h]
  LPVOID lpBuffer; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v30; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-1Ch] BYREF
  unsigned int puLen; // [rsp+68h] [rbp-18h] BYREF
  DWORD dwHandle; // [rsp+6Ch] [rbp-14h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v30 = 0;
  v31 = 0;
  v4 = 0;
  v5 = 0;
  if ( !lpwstrFilename )
  {
    v6 = 100;
LABEL_7:
    v7 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
      (const char *)0x80004003LL,
      dwCreationDisposition);
    return v7;
  }
  if ( !a2 )
  {
    v6 = 101;
    goto LABEL_7;
  }
  if ( !a3 )
  {
    v6 = 102;
    goto LABEL_7;
  }
  FileW = CreateFileW(lpwstrFilename, 0x80000000, 1u, 0, 3u, 0, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v7 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v7 = LastError;
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( v7 == -2147024894 || v7 == -2147024893 )
        goto LABEL_45;
    }
    else
    {
      v7 = -2147418113;
    }
    v11 = 116;
    goto LABEL_20;
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    v13 = 122;
LABEL_25:
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v13,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
           v12);
    goto LABEL_45;
  }
  if ( !FileSize.HighPart )
  {
    FileMappingW = CreateFileMappingW(v9, 0, 2u, 0, 0, 0);
    v4 = FileMappingW;
    if ( !FileMappingW )
    {
      v13 = 127;
      goto LABEL_25;
    }
    v15 = (unsigned __int64)MapViewOfFileEx(FileMappingW, 4u, 0, 0, 0, 0);
    lpBaseAddress = (LPCVOID)v15;
    if ( !v15 )
    {
      v13 = 130;
      goto LABEL_25;
    }
    RawFileVersionFromModule = GetRawFileVersionFromModule((HINSTANCE)(v15 | 1), FileSize.QuadPart, &v30, &v31);
    if ( RawFileVersionFromModule == -2147020580 )
    {
      dwHandle = 0;
      lpBuffer = 0;
      puLen = 0;
      FileVersionInfoSize = GetFileVersionInfoSizeExW(0, lpwstrFilename, &dwHandle);
      v19 = FileVersionInfoSize;
      if ( !FileVersionInfoSize )
      {
        v20 = 149;
LABEL_35:
        v7 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v20,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
               v18);
LABEL_44:
        UnmapViewOfFile(lpBaseAddress);
        goto LABEL_45;
      }
      v5 = SafeSusAllocArray(FileVersionInfoSize, 1u);
      v7 = v5 == 0 ? 0x8007000E : 0;
      if ( !v5 )
      {
        v21 = 150;
LABEL_39:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
          (const char *)v7,
          dwCreationDispositionb);
        goto LABEL_44;
      }
      if ( !GetFileVersionInfoExW(0, lpwstrFilename, dwHandle, v19, v5) )
      {
        v21 = 158;
LABEL_38:
        v7 = -2147023084;
        goto LABEL_39;
      }
      if ( !VerQueryValueW(v5, L"\\", &lpBuffer, &puLen) )
      {
        v20 = 161;
        goto LABEL_35;
      }
      if ( puLen < 0x34 )
      {
        v21 = 162;
        goto LABEL_38;
      }
      v30 = *((_DWORD *)lpBuffer + 2);
      v31 = *((_DWORD *)lpBuffer + 3);
    }
    else if ( RawFileVersionFromModule >= 0 )
    {
LABEL_43:
      v7 = RawFileVersionFromModule;
      goto LABEL_44;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
      (const char *)(unsigned int)RawFileVersionFromModule,
      dwCreationDispositionb);
    goto LABEL_43;
  }
  v7 = -2147024883;
  v11 = 124;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
    (const char *)v7,
    dwCreationDispositiona);
LABEL_45:
  *a2 = v30;
  *a3 = v31;
  if ( v5 )
    SusFree(v5);
  if ( v4 )
    CloseHandle(v4);
  if ( v9 != (void *)-1LL )
    CloseHandle(v9);
  return v7;
}

```

## disassembly

```asm
0x14003a940  mov     [rsp-28h+arg_8], rbx
0x14003a945  mov     [rsp-28h+arg_10], rsi
0x14003a94a  mov     [rsp-28h+arg_18], rdi
0x14003a94f  push    rbp
0x14003a950  push    r12
0x14003a952  push    r13
0x14003a954  push    r14
0x14003a956  push    r15
0x14003a958  mov     rbp, rsp
0x14003a95b  sub     rsp, 80h
0x14003a962  mov     rax, cs:__security_cookie
0x14003a969  xor     rax, rsp
0x14003a96c  mov     [rbp+var_8], rax
0x14003a970  xor     r12d, r12d
0x14003a973  mov     [rbp+var_38], rdx
0x14003a977  mov     [rbp+var_20], r12d
0x14003a97b  mov     rax, r8
0x14003a97e  mov     [rbp+var_30], rax
0x14003a982  mov     r15, rcx
0x14003a985  mov     [rbp+var_1C], r12d
0x14003a989  mov     edi, r12d
0x14003a98c  mov     ebx, r12d
0x14003a98f  test    rcx, rcx
0x14003a992  jnz     short loc_14003A999
0x14003a994  lea     edx, [rcx+64h]
0x14003a997  jmp     short loc_14003A9AD
0x14003a999  test    rdx, rdx
0x14003a99c  jnz     short loc_14003A9A5
0x14003a99e  mov     edx, 65h ; 'e'
0x14003a9a3  jmp     short loc_14003A9AD
0x14003a9a5  test    rax, rax
0x14003a9a8  jnz     short loc_14003A9CA
0x14003a9aa  lea     edx, [rax+66h]; void *
0x14003a9ad  mov     rcx, [rbp+28h]; this
0x14003a9b1  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003a9b8  mov     esi, 80004003h
0x14003a9bd  mov     r9d, esi; char *
0x14003a9c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003a9c5  jmp     loc_14003AC4F
0x14003a9ca  xor     r9d, r9d; lpSecurityAttributes
0x14003a9cd  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x14003a9d2  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x14003a9d7  mov     edx, 80000000h; dwDesiredAccess
0x14003a9dc  mov     [rsp+80h+dwCreationDisposition], 3; int
0x14003a9e4  lea     esi, [r9+1]
0x14003a9e8  mov     r8d, esi; dwShareMode
0x14003a9eb  call    cs:__imp_CreateFileW
0x14003a9f1  mov     r13, rax
0x14003a9f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003a9f8  jnz     short loc_14003AA39
0x14003a9fa  call    cs:__imp_GetLastError
0x14003aa00  movzx   esi, ax
0x14003aa03  or      esi, 80070000h
0x14003aa09  test    eax, eax
0x14003aa0b  cmovle  esi, eax
0x14003aa0e  test    esi, esi
0x14003aa10  js      short loc_14003AA19
0x14003aa12  mov     esi, 8000FFFFh
0x14003aa17  jmp     short loc_14003AA32
0x14003aa19  mov     eax, esi
0x14003aa1b  cmp     esi, 80070002h
0x14003aa21  jz      loc_14003AC13
0x14003aa27  cmp     eax, 80070003h
0x14003aa2c  jz      loc_14003AC13
0x14003aa32  mov     edx, 74h ; 't'
0x14003aa37  jmp     short loc_14003AA63
0x14003aa39  lea     rdx, [rbp+FileSize]; lpFileSize
0x14003aa3d  mov     qword ptr [rbp+FileSize], r12
0x14003aa41  mov     rcx, r13; hFile
0x14003aa44  call    cs:__imp_GetFileSizeEx
0x14003aa4a  test    eax, eax
0x14003aa4c  jnz     short loc_14003AA53
0x14003aa4e  lea     edx, [rax+7Ah]
0x14003aa51  jmp     short loc_14003AACF
0x14003aa53  cmp     dword ptr [rbp+FileSize+4], r12d
0x14003aa57  jz      short loc_14003AA7B
0x14003aa59  mov     esi, 8007000Dh
0x14003aa5e  mov     edx, 7Ch ; '|'; void *
0x14003aa63  mov     rcx, [rbp+28h]; this
0x14003aa67  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003aa6e  mov     r9d, esi; char *
0x14003aa71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003aa76  jmp     loc_14003AC13
0x14003aa7b  xor     r9d, r9d; dwMaximumSizeHigh
0x14003aa7e  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpName
0x14003aa83  xor     edx, edx; lpFileMappingAttributes
0x14003aa85  mov     [rsp+80h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x14003aa8a  mov     rcx, r13; hFile
0x14003aa8d  lea     r8d, [r9+2]; flProtect
0x14003aa91  call    cs:__imp_CreateFileMappingW
0x14003aa97  mov     rdi, rax
0x14003aa9a  test    rax, rax
0x14003aa9d  jnz     short loc_14003AAA4
0x14003aa9f  lea     edx, [rax+7Fh]
0x14003aaa2  jmp     short loc_14003AACF
0x14003aaa4  xor     r9d, r9d; dwFileOffsetLow
0x14003aaa7  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpBaseAddress
0x14003aaac  xor     r8d, r8d; dwFileOffsetHigh
0x14003aaaf  mov     qword ptr [rsp+80h+dwCreationDisposition], r12; int
0x14003aab4  mov     rcx, rax; hFileMappingObject
0x14003aab7  lea     edx, [r9+4]; dwDesiredAccess
0x14003aabb  call    cs:__imp_MapViewOfFileEx
0x14003aac1  mov     [rbp+lpBaseAddress], rax
0x14003aac5  test    rax, rax
0x14003aac8  jnz     short loc_14003AAE6
0x14003aaca  mov     edx, 82h; void *
0x14003aacf  mov     rcx, [rbp+28h]; this
0x14003aad3  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003aada  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14003aadf  mov     esi, eax
0x14003aae1  jmp     loc_14003AC13
0x14003aae6  mov     rdx, qword ptr [rbp+FileSize]; unsigned __int64
0x14003aaea  lea     r9, [rbp+var_1C]; unsigned int *
0x14003aaee  mov     rcx, rax
0x14003aaf1  lea     r8, [rbp+var_20]; unsigned int *
0x14003aaf5  or      rcx, rsi; hModule
0x14003aaf8  call    ?GetRawFileVersionFromModule@@YAJPEAUHINSTANCE__@@_KPEAK2@Z; GetRawFileVersionFromModule(HINSTANCE__ *,unsigned __int64,ulong *,ulong *)
0x14003aafd  mov     r14d, eax
0x14003ab00  cmp     eax, 800710DCh
0x14003ab05  jnz     loc_14003ABE9
0x14003ab0b  lea     r8, [rbp+dwHandle]; lpdwHandle
0x14003ab0f  mov     [rbp+dwHandle], r12d
0x14003ab13  mov     rdx, r15; lpwstrFilename
0x14003ab16  mov     [rbp+lpBuffer], r12
0x14003ab1a  xor     ecx, ecx; dwFlags
0x14003ab1c  mov     [rbp+puLen], r12d
0x14003ab20  call    cs:__imp_GetFileVersionInfoSizeExW
0x14003ab26  mov     r12d, eax
0x14003ab29  test    eax, eax
0x14003ab2b  jnz     short loc_14003AB34
0x14003ab2d  mov     edx, 95h
0x14003ab32  jmp     short loc_14003AB9E
0x14003ab34  mov     rcx, r12; unsigned __int64
0x14003ab37  mov     rdx, rsi; unsigned __int64
0x14003ab3a  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14003ab3f  mov     rbx, rax
0x14003ab42  neg     rax
0x14003ab45  sbb     esi, esi
0x14003ab47  not     esi
0x14003ab49  and     esi, 8007000Eh
0x14003ab4f  test    rbx, rbx
0x14003ab52  jnz     short loc_14003AB5B
0x14003ab54  mov     edx, 96h
0x14003ab59  jmp     short loc_14003ABC2
0x14003ab5b  mov     r8d, [rbp+dwHandle]; dwHandle
0x14003ab5f  mov     r9d, r12d; dwLen
0x14003ab62  mov     rdx, r15; lpwstrFilename
0x14003ab65  mov     qword ptr [rsp+80h+dwCreationDisposition], rbx; int
0x14003ab6a  xor     ecx, ecx; dwFlags
0x14003ab6c  call    cs:__imp_GetFileVersionInfoExW
0x14003ab72  test    eax, eax
0x14003ab74  jnz     short loc_14003AB7D
0x14003ab76  mov     edx, 9Eh
0x14003ab7b  jmp     short loc_14003ABBD
0x14003ab7d  lea     r9, [rbp+puLen]; puLen
0x14003ab81  mov     rcx, rbx; pBlock
0x14003ab84  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x14003ab88  lea     rdx, SubBlock; "\\"
0x14003ab8f  call    cs:__imp_VerQueryValueW
0x14003ab95  test    eax, eax
0x14003ab97  jnz     short loc_14003ABB2
0x14003ab99  mov     edx, 0A1h; void *
0x14003ab9e  mov     rcx, [rbp+28h]; this
0x14003aba2  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003aba9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14003abae  mov     esi, eax
0x14003abb0  jmp     short loc_14003AC09
0x14003abb2  cmp     [rbp+puLen], 34h ; '4'
0x14003abb6  jnb     short loc_14003ABD7
0x14003abb8  mov     edx, 0A2h; void *
0x14003abbd  mov     esi, 80070714h
0x14003abc2  mov     rcx, [rbp+28h]; this
0x14003abc6  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003abcd  mov     r9d, esi; char *
0x14003abd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003abd5  jmp     short loc_14003AC09
0x14003abd7  mov     rcx, [rbp+lpBuffer]
0x14003abdb  mov     eax, [rcx+8]
0x14003abde  mov     [rbp+var_20], eax
0x14003abe1  mov     eax, [rcx+0Ch]
0x14003abe4  mov     [rbp+var_1C], eax
0x14003abe7  jmp     short loc_14003ABEE
0x14003abe9  test    r14d, r14d
0x14003abec  jns     short loc_14003AC06
0x14003abee  mov     rcx, [rbp+28h]; this
0x14003abf2  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003abf9  mov     r9d, r14d; char *
0x14003abfc  mov     edx, 0A8h; void *
0x14003ac01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ac06  mov     esi, r14d
0x14003ac09  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x14003ac0d  call    cs:__imp_UnmapViewOfFile
0x14003ac13  mov     eax, [rbp+var_20]
0x14003ac16  mov     rcx, [rbp+var_38]
0x14003ac1a  mov     [rcx], eax
0x14003ac1c  mov     rcx, [rbp+var_30]
0x14003ac20  mov     eax, [rbp+var_1C]
0x14003ac23  mov     [rcx], eax
0x14003ac25  test    rbx, rbx
0x14003ac28  jz      short loc_14003AC32
0x14003ac2a  mov     rcx, rbx; lpMem
0x14003ac2d  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14003ac32  test    rdi, rdi
0x14003ac35  jz      short loc_14003AC40
0x14003ac37  mov     rcx, rdi; hObject
0x14003ac3a  call    cs:__imp_CloseHandle
0x14003ac40  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x14003ac44  jz      short loc_14003AC4F
0x14003ac46  mov     rcx, r13; hObject
0x14003ac49  call    cs:__imp_CloseHandle
0x14003ac4f  mov     eax, esi
0x14003ac51  mov     rcx, [rbp+var_8]
0x14003ac55  xor     rcx, rsp; StackCookie
0x14003ac58  call    __security_check_cookie
0x14003ac5d  lea     r11, [rsp+80h+var_s0]
0x14003ac65  mov     rbx, [r11+38h]
0x14003ac69  mov     rsi, [r11+40h]
0x14003ac6d  mov     rdi, [r11+48h]
0x14003ac71  mov     rsp, r11
0x14003ac74  pop     r15
0x14003ac76  pop     r14
0x14003ac78  pop     r13
0x14003ac7a  pop     r12
0x14003ac7c  pop     rbp
0x14003ac7d  retn
```
