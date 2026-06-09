# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x180001010`
- end: `0x18000105a`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `74`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001010`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180001031`
- `KERNEL32!ReadFile` at `0x180001031`

## pseudocode

```c
__int64 __fastcall CFileStream::Read(CFileStream *this, void *a2, DWORD a3, unsigned int *a4)
{
  void *v4; // rcx
  __int64 result; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  v4 = (void *)*((_QWORD *)this + 2);
  NumberOfBytesRead = 0;
  if ( !ReadFile(v4, a2, a3, &NumberOfBytesRead, 0) )
    return 2147500037LL;
  result = 0;
  if ( a4 )
    *a4 = NumberOfBytesRead;
  return result;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_8], rbx
0x180001015  push    rdi
0x180001016  sub     rsp, 30h
0x18000101a  mov     rcx, [rcx+10h]; hFile
0x18000101e  mov     rbx, r9
0x180001021  xor     edi, edi
0x180001023  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180001028  mov     [rsp+38h+NumberOfBytesRead], edi
0x18000102c  mov     [rsp+38h+lpOverlapped], rdi; lpOverlapped
0x180001031  call    cs:__imp_ReadFile
0x180001037  test    eax, eax
0x180001039  jz      short loc_180001053
0x18000103b  mov     eax, edi
0x18000103d  test    rbx, rbx
0x180001040  jz      short loc_180001048
0x180001042  mov     ecx, [rsp+38h+NumberOfBytesRead]
0x180001046  mov     [rbx], ecx
0x180001048  mov     rbx, [rsp+38h+arg_8]
0x18000104d  add     rsp, 30h
0x180001051  pop     rdi
0x180001052  retn
0x180001053  mov     eax, 80004005h
0x180001058  jmp     short loc_180001048
```
