# CreateNewFileFromOldFileMapped

- ea: `0x180003580`
- end: `0x1800036d9`
- name: `CreateNewFileFromOldFileMapped`
- size: `345`
- prototype: `__int64 __fastcall(void *Src, __int64 lDistanceToMove, HANDLE hFile, __int64, int, unsigned int, __int64, char *Srca, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002720`

## callees

- `0x180003580`
- `0x180004678`
- `0x180006d9c`
- `0x180006e64`
- `0x180006fd0`
- `0x180009061`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003679`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000368f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003679`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000368f`

## pseudocode

```c
__int64 __fastcall CreateNewFileFromOldFileMapped(
        void *Src,
        __int64 lDistanceToMove,
        HANDLE hFile,
        __int64 a4,
        int a5,
        unsigned int a6,
        __int64 a7,
        char *Srca,
        __int64 a9,
        __int64 a10)
{
  unsigned __int64 v11; // rdi
  unsigned int MappedFileByHandle; // ebx
  char *v14; // r14
  __int64 v15; // rcx
  __int64 i; // rbx
  unsigned __int64 v18; // rdx
  __int64 v19; // rsi
  size_t v20; // r8
  LPCVOID lpBaseAddress[8]; // [rsp+28h] [rbp-40h] BYREF

  v11 = (unsigned int)lDistanceToMove;
  lpBaseAddress[0] = 0;
  MappedFileByHandle = MyCreateMappedFileByHandle(hFile, lDistanceToMove, lpBaseAddress);
  if ( MappedFileByHandle )
  {
    v14 = (char *)lpBaseAddress[0];
    memcpy_0((void *)lpBaseAddress[0], Src, (unsigned int)v11);
    if ( ~(unsigned int)Crc32(v15, v14, (unsigned int)v11) == a5 )
    {
      for ( i = 0; (unsigned int)i < a6; i = (unsigned int)(i + 1) )
      {
        v18 = *(unsigned int *)(a7 + 12 * i + 8);
        v19 = a7 + 12 * i;
        if ( v18 <= v11 )
        {
          v20 = *(unsigned int *)(v19 + 4);
          if ( v20 <= v11 - v18 )
            memcpy_0(&v14[v18], Srca, v20);
        }
        Srca += *(unsigned int *)(v19 + 4);
      }
      MappedFileByHandle = ProgressCallbackWrapper(a9, a10, (unsigned int)v11, (unsigned int)v11);
    }
    else
    {
      SetLastError(0xC00E4104);
      LODWORD(v11) = 0;
      MappedFileByHandle = 0;
    }
    MyUnmapCreatedMappedFile(hFile, v14, v11);
  }
  return MappedFileByHandle;
}

```

## disassembly

```asm
0x180003580  mov     rax, rsp
0x180003583  mov     [rax+20h], r9
0x180003587  mov     [rax+18h], r8
0x18000358b  push    rbx
0x18000358c  push    rsi
0x18000358d  push    rdi
0x18000358e  push    r12
0x180003590  push    r13
0x180003592  push    r14
0x180003594  push    r15
0x180003596  sub     rsp, 30h
0x18000359a  mov     r13, r9
0x18000359d  mov     r12, r8
0x1800035a0  mov     edi, edx
0x1800035a2  mov     rsi, rcx
0x1800035a5  mov     qword ptr [rax-40h], 0
0x1800035ad  lea     r8, [rax-40h]
0x1800035b1  mov     rcx, r12
0x1800035b4  call    MyCreateMappedFileByHandle
0x1800035b9  mov     ebx, eax
0x1800035bb  test    eax, eax
0x1800035bd  jz      loc_1800036C7
0x1800035c3  mov     r8d, edi; Size
0x1800035c6  mov     rdx, rsi; Src
0x1800035c9  mov     r14, [rsp+68h+lpBaseAddress]
0x1800035ce  mov     rcx, r14; void *
0x1800035d1  call    memcpy_0
0x1800035d6  mov     r8d, edi
0x1800035d9  mov     rdx, r14
0x1800035dc  call    Crc32
0x1800035e1  not     eax
0x1800035e3  cmp     eax, [rsp+68h+arg_20]
0x1800035ea  jnz     loc_180003674
0x1800035f0  xor     ebx, ebx
0x1800035f2  mov     [rsp+68h+var_44], ebx
0x1800035f6  mov     r15, [rsp+68h+Src]
0x1800035fe  cmp     ebx, [rsp+68h+arg_28]
0x180003605  jnb     short loc_180003651
0x180003607  lea     rcx, [rbx+rbx*2]
0x18000360b  mov     rax, [rsp+68h+arg_30]
0x180003613  mov     edx, [rax+rcx*4+8]
0x180003617  lea     rsi, [rax+rcx*4]
0x18000361b  mov     rax, rdi
0x18000361e  cmp     rdx, rdi
0x180003621  ja      short loc_18000363B
0x180003623  mov     r8d, [rsi+4]; Size
0x180003627  sub     rax, rdx
0x18000362a  cmp     r8, rax
0x18000362d  ja      short loc_18000363B
0x18000362f  lea     rcx, [rdx+r14]; void *
0x180003633  mov     rdx, r15; Src
0x180003636  call    memcpy_0
0x18000363b  mov     eax, [rsi+4]
0x18000363e  add     r15, rax
0x180003641  mov     [rsp+68h+Src], r15
0x180003649  inc     ebx
0x18000364b  mov     [rsp+68h+var_44], ebx
0x18000364f  jmp     short loc_1800035FE
0x180003651  mov     r9d, edi
0x180003654  mov     r8d, edi
0x180003657  mov     rdx, [rsp+68h+arg_48]
0x18000365f  mov     rcx, [rsp+68h+arg_40]
0x180003667  call    ProgressCallbackWrapper
0x18000366c  mov     ebx, eax
0x18000366e  mov     [rsp+68h+var_48], eax
0x180003672  jmp     short loc_18000368B
0x180003674  mov     ecx, 0C00E4104h; dwErrCode
0x180003679  call    cs:__imp_SetLastError
0x18000367f  xor     edi, edi
0x180003681  mov     [rsp+68h+arg_8], edi
0x180003685  xor     ebx, ebx
0x180003687  mov     [rsp+68h+var_48], ebx
0x18000368b  jmp     short loc_1800036B6
0x18000368d  mov     ecx, eax; dwErrCode
0x18000368f  call    cs:__imp_SetLastError
0x180003695  xor     edi, edi
0x180003697  mov     [rsp+68h+arg_8], edi
0x18000369b  xor     ebx, ebx
0x18000369d  mov     [rsp+68h+var_48], ebx
0x1800036a1  mov     r13, [rsp+68h+arg_18]
0x1800036a9  mov     r12, [rsp+68h+arg_10]
0x1800036b1  mov     r14, [rsp+68h+lpBaseAddress]
0x1800036b6  mov     r9, r13
0x1800036b9  mov     r8d, edi; lDistanceToMove
0x1800036bc  mov     rdx, r14; lpBaseAddress
0x1800036bf  mov     rcx, r12; hFile
0x1800036c2  call    MyUnmapCreatedMappedFile
0x1800036c7  mov     eax, ebx
0x1800036c9  add     rsp, 30h
0x1800036cd  pop     r15
0x1800036cf  pop     r14
0x1800036d1  pop     r13
0x1800036d3  pop     r12
0x1800036d5  pop     rdi
0x1800036d6  pop     rsi
0x1800036d7  pop     rbx
0x1800036d8  retn
```
