# CFileBuffer::WaitComplete(void)

- ea: `0x180016f00`
- end: `0x180016f87`
- name: `?WaitComplete@CFileBuffer@@QEAAHXZ`
- size: `135`
- prototype: `__int64 __fastcall(CFileBuffer *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016498`
- `0x1800166ec`
- `0x180016990`
- `0x180016a94`
- `0x180016f90`
- `0x180017170`

## callees

- `0x180001460`
- `0x180016f00`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180016f47`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180016f47`

## pseudocode

```c
__int64 __fastcall CFileBuffer::WaitComplete(CFileBuffer *this)
{
  unsigned int v3; // edi
  struct _OVERLAPPED *v4; // rdx
  void *v5; // rcx
  DWORD NumberOfBytesTransferred; // [rsp+20h] [rbp-18h] BYREF

  if ( *(_DWORD *)this == 3 )
  {
    *(_DWORD *)this = 0;
    return 0;
  }
  if ( *(_DWORD *)this != 1 )
    return 1;
  v3 = 0;
  v4 = (struct _OVERLAPPED *)((char *)this + 48);
  *(_DWORD *)this = 0;
  v5 = (void *)*((_QWORD *)this + 10);
  NumberOfBytesTransferred = 0;
  if ( !GetOverlappedResult(v5, v4, &NumberOfBytesTransferred, 1) )
    return 0;
  if ( NumberOfBytesTransferred == *((_DWORD *)this + 7) )
    return 1;
  LOBYTE(v3) = NumberOfBytesTransferred + *((_DWORD *)this + 8) == *((_DWORD *)this + 10);
  return v3;
}

```

## disassembly

```asm
0x180016f00  mov     [rsp+arg_8], rbx
0x180016f05  push    rdi
0x180016f06  sub     rsp, 30h
0x180016f0a  mov     rax, cs:__security_cookie
0x180016f11  xor     rax, rsp
0x180016f14  mov     [rsp+38h+var_10], rax
0x180016f19  cmp     dword ptr [rcx], 3
0x180016f1c  mov     rbx, rcx
0x180016f1f  jnz     short loc_180016F29
0x180016f21  xor     edi, edi
0x180016f23  mov     [rcx], edi
0x180016f25  xor     eax, eax
0x180016f27  jmp     short loc_180016F6F
0x180016f29  cmp     dword ptr [rcx], 1
0x180016f2c  jnz     short loc_180016F6A
0x180016f2e  xor     edi, edi
0x180016f30  lea     rdx, [rcx+30h]; lpOverlapped
0x180016f34  mov     [rcx], edi
0x180016f36  lea     r8, [rsp+38h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180016f3b  mov     rcx, [rcx+50h]; hFile
0x180016f3f  mov     [rsp+38h+NumberOfBytesTransferred], edi
0x180016f43  lea     r9d, [rdi+1]; bWait
0x180016f47  call    cs:__imp_GetOverlappedResult
0x180016f4d  test    eax, eax
0x180016f4f  jz      short loc_180016F25
0x180016f51  mov     eax, [rsp+38h+NumberOfBytesTransferred]
0x180016f55  cmp     eax, [rbx+1Ch]
0x180016f58  jz      short loc_180016F6A
0x180016f5a  mov     edx, [rbx+20h]
0x180016f5d  add     edx, eax
0x180016f5f  cmp     edx, [rbx+28h]
0x180016f62  setz    dil
0x180016f66  mov     eax, edi
0x180016f68  jmp     short loc_180016F6F
0x180016f6a  mov     eax, 1
0x180016f6f  mov     rcx, [rsp+38h+var_10]
0x180016f74  xor     rcx, rsp; StackCookie
0x180016f77  call    __security_check_cookie
0x180016f7c  mov     rbx, [rsp+38h+arg_8]
0x180016f81  add     rsp, 30h
0x180016f85  pop     rdi
0x180016f86  retn
```
