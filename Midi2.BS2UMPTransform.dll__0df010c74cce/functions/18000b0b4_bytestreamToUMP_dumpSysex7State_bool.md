# bytestreamToUMP::dumpSysex7State(bool)

- ea: `0x18000b0b4`
- end: `0x18000b1c8`
- name: `?dumpSysex7State@bytestreamToUMP@@QEAAX_N@Z`
- size: `276`
- prototype: `void __fastcall(bytestreamToUMP *this, char)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a980`
- `0x18000ade4`

## callees

- `0x18000b0b4`

## pseudocode

```c
void __fastcall bytestreamToUMP::dumpSysex7State(bytestreamToUMP *this, char a2)
{
  int v3; // edx

  if ( *((_BYTE *)this + 2) && *((_BYTE *)this + 3) )
  {
    *((_DWORD *)this + *((int *)this + 32) + 3) = (*((unsigned __int8 *)this + 136) << 24) + 805306368;
    *((_DWORD *)this + *((int *)this + 32) + 3) += *((unsigned __int8 *)this + 2) << 20;
    *((_DWORD *)this + *((int *)this + 32) + 3) += *((unsigned __int8 *)this + 3) << 16;
    *((_DWORD *)this + (*((_DWORD *)this + 32))++ + 3) += *((unsigned __int8 *)this + 5)
                                                        + (*((unsigned __int8 *)this + 4) << 8);
    ++*((_DWORD *)this + 33);
    v3 = *((_DWORD *)this + 32);
    if ( v3 == 4 )
    {
      *((_DWORD *)this + 32) = 0;
      v3 = 0;
    }
    *((_DWORD *)this + v3 + 3) = *((unsigned __int8 *)this + 9)
                               + (*((unsigned __int8 *)this + 8) << 8)
                               + (*((unsigned __int8 *)this + 7) << 16)
                               + (*((unsigned __int8 *)this + 6) << 24);
    ++*((_DWORD *)this + 33);
    if ( ++*((_DWORD *)this + 32) == 4 )
      *((_DWORD *)this + 32) = 0;
    *((_DWORD *)this + 1) = 0;
    *((_WORD *)this + 4) = 0;
    if ( *((_BYTE *)this + 2) == 1 )
      *((_BYTE *)this + 2) = 2;
  }
  if ( a2 )
    *((_BYTE *)this + 2) = 1;
  *((_BYTE *)this + 3) = 0;
}

```

## disassembly

```asm
0x18000b0b4  xor     r11d, r11d
0x18000b0b7  mov     r10b, dl
0x18000b0ba  mov     r9, rcx
0x18000b0bd  cmp     [rcx+2], r11b
0x18000b0c1  jbe     loc_18000B1B9
0x18000b0c7  cmp     [rcx+3], r11b
0x18000b0cb  jbe     loc_18000B1B9
0x18000b0d1  movsxd  rax, dword ptr [rcx+80h]
0x18000b0d8  movzx   r8d, byte ptr [rcx+88h]
0x18000b0e0  shl     r8d, 18h
0x18000b0e4  add     r8d, 30000000h
0x18000b0eb  mov     [rcx+rax*4+0Ch], r8d
0x18000b0f0  movsxd  rcx, dword ptr [rcx+80h]
0x18000b0f7  movzx   eax, byte ptr [r9+2]
0x18000b0fc  shl     eax, 14h
0x18000b0ff  add     [r9+rcx*4+0Ch], eax
0x18000b104  movsxd  rcx, dword ptr [r9+80h]
0x18000b10b  movzx   eax, byte ptr [r9+3]
0x18000b110  shl     eax, 10h
0x18000b113  add     [r9+rcx*4+0Ch], eax
0x18000b118  movzx   ecx, byte ptr [r9+4]
0x18000b11d  movzx   eax, byte ptr [r9+5]
0x18000b122  movsxd  rdx, dword ptr [r9+80h]
0x18000b129  shl     ecx, 8
0x18000b12c  add     ecx, eax
0x18000b12e  add     [r9+rdx*4+0Ch], ecx
0x18000b133  inc     dword ptr [r9+80h]
0x18000b13a  inc     dword ptr [r9+84h]
0x18000b141  mov     edx, [r9+80h]
0x18000b148  cmp     edx, 4
0x18000b14b  jnz     short loc_18000B157
0x18000b14d  mov     [r9+80h], r11d
0x18000b154  mov     edx, r11d
0x18000b157  movzx   eax, byte ptr [r9+7]
0x18000b15c  movzx   ecx, byte ptr [r9+6]
0x18000b161  shl     eax, 10h
0x18000b164  shl     ecx, 18h
0x18000b167  add     ecx, eax
0x18000b169  movzx   eax, byte ptr [r9+8]
0x18000b16e  shl     eax, 8
0x18000b171  add     ecx, eax
0x18000b173  movzx   eax, byte ptr [r9+9]
0x18000b178  add     ecx, eax
0x18000b17a  movsxd  rax, edx
0x18000b17d  mov     [r9+rax*4+0Ch], ecx
0x18000b182  inc     dword ptr [r9+84h]
0x18000b189  inc     dword ptr [r9+80h]
0x18000b190  cmp     dword ptr [r9+80h], 4
0x18000b198  jnz     short loc_18000B1A1
0x18000b19a  mov     [r9+80h], r11d
0x18000b1a1  mov     rax, r11
0x18000b1a4  mov     [r9+4], eax
0x18000b1a8  mov     [r9+8], ax
0x18000b1ad  cmp     byte ptr [r9+2], 1
0x18000b1b2  jnz     short loc_18000B1B9
0x18000b1b4  mov     byte ptr [r9+2], 2
0x18000b1b9  test    r10b, r10b
0x18000b1bc  jz      short loc_18000B1C3
0x18000b1be  mov     byte ptr [r9+2], 1
0x18000b1c3  mov     [r9+3], r11b
0x18000b1c7  retn
```
