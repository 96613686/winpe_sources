# StructuredQuery1::LoadExistingSchemaBinary

- ea: `0x18003531c`
- end: `0x180035418`
- name: `StructuredQuery1::LoadExistingSchemaBinary`
- size: `252`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180034f50`

## callees

- `0x18003531c`
- `0x180035420`
- `0x180059920`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003539e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003539e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800353b3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800353b3`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180035395`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180035395`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003536a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003536a`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::LoadExistingSchemaBinary(
        StructuredQuery1 *lpFileName,
        __int64 a2,
        const FILETIME *a3)
{
  bool IsCurrentProcessAppContainer; // si
  unsigned int v7; // ebx
  HANDLE FileW; // rax
  void *v9; // rdi
  int Error; // eax
  _QWORD v12[11]; // [rsp+40h] [rbp-58h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+B8h] [rbp+20h] BYREF

  IsCurrentProcessAppContainer = StructuredQuery1::IsCurrentProcessAppContainer(lpFileName);
  v7 = 1;
  if ( IsCurrentProcessAppContainer )
    goto LABEL_5;
  FileW = CreateFileW((LPCWSTR)lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v9 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    LastWriteTime = 0;
    GetFileTime(FileW, 0, 0, &LastWriteTime);
    if ( !CloseHandle(v9) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        return (unsigned int)Error;
    }
    if ( CompareFileTime(a3, &LastWriteTime) < 0 )
    {
LABEL_5:
      v12[2] = 0;
      v12[0] = 31;
      v12[1] = lpFileName;
      Error = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)a2 + 32LL))(a2, 0, v12);
      if ( Error >= 0 || !IsCurrentProcessAppContainer )
        return (unsigned int)Error;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18003531c  push    rbx
0x18003531e  push    rbp
0x18003531f  push    rsi
0x180035320  push    rdi
0x180035321  push    r14
0x180035323  push    r15
0x180035325  sub     rsp, 68h
0x180035329  mov     r14, r8
0x18003532c  mov     r15, rdx
0x18003532f  mov     rbp, rcx
0x180035332  call    ?IsCurrentProcessAppContainer@StructuredQuery1@@YA_NXZ; StructuredQuery1::IsCurrentProcessAppContainer(void)
0x180035337  mov     sil, al
0x18003533a  mov     ebx, 1
0x18003533f  test    al, al
0x180035341  jnz     short loc_1800353BD
0x180035343  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x18003534c  xor     r9d, r9d; lpSecurityAttributes
0x18003534f  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180035357  mov     r8d, ebx; dwShareMode
0x18003535a  mov     edx, 80000000h; dwDesiredAccess
0x18003535f  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x180035367  mov     rcx, rbp; lpFileName
0x18003536a  call    cs:__imp_CreateFileW
0x180035370  mov     rdi, rax
0x180035373  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180035377  jz      short loc_1800353F7
0x180035379  lea     r9, [rsp+98h+LastWriteTime]; lpLastWriteTime
0x180035381  mov     qword ptr [rsp+98h+LastWriteTime.dwLowDateTime], 0
0x18003538d  xor     r8d, r8d; lpLastAccessTime
0x180035390  xor     edx, edx; lpCreationTime
0x180035392  mov     rcx, rax; hFile
0x180035395  call    cs:__imp_GetFileTime
0x18003539b  mov     rcx, rdi; hObject
0x18003539e  call    cs:__imp_CloseHandle
0x1800353a4  test    eax, eax
0x1800353a6  jz      short loc_180035406
0x1800353a8  lea     rdx, [rsp+98h+LastWriteTime]; lpFileTime2
0x1800353b0  mov     rcx, r14; lpFileTime1
0x1800353b3  call    cs:__imp_CompareFileTime
0x1800353b9  test    eax, eax
0x1800353bb  jns     short loc_1800353F7
0x1800353bd  xor     eax, eax
0x1800353bf  lea     r8, [rsp+98h+var_58]
0x1800353c4  mov     [rsp+98h+var_48], rax
0x1800353c9  xorps   xmm0, xmm0
0x1800353cc  movups  [rsp+98h+var_58], xmm0
0x1800353d1  mov     eax, 1Fh
0x1800353d6  mov     qword ptr [rsp+98h+var_58+8], rbp
0x1800353db  mov     word ptr [rsp+98h+var_58], ax
0x1800353e0  xor     edx, edx
0x1800353e2  mov     rax, [r15]
0x1800353e5  mov     rcx, r15
0x1800353e8  mov     rax, [rax+20h]
0x1800353ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800353f1  test    eax, eax
0x1800353f3  js      short loc_180035411
0x1800353f5  mov     ebx, eax
0x1800353f7  mov     eax, ebx
0x1800353f9  add     rsp, 68h
0x1800353fd  pop     r15
0x1800353ff  pop     r14
0x180035401  pop     rdi
0x180035402  pop     rsi
0x180035403  pop     rbp
0x180035404  pop     rbx
0x180035405  retn
0x180035406  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003540b  test    eax, eax
0x18003540d  js      short loc_1800353F5
0x18003540f  jmp     short loc_1800353A8
0x180035411  test    sil, sil
0x180035414  jnz     short loc_1800353F7
0x180035416  jmp     short loc_1800353F5
```
