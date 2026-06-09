# CBufferedFile::CommitBuffer(void)

- ea: `0x18003e3fc`
- end: `0x18003e522`
- name: `?CommitBuffer@CBufferedFile@@IEAAJXZ`
- size: `294`
- prototype: `__int64 __fastcall(CBufferedFile *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003e3a0`
- `0x18003e9a4`
- `0x18003eb70`
- `0x18003ebf0`
- `0x18003ece0`
- `0x18003edf0`

## callees

- `0x1800015d0`
- `0x18003e3fc`

## import_xrefs

- `KERNEL32!FlushFileBuffers` at `0x18003e4fa`
- `KERNEL32!FlushFileBuffers` at `0x18003e4fa`
- `KERNEL32!WriteFile` at `0x18003e49a`
- `KERNEL32!WriteFile` at `0x18003e49a`
- `KERNEL32!GetLastError` at `0x18003e465`
- `KERNEL32!GetLastError` at `0x18003e4a4`
- `KERNEL32!GetLastError` at `0x18003e4de`
- `KERNEL32!GetLastError` at `0x18003e465`
- `KERNEL32!GetLastError` at `0x18003e4a4`
- `KERNEL32!GetLastError` at `0x18003e4de`
- `KERNEL32!SetFilePointer` at `0x18003e45a`
- `KERNEL32!SetFilePointer` at `0x18003e4d3`
- `KERNEL32!SetFilePointer` at `0x18003e45a`
- `KERNEL32!SetFilePointer` at `0x18003e4d3`

## pseudocode

```c
__int64 __fastcall CBufferedFile::CommitBuffer(CBufferedFile *this)
{
  __int64 v3; // rdi
  __int64 v4; // rbp
  __int64 v5; // rsi
  __int64 v6; // r14
  void *v7; // rcx
  const void *v8; // rdx
  DWORD v9; // r8d
  unsigned __int64 v10; // rdi
  void *v11; // rcx
  __int64 v12; // rax
  void *v13; // rcx
  void *v14; // rcx
  LONG DistanceToMoveHigh; // [rsp+30h] [rbp-28h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-24h] BYREF

  if ( !*((_DWORD *)this + 19) )
    return 1;
  v3 = *((_QWORD *)this + 4);
  v4 = *((unsigned int *)this + 15);
  v5 = v3 + *((unsigned int *)this + 18);
  v6 = *((unsigned int *)this + 10);
  v7 = (void *)*((_QWORD *)this + 1);
  DistanceToMoveHigh = HIDWORD(v5);
  if ( SetFilePointer(v7, v5, &DistanceToMoveHigh, 0) == -1 && GetLastError() )
    return 2147500037LL;
  v8 = (const void *)(*((_QWORD *)this + 6) + *((unsigned int *)this + 18));
  v9 = *((_DWORD *)this + 19);
  v10 = v4 - v6 + v3;
  v11 = (void *)*((_QWORD *)this + 1);
  NumberOfBytesWritten = 0;
  if ( !WriteFile(v11, v8, v9, &NumberOfBytesWritten, 0) )
    GetLastError();
  v12 = NumberOfBytesWritten;
  *((_DWORD *)this + 10) -= NumberOfBytesWritten;
  if ( v5 + v12 < v10 )
  {
    v13 = (void *)*((_QWORD *)this + 1);
    DistanceToMoveHigh = HIDWORD(v10);
    if ( SetFilePointer(v13, v10, &DistanceToMoveHigh, 0) == -1 )
    {
      if ( GetLastError() )
        return 2147500037LL;
    }
  }
  v14 = (void *)*((_QWORD *)this + 1);
  *((_DWORD *)this + 19) = 0;
  FlushFileBuffers(v14);
  return 0;
}

```

## disassembly

```asm
0x18003e3fc  mov     [rsp+arg_8], rbx
0x18003e401  mov     [rsp+arg_10], rbp
0x18003e406  push    rsi
0x18003e407  push    rdi
0x18003e408  push    r14
0x18003e40a  sub     rsp, 40h
0x18003e40e  mov     rax, cs:__security_cookie
0x18003e415  xor     rax, rsp
0x18003e418  mov     [rsp+58h+var_20], rax
0x18003e41d  cmp     dword ptr [rcx+4Ch], 0
0x18003e421  mov     rbx, rcx
0x18003e424  jnz     short loc_18003E430
0x18003e426  mov     eax, 1
0x18003e42b  jmp     loc_18003E502
0x18003e430  mov     rdi, [rcx+20h]
0x18003e434  lea     r8, [rsp+58h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18003e439  mov     esi, [rcx+48h]
0x18003e43c  xor     r9d, r9d; dwMoveMethod
0x18003e43f  mov     ebp, [rcx+3Ch]
0x18003e442  add     rsi, rdi
0x18003e445  mov     r14d, [rcx+28h]
0x18003e449  mov     rax, rsi
0x18003e44c  mov     rcx, [rcx+8]; hFile
0x18003e450  mov     edx, esi; lDistanceToMove
0x18003e452  shr     rax, 20h
0x18003e456  mov     [rsp+58h+DistanceToMoveHigh], eax
0x18003e45a  call    cs:__imp_SetFilePointer
0x18003e460  cmp     eax, 0FFFFFFFFh
0x18003e463  jnz     short loc_18003E46F
0x18003e465  call    cs:__imp_GetLastError
0x18003e46b  test    eax, eax
0x18003e46d  jnz     short loc_18003E4E8
0x18003e46f  mov     edx, [rbx+48h]
0x18003e472  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003e477  add     rdx, [rbx+30h]; lpBuffer
0x18003e47b  sub     rbp, r14
0x18003e47e  mov     r8d, [rbx+4Ch]; nNumberOfBytesToWrite
0x18003e482  add     rdi, rbp
0x18003e485  mov     rcx, [rbx+8]; hFile
0x18003e489  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18003e491  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18003e49a  call    cs:__imp_WriteFile
0x18003e4a0  test    eax, eax
0x18003e4a2  jnz     short loc_18003E4AA
0x18003e4a4  call    cs:__imp_GetLastError
0x18003e4aa  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x18003e4ae  sub     [rbx+28h], eax
0x18003e4b1  lea     rcx, [rsi+rax]
0x18003e4b5  cmp     rcx, rdi
0x18003e4b8  jnb     short loc_18003E4EF
0x18003e4ba  mov     rcx, [rbx+8]; hFile
0x18003e4be  lea     r8, [rsp+58h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18003e4c3  mov     rax, rdi
0x18003e4c6  mov     edx, edi; lDistanceToMove
0x18003e4c8  shr     rax, 20h
0x18003e4cc  xor     r9d, r9d; dwMoveMethod
0x18003e4cf  mov     [rsp+58h+DistanceToMoveHigh], eax
0x18003e4d3  call    cs:__imp_SetFilePointer
0x18003e4d9  cmp     eax, 0FFFFFFFFh
0x18003e4dc  jnz     short loc_18003E4EF
0x18003e4de  call    cs:__imp_GetLastError
0x18003e4e4  test    eax, eax
0x18003e4e6  jz      short loc_18003E4EF
0x18003e4e8  mov     eax, 80004005h
0x18003e4ed  jmp     short loc_18003E502
0x18003e4ef  mov     rcx, [rbx+8]; hFile
0x18003e4f3  mov     dword ptr [rbx+4Ch], 0
0x18003e4fa  call    cs:__imp_FlushFileBuffers
0x18003e500  xor     eax, eax
0x18003e502  mov     rcx, [rsp+58h+var_20]
0x18003e507  xor     rcx, rsp; StackCookie
0x18003e50a  call    __security_check_cookie
0x18003e50f  mov     rbx, [rsp+58h+arg_8]
0x18003e514  mov     rbp, [rsp+58h+arg_10]
0x18003e519  add     rsp, 40h
0x18003e51d  pop     r14
0x18003e51f  pop     rdi
0x18003e520  pop     rsi
0x18003e521  retn
```
