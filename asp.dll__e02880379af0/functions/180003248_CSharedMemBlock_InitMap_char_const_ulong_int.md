# CSharedMemBlock::InitMap(char const *,ulong,int)

- ea: `0x180003248`
- end: `0x18000330b`
- name: `?InitMap@CSharedMemBlock@@QEAAJPEBDKH@Z`
- size: `195`
- prototype: `__int64 __fastcall(CSharedMemBlock *__hidden this, LPCSTR lpName, size_t Size, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002fec`
- `0x180003160`

## callees

- `0x180001c90`
- `0x180003248`
- `0x180023d86`
- `0x180049d4c`

## import_xrefs

- `KERNEL32!OpenFileMappingA` at `0x18000326a`
- `KERNEL32!OpenFileMappingA` at `0x18000326a`
- `KERNEL32!CreateFileMappingA` at `0x1800032e3`
- `KERNEL32!CreateFileMappingA` at `0x1800032e3`
- `KERNEL32!MapViewOfFile` at `0x180003293`
- `KERNEL32!MapViewOfFile` at `0x180003293`
- `KERNEL32!CloseHandle` at `0x1800253f0`
- `KERNEL32!CloseHandle` at `0x1800253f0`
- `KERNEL32!GetLastError` at `0x1800032f5`
- `KERNEL32!GetLastError` at `0x1800253d2`
- `KERNEL32!GetLastError` at `0x1800032f5`
- `KERNEL32!GetLastError` at `0x1800253d2`

## pseudocode

```c
signed int __fastcall CSharedMemBlock::InitMap(CSharedMemBlock *this, LPCSTR lpName, size_t Size, int a4)
{
  size_t v4; // rsi
  HANDLE v8; // rax
  void *v9; // rax
  signed int result; // eax
  HANDLE FileMappingA; // rax

  v4 = (unsigned int)Size;
  if ( !a4 )
  {
    v8 = OpenFileMappingA(6u, 0, lpName);
    *(_QWORD *)this = v8;
    if ( !v8 )
      return -2147467259;
    goto LABEL_3;
  }
  result = CSharedMemBlock::InitSD(this);
  if ( result < 0 )
    return result;
  FileMappingA = CreateFileMappingA(
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   (LPSECURITY_ATTRIBUTES)((char *)this + 16),
                   4u,
                   0,
                   v4,
                   lpName);
  *(_QWORD *)this = FileMappingA;
  if ( FileMappingA )
  {
    if ( GetLastError() == 183 )
    {
      CloseHandle(*(HANDLE *)this);
      result = -2147024713;
      *(_QWORD *)this = 0;
      return result;
    }
LABEL_3:
    v9 = MapViewOfFile(*(HANDLE *)this, 0xF001Fu, 0, 0, 0);
    *((_QWORD *)this + 1) = v9;
    if ( v9 )
    {
      if ( a4 )
        memset_0(v9, 0, v4);
      return 0;
    }
    CSharedMemBlock::UnInitMap(this);
    return -2147467259;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180003248  push    rbx
0x18000324a  push    rbp
0x18000324b  push    rsi
0x18000324c  push    rdi
0x18000324d  sub     rsp, 38h
0x180003251  mov     esi, r8d
0x180003254  mov     edi, r9d
0x180003257  mov     rbp, rdx
0x18000325a  mov     rbx, rcx
0x18000325d  test    r9d, r9d
0x180003260  jnz     short loc_1800032C2
0x180003262  mov     r8, rdx; lpName
0x180003265  xor     edx, edx; bInheritHandle
0x180003267  lea     ecx, [rdx+6]; dwDesiredAccess
0x18000326a  call    cs:__imp_OpenFileMappingA
0x180003270  mov     [rbx], rax
0x180003273  test    rax, rax
0x180003276  jz      loc_18002540F
0x18000327c  mov     rcx, [rbx]; hFileMappingObject
0x18000327f  xor     r9d, r9d; dwFileOffsetLow
0x180003282  xor     r8d, r8d; dwFileOffsetHigh
0x180003285  mov     [rsp+58h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18000328e  mov     edx, 0F001Fh; dwDesiredAccess
0x180003293  call    cs:__imp_MapViewOfFile
0x180003299  mov     [rbx+8], rax
0x18000329d  test    rax, rax
0x1800032a0  jz      loc_180025407
0x1800032a6  test    edi, edi
0x1800032a8  jz      short loc_1800032B7
0x1800032aa  mov     r8, rsi; Size
0x1800032ad  xor     edx, edx; Val
0x1800032af  mov     rcx, rax; void *
0x1800032b2  call    memset_0
0x1800032b7  xor     eax, eax
0x1800032b9  add     rsp, 38h
0x1800032bd  pop     rdi
0x1800032be  pop     rsi
0x1800032bf  pop     rbp
0x1800032c0  pop     rbx
0x1800032c1  retn
0x1800032c2  call    ?InitSD@CSharedMemBlock@@QEAAJXZ; CSharedMemBlock::InitSD(void)
0x1800032c7  test    eax, eax
0x1800032c9  js      short loc_1800032B9
0x1800032cb  xor     r9d, r9d; dwMaximumSizeHigh
0x1800032ce  mov     [rsp+58h+lpName], rbp; lpName
0x1800032d3  lea     rdx, [rbx+10h]; lpFileMappingAttributes
0x1800032d7  mov     dword ptr [rsp+58h+dwNumberOfBytesToMap], esi; dwMaximumSizeLow
0x1800032db  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800032df  lea     r8d, [r9+4]; flProtect
0x1800032e3  call    cs:__imp_CreateFileMappingA
0x1800032e9  mov     [rbx], rax
0x1800032ec  test    rax, rax
0x1800032ef  jz      loc_1800253D2
0x1800032f5  call    cs:__imp_GetLastError
0x1800032fb  cmp     eax, 0B7h
0x180003300  jnz     loc_18000327C
0x180003306  jmp     loc_1800253ED
0x1800253d2  call    cs:__imp_GetLastError
0x1800253d8  test    eax, eax
0x1800253da  jle     loc_1800032B9
0x1800253e0  movzx   eax, ax
0x1800253e3  or      eax, 80070000h
0x1800253e8  jmp     loc_1800032B9
0x1800253ed  mov     rcx, [rbx]; hObject
0x1800253f0  call    cs:__imp_CloseHandle
0x1800253f6  mov     eax, 800700B7h
0x1800253fb  mov     qword ptr [rbx], 0
0x180025402  jmp     loc_1800032B9
0x180025407  mov     rcx, rbx; this
0x18002540a  call    ?UnInitMap@CSharedMemBlock@@QEAAJXZ; CSharedMemBlock::UnInitMap(void)
0x18002540f  mov     eax, 80004005h
0x180025414  jmp     loc_1800032B9
```
