# SaveSdbInfo(RtlArray<_SavedSdbInfo> &,ushort const *)

- ea: `0x180039508`
- end: `0x180039738`
- name: `?SaveSdbInfo@@YAJAEAV?$RtlArray@U_SavedSdbInfo@@@@PEBG@Z`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800384a0`

## callees

- `0x180001cf0`
- `0x18000a654`
- `0x180039508`
- `0x18004fec8`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1800396a0`
- `KERNEL32!WriteFile` at `0x1800396a0`
- `KERNEL32!CreateFileW` at `0x18003957c`
- `KERNEL32!CreateFileW` at `0x18003957c`
- `KERNEL32!CloseHandle` at `0x1800396c6`
- `KERNEL32!CloseHandle` at `0x1800396c6`
- `KERNEL32!GetLastError` at `0x18003958b`
- `KERNEL32!GetLastError` at `0x1800396f5`
- `KERNEL32!GetLastError` at `0x18003958b`
- `KERNEL32!GetLastError` at `0x1800396f5`

## string_xrefs

- `0x1800395a2`: `Failed to create sdb info file: 0x%x`
- `0x18003970c`: `Failed to write to sdb info file: 0x%x`

## pseudocode

```c
__int64 __fastcall SaveSdbInfo(unsigned __int64 *a1, const WCHAR *a2)
{
  int v3; // ebx
  HANDLE FileW; // rsi
  signed int LastError; // eax
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  const wchar_t *v11; // rcx
  __int64 v12; // rax
  int v13; // ebp
  signed int v15; // eax
  ULONG dwCreationDisposition; // [rsp+20h] [rbp-688h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-688h]
  DWORD dwCreationDispositionb[2]; // [rsp+20h] [rbp-688h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-680h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-678h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-668h] BYREF
  WCHAR pszPathOut[264]; // [rsp+50h] [rbp-658h] BYREF
  wchar_t pszDest[520]; // [rsp+260h] [rbp-448h] BYREF

  NumberOfBytesWritten = 0;
  v3 = PathCchCombineEx(pszPathOut, (size_t)a2, a2, L"Metadata.txt", dwCreationDisposition);
  if ( v3 >= 0 )
  {
    FileW = CreateFileW(pszPathOut, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2147467259;
      dwCreationDispositiona[0] = v3;
      AslLogCallPrintf(1, "SaveSdbInfo", 537, "Failed to create sdb info file: 0x%x", *(_QWORD *)dwCreationDispositiona);
    }
    else
    {
      v6 = a1[2];
      if ( v6 )
      {
        v7 = 0;
        while ( 1 )
        {
          v8 = 0;
          if ( v7 < v6 )
          {
            v9 = a1[1] * v7;
            if ( !is_mul_ok(a1[1], v7) || (v10 = a1[5], v8 = v10 + v9, v10 + v9 < v10) )
              v8 = 0;
          }
          if ( *(_QWORD *)v8 && *(_QWORD *)(v8 + 32) )
          {
            v11 = L"True";
            hTemplateFile = *(HANDLE *)(v8 + 32);
            if ( !*(_DWORD *)(v8 + 24) )
              v11 = L"False";
            *(_QWORD *)dwFlagsAndAttributes = v11;
            if ( StringCchPrintfW(pszDest, 0x208u, L"%ls;%ls;%ls;%ls\r\n") >= 0 )
            {
              v12 = -1;
              do
                ++v12;
              while ( pszDest[v12] );
              v13 = 2 * v12;
              if ( !WriteFile(FileW, pszDest, 2 * v12, &NumberOfBytesWritten, 0) || v13 != NumberOfBytesWritten )
                break;
            }
          }
          v6 = a1[2];
          if ( ++v7 >= v6 )
            goto LABEL_24;
        }
        v15 = GetLastError();
        v3 = v15;
        if ( v15 > 0 )
          v3 = (unsigned __int16)v15 | 0x80070000;
        if ( v3 >= 0 )
          v3 = -2147467259;
        dwCreationDispositionb[0] = v3;
        AslLogCallPrintf(
          1,
          "SaveSdbInfo",
          584,
          "Failed to write to sdb info file: 0x%x",
          *(_QWORD *)dwCreationDispositionb,
          *(_QWORD *)dwFlagsAndAttributes,
          hTemplateFile);
      }
      else
      {
LABEL_24:
        v3 = 0;
      }
      CloseHandle(FileW);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180039508  mov     [rsp+arg_10], rbx
0x18003950d  push    rbp
0x18003950e  push    rsi
0x18003950f  push    rdi
0x180039510  push    r12
0x180039512  push    r14
0x180039514  sub     rsp, 680h
0x18003951b  mov     rax, cs:__security_cookie
0x180039522  xor     rax, rsp
0x180039525  mov     [rsp+6A8h+var_38], rax
0x18003952d  mov     rdi, rcx
0x180039530  lea     r9, aMetadataTxt; "Metadata.txt"
0x180039537  xor     r14d, r14d
0x18003953a  lea     rcx, [rsp+6A8h+pszPathOut]; pszPathOut
0x18003953f  mov     r8, rdx; pszPathIn
0x180039542  mov     [rsp+6A8h+NumberOfBytesWritten], r14d
0x180039547  call    PathCchCombineEx
0x18003954c  mov     ebx, eax
0x18003954e  test    eax, eax
0x180039550  js      loc_1800396CC
0x180039556  mov     [rsp+6A8h+hTemplateFile], r14; hTemplateFile
0x18003955b  lea     r8d, [r14+1]; dwShareMode
0x18003955f  mov     [rsp+6A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180039567  lea     rcx, [rsp+6A8h+pszPathOut]; lpFileName
0x18003956c  xor     r9d, r9d; lpSecurityAttributes
0x18003956f  mov     [rsp+6A8h+dwCreationDisposition], 2; dwCreationDisposition
0x180039577  mov     edx, 40000000h; dwDesiredAccess
0x18003957c  call    cs:__imp_CreateFileW
0x180039582  mov     rsi, rax
0x180039585  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039589  jnz     short loc_1800395D1
0x18003958b  call    cs:__imp_GetLastError
0x180039591  mov     ebx, eax
0x180039593  test    eax, eax
0x180039595  jle     short loc_1800395A0
0x180039597  movzx   ebx, ax
0x18003959a  or      ebx, 80070000h
0x1800395a0  test    ebx, ebx
0x1800395a2  lea     r9, aFailedToCreate_8; "Failed to create sdb info file: 0x%x"
0x1800395a9  mov     eax, 80004005h
0x1800395ae  lea     rdx, aSavesdbinfo; "SaveSdbInfo"
0x1800395b5  cmovns  ebx, eax
0x1800395b8  mov     r8d, 219h
0x1800395be  mov     ecx, 1
0x1800395c3  mov     [rsp+6A8h+dwCreationDisposition], ebx
0x1800395c7  call    AslLogCallPrintf
0x1800395cc  jmp     loc_1800396CC
0x1800395d1  mov     rax, [rdi+10h]
0x1800395d5  test    rax, rax
0x1800395d8  jz      loc_1800396C0
0x1800395de  mov     rbx, r14
0x1800395e1  lea     r12, aFalse_0; "False"
0x1800395e8  mov     rdx, r14
0x1800395eb  cmp     rbx, rax
0x1800395ee  jnb     short loc_18003960C
0x1800395f0  mov     rax, rbx
0x1800395f3  mul     qword ptr [rdi+8]
0x1800395f7  test    rdx, rdx
0x1800395fa  jnz     short loc_180039609
0x1800395fc  mov     rcx, [rdi+28h]
0x180039600  lea     rdx, [rcx+rax]
0x180039604  cmp     rdx, rcx
0x180039607  jnb     short loc_18003960C
0x180039609  mov     rdx, r14
0x18003960c  mov     r9, [rdx]
0x18003960f  test    r9, r9
0x180039612  jz      loc_1800396B0
0x180039618  mov     r8, [rdx+20h]
0x18003961c  test    r8, r8
0x18003961f  jz      loc_1800396B0
0x180039625  cmp     [rdx+18h], r14d
0x180039629  lea     rcx, aTrue_0; "True"
0x180039630  mov     [rsp+6A8h+hTemplateFile], r8
0x180039635  lea     rax, aTrue_0; "True"
0x18003963c  cmovz   rcx, r12
0x180039640  lea     r8, aLsLsLsLs; "%ls;%ls;%ls;%ls\r\n"
0x180039647  cmp     [rdx+8], r14d
0x18003964b  mov     edx, 208h; cchDest
0x180039650  mov     qword ptr [rsp+6A8h+dwFlagsAndAttributes], rcx
0x180039655  lea     rcx, [rsp+6A8h+pszDest]; pszDest
0x18003965d  cmovz   rax, r12
0x180039661  mov     qword ptr [rsp+6A8h+dwCreationDisposition], rax
0x180039666  call    StringCchPrintfW
0x18003966b  test    eax, eax
0x18003966d  js      short loc_1800396B0
0x18003966f  lea     rcx, [rsp+6A8h+pszDest]
0x180039677  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003967b  inc     rax
0x18003967e  cmp     [rcx+rax*2], r14w
0x180039683  jnz     short loc_18003967B
0x180039685  lea     ebp, [rax+rax]
0x180039688  mov     qword ptr [rsp+6A8h+dwCreationDisposition], r14; lpOverlapped
0x18003968d  mov     r8d, ebp; nNumberOfBytesToWrite
0x180039690  lea     r9, [rsp+6A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180039695  lea     rdx, [rsp+6A8h+pszDest]; lpBuffer
0x18003969d  mov     rcx, rsi; hFile
0x1800396a0  call    cs:__imp_WriteFile
0x1800396a6  test    eax, eax
0x1800396a8  jz      short loc_1800396F5
0x1800396aa  cmp     ebp, [rsp+6A8h+NumberOfBytesWritten]
0x1800396ae  jnz     short loc_1800396F5
0x1800396b0  mov     rax, [rdi+10h]
0x1800396b4  inc     rbx
0x1800396b7  cmp     rbx, rax
0x1800396ba  jb      loc_1800395E8
0x1800396c0  mov     ebx, r14d
0x1800396c3  mov     rcx, rsi; hObject
0x1800396c6  call    cs:__imp_CloseHandle
0x1800396cc  mov     eax, ebx
0x1800396ce  mov     rcx, [rsp+6A8h+var_38]
0x1800396d6  xor     rcx, rsp; StackCookie
0x1800396d9  call    __security_check_cookie
0x1800396de  mov     rbx, [rsp+6A8h+arg_10]
0x1800396e6  add     rsp, 680h
0x1800396ed  pop     r14
0x1800396ef  pop     r12
0x1800396f1  pop     rdi
0x1800396f2  pop     rsi
0x1800396f3  pop     rbp
0x1800396f4  retn
0x1800396f5  call    cs:__imp_GetLastError
0x1800396fb  mov     ebx, eax
0x1800396fd  test    eax, eax
0x1800396ff  jle     short loc_18003970A
0x180039701  movzx   ebx, ax
0x180039704  or      ebx, 80070000h
0x18003970a  test    ebx, ebx
0x18003970c  lea     r9, aFailedToWriteT; "Failed to write to sdb info file: 0x%x"
0x180039713  mov     eax, 80004005h
0x180039718  lea     rdx, aSavesdbinfo; "SaveSdbInfo"
0x18003971f  cmovns  ebx, eax
0x180039722  mov     r8d, 248h
0x180039728  mov     ecx, 1
0x18003972d  mov     [rsp+6A8h+dwCreationDisposition], ebx
0x180039731  call    AslLogCallPrintf
0x180039736  jmp     short loc_1800396C3
```
