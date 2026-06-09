# jsonbPayloadSize

- ea: `0x180087c68`
- end: `0x180087dbb`
- name: `jsonbPayloadSize`
- size: `339`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, unsigned int *)`
- caller_count: `15`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180081d0c`
- `0x180081e68`
- `0x180082340`
- `0x1800834b0`
- `0x180083750`
- `0x1800839a8`
- `0x180083f44`
- `0x180084730`
- `0x180084cb8`
- `0x180085b84`
- `0x180086358`
- `0x180086570`
- `0x18008671c`
- `0x180087c08`
- `0x180087dc4`

## callees

- `0x180087c68`

## pseudocode

```c
__int64 __fastcall jsonbPayloadSize(__int64 *a1, unsigned int a2, unsigned int *a3)
{
  unsigned __int64 v3; // r10
  __int64 v5; // r9
  __int64 v6; // rsi
  unsigned __int8 v7; // al
  unsigned int v8; // r8d
  unsigned int v9; // edx
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // rax
  int v13; // r8d
  int v14; // r8d
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  unsigned __int64 v18; // r9

  v3 = *((unsigned int *)a1 + 2);
  if ( a2 > (unsigned int)v3 )
    goto LABEL_25;
  v5 = *a1;
  v6 = a2;
  v7 = *(_BYTE *)(*a1 + a2) >> 4;
  if ( v7 > 0xBu )
  {
    if ( v7 == 12 )
    {
      v10 = a2 + 1;
      if ( (unsigned int)v10 < (unsigned int)v3 )
      {
        v8 = *(unsigned __int8 *)(v10 + v5);
        v9 = 2;
        goto LABEL_21;
      }
LABEL_25:
      *a3 = 0;
      return 0;
    }
    if ( v7 == 13 )
    {
      v11 = a2 + 2;
      if ( (unsigned int)v11 >= (unsigned int)v3 )
        goto LABEL_25;
      v12 = a2 + 1;
      v9 = 3;
      v13 = *(unsigned __int8 *)(v12 + v5) << 8;
    }
    else
    {
      if ( v7 == 14 )
      {
        v11 = a2 + 4;
        if ( (unsigned int)v11 >= (unsigned int)v3 )
          goto LABEL_25;
        v14 = (*(unsigned __int8 *)(a2 + 3 + v5) << 8) + (*(unsigned __int8 *)(a2 + 2 + v5) << 16);
        v15 = a2 + 1;
        v9 = 5;
        v16 = *(unsigned __int8 *)(v15 + v5) << 24;
      }
      else
      {
        v11 = a2 + 8;
        if ( (unsigned int)v11 >= (unsigned int)v3
          || *(_BYTE *)(a2 + 1 + v5)
          || *(_BYTE *)(a2 + 2 + v5)
          || *(_BYTE *)(a2 + 3 + v5)
          || *(_BYTE *)(a2 + 4 + v5) )
        {
          goto LABEL_25;
        }
        v14 = (*(unsigned __int8 *)(a2 + 6 + v5) << 16) + (*(unsigned __int8 *)(a2 + 5 + v5) << 24);
        v17 = a2 + 7;
        v9 = 9;
        v16 = *(unsigned __int8 *)(v17 + v5) << 8;
      }
      v13 = v16 + v14;
    }
    v8 = *(unsigned __int8 *)(v11 + v5) + v13;
    goto LABEL_21;
  }
  v8 = v7;
  v9 = 1;
LABEL_21:
  v18 = v6 + v9 + v8;
  if ( v18 > v3 && v18 > (unsigned int)(v3 - *((_DWORD *)a1 + 13)) )
  {
    v8 = 0;
    v9 = 0;
  }
  *a3 = v8;
  return v9;
}

```

## disassembly

```asm
0x180087c68  push    rbx
0x180087c6a  push    rsi
0x180087c6b  push    rdi
0x180087c6c  mov     r10d, [rcx+8]
0x180087c70  mov     rdi, r8
0x180087c73  mov     r11, rcx
0x180087c76  cmp     edx, r10d
0x180087c79  ja      loc_180087DAE
0x180087c7f  mov     r9, [rcx]
0x180087c82  mov     esi, edx
0x180087c84  mov     al, [r9+rsi]
0x180087c88  shr     al, 4
0x180087c8b  cmp     al, 0Bh
0x180087c8d  ja      short loc_180087C9D
0x180087c8f  movzx   r8d, al
0x180087c93  mov     edx, 1
0x180087c98  jmp     loc_180087D86
0x180087c9d  cmp     al, 0Ch
0x180087c9f  jnz     short loc_180087CBB
0x180087ca1  inc     edx
0x180087ca3  cmp     edx, r10d
0x180087ca6  jnb     loc_180087DAE
0x180087cac  movzx   r8d, byte ptr [rdx+r9]
0x180087cb1  mov     edx, 2
0x180087cb6  jmp     loc_180087D86
0x180087cbb  cmp     al, 0Dh
0x180087cbd  jnz     short loc_180087CE1
0x180087cbf  lea     ebx, [rdx+2]
0x180087cc2  cmp     ebx, r10d
0x180087cc5  jnb     loc_180087DAE
0x180087ccb  lea     eax, [rdx+1]
0x180087cce  mov     edx, 3
0x180087cd3  movzx   r8d, byte ptr [rax+r9]
0x180087cd8  shl     r8d, 8
0x180087cdc  jmp     loc_180087D7E
0x180087ce1  cmp     al, 0Eh
0x180087ce3  jnz     short loc_180087D1D
0x180087ce5  lea     ebx, [rdx+4]
0x180087ce8  cmp     ebx, r10d
0x180087ceb  jnb     loc_180087DAE
0x180087cf1  lea     eax, [rdx+2]
0x180087cf4  movzx   r8d, byte ptr [rax+r9]
0x180087cf9  lea     eax, [rdx+3]
0x180087cfc  movzx   eax, byte ptr [rax+r9]
0x180087d01  shl     eax, 8
0x180087d04  shl     r8d, 10h
0x180087d08  add     r8d, eax
0x180087d0b  lea     eax, [rdx+1]
0x180087d0e  mov     edx, 5
0x180087d13  movzx   eax, byte ptr [rax+r9]
0x180087d18  shl     eax, 18h
0x180087d1b  jmp     short loc_180087D7B
0x180087d1d  lea     ebx, [rdx+8]
0x180087d20  cmp     ebx, r10d
0x180087d23  jnb     loc_180087DAE
0x180087d29  lea     eax, [rdx+1]
0x180087d2c  cmp     byte ptr [rax+r9], 0
0x180087d31  jnz     short loc_180087DAE
0x180087d33  lea     eax, [rdx+2]
0x180087d36  cmp     byte ptr [rax+r9], 0
0x180087d3b  jnz     short loc_180087DAE
0x180087d3d  lea     eax, [rdx+3]
0x180087d40  cmp     byte ptr [rax+r9], 0
0x180087d45  jnz     short loc_180087DAE
0x180087d47  lea     eax, [rdx+4]
0x180087d4a  cmp     byte ptr [rax+r9], 0
0x180087d4f  jnz     short loc_180087DAE
0x180087d51  lea     eax, [rdx+5]
0x180087d54  movzx   r8d, byte ptr [rax+r9]
0x180087d59  lea     eax, [rdx+6]
0x180087d5c  movzx   eax, byte ptr [rax+r9]
0x180087d61  shl     eax, 10h
0x180087d64  shl     r8d, 18h
0x180087d68  add     r8d, eax
0x180087d6b  lea     eax, [rdx+7]
0x180087d6e  mov     edx, 9
0x180087d73  movzx   eax, byte ptr [rax+r9]
0x180087d78  shl     eax, 8
0x180087d7b  add     r8d, eax
0x180087d7e  movzx   ecx, byte ptr [rbx+r9]
0x180087d83  add     r8d, ecx
0x180087d86  mov     eax, edx
0x180087d88  add     rax, rsi
0x180087d8b  mov     r9d, r8d
0x180087d8e  add     r9, rax
0x180087d91  cmp     r9, r10
0x180087d94  jbe     short loc_180087DA7
0x180087d96  sub     r10d, [r11+34h]
0x180087d9a  mov     eax, r10d
0x180087d9d  cmp     r9, rax
0x180087da0  jbe     short loc_180087DA7
0x180087da2  xor     r8d, r8d
0x180087da5  xor     edx, edx
0x180087da7  mov     [rdi], r8d
0x180087daa  mov     eax, edx
0x180087dac  jmp     short loc_180087DB7
0x180087dae  mov     dword ptr [r8], 0
0x180087db5  xor     eax, eax
0x180087db7  pop     rdi
0x180087db8  pop     rsi
0x180087db9  pop     rbx
0x180087dba  retn
```
