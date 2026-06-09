# pSetupGrowMappedFileAtOffset

- ea: `0x14000c848`
- end: `0x14000c8b4`
- name: `pSetupGrowMappedFileAtOffset`
- size: `108`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x14000d84c`
- `0x14000d8c0`
- `0x140010028`

## callees

- `0x14000c848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c89f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c89f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14000c894`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14000c894`

## pseudocode

```c
__int64 __fastcall pSetupGrowMappedFileAtOffset(HANDLE hFile, unsigned int a2, __int64 a3, unsigned int a4, int a5)
{
  unsigned int v6; // ebx
  __int64 v7; // r11
  unsigned int i; // r8d

  if ( a4 > a2 )
    return 87;
  v6 = 0;
  v7 = a3 + a4;
  for ( i = a2 - a4; (--i & 0x80000000) == 0; *(_BYTE *)(i + a5 + v7) = *(_BYTE *)(i + v7) )
    ;
  if ( SetFilePointer(hFile, a5 + a2, 0, 0) == -1 )
    return GetLastError();
  return v6;
}

```

## disassembly

```asm
0x14000c848  mov     [rsp+arg_0], rbx
0x14000c84d  push    rdi
0x14000c84e  sub     rsp, 20h
0x14000c852  mov     rdi, rcx
0x14000c855  cmp     r9d, edx
0x14000c858  jbe     short loc_14000C861
0x14000c85a  mov     eax, 57h ; 'W'
0x14000c85f  jmp     short loc_14000C8A9
0x14000c861  mov     r11d, r9d
0x14000c864  xor     ebx, ebx
0x14000c866  add     r11, r8
0x14000c869  mov     r8d, edx
0x14000c86c  sub     r8d, r9d
0x14000c86f  mov     r9d, [rsp+28h+arg_20]
0x14000c874  jmp     short loc_14000C882
0x14000c876  mov     al, [r8+r11]
0x14000c87a  lea     ecx, [r8+r9]
0x14000c87e  mov     [rcx+r11], al
0x14000c882  sub     r8d, 1
0x14000c886  jns     short loc_14000C876
0x14000c888  add     edx, r9d; lDistanceToMove
0x14000c88b  xor     r8d, r8d; lpDistanceToMoveHigh
0x14000c88e  xor     r9d, r9d; dwMoveMethod
0x14000c891  mov     rcx, rdi; hFile
0x14000c894  call    cs:__imp_SetFilePointer
0x14000c89a  cmp     eax, 0FFFFFFFFh
0x14000c89d  jnz     short loc_14000C8A7
0x14000c89f  call    cs:__imp_GetLastError
0x14000c8a5  mov     ebx, eax
0x14000c8a7  mov     eax, ebx
0x14000c8a9  mov     rbx, [rsp+28h+arg_0]
0x14000c8ae  add     rsp, 20h
0x14000c8b2  pop     rdi
0x14000c8b3  retn
```
