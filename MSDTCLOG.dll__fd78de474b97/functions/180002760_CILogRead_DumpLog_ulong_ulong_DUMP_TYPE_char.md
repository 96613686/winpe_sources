# CILogRead::DumpLog(ulong,ulong,_DUMP_TYPE,char *)

- ea: `0x180002760`
- end: `0x1800028f7`
- name: `?DumpLog@CILogRead@@UEAAJKKW4_DUMP_TYPE@@PEAD@Z`
- size: `407`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, unsigned int, int, LPCSTR lpFileName)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x18000130c`
- `0x180002760`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002895`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000288b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000288b`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800027de`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800027de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800028ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800028ba`
- `msvcrt!puts` at `0x1800028c7`
- `msvcrt!puts` at `0x1800028c7`

## pseudocode

```c
__int64 __fastcall CILogRead::DumpLog(_QWORD *a1, unsigned int a2, unsigned int a3, int a4, LPCSTR lpFileName)
{
  unsigned int v7; // ebp
  unsigned int v9; // edx
  HANDLE FileA; // rsi
  signed int LastError; // eax
  unsigned int v12; // ebx
  void *v13; // r14
  signed int v14; // eax
  DWORD nNumberOfBytesToWrite; // [rsp+78h] [rbp+10h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF

  v7 = a3;
  v9 = *(_DWORD *)(a1[2] + 292LL);
  if ( a3 == -1 && a2 )
    v7 = *(_DWORD *)(a1[2] + 292LL);
  if ( a2 > v7 || a2 > v9 || v7 > v9 )
    return 2147942487LL;
  FileA = 0;
  if ( lpFileName && (FileA = CreateFileA(lpFileName, 0x40000000u, 0, 0, 4u, 0x80u, 0), FileA == (HANDLE)-1LL) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v13 = operator new[](0xA230u);
    if ( v13 )
    {
      nNumberOfBytesToWrite = 0;
      NumberOfBytesWritten = 0;
      do
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD *, void *, __int64, _QWORD, int, DWORD *))(*a1 + 88LL))(
                a1,
                v13,
                41520,
                a2,
                a4,
                &nNumberOfBytesToWrite);
        if ( v12 )
          break;
        if ( FileA )
        {
          if ( !WriteFile(FileA, v13, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
          {
            v14 = GetLastError();
            v12 = v14;
            if ( v14 > 0 )
              v12 = (unsigned __int16)v14 | 0x80070000;
            break;
          }
        }
        else
        {
          puts((const char *)v13);
        }
        ++a2;
      }
      while ( a2 <= v7 );
      operator delete(v13);
    }
    else
    {
      v12 = -2147024882;
    }
    if ( FileA )
      CloseHandle(FileA);
  }
  return v12;
}

```

## disassembly

```asm
0x180002760  mov     [rsp+arg_0], rbx
0x180002765  mov     [rsp+arg_18], rbp
0x18000276a  push    rsi
0x18000276b  push    rdi
0x18000276c  push    r12
0x18000276e  push    r14
0x180002770  push    r15
0x180002772  sub     rsp, 40h
0x180002776  mov     rax, [rcx+10h]
0x18000277a  mov     edi, edx
0x18000277c  mov     r12d, r9d
0x18000277f  mov     ebp, r8d
0x180002782  mov     r15, rcx
0x180002785  mov     edx, [rax+124h]
0x18000278b  cmp     r8d, 0FFFFFFFFh
0x18000278f  jnz     short loc_180002797
0x180002791  test    edi, edi
0x180002793  jz      short loc_180002797
0x180002795  mov     ebp, edx
0x180002797  cmp     edi, ebp
0x180002799  ja      loc_1800028D9
0x18000279f  cmp     edi, edx
0x1800027a1  ja      loc_1800028D9
0x1800027a7  cmp     ebp, edx
0x1800027a9  ja      loc_1800028D9
0x1800027af  mov     rcx, [rsp+68h+lpFileName]; lpFileName
0x1800027b7  xor     esi, esi
0x1800027b9  test    rcx, rcx
0x1800027bc  jz      short loc_18000280B
0x1800027be  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x1800027c3  xor     r9d, r9d; lpSecurityAttributes
0x1800027c6  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800027ce  xor     r8d, r8d; dwShareMode
0x1800027d1  mov     edx, 40000000h; dwDesiredAccess
0x1800027d6  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x1800027de  call    cs:__imp_CreateFileA
0x1800027e4  mov     rsi, rax
0x1800027e7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800027eb  jnz     short loc_18000280B
0x1800027ed  call    cs:__imp_GetLastError
0x1800027f3  mov     ebx, eax
0x1800027f5  test    eax, eax
0x1800027f7  jle     loc_1800028C0
0x1800027fd  movzx   ebx, ax
0x180002800  or      ebx, 80070000h
0x180002806  jmp     loc_1800028C0
0x18000280b  mov     ecx, 0A230h; unsigned __int64
0x180002810  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002815  mov     r14, rax
0x180002818  test    rax, rax
0x18000281b  jnz     short loc_180002827
0x18000281d  mov     ebx, 8007000Eh
0x180002822  jmp     loc_1800028B2
0x180002827  mov     [rsp+68h+nNumberOfBytesToWrite], 0
0x18000282f  mov     [rsp+68h+NumberOfBytesWritten], 0
0x18000283a  mov     rax, [r15]
0x18000283d  lea     rcx, [rsp+68h+nNumberOfBytesToWrite]
0x180002842  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rcx
0x180002847  mov     r9d, edi
0x18000284a  mov     r8d, 0A230h
0x180002850  mov     [rsp+68h+dwCreationDisposition], r12d
0x180002855  mov     rdx, r14
0x180002858  mov     rcx, r15
0x18000285b  mov     rax, [rax+58h]
0x18000285f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002864  mov     ebx, eax
0x180002866  test    eax, eax
0x180002868  jnz     short loc_1800028AA
0x18000286a  test    rsi, rsi
0x18000286d  jz      short loc_1800028C4
0x18000286f  mov     r8d, [rsp+68h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180002874  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000287c  mov     rdx, r14; lpBuffer
0x18000287f  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x180002888  mov     rcx, rsi; hFile
0x18000288b  call    cs:__imp_WriteFile
0x180002891  test    eax, eax
0x180002893  jnz     short loc_1800028CD
0x180002895  call    cs:__imp_GetLastError
0x18000289b  mov     ebx, eax
0x18000289d  test    eax, eax
0x18000289f  jle     short loc_1800028AA
0x1800028a1  movzx   ebx, ax
0x1800028a4  or      ebx, 80070000h
0x1800028aa  mov     rcx, r14; Block
0x1800028ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800028b2  test    rsi, rsi
0x1800028b5  jz      short loc_1800028C0
0x1800028b7  mov     rcx, rsi; hObject
0x1800028ba  call    cs:__imp_CloseHandle
0x1800028c0  mov     eax, ebx
0x1800028c2  jmp     short loc_1800028DE
0x1800028c4  mov     rcx, r14; Buffer
0x1800028c7  call    cs:__imp_puts
0x1800028cd  inc     edi
0x1800028cf  cmp     edi, ebp
0x1800028d1  jbe     loc_18000283A
0x1800028d7  jmp     short loc_1800028AA
0x1800028d9  mov     eax, 80070057h
0x1800028de  lea     r11, [rsp+68h+var_28]
0x1800028e3  mov     rbx, [r11+30h]
0x1800028e7  mov     rbp, [r11+48h]
0x1800028eb  mov     rsp, r11
0x1800028ee  pop     r15
0x1800028f0  pop     r14
0x1800028f2  pop     r12
0x1800028f4  pop     rdi
0x1800028f5  pop     rsi
0x1800028f6  retn
```
