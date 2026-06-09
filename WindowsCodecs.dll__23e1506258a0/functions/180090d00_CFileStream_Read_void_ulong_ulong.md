# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x180090d00`
- end: `0x180090e6d`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `365`
- prototype: `int(CFileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180090d00`
- `0x1800916e0`
- `0x1800bb784`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180090d51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180090d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090e35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090e35`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180090d68`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180090de2`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180090d68`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180090de2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180090d8e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180090d8e`

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
0x180090d00  mov     [rsp+arg_10], rbx
0x180090d05  push    rbp
0x180090d06  push    rsi
0x180090d07  push    rdi
0x180090d08  push    r14
0x180090d0a  push    r15
0x180090d0c  sub     rsp, 30h
0x180090d10  mov     qword ptr [rsp+58h+NewFilePointer], 0
0x180090d19  mov     r14, r9
0x180090d1c  mov     [rsp+58h+NumberOfBytesRead], 0
0x180090d24  mov     ebp, r8d
0x180090d27  mov     rax, [rcx]
0x180090d2a  mov     r15, rdx
0x180090d2d  mov     rsi, rcx
0x180090d30  mov     rax, [rax+70h]
0x180090d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090d39  test    r15, r15
0x180090d3c  jz      loc_180090E4C
0x180090d42  cmp     qword ptr [rsi+68h], 0FFFFFFFFFFFFFFFFh
0x180090d47  jz      loc_180090E53
0x180090d4d  xor     ecx, ecx; dwErrCode
0x180090d4f  xor     ebx, ebx
0x180090d51  call    cs:__imp_SetLastError
0x180090d57  mov     rcx, [rsi+68h]; hFile
0x180090d5b  lea     r9d, [rbx+1]; dwMoveMethod
0x180090d5f  lea     r8, [rsp+58h+NewFilePointer]; lpNewFilePointer
0x180090d64  mov     edx, ebx; liDistanceToMove
0x180090d66  xor     edi, edi
0x180090d68  call    cs:__imp_SetFilePointerEx
0x180090d6e  test    eax, eax
0x180090d70  jz      loc_180090E35
0x180090d76  test    edi, edi
0x180090d78  js      short loc_180090DAC
0x180090d7a  mov     rcx, [rsi+68h]; hFile
0x180090d7e  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180090d83  mov     r8d, ebp; nNumberOfBytesToRead
0x180090d86  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x180090d8b  mov     rdx, r15; lpBuffer
0x180090d8e  call    cs:__imp_ReadFile
0x180090d94  test    eax, eax
0x180090d96  jz      loc_180090E5A
0x180090d9c  mov     eax, [rsp+58h+NumberOfBytesRead]
0x180090da0  test    r14, r14
0x180090da3  jz      short loc_180090DA8
0x180090da5  mov     [r14], eax
0x180090da8  cmp     eax, ebp
0x180090daa  jnz     short loc_180090DCE
0x180090dac  mov     rcx, [rsi]
0x180090daf  mov     rax, [rcx+78h]
0x180090db3  mov     rcx, rsi
0x180090db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090dbb  mov     rbx, [rsp+58h+arg_10]
0x180090dc0  mov     eax, edi
0x180090dc2  add     rsp, 30h
0x180090dc6  pop     r15
0x180090dc8  pop     r14
0x180090dca  pop     rdi
0x180090dcb  pop     rsi
0x180090dcc  pop     rbp
0x180090dcd  retn
0x180090dce  test    r14, r14
0x180090dd1  jnz     short loc_180090DAC
0x180090dd3  mov     rdx, qword ptr [rsp+58h+NewFilePointer]; liDistanceToMove
0x180090dd8  xor     r9d, r9d; dwMoveMethod
0x180090ddb  mov     rcx, [rsi+68h]; hFile
0x180090ddf  xor     r8d, r8d; lpNewFilePointer
0x180090de2  call    cs:__imp_SetFilePointerEx
0x180090de8  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180090def  mov     ebx, 88982F72h
0x180090df4  jz      short loc_180090DFD
0x180090df6  mov     ecx, ebx; int
0x180090df8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180090dfd  mov     edi, ebx
0x180090dff  jmp     short loc_180090DAC
0x180090e01  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180090e08  jz      short loc_180090DAC
0x180090e0a  mov     ecx, edi; int
0x180090e0c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180090e11  jmp     short loc_180090DAC
0x180090e13  test    edi, edi
0x180090e15  mov     eax, 88982F94h
0x180090e1a  cmovns  edi, eax
0x180090e1d  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x180090e23  jz      loc_180090D76
0x180090e29  mov     ecx, edi; int
0x180090e2b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180090e30  jmp     loc_180090D76
0x180090e35  call    cs:__imp_GetLastError
0x180090e3b  mov     edi, eax
0x180090e3d  test    eax, eax
0x180090e3f  jle     short loc_180090E13
0x180090e41  movzx   edi, ax
0x180090e44  or      edi, 80070000h
0x180090e4a  jmp     short loc_180090E13
0x180090e4c  mov     edi, 80070057h
0x180090e51  jmp     short loc_180090E01
0x180090e53  mov     edi, 88982F0Ch
0x180090e58  jmp     short loc_180090E01
0x180090e5a  call    ?GetWin32HRESULT@@YAJXZ; GetWin32HRESULT(void)
0x180090e5f  test    eax, eax
0x180090e61  mov     edi, eax
0x180090e63  mov     ebx, 88982F72h
0x180090e68  cmovns  edi, ebx
0x180090e6b  jmp     short loc_180090E01
```
