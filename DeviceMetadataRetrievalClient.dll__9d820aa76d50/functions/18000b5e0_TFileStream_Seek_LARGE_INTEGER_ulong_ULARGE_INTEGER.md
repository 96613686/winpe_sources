# TFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x18000b5e0`
- end: `0x18000b644`
- name: `?Seek@TFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `100`
- prototype: `int(TFileStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000b5e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b627`
- `KERNEL32!GetLastError` at `0x18000b627`
- `KERNEL32!SetFilePointerEx` at `0x18000b61d`
- `KERNEL32!SetFilePointerEx` at `0x18000b61d`

## pseudocode

```c
__int64 __fastcall TFileStream::Seek(HANDLE *this, LARGE_INTEGER a2, int a3, LARGE_INTEGER *a4)
{
  int v5; // r8d
  DWORD v7; // r9d
  unsigned int v8; // ebx
  signed int LastError; // eax

  if ( a3 )
  {
    v5 = a3 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
        return 2147680257LL;
      v7 = 2;
    }
    else
    {
      v7 = 1;
    }
  }
  else
  {
    v7 = 0;
  }
  v8 = 0;
  if ( !SetFilePointerEx(this[1], a2, a4, v7) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x18000b5e0  push    rbx
0x18000b5e2  sub     rsp, 20h
0x18000b5e6  mov     rax, r9
0x18000b5e9  test    r8d, r8d
0x18000b5ec  jz      short loc_18000B611
0x18000b5ee  sub     r8d, 1
0x18000b5f2  jz      short loc_18000B609
0x18000b5f4  cmp     r8d, 1
0x18000b5f8  jz      short loc_18000B601
0x18000b5fa  mov     eax, 80030001h
0x18000b5ff  jmp     short loc_18000B63E
0x18000b601  mov     r9d, 2
0x18000b607  jmp     short loc_18000B614
0x18000b609  mov     r9d, 1
0x18000b60f  jmp     short loc_18000B614
0x18000b611  xor     r9d, r9d; dwMoveMethod
0x18000b614  mov     rcx, [rcx+8]; hFile
0x18000b618  mov     r8, rax; lpNewFilePointer
0x18000b61b  xor     ebx, ebx
0x18000b61d  call    cs:__imp_SetFilePointerEx
0x18000b623  test    eax, eax
0x18000b625  jnz     short loc_18000B63C
0x18000b627  call    cs:__imp_GetLastError
0x18000b62d  mov     ebx, eax
0x18000b62f  test    eax, eax
0x18000b631  jle     short loc_18000B63C
0x18000b633  movzx   ebx, ax
0x18000b636  or      ebx, 80070000h
0x18000b63c  mov     eax, ebx
0x18000b63e  add     rsp, 20h
0x18000b642  pop     rbx
0x18000b643  retn
```
