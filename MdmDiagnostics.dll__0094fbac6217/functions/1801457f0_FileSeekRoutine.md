# FileSeekRoutine

- ea: `0x1801457f0`
- end: `0x180145888`
- name: `FileSeekRoutine`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1801457f0`
- `0x1801595f4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18014582c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18014582c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145836`

## pseudocode

```c
__int64 __fastcall FileSeekRoutine(void *a1, LARGE_INTEGER a2, int a3, union _LARGE_INTEGER *a4)
{
  DWORD v5; // r9d
  signed int LastError; // eax
  unsigned int v7; // r10d
  __int64 v8; // rdx
  unsigned int v9; // r10d
  union _LARGE_INTEGER NewFilePointer; // [rsp+40h] [rbp+8h] BYREF

  NewFilePointer.QuadPart = 0;
  if ( !a1 )
    goto LABEL_15;
  if ( !a3 )
  {
    v5 = 0;
    goto LABEL_6;
  }
  v5 = 1;
  if ( a3 != 1 )
  {
    v5 = 2;
    if ( a3 != 2 )
    {
LABEL_15:
      v8 = 2147942487LL;
      goto LABEL_16;
    }
  }
LABEL_6:
  if ( !SetFilePointerEx(a1, a2, &NewFilePointer, v5) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_9;
  }
  if ( a4 )
  {
    if ( NewFilePointer.QuadPart < 0 )
    {
      v7 = -2147418113;
LABEL_9:
      v8 = v7;
LABEL_16:
      LogErrorFxn(a1, v8);
      return v9;
    }
    *a4 = NewFilePointer;
  }
  return 0;
}

```

## disassembly

```asm
0x1801457f0  push    rbx
0x1801457f2  sub     rsp, 30h
0x1801457f6  mov     qword ptr [rsp+38h+NewFilePointer], 0
0x1801457ff  mov     rbx, r9
0x180145802  test    rcx, rcx
0x180145805  jz      short loc_180145872
0x180145807  test    r8d, r8d
0x18014580a  jnz     short loc_180145811
0x18014580c  xor     r9d, r9d
0x18014580f  jmp     short loc_180145827
0x180145811  mov     r9d, 1
0x180145817  cmp     r8d, r9d
0x18014581a  jz      short loc_180145827
0x18014581c  mov     r9d, 2; dwMoveMethod
0x180145822  cmp     r8d, r9d
0x180145825  jnz     short loc_180145872
0x180145827  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x18014582c  call    cs:__imp_SetFilePointerEx
0x180145832  test    eax, eax
0x180145834  jnz     short loc_180145853
0x180145836  call    cs:__imp_GetLastError
0x18014583c  mov     r10d, eax
0x18014583f  test    eax, eax
0x180145841  jle     short loc_18014584E
0x180145843  movzx   r10d, ax
0x180145847  or      r10d, 80070000h
0x18014584e  mov     edx, r10d
0x180145851  jmp     short loc_18014587A
0x180145853  test    rbx, rbx
0x180145856  jz      short loc_18014586D
0x180145858  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x18014585d  test    rax, rax
0x180145860  jns     short loc_18014586A
0x180145862  mov     r10d, 8000FFFFh
0x180145868  jmp     short loc_18014584E
0x18014586a  mov     [rbx], rax
0x18014586d  xor     r10d, r10d
0x180145870  jmp     short loc_18014587F
0x180145872  mov     edx, 80070057h
0x180145877  mov     r10d, edx
0x18014587a  call    LogErrorFxn
0x18014587f  mov     eax, r10d
0x180145882  add     rsp, 30h
0x180145886  pop     rbx
0x180145887  retn
```
