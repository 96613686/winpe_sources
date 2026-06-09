# mlib::basic_handlebuf<char,std::char_traits<char>>::WriteElements(char const *,__int64,ulong *)

- ea: `0x1400134bc`
- end: `0x14001356d`
- name: `?WriteElements@?$basic_handlebuf@DU?$char_traits@D@std@@@mlib@@AEAAKPEBD_JPEAK@Z`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400136ac`

## callees

- `0x140004850`
- `0x1400134bc`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x140013505`
- `KERNEL32!WriteConsoleW` at `0x140013505`
- `KERNEL32!WriteFile` at `0x140013520`
- `KERNEL32!WriteFile` at `0x14001355c`
- `KERNEL32!WriteFile` at `0x140013520`
- `KERNEL32!WriteFile` at `0x14001355c`
- `KERNEL32!WriteConsoleA` at `0x140013554`
- `KERNEL32!WriteConsoleA` at `0x140013554`

## pseudocode

```c
BOOL __fastcall mlib::basic_handlebuf<char,std::char_traits<char>>::WriteElements(
        __int64 a1,
        const void *a2,
        DWORD a3,
        DWORD *a4)
{
  __int64 v6; // rax
  const void *v7; // rdx
  void *v8; // rcx
  BOOL v9; // ecx
  bool v11; // zf
  void *v12; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 204) )
  {
    v6 = mlib::basic_handlebuf<char,std::char_traits<char>>::TranscodeBuffer<char>();
    if ( v6 )
    {
      v7 = *(const void **)(a1 + 208);
      v8 = *(void **)(a1 + 136);
      if ( *(_BYTE *)(a1 + 192) )
        return WriteConsoleW(v8, v7, v6, a4, 0);
      NumberOfBytesWritten = 0;
      v9 = WriteFile(v8, v7, 2 * v6, &NumberOfBytesWritten, 0);
      *a4 = NumberOfBytesWritten >> 1;
      return v9;
    }
    else
    {
      return 1;
    }
  }
  else
  {
    v11 = *(_BYTE *)(a1 + 192) == 0;
    v12 = *(void **)(a1 + 136);
    if ( v11 )
      return WriteFile(v12, a2, a3, a4, 0);
    else
      return WriteConsoleA(v12, a2, a3, a4, 0);
  }
}

```

## disassembly

```asm
0x1400134bc  mov     [rsp+arg_8], rbx
0x1400134c1  push    rdi
0x1400134c2  sub     rsp, 30h
0x1400134c6  cmp     dword ptr [rcx+0CCh], 0
0x1400134cd  mov     rdi, r9
0x1400134d0  mov     rbx, rcx
0x1400134d3  jz      short loc_14001353B
0x1400134d5  call    ??$TranscodeBuffer@D@?$basic_handlebuf@DU?$char_traits@D@std@@@mlib@@AEAA_KPEBD_J@Z; mlib::basic_handlebuf<char,std::char_traits<char>>::TranscodeBuffer<char>(char const *,__int64)
0x1400134da  test    rax, rax
0x1400134dd  jz      short loc_140013534
0x1400134df  cmp     byte ptr [rbx+0C0h], 0
0x1400134e6  mov     rdx, [rbx+0D0h]; lpBuffer
0x1400134ed  mov     rcx, [rbx+88h]; hFile
0x1400134f4  mov     [rsp+38h+lpReserved], 0; lpOverlapped
0x1400134fd  jz      short loc_14001350F
0x1400134ff  mov     r9, rdi; lpNumberOfCharsWritten
0x140013502  mov     r8d, eax; nNumberOfCharsToWrite
0x140013505  call    cs:__imp_WriteConsoleW
0x14001350b  mov     ecx, eax
0x14001350d  jmp     short loc_140013530
0x14001350f  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x140013513  mov     [rsp+38h+NumberOfBytesWritten], 0
0x14001351b  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140013520  call    cs:__imp_WriteFile
0x140013526  mov     ecx, eax
0x140013528  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x14001352c  shr     eax, 1
0x14001352e  mov     [rdi], eax
0x140013530  mov     eax, ecx
0x140013532  jmp     short loc_140013562
0x140013534  mov     eax, 1
0x140013539  jmp     short loc_140013562
0x14001353b  cmp     byte ptr [rbx+0C0h], 0
0x140013542  mov     rcx, [rcx+88h]; hFile
0x140013549  mov     [rsp+38h+lpReserved], 0; lpOverlapped
0x140013552  jz      short loc_14001355C
0x140013554  call    cs:__imp_WriteConsoleA
0x14001355a  jmp     short loc_140013562
0x14001355c  call    cs:__imp_WriteFile
0x140013562  mov     rbx, [rsp+38h+arg_8]
0x140013567  add     rsp, 30h
0x14001356b  pop     rdi
0x14001356c  retn
```
