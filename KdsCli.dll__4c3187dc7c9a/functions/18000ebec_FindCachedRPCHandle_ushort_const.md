# FindCachedRPCHandle(ushort const *)

- ea: `0x18000ebec`
- end: `0x18000ec4e`
- name: `?FindCachedRPCHandle@@YAPEAU_RPC_HANDLE_CACHE@@PEBG@Z`
- size: `98`
- prototype: `struct _RPC_HANDLE_CACHE *__fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eab8`
- `0x18000edb8`

## callees

- `0x18000ebec`

## pseudocode

```c
struct _RPC_HANDLE_CACHE *__fastcall FindCachedRPCHandle(char *a1)
{
  __int64 *v1; // rax
  _QWORD *v3; // rdx
  char *v4; // rcx
  char *v5; // r8
  int v6; // r10d
  int v7; // r9d

  v1 = (__int64 *)qword_1800234C8;
  if ( qword_1800234C8 )
  {
    while ( v1 != &qword_1800234C8 )
    {
      v3 = (_QWORD *)*(v1 - 1);
      v4 = (char *)v3[1];
      v5 = (char *)(a1 - v4);
      do
      {
        v6 = *(unsigned __int16 *)&v5[(_QWORD)v4];
        v7 = *(unsigned __int16 *)v4 - v6;
        if ( v7 )
          break;
        v4 += 2;
      }
      while ( v6 );
      if ( !v7 && *v3 )
        return (struct _RPC_HANDLE_CACHE *)*(v1 - 1);
      v1 = (__int64 *)*v1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ebec  mov     [rsp+arg_0], rbx
0x18000ebf1  mov     rax, cs:qword_1800234C8
0x18000ebf8  mov     r11, rcx
0x18000ebfb  test    rax, rax
0x18000ebfe  jz      short loc_18000EC41
0x18000ec00  lea     rbx, qword_1800234C8
0x18000ec07  jmp     short loc_18000EC3C
0x18000ec09  mov     rdx, [rax-8]
0x18000ec0d  mov     r8, r11
0x18000ec10  mov     rcx, [rdx+8]
0x18000ec14  sub     r8, rcx
0x18000ec17  movzx   r9d, word ptr [rcx]
0x18000ec1b  movzx   r10d, word ptr [rcx+r8]
0x18000ec20  sub     r9d, r10d
0x18000ec23  jnz     short loc_18000EC2E
0x18000ec25  add     rcx, 2
0x18000ec29  test    r10d, r10d
0x18000ec2c  jnz     short loc_18000EC17
0x18000ec2e  test    r9d, r9d
0x18000ec31  jnz     short loc_18000EC39
0x18000ec33  cmp     qword ptr [rdx], 0
0x18000ec37  jnz     short loc_18000EC49
0x18000ec39  mov     rax, [rax]
0x18000ec3c  cmp     rax, rbx
0x18000ec3f  jnz     short loc_18000EC09
0x18000ec41  xor     eax, eax
0x18000ec43  mov     rbx, [rsp+arg_0]
0x18000ec48  retn
0x18000ec49  mov     rax, rdx
0x18000ec4c  jmp     short loc_18000EC43
```
