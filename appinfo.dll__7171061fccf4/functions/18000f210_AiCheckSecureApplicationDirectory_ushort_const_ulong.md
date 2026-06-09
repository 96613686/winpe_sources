# AiCheckSecureApplicationDirectory(ushort const *,ulong *)

- ea: `0x18000f210`
- end: `0x18000f3d1`
- name: `?AiCheckSecureApplicationDirectory@@YAKPEBGPEAK@Z`
- size: `449`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18000f6d0`
- `0x18002ed98`
- `0x18003d070`
- `0x180040d64`

## callees

- `0x18000f210`
- `0x1800177a4`
- `0x180017840`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f2d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f33f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f2d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f33f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f2c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f32b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f2c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f32b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f2b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f2b0`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f28e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f2e9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f28e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f2e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f264`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f264`
- `ntdll!RtlFreeUnicodeString` at `0x18000f3ad`
- `ntdll!RtlFreeUnicodeString` at `0x18000f3ad`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000f30e`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000f30e`
- `ntdll!RtlReleaseRelativeName` at `0x18000f2cc`
- `ntdll!RtlReleaseRelativeName` at `0x18000f336`
- `ntdll!RtlReleaseRelativeName` at `0x18000f2cc`
- `ntdll!RtlReleaseRelativeName` at `0x18000f336`
- `ntdll!RtlPrefixUnicodeString` at `0x18000f372`
- `ntdll!RtlPrefixUnicodeString` at `0x18000f372`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000f320`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000f320`

## pseudocode

```c
__int64 __fastcall AiCheckSecureApplicationDirectory(const unsigned __int16 *a1, unsigned int *a2)
{
  WCHAR *v3; // rbp
  HANDLE FileW; // rax
  void *v5; // rdi
  int v6; // ebx
  DWORD FinalPathNameByHandleW; // eax
  DWORD v8; // esi
  ULONG LastError; // eax
  WCHAR *v10; // rax
  NTSTATUS v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-88h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-80h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-78h]
  UNICODE_STRING String2; // [rsp+40h] [rbp-68h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+50h] [rbp-58h] BYREF

  *a2 = 0;
  String2 = 0;
  v3 = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0x2000000u, 0);// Object/reg path-trust audit: secure-directory check opens caller path and derives final path by handle before prefix checks; string-only DOS device/symlink prefix spoof not sufficient.
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_4;
  v6 = 8;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 8u);
  v8 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
    goto LABEL_4;
  v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * (FinalPathNameByHandleW + 1));
  v3 = v10;
  if ( !v10 )
  {
    LocalFree(0);
    RtlReleaseRelativeName(&RelativeName);
    CloseHandle(v5);
    goto LABEL_12;
  }
  if ( GetFinalPathNameByHandleW(v5, v10, v8, 8u) )
  {
    v6 = 0;
    v11 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(
            v3,
            &String2,
            0,
            &RelativeName,
            dwCreationDisposition,
            dwFlagsAndAttributes,
            hTemplateFile);
    String2.MaximumLength += 2;
    if ( v11 >= 0 )
      goto LABEL_11;
    LastError = RtlNtStatusToDosErrorNoTeb(v11);
  }
  else
  {
LABEL_4:
    LastError = GetLastError();
  }
  v6 = LastError;
LABEL_11:
  LocalFree(v3);
  RtlReleaseRelativeName(&RelativeName);
  CloseHandle(v5);
  if ( v6 )
  {
LABEL_12:
    v12 = 0;
    if ( v6 != 5 )
      v12 = v6;
    goto LABEL_24;
  }
  v12 = 0;
  v13 = 0;
  while ( !RtlPrefixUnicodeString((PCUNICODE_STRING)&(&g_Dirs)[2 * v13], &String2, 1u) )
  {
    if ( ++v13 >= 3 )
    {
      if ( v13 == 3 )
        goto LABEL_24;
      break;
    }
  }
  if ( !v13 )
    goto LABEL_23;
  v14 = v13 - 1;
  if ( !v14 )
  {
    AipCheckSecureWindowsDirectory(&String2, a2);
    goto LABEL_24;
  }
  if ( v14 == 1 && g_bPFX86Supported )
LABEL_23:
    AipCheckSecurePFDirectory(&String2, a2);
LABEL_24:
  RtlFreeUnicodeString(&String2);
  return v12;
}

```

## disassembly

```asm
0x18000f210  push    rbx
0x18000f212  push    rbp
0x18000f213  push    rsi
0x18000f214  push    rdi
0x18000f215  push    r14
0x18000f217  push    r15
0x18000f219  sub     rsp, 78h
0x18000f21d  xor     r15d, r15d
0x18000f220  xorps   xmm0, xmm0
0x18000f223  mov     [rdx], r15d
0x18000f226  mov     r14, rdx
0x18000f229  mov     [rsp+0A8h+hTemplateFile], r15; hTemplateFile
0x18000f22e  mov     edx, 80000000h; dwDesiredAccess
0x18000f233  movups  xmmword ptr [rsp+0A8h+RelativeName.RelativeName.MaximumLength], xmm0
0x18000f238  mov     dword ptr [rsp+0A8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000f240  xor     r9d, r9d; lpSecurityAttributes
0x18000f243  mov     r8d, 5; dwShareMode
0x18000f249  mov     dword ptr [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000f251  movups  xmmword ptr [rsp+0A8h+String2.Length], xmm0
0x18000f256  mov     ebp, r15d
0x18000f259  mov     [rsp+0A8h+RelativeName.RelativeName.Length], r15w
0x18000f25f  movups  xmmword ptr [rsp+0A8h+RelativeName.ContainingDirectory], xmm0
0x18000f264  call    cs:__imp_CreateFileW; Object/reg path-trust audit: secure-directory check opens caller path and derives final path by handle before prefix checks; string-only DOS device/symlink prefix spoof not sufficient.
0x18000f26a  mov     rdi, rax
0x18000f26d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f271  jnz     short loc_18000F27E
0x18000f273  call    cs:__imp_GetLastError
0x18000f279  jmp     loc_18000F326
0x18000f27e  mov     ebx, 8
0x18000f283  xor     r8d, r8d; cchFilePath
0x18000f286  mov     r9d, ebx; dwFlags
0x18000f289  xor     edx, edx; lpszFilePath
0x18000f28b  mov     rcx, rdi; hFile
0x18000f28e  call    cs:__imp_GetFinalPathNameByHandleW
0x18000f294  mov     esi, eax
0x18000f296  test    eax, eax
0x18000f298  jnz     short loc_18000F2A5
0x18000f29a  call    cs:__imp_GetLastError
0x18000f2a0  jmp     loc_18000F326
0x18000f2a5  lea     edx, [rax+1]
0x18000f2a8  mov     ecx, 40h ; '@'; uFlags
0x18000f2ad  add     rdx, rdx; uBytes
0x18000f2b0  call    cs:__imp_LocalAlloc
0x18000f2b6  mov     rbp, rax
0x18000f2b9  test    rax, rax
0x18000f2bc  jnz     short loc_18000F2DD
0x18000f2be  mov     rcx, rax; hMem
0x18000f2c1  call    cs:__imp_LocalFree
0x18000f2c7  lea     rcx, [rsp+0A8h+RelativeName]; RelativeName
0x18000f2cc  call    cs:__imp_RtlReleaseRelativeName
0x18000f2d2  mov     rcx, rdi; hObject
0x18000f2d5  call    cs:__imp_CloseHandle
0x18000f2db  jmp     short loc_18000F349
0x18000f2dd  mov     r9d, ebx; dwFlags
0x18000f2e0  mov     r8d, esi; cchFilePath
0x18000f2e3  mov     rdx, rbp; lpszFilePath
0x18000f2e6  mov     rcx, rdi; hFile
0x18000f2e9  call    cs:__imp_GetFinalPathNameByHandleW
0x18000f2ef  test    eax, eax
0x18000f2f1  jnz     short loc_18000F2FB
0x18000f2f3  call    cs:__imp_GetLastError
0x18000f2f9  jmp     short loc_18000F326
0x18000f2fb  lea     r9, [rsp+0A8h+RelativeName]
0x18000f300  xor     r8d, r8d
0x18000f303  lea     rdx, [rsp+0A8h+String2]
0x18000f308  mov     rcx, rbp
0x18000f30b  mov     ebx, r15d
0x18000f30e  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18000f314  add     [rsp+0A8h+String2.MaximumLength], 2
0x18000f31a  test    eax, eax
0x18000f31c  jns     short loc_18000F328
0x18000f31e  mov     ecx, eax; Status
0x18000f320  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000f326  mov     ebx, eax
0x18000f328  mov     rcx, rbp; hMem
0x18000f32b  call    cs:__imp_LocalFree
0x18000f331  lea     rcx, [rsp+0A8h+RelativeName]; RelativeName
0x18000f336  call    cs:__imp_RtlReleaseRelativeName
0x18000f33c  mov     rcx, rdi; hObject
0x18000f33f  call    cs:__imp_CloseHandle
0x18000f345  test    ebx, ebx
0x18000f347  jz      short loc_18000F354
0x18000f349  cmp     ebx, 5
0x18000f34c  mov     edi, r15d
0x18000f34f  cmovnz  edi, ebx
0x18000f352  jmp     short loc_18000F3A8
0x18000f354  mov     edi, r15d
0x18000f357  lea     rsi, ?g_Dirs@@3PAU_UNICODE_STRING@@A; _UNICODE_STRING near * g_Dirs
0x18000f35e  mov     ebx, r15d
0x18000f361  mov     ecx, ebx
0x18000f363  lea     rdx, [rsp+0A8h+String2]; String2
0x18000f368  shl     rcx, 4
0x18000f36c  mov     r8b, 1; CaseInsensitive
0x18000f36f  add     rcx, rsi; String1
0x18000f372  call    cs:__imp_RtlPrefixUnicodeString
0x18000f378  test    al, al
0x18000f37a  jnz     short loc_18000F385
0x18000f37c  inc     ebx
0x18000f37e  cmp     ebx, 3
0x18000f381  jb      short loc_18000F361
0x18000f383  jz      short loc_18000F3A8
0x18000f385  test    ebx, ebx
0x18000f387  jz      short loc_18000F39B
0x18000f389  sub     ebx, 1
0x18000f38c  jz      short loc_18000F3C2
0x18000f38e  cmp     ebx, 1
0x18000f391  jnz     short loc_18000F3A8
0x18000f393  cmp     cs:?g_bPFX86Supported@@3HA, edi; int g_bPFX86Supported
0x18000f399  jz      short loc_18000F3A8
0x18000f39b  mov     rdx, r14; unsigned int *
0x18000f39e  lea     rcx, [rsp+0A8h+String2]; String2
0x18000f3a3  call    ?AipCheckSecurePFDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z; AipCheckSecurePFDirectory(_UNICODE_STRING *,ulong *)
0x18000f3a8  lea     rcx, [rsp+0A8h+String2]; UnicodeString
0x18000f3ad  call    cs:__imp_RtlFreeUnicodeString
0x18000f3b3  mov     eax, edi
0x18000f3b5  add     rsp, 78h
0x18000f3b9  pop     r15
0x18000f3bb  pop     r14
0x18000f3bd  pop     rdi
0x18000f3be  pop     rsi
0x18000f3bf  pop     rbp
0x18000f3c0  pop     rbx
0x18000f3c1  retn
0x18000f3c2  mov     rdx, r14; unsigned int *
0x18000f3c5  lea     rcx, [rsp+0A8h+String2]; struct _UNICODE_STRING *
0x18000f3ca  call    ?AipCheckSecureWindowsDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z; AipCheckSecureWindowsDirectory(_UNICODE_STRING *,ulong *)
0x18000f3cf  jmp     short loc_18000F3A8
```
