# ByteSliceManager::WriteTo(void *)

- ea: `0x18009cf70`
- end: `0x18009d100`
- name: `?WriteTo@ByteSliceManager@@UEBAXPEAX@Z`
- size: `400`
- prototype: `void __fastcall(ByteSliceManager *__hidden this, HANDLE hFile)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18009d750`
- `0x18009d7a0`

## callees

- `0x1800598e0`
- `0x180062344`
- `0x18009cf70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d06d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d06d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009d00e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009d00e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18009cf95`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18009cfcb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18009d0d2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18009d0e9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18009cf95`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18009cfcb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18009d0d2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18009d0e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ByteSliceManager::WriteTo(ByteSliceManager *this, HANDLE hFile)
{
  DWORD v4; // ecx
  unsigned int v5; // edx
  LONG v6; // r10d
  unsigned __int8 *FreeBlockAddress; // rax
  DWORD v8; // ebx
  signed int LastError; // eax
  signed int v10; // eax
  int v11; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-19h] BYREF
  signed int v13; // [rsp+38h] [rbp-11h]
  __int128 v14; // [rsp+40h] [rbp-9h]
  signed int v15; // [rsp+50h] [rbp+7h]
  int v16; // [rsp+60h] [rbp+17h]
  __int128 v17; // [rsp+68h] [rbp+1Fh]
  __int64 v18; // [rsp+78h] [rbp+2Fh]
  DWORD NumberOfBytesWritten; // [rsp+B0h] [rbp+67h] BYREF

  v4 = SetFilePointer(hFile, 0, 0, 1u);
  v5 = v4 % *((unsigned __int8 *)this + 40);
  if ( v5 )
    v6 = v4 + *((unsigned __int8 *)this + 40) - v5;
  else
    v6 = v4;
  *((_DWORD *)this + 11) = v6;
  if ( v4 != v6 )
    SetFilePointer(hFile, v6, 0, 0);
  FreeBlockAddress = ByteSliceManager::LastFreeBlockAddress(this);
  v8 = (_DWORD)FreeBlockAddress + ((*(_DWORD *)FreeBlockAddress & 0xFF000000) != 0 ? 4 : 8) - *((_DWORD *)this + 4);
  NumberOfBytesWritten = 0;
  if ( !WriteFile(hFile, *((LPCVOID *)this + 2), v8, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = LastError;
    v14 = 0;
    pExceptionObject = &CNLException::`vftable';
    v15 = LastError;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    throw (CNLException *)&pExceptionObject;
  }
  if ( NumberOfBytesWritten != v8 )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    v13 = v10;
    v14 = 0;
    pExceptionObject = &CNLException::`vftable';
    v15 = v10;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    throw (CNLException *)&pExceptionObject;
  }
  if ( *((_BYTE *)this + 30) )
    SetFilePointer(hFile, *((_DWORD *)this + 2) - *((_DWORD *)this + 12), 0, 0);
  v11 = *((_DWORD *)this + 11);
  *((_DWORD *)this + 12) = SetFilePointer(hFile, 0, 0, 1u) - v11;
}

```

## disassembly

```asm
0x18009cf70  push    rbp
0x18009cf72  push    rbx
0x18009cf73  push    rsi
0x18009cf74  push    rdi
0x18009cf75  lea     rbp, [rsp-3Fh]
0x18009cf7a  sub     rsp, 88h
0x18009cf81  mov     rsi, rdx
0x18009cf84  mov     rdi, rcx
0x18009cf87  mov     r9d, 1; dwMoveMethod
0x18009cf8d  xor     r8d, r8d; lpDistanceToMoveHigh
0x18009cf90  xor     edx, edx; lDistanceToMove
0x18009cf92  mov     rcx, rsi; hFile
0x18009cf95  call    cs:__imp_SetFilePointer
0x18009cf9b  mov     ecx, eax
0x18009cf9d  movzx   r10d, byte ptr [rdi+28h]
0x18009cfa2  xor     edx, edx
0x18009cfa4  div     r10d
0x18009cfa7  test    edx, edx
0x18009cfa9  jz      short loc_18009CFB3
0x18009cfab  sub     r10d, edx
0x18009cfae  add     r10d, ecx
0x18009cfb1  jmp     short loc_18009CFB6
0x18009cfb3  mov     r10d, ecx
0x18009cfb6  mov     [rdi+2Ch], r10d
0x18009cfba  cmp     ecx, r10d
0x18009cfbd  jz      short loc_18009CFD1
0x18009cfbf  xor     r9d, r9d; dwMoveMethod
0x18009cfc2  xor     r8d, r8d; lpDistanceToMoveHigh
0x18009cfc5  mov     edx, r10d; lDistanceToMove
0x18009cfc8  mov     rcx, rsi; hFile
0x18009cfcb  call    cs:__imp_SetFilePointer
0x18009cfd1  mov     rcx, rdi; this
0x18009cfd4  call    ?LastFreeBlockAddress@ByteSliceManager@@IEBAPEAEXZ; ByteSliceManager::LastFreeBlockAddress(void)
0x18009cfd9  mov     ecx, [rax]
0x18009cfdb  and     ecx, 0FF000000h
0x18009cfe1  neg     ecx
0x18009cfe3  sbb     edx, edx
0x18009cfe5  and     edx, 0FFFFFFFCh
0x18009cfe8  lea     ebx, [rdx+8]
0x18009cfeb  sub     ebx, [rdi+10h]
0x18009cfee  add     ebx, eax
0x18009cff0  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18009cff7  mov     [rsp+0A0h+lpOverlapped], 0; lpOverlapped
0x18009d000  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18009d004  mov     r8d, ebx; nNumberOfBytesToWrite
0x18009d007  mov     rdx, [rdi+10h]; lpBuffer
0x18009d00b  mov     rcx, rsi; hFile
0x18009d00e  call    cs:__imp_WriteFile
0x18009d014  test    eax, eax
0x18009d016  jnz     short loc_18009D068
0x18009d018  call    cs:__imp_GetLastError
0x18009d01e  test    eax, eax
0x18009d020  jle     short loc_18009D02A
0x18009d022  movzx   eax, ax
0x18009d025  or      eax, 80070000h
0x18009d02a  mov     [rbp+57h+var_68], eax
0x18009d02d  xorps   xmm0, xmm0
0x18009d030  movdqu  [rbp+57h+var_60], xmm0
0x18009d035  lea     rcx, ??_7CNLException@@6B@; const CNLException::`vftable'
0x18009d03c  mov     [rbp+57h+pExceptionObject], rcx
0x18009d040  mov     [rbp+57h+var_50], eax
0x18009d043  mov     [rbp+57h+var_40], 0
0x18009d04a  movdqu  [rbp+57h+var_38], xmm0
0x18009d04f  mov     [rbp+57h+var_28], 0
0x18009d057  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18009d05e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18009d062  call    _CxxThrowException_0
0x18009d068  cmp     [rbp+57h+NumberOfBytesWritten], ebx
0x18009d06b  jz      short loc_18009D0BD
0x18009d06d  call    cs:__imp_GetLastError
0x18009d073  test    eax, eax
0x18009d075  jle     short loc_18009D07F
0x18009d077  movzx   eax, ax
0x18009d07a  or      eax, 80070000h
0x18009d07f  mov     [rbp+57h+var_68], eax
0x18009d082  xorps   xmm0, xmm0
0x18009d085  movdqu  [rbp+57h+var_60], xmm0
0x18009d08a  lea     rcx, ??_7CNLException@@6B@; const CNLException::`vftable'
0x18009d091  mov     [rbp+57h+pExceptionObject], rcx
0x18009d095  mov     [rbp+57h+var_50], eax
0x18009d098  mov     [rbp+57h+var_40], 0
0x18009d09f  movdqu  [rbp+57h+var_38], xmm0
0x18009d0a4  mov     [rbp+57h+var_28], 0
0x18009d0ac  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18009d0b3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18009d0b7  call    _CxxThrowException_0
0x18009d0bd  cmp     byte ptr [rdi+1Eh], 0
0x18009d0c1  jz      short loc_18009D0D8
0x18009d0c3  mov     edx, [rdi+8]
0x18009d0c6  sub     edx, [rdi+30h]; lDistanceToMove
0x18009d0c9  xor     r9d, r9d; dwMoveMethod
0x18009d0cc  xor     r8d, r8d; lpDistanceToMoveHigh
0x18009d0cf  mov     rcx, rsi; hFile
0x18009d0d2  call    cs:__imp_SetFilePointer
0x18009d0d8  mov     ebx, [rdi+2Ch]
0x18009d0db  mov     r9d, 1; dwMoveMethod
0x18009d0e1  xor     r8d, r8d; lpDistanceToMoveHigh
0x18009d0e4  xor     edx, edx; lDistanceToMove
0x18009d0e6  mov     rcx, rsi; hFile
0x18009d0e9  call    cs:__imp_SetFilePointer
0x18009d0ef  sub     eax, ebx
0x18009d0f1  mov     [rdi+30h], eax
0x18009d0f4  add     rsp, 88h
0x18009d0fb  pop     rdi
0x18009d0fc  pop     rsi
0x18009d0fd  pop     rbx
0x18009d0fe  pop     rbp
0x18009d0ff  retn
```
