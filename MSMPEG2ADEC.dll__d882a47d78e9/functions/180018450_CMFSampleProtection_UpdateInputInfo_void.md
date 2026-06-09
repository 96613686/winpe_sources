# CMFSampleProtection::UpdateInputInfo(void)

- ea: `0x180018450`
- end: `0x1800184a8`
- name: `?UpdateInputInfo@CMFSampleProtection@@QEAAJXZ`
- size: `88`
- prototype: `__int64 __fastcall(CMFSampleProtection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000de70`
- `0x180015a40`

## callees

- `0x180018450`

## pseudocode

```c
__int64 __fastcall CMFSampleProtection::UpdateInputInfo(CMFSampleProtection *this)
{
  __int64 v2; // rax
  unsigned __int8 v3; // al
  __int64 v4; // rdx
  char v5; // cl
  __int64 result; // rax

  v2 = (58957 * *((_DWORD *)this + 170) - 151451) & 0x7FFFF;
  *((_QWORD *)this + 85) = v2;
  v3 = v2 & 7;
  while ( 1 )
  {
    v4 = v3;
    v5 = *((_BYTE *)this + v3 + 660);
    if ( v5 != -1 )
      break;
    if ( ++v3 >= 0x11u )
      return 0;
  }
  result = 0;
  *((_BYTE *)this + v4 + 660) = v5 + 1;
  return result;
}

```

## disassembly

```asm
0x180018450  imul    rax, [rcx+2A8h], 0E64Dh
0x18001845b  mov     r8, rcx
0x18001845e  sub     rax, 24F9Bh
0x180018464  and     eax, 7FFFFh
0x180018469  mov     [rcx+2A8h], rax
0x180018470  and     al, 7
0x180018472  nop     dword ptr [rax+00h]
0x180018476  nop     word ptr [rax+rax+00000000h]
0x180018480  movzx   edx, al
0x180018483  movzx   ecx, byte ptr [rdx+r8+294h]
0x18001848c  cmp     cl, 0FFh
0x18001848f  jnz     short loc_18001849B
0x180018491  inc     al
0x180018493  cmp     al, 11h
0x180018495  jb      short loc_180018480
0x180018497  xor     eax, eax
0x180018499  retn
0x18001849b  inc     cl
0x18001849d  xor     eax, eax
0x18001849f  mov     [rdx+r8+294h], cl
0x1800184a7  retn
```
