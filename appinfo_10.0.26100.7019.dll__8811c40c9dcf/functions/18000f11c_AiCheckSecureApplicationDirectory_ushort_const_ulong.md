# AiCheckSecureApplicationDirectory(ushort const *,ulong *)

- ea: `0x18000f11c`
- end: `0x18000f313`
- name: `?AiCheckSecureApplicationDirectory@@YAKPEBGPEAK@Z`
- size: `503`
- prototype: `unsigned int(const unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18000f990`
- `0x18002b828`
- `0x180039cb0`
- `0x18003c4c4`

## callees

- `0x18000f11c`
- `0x180016e50`
- `0x180016f00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f197`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f261`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f261`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f242`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f242`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f1d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f1d4`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f1b6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f1fc`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f1b6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000f1fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f182`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f182`
- `ntdll!RtlFreeUnicodeString` at `0x18000f2d8`
- `ntdll!RtlFreeUnicodeString` at `0x18000f2d8`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000f21a`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000f21a`
- `ntdll!RtlReleaseRelativeName` at `0x18000f252`
- `ntdll!RtlReleaseRelativeName` at `0x18000f252`
- `ntdll!RtlPrefixUnicodeString` at `0x18000f294`
- `ntdll!RtlPrefixUnicodeString` at `0x18000f294`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000f231`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000f231`

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
0x18000f11c  mov     r11, rsp
0x18000f11f  mov     [r11+8], rbx
0x18000f123  mov     [r11+10h], rsi
0x18000f127  mov     [r11+18h], rdi
0x18000f12b  mov     [r11+20h], r12
0x18000f12f  push    rbp
0x18000f130  push    r14
0x18000f132  push    r15
0x18000f134  mov     rbp, rsp
0x18000f137  sub     rsp, 70h
0x18000f13b  xor     edi, edi
0x18000f13d  xor     eax, eax
0x18000f13f  xorps   xmm0, xmm0
0x18000f142  mov     [r11-58h], rdi
0x18000f146  mov     r14, rdx
0x18000f149  mov     [rdx], edi
0x18000f14b  mov     [rsp+70h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000f153  xor     r9d, r9d; lpSecurityAttributes
0x18000f156  lea     r8d, [rdi+5]; dwShareMode
0x18000f15a  mov     [rbp+RelativeName.RelativeName.Length], di
0x18000f15e  mov     edx, 80000000h; dwDesiredAccess
0x18000f163  mov     [rbp+RelativeName.ContainingDirectory+2], rax
0x18000f167  movups  xmmword ptr [rbp+String2.Length], xmm0
0x18000f16b  mov     esi, edi
0x18000f16d  mov     dword ptr [rbp+RelativeName.CurDirRef+2], eax
0x18000f170  mov     ebx, edi
0x18000f172  mov     word ptr [rbp+RelativeName.CurDirRef+6], ax
0x18000f176  movups  xmmword ptr [rbp+RelativeName.RelativeName.MaximumLength], xmm0
0x18000f17a  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x18000f182  call    cs:__imp_CreateFileW
0x18000f189  nop     dword ptr [rax+rax+00h]
0x18000f18e  mov     r12, rax
0x18000f191  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f195  jnz     short loc_18000F1A8
0x18000f197  call    cs:__imp_GetLastError
0x18000f19e  nop     dword ptr [rax+rax+00h]
0x18000f1a3  jmp     loc_18000F23D
0x18000f1a8  mov     r9d, 8; dwFlags
0x18000f1ae  xor     r8d, r8d; cchFilePath
0x18000f1b1  xor     edx, edx; lpszFilePath
0x18000f1b3  mov     rcx, r12; hFile
0x18000f1b6  call    cs:__imp_GetFinalPathNameByHandleW
0x18000f1bd  nop     dword ptr [rax+rax+00h]
0x18000f1c2  mov     r15d, eax
0x18000f1c5  test    eax, eax
0x18000f1c7  jz      short loc_18000F197
0x18000f1c9  lea     edx, [rax+1]
0x18000f1cc  mov     ecx, 40h ; '@'; uFlags
0x18000f1d1  add     rdx, rdx; uBytes
0x18000f1d4  call    cs:__imp_LocalAlloc
0x18000f1db  nop     dword ptr [rax+rax+00h]
0x18000f1e0  mov     rbx, rax
0x18000f1e3  test    rax, rax
0x18000f1e6  jnz     short loc_18000F1ED
0x18000f1e8  lea     esi, [rax+8]
0x18000f1eb  jmp     short loc_18000F23F
0x18000f1ed  mov     r9d, 8; dwFlags
0x18000f1f3  mov     r8d, r15d; cchFilePath
0x18000f1f6  mov     rdx, rbx; lpszFilePath
0x18000f1f9  mov     rcx, r12; hFile
0x18000f1fc  call    cs:__imp_GetFinalPathNameByHandleW
0x18000f203  nop     dword ptr [rax+rax+00h]
0x18000f208  test    eax, eax
0x18000f20a  jz      short loc_18000F197
0x18000f20c  lea     r9, [rbp+RelativeName]
0x18000f210  xor     r8d, r8d
0x18000f213  lea     rdx, [rbp+String2]
0x18000f217  mov     rcx, rbx
0x18000f21a  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18000f221  nop     dword ptr [rax+rax+00h]
0x18000f226  add     [rbp+String2.MaximumLength], 2
0x18000f22b  test    eax, eax
0x18000f22d  jns     short loc_18000F23F
0x18000f22f  mov     ecx, eax; Status
0x18000f231  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000f238  nop     dword ptr [rax+rax+00h]
0x18000f23d  mov     esi, eax
0x18000f23f  mov     rcx, rbx; hMem
0x18000f242  call    cs:__imp_LocalFree
0x18000f249  nop     dword ptr [rax+rax+00h]
0x18000f24e  lea     rcx, [rbp+RelativeName]; RelativeName
0x18000f252  call    cs:__imp_RtlReleaseRelativeName
0x18000f259  nop     dword ptr [rax+rax+00h]
0x18000f25e  mov     rcx, r12; hObject
0x18000f261  call    cs:__imp_CloseHandle
0x18000f268  nop     dword ptr [rax+rax+00h]
0x18000f26d  test    esi, esi
0x18000f26f  jz      short loc_18000F27B
0x18000f271  cmp     esi, 5
0x18000f274  cmovnz  edi, esi
0x18000f277  mov     esi, edi
0x18000f279  jmp     short loc_18000F2D4
0x18000f27b  mov     ebx, edi
0x18000f27d  lea     rax, ?g_Dirs@@3PAU_UNICODE_STRING@@A; _UNICODE_STRING near * g_Dirs
0x18000f284  mov     ecx, ebx
0x18000f286  shl     rcx, 4
0x18000f28a  lea     rdx, [rbp+String2]; String2
0x18000f28e  add     rcx, rax; String1
0x18000f291  mov     r8b, 1; CaseInsensitive
0x18000f294  call    cs:__imp_RtlPrefixUnicodeString
0x18000f29b  nop     dword ptr [rax+rax+00h]
0x18000f2a0  test    al, al
0x18000f2a2  jnz     short loc_18000F2B2
0x18000f2a4  inc     ebx
0x18000f2a6  mov     eax, ebx
0x18000f2a8  cmp     ebx, 3
0x18000f2ab  jb      short loc_18000F27D
0x18000f2ad  cmp     eax, 3
0x18000f2b0  jz      short loc_18000F2D4
0x18000f2b2  test    ebx, ebx
0x18000f2b4  jz      short loc_18000F2C8
0x18000f2b6  sub     ebx, 1
0x18000f2b9  jz      short loc_18000F305
0x18000f2bb  cmp     ebx, 1
0x18000f2be  jnz     short loc_18000F2D4
0x18000f2c0  cmp     cs:?g_bPFX86Supported@@3HA, edi; int g_bPFX86Supported
0x18000f2c6  jz      short loc_18000F2D4
0x18000f2c8  mov     rdx, r14; unsigned int *
0x18000f2cb  lea     rcx, [rbp+String2]; String2
0x18000f2cf  call    ?AipCheckSecurePFDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z; AipCheckSecurePFDirectory(_UNICODE_STRING *,ulong *)
0x18000f2d4  lea     rcx, [rbp+String2]; UnicodeString
0x18000f2d8  call    cs:__imp_RtlFreeUnicodeString
0x18000f2df  nop     dword ptr [rax+rax+00h]
0x18000f2e4  lea     r11, [rsp+70h+var_s0]
0x18000f2e9  mov     eax, esi
0x18000f2eb  mov     rbx, [r11+20h]
0x18000f2ef  mov     rsi, [r11+28h]
0x18000f2f3  mov     rdi, [r11+30h]
0x18000f2f7  mov     r12, [r11+38h]
0x18000f2fb  mov     rsp, r11
0x18000f2fe  pop     r15
0x18000f300  pop     r14
0x18000f302  pop     rbp
0x18000f303  retn
0x18000f305  mov     rdx, r14; unsigned int *
0x18000f308  lea     rcx, [rbp+String2]; struct _UNICODE_STRING *
0x18000f30c  call    ?AipCheckSecureWindowsDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z; AipCheckSecureWindowsDirectory(_UNICODE_STRING *,ulong *)
0x18000f311  jmp     short loc_18000F2D4
```
