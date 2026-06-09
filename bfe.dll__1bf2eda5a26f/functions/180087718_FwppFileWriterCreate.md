# FwppFileWriterCreate

- ea: `0x180087718`
- end: `0x180087815`
- name: `FwppFileWriterCreate`
- size: `253`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18007d9ec`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180022730`
- `0x180024370`
- `0x180087718`
- `0x18008781c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087793`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800877c3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800877c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180087780`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180087780`

## string_xrefs

- `0x18008779c`: `CreateFileW`
- `0x1800877ce`: `FwppFileWriterCreate`

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
      v5 = FwppFileWriterWrite(v6, &qword_1800DF430, 3);
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
0x180087718  mov     rax, rsp
0x18008771b  mov     [rax+8], rbx
0x18008771f  mov     [rax+10h], rbp
0x180087723  push    rsi
0x180087724  push    rdi
0x180087725  push    r14
0x180087727  sub     rsp, 40h
0x18008772b  mov     r14, rdx
0x18008772e  mov     qword ptr [rax+18h], 0
0x180087736  mov     rbp, rcx
0x180087739  lea     r8, [rax+18h]
0x18008773d  xor     edx, edx; dwFlags
0x18008773f  mov     ecx, 10010h; dwBytes
0x180087744  xor     esi, esi
0x180087746  call    WfpMemAlloc
0x18008774b  mov     rbx, rax
0x18008774e  test    rax, rax
0x180087751  jnz     short loc_1800877B2
0x180087753  mov     rdi, [rsp+58h+arg_10]
0x180087758  xor     r9d, r9d; lpSecurityAttributes
0x18008775b  mov     [rsp+58h+hTemplateFile], rsi; hTemplateFile
0x180087760  mov     edx, 40000000h; dwDesiredAccess
0x180087765  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008776d  mov     rcx, rbp; lpFileName
0x180087770  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x180087778  mov     [rdi], esi
0x18008777a  lea     esi, [rax+1]
0x18008777d  mov     r8d, esi; dwShareMode
0x180087780  call    cs:__imp_CreateFileW
0x180087786  mov     [rdi+10008h], rax
0x18008778d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180087791  jnz     short loc_1800877F3
0x180087793  call    cs:__imp_GetLastError
0x180087799  mov     r8d, eax
0x18008779c  lea     rdx, aCreatefilew; "CreateFileW"
0x1800877a3  call    WfpReportSysErrorAsWinError
0x1800877a8  mov     rbx, rax
0x1800877ab  xor     esi, esi
0x1800877ad  test    rax, rax
0x1800877b0  jz      short loc_1800877DD
0x1800877b2  lea     rcx, [rsp+58h+arg_10]
0x1800877b7  call    FwppFileWriterDestroy
0x1800877bc  test    esi, esi
0x1800877be  jz      short loc_1800877C9
0x1800877c0  mov     rcx, rbp; lpFileName
0x1800877c3  call    cs:__imp_DeleteFileW
0x1800877c9  test    rbx, rbx
0x1800877cc  jz      short loc_1800877DD
0x1800877ce  lea     rdx, aFwppfilewriter_1; "FwppFileWriterCreate"
0x1800877d5  mov     rcx, rbx
0x1800877d8  call    WfpReportError
0x1800877dd  mov     rbp, [rsp+58h+arg_8]
0x1800877e2  mov     rax, rbx
0x1800877e5  mov     rbx, [rsp+58h+arg_0]
0x1800877ea  add     rsp, 40h
0x1800877ee  pop     r14
0x1800877f0  pop     rdi
0x1800877f1  pop     rsi
0x1800877f2  retn
0x1800877f3  mov     r8d, 3
0x1800877f9  lea     rdx, qword_1800DF430
0x180087800  mov     rcx, rdi
0x180087803  call    FwppFileWriterWrite
0x180087808  mov     rbx, rax
0x18008780b  test    rax, rax
0x18008780e  jnz     short loc_1800877B2
0x180087810  mov     [r14], rdi
0x180087813  jmp     short loc_1800877DD
```
