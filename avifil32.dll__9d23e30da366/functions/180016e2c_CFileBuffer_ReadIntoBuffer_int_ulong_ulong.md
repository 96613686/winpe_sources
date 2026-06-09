# CFileBuffer::ReadIntoBuffer(int,ulong,ulong)

- ea: `0x180016e2c`
- end: `0x180016ef9`
- name: `?ReadIntoBuffer@CFileBuffer@@AEAAHHKK@Z`
- size: `205`
- prototype: `int(CFileBuffer *__hidden this, int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180016990`
- `0x180016d20`
- `0x180016f90`

## callees

- `0x180001460`
- `0x180016e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ecc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180016e77`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180016e77`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180016ea5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180016ea5`

## pseudocode

```c
__int64 __fastcall CFileBuffer::ReadIntoBuffer(CFileBuffer *this, int a2, int a3, DWORD a4)
{
  unsigned int v8; // eax
  struct _OVERLAPPED *lpOverlapped; // rbx
  void *v10; // rcx
  void *v11; // rdx
  DWORD v12; // ecx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 >= 0 )
  {
    v8 = *((_DWORD *)this + 6);
    if ( a2 <= v8 && a4 <= v8 - a2 )
    {
      lpOverlapped = (struct _OVERLAPPED *)((char *)this + 48);
      NumberOfBytesRead = 0;
      ResetEvent(*((HANDLE *)this + 9));
      v10 = (void *)*((_QWORD *)this + 10);
      *(_DWORD *)this = 1;
      v11 = (void *)(*((_QWORD *)this + 1) + (unsigned int)a2);
      *((_DWORD *)this + 16) = a3;
      *((_DWORD *)this + 17) = 0;
      if ( ReadFile(v10, v11, a4, &NumberOfBytesRead, lpOverlapped) )
      {
        v12 = NumberOfBytesRead;
        *(_DWORD *)this = 0;
        if ( v12 == a4 || *((_DWORD *)this + 8) + v12 == *((_DWORD *)this + 10) )
          return 1;
      }
      else
      {
        if ( GetLastError() == 997 )
          return 1;
        *(_DWORD *)this = 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016e2c  push    rbx
0x180016e2e  push    rbp
0x180016e2f  push    rsi
0x180016e30  push    rdi
0x180016e31  push    r14
0x180016e33  sub     rsp, 40h
0x180016e37  mov     rax, cs:__security_cookie
0x180016e3e  xor     rax, rsp
0x180016e41  mov     [rsp+68h+var_30], rax
0x180016e46  mov     esi, edx
0x180016e48  mov     ebp, r9d
0x180016e4b  mov     r14d, r8d
0x180016e4e  mov     rdi, rcx
0x180016e51  test    edx, edx
0x180016e53  js      loc_180016EDF
0x180016e59  mov     eax, [rcx+18h]
0x180016e5c  cmp     esi, eax
0x180016e5e  ja      short loc_180016EDF
0x180016e60  sub     eax, esi
0x180016e62  cmp     r9d, eax
0x180016e65  ja      short loc_180016EDF
0x180016e67  lea     rbx, [rcx+30h]
0x180016e6b  mov     [rsp+68h+NumberOfBytesRead], 0
0x180016e73  mov     rcx, [rbx+18h]; hEvent
0x180016e77  call    cs:__imp_ResetEvent
0x180016e7d  mov     rcx, [rdi+50h]; hFile
0x180016e81  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180016e86  mov     edx, esi
0x180016e88  mov     dword ptr [rdi], 1
0x180016e8e  add     rdx, [rdi+8]; lpBuffer
0x180016e92  mov     r8d, ebp; nNumberOfBytesToRead
0x180016e95  mov     [rdi+40h], r14d
0x180016e99  mov     dword ptr [rdi+44h], 0
0x180016ea0  mov     [rsp+68h+lpOverlapped], rbx; lpOverlapped
0x180016ea5  call    cs:__imp_ReadFile
0x180016eab  test    eax, eax
0x180016ead  jz      short loc_180016ECC
0x180016eaf  mov     ecx, [rsp+68h+NumberOfBytesRead]
0x180016eb3  mov     dword ptr [rdi], 0
0x180016eb9  cmp     ecx, ebp
0x180016ebb  jz      short loc_180016EC5
0x180016ebd  add     ecx, [rdi+20h]
0x180016ec0  cmp     ecx, [rdi+28h]
0x180016ec3  jnz     short loc_180016EDF
0x180016ec5  mov     eax, 1
0x180016eca  jmp     short loc_180016EE1
0x180016ecc  call    cs:__imp_GetLastError
0x180016ed2  cmp     eax, 3E5h
0x180016ed7  jz      short loc_180016EC5
0x180016ed9  mov     dword ptr [rdi], 0
0x180016edf  xor     eax, eax
0x180016ee1  mov     rcx, [rsp+68h+var_30]
0x180016ee6  xor     rcx, rsp; StackCookie
0x180016ee9  call    __security_check_cookie
0x180016eee  add     rsp, 40h
0x180016ef2  pop     r14
0x180016ef4  pop     rdi
0x180016ef5  pop     rsi
0x180016ef6  pop     rbp
0x180016ef7  pop     rbx
0x180016ef8  retn
```
