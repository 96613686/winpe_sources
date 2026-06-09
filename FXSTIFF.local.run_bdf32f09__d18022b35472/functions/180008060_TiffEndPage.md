# TiffEndPage

- ea: `0x180008060`
- end: `0x18000821b`
- name: `TiffEndPage`
- size: `443`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005d80`
- `0x180008230`
- `0x18000ac38`
- `0x18000b604`

## callees

- `0x180008060`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1800080a1`
- `KERNEL32!SetFilePointer` at `0x1800080c8`
- `KERNEL32!SetFilePointer` at `0x1800080fa`
- `KERNEL32!SetFilePointer` at `0x1800080a1`
- `KERNEL32!SetFilePointer` at `0x1800080c8`
- `KERNEL32!SetFilePointer` at `0x1800080fa`
- `KERNEL32!WriteFile` at `0x1800080e7`
- `KERNEL32!WriteFile` at `0x1800081e6`
- `KERNEL32!WriteFile` at `0x1800080e7`
- `KERNEL32!WriteFile` at `0x1800081e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __fastcall TiffEndPage(__int64 a1)
{
  bool v1; // zf
  __int64 v2; // rdi
  int v3; // esi
  DWORD v5; // eax
  LONG v6; // ecx
  int v7; // eax
  BOOL result; // eax
  LONG Buffer; // [rsp+50h] [rbp+8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+10h] BYREF

  v1 = *(_QWORD *)a1 == -1;
  v2 = a1 + 572;
  v3 = 4;
  NumberOfBytesWritten = 0;
  Buffer = 0;
  if ( v1 )
  {
    v6 = *(_DWORD *)(a1 + 24);
    Buffer = v6;
  }
  else
  {
    v5 = SetFilePointer(*(HANDLE *)a1, 0, 0, 1u);
    Buffer = v5;
    if ( (v5 & 7) != 0 )
      Buffer = (v5 & 0xFFFFFFF8) + 8;
    SetFilePointer(*(HANDLE *)a1, *(_DWORD *)(a1 + 844), 0, 0);
    WriteFile(*(HANDLE *)a1, &Buffer, 4u, &NumberOfBytesWritten, 0);
    SetFilePointer(*(HANDLE *)a1, Buffer, 0, 0);
    v6 = Buffer;
  }
  ++*(_DWORD *)(a1 + 836);
  *(_DWORD *)(v2 + 222) = *(_DWORD *)(a1 + 1684);
  *(_DWORD *)(v2 + 190) = (unsigned __int16)(*(_WORD *)(a1 + 836) - 1);
  *(_DWORD *)(v2 + 22) = *(_DWORD *)(a1 + 1564);
  *(_DWORD *)(v2 + 34) = *(_DWORD *)(a1 + 848);
  *(_DWORD *)(v2 + 118) = *(_DWORD *)(a1 + 848);
  *(_DWORD *)(v2 + 130) = *(_DWORD *)(a1 + 856);
  *(_DWORD *)(v2 + 94) = *(_DWORD *)(a1 + 840);
  *(_DWORD *)(v2 + 142) = v6 + 214;
  *(_DWORD *)(v2 + 154) = v6 + 222;
  *(_DWORD *)(v2 + 202) = v6 + 230;
  *(_DWORD *)(v2 + 82) = *(_DWORD *)(a1 + 1628);
  v7 = *(_DWORD *)(a1 + 852);
  if ( v7 == 1 )
  {
    *(_DWORD *)(v2 + 58) = 1;
  }
  else
  {
    if ( v7 == 4 )
      *(_DWORD *)(v2 + 58) = 4;
    else
      *(_DWORD *)(v2 + 58) = 3;
    v3 = (*(_DWORD *)(a1 + 852) != 2) + 4;
  }
  *(_DWORD *)(v2 + 166) = v3;
  if ( *(_QWORD *)a1 != -1 )
  {
    result = WriteFile(*(HANDLE *)a1, (LPCVOID)v2, 0x106u, &NumberOfBytesWritten, 0);
    if ( !result )
      return result;
    *(_DWORD *)(a1 + 844) = Buffer + 206;
  }
  *(_DWORD *)(a1 + 856) = 0;
  return 1;
}

```

## disassembly

```asm
0x180008060  mov     [rsp+arg_10], rbx
0x180008065  push    rsi
0x180008066  push    rdi
0x180008067  push    r14
0x180008069  sub     rsp, 30h
0x18000806d  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180008071  lea     rdi, [rcx+23Ch]
0x180008078  mov     esi, 4
0x18000807d  mov     [rsp+48h+NumberOfBytesWritten], 0
0x180008085  mov     rbx, rcx
0x180008088  mov     [rsp+48h+Buffer], 0
0x180008090  lea     r14d, [rsi-3]
0x180008094  jz      short loc_180008106
0x180008096  mov     rcx, [rcx]; hFile
0x180008099  mov     r9d, r14d; dwMoveMethod
0x18000809c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000809f  xor     edx, edx; lDistanceToMove
0x1800080a1  call    cs:__imp_SetFilePointer
0x1800080a7  mov     [rsp+48h+Buffer], eax
0x1800080ab  test    al, 7
0x1800080ad  jz      short loc_1800080B9
0x1800080af  and     eax, 0FFFFFFF8h
0x1800080b2  add     eax, 8
0x1800080b5  mov     [rsp+48h+Buffer], eax
0x1800080b9  mov     edx, [rbx+34Ch]; lDistanceToMove
0x1800080bf  xor     r9d, r9d; dwMoveMethod
0x1800080c2  mov     rcx, [rbx]; hFile
0x1800080c5  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800080c8  call    cs:__imp_SetFilePointer
0x1800080ce  mov     rcx, [rbx]; hFile
0x1800080d1  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800080d6  mov     r8d, esi; nNumberOfBytesToWrite
0x1800080d9  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800080e2  lea     rdx, [rsp+48h+Buffer]; lpBuffer
0x1800080e7  call    cs:__imp_WriteFile
0x1800080ed  mov     edx, [rsp+48h+Buffer]; lDistanceToMove
0x1800080f1  xor     r9d, r9d; dwMoveMethod
0x1800080f4  mov     rcx, [rbx]; hFile
0x1800080f7  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800080fa  call    cs:__imp_SetFilePointer
0x180008100  mov     ecx, [rsp+48h+Buffer]
0x180008104  jmp     short loc_18000810D
0x180008106  mov     ecx, [rcx+18h]
0x180008109  mov     [rsp+48h+Buffer], ecx
0x18000810d  add     [rbx+344h], r14d
0x180008114  mov     eax, [rbx+694h]
0x18000811a  mov     [rdi+0DEh], eax
0x180008120  movzx   eax, word ptr [rbx+344h]
0x180008127  sub     ax, r14w
0x18000812b  movzx   eax, ax
0x18000812e  mov     [rdi+0BEh], eax
0x180008134  mov     eax, [rbx+61Ch]
0x18000813a  mov     [rdi+16h], eax
0x18000813d  mov     eax, [rbx+350h]
0x180008143  mov     [rdi+22h], eax
0x180008146  mov     eax, [rbx+350h]
0x18000814c  mov     [rdi+76h], eax
0x18000814f  mov     eax, [rbx+358h]
0x180008155  mov     [rdi+82h], eax
0x18000815b  mov     eax, [rbx+348h]
0x180008161  mov     [rdi+5Eh], eax
0x180008164  lea     eax, [rcx+0D6h]
0x18000816a  mov     [rdi+8Eh], eax
0x180008170  lea     eax, [rcx+0DEh]
0x180008176  mov     [rdi+9Ah], eax
0x18000817c  lea     eax, [rcx+0E6h]
0x180008182  mov     [rdi+0CAh], eax
0x180008188  mov     eax, [rbx+65Ch]
0x18000818e  mov     [rdi+52h], eax
0x180008191  mov     eax, [rbx+354h]
0x180008197  cmp     eax, r14d
0x18000819a  jnz     short loc_1800081A2
0x18000819c  mov     [rdi+3Ah], r14d
0x1800081a0  jmp     short loc_1800081C0
0x1800081a2  cmp     eax, esi
0x1800081a4  jnz     short loc_1800081AB
0x1800081a6  mov     [rdi+3Ah], esi
0x1800081a9  jmp     short loc_1800081B2
0x1800081ab  mov     dword ptr [rdi+3Ah], 3
0x1800081b2  xor     eax, eax
0x1800081b4  cmp     dword ptr [rbx+354h], 2
0x1800081bb  setnz   al
0x1800081be  add     esi, eax
0x1800081c0  mov     [rdi+0A6h], esi
0x1800081c6  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800081ca  jz      short loc_180008200
0x1800081cc  mov     rcx, [rbx]; hFile
0x1800081cf  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800081d4  mov     r8d, 106h; nNumberOfBytesToWrite
0x1800081da  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800081e3  mov     rdx, rdi; lpBuffer
0x1800081e6  call    cs:__imp_WriteFile
0x1800081ec  test    eax, eax
0x1800081ee  jz      short loc_18000820D
0x1800081f0  mov     ecx, [rsp+48h+Buffer]
0x1800081f4  add     ecx, 0CEh
0x1800081fa  mov     [rbx+34Ch], ecx
0x180008200  mov     dword ptr [rbx+358h], 0
0x18000820a  mov     eax, r14d
0x18000820d  mov     rbx, [rsp+48h+arg_10]
0x180008212  add     rsp, 30h
0x180008216  pop     r14
0x180008218  pop     rdi
0x180008219  pop     rsi
0x18000821a  retn
```
