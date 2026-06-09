# CBufferedReader::OpenFile(ushort const *)

- ea: `0x180032890`
- end: `0x1800329af`
- name: `?OpenFile@CBufferedReader@@QEAAJPEBG@Z`
- size: `287`
- prototype: `__int64 __fastcall(CBufferedReader *__hidden this, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002ef00`

## callees

- `0x1800326f8`
- `0x180032890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003295e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003295e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800328b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800328b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800328dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800328dd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003293d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003293d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032921`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032921`

## pseudocode

```c
__int64 __fastcall CBufferedReader::OpenFile(CBufferedReader *this, LPCWSTR lpFileName)
{
  void *v3; // rcx
  HANDLE FileW; // rax
  __int64 result; // rax
  int v7; // ecx
  LONG DistanceToMoveHigh[6]; // [rsp+40h] [rbp-18h] BYREF
  __int16 Buffer; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v10; // [rsp+70h] [rbp+18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp+20h] BYREF

  v10 = 0;
  v3 = *(void **)this;
  if ( v3 )
    CloseHandle(v3);
  FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  *(_QWORD *)this = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 2147500037LL;
  Buffer = 0;
  NumberOfBytesRead = 0;
  DistanceToMoveHigh[0] = 0;
  *((_DWORD *)this + 16394) = 0;
  if ( !ReadFile(FileW, &Buffer, 2u, &NumberOfBytesRead, 0)
    || SetFilePointer(*(HANDLE *)this, 0, DistanceToMoveHigh, 0) == -1 )
  {
    GetLastError();
  }
  else if ( Buffer == -257 )
  {
    *((_DWORD *)this + 16394) = 1;
  }
  *((_DWORD *)this + 16388) = 0;
  v7 = CBufferedReader::FillBuffer(this, 0, &v10);
  if ( v7 >= 0 && !*((_DWORD *)this + 16392) )
    v7 = CBufferedReader::FillBuffer(this, 1u, &v10);
  result = 0;
  if ( v7 != 1 )
    return (unsigned int)v7;
  return result;
}

```

## disassembly

```asm
0x180032890  mov     [rsp+arg_8], rbx
0x180032895  push    rdi
0x180032896  sub     rsp, 50h
0x18003289a  mov     rbx, rcx
0x18003289d  mov     [rsp+58h+arg_10], 0
0x1800328a5  mov     rcx, [rcx]; hObject
0x1800328a8  mov     rdi, rdx
0x1800328ab  test    rcx, rcx
0x1800328ae  jz      short loc_1800328B6
0x1800328b0  call    cs:__imp_CloseHandle
0x1800328b6  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800328bf  mov     r8d, 3; dwShareMode
0x1800328c5  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800328cd  xor     r9d, r9d; lpSecurityAttributes
0x1800328d0  mov     edx, 80000000h; dwDesiredAccess
0x1800328d5  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800328da  mov     rcx, rdi; lpFileName
0x1800328dd  call    cs:__imp_CreateFileW
0x1800328e3  mov     [rbx], rax
0x1800328e6  mov     rcx, rax; hFile
0x1800328e9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800328ed  jnz     short loc_1800328F9
0x1800328ef  mov     eax, 80004005h
0x1800328f4  jmp     loc_1800329A4
0x1800328f9  xor     eax, eax
0x1800328fb  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180032900  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x180032905  mov     [rsp+58h+Buffer], ax
0x18003290a  mov     [rsp+58h+NumberOfBytesRead], eax
0x18003290e  mov     [rsp+58h+DistanceToMoveHigh], eax
0x180032912  lea     r8d, [rax+2]; nNumberOfBytesToRead
0x180032916  mov     [rbx+10028h], eax
0x18003291c  mov     qword ptr [rsp+58h+dwCreationDisposition], rax; lpOverlapped
0x180032921  call    cs:__imp_ReadFile
0x180032927  mov     edi, 1
0x18003292c  test    eax, eax
0x18003292e  jz      short loc_18003295E
0x180032930  mov     rcx, [rbx]; hFile
0x180032933  lea     r8, [rsp+58h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180032938  xor     r9d, r9d; dwMoveMethod
0x18003293b  xor     edx, edx; lDistanceToMove
0x18003293d  call    cs:__imp_SetFilePointer
0x180032943  cmp     eax, 0FFFFFFFFh
0x180032946  jz      short loc_18003295E
0x180032948  cmp     byte ptr [rsp+58h+Buffer], 0FFh
0x18003294d  jnz     short loc_180032964
0x18003294f  cmp     byte ptr [rsp+58h+Buffer+1], 0FEh
0x180032954  jnz     short loc_180032964
0x180032956  mov     [rbx+10028h], edi
0x18003295c  jmp     short loc_180032964
0x18003295e  call    cs:__imp_GetLastError
0x180032964  lea     r8, [rsp+58h+arg_10]; unsigned int *
0x180032969  mov     dword ptr [rbx+10010h], 0
0x180032973  xor     edx, edx; unsigned int
0x180032975  mov     rcx, rbx; this
0x180032978  call    ?FillBuffer@CBufferedReader@@AEAAJKPEAK@Z; CBufferedReader::FillBuffer(ulong,ulong *)
0x18003297d  mov     ecx, eax
0x18003297f  test    eax, eax
0x180032981  js      short loc_18003299D
0x180032983  cmp     dword ptr [rbx+10020h], 0
0x18003298a  jnz     short loc_18003299D
0x18003298c  lea     r8, [rsp+58h+arg_10]; unsigned int *
0x180032991  mov     edx, edi; unsigned int
0x180032993  mov     rcx, rbx; this
0x180032996  call    ?FillBuffer@CBufferedReader@@AEAAJKPEAK@Z; CBufferedReader::FillBuffer(ulong,ulong *)
0x18003299b  mov     ecx, eax
0x18003299d  xor     eax, eax
0x18003299f  cmp     ecx, edi
0x1800329a1  cmovnz  eax, ecx
0x1800329a4  mov     rbx, [rsp+58h+arg_8]
0x1800329a9  add     rsp, 50h
0x1800329ad  pop     rdi
0x1800329ae  retn
```
