# AiCheckSecureApplicationDirectory(ushort const *,ulong *)

- ea: `0x18000f24c`
- end: `0x18000f443`
- name: `?AiCheckSecureApplicationDirectory@@YAKPEBGPEAK@Z`
- size: `503`
- prototype: `unsigned int(const unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18000fac0`
- `0x18002a2a8`
- `0x18003ac30`
- `0x18003e5d4`

## callees

- `0x18000f24c`
- `0x180017108`
- `0x1800171b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f391`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f372`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f372`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f304`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f304`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f2e6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f32c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f2e6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f32c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f2b2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f2b2`
- `ntdll!RtlFreeUnicodeString` at `0x18000f408`
- `ntdll!RtlFreeUnicodeString` at `0x18000f408`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000f34a`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000f34a`
- `ntdll!RtlReleaseRelativeName` at `0x18000f382`
- `ntdll!RtlReleaseRelativeName` at `0x18000f382`
- `ntdll!RtlPrefixUnicodeString` at `0x18000f3c4`
- `ntdll!RtlPrefixUnicodeString` at `0x18000f3c4`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000f361`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000f361`

## pseudocode

```c
__int64 __fastcall AiCheckSecureApplicationDirectory(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int v2; // edi
  unsigned int v4; // esi
  WCHAR *v5; // rbx
  HANDLE FileW; // rax
  void *v7; // r12
  ULONG LastError; // eax
  DWORD FinalPathNameByHandleW; // eax
  DWORD v10; // r15d
  WCHAR *v11; // rax
  NTSTATUS v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  UNICODE_STRING String2; // [rsp+40h] [rbp-30h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+50h] [rbp-20h] BYREF

  v2 = 0;
  *a2 = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  String2 = 0;
  v4 = 0;
  v5 = 0;
  FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0x2000000u, 0);
  v7 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_2;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 8u);
  v10 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
    goto LABEL_2;
  v11 = (WCHAR *)LocalAlloc(0x40u, 2LL * (FinalPathNameByHandleW + 1));
  v5 = v11;
  if ( !v11 )
  {
    v4 = 8;
    goto LABEL_10;
  }
  if ( GetFinalPathNameByHandleW(v7, v11, v10, 8u) )
  {
    v12 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(v5, &String2, 0, &RelativeName);
    String2.MaximumLength += 2;
    if ( v12 >= 0 )
      goto LABEL_10;
    LastError = RtlNtStatusToDosErrorNoTeb(v12);
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
  }
  v4 = LastError;
LABEL_10:
  LocalFree(v5);
  RtlReleaseRelativeName(&RelativeName);
  CloseHandle(v7);
  if ( v4 )
  {
    if ( v4 != 5 )
      v2 = v4;
    v4 = v2;
  }
  else
  {
    v13 = 0;
    while ( !RtlPrefixUnicodeString(&g_Dirs + v13, &String2, 1u) )
    {
      if ( ++v13 >= 3 )
      {
        if ( v13 == 3 )
          goto LABEL_23;
        break;
      }
    }
    if ( !v13 )
      goto LABEL_22;
    v14 = v13 - 1;
    if ( !v14 )
    {
      AipCheckSecureWindowsDirectory(&String2, a2);
      goto LABEL_23;
    }
    if ( v14 == 1 && g_bPFX86Supported )
LABEL_22:
      AipCheckSecurePFDirectory(&String2, a2);
  }
LABEL_23:
  RtlFreeUnicodeString(&String2);
  return v4;
}

```

## disassembly

```asm
0x18000f24c  mov     r11, rsp
0x18000f24f  mov     [r11+8], rbx
0x18000f253  mov     [r11+10h], rsi
0x18000f257  mov     [r11+18h], rdi
0x18000f25b  mov     [r11+20h], r12
0x18000f25f  push    rbp
0x18000f260  push    r14
0x18000f262  push    r15
0x18000f264  mov     rbp, rsp
0x18000f267  sub     rsp, 70h
0x18000f26b  xor     edi, edi
0x18000f26d  xor     eax, eax
0x18000f26f  xorps   xmm0, xmm0
0x18000f272  mov     [r11-58h], rdi
0x18000f276  mov     r14, rdx
0x18000f279  mov     [rdx], edi
0x18000f27b  mov     [rsp+70h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000f283  xor     r9d, r9d; lpSecurityAttributes
0x18000f286  lea     r8d, [rdi+5]; dwShareMode
0x18000f28a  mov     [rbp+RelativeName.RelativeName.Length], di
0x18000f28e  mov     edx, 80000000h; dwDesiredAccess
0x18000f293  mov     [rbp+RelativeName.ContainingDirectory+2], rax
0x18000f297  movups  xmmword ptr [rbp+String2.Length], xmm0
0x18000f29b  mov     esi, edi
0x18000f29d  mov     dword ptr [rbp+RelativeName.CurDirRef+2], eax
0x18000f2a0  mov     ebx, edi
0x18000f2a2  mov     word ptr [rbp+RelativeName.CurDirRef+6], ax
0x18000f2a6  movups  xmmword ptr [rbp+RelativeName.RelativeName.MaximumLength], xmm0
0x18000f2aa  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x18000f2b2  call    cs:__imp_CreateFileW
0x18000f2b9  nop     dword ptr [rax+rax+00h]
0x18000f2be  mov     r12, rax
0x18000f2c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f2c5  jnz     short loc_18000F2D8
0x18000f2c7  call    cs:__imp_GetLastError
0x18000f2ce  nop     dword ptr [rax+rax+00h]
0x18000f2d3  jmp     loc_18000F36D
0x18000f2d8  mov     r9d, 8; dwFlags
0x18000f2de  xor     r8d, r8d; cchFilePath
0x18000f2e1  xor     edx, edx; lpszFilePath
0x18000f2e3  mov     rcx, r12; hFile
0x18000f2e6  call    cs:__imp_GetFinalPathNameByHandleW
0x18000f2ed  nop     dword ptr [rax+rax+00h]
0x18000f2f2  mov     r15d, eax
0x18000f2f5  test    eax, eax
0x18000f2f7  jz      short loc_18000F2C7
0x18000f2f9  lea     edx, [rax+1]
0x18000f2fc  mov     ecx, 40h ; '@'; uFlags
0x18000f301  add     rdx, rdx; uBytes
0x18000f304  call    cs:__imp_LocalAlloc
0x18000f30b  nop     dword ptr [rax+rax+00h]
0x18000f310  mov     rbx, rax
0x18000f313  test    rax, rax
0x18000f316  jnz     short loc_18000F31D
0x18000f318  lea     esi, [rax+8]
0x18000f31b  jmp     short loc_18000F36F
0x18000f31d  mov     r9d, 8; dwFlags
0x18000f323  mov     r8d, r15d; cchFilePath
0x18000f326  mov     rdx, rbx; lpszFilePath
0x18000f329  mov     rcx, r12; hFile
0x18000f32c  call    cs:__imp_GetFinalPathNameByHandleW
0x18000f333  nop     dword ptr [rax+rax+00h]
0x18000f338  test    eax, eax
0x18000f33a  jz      short loc_18000F2C7
0x18000f33c  lea     r9, [rbp+RelativeName]
0x18000f340  xor     r8d, r8d
0x18000f343  lea     rdx, [rbp+String2]
0x18000f347  mov     rcx, rbx
0x18000f34a  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18000f351  nop     dword ptr [rax+rax+00h]
0x18000f356  add     [rbp+String2.MaximumLength], 2
0x18000f35b  test    eax, eax
0x18000f35d  jns     short loc_18000F36F
0x18000f35f  mov     ecx, eax; Status
0x18000f361  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000f368  nop     dword ptr [rax+rax+00h]
0x18000f36d  mov     esi, eax
0x18000f36f  mov     rcx, rbx; hMem
0x18000f372  call    cs:__imp_LocalFree
0x18000f379  nop     dword ptr [rax+rax+00h]
0x18000f37e  lea     rcx, [rbp+RelativeName]; RelativeName
0x18000f382  call    cs:__imp_RtlReleaseRelativeName
0x18000f389  nop     dword ptr [rax+rax+00h]
0x18000f38e  mov     rcx, r12; hObject
0x18000f391  call    cs:__imp_CloseHandle
0x18000f398  nop     dword ptr [rax+rax+00h]
0x18000f39d  test    esi, esi
0x18000f39f  jz      short loc_18000F3AB
0x18000f3a1  cmp     esi, 5
0x18000f3a4  cmovnz  edi, esi
0x18000f3a7  mov     esi, edi
0x18000f3a9  jmp     short loc_18000F404
0x18000f3ab  mov     ebx, edi
0x18000f3ad  lea     rax, ?g_Dirs@@3PAU_UNICODE_STRING@@A; _UNICODE_STRING near * g_Dirs
0x18000f3b4  mov     ecx, ebx
0x18000f3b6  shl     rcx, 4
0x18000f3ba  lea     rdx, [rbp+String2]; String2
0x18000f3be  add     rcx, rax; String1
0x18000f3c1  mov     r8b, 1; CaseInsensitive
0x18000f3c4  call    cs:__imp_RtlPrefixUnicodeString
0x18000f3cb  nop     dword ptr [rax+rax+00h]
0x18000f3d0  test    al, al
0x18000f3d2  jnz     short loc_18000F3E2
0x18000f3d4  inc     ebx
0x18000f3d6  mov     eax, ebx
0x18000f3d8  cmp     ebx, 3
0x18000f3db  jb      short loc_18000F3AD
0x18000f3dd  cmp     eax, 3
0x18000f3e0  jz      short loc_18000F404
0x18000f3e2  test    ebx, ebx
0x18000f3e4  jz      short loc_18000F3F8
0x18000f3e6  sub     ebx, 1
0x18000f3e9  jz      short loc_18000F435
0x18000f3eb  cmp     ebx, 1
0x18000f3ee  jnz     short loc_18000F404
0x18000f3f0  cmp     cs:?g_bPFX86Supported@@3HA, edi; int g_bPFX86Supported
0x18000f3f6  jz      short loc_18000F404
0x18000f3f8  mov     rdx, r14; unsigned int *
0x18000f3fb  lea     rcx, [rbp+String2]; String2
0x18000f3ff  call    ?AipCheckSecurePFDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z; AipCheckSecurePFDirectory(_UNICODE_STRING *,ulong *)
0x18000f404  lea     rcx, [rbp+String2]; UnicodeString
0x18000f408  call    cs:__imp_RtlFreeUnicodeString
0x18000f40f  nop     dword ptr [rax+rax+00h]
0x18000f414  lea     r11, [rsp+70h+var_s0]
0x18000f419  mov     eax, esi
0x18000f41b  mov     rbx, [r11+20h]
0x18000f41f  mov     rsi, [r11+28h]
0x18000f423  mov     rdi, [r11+30h]
0x18000f427  mov     r12, [r11+38h]
0x18000f42b  mov     rsp, r11
0x18000f42e  pop     r15
0x18000f430  pop     r14
0x18000f432  pop     rbp
0x18000f433  retn
0x18000f435  mov     rdx, r14; unsigned int *
0x18000f438  lea     rcx, [rbp+String2]; struct _UNICODE_STRING *
0x18000f43c  call    ?AipCheckSecureWindowsDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z; AipCheckSecureWindowsDirectory(_UNICODE_STRING *,ulong *)
0x18000f441  jmp     short loc_18000F404
```
