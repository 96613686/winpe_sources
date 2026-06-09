# CBufferedFile::Seek(long,CBufferedFile::BFILE_STATUS_FLAGS *)

- ea: `0x18003ebf0`
- end: `0x18003ecd5`
- name: `?Seek@CBufferedFile@@UEAAJJPEAW4BFILE_STATUS_FLAGS@1@@Z`
- size: `229`
- prototype: `__int64 __fastcall(CBufferedFile *__hidden this, LONG lDistanceToMove, enum CBufferedFile::BFILE_STATUS_FLAGS *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800015d0`
- `0x18003e3fc`
- `0x18003e9a4`
- `0x18003ebf0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003ec86`
- `KERNEL32!GetLastError` at `0x18003ec86`
- `KERNEL32!SetFilePointer` at `0x18003ec7b`
- `KERNEL32!SetFilePointer` at `0x18003ec7b`

## pseudocode

```c
__int64 __fastcall CBufferedFile::Seek(
        CBufferedFile *this,
        LONG lDistanceToMove,
        enum CBufferedFile::BFILE_STATUS_FLAGS *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // ecx
  unsigned __int64 v10; // rdx
  void *v11; // rcx
  LONG DistanceToMoveHigh; // [rsp+20h] [rbp-28h] BYREF

  if ( *((_QWORD *)this + 1) )
  {
    if ( *((_DWORD *)this + 19) )
      CBufferedFile::CommitBuffer(this);
    v6 = *((unsigned int *)this + 16);
    v7 = *((unsigned int *)this + 17);
    v8 = lDistanceToMove + v7 + v6;
    if ( v8 >= 0 && v8 < *((_DWORD *)this + 15) )
    {
      *((_DWORD *)this + 16) = v8;
      *((_DWORD *)this + 17) = 0;
      return 0;
    }
    if ( lDistanceToMove < 0 )
    {
      v10 = v7 + *((_QWORD *)this + 4) + v6;
      if ( (unsigned int)-lDistanceToMove > v10 )
        lDistanceToMove = -(int)v10;
    }
    v11 = (void *)*((_QWORD *)this + 1);
    DistanceToMoveHigh = 0;
    if ( SetFilePointer(v11, lDistanceToMove, &DistanceToMoveHigh, 1u) != -1 || !GetLastError() )
    {
      *((_DWORD *)this + 6) = 0;
      *((_DWORD *)this + 15) = 0;
      CBufferedFile::RefillBuffer(this, 0, 0);
      return 0;
    }
    if ( a3 )
      *(_DWORD *)a3 = 8;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18003ebf0  push    rbx
0x18003ebf2  push    rsi
0x18003ebf3  push    rdi
0x18003ebf4  sub     rsp, 30h
0x18003ebf8  mov     rax, cs:__security_cookie
0x18003ebff  xor     rax, rsp
0x18003ec02  mov     [rsp+48h+var_20], rax
0x18003ec07  cmp     qword ptr [rcx+8], 0
0x18003ec0c  mov     rsi, r8
0x18003ec0f  mov     edi, edx
0x18003ec11  mov     rbx, rcx
0x18003ec14  jz      loc_18003EC9B
0x18003ec1a  cmp     dword ptr [rcx+4Ch], 0
0x18003ec1e  jz      short loc_18003EC25
0x18003ec20  call    ?CommitBuffer@CBufferedFile@@IEAAJXZ; CBufferedFile::CommitBuffer(void)
0x18003ec25  mov     edx, [rbx+40h]
0x18003ec28  mov     r8d, [rbx+44h]
0x18003ec2c  lea     ecx, [r8+rdx]
0x18003ec30  add     ecx, edi
0x18003ec32  js      short loc_18003EC47
0x18003ec34  cmp     ecx, [rbx+3Ch]
0x18003ec37  jge     short loc_18003EC47
0x18003ec39  mov     [rbx+40h], ecx
0x18003ec3c  mov     dword ptr [rbx+44h], 0
0x18003ec43  xor     eax, eax
0x18003ec45  jmp     short loc_18003ECA0
0x18003ec47  test    edi, edi
0x18003ec49  jns     short loc_18003EC62
0x18003ec4b  mov     rcx, [rbx+20h]
0x18003ec4f  mov     eax, edi
0x18003ec51  add     rcx, r8
0x18003ec54  neg     eax
0x18003ec56  add     rdx, rcx
0x18003ec59  cmp     rax, rdx
0x18003ec5c  jbe     short loc_18003EC62
0x18003ec5e  mov     edi, edx
0x18003ec60  neg     edi
0x18003ec62  mov     rcx, [rbx+8]; hFile
0x18003ec66  lea     r8, [rsp+48h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18003ec6b  mov     r9d, 1; dwMoveMethod
0x18003ec71  mov     [rsp+48h+DistanceToMoveHigh], 0
0x18003ec79  mov     edx, edi; lDistanceToMove
0x18003ec7b  call    cs:__imp_SetFilePointer
0x18003ec81  cmp     eax, 0FFFFFFFFh
0x18003ec84  jnz     short loc_18003ECB5
0x18003ec86  call    cs:__imp_GetLastError
0x18003ec8c  test    eax, eax
0x18003ec8e  jz      short loc_18003ECB5
0x18003ec90  test    rsi, rsi
0x18003ec93  jz      short loc_18003EC9B
0x18003ec95  mov     dword ptr [rsi], 8
0x18003ec9b  mov     eax, 80004005h
0x18003eca0  mov     rcx, [rsp+48h+var_20]
0x18003eca5  xor     rcx, rsp; StackCookie
0x18003eca8  call    __security_check_cookie
0x18003ecad  add     rsp, 30h
0x18003ecb1  pop     rdi
0x18003ecb2  pop     rsi
0x18003ecb3  pop     rbx
0x18003ecb4  retn
0x18003ecb5  xor     r8d, r8d; int
0x18003ecb8  mov     dword ptr [rbx+18h], 0
0x18003ecbf  xor     edx, edx; unsigned int
0x18003ecc1  mov     dword ptr [rbx+3Ch], 0
0x18003ecc8  mov     rcx, rbx; this
0x18003eccb  call    ?RefillBuffer@CBufferedFile@@IEAAJKH@Z; CBufferedFile::RefillBuffer(ulong,int)
0x18003ecd0  jmp     loc_18003EC43
```
