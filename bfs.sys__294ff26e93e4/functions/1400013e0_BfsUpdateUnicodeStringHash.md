# BfsUpdateUnicodeStringHash

- ea: `0x1400013e0`
- end: `0x14000144c`
- name: `BfsUpdateUnicodeStringHash`
- size: `108`
- prototype: `__int64 __fastcall(unsigned __int16 *, _QWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001320`
- `0x14000b4c8`
- `0x14000b654`
- `0x14000c0f4`
- `0x14000d734`

## callees

- `0x1400013e0`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140001409`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140001409`

## pseudocode

```c
__int64 __fastcall BfsUpdateUnicodeStringHash(unsigned __int16 *a1, _QWORD *a2)
{
  __int64 result; // rax
  __int64 v3; // rbx
  WCHAR v6; // ax

  result = *a1;
  v3 = 0;
  if ( (result & 0xFFFFFFFE) != 0 )
  {
    do
    {
      v6 = RtlUpcaseUnicodeChar(*(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v3));
      v3 = (unsigned int)(v3 + 1);
      *a2 = ((unsigned __int64)v6 >> 8) + 37 * ((unsigned __int8)v6 + 37LL * *a2);
      result = *a1 >> 1;
    }
    while ( (unsigned int)v3 < (unsigned int)result );
  }
  return result;
}

```

## disassembly

```asm
0x1400013e0  mov     [rsp+arg_0], rbx
0x1400013e5  mov     [rsp+arg_8], rsi
0x1400013ea  push    rdi
0x1400013eb  sub     rsp, 20h
0x1400013ef  movzx   eax, word ptr [rcx]
0x1400013f2  xor     ebx, ebx
0x1400013f4  mov     rsi, rdx
0x1400013f7  mov     rdi, rcx
0x1400013fa  test    eax, 0FFFFFFFEh
0x1400013ff  jbe     short loc_14000143B
0x140001401  mov     rcx, [rdi+8]
0x140001405  movzx   ecx, word ptr [rcx+rbx*2]; SourceCharacter
0x140001409  call    cs:__imp_RtlUpcaseUnicodeChar
0x140001410  nop     dword ptr [rax+rax+00h]
0x140001415  imul    rcx, [rsi], 25h ; '%'
0x140001419  movzx   edx, ax
0x14000141c  inc     ebx
0x14000141e  movzx   eax, dl
0x140001421  add     rcx, rax
0x140001424  shr     rdx, 8
0x140001428  imul    rax, rcx, 25h ; '%'
0x14000142c  add     rax, rdx
0x14000142f  mov     [rsi], rax
0x140001432  movzx   eax, word ptr [rdi]
0x140001435  shr     eax, 1
0x140001437  cmp     ebx, eax
0x140001439  jb      short loc_140001401
0x14000143b  mov     rbx, [rsp+28h+arg_0]
0x140001440  mov     rsi, [rsp+28h+arg_8]
0x140001445  add     rsp, 20h
0x140001449  pop     rdi
0x14000144a  retn
```
