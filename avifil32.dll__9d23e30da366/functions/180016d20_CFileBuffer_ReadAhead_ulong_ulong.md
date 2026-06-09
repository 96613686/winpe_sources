# CFileBuffer::ReadAhead(ulong,ulong)

- ea: `0x180016d20`
- end: `0x180016e25`
- name: `?ReadAhead@CFileBuffer@@QEAAXKK@Z`
- size: `261`
- prototype: `void __fastcall(CFileBuffer *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800091d0`
- `0x180016a94`

## callees

- `0x180001460`
- `0x1800163d4`
- `0x18001692c`
- `0x180016d20`
- `0x180016e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016db0`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180016d6c`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180016d6c`

## pseudocode

```c
void __fastcall CFileBuffer::ReadAhead(CFileBuffer *this, unsigned int a2, unsigned int a3)
{
  unsigned __int64 v4; // rsi
  unsigned __int64 v6; // rcx
  int v7; // r8d
  DWORD v8; // r9d
  DWORD NumberOfBytesTransferred; // [rsp+20h] [rbp-18h] BYREF

  v4 = a2;
  if ( *(_DWORD *)this )
  {
    if ( *(_DWORD *)this != 1 )
      return;
    NumberOfBytesTransferred = 0;
    if ( GetOverlappedResult(*((HANDLE *)this + 10), (LPOVERLAPPED)((char *)this + 48), &NumberOfBytesTransferred, 0) )
    {
      if ( NumberOfBytesTransferred == *((_DWORD *)this + 7)
        || *((_DWORD *)this + 8) + NumberOfBytesTransferred == *((_DWORD *)this + 10) )
      {
        *(_DWORD *)this = 0;
        goto LABEL_7;
      }
    }
    else if ( GetLastError() == 996 )
    {
      return;
    }
    *(_DWORD *)this = 3;
    return;
  }
LABEL_7:
  if ( !(unsigned int)CFileBuffer::QueryPosition(this, v4, a3) )
  {
    *((_DWORD *)this + 10) = a3;
    if ( *((_DWORD *)this + 1) )
    {
      CFileBuffer::Commit((HANDLE *)this);
    }
    else
    {
      v6 = *((unsigned int *)this + 9);
      v7 = v4 - v4 % v6;
      *((_DWORD *)this + 8) = v7;
      v8 = a3 - v7 + v6 - 1 - (a3 - v7 + v6 - 1) % v6;
      if ( v8 >= *((_DWORD *)this + 6) )
        v8 = *((_DWORD *)this + 6);
      *((_DWORD *)this + 7) = v8;
      CFileBuffer::ReadIntoBuffer(this, 0, v7, v8);
    }
  }
}

```

## disassembly

```asm
0x180016d20  mov     [rsp+arg_8], rbx
0x180016d25  mov     [rsp+arg_18], rsi
0x180016d2a  push    rdi
0x180016d2b  sub     rsp, 30h
0x180016d2f  mov     rax, cs:__security_cookie
0x180016d36  xor     rax, rsp
0x180016d39  mov     [rsp+38h+var_10], rax
0x180016d3e  cmp     dword ptr [rcx], 0
0x180016d41  mov     edi, r8d
0x180016d44  mov     esi, edx
0x180016d46  mov     rbx, rcx
0x180016d49  jz      short loc_180016D8D
0x180016d4b  cmp     dword ptr [rcx], 1
0x180016d4e  jnz     loc_180016E08
0x180016d54  lea     rdx, [rcx+30h]; lpOverlapped
0x180016d58  mov     [rsp+38h+NumberOfBytesTransferred], 0
0x180016d60  mov     rcx, [rcx+50h]; hFile
0x180016d64  lea     r8, [rsp+38h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180016d69  xor     r9d, r9d; bWait
0x180016d6c  call    cs:__imp_GetOverlappedResult
0x180016d72  test    eax, eax
0x180016d74  jz      short loc_180016DB0
0x180016d76  mov     ecx, [rsp+38h+NumberOfBytesTransferred]
0x180016d7a  cmp     ecx, [rbx+1Ch]
0x180016d7d  jz      short loc_180016D87
0x180016d7f  add     ecx, [rbx+20h]
0x180016d82  cmp     ecx, [rbx+28h]
0x180016d85  jnz     short loc_180016DBD
0x180016d87  mov     dword ptr [rbx], 0
0x180016d8d  mov     r8d, edi; unsigned int
0x180016d90  mov     edx, esi; unsigned int
0x180016d92  mov     rcx, rbx; this
0x180016d95  call    ?QueryPosition@CFileBuffer@@QEAAHKK@Z; CFileBuffer::QueryPosition(ulong,ulong)
0x180016d9a  test    eax, eax
0x180016d9c  jnz     short loc_180016E08
0x180016d9e  mov     [rbx+28h], edi
0x180016da1  cmp     [rbx+4], eax
0x180016da4  jz      short loc_180016DC5
0x180016da6  mov     rcx, rbx; this
0x180016da9  call    ?Commit@CFileBuffer@@QEAAHXZ; CFileBuffer::Commit(void)
0x180016dae  jmp     short loc_180016E08
0x180016db0  call    cs:__imp_GetLastError
0x180016db6  cmp     eax, 3E4h
0x180016dbb  jz      short loc_180016E08
0x180016dbd  mov     dword ptr [rbx], 3
0x180016dc3  jmp     short loc_180016E08
0x180016dc5  mov     ecx, [rbx+24h]
0x180016dc8  xor     edx, edx
0x180016dca  mov     rax, rsi
0x180016dcd  mov     r8, rsi
0x180016dd0  div     rcx
0x180016dd3  lea     r9, [rcx-1]
0x180016dd7  sub     r8d, edx; unsigned int
0x180016dda  xor     edx, edx
0x180016ddc  sub     edi, r8d
0x180016ddf  mov     [rbx+20h], r8d
0x180016de3  mov     eax, edi
0x180016de5  add     r9, rax
0x180016de8  mov     rax, r9
0x180016deb  div     rcx
0x180016dee  mov     rcx, rbx; this
0x180016df1  sub     r9d, edx
0x180016df4  cmp     r9d, [rbx+18h]
0x180016df8  cmovnb  r9d, [rbx+18h]; unsigned int
0x180016dfd  xor     edx, edx; int
0x180016dff  mov     [rbx+1Ch], r9d
0x180016e03  call    ?ReadIntoBuffer@CFileBuffer@@AEAAHHKK@Z; CFileBuffer::ReadIntoBuffer(int,ulong,ulong)
0x180016e08  mov     rcx, [rsp+38h+var_10]
0x180016e0d  xor     rcx, rsp; StackCookie
0x180016e10  call    __security_check_cookie
0x180016e15  mov     rbx, [rsp+38h+arg_8]
0x180016e1a  mov     rsi, [rsp+38h+arg_18]
0x180016e1f  add     rsp, 30h
0x180016e23  pop     rdi
0x180016e24  retn
```
