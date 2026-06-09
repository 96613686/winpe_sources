# AipNormalizePath(ushort const *,_UNICODE_STRING *)

- ea: `0x180013494`
- end: `0x1800135fa`
- name: `?AipNormalizePath@@YAKPEBGPEAU_UNICODE_STRING@@@Z`
- size: `358`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180013d80`

## callees

- `0x180013494`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800135b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800135b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013541`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013541`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180013524`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180013569`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180013524`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180013569`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800134f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800134f0`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180013587`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180013587`
- `ntdll!RtlReleaseRelativeName` at `0x1800135c1`
- `ntdll!RtlReleaseRelativeName` at `0x1800135c1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001359f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001359f`

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
0x180013494  mov     r11, rsp
0x180013497  mov     [r11+8], rbx
0x18001349b  mov     [r11+10h], rbp
0x18001349f  mov     [r11+18h], rsi
0x1800134a3  mov     [r11+20h], rdi
0x1800134a7  push    r14
0x1800134a9  sub     rsp, 60h
0x1800134ad  xor     ebx, ebx
0x1800134af  xor     eax, eax
0x1800134b1  mov     [r11-38h], rbx
0x1800134b5  xorps   xmm0, xmm0
0x1800134b8  mov     r14, rdx
0x1800134bb  mov     [rsp+68h+RelativeName.RelativeName.Length], bx
0x1800134c0  movups  xmmword ptr [rsp+68h+RelativeName.RelativeName.MaximumLength], xmm0
0x1800134c5  mov     [r11-16h], rax
0x1800134c9  lea     r8d, [rbx+5]; dwShareMode
0x1800134cd  mov     [rsp+68h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800134d5  xor     r9d, r9d; lpSecurityAttributes
0x1800134d8  mov     edx, 80000000h; dwDesiredAccess
0x1800134dd  mov     dword ptr [rsp+68h+RelativeName.CurDirRef+2], eax
0x1800134e1  mov     edi, ebx
0x1800134e3  mov     word ptr [rsp+68h+RelativeName.CurDirRef+6], ax
0x1800134e8  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800134f0  call    cs:__imp_CreateFileW
0x1800134f7  nop     dword ptr [rax+rax+00h]
0x1800134fc  mov     rsi, rax
0x1800134ff  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013503  jnz     short loc_180013516
0x180013505  call    cs:__imp_GetLastError
0x18001350c  nop     dword ptr [rax+rax+00h]
0x180013511  jmp     loc_1800135AB
0x180013516  mov     r9d, 8; dwFlags
0x18001351c  xor     r8d, r8d; cchFilePath
0x18001351f  xor     edx, edx; lpszFilePath
0x180013521  mov     rcx, rsi; hFile
0x180013524  call    cs:__imp_GetFinalPathNameByHandleW
0x18001352b  nop     dword ptr [rax+rax+00h]
0x180013530  mov     ebp, eax
0x180013532  test    eax, eax
0x180013534  jz      short loc_180013505
0x180013536  lea     edx, [rax+1]
0x180013539  mov     ecx, 40h ; '@'; uFlags
0x18001353e  add     rdx, rdx; uBytes
0x180013541  call    cs:__imp_LocalAlloc
0x180013548  nop     dword ptr [rax+rax+00h]
0x18001354d  mov     rdi, rax
0x180013550  test    rax, rax
0x180013553  jnz     short loc_18001355A
0x180013555  lea     ebx, [rax+8]
0x180013558  jmp     short loc_1800135AD
0x18001355a  mov     r9d, 8; dwFlags
0x180013560  mov     r8d, ebp; cchFilePath
0x180013563  mov     rdx, rdi; lpszFilePath
0x180013566  mov     rcx, rsi; hFile
0x180013569  call    cs:__imp_GetFinalPathNameByHandleW
0x180013570  nop     dword ptr [rax+rax+00h]
0x180013575  test    eax, eax
0x180013577  jz      short loc_180013505
0x180013579  lea     r9, [rsp+68h+RelativeName]
0x18001357e  xor     r8d, r8d
0x180013581  mov     rdx, r14
0x180013584  mov     rcx, rdi
0x180013587  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18001358e  nop     dword ptr [rax+rax+00h]
0x180013593  add     word ptr [r14+2], 2
0x180013599  test    eax, eax
0x18001359b  jns     short loc_1800135AD
0x18001359d  mov     ecx, eax; Status
0x18001359f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800135a6  nop     dword ptr [rax+rax+00h]
0x1800135ab  mov     ebx, eax
0x1800135ad  mov     rcx, rdi; hMem
0x1800135b0  call    cs:__imp_LocalFree
0x1800135b7  nop     dword ptr [rax+rax+00h]
0x1800135bc  lea     rcx, [rsp+68h+RelativeName]; RelativeName
0x1800135c1  call    cs:__imp_RtlReleaseRelativeName
0x1800135c8  nop     dword ptr [rax+rax+00h]
0x1800135cd  mov     rcx, rsi; hObject
0x1800135d0  call    cs:__imp_CloseHandle
0x1800135d7  nop     dword ptr [rax+rax+00h]
0x1800135dc  lea     r11, [rsp+68h+var_8]
0x1800135e1  mov     eax, ebx
0x1800135e3  mov     rbx, [r11+10h]
0x1800135e7  mov     rbp, [r11+18h]
0x1800135eb  mov     rsi, [r11+20h]
0x1800135ef  mov     rdi, [r11+28h]
0x1800135f3  mov     rsp, r11
0x1800135f6  pop     r14
0x1800135f8  retn
```
