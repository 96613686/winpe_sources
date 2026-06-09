# EncryptDumpFile(void *,void *)

- ea: `0x180002340`
- end: `0x18000242d`
- name: `?EncryptDumpFile@@YAJPEAX0@Z`
- size: `237`
- prototype: `signed int __fastcall(HANDLE hFile, HANDLE)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002340`
- `0x180002440`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800023be`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800023eb`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800023be`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800023eb`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180002391`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180002391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000239b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000239b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023f5`

## pseudocode

```c
signed int __fastcall EncryptDumpFile(HANDLE hFile, HANDLE a2)
{
  signed int result; // eax
  bool v5; // sf
  bool v6; // sf
  bool v7; // sf
  struct IUnknown v8; // [rsp+20h] [rbp-30h] BYREF
  HANDLE v9; // [rsp+28h] [rbp-28h]
  int v10; // [rsp+30h] [rbp-20h]
  IUnknown v11; // [rsp+38h] [rbp-18h] BYREF
  HANDLE v12; // [rsp+40h] [rbp-10h]
  int v13; // [rsp+48h] [rbp-8h]
  LARGE_INTEGER FileSize; // [rsp+68h] [rbp+18h] BYREF

  v11.lpVtbl = (struct IUnknownVtbl *)&CFileStream::`vftable';
  v12 = hFile;
  v13 = 1;
  v8.lpVtbl = (struct IUnknownVtbl *)&CFileStream::`vftable';
  v9 = a2;
  v10 = 1;
  FileSize.QuadPart = 0;
  if ( GetFileSizeEx(hFile, &FileSize) )
    goto LABEL_8;
  result = GetLastError();
  v5 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v5 = result < 0;
  }
  if ( !v5 )
  {
LABEL_8:
    if ( SetFilePointerEx(hFile, 0, 0, 0) )
      goto LABEL_12;
    result = GetLastError();
    v6 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v6 = result < 0;
    }
    if ( !v6 )
    {
LABEL_12:
      if ( SetFilePointerEx(a2, 0, 0, 0) )
        return EncryptDumpStream(&v11, &v8, FileSize.QuadPart);
      result = GetLastError();
      v7 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v7 = result < 0;
      }
      if ( !v7 )
        return EncryptDumpStream(&v11, &v8, FileSize.QuadPart);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002340  mov     [rsp-8+arg_10], rbx
0x180002345  mov     [rsp-8+arg_18], rdi
0x18000234a  push    rbp
0x18000234b  mov     rbp, rsp
0x18000234e  sub     rsp, 50h
0x180002352  mov     rdi, rdx
0x180002355  mov     rbx, rcx
0x180002358  lea     rcx, ??_7CFileStream@@6B@; const CFileStream::`vftable'
0x18000235f  mov     [rbp+var_18.lpVtbl], rcx
0x180002363  mov     [rbp+var_10], rbx
0x180002367  mov     eax, 1
0x18000236c  mov     [rbp+var_8], eax
0x18000236f  mov     [rbp+var_30.lpVtbl], rcx
0x180002373  mov     [rbp+var_28], rdx
0x180002377  mov     [rbp+var_20], eax
0x18000237a  mov     qword ptr [rbp+FileSize], 0
0x180002382  mov     qword ptr [rbp+liDistanceToMove], 0
0x18000238a  lea     rdx, [rbp+FileSize]; lpFileSize
0x18000238e  mov     rcx, rbx; hFile
0x180002391  call    cs:__imp_GetFileSizeEx
0x180002397  test    eax, eax
0x180002399  jnz     short loc_1800023B1
0x18000239b  call    cs:__imp_GetLastError
0x1800023a1  test    eax, eax
0x1800023a3  jle     short loc_1800023AF
0x1800023a5  movzx   eax, ax
0x1800023a8  or      eax, 80070000h
0x1800023ad  test    eax, eax
0x1800023af  js      short loc_18000241D
0x1800023b1  xor     r9d, r9d; dwMoveMethod
0x1800023b4  xor     r8d, r8d; lpNewFilePointer
0x1800023b7  mov     rdx, qword ptr [rbp+liDistanceToMove]; liDistanceToMove
0x1800023bb  mov     rcx, rbx; hFile
0x1800023be  call    cs:__imp_SetFilePointerEx
0x1800023c4  test    eax, eax
0x1800023c6  jnz     short loc_1800023DE
0x1800023c8  call    cs:__imp_GetLastError
0x1800023ce  test    eax, eax
0x1800023d0  jle     short loc_1800023DC
0x1800023d2  movzx   eax, ax
0x1800023d5  or      eax, 80070000h
0x1800023da  test    eax, eax
0x1800023dc  js      short loc_18000241D
0x1800023de  xor     r9d, r9d; dwMoveMethod
0x1800023e1  xor     r8d, r8d; lpNewFilePointer
0x1800023e4  mov     rdx, qword ptr [rbp+liDistanceToMove]; liDistanceToMove
0x1800023e8  mov     rcx, rdi; hFile
0x1800023eb  call    cs:__imp_SetFilePointerEx
0x1800023f1  test    eax, eax
0x1800023f3  jnz     short loc_18000240B
0x1800023f5  call    cs:__imp_GetLastError
0x1800023fb  test    eax, eax
0x1800023fd  jle     short loc_180002409
0x1800023ff  movzx   eax, ax
0x180002402  or      eax, 80070000h
0x180002407  test    eax, eax
0x180002409  js      short loc_18000241D
0x18000240b  mov     r8, qword ptr [rbp+FileSize]; unsigned __int64
0x18000240f  lea     rdx, [rbp+var_30]; struct IUnknown *
0x180002413  lea     rcx, [rbp+var_18]; struct IUnknown *
0x180002417  call    ?EncryptDumpStream@@YAJPEAUIUnknown@@0_K@Z; EncryptDumpStream(IUnknown *,IUnknown *,unsigned __int64)
0x18000241c  nop
0x18000241d  mov     rbx, [rsp+50h+arg_10]
0x180002422  mov     rdi, [rsp+50h+arg_18]
0x180002427  add     rsp, 50h
0x18000242b  pop     rbp
0x18000242c  retn
```
