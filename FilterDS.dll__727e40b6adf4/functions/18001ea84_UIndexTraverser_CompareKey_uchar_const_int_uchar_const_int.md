# UIndexTraverser::CompareKey(uchar const *,int,uchar const *,int)

- ea: `0x18001ea84`
- end: `0x18001eadb`
- name: `?CompareKey@UIndexTraverser@@AEAAHPEBEH0H@Z`
- size: `87`
- prototype: `__int64 __fastcall(UIndexTraverser *__hidden this, const unsigned __int8 *, int, const unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001eae4`
- `0x18001f2d0`

## callees

- `0x18001ea84`

## pseudocode

```c
__int64 __fastcall UIndexTraverser::CompareKey(
        UIndexTraverser *this,
        const unsigned __int8 *a2,
        int a3,
        const unsigned __int8 *a4,
        int a5)
{
  int v5; // r11d
  __int64 v7; // r10
  unsigned int v8; // ecx
  unsigned __int8 v9; // dl
  int v10; // r8d

  v5 = a3;
  if ( a3 >= a5 )
    v5 = a5;
  v7 = 0;
  v8 = 1;
  if ( v5 <= 0 )
  {
LABEL_7:
    v10 = a3 - a5;
    if ( v10 )
    {
      if ( v10 < 0 )
        return (unsigned int)-1;
      return v8;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    while ( 1 )
    {
      v9 = a4[v7];
      if ( a2[v7] < v9 )
        return 0xFFFFFFFFLL;
      if ( a2[v7] != v9 )
        return v8;
      v7 = (unsigned int)(v7 + 1);
      if ( (int)v7 >= v5 )
        goto LABEL_7;
    }
  }
}

```

## disassembly

```asm
0x18001ea84  mov     [rsp+arg_0], rdi
0x18001ea89  cmp     r8d, [rsp+arg_20]
0x18001ea8e  mov     r11d, r8d
0x18001ea91  mov     rdi, rdx
0x18001ea94  cmovge  r11d, [rsp+arg_20]
0x18001ea9a  xor     r10d, r10d
0x18001ea9d  lea     ecx, [r10+1]
0x18001eaa1  test    r11d, r11d
0x18001eaa4  jle     short loc_18001EABA
0x18001eaa6  mov     dl, [r10+r9]
0x18001eaaa  cmp     [r10+rdi], dl
0x18001eaae  jb      short loc_18001EAC5
0x18001eab0  jnz     short loc_18001EAD3
0x18001eab2  add     r10d, ecx
0x18001eab5  cmp     r10d, r11d
0x18001eab8  jl      short loc_18001EAA6
0x18001eaba  sub     r8d, [rsp+arg_20]
0x18001eabf  jnz     short loc_18001EACA
0x18001eac1  xor     eax, eax
0x18001eac3  jmp     short loc_18001EAD5
0x18001eac5  or      eax, 0FFFFFFFFh
0x18001eac8  jmp     short loc_18001EAD5
0x18001eaca  or      eax, 0FFFFFFFFh
0x18001eacd  test    r8d, r8d
0x18001ead0  cmovs   ecx, eax
0x18001ead3  mov     eax, ecx
0x18001ead5  mov     rdi, [rsp+arg_0]
0x18001eada  retn
```
