# ByteSliceManager::WriteTo(void *)

- ea: `0x180035350`
- end: `0x1800354ba`
- name: `?WriteTo@ByteSliceManager@@UEBAXPEAX@Z`
- size: `362`
- prototype: `void __fastcall(ByteSliceManager *__hidden this, HANDLE hFile)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18006cae0`
- `0x18006cb20`

## callees

- `0x180035350`
- `0x180035640`
- `0x18003ed6c`
- `0x18006c18c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800353fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003543c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800353fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003543c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180035373`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800353a9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180035486`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003549d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180035373`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800353a9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180035486`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003549d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800353f4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800353f4`

## pseudocode

```c
void __fastcall ByteSliceManager::WriteTo(ByteSliceManager *this, HANDLE hFile)
{
  DWORD v4; // eax
  unsigned int v5; // edx
  LONG v6; // r10d
  unsigned __int8 *FreeBlockAddress; // rax
  unsigned int v8; // ecx
  DWORD v9; // ebx
  signed int LastError; // eax
  signed int v11; // eax
  int v12; // ebx
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-48h] BYREF
  const void *retaddr; // [rsp+78h] [rbp+0h]
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+8h] BYREF

  v4 = SetFilePointer(hFile, 0, 0, 1u);
  v5 = v4 % *((unsigned __int8 *)this + 35);
  if ( v5 )
    v6 = v4 + *((unsigned __int8 *)this + 35) - v5;
  else
    v6 = v4;
  *((_DWORD *)this + 10) = v6;
  if ( v4 != v6 )
    SetFilePointer(hFile, v6, 0, 0);
  FreeBlockAddress = ByteSliceManager::LastFreeBlockAddress(this);
  v8 = *(_DWORD *)FreeBlockAddress & 0xFF000000;
  NumberOfBytesWritten = 0;
  v9 = (_DWORD)FreeBlockAddress + (v8 != 0 ? 4 : 8) - *((_DWORD *)this + 4);
  if ( !WriteFile(hFile, *((LPCVOID *)this + 2), v9, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CNLException::CNLException((CNLException *)pExceptionObject, (unsigned int)LastError, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  if ( NumberOfBytesWritten != v9 )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    CNLException::CNLException((CNLException *)pExceptionObject, (unsigned int)v11, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  if ( *((_BYTE *)this + 30) )
    SetFilePointer(hFile, *((_DWORD *)this + 3) - *((_DWORD *)this + 11), 0, 0);
  v12 = *((_DWORD *)this + 10);
  *((_DWORD *)this + 11) = SetFilePointer(hFile, 0, 0, 1u) - v12;
}

```

## disassembly

```asm
0x180035350  mov     [rsp+arg_8], rbx
0x180035355  mov     [rsp+arg_10], rsi
0x18003535a  push    rdi
0x18003535b  sub     rsp, 70h
0x18003535f  mov     rsi, rdx
0x180035362  mov     rdi, rcx
0x180035365  mov     rcx, rsi; hFile
0x180035368  mov     r9d, 1; dwMoveMethod
0x18003536e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180035371  xor     edx, edx; lDistanceToMove
0x180035373  call    cs:__imp_SetFilePointer
0x180035379  movzx   r10d, byte ptr [rdi+23h]
0x18003537e  xor     edx, edx
0x180035380  mov     ecx, eax
0x180035382  div     r10d
0x180035385  test    edx, edx
0x180035387  jz      short loc_180035391
0x180035389  sub     r10d, edx
0x18003538c  add     r10d, ecx
0x18003538f  jmp     short loc_180035394
0x180035391  mov     r10d, ecx
0x180035394  mov     [rdi+28h], r10d
0x180035398  cmp     ecx, r10d
0x18003539b  jz      short loc_1800353AF
0x18003539d  xor     r9d, r9d; dwMoveMethod
0x1800353a0  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800353a3  mov     edx, r10d; lDistanceToMove
0x1800353a6  mov     rcx, rsi; hFile
0x1800353a9  call    cs:__imp_SetFilePointer
0x1800353af  mov     rcx, rdi; this
0x1800353b2  call    ?LastFreeBlockAddress@ByteSliceManager@@IEBAPEAEXZ; ByteSliceManager::LastFreeBlockAddress(void)
0x1800353b7  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800353bf  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800353c8  mov     ecx, [rax]
0x1800353ca  and     ecx, 0FF000000h
0x1800353d0  mov     [rsp+78h+NumberOfBytesWritten], 0
0x1800353db  neg     ecx
0x1800353dd  mov     rcx, rsi; hFile
0x1800353e0  sbb     edx, edx
0x1800353e2  and     edx, 0FFFFFFFCh
0x1800353e5  lea     ebx, [rdx+8]
0x1800353e8  mov     rdx, [rdi+10h]; lpBuffer
0x1800353ec  sub     ebx, [rdi+10h]
0x1800353ef  add     ebx, eax
0x1800353f1  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800353f4  call    cs:__imp_WriteFile
0x1800353fa  test    eax, eax
0x1800353fc  jnz     short loc_180035433
0x1800353fe  call    cs:__imp_GetLastError
0x180035404  test    eax, eax
0x180035406  jle     short loc_180035410
0x180035408  movzx   eax, ax
0x18003540b  or      eax, 80070000h
0x180035410  mov     r8, [rsp+78h]; void *
0x180035415  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18003541a  mov     edx, eax; int
0x18003541c  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180035421  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180035428  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18003542d  call    _CxxThrowException_0
0x180035433  cmp     [rsp+78h+NumberOfBytesWritten], ebx
0x18003543a  jz      short loc_180035471
0x18003543c  call    cs:__imp_GetLastError
0x180035442  test    eax, eax
0x180035444  jle     short loc_18003544E
0x180035446  movzx   eax, ax
0x180035449  or      eax, 80070000h
0x18003544e  mov     r8, [rsp+78h]; void *
0x180035453  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180035458  mov     edx, eax; int
0x18003545a  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18003545f  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180035466  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18003546b  call    _CxxThrowException_0
0x180035471  cmp     byte ptr [rdi+1Eh], 0
0x180035475  jz      short loc_18003548C
0x180035477  mov     edx, [rdi+0Ch]
0x18003547a  xor     r9d, r9d; dwMoveMethod
0x18003547d  sub     edx, [rdi+2Ch]; lDistanceToMove
0x180035480  xor     r8d, r8d; lpDistanceToMoveHigh
0x180035483  mov     rcx, rsi; hFile
0x180035486  call    cs:__imp_SetFilePointer
0x18003548c  mov     ebx, [rdi+28h]
0x18003548f  mov     r9d, 1; dwMoveMethod
0x180035495  xor     r8d, r8d; lpDistanceToMoveHigh
0x180035498  xor     edx, edx; lDistanceToMove
0x18003549a  mov     rcx, rsi; hFile
0x18003549d  call    cs:__imp_SetFilePointer
0x1800354a3  sub     eax, ebx
0x1800354a5  lea     r11, [rsp+78h+var_8]
0x1800354aa  mov     rbx, [r11+18h]
0x1800354ae  mov     rsi, [r11+20h]
0x1800354b2  mov     [rdi+2Ch], eax
0x1800354b5  mov     rsp, r11
0x1800354b8  pop     rdi
0x1800354b9  retn
```
