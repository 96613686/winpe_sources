# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x180091300`
- end: `0x18009148c`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `396`
- prototype: `int(CFileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180091300`
- `0x180091d24`
- `0x1800bd9d4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091351`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009144e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009144e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18009136e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800913f5`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18009136e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800913f5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009139a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009139a`

## pseudocode

```c
__int64 __fastcall CFileStream::Read(CFileStream *this, void *a2, DWORD a3, unsigned int *a4)
{
  signed int Win32HRESULT; // edi
  DWORD v9; // eax
  signed int LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF
  _LARGE_INTEGER NewFilePointer; // [rsp+68h] [rbp+10h] BYREF

  NewFilePointer.QuadPart = 0;
  NumberOfBytesRead = 0;
  (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)this + 112LL))(this);
  if ( !a2 )
  {
    Win32HRESULT = -2147024809;
    goto LABEL_14;
  }
  if ( *((_QWORD *)this + 13) == -1 )
  {
    Win32HRESULT = -2003292404;
LABEL_14:
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(Win32HRESULT);
    goto LABEL_9;
  }
  SetLastError(0);
  Win32HRESULT = 0;
  if ( !SetFilePointerEx(*((HANDLE *)this + 13), 0, &NewFilePointer, 1u) )
  {
    LastError = GetLastError();
    Win32HRESULT = LastError;
    if ( LastError > 0 )
      Win32HRESULT = (unsigned __int16)LastError | 0x80070000;
    if ( Win32HRESULT >= 0 )
      Win32HRESULT = -2003292268;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(Win32HRESULT);
  }
  if ( Win32HRESULT >= 0 )
  {
    if ( ReadFile(*((HANDLE *)this + 13), a2, a3, &NumberOfBytesRead, 0) )
    {
      v9 = NumberOfBytesRead;
      if ( a4 )
        *a4 = NumberOfBytesRead;
      if ( v9 != a3 && !a4 )
      {
        SetFilePointerEx(*((HANDLE *)this + 13), NewFilePointer, 0, 0);
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(-2003292302);
        Win32HRESULT = -2003292302;
      }
      goto LABEL_9;
    }
    Win32HRESULT = GetWin32HRESULT();
    if ( Win32HRESULT >= 0 )
      Win32HRESULT = -2003292302;
    goto LABEL_14;
  }
LABEL_9:
  (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)this + 120LL))(this);
  return (unsigned int)Win32HRESULT;
}

```

## disassembly

```asm
0x180091300  mov     [rsp+arg_10], rbx
0x180091305  push    rbp
0x180091306  push    rsi
0x180091307  push    rdi
0x180091308  push    r14
0x18009130a  push    r15
0x18009130c  sub     rsp, 30h
0x180091310  mov     qword ptr [rsp+58h+NewFilePointer], 0
0x180091319  mov     r14, r9
0x18009131c  mov     [rsp+58h+NumberOfBytesRead], 0
0x180091324  mov     ebp, r8d
0x180091327  mov     rax, [rcx]
0x18009132a  mov     r15, rdx
0x18009132d  mov     rsi, rcx
0x180091330  mov     rax, [rax+70h]
0x180091334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091339  test    r15, r15
0x18009133c  jz      loc_18009146B
0x180091342  cmp     qword ptr [rsi+68h], 0FFFFFFFFFFFFFFFFh
0x180091347  jz      loc_180091472
0x18009134d  xor     ecx, ecx; dwErrCode
0x18009134f  xor     ebx, ebx
0x180091351  call    cs:__imp_SetLastError
0x180091358  nop     dword ptr [rax+rax+00h]
0x18009135d  mov     rcx, [rsi+68h]; hFile
0x180091361  lea     r9d, [rbx+1]; dwMoveMethod
0x180091365  lea     r8, [rsp+58h+NewFilePointer]; lpNewFilePointer
0x18009136a  mov     edx, ebx; liDistanceToMove
0x18009136c  xor     edi, edi
0x18009136e  call    cs:__imp_SetFilePointerEx
0x180091375  nop     dword ptr [rax+rax+00h]
0x18009137a  test    eax, eax
0x18009137c  jz      loc_18009144E
0x180091382  test    edi, edi
0x180091384  js      short loc_1800913BE
0x180091386  mov     rcx, [rsi+68h]; hFile
0x18009138a  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009138f  mov     r8d, ebp; nNumberOfBytesToRead
0x180091392  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x180091397  mov     rdx, r15; lpBuffer
0x18009139a  call    cs:__imp_ReadFile
0x1800913a1  nop     dword ptr [rax+rax+00h]
0x1800913a6  test    eax, eax
0x1800913a8  jz      loc_180091479
0x1800913ae  mov     eax, [rsp+58h+NumberOfBytesRead]
0x1800913b2  test    r14, r14
0x1800913b5  jz      short loc_1800913BA
0x1800913b7  mov     [r14], eax
0x1800913ba  cmp     eax, ebp
0x1800913bc  jnz     short loc_1800913E1
0x1800913be  mov     rcx, [rsi]
0x1800913c1  mov     rax, [rcx+78h]
0x1800913c5  mov     rcx, rsi
0x1800913c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800913cd  mov     rbx, [rsp+58h+arg_10]
0x1800913d2  mov     eax, edi
0x1800913d4  add     rsp, 30h
0x1800913d8  pop     r15
0x1800913da  pop     r14
0x1800913dc  pop     rdi
0x1800913dd  pop     rsi
0x1800913de  pop     rbp
0x1800913df  retn
0x1800913e1  test    r14, r14
0x1800913e4  jnz     short loc_1800913BE
0x1800913e6  mov     rdx, qword ptr [rsp+58h+NewFilePointer]; liDistanceToMove
0x1800913eb  xor     r9d, r9d; dwMoveMethod
0x1800913ee  mov     rcx, [rsi+68h]; hFile
0x1800913f2  xor     r8d, r8d; lpNewFilePointer
0x1800913f5  call    cs:__imp_SetFilePointerEx
0x1800913fc  nop     dword ptr [rax+rax+00h]
0x180091401  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180091408  mov     ebx, 88982F72h
0x18009140d  jz      short loc_180091416
0x18009140f  mov     ecx, ebx; int
0x180091411  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180091416  mov     edi, ebx
0x180091418  jmp     short loc_1800913BE
0x18009141a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180091421  jz      short loc_1800913BE
0x180091423  mov     ecx, edi; int
0x180091425  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009142a  jmp     short loc_1800913BE
0x18009142c  test    edi, edi
0x18009142e  mov     eax, 88982F94h
0x180091433  cmovns  edi, eax
0x180091436  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x18009143c  jz      loc_180091382
0x180091442  mov     ecx, edi; int
0x180091444  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180091449  jmp     loc_180091382
0x18009144e  call    cs:__imp_GetLastError
0x180091455  nop     dword ptr [rax+rax+00h]
0x18009145a  mov     edi, eax
0x18009145c  test    eax, eax
0x18009145e  jle     short loc_18009142C
0x180091460  movzx   edi, ax
0x180091463  or      edi, 80070000h
0x180091469  jmp     short loc_18009142C
0x18009146b  mov     edi, 80070057h
0x180091470  jmp     short loc_18009141A
0x180091472  mov     edi, 88982F0Ch
0x180091477  jmp     short loc_18009141A
0x180091479  call    ?GetWin32HRESULT@@YAJXZ; GetWin32HRESULT(void)
0x18009147e  test    eax, eax
0x180091480  mov     edi, eax
0x180091482  mov     ebx, 88982F72h
0x180091487  cmovns  edi, ebx
0x18009148a  jmp     short loc_18009141A
```
