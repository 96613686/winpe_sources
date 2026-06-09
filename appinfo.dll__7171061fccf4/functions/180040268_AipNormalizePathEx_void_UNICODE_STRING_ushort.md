# AipNormalizePathEx(void *,_UNICODE_STRING *,ushort * *)

- ea: `0x180040268`
- end: `0x180040346`
- name: `?AipNormalizePathEx@@YAKPEAXPEAU_UNICODE_STRING@@PEAPEAG@Z`
- size: `222`
- prototype: `__int64 __fastcall(HANDLE hFile, struct _UNICODE_STRING *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x18003f7ac`

## callees

- `0x180040268`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040326`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040326`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800402c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800402c0`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18004029d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800402da`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18004029d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800402da`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800402f2`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800402f2`
- `ntdll!RtlReleaseRelativeName` at `0x180040331`
- `ntdll!RtlReleaseRelativeName` at `0x180040331`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800402fe`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800402fe`

## pseudocode

```c
__int64 __fastcall AipNormalizePathEx(HANDLE hFile, struct _UNICODE_STRING *a2, unsigned __int16 **a3)
{
  unsigned int v5; // edi
  DWORD FinalPathNameByHandleW; // eax
  DWORD v8; // ebp
  unsigned __int16 *v9; // rbx
  DWORD LastError; // eax
  WCHAR *v11; // rax
  NTSTATUS v12; // eax
  USHORT MaximumLength; // ax
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+20h] [rbp-58h] BYREF

  memset(&RelativeName, 0, sizeof(RelativeName));
  v5 = 8;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 8u);
  v8 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
  {
    v9 = 0;
LABEL_3:
    LastError = GetLastError();
LABEL_4:
    v5 = LastError;
    goto LABEL_12;
  }
  v11 = (WCHAR *)LocalAlloc(0x40u, 2LL * (FinalPathNameByHandleW + 1));
  v9 = v11;
  if ( !v11 )
    goto LABEL_12;
  if ( !GetFinalPathNameByHandleW(hFile, v11, v8, 8u) )
    goto LABEL_3;
  v12 = ((__int64 (__fastcall *)(unsigned __int16 *, struct _UNICODE_STRING *, _QWORD, struct _RTL_RELATIVE_NAME_U *))RtlDosPathNameToRelativeNtPathName_U_WithStatus)(
          v9,
          a2,
          0,
          &RelativeName);
  if ( v12 < 0 )
  {
    LastError = RtlNtStatusToDosErrorNoTeb(v12);
    goto LABEL_4;
  }
  MaximumLength = a2->MaximumLength;
  v5 = 0;
  if ( MaximumLength <= 0xFFFDu )
    a2->MaximumLength = MaximumLength + 2;
  *a3 = v9;
  v9 = 0;
LABEL_12:
  LocalFree(v9);
  RtlReleaseRelativeName(&RelativeName);
  return v5;
}

```

## disassembly

```asm
0x180040268  push    rbx
0x18004026a  push    rbp
0x18004026b  push    rsi
0x18004026c  push    rdi
0x18004026d  push    r14
0x18004026f  push    r15
0x180040271  sub     rsp, 48h
0x180040275  xor     eax, eax
0x180040277  xorps   xmm0, xmm0
0x18004027a  mov     r15, r8
0x18004027d  mov     [rsp+78h+RelativeName.RelativeName.Length], ax
0x180040282  mov     rsi, rdx
0x180040285  xor     r8d, r8d; cchFilePath
0x180040288  movups  xmmword ptr [rsp+78h+RelativeName.RelativeName.MaximumLength], xmm0
0x18004028d  lea     edi, [rax+8]
0x180040290  xor     edx, edx; lpszFilePath
0x180040292  mov     r9d, edi; dwFlags
0x180040295  mov     r14, rcx
0x180040298  movups  xmmword ptr [rsp+78h+RelativeName.ContainingDirectory], xmm0
0x18004029d  call    cs:__imp_GetFinalPathNameByHandleW
0x1800402a3  mov     ebp, eax
0x1800402a5  test    eax, eax
0x1800402a7  jnz     short loc_1800402B5
0x1800402a9  xor     ebx, ebx
0x1800402ab  call    cs:__imp_GetLastError
0x1800402b1  mov     edi, eax
0x1800402b3  jmp     short loc_180040323
0x1800402b5  lea     edx, [rax+1]
0x1800402b8  mov     ecx, 40h ; '@'; uFlags
0x1800402bd  add     rdx, rdx; uBytes
0x1800402c0  call    cs:__imp_LocalAlloc
0x1800402c6  mov     rbx, rax
0x1800402c9  test    rax, rax
0x1800402cc  jz      short loc_180040323
0x1800402ce  mov     r9d, edi; dwFlags
0x1800402d1  mov     r8d, ebp; cchFilePath
0x1800402d4  mov     rdx, rax; lpszFilePath
0x1800402d7  mov     rcx, r14; hFile
0x1800402da  call    cs:__imp_GetFinalPathNameByHandleW
0x1800402e0  test    eax, eax
0x1800402e2  jz      short loc_1800402AB
0x1800402e4  lea     r9, [rsp+78h+RelativeName]
0x1800402e9  xor     r8d, r8d
0x1800402ec  mov     rdx, rsi
0x1800402ef  mov     rcx, rbx
0x1800402f2  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1800402f8  test    eax, eax
0x1800402fa  jns     short loc_180040306
0x1800402fc  mov     ecx, eax; Status
0x1800402fe  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180040304  jmp     short loc_1800402B1
0x180040306  movzx   eax, word ptr [rsi+2]
0x18004030a  xor     edi, edi
0x18004030c  mov     ecx, 0FFFDh
0x180040311  cmp     ax, cx
0x180040314  ja      short loc_18004031E
0x180040316  add     ax, 2
0x18004031a  mov     [rsi+2], ax
0x18004031e  mov     [r15], rbx
0x180040321  xor     ebx, ebx
0x180040323  mov     rcx, rbx; hMem
0x180040326  call    cs:__imp_LocalFree
0x18004032c  lea     rcx, [rsp+78h+RelativeName]; RelativeName
0x180040331  call    cs:__imp_RtlReleaseRelativeName
0x180040337  mov     eax, edi
0x180040339  add     rsp, 48h
0x18004033d  pop     r15
0x18004033f  pop     r14
0x180040341  pop     rdi
0x180040342  pop     rsi
0x180040343  pop     rbp
0x180040344  pop     rbx
0x180040345  retn
```
