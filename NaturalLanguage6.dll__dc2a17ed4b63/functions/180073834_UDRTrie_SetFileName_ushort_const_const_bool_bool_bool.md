# UDRTrie::SetFileName(ushort const * const,bool,bool,bool)

- ea: `0x180073834`
- end: `0x180073ac0`
- name: `?SetFileName@UDRTrie@@QEAAXQEBG_N11@Z`
- size: `652`
- prototype: `void(UDRTrie *__hidden this, const unsigned __int16 *const, bool, bool, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18006bea4`

## callees

- `0x1800162e4`
- `0x180035640`
- `0x18003c078`
- `0x18003ed6c`
- `0x180073834`
- `0x18009e300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1800738fa`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1800738fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073a0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073a49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073a0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073a49`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800738c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180073924`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800738c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180073924`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180073968`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180073968`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800739b3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800739b3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800739fa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800739fa`

## pseudocode

```c
void __fastcall UDRTrie::SetFileName(UDRTrie *this, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  const WCHAR *v4; // rsi
  int v5; // eax
  char *FileW; // rax
  char *v7; // rcx
  int v8; // edi
  BOOL v9; // eax
  DWORD v10; // ecx
  void *v11; // rcx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-21h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-1Dh] BYREF
  _BYTE pExceptionObject[64]; // [rsp+48h] [rbp-19h] BYREF
  __int16 Buffer; // [rsp+88h] [rbp+27h] BYREF
  const void *retaddr; // [rsp+B8h] [rbp+57h]

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  if ( (unsigned int)(v2 - 1) > 0x1FE )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 3241213977LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  v4 = (const WCHAR *)((char *)this + 36);
  v5 = StringCchCopyW((unsigned __int16 *)this + 18, 0x200u, a2);
  ThrowIfFailed(v5);
  *((_BYTE *)this + 1098) = 1;
  FileW = (char *)CreateFileW(v4, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  *((_QWORD *)this + 133) = FileW;
  v7 = FileW;
  if ( !FileW || FileW == (char *)-1LL )
  {
    v8 = 0;
    while ( 1 )
    {
      if ( FileW )
      {
        v7 = FileW;
        if ( FileW != (char *)-1LL )
          break;
      }
      SleepEx(5 * (v8 + 1), 1);
      FileW = (char *)CreateFileW(v4, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      ++v8;
      *((_QWORD *)this + 133) = FileW;
      v7 = FileW;
      if ( v8 >= 5 )
      {
        if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        {
          CNLException::CNLException((CNLException *)pExceptionObject, 3241213976LL, retaddr);
          throw (CNLException *)pExceptionObject;
        }
        break;
      }
    }
    *((_BYTE *)this + 1098) = 1;
  }
  NumberOfBytesRead = 0;
  v9 = ReadFile(v7, &Buffer, 2u, &NumberOfBytesRead, 0);
  v10 = NumberOfBytesRead;
  if ( !v9 || NumberOfBytesRead == 2 && Buffer != -257 )
    *((_BYTE *)this + 1098) = 1;
  if ( !*((_BYTE *)this + 1098) && !v10 )
  {
    v11 = (void *)*((_QWORD *)this + 133);
    NumberOfBytesWritten = 0;
    if ( SetFilePointer(v11, 0, 0, 0) )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, 3241213975LL, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    if ( !WriteFile(*((HANDLE *)this + 133), byte_1800C6618, 2u, &NumberOfBytesWritten, 0) )
    {
      CloseHandle(*((HANDLE *)this + 133));
      *((_QWORD *)this + 133) = 0;
      CNLException::CNLException((CNLException *)pExceptionObject, 3241213975LL, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    *((_BYTE *)this + 1097) = 1;
  }
  CloseHandle(*((HANDLE *)this + 133));
  *((_QWORD *)this + 133) = 0;
}

```

## disassembly

```asm
0x180073834  mov     [rsp-8+arg_10], rbx
0x180073839  mov     [rsp-8+arg_18], rsi
0x18007383e  push    rbp
0x18007383f  push    rdi
0x180073840  push    r14
0x180073842  lea     rbp, [rsp-3Fh]
0x180073847  sub     rsp, 0A0h
0x18007384e  mov     rax, cs:__security_cookie
0x180073855  xor     rax, rsp
0x180073858  mov     [rbp+4Fh+var_20], rax
0x18007385c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180073860  mov     rbx, rcx
0x180073863  xor     r14d, r14d
0x180073866  inc     rax
0x180073869  cmp     [rdx+rax*2], r14w
0x18007386e  jnz     short loc_180073866
0x180073870  dec     eax
0x180073872  cmp     eax, 1FEh
0x180073877  ja      loc_180073A9D
0x18007387d  lea     rsi, [rcx+24h]
0x180073881  mov     r8, rdx; unsigned __int16 *
0x180073884  mov     rcx, rsi; unsigned __int16 *
0x180073887  mov     edx, 200h; unsigned __int64
0x18007388c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180073891  mov     ecx, eax; int
0x180073893  call    ?ThrowIfFailed@@YAXJ@Z; ThrowIfFailed(long)
0x180073898  xor     r9d, r9d; lpSecurityAttributes
0x18007389b  mov     [rsp+0B0h+hTemplateFile], r14; hTemplateFile
0x1800738a0  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800738a8  mov     edx, 80000000h; dwDesiredAccess
0x1800738ad  mov     rcx, rsi; lpFileName
0x1800738b0  mov     byte ptr [rbx+44Ah], 1
0x1800738b7  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800738bf  lea     r8d, [r9+1]; dwShareMode
0x1800738c3  call    cs:__imp_CreateFileW
0x1800738c9  mov     [rbx+428h], rax
0x1800738d0  mov     rcx, rax
0x1800738d3  test    rax, rax
0x1800738d6  jz      short loc_1800738DE
0x1800738d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800738dc  jnz     short loc_18007394F
0x1800738de  mov     edi, r14d
0x1800738e1  test    rax, rax
0x1800738e4  jz      short loc_1800738EF
0x1800738e6  mov     rcx, rax
0x1800738e9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800738ed  jnz     short loc_180073948
0x1800738ef  lea     eax, [rdi+1]
0x1800738f2  mov     edx, 1; bAlertable
0x1800738f7  lea     ecx, [rax+rax*4]; dwMilliseconds
0x1800738fa  call    cs:__imp_SleepEx
0x180073900  xor     r9d, r9d; lpSecurityAttributes
0x180073903  mov     [rsp+0B0h+hTemplateFile], r14; hTemplateFile
0x180073908  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180073910  mov     edx, 80000000h; dwDesiredAccess
0x180073915  mov     rcx, rsi; lpFileName
0x180073918  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180073920  lea     r8d, [r9+1]; dwShareMode
0x180073924  call    cs:__imp_CreateFileW
0x18007392a  inc     edi
0x18007392c  mov     [rbx+428h], rax
0x180073933  mov     rcx, rax; hFile
0x180073936  cmp     edi, 5
0x180073939  jl      short loc_1800738E1
0x18007393b  dec     rax
0x18007393e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180073942  ja      loc_180073A7A
0x180073948  mov     byte ptr [rbx+44Ah], 1
0x18007394f  mov     edi, 2
0x180073954  mov     [rbp+4Fh+NumberOfBytesRead], r14d
0x180073958  mov     r8d, edi; nNumberOfBytesToRead
0x18007395b  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14; lpOverlapped
0x180073960  lea     r9, [rbp+4Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x180073964  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x180073968  call    cs:__imp_ReadFile
0x18007396e  mov     ecx, [rbp+4Fh+NumberOfBytesRead]
0x180073971  test    eax, eax
0x180073973  jz      short loc_180073984
0x180073975  cmp     ecx, edi
0x180073977  jnz     short loc_18007398B
0x180073979  mov     eax, 0FEFFh
0x18007397e  cmp     [rbp+4Fh+Buffer], ax
0x180073982  jz      short loc_18007398B
0x180073984  mov     byte ptr [rbx+44Ah], 1
0x18007398b  cmp     [rbx+44Ah], r14b
0x180073992  jnz     loc_180073A42
0x180073998  test    ecx, ecx
0x18007399a  jnz     loc_180073A42
0x1800739a0  mov     rcx, [rbx+428h]; hFile
0x1800739a7  xor     r9d, r9d; dwMoveMethod
0x1800739aa  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800739ad  mov     [rbp+4Fh+NumberOfBytesWritten], r14d
0x1800739b1  xor     edx, edx; lDistanceToMove
0x1800739b3  call    cs:__imp_SetFilePointer
0x1800739b9  test    eax, eax
0x1800739bb  jz      short loc_1800739E0
0x1800739bd  mov     r8, [rbp+57h]; void *
0x1800739c1  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x1800739c5  mov     edx, 0C1310017h; int
0x1800739ca  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x1800739cf  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x1800739d6  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1800739da  call    _CxxThrowException_0
0x1800739e0  mov     rcx, [rbx+428h]; hFile
0x1800739e7  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800739eb  mov     r8d, edi; nNumberOfBytesToWrite
0x1800739ee  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14; lpOverlapped
0x1800739f3  lea     rdx, byte_1800C6618; lpBuffer
0x1800739fa  call    cs:__imp_WriteFile
0x180073a00  test    eax, eax
0x180073a02  jnz     short loc_180073A3B
0x180073a04  mov     rcx, [rbx+428h]; hObject
0x180073a0b  call    cs:__imp_CloseHandle
0x180073a11  mov     r8, [rbp+57h]; void *
0x180073a15  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180073a19  mov     edx, 0C1310017h; int
0x180073a1e  mov     [rbx+428h], r14
0x180073a25  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180073a2a  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180073a31  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180073a35  call    _CxxThrowException_0
0x180073a3b  mov     byte ptr [rbx+449h], 1
0x180073a42  mov     rcx, [rbx+428h]; hObject
0x180073a49  call    cs:__imp_CloseHandle
0x180073a4f  mov     [rbx+428h], r14
0x180073a56  mov     rcx, [rbp+4Fh+var_20]
0x180073a5a  xor     rcx, rsp; StackCookie
0x180073a5d  call    __security_check_cookie
0x180073a62  lea     r11, [rsp+0B0h+var_10]
0x180073a6a  mov     rbx, [r11+30h]
0x180073a6e  mov     rsi, [r11+38h]
0x180073a72  mov     rsp, r11
0x180073a75  pop     r14
0x180073a77  pop     rdi
0x180073a78  pop     rbp
0x180073a79  retn
0x180073a7a  mov     r8, [rbp+57h]; void *
0x180073a7e  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180073a82  mov     edx, 0C1310018h; int
0x180073a87  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180073a8c  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180073a93  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180073a97  call    _CxxThrowException_0
0x180073a9d  mov     r8, [rbp+57h]; void *
0x180073aa1  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180073aa5  mov     edx, 0C1310019h; int
0x180073aaa  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180073aaf  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180073ab6  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180073aba  call    _CxxThrowException_0
```
