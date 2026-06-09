# jsonbPayloadSize

- ea: `0x180078a58`
- end: `0x180078bab`
- name: `jsonbPayloadSize`
- size: `339`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180072aa4`
- `0x180072c00`
- `0x1800730d8`
- `0x180074260`
- `0x180074500`
- `0x180074758`
- `0x180074d08`
- `0x1800754f0`
- `0x180075a9c`
- `0x180076974`
- `0x180077148`
- `0x180077360`
- `0x18007750c`
- `0x1800789f8`
- `0x180078bb4`

## callees

- `0x180078a58`

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
0x180078a58  push    rbx
0x180078a5a  push    rsi
0x180078a5b  push    rdi
0x180078a5c  mov     r10d, [rcx+8]
0x180078a60  mov     rdi, r8
0x180078a63  mov     r11, rcx
0x180078a66  cmp     edx, r10d
0x180078a69  ja      loc_180078B9E
0x180078a6f  mov     r9, [rcx]
0x180078a72  mov     esi, edx
0x180078a74  mov     al, [r9+rsi]
0x180078a78  shr     al, 4
0x180078a7b  cmp     al, 0Bh
0x180078a7d  ja      short loc_180078A8D
0x180078a7f  movzx   r8d, al
0x180078a83  mov     edx, 1
0x180078a88  jmp     loc_180078B76
0x180078a8d  cmp     al, 0Ch
0x180078a8f  jnz     short loc_180078AAB
0x180078a91  inc     edx
0x180078a93  cmp     edx, r10d
0x180078a96  jnb     loc_180078B9E
0x180078a9c  movzx   r8d, byte ptr [rdx+r9]
0x180078aa1  mov     edx, 2
0x180078aa6  jmp     loc_180078B76
0x180078aab  cmp     al, 0Dh
0x180078aad  jnz     short loc_180078AD1
0x180078aaf  lea     ebx, [rdx+2]
0x180078ab2  cmp     ebx, r10d
0x180078ab5  jnb     loc_180078B9E
0x180078abb  lea     eax, [rdx+1]
0x180078abe  mov     edx, 3
0x180078ac3  movzx   r8d, byte ptr [rax+r9]
0x180078ac8  shl     r8d, 8
0x180078acc  jmp     loc_180078B6E
0x180078ad1  cmp     al, 0Eh
0x180078ad3  jnz     short loc_180078B0D
0x180078ad5  lea     ebx, [rdx+4]
0x180078ad8  cmp     ebx, r10d
0x180078adb  jnb     loc_180078B9E
0x180078ae1  lea     eax, [rdx+2]
0x180078ae4  movzx   r8d, byte ptr [rax+r9]
0x180078ae9  lea     eax, [rdx+3]
0x180078aec  movzx   eax, byte ptr [rax+r9]
0x180078af1  shl     eax, 8
0x180078af4  shl     r8d, 10h
0x180078af8  add     r8d, eax
0x180078afb  lea     eax, [rdx+1]
0x180078afe  mov     edx, 5
0x180078b03  movzx   eax, byte ptr [rax+r9]
0x180078b08  shl     eax, 18h
0x180078b0b  jmp     short loc_180078B6B
0x180078b0d  lea     ebx, [rdx+8]
0x180078b10  cmp     ebx, r10d
0x180078b13  jnb     loc_180078B9E
0x180078b19  lea     eax, [rdx+1]
0x180078b1c  cmp     byte ptr [rax+r9], 0
0x180078b21  jnz     short loc_180078B9E
0x180078b23  lea     eax, [rdx+2]
0x180078b26  cmp     byte ptr [rax+r9], 0
0x180078b2b  jnz     short loc_180078B9E
0x180078b2d  lea     eax, [rdx+3]
0x180078b30  cmp     byte ptr [rax+r9], 0
0x180078b35  jnz     short loc_180078B9E
0x180078b37  lea     eax, [rdx+4]
0x180078b3a  cmp     byte ptr [rax+r9], 0
0x180078b3f  jnz     short loc_180078B9E
0x180078b41  lea     eax, [rdx+5]
0x180078b44  movzx   r8d, byte ptr [rax+r9]
0x180078b49  lea     eax, [rdx+6]
0x180078b4c  movzx   eax, byte ptr [rax+r9]
0x180078b51  shl     eax, 10h
0x180078b54  shl     r8d, 18h
0x180078b58  add     r8d, eax
0x180078b5b  lea     eax, [rdx+7]
0x180078b5e  mov     edx, 9
0x180078b63  movzx   eax, byte ptr [rax+r9]
0x180078b68  shl     eax, 8
0x180078b6b  add     r8d, eax
0x180078b6e  movzx   ecx, byte ptr [rbx+r9]
0x180078b73  add     r8d, ecx
0x180078b76  mov     eax, edx
0x180078b78  add     rax, rsi
0x180078b7b  mov     r9d, r8d
0x180078b7e  add     r9, rax
0x180078b81  cmp     r9, r10
0x180078b84  jbe     short loc_180078B97
0x180078b86  sub     r10d, [r11+34h]
0x180078b8a  mov     eax, r10d
0x180078b8d  cmp     r9, rax
0x180078b90  jbe     short loc_180078B97
0x180078b92  xor     r8d, r8d
0x180078b95  xor     edx, edx
0x180078b97  mov     [rdi], r8d
0x180078b9a  mov     eax, edx
0x180078b9c  jmp     short loc_180078BA7
0x180078b9e  mov     dword ptr [r8], 0
0x180078ba5  xor     eax, eax
0x180078ba7  pop     rdi
0x180078ba8  pop     rsi
0x180078ba9  pop     rbx
0x180078baa  retn
```
