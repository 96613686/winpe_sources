# AipNormalizePath(ushort const *,_UNICODE_STRING *)

- ea: `0x180011c6c`
- end: `0x180011d65`
- name: `?AipNormalizePath@@YAKPEBGPEAU_UNICODE_STRING@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18003fa00`
- `0x18003fde4`
- `0x180040164`

## callees

- `0x180011c6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011d3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011d3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011ced`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011ced`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180011cd8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180011d07`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180011cd8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180011d07`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011cb1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011cb1`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180011d21`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180011d21`
- `ntdll!RtlReleaseRelativeName` at `0x180011d49`
- `ntdll!RtlReleaseRelativeName` at `0x180011d49`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180011d33`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180011d33`

## pseudocode

```c
__int64 __fastcall AipNormalizePath(const unsigned __int16 *a1, struct _UNICODE_STRING *a2)
{
  WCHAR *v3; // rdi
  HANDLE FileW; // rax
  void *v5; // rsi
  DWORD LastError; // eax
  unsigned int v7; // ebx
  DWORD FinalPathNameByHandleW; // eax
  DWORD v9; // ebp
  WCHAR *v10; // rax
  NTSTATUS v11; // eax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-68h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-60h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-58h]
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+40h] [rbp-48h] BYREF

  v3 = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0x2000000u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_2;
  v7 = 8;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 8u);
  v9 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
    goto LABEL_2;
  v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * (FinalPathNameByHandleW + 1));
  v3 = v10;
  if ( !v10 )
    goto LABEL_9;
  if ( !GetFinalPathNameByHandleW(v5, v10, v9, 8u) )
  {
LABEL_2:
    LastError = GetLastError();
LABEL_8:
    v7 = LastError;
    goto LABEL_9;
  }
  v7 = 0;
  v11 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(
          v3,
          a2,
          0,
          &RelativeName,
          dwCreationDisposition,
          dwFlagsAndAttributes,
          hTemplateFile);
  a2->MaximumLength += 2;
  if ( v11 < 0 )
  {
    LastError = RtlNtStatusToDosErrorNoTeb(v11);
    goto LABEL_8;
  }
LABEL_9:
  LocalFree(v3);
  RtlReleaseRelativeName(&RelativeName);
  CloseHandle(v5);
  return v7;
}

```

## disassembly

```asm
0x180011c6c  push    rbx
0x180011c6e  push    rbp
0x180011c6f  push    rsi
0x180011c70  push    rdi
0x180011c71  push    r14
0x180011c73  sub     rsp, 60h
0x180011c77  xor     eax, eax
0x180011c79  xorps   xmm0, xmm0
0x180011c7c  mov     [rsp+88h+hTemplateFile], rax; hTemplateFile
0x180011c81  mov     r14, rdx
0x180011c84  movups  xmmword ptr [rsp+88h+RelativeName.RelativeName.MaximumLength], xmm0
0x180011c89  xor     edi, edi
0x180011c8b  mov     dword ptr [rsp+88h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180011c93  xor     r9d, r9d; lpSecurityAttributes
0x180011c96  mov     [rsp+88h+RelativeName.RelativeName.Length], ax
0x180011c9b  mov     edx, 80000000h; dwDesiredAccess
0x180011ca0  mov     dword ptr [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180011ca8  movups  xmmword ptr [rsp+88h+RelativeName.ContainingDirectory], xmm0
0x180011cad  lea     r8d, [rdi+5]; dwShareMode
0x180011cb1  call    cs:__imp_CreateFileW
0x180011cb7  mov     rsi, rax
0x180011cba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011cbe  jnz     short loc_180011CC8
0x180011cc0  call    cs:__imp_GetLastError
0x180011cc6  jmp     short loc_180011D39
0x180011cc8  mov     ebx, 8
0x180011ccd  xor     r8d, r8d; cchFilePath
0x180011cd0  mov     r9d, ebx; dwFlags
0x180011cd3  xor     edx, edx; lpszFilePath
0x180011cd5  mov     rcx, rsi; hFile
0x180011cd8  call    cs:__imp_GetFinalPathNameByHandleW
0x180011cde  mov     ebp, eax
0x180011ce0  test    eax, eax
0x180011ce2  jz      short loc_180011CC0
0x180011ce4  lea     edx, [rax+1]
0x180011ce7  add     rdx, rdx; uBytes
0x180011cea  lea     ecx, [rbx+38h]; uFlags
0x180011ced  call    cs:__imp_LocalAlloc
0x180011cf3  mov     rdi, rax
0x180011cf6  test    rax, rax
0x180011cf9  jz      short loc_180011D3B
0x180011cfb  mov     r9d, ebx; dwFlags
0x180011cfe  mov     r8d, ebp; cchFilePath
0x180011d01  mov     rdx, rax; lpszFilePath
0x180011d04  mov     rcx, rsi; hFile
0x180011d07  call    cs:__imp_GetFinalPathNameByHandleW
0x180011d0d  test    eax, eax
0x180011d0f  jz      short loc_180011CC0
0x180011d11  lea     r9, [rsp+88h+RelativeName]
0x180011d16  xor     r8d, r8d
0x180011d19  mov     rdx, r14
0x180011d1c  mov     rcx, rdi
0x180011d1f  xor     ebx, ebx
0x180011d21  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x180011d27  add     word ptr [r14+2], 2
0x180011d2d  test    eax, eax
0x180011d2f  jns     short loc_180011D3B
0x180011d31  mov     ecx, eax; Status
0x180011d33  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180011d39  mov     ebx, eax
0x180011d3b  mov     rcx, rdi; hMem
0x180011d3e  call    cs:__imp_LocalFree
0x180011d44  lea     rcx, [rsp+88h+RelativeName]; RelativeName
0x180011d49  call    cs:__imp_RtlReleaseRelativeName
0x180011d4f  mov     rcx, rsi; hObject
0x180011d52  call    cs:__imp_CloseHandle
0x180011d58  mov     eax, ebx
0x180011d5a  add     rsp, 60h
0x180011d5e  pop     r14
0x180011d60  pop     rdi
0x180011d61  pop     rsi
0x180011d62  pop     rbp
0x180011d63  pop     rbx
0x180011d64  retn
```
