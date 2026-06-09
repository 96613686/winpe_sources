# CBitStream::GetBits(uint)

- ea: `0x180005f80`
- end: `0x180006024`
- name: `?GetBits@CBitStream@@QEAAII@Z`
- size: `164`
- prototype: `__int64 __fastcall(CBitStream *this, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ac0`
- `0x1800056c0`
- `0x18000602c`
- `0x180006068`
- `0x180006abc`

## callees

- `0x180005f80`

## pseudocode

```c
__int64 __fastcall CBitStream::GetBits(CBitStream *this, unsigned int a2)
{
  int v2; // edi
  __int64 v4; // rsi
  unsigned int v6; // ecx
  unsigned __int16 v7; // bx
  int v8; // edx

  v2 = *((_DWORD *)this + 9);
  v4 = *((_QWORD *)this + 6);
  v6 = 16 - (v2 & 0xF);
  if ( a2 > v6 )
    v7 = ((*(unsigned __int8 *)(((v2 >> 3) & 0xFFFFFFFE) + 1 + v4)
         | (unsigned __int16)(*(unsigned __int8 *)(((v2 >> 3) & 0xFFFFFFFE) + v4) << 8)) << (v2 & 0xF))
       | ((unsigned __int16)(*(unsigned __int8 *)(((((v2 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)this + 4) - 1)) + 1 + v4)
                           | (*(unsigned __int8 *)(((((v2 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)this + 4) - 1)) + v4) << 8)) >> v6);
  else
    v7 = (*(unsigned __int8 *)(((v2 >> 3) & 0xFFFFFFFE) + 1 + v4)
        | (unsigned __int16)(*(unsigned __int8 *)(((v2 >> 3) & 0xFFFFFFFE) + v4) << 8)) << (v2 & 0xF);
  v8 = *((_DWORD *)this + 5);
  *((_DWORD *)this + 8) += a2;
  *((_DWORD *)this + 6) -= a2;
  *((_DWORD *)this + 9) = (v8 - 1) & (v2 + a2);
  return v7 >> (16 - a2);
}

```

## disassembly

```asm
0x180005f80  push    rbx
0x180005f82  push    rsi
0x180005f83  push    rdi
0x180005f84  mov     edi, [rcx+24h]
0x180005f87  mov     rax, rcx
0x180005f8a  mov     ecx, edi
0x180005f8c  mov     r8d, edi
0x180005f8f  sar     ecx, 3
0x180005f92  and     r8d, 0Fh
0x180005f96  and     ecx, 0FFFFFFFEh
0x180005f99  mov     r11d, 10h
0x180005f9f  mov     rsi, [rax+30h]
0x180005fa3  mov     r9d, edx
0x180005fa6  mov     ebx, ecx
0x180005fa8  movzx   r10d, byte ptr [rcx+rsi]
0x180005fad  inc     ecx
0x180005faf  shl     r10w, 8
0x180005fb4  movzx   ecx, byte ptr [rcx+rsi]
0x180005fb8  or      r10w, cx
0x180005fbc  mov     ecx, r8d
0x180005fbf  shl     r10w, cl
0x180005fc3  mov     ecx, r11d
0x180005fc6  sub     ecx, r8d
0x180005fc9  cmp     edx, ecx
0x180005fcb  ja      short loc_180005FF9
0x180005fcd  movzx   ebx, r10w
0x180005fd1  mov     edx, [rax+14h]
0x180005fd4  lea     r8d, [rdi+r9]
0x180005fd8  add     [rax+20h], r9d
0x180005fdc  dec     edx
0x180005fde  sub     [rax+18h], r9d
0x180005fe2  and     r8d, edx
0x180005fe5  sub     r11b, r9b
0x180005fe8  mov     [rax+24h], r8d
0x180005fec  movzx   eax, bx
0x180005fef  movzx   ecx, r11b
0x180005ff3  shr     eax, cl
0x180005ff5  pop     rdi
0x180005ff6  pop     rsi
0x180005ff7  pop     rbx
0x180005ff8  retn
0x180005ff9  mov     r8d, [rax+10h]
0x180005ffd  lea     edx, [rbx+2]
0x180006000  dec     r8d
0x180006003  and     r8d, edx
0x180006006  mov     edx, r8d
0x180006009  movzx   ebx, byte ptr [r8+rsi]
0x18000600e  shl     bx, 8
0x180006012  inc     edx
0x180006014  movzx   edx, byte ptr [rdx+rsi]
0x180006018  or      bx, dx
0x18000601b  shr     bx, cl
0x18000601e  or      bx, r10w
0x180006022  jmp     short loc_180005FD1
```
