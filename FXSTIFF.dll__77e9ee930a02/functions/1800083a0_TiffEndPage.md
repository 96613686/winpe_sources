# TiffEndPage

- ea: `0x1800083a0`
- end: `0x18000857e`
- name: `TiffEndPage`
- size: `478`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005ed0`
- `0x180008590`
- `0x18000b120`
- `0x18000bb50`

## callees

- `0x1800083a0`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1800083e5`
- `KERNEL32!SetFilePointer` at `0x180008412`
- `KERNEL32!SetFilePointer` at `0x180008450`
- `KERNEL32!SetFilePointer` at `0x1800083e5`
- `KERNEL32!SetFilePointer` at `0x180008412`
- `KERNEL32!SetFilePointer` at `0x180008450`
- `KERNEL32!WriteFile` at `0x180008437`
- `KERNEL32!WriteFile` at `0x180008542`
- `KERNEL32!WriteFile` at `0x180008437`
- `KERNEL32!WriteFile` at `0x180008542`

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
0x1800083a0  mov     [rsp+arg_10], rbx
0x1800083a5  push    rsi
0x1800083a6  push    rdi
0x1800083a7  push    r14
0x1800083a9  sub     rsp, 30h
0x1800083ad  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800083b1  lea     rdi, [rcx+23Ch]
0x1800083b8  mov     esi, 4
0x1800083bd  mov     [rsp+48h+NumberOfBytesWritten], 0
0x1800083c5  mov     rbx, rcx
0x1800083c8  mov     [rsp+48h+Buffer], 0
0x1800083d0  lea     r14d, [rsi-3]
0x1800083d4  jz      loc_180008462
0x1800083da  mov     rcx, [rcx]; hFile
0x1800083dd  mov     r9d, r14d; dwMoveMethod
0x1800083e0  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800083e3  xor     edx, edx; lDistanceToMove
0x1800083e5  call    cs:__imp_SetFilePointer
0x1800083ec  nop     dword ptr [rax+rax+00h]
0x1800083f1  mov     [rsp+48h+Buffer], eax
0x1800083f5  test    al, 7
0x1800083f7  jz      short loc_180008403
0x1800083f9  and     eax, 0FFFFFFF8h
0x1800083fc  add     eax, 8
0x1800083ff  mov     [rsp+48h+Buffer], eax
0x180008403  mov     edx, [rbx+34Ch]; lDistanceToMove
0x180008409  xor     r9d, r9d; dwMoveMethod
0x18000840c  mov     rcx, [rbx]; hFile
0x18000840f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180008412  call    cs:__imp_SetFilePointer
0x180008419  nop     dword ptr [rax+rax+00h]
0x18000841e  mov     rcx, [rbx]; hFile
0x180008421  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180008426  mov     r8d, esi; nNumberOfBytesToWrite
0x180008429  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180008432  lea     rdx, [rsp+48h+Buffer]; lpBuffer
0x180008437  call    cs:__imp_WriteFile
0x18000843e  nop     dword ptr [rax+rax+00h]
0x180008443  mov     edx, [rsp+48h+Buffer]; lDistanceToMove
0x180008447  xor     r9d, r9d; dwMoveMethod
0x18000844a  mov     rcx, [rbx]; hFile
0x18000844d  xor     r8d, r8d; lpDistanceToMoveHigh
0x180008450  call    cs:__imp_SetFilePointer
0x180008457  nop     dword ptr [rax+rax+00h]
0x18000845c  mov     ecx, [rsp+48h+Buffer]
0x180008460  jmp     short loc_180008469
0x180008462  mov     ecx, [rcx+18h]
0x180008465  mov     [rsp+48h+Buffer], ecx
0x180008469  add     [rbx+344h], r14d
0x180008470  mov     eax, [rbx+694h]
0x180008476  mov     [rdi+0DEh], eax
0x18000847c  movzx   eax, word ptr [rbx+344h]
0x180008483  sub     ax, r14w
0x180008487  movzx   eax, ax
0x18000848a  mov     [rdi+0BEh], eax
0x180008490  mov     eax, [rbx+61Ch]
0x180008496  mov     [rdi+16h], eax
0x180008499  mov     eax, [rbx+350h]
0x18000849f  mov     [rdi+22h], eax
0x1800084a2  mov     eax, [rbx+350h]
0x1800084a8  mov     [rdi+76h], eax
0x1800084ab  mov     eax, [rbx+358h]
0x1800084b1  mov     [rdi+82h], eax
0x1800084b7  mov     eax, [rbx+348h]
0x1800084bd  mov     [rdi+5Eh], eax
0x1800084c0  lea     eax, [rcx+0D6h]
0x1800084c6  mov     [rdi+8Eh], eax
0x1800084cc  lea     eax, [rcx+0DEh]
0x1800084d2  mov     [rdi+9Ah], eax
0x1800084d8  lea     eax, [rcx+0E6h]
0x1800084de  mov     [rdi+0CAh], eax
0x1800084e4  mov     eax, [rbx+65Ch]
0x1800084ea  mov     [rdi+52h], eax
0x1800084ed  mov     eax, [rbx+354h]
0x1800084f3  cmp     eax, r14d
0x1800084f6  jnz     short loc_1800084FE
0x1800084f8  mov     [rdi+3Ah], r14d
0x1800084fc  jmp     short loc_18000851C
0x1800084fe  cmp     eax, esi
0x180008500  jnz     short loc_180008507
0x180008502  mov     [rdi+3Ah], esi
0x180008505  jmp     short loc_18000850E
0x180008507  mov     dword ptr [rdi+3Ah], 3
0x18000850e  xor     eax, eax
0x180008510  cmp     dword ptr [rbx+354h], 2
0x180008517  setnz   al
0x18000851a  add     esi, eax
0x18000851c  mov     [rdi+0A6h], esi
0x180008522  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180008526  jz      short loc_180008562
0x180008528  mov     rcx, [rbx]; hFile
0x18000852b  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180008530  mov     r8d, 106h; nNumberOfBytesToWrite
0x180008536  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18000853f  mov     rdx, rdi; lpBuffer
0x180008542  call    cs:__imp_WriteFile
0x180008549  nop     dword ptr [rax+rax+00h]
0x18000854e  test    eax, eax
0x180008550  jz      short loc_18000856F
0x180008552  mov     ecx, [rsp+48h+Buffer]
0x180008556  add     ecx, 0CEh
0x18000855c  mov     [rbx+34Ch], ecx
0x180008562  mov     dword ptr [rbx+358h], 0
0x18000856c  mov     eax, r14d
0x18000856f  mov     rbx, [rsp+48h+arg_10]
0x180008574  add     rsp, 30h
0x180008578  pop     r14
0x18000857a  pop     rdi
0x18000857b  pop     rsi
0x18000857c  retn
```
