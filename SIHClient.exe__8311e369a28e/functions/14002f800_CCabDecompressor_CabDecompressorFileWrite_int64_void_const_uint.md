# CCabDecompressor::CabDecompressorFileWrite(__int64,void const *,uint)

- ea: `0x14002f800`
- end: `0x14002f93e`
- name: `?CabDecompressorFileWrite@CCabDecompressor@@CAI_JPEBXI@Z`
- size: `318`
- prototype: `__int64 __fastcall(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000feec`
- `0x1400154b4`
- `0x14002f800`
- `0x140045dc0`
- `0x14004d140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f858`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002f84e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002f84e`

## string_xrefs

- `0x14002f8a0`: `CabDecompressorFileWrite - invalid buffer`
- `0x14002f876`: `CabDecompressorFileWrite - WriteFile`
- `0x14002f8f6`: `Write decompressed file to buffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CCabDecompressor::CabDecompressorFileWrite(INT_PTR hf, void *pv, UINT cb)
{
  unsigned int v3; // ebx
  size_t v4; // rbp
  void *v7; // rcx
  signed int LastError; // eax
  signed int v9; // ecx
  __int64 v10; // r9
  __int64 v11; // rdi
  UINT v12; // eax
  UINT v13; // r14d
  int v14; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-48h]
  const wchar_t *v17; // [rsp+28h] [rbp-40h]
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-38h] BYREF

  v3 = -1;
  v4 = cb;
  if ( *(_DWORD *)(hf + 16) != 1 )
  {
    v11 = *(_QWORD *)(hf + 8);
    if ( !v11 )
    {
      v17 = L"CabDecompressorFileWrite - invalid buffer";
      lpOverlapped = 0;
LABEL_8:
      v10 = 3;
LABEL_18:
      WUTrace(0, 0, 32, v10, lpOverlapped, v17);
      return v3;
    }
    v12 = *(_DWORD *)(v11 + 20);
    v13 = v12 + cb;
    if ( v12 + cb < v12 )
    {
      v14 = -2147024362;
    }
    else if ( *(_DWORD *)(v11 + 16) >= v13
           || (v14 = CSafeBuffer<unsigned char>::resize(*(_QWORD *)(hf + 8), v13), v14 >= 0) )
    {
      memmove((void *)(*(_QWORD *)(v11 + 8) + *(unsigned int *)(v11 + 20)), pv, v4);
      *(_DWORD *)(v11 + 20) = v13;
      v3 = v4;
      *(_DWORD *)(hf + 20) += v4;
      return v3;
    }
    v10 = 5;
    v17 = L"Write decompressed file to buffer";
    LODWORD(lpOverlapped) = v14;
    goto LABEL_18;
  }
  v7 = *(void **)(hf + 8);
  NumberOfBytesWritten = 0;
  if ( !WriteFile(v7, pv, cb, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    v9 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v9 = LastError;
    if ( v9 >= 0 )
      v9 = -2147418113;
    v17 = L"CabDecompressorFileWrite - WriteFile";
    LODWORD(lpOverlapped) = v9;
    goto LABEL_8;
  }
  return NumberOfBytesWritten;
}

```

## disassembly

```asm
0x14002f800  mov     [rsp+arg_18], rbx
0x14002f805  push    rbp
0x14002f806  push    rsi
0x14002f807  push    rdi
0x14002f808  push    r14
0x14002f80a  push    r15
0x14002f80c  sub     rsp, 40h
0x14002f810  mov     rax, cs:__security_cookie
0x14002f817  xor     rax, rsp
0x14002f81a  mov     [rsp+68h+var_30], rax
0x14002f81f  or      ebx, 0FFFFFFFFh
0x14002f822  mov     ebp, r8d
0x14002f825  cmp     dword ptr [rcx+10h], 1
0x14002f829  mov     r15, rdx
0x14002f82c  mov     rsi, rcx
0x14002f82f  jnz     short loc_14002F897
0x14002f831  mov     rcx, [rcx+8]; hFile
0x14002f835  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002f83a  mov     r8d, ebp; nNumberOfBytesToWrite
0x14002f83d  mov     [rsp+68h+NumberOfBytesWritten], 0
0x14002f845  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x14002f84e  call    cs:__imp_WriteFile
0x14002f854  test    eax, eax
0x14002f856  jnz     short loc_14002F88E
0x14002f858  call    cs:__imp_GetLastError
0x14002f85e  movzx   ecx, ax
0x14002f861  or      ecx, 80070000h
0x14002f867  test    eax, eax
0x14002f869  cmovle  ecx, eax
0x14002f86c  mov     eax, 8000FFFFh
0x14002f871  test    ecx, ecx
0x14002f873  cmovns  ecx, eax
0x14002f876  lea     rax, aCabdecompresso_3; "CabDecompressorFileWrite - WriteFile"
0x14002f87d  mov     [rsp+68h+var_40], rax
0x14002f882  mov     dword ptr [rsp+68h+lpOverlapped], ecx
0x14002f886  mov     r9d, 3
0x14002f88c  jmp     short loc_14002F90C
0x14002f88e  mov     ebx, [rsp+68h+NumberOfBytesWritten]
0x14002f892  jmp     loc_14002F91B
0x14002f897  mov     rdi, [rcx+8]
0x14002f89b  test    rdi, rdi
0x14002f89e  jnz     short loc_14002F8B3
0x14002f8a0  lea     rax, aCabdecompresso_1; "CabDecompressorFileWrite - invalid buff"...
0x14002f8a7  mov     [rsp+68h+var_40], rax
0x14002f8ac  mov     [rsp+68h+lpOverlapped], rdi
0x14002f8b1  jmp     short loc_14002F886
0x14002f8b3  mov     eax, [rdi+14h]
0x14002f8b6  lea     r14d, [rax+rbp]
0x14002f8ba  cmp     r14d, eax
0x14002f8bd  jb      short loc_14002F8F1
0x14002f8bf  cmp     [rdi+10h], r14d
0x14002f8c3  jnb     short loc_14002F8D4
0x14002f8c5  mov     edx, r14d
0x14002f8c8  mov     rcx, rdi
0x14002f8cb  call    ?resize@?$CSafeBuffer@E@@QEAAJI@Z; CSafeBuffer<uchar>::resize(uint)
0x14002f8d0  test    eax, eax
0x14002f8d2  js      short loc_14002F8F6
0x14002f8d4  mov     ecx, [rdi+14h]
0x14002f8d7  mov     r8, rbp; Size
0x14002f8da  add     rcx, [rdi+8]; void *
0x14002f8de  mov     rdx, r15; Src
0x14002f8e1  call    memmove
0x14002f8e6  mov     [rdi+14h], r14d
0x14002f8ea  mov     ebx, ebp
0x14002f8ec  add     [rsi+14h], ebp
0x14002f8ef  jmp     short loc_14002F91B
0x14002f8f1  mov     eax, 80070216h
0x14002f8f6  lea     rcx, aWriteDecompres; "Write decompressed file to buffer"
0x14002f8fd  mov     r9d, 5
0x14002f903  mov     [rsp+68h+var_40], rcx
0x14002f908  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x14002f90c  mov     r8d, 20h ; ' '
0x14002f912  xor     edx, edx
0x14002f914  xor     ecx, ecx
0x14002f916  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002f91b  mov     eax, ebx
0x14002f91d  mov     rcx, [rsp+68h+var_30]
0x14002f922  xor     rcx, rsp; StackCookie
0x14002f925  call    __security_check_cookie
0x14002f92a  mov     rbx, [rsp+68h+arg_18]
0x14002f932  add     rsp, 40h
0x14002f936  pop     r15
0x14002f938  pop     r14
0x14002f93a  pop     rdi
0x14002f93b  pop     rsi
0x14002f93c  pop     rbp
0x14002f93d  retn
```
