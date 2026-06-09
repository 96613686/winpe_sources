# FwppFileWriterCreate

- ea: `0x18008a63c`
- end: `0x18008a74c`
- name: `FwppFileWriterCreate`
- size: `272`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180080834`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180024e40`
- `0x180026d90`
- `0x18008a63c`
- `0x18008a754`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a6bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a6bd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008a6f3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008a6f3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008a6a4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008a6a4`

## string_xrefs

- `0x18008a6cc`: `CreateFileW`
- `0x18008a704`: `FwppFileWriterCreate`

## pseudocode

```c
__int64 __fastcall FwppFileWriterCreate(LPCWSTR lpFileName, _QWORD *a2)
{
  int v4; // esi
  __int64 v5; // rbx
  _DWORD *v6; // rdi
  HANDLE FileW; // rax
  DWORD LastError; // eax
  __int64 v9; // rcx
  _DWORD *v11; // [rsp+70h] [rbp+18h] BYREF

  v11 = 0;
  v4 = 0;
  v5 = WfpMemAlloc(0x10010u, 0);
  if ( !v5 )
  {
    v6 = v11;
    *v11 = 0;
    v4 = 1;
    FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
    *((_QWORD *)v6 + 8193) = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v5 = WfpReportSysErrorAsWinError(v9, "CreateFileW", LastError);
      v4 = 0;
      if ( !v5 )
        return v5;
    }
    else
    {
      v5 = FwppFileWriterWrite(v6, &qword_1800E2410, 3);
      if ( !v5 )
      {
        *a2 = v6;
        return v5;
      }
    }
  }
  FwppFileWriterDestroy(&v11);
  if ( v4 )
    DeleteFileW(lpFileName);
  WfpReportError(v5, "FwppFileWriterCreate");
  return v5;
}

```

## disassembly

```asm
0x18008a63c  mov     rax, rsp
0x18008a63f  mov     [rax+8], rbx
0x18008a643  mov     [rax+10h], rbp
0x18008a647  push    rsi
0x18008a648  push    rdi
0x18008a649  push    r14
0x18008a64b  sub     rsp, 40h
0x18008a64f  mov     r14, rdx
0x18008a652  mov     qword ptr [rax+18h], 0
0x18008a65a  mov     rbp, rcx
0x18008a65d  lea     r8, [rax+18h]
0x18008a661  xor     edx, edx; dwFlags
0x18008a663  mov     ecx, 10010h; dwBytes
0x18008a668  xor     esi, esi
0x18008a66a  call    WfpMemAlloc
0x18008a66f  mov     rbx, rax
0x18008a672  test    rax, rax
0x18008a675  jnz     short loc_18008A6E2
0x18008a677  mov     rdi, [rsp+58h+arg_10]
0x18008a67c  xor     r9d, r9d; lpSecurityAttributes
0x18008a67f  mov     [rsp+58h+hTemplateFile], rsi; hTemplateFile
0x18008a684  mov     edx, 40000000h; dwDesiredAccess
0x18008a689  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008a691  mov     rcx, rbp; lpFileName
0x18008a694  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x18008a69c  mov     [rdi], esi
0x18008a69e  lea     esi, [rax+1]
0x18008a6a1  mov     r8d, esi; dwShareMode
0x18008a6a4  call    cs:__imp_CreateFileW
0x18008a6ab  nop     dword ptr [rax+rax+00h]
0x18008a6b0  mov     [rdi+10008h], rax
0x18008a6b7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008a6bb  jnz     short loc_18008A72A
0x18008a6bd  call    cs:__imp_GetLastError
0x18008a6c4  nop     dword ptr [rax+rax+00h]
0x18008a6c9  mov     r8d, eax
0x18008a6cc  lea     rdx, aCreatefilew; "CreateFileW"
0x18008a6d3  call    WfpReportSysErrorAsWinError
0x18008a6d8  mov     rbx, rax
0x18008a6db  xor     esi, esi
0x18008a6dd  test    rax, rax
0x18008a6e0  jz      short loc_18008A713
0x18008a6e2  lea     rcx, [rsp+58h+arg_10]
0x18008a6e7  call    FwppFileWriterDestroy
0x18008a6ec  test    esi, esi
0x18008a6ee  jz      short loc_18008A6FF
0x18008a6f0  mov     rcx, rbp; lpFileName
0x18008a6f3  call    cs:__imp_DeleteFileW
0x18008a6fa  nop     dword ptr [rax+rax+00h]
0x18008a6ff  test    rbx, rbx
0x18008a702  jz      short loc_18008A713
0x18008a704  lea     rdx, aFwppfilewriter_1; "FwppFileWriterCreate"
0x18008a70b  mov     rcx, rbx
0x18008a70e  call    WfpReportError
0x18008a713  mov     rbp, [rsp+58h+arg_8]
0x18008a718  mov     rax, rbx
0x18008a71b  mov     rbx, [rsp+58h+arg_0]
0x18008a720  add     rsp, 40h
0x18008a724  pop     r14
0x18008a726  pop     rdi
0x18008a727  pop     rsi
0x18008a728  retn
0x18008a72a  mov     r8d, 3
0x18008a730  lea     rdx, qword_1800E2410
0x18008a737  mov     rcx, rdi
0x18008a73a  call    FwppFileWriterWrite
0x18008a73f  mov     rbx, rax
0x18008a742  test    rax, rax
0x18008a745  jnz     short loc_18008A6E2
0x18008a747  mov     [r14], rdi
0x18008a74a  jmp     short loc_18008A713
```
