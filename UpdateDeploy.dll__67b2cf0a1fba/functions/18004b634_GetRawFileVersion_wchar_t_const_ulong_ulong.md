# GetRawFileVersion(wchar_t const *,ulong *,ulong *)

- ea: `0x18004b634`
- end: `0x18004b972`
- name: `?GetRawFileVersion@@YAJPEB_WPEAK1@Z`
- size: `830`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18004b558`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000dce4`
- `0x18000dd60`
- `0x18004b634`
- `0x18004b978`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b6ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b6ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b92e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b93d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b92e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b93d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18004b7af`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18004b7af`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004b785`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004b785`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18004b901`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18004b901`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18004b883`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18004b883`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18004b814`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18004b814`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18004b860`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18004b860`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004b6df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004b6df`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18004b738`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18004b738`

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
0x18004b634  mov     [rsp-28h+arg_8], rbx
0x18004b639  mov     [rsp-28h+arg_10], rsi
0x18004b63e  mov     [rsp-28h+arg_18], rdi
0x18004b643  push    rbp
0x18004b644  push    r12
0x18004b646  push    r13
0x18004b648  push    r14
0x18004b64a  push    r15
0x18004b64c  mov     rbp, rsp
0x18004b64f  sub     rsp, 80h
0x18004b656  mov     rax, cs:__security_cookie
0x18004b65d  xor     rax, rsp
0x18004b660  mov     [rbp+var_8], rax
0x18004b664  xor     r12d, r12d
0x18004b667  mov     [rbp+var_38], rdx
0x18004b66b  mov     [rbp+var_20], r12d
0x18004b66f  mov     rax, r8
0x18004b672  mov     [rbp+var_30], rax
0x18004b676  mov     r15, rcx
0x18004b679  mov     [rbp+var_1C], r12d
0x18004b67d  mov     edi, r12d
0x18004b680  mov     ebx, r12d
0x18004b683  test    rcx, rcx
0x18004b686  jnz     short loc_18004B68D
0x18004b688  lea     edx, [rcx+64h]
0x18004b68b  jmp     short loc_18004B6A1
0x18004b68d  test    rdx, rdx
0x18004b690  jnz     short loc_18004B699
0x18004b692  mov     edx, 65h ; 'e'
0x18004b697  jmp     short loc_18004B6A1
0x18004b699  test    rax, rax
0x18004b69c  jnz     short loc_18004B6BE
0x18004b69e  lea     edx, [rax+66h]; void *
0x18004b6a1  mov     rcx, [rbp+28h]; this
0x18004b6a5  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004b6ac  mov     esi, 80004003h
0x18004b6b1  mov     r9d, esi; char *
0x18004b6b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b6b9  jmp     loc_18004B943
0x18004b6be  xor     r9d, r9d; lpSecurityAttributes
0x18004b6c1  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x18004b6c6  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18004b6cb  mov     edx, 80000000h; dwDesiredAccess
0x18004b6d0  mov     [rsp+80h+dwCreationDisposition], 3; int
0x18004b6d8  lea     esi, [r9+1]
0x18004b6dc  mov     r8d, esi; dwShareMode
0x18004b6df  call    cs:__imp_CreateFileW
0x18004b6e5  mov     r13, rax
0x18004b6e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004b6ec  jnz     short loc_18004B72D
0x18004b6ee  call    cs:__imp_GetLastError
0x18004b6f4  movzx   esi, ax
0x18004b6f7  or      esi, 80070000h
0x18004b6fd  test    eax, eax
0x18004b6ff  cmovle  esi, eax
0x18004b702  test    esi, esi
0x18004b704  js      short loc_18004B70D
0x18004b706  mov     esi, 8000FFFFh
0x18004b70b  jmp     short loc_18004B726
0x18004b70d  mov     eax, esi
0x18004b70f  cmp     esi, 80070002h
0x18004b715  jz      loc_18004B907
0x18004b71b  cmp     eax, 80070003h
0x18004b720  jz      loc_18004B907
0x18004b726  mov     edx, 74h ; 't'
0x18004b72b  jmp     short loc_18004B757
0x18004b72d  lea     rdx, [rbp+FileSize]; lpFileSize
0x18004b731  mov     qword ptr [rbp+FileSize], r12
0x18004b735  mov     rcx, r13; hFile
0x18004b738  call    cs:__imp_GetFileSizeEx
0x18004b73e  test    eax, eax
0x18004b740  jnz     short loc_18004B747
0x18004b742  lea     edx, [rax+7Ah]
0x18004b745  jmp     short loc_18004B7C3
0x18004b747  cmp     dword ptr [rbp+FileSize+4], r12d
0x18004b74b  jz      short loc_18004B76F
0x18004b74d  mov     esi, 8007000Dh
0x18004b752  mov     edx, 7Ch ; '|'; void *
0x18004b757  mov     rcx, [rbp+28h]; this
0x18004b75b  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004b762  mov     r9d, esi; char *
0x18004b765  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b76a  jmp     loc_18004B907
0x18004b76f  xor     r9d, r9d; dwMaximumSizeHigh
0x18004b772  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpName
0x18004b777  xor     edx, edx; lpFileMappingAttributes
0x18004b779  mov     [rsp+80h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x18004b77e  mov     rcx, r13; hFile
0x18004b781  lea     r8d, [r9+2]; flProtect
0x18004b785  call    cs:__imp_CreateFileMappingW
0x18004b78b  mov     rdi, rax
0x18004b78e  test    rax, rax
0x18004b791  jnz     short loc_18004B798
0x18004b793  lea     edx, [rax+7Fh]
0x18004b796  jmp     short loc_18004B7C3
0x18004b798  xor     r9d, r9d; dwFileOffsetLow
0x18004b79b  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpBaseAddress
0x18004b7a0  xor     r8d, r8d; dwFileOffsetHigh
0x18004b7a3  mov     qword ptr [rsp+80h+dwCreationDisposition], r12; int
0x18004b7a8  mov     rcx, rax; hFileMappingObject
0x18004b7ab  lea     edx, [r9+4]; dwDesiredAccess
0x18004b7af  call    cs:__imp_MapViewOfFileEx
0x18004b7b5  mov     [rbp+lpBaseAddress], rax
0x18004b7b9  test    rax, rax
0x18004b7bc  jnz     short loc_18004B7DA
0x18004b7be  mov     edx, 82h; void *
0x18004b7c3  mov     rcx, [rbp+28h]; this
0x18004b7c7  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004b7ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004b7d3  mov     esi, eax
0x18004b7d5  jmp     loc_18004B907
0x18004b7da  mov     rdx, qword ptr [rbp+FileSize]; unsigned __int64
0x18004b7de  lea     r9, [rbp+var_1C]; unsigned int *
0x18004b7e2  mov     rcx, rax
0x18004b7e5  lea     r8, [rbp+var_20]; unsigned int *
0x18004b7e9  or      rcx, rsi; hModule
0x18004b7ec  call    ?GetRawFileVersionFromModule@@YAJPEAUHINSTANCE__@@_KPEAK2@Z; GetRawFileVersionFromModule(HINSTANCE__ *,unsigned __int64,ulong *,ulong *)
0x18004b7f1  mov     r14d, eax
0x18004b7f4  cmp     eax, 800710DCh
0x18004b7f9  jnz     loc_18004B8DD
0x18004b7ff  lea     r8, [rbp+dwHandle]; lpdwHandle
0x18004b803  mov     [rbp+dwHandle], r12d
0x18004b807  mov     rdx, r15; lpwstrFilename
0x18004b80a  mov     [rbp+lpBuffer], r12
0x18004b80e  xor     ecx, ecx; dwFlags
0x18004b810  mov     [rbp+puLen], r12d
0x18004b814  call    cs:__imp_GetFileVersionInfoSizeExW
0x18004b81a  mov     r12d, eax
0x18004b81d  test    eax, eax
0x18004b81f  jnz     short loc_18004B828
0x18004b821  mov     edx, 95h
0x18004b826  jmp     short loc_18004B892
0x18004b828  mov     rcx, r12; unsigned __int64
0x18004b82b  mov     rdx, rsi; unsigned __int64
0x18004b82e  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18004b833  mov     rbx, rax
0x18004b836  neg     rax
0x18004b839  sbb     esi, esi
0x18004b83b  not     esi
0x18004b83d  and     esi, 8007000Eh
0x18004b843  test    rbx, rbx
0x18004b846  jnz     short loc_18004B84F
0x18004b848  mov     edx, 96h
0x18004b84d  jmp     short loc_18004B8B6
0x18004b84f  mov     r8d, [rbp+dwHandle]; dwHandle
0x18004b853  mov     r9d, r12d; dwLen
0x18004b856  mov     rdx, r15; lpwstrFilename
0x18004b859  mov     qword ptr [rsp+80h+dwCreationDisposition], rbx; int
0x18004b85e  xor     ecx, ecx; dwFlags
0x18004b860  call    cs:__imp_GetFileVersionInfoExW
0x18004b866  test    eax, eax
0x18004b868  jnz     short loc_18004B871
0x18004b86a  mov     edx, 9Eh
0x18004b86f  jmp     short loc_18004B8B1
0x18004b871  lea     r9, [rbp+puLen]; puLen
0x18004b875  mov     rcx, rbx; pBlock
0x18004b878  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x18004b87c  lea     rdx, SubBlock; "\\"
0x18004b883  call    cs:__imp_VerQueryValueW
0x18004b889  test    eax, eax
0x18004b88b  jnz     short loc_18004B8A6
0x18004b88d  mov     edx, 0A1h; void *
0x18004b892  mov     rcx, [rbp+28h]; this
0x18004b896  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004b89d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004b8a2  mov     esi, eax
0x18004b8a4  jmp     short loc_18004B8FD
0x18004b8a6  cmp     [rbp+puLen], 34h ; '4'
0x18004b8aa  jnb     short loc_18004B8CB
0x18004b8ac  mov     edx, 0A2h; void *
0x18004b8b1  mov     esi, 80070714h
0x18004b8b6  mov     rcx, [rbp+28h]; this
0x18004b8ba  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004b8c1  mov     r9d, esi; char *
0x18004b8c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b8c9  jmp     short loc_18004B8FD
0x18004b8cb  mov     rcx, [rbp+lpBuffer]
0x18004b8cf  mov     eax, [rcx+8]
0x18004b8d2  mov     [rbp+var_20], eax
0x18004b8d5  mov     eax, [rcx+0Ch]
0x18004b8d8  mov     [rbp+var_1C], eax
0x18004b8db  jmp     short loc_18004B8E2
0x18004b8dd  test    r14d, r14d
0x18004b8e0  jns     short loc_18004B8FA
0x18004b8e2  mov     rcx, [rbp+28h]; this
0x18004b8e6  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004b8ed  mov     r9d, r14d; char *
0x18004b8f0  mov     edx, 0A8h; void *
0x18004b8f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b8fa  mov     esi, r14d
0x18004b8fd  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x18004b901  call    cs:__imp_UnmapViewOfFile
0x18004b907  mov     eax, [rbp+var_20]
0x18004b90a  mov     rcx, [rbp+var_38]
0x18004b90e  mov     [rcx], eax
0x18004b910  mov     rcx, [rbp+var_30]
0x18004b914  mov     eax, [rbp+var_1C]
0x18004b917  mov     [rcx], eax
0x18004b919  test    rbx, rbx
0x18004b91c  jz      short loc_18004B926
0x18004b91e  mov     rcx, rbx; lpMem
0x18004b921  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18004b926  test    rdi, rdi
0x18004b929  jz      short loc_18004B934
0x18004b92b  mov     rcx, rdi; hObject
0x18004b92e  call    cs:__imp_CloseHandle
0x18004b934  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18004b938  jz      short loc_18004B943
0x18004b93a  mov     rcx, r13; hObject
0x18004b93d  call    cs:__imp_CloseHandle
0x18004b943  mov     eax, esi
0x18004b945  mov     rcx, [rbp+var_8]
0x18004b949  xor     rcx, rsp; StackCookie
0x18004b94c  call    __security_check_cookie
0x18004b951  lea     r11, [rsp+80h+var_s0]
0x18004b959  mov     rbx, [r11+38h]
0x18004b95d  mov     rsi, [r11+40h]
0x18004b961  mov     rdi, [r11+48h]
0x18004b965  mov     rsp, r11
0x18004b968  pop     r15
0x18004b96a  pop     r14
0x18004b96c  pop     r13
0x18004b96e  pop     r12
0x18004b970  pop     rbp
0x18004b971  retn
```
