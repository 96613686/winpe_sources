# CFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x180001060`
- end: `0x1800010df`
- name: `?Seek@CFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001060`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000109a`
- `KERNEL32!GetLastError` at `0x18000109a`
- `KERNEL32!SetFilePointerEx` at `0x180001083`
- `KERNEL32!SetFilePointerEx` at `0x180001083`

## pseudocode

```c
signed int __fastcall CFileStream::Seek(HANDLE *this, LARGE_INTEGER a2, int a3, union _ULARGE_INTEGER *a4)
{
  DWORD v5; // r9d
  signed int result; // eax
  int v7; // r8d
  LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF

  NewFilePointer.QuadPart = 0;
  if ( a3 )
  {
    v7 = a3 - 1;
    if ( v7 )
    {
      if ( v7 != 1 )
        return -2147024809;
      v5 = 2;
    }
    else
    {
      v5 = 1;
    }
  }
  else
  {
    v5 = 0;
  }
  if ( SetFilePointerEx(this[2], a2, &NewFilePointer, v5) )
  {
    if ( a4 )
      *a4 = (union _ULARGE_INTEGER)NewFilePointer.QuadPart;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180001060  push    rbx
0x180001062  sub     rsp, 30h
0x180001066  mov     qword ptr [rsp+38h+NewFilePointer], 0
0x18000106f  mov     rbx, r9
0x180001072  test    r8d, r8d
0x180001075  jnz     short loc_1800010AE
0x180001077  xor     r9d, r9d; dwMoveMethod
0x18000107a  mov     rcx, [rcx+10h]; hFile
0x18000107e  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x180001083  call    cs:__imp_SetFilePointerEx
0x180001089  test    eax, eax
0x18000108b  jz      short loc_18000109A
0x18000108d  test    rbx, rbx
0x180001090  jnz     short loc_1800010D5
0x180001092  xor     eax, eax
0x180001094  add     rsp, 30h
0x180001098  pop     rbx
0x180001099  retn
0x18000109a  call    cs:__imp_GetLastError
0x1800010a0  test    eax, eax
0x1800010a2  jle     short loc_180001094
0x1800010a4  movzx   eax, ax
0x1800010a7  or      eax, 80070000h
0x1800010ac  jmp     short loc_180001094
0x1800010ae  sub     r8d, 1
0x1800010b2  jz      short loc_1800010CD
0x1800010b4  cmp     r8d, 1
0x1800010b8  jz      short loc_1800010C5
0x1800010ba  mov     eax, 80070057h
0x1800010bf  add     rsp, 30h
0x1800010c3  pop     rbx
0x1800010c4  retn
0x1800010c5  mov     r9d, 2
0x1800010cb  jmp     short loc_18000107A
0x1800010cd  mov     r9d, 1
0x1800010d3  jmp     short loc_18000107A
0x1800010d5  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x1800010da  mov     [rbx], rax
0x1800010dd  jmp     short loc_180001092
```
