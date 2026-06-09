# pSetupGrowMappedFileAtOffset

- ea: `0x180040f2c`
- end: `0x180040f98`
- name: `pSetupGrowMappedFileAtOffset`
- size: `108`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x18003f96c`

## callees

- `0x180040f2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f83`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180040f78`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180040f78`

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
0x180040f2c  mov     [rsp+arg_0], rbx
0x180040f31  push    rdi
0x180040f32  sub     rsp, 20h
0x180040f36  mov     rdi, rcx
0x180040f39  cmp     r9d, edx
0x180040f3c  jbe     short loc_180040F45
0x180040f3e  mov     eax, 57h ; 'W'
0x180040f43  jmp     short loc_180040F8D
0x180040f45  mov     r11d, r9d
0x180040f48  xor     ebx, ebx
0x180040f4a  add     r11, r8
0x180040f4d  mov     r8d, edx
0x180040f50  sub     r8d, r9d
0x180040f53  mov     r9d, [rsp+28h+arg_20]
0x180040f58  jmp     short loc_180040F66
0x180040f5a  mov     al, [r8+r11]
0x180040f5e  lea     ecx, [r8+r9]
0x180040f62  mov     [rcx+r11], al
0x180040f66  sub     r8d, 1
0x180040f6a  jns     short loc_180040F5A
0x180040f6c  add     edx, r9d; lDistanceToMove
0x180040f6f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180040f72  xor     r9d, r9d; dwMoveMethod
0x180040f75  mov     rcx, rdi; hFile
0x180040f78  call    cs:__imp_SetFilePointer
0x180040f7e  cmp     eax, 0FFFFFFFFh
0x180040f81  jnz     short loc_180040F8B
0x180040f83  call    cs:__imp_GetLastError
0x180040f89  mov     ebx, eax
0x180040f8b  mov     eax, ebx
0x180040f8d  mov     rbx, [rsp+28h+arg_0]
0x180040f92  add     rsp, 20h
0x180040f96  pop     rdi
0x180040f97  retn
```
