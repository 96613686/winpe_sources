# btreeComputeFreeSpace

- ea: `0x180054a34`
- end: `0x180054b79`
- name: `btreeComputeFreeSpace`
- size: `325`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001cea8`
- `0x18001ed0c`
- `0x180020e14`
- `0x1800224a0`
- `0x180054970`
- `0x18006b17c`

## callees

- `0x1800275f0`
- `0x180054a34`
- `0x180060134`

## pseudocode

```c
__int64 __fastcall btreeComputeFreeSpace(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // r9
  unsigned int v4; // r11d
  int v5; // edi
  int v6; // ebp
  unsigned int v7; // r10d
  signed int v8; // r8d
  unsigned int v9; // r9d
  int v10; // ecx
  int v11; // r9d

  v1 = *(_QWORD *)(a1 + 80);
  v3 = *(unsigned __int8 *)(a1 + 9);
  v4 = *(_DWORD *)(*(_QWORD *)(a1 + 72) + 56LL);
  v5 = v3 + *(unsigned __int8 *)(a1 + 10) + 2 * (*(unsigned __int16 *)(a1 + 24) + 4);
  v6 = (unsigned __int16)(_byteswap_ushort(*(_WORD *)(v3 + v1 + 5)) - 1);
  v7 = (*(unsigned __int8 *)(v3 + v1 + 1) << 8) | *(unsigned __int8 *)(v3 + v1 + 2);
  v8 = *(unsigned __int8 *)(v3 + v1 + 7) + 1 + v6;
  if ( !v7 )
  {
LABEL_7:
    if ( v8 <= (int)v4 && v8 >= v5 )
    {
      *(_DWORD *)(a1 + 20) = (unsigned __int16)(v8 - v5);
      return 0;
    }
    v11 = 72822;
LABEL_9:
    sqlite3_log(
      11,
      "%s at line %d of [%.10s]",
      "database corruption",
      v11,
      "2aabe05e2e8cae4847a802ee2daddc1d7413d8fc560254d93ee3e72c14685b6c");
    return 11;
  }
  if ( v7 < v6 + 1 )
  {
    v11 = 72791;
    goto LABEL_9;
  }
  while ( 1 )
  {
    if ( (int)v7 > (int)(v4 - 4) )
    {
      v11 = 72796;
      goto LABEL_9;
    }
    v9 = *(unsigned __int8 *)(v7 + v1 + 1) | (*(unsigned __int8 *)(v7 + v1) << 8);
    v10 = *(unsigned __int8 *)(v7 + v1 + 3) | (*(unsigned __int8 *)(v7 + v1 + 2) << 8);
    v8 += v10;
    if ( v9 <= v10 + v7 + 3 )
      break;
    v7 = *(unsigned __int8 *)(v7 + v1 + 1) | (*(unsigned __int8 *)(v7 + v1) << 8);
  }
  if ( v9 )
  {
    v11 = 72806;
    goto LABEL_9;
  }
  if ( v10 + v7 <= v4 )
    goto LABEL_7;
  return sqlite3ReportError(11, 72810, "database corruption");
}

```

## disassembly

```asm
0x180054a34  push    rbx
0x180054a36  push    rbp
0x180054a37  push    rsi
0x180054a38  push    rdi
0x180054a39  sub     rsp, 38h
0x180054a3d  mov     rbx, [rcx+50h]
0x180054a41  mov     rsi, rcx
0x180054a44  movzx   r9d, byte ptr [rcx+9]
0x180054a49  mov     rax, [rcx+48h]
0x180054a4d  movzx   edi, word ptr [rcx+18h]
0x180054a51  movzx   ecx, byte ptr [rcx+0Ah]
0x180054a55  add     edi, 4
0x180054a58  movsxd  r8, r9d
0x180054a5b  add     ecx, r9d
0x180054a5e  mov     r11d, [rax+38h]
0x180054a62  movzx   eax, byte ptr [r8+rbx+5]
0x180054a68  lea     edi, [rcx+rdi*2]
0x180054a6b  movzx   edx, byte ptr [r8+rbx+6]
0x180054a71  movzx   r10d, byte ptr [r8+rbx+2]
0x180054a77  shl     eax, 8
0x180054a7a  or      edx, eax
0x180054a7c  movzx   eax, byte ptr [r8+rbx+1]
0x180054a82  movzx   r8d, byte ptr [r9+rbx+7]
0x180054a88  dec     edx
0x180054a8a  movzx   ebp, dx
0x180054a8d  shl     eax, 8
0x180054a90  or      r10d, eax
0x180054a93  lea     r8d, [r8+1]
0x180054a97  lea     r8d, [r8+rbp]
0x180054a9b  jbe     short loc_180054AF2
0x180054a9d  lea     eax, [rbp+1]
0x180054aa0  cmp     r10d, eax
0x180054aa3  jb      loc_180054B51
0x180054aa9  lea     ebp, [r11-4]
0x180054aad  cmp     r10d, ebp
0x180054ab0  jg      loc_180054B59
0x180054ab6  mov     edx, r10d
0x180054ab9  movzx   eax, byte ptr [rdx+rbx+1]
0x180054abe  movzx   r9d, byte ptr [rdx+rbx]
0x180054ac3  movzx   ecx, byte ptr [rdx+rbx+2]
0x180054ac8  shl     r9d, 8
0x180054acc  or      r9d, eax
0x180054acf  shl     ecx, 8
0x180054ad2  movzx   eax, byte ptr [rdx+rbx+3]
0x180054ad7  or      ecx, eax
0x180054ad9  add     r8d, ecx
0x180054adc  lea     edx, [rcx+r10]
0x180054ae0  lea     eax, [rdx+3]
0x180054ae3  cmp     r9d, eax
0x180054ae6  ja      short loc_180054B2E
0x180054ae8  test    r9d, r9d
0x180054aeb  jnz     short loc_180054B49
0x180054aed  cmp     edx, r11d
0x180054af0  ja      short loc_180054B61
0x180054af2  cmp     r8d, r11d
0x180054af5  jle     short loc_180054B36
0x180054af7  mov     r9d, 11C76h
0x180054afd  lea     rax, a20241207203959+14h; "2aabe05e2e8cae4847a802ee2daddc1d7413d8f"...
0x180054b04  mov     ebx, 0Bh
0x180054b09  mov     ecx, ebx
0x180054b0b  mov     [rsp+58h+var_38], rax
0x180054b10  lea     r8, aDatabaseCorrup; "database corruption"
0x180054b17  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x180054b1e  call    sqlite3_log
0x180054b23  mov     eax, ebx
0x180054b25  add     rsp, 38h
0x180054b29  pop     rdi
0x180054b2a  pop     rsi
0x180054b2b  pop     rbp
0x180054b2c  pop     rbx
0x180054b2d  retn
0x180054b2e  mov     r10d, r9d
0x180054b31  jmp     loc_180054AAD
0x180054b36  cmp     r8d, edi
0x180054b39  jl      short loc_180054AF7
0x180054b3b  sub     r8d, edi
0x180054b3e  movzx   eax, r8w
0x180054b42  mov     [rsi+14h], eax
0x180054b45  xor     eax, eax
0x180054b47  jmp     short loc_180054B25
0x180054b49  mov     r9d, 11C66h
0x180054b4f  jmp     short loc_180054AFD
0x180054b51  mov     r9d, 11C57h
0x180054b57  jmp     short loc_180054AFD
0x180054b59  mov     r9d, 11C5Ch
0x180054b5f  jmp     short loc_180054AFD
0x180054b61  lea     r8, aDatabaseCorrup; "database corruption"
0x180054b68  mov     edx, 11C6Ah
0x180054b6d  mov     ecx, 0Bh
0x180054b72  call    sqlite3ReportError
0x180054b77  jmp     short loc_180054B25
```
