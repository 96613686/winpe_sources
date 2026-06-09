# SmpFindSubStr

- ea: `0x1400012c8`
- end: `0x140001347`
- name: `SmpFindSubStr`
- size: `127`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007410`

## callees

- `0x1400012c8`

## import_xrefs

- `ntoskrnl!_wcsnicmp` at `0x140001317`
- `ntoskrnl!_wcsnicmp` at `0x140001317`

## pseudocode

```c
char __fastcall SmpFindSubStr(__int64 a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v3; // ecx
  unsigned int v6; // edi
  unsigned int v7; // ebx

  v3 = *a2;
  if ( (v3 & 0xFFFE) <= 0x1E )
    return 0;
  v6 = 15;
  v7 = *a3 >> 1;
  if ( v7 + 15 > v3 >> 1 )
    return 0;
  while ( _wcsnicmp((const wchar_t *)(*((_QWORD *)a2 + 1) + 2LL * v6), *((const wchar_t **)a3 + 1), v7) )
  {
    ++v6;
    if ( v7 + v6 > *a2 >> 1 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1400012c8  push    rbx
0x1400012ca  push    rbp
0x1400012cb  push    rsi
0x1400012cc  push    rdi
0x1400012cd  push    r14
0x1400012cf  sub     rsp, 20h
0x1400012d3  movzx   ecx, word ptr [rdx]
0x1400012d6  mov     rsi, rdx
0x1400012d9  mov     edx, 0FFFEh
0x1400012de  movzx   eax, cx
0x1400012e1  and     ax, dx
0x1400012e4  mov     rbp, r8
0x1400012e7  mov     edx, 1Eh
0x1400012ec  cmp     dx, ax
0x1400012ef  jnb     short loc_140001335
0x1400012f1  movzx   ebx, word ptr [r8]
0x1400012f5  lea     edi, [rdx-0Fh]
0x1400012f8  shr     ebx, 1
0x1400012fa  shr     ecx, 1
0x1400012fc  lea     eax, [rbx+0Fh]
0x1400012ff  cmp     eax, ecx
0x140001301  ja      short loc_140001335
0x140001303  mov     r14d, ebx
0x140001306  mov     rax, [rsi+8]
0x14000130a  mov     r8, r14; MaxCount
0x14000130d  mov     rdx, [rbp+8]; Str2
0x140001311  mov     ecx, edi
0x140001313  lea     rcx, [rax+rcx*2]; Str1
0x140001317  call    cs:__imp__wcsnicmp
0x14000131e  nop     dword ptr [rax+rax+00h]
0x140001323  test    eax, eax
0x140001325  jz      short loc_140001343
0x140001327  movzx   ecx, word ptr [rsi]
0x14000132a  inc     edi
0x14000132c  shr     ecx, 1
0x14000132e  lea     eax, [rbx+rdi]
0x140001331  cmp     eax, ecx
0x140001333  jbe     short loc_140001306
0x140001335  xor     al, al
0x140001337  add     rsp, 20h
0x14000133b  pop     r14
0x14000133d  pop     rdi
0x14000133e  pop     rsi
0x14000133f  pop     rbp
0x140001340  pop     rbx
0x140001341  retn
0x140001343  mov     al, 1
0x140001345  jmp     short loc_140001337
```
