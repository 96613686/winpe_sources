# DloadObtainSection(ulong *,ulong *)

- ea: `0x1400014a0`
- end: `0x14000153b`
- name: `?DloadObtainSection@@YAPEAXPEAK0@Z`
- size: `155`
- prototype: `void *__fastcall(unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001f00`

## callees

- `0x1400014a0`

## pseudocode

```c
char *__fastcall DloadObtainSection(unsigned int *a1, unsigned int *a2)
{
  __int64 v4; // r10
  unsigned int v5; // r8d
  unsigned int v6; // r11d
  unsigned int v7; // r10d
  struct HINSTANCE__ *v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // edx

  if ( *(_DWORD *)&byte_140000040[(int)off_14000003C + 68] <= 0xDu )
    return 0;
  v4 = *(unsigned int *)&byte_140000040[(int)off_14000003C + 176];
  v5 = 0;
  if ( !(_DWORD)v4 )
    return 0;
  v6 = *(unsigned __int16 *)((char *)&word_140000006 + (int)off_14000003C);
  v7 = *(_DWORD *)((char *)&word_14000000C + v4);
  v8 = (struct HINSTANCE__ *)((char *)&_NULL_IMPORT_DESCRIPTOR
                            + (int)off_14000003C
                            + *(unsigned __int16 *)((char *)&word_140000014 + (int)off_14000003C)
                            + 24);
  if ( !(_WORD)v6 )
    return 0;
  while ( 1 )
  {
    v9 = *((_DWORD *)v8 + 3);
    if ( v7 >= v9 )
    {
      v10 = *((_DWORD *)v8 + 2);
      if ( v7 < v10 + v9 )
        break;
    }
    ++v5;
    v8 += 10;
    if ( v5 >= v6 )
      return 0;
  }
  *a1 = v10;
  *a2 = *((_DWORD *)v8 + 9);
  return (char *)&_NULL_IMPORT_DESCRIPTOR + *((unsigned int *)v8 + 3);
}

```

## disassembly

```asm
0x1400014a0  mov     [rsp+arg_0], rbx
0x1400014a5  mov     [rsp+arg_8], rsi
0x1400014aa  mov     [rsp+arg_10], rdi
0x1400014af  movsxd  r9, cs:off_14000003C
0x1400014b6  lea     rsi, __NULL_IMPORT_DESCRIPTOR
0x1400014bd  add     r9, rsi
0x1400014c0  mov     rbx, rdx
0x1400014c3  mov     rdi, rcx
0x1400014c6  cmp     dword ptr [r9+84h], 0Dh
0x1400014ce  jbe     short loc_140001519
0x1400014d0  mov     r10d, [r9+0F0h]
0x1400014d7  xor     r8d, r8d
0x1400014da  test    r10d, r10d
0x1400014dd  jz      short loc_140001519
0x1400014df  movzx   ecx, word ptr [r9+14h]
0x1400014e4  movzx   r11d, word ptr [r9+6]
0x1400014e9  add     rcx, 18h
0x1400014ed  mov     r10d, [r10+rsi+0Ch]
0x1400014f2  add     rcx, r9
0x1400014f5  cmp     r8w, r11w
0x1400014f9  jnb     short loc_140001519
0x1400014fb  mov     eax, [rcx+0Ch]
0x1400014fe  cmp     r10d, eax
0x140001501  jb      short loc_14000150D
0x140001503  mov     edx, [rcx+8]
0x140001506  add     eax, edx
0x140001508  cmp     r10d, eax
0x14000150b  jb      short loc_14000152B
0x14000150d  inc     r8d
0x140001510  add     rcx, 28h ; '('
0x140001514  cmp     r8d, r11d
0x140001517  jb      short loc_1400014FB
0x140001519  xor     eax, eax
0x14000151b  mov     rbx, [rsp+arg_0]
0x140001520  mov     rsi, [rsp+arg_8]
0x140001525  mov     rdi, [rsp+arg_10]
0x14000152a  retn
0x14000152b  mov     [rdi], edx
0x14000152d  mov     eax, [rcx+24h]
0x140001530  mov     [rbx], eax
0x140001532  mov     eax, [rcx+0Ch]
0x140001535  add     rax, rsi
0x140001538  jmp     short loc_14000151B
```
