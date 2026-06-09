# AipNormalizePath(ushort const *,_UNICODE_STRING *)

- ea: `0x1800135d4`
- end: `0x18001373a`
- name: `?AipNormalizePath@@YAKPEBGPEAU_UNICODE_STRING@@@Z`
- size: `358`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180013de0`
- `0x18003ccb0`
- `0x18003d0c8`

## callees

- `0x1800135d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013645`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013710`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013681`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013681`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180013664`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800136a9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180013664`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800136a9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013630`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013630`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800136c7`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800136c7`
- `ntdll!RtlReleaseRelativeName` at `0x180013701`
- `ntdll!RtlReleaseRelativeName` at `0x180013701`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800136df`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800136df`

## pseudocode

```c
__int64 __fastcall AipNormalizePath(const unsigned __int16 *a1, struct _UNICODE_STRING *a2)
{
  unsigned int v2; // ebx
  WCHAR *v4; // rdi
  HANDLE FileW; // rax
  void *v6; // rsi
  ULONG LastError; // eax
  DWORD FinalPathNameByHandleW; // eax
  DWORD v9; // ebp
  WCHAR *v10; // rax
  NTSTATUS v11; // eax
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+40h] [rbp-28h] BYREF

  v2 = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  v4 = 0;
  FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0x2000000u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_2;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 8u);
  v9 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
    goto LABEL_2;
  v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * (FinalPathNameByHandleW + 1));
  v4 = v10;
  if ( v10 )
  {
    if ( GetFinalPathNameByHandleW(v6, v10, v9, 8u) )
    {
      v11 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(v4, a2, 0, &RelativeName);
      a2->MaximumLength += 2;
      if ( v11 >= 0 )
        goto LABEL_10;
      LastError = RtlNtStatusToDosErrorNoTeb(v11);
LABEL_9:
      v2 = LastError;
      goto LABEL_10;
    }
LABEL_2:
    LastError = GetLastError();
    goto LABEL_9;
  }
  v2 = 8;
LABEL_10:
  LocalFree(v4);
  RtlReleaseRelativeName(&RelativeName);
  CloseHandle(v6);
  return v2;
}

```

## disassembly

```asm
0x1800135d4  mov     r11, rsp
0x1800135d7  mov     [r11+8], rbx
0x1800135db  mov     [r11+10h], rbp
0x1800135df  mov     [r11+18h], rsi
0x1800135e3  mov     [r11+20h], rdi
0x1800135e7  push    r14
0x1800135e9  sub     rsp, 60h
0x1800135ed  xor     ebx, ebx
0x1800135ef  xor     eax, eax
0x1800135f1  mov     [r11-38h], rbx
0x1800135f5  xorps   xmm0, xmm0
0x1800135f8  mov     r14, rdx
0x1800135fb  mov     [rsp+68h+RelativeName.RelativeName.Length], bx
0x180013600  movups  xmmword ptr [rsp+68h+RelativeName.RelativeName.MaximumLength], xmm0
0x180013605  mov     [r11-16h], rax
0x180013609  lea     r8d, [rbx+5]; dwShareMode
0x18001360d  mov     [rsp+68h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180013615  xor     r9d, r9d; lpSecurityAttributes
0x180013618  mov     edx, 80000000h; dwDesiredAccess
0x18001361d  mov     dword ptr [rsp+68h+RelativeName.CurDirRef+2], eax
0x180013621  mov     edi, ebx
0x180013623  mov     word ptr [rsp+68h+RelativeName.CurDirRef+6], ax
0x180013628  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180013630  call    cs:__imp_CreateFileW
0x180013637  nop     dword ptr [rax+rax+00h]
0x18001363c  mov     rsi, rax
0x18001363f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013643  jnz     short loc_180013656
0x180013645  call    cs:__imp_GetLastError
0x18001364c  nop     dword ptr [rax+rax+00h]
0x180013651  jmp     loc_1800136EB
0x180013656  mov     r9d, 8; dwFlags
0x18001365c  xor     r8d, r8d; cchFilePath
0x18001365f  xor     edx, edx; lpszFilePath
0x180013661  mov     rcx, rsi; hFile
0x180013664  call    cs:__imp_GetFinalPathNameByHandleW
0x18001366b  nop     dword ptr [rax+rax+00h]
0x180013670  mov     ebp, eax
0x180013672  test    eax, eax
0x180013674  jz      short loc_180013645
0x180013676  lea     edx, [rax+1]
0x180013679  mov     ecx, 40h ; '@'; uFlags
0x18001367e  add     rdx, rdx; uBytes
0x180013681  call    cs:__imp_LocalAlloc
0x180013688  nop     dword ptr [rax+rax+00h]
0x18001368d  mov     rdi, rax
0x180013690  test    rax, rax
0x180013693  jnz     short loc_18001369A
0x180013695  lea     ebx, [rax+8]
0x180013698  jmp     short loc_1800136ED
0x18001369a  mov     r9d, 8; dwFlags
0x1800136a0  mov     r8d, ebp; cchFilePath
0x1800136a3  mov     rdx, rdi; lpszFilePath
0x1800136a6  mov     rcx, rsi; hFile
0x1800136a9  call    cs:__imp_GetFinalPathNameByHandleW
0x1800136b0  nop     dword ptr [rax+rax+00h]
0x1800136b5  test    eax, eax
0x1800136b7  jz      short loc_180013645
0x1800136b9  lea     r9, [rsp+68h+RelativeName]
0x1800136be  xor     r8d, r8d
0x1800136c1  mov     rdx, r14
0x1800136c4  mov     rcx, rdi
0x1800136c7  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1800136ce  nop     dword ptr [rax+rax+00h]
0x1800136d3  add     word ptr [r14+2], 2
0x1800136d9  test    eax, eax
0x1800136db  jns     short loc_1800136ED
0x1800136dd  mov     ecx, eax; Status
0x1800136df  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800136e6  nop     dword ptr [rax+rax+00h]
0x1800136eb  mov     ebx, eax
0x1800136ed  mov     rcx, rdi; hMem
0x1800136f0  call    cs:__imp_LocalFree
0x1800136f7  nop     dword ptr [rax+rax+00h]
0x1800136fc  lea     rcx, [rsp+68h+RelativeName]; RelativeName
0x180013701  call    cs:__imp_RtlReleaseRelativeName
0x180013708  nop     dword ptr [rax+rax+00h]
0x18001370d  mov     rcx, rsi; hObject
0x180013710  call    cs:__imp_CloseHandle
0x180013717  nop     dword ptr [rax+rax+00h]
0x18001371c  lea     r11, [rsp+68h+var_8]
0x180013721  mov     eax, ebx
0x180013723  mov     rbx, [r11+10h]
0x180013727  mov     rbp, [r11+18h]
0x18001372b  mov     rsi, [r11+20h]
0x18001372f  mov     rdi, [r11+28h]
0x180013733  mov     rsp, r11
0x180013736  pop     r14
0x180013738  retn
```
