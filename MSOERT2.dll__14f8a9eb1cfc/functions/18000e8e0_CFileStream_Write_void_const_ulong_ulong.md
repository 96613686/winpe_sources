# CFileStream::Write(void const *,ulong,ulong *)

- ea: `0x18000e8e0`
- end: `0x18000e92b`
- name: `?Write@CFileStream@@UEAAJPEBXKPEAK@Z`
- size: `75`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001c80`
- `0x18000e8e0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18000e903`
- `KERNEL32!WriteFile` at `0x18000e903`

## pseudocode

```c
__int64 __fastcall CFileStream::Write(CFileStream *this, const void *a2, DWORD a3, unsigned int *a4)
{
  void *v4; // rcx
  unsigned int v6; // ecx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  v4 = (void *)*((_QWORD *)this + 2);
  NumberOfBytesWritten = 0;
  if ( WriteFile(v4, a2, a3, &NumberOfBytesWritten, 0) )
  {
    v6 = 0;
    if ( a4 )
      *a4 = NumberOfBytesWritten;
  }
  else
  {
    return (unsigned int)HrGetLastError();
  }
  return v6;
}

```

## disassembly

```asm
0x18000e8e0  push    rbx
0x18000e8e2  sub     rsp, 30h
0x18000e8e6  mov     rcx, [rcx+10h]; hFile
0x18000e8ea  mov     rbx, r9
0x18000e8ed  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000e8f2  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18000e8fa  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18000e903  call    cs:__imp_WriteFile
0x18000e909  test    eax, eax
0x18000e90b  jnz     short loc_18000E916
0x18000e90d  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18000e912  mov     ecx, eax
0x18000e914  jmp     short loc_18000E923
0x18000e916  xor     ecx, ecx
0x18000e918  test    rbx, rbx
0x18000e91b  jz      short loc_18000E923
0x18000e91d  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x18000e921  mov     [rbx], eax
0x18000e923  mov     eax, ecx
0x18000e925  add     rsp, 30h
0x18000e929  pop     rbx
0x18000e92a  retn
```
