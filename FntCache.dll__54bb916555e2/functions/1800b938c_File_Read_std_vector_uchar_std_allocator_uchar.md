# File::Read(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800b938c`
- end: `0x1800b93df`
- name: `?Read@File@@QEAA_KAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800a3dc0`

## callees

- `0x18009e420`
- `0x1800a1558`
- `0x1800b938c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b93c6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b93c6`

## pseudocode

```c
__int64 __fastcall File::Read(HANDLE *a1, __int64 a2, __int64 a3, __int64 a4)
{
  void *v4; // rax
  unsigned __int64 v5; // r8
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp+10h] BYREF

  v4 = *(void **)a2;
  v5 = *(_QWORD *)(a2 + 8) - *(_QWORD *)a2;
  NumberOfBytesRead = 0;
  if ( v5 > 0xFFFFFFFF )
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(a1, 0xFFFFFFFFLL, v5, a4);
  if ( !ReadFile(*a1, v4, v5, &NumberOfBytesRead, 0) )
    OSException::ThrowLastError();
  return NumberOfBytesRead;
}

```

## disassembly

```asm
0x1800b938c  sub     rsp, 38h
0x1800b9390  mov     rax, [rdx]
0x1800b9393  mov     r8, [rdx+8]
0x1800b9397  mov     edx, 0FFFFFFFFh
0x1800b939c  sub     r8, rax; nNumberOfBytesToRead
0x1800b939f  mov     [rsp+38h+NumberOfBytesRead], 0
0x1800b93a7  cmp     r8, rdx
0x1800b93aa  jbe     short loc_1800B93B2
0x1800b93ac  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x1800b93b2  mov     rcx, [rcx]; hFile
0x1800b93b5  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800b93ba  mov     rdx, rax; lpBuffer
0x1800b93bd  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800b93c6  call    cs:__imp_ReadFile
0x1800b93cc  test    eax, eax
0x1800b93ce  jnz     short loc_1800B93D6
0x1800b93d0  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x1800b93d6  mov     eax, [rsp+38h+NumberOfBytesRead]
0x1800b93da  add     rsp, 38h
0x1800b93de  retn
```
