# av_file_map

- ea: `0x18003a0e0`
- end: `0x18003a2a6`
- name: `av_file_map`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180037180`
- `0x18003a0e0`
- `0x18003a2cc`
- `0x180042ad0`
- `0x180078be6`
- `0x180078d5a`
- `0x180078d60`
- `0x180078e90`
- `0x18007a806`
- `0x18007b020`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a28b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a28b`
- `api-ms-win-core-memory-l1-1-1!CreateFileMappingFromApp` at `0x18003a23c`
- `api-ms-win-core-memory-l1-1-1!CreateFileMappingFromApp` at `0x18003a23c`
- `api-ms-win-core-memory-l1-1-1!MapViewOfFileFromApp` at `0x18003a27f`
- `api-ms-win-core-memory-l1-1-1!MapViewOfFileFromApp` at `0x18003a27f`

## string_xrefs

- `0x18003a173`: `Cannot read file '%s': %s\n`
- `0x18003a24d`: `Error occurred in CreateFileMapping()\n`

## pseudocode

```c
__int64 __fastcall av_file_map(const char *a1, __int64 *a2, _QWORD *a3, int a4, __int64 a5)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // edi
  __int64 st_size; // rax
  __int64 v12; // r14
  __int64 result; // rax
  intptr_t osfhandle; // rax
  __int64 FileMappingFromApp; // rax
  void *v16; // r15
  char **v17; // [rsp+30h] [rbp-81h] BYREF
  int v18; // [rsp+38h] [rbp-79h]
  __int64 v19; // [rsp+40h] [rbp-71h]
  _stat64i32 Stat; // [rsp+48h] [rbp-69h] BYREF
  char v21[64]; // [rsp+80h] [rbp-31h] BYREF

  v18 = a4;
  v17 = &off_180085A50;
  v19 = a5;
  v8 = sub_18003A2CC(a1, 0);
  v9 = 0;
  v10 = v8;
  *a2 = 0;
  *a3 = 0;
  _mm_lfence();
  if ( v8 < 0 )
  {
    v9 = -*errno();
    sub_18007B020(v21, 0, 64);
    av_strerror(v9, v21, 64);
    av_log(&v17, 16, "Cannot read file '%s': %s\n", a1, v21);
    return v9;
  }
  if ( fstat64i32(v8, &Stat) < 0 )
  {
    _mm_lfence();
    v9 = -*errno();
    sub_18007B020(v21, 0, 64);
    av_strerror(v9, v21, 64);
    av_log(&v17, 16, "Error occurred in fstat(): %s\n", v21);
LABEL_8:
    close(v10);
    return v9;
  }
  st_size = Stat.st_size;
  *a3 = Stat.st_size;
  if ( !st_size )
  {
    v12 = 0;
LABEL_7:
    _mm_lfence();
    *a2 = v12;
    goto LABEL_8;
  }
  _mm_lfence();
  osfhandle = get_osfhandle(v10);
  FileMappingFromApp = CreateFileMappingFromApp(osfhandle, 0, 2);
  v16 = (void *)FileMappingFromApp;
  _mm_lfence();
  if ( FileMappingFromApp )
  {
    v12 = MapViewOfFileFromApp(FileMappingFromApp, 1, 0, *a3);
    CloseHandle(v16);
    if ( v12 )
      goto LABEL_7;
    _mm_lfence();
    av_log(&v17, 16, "Error occurred in MapViewOfFile()\n");
  }
  else
  {
    av_log(&v17, 16, "Error occurred in CreateFileMapping()\n");
  }
  close(v10);
  result = 0xFFFFFFFFLL;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x18003a0e0  push    rbp
0x18003a0e2  push    rbx
0x18003a0e3  push    rsi
0x18003a0e4  push    rdi
0x18003a0e5  push    r12
0x18003a0e7  push    r14
0x18003a0e9  push    r15
0x18003a0eb  lea     rbp, [rsp-1Fh]
0x18003a0f0  sub     rsp, 0D0h
0x18003a0f7  mov     rax, cs:__security_cookie
0x18003a0fe  xor     rax, rsp
0x18003a101  mov     [rbp+4Fh+var_40], rax
0x18003a105  mov     rax, [rbp+4Fh+arg_20]
0x18003a109  mov     r14, rcx
0x18003a10c  lea     rcx, off_180085A50; "FILE"
0x18003a113  mov     [rbp+4Fh+var_C8], r9d
0x18003a117  mov     [rsp+100h+var_D0], rcx
0x18003a11c  mov     r12, rdx
0x18003a11f  mov     rcx, r14
0x18003a122  mov     [rbp+4Fh+var_C0], rax
0x18003a126  xor     edx, edx
0x18003a128  mov     rsi, r8
0x18003a12b  call    sub_18003A2CC
0x18003a130  xor     ebx, ebx
0x18003a132  mov     edi, eax
0x18003a134  mov     [r12], rbx
0x18003a138  mov     [rsi], rbx
0x18003a13b  lfence
0x18003a13e  test    eax, eax
0x18003a140  jns     short loc_18003A18E
0x18003a142  call    _errno
0x18003a147  mov     esi, 40h ; '@'
0x18003a14c  lea     rcx, [rbp+4Fh+var_80]
0x18003a150  mov     r8d, esi
0x18003a153  xor     edx, edx
0x18003a155  mov     ebx, [rax]
0x18003a157  neg     ebx
0x18003a159  call    sub_18007B020
0x18003a15e  mov     r8d, esi
0x18003a161  lea     rdx, [rbp+4Fh+var_80]
0x18003a165  mov     ecx, ebx
0x18003a167  call    av_strerror
0x18003a16c  lea     rax, [rbp+4Fh+var_80]
0x18003a170  mov     r9, r14
0x18003a173  lea     r8, aCannotReadFile; "Cannot read file '%s': %s\n"
0x18003a17a  mov     [rsp+100h+var_E0], rax
0x18003a17f  lea     edx, [rsi-30h]
0x18003a182  lea     rcx, [rsp+100h+var_D0]
0x18003a187  call    av_log
0x18003a18c  jmp     short loc_18003A201
0x18003a18e  lea     rdx, [rbp+4Fh+Stat]; Stat
0x18003a192  mov     ecx, edi; FileHandle
0x18003a194  call    _fstat64i32
0x18003a199  test    eax, eax
0x18003a19b  jns     short loc_18003A1E4
0x18003a19d  lfence
0x18003a1a0  call    _errno
0x18003a1a5  mov     esi, 40h ; '@'
0x18003a1aa  lea     rcx, [rbp+4Fh+var_80]
0x18003a1ae  mov     r8d, esi
0x18003a1b1  xor     edx, edx
0x18003a1b3  mov     ebx, [rax]
0x18003a1b5  neg     ebx
0x18003a1b7  call    sub_18007B020
0x18003a1bc  mov     r8d, esi
0x18003a1bf  lea     rdx, [rbp+4Fh+var_80]
0x18003a1c3  mov     ecx, ebx
0x18003a1c5  call    av_strerror
0x18003a1ca  lea     r9, [rbp+4Fh+var_80]
0x18003a1ce  lea     r8, aErrorOccurredI; "Error occurred in fstat(): %s\n"
0x18003a1d5  lea     edx, [rsi-30h]
0x18003a1d8  lea     rcx, [rsp+100h+var_D0]
0x18003a1dd  call    av_log
0x18003a1e2  jmp     short loc_18003A1FA
0x18003a1e4  movsxd  rax, [rbp+4Fh+Stat.st_size]
0x18003a1e8  mov     [rsi], rax
0x18003a1eb  test    rax, rax
0x18003a1ee  jnz     short loc_18003A221
0x18003a1f0  mov     r14, rbx
0x18003a1f3  lfence
0x18003a1f6  mov     [r12], r14
0x18003a1fa  mov     ecx, edi; FileHandle
0x18003a1fc  call    _close
0x18003a201  mov     eax, ebx
0x18003a203  mov     rcx, [rbp+4Fh+var_40]
0x18003a207  xor     rcx, rsp; StackCookie
0x18003a20a  call    __security_check_cookie
0x18003a20f  add     rsp, 0D0h
0x18003a216  pop     r15
0x18003a218  pop     r14
0x18003a21a  pop     r12
0x18003a21c  pop     rdi
0x18003a21d  pop     rsi
0x18003a21e  pop     rbx
0x18003a21f  pop     rbp
0x18003a220  retn
0x18003a221  lfence
0x18003a224  mov     ecx, edi; FileHandle
0x18003a226  call    _get_osfhandle
0x18003a22b  xor     r9d, r9d
0x18003a22e  mov     [rsp+100h+var_E0], rbx
0x18003a233  xor     edx, edx
0x18003a235  mov     rcx, rax
0x18003a238  lea     r8d, [r9+2]
0x18003a23c  call    cs:CreateFileMappingFromApp
0x18003a242  mov     r15, rax
0x18003a245  lfence
0x18003a248  test    rax, rax
0x18003a24b  jnz     short loc_18003A272
0x18003a24d  lea     r8, aErrorOccurredI_0; "Error occurred in CreateFileMapping()\n"
0x18003a254  mov     edx, 10h
0x18003a259  lea     rcx, [rsp+100h+var_D0]
0x18003a25e  call    av_log
0x18003a263  mov     ecx, edi; FileHandle
0x18003a265  call    _close
0x18003a26a  or      eax, 0FFFFFFFFh
0x18003a26d  mov     [rsi], rbx
0x18003a270  jmp     short loc_18003A203
0x18003a272  mov     r9, [rsi]
0x18003a275  xor     r8d, r8d
0x18003a278  mov     rcx, r15
0x18003a27b  lea     edx, [r8+1]
0x18003a27f  call    cs:MapViewOfFileFromApp
0x18003a285  mov     rcx, r15; hObject
0x18003a288  mov     r14, rax
0x18003a28b  call    cs:CloseHandle
0x18003a291  test    r14, r14
0x18003a294  jnz     loc_18003A1F3
0x18003a29a  lfence
0x18003a29d  lea     r8, aErrorOccurredI_1; "Error occurred in MapViewOfFile()\n"
0x18003a2a4  jmp     short loc_18003A254
```
