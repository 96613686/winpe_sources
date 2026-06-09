# RobustIntersections::EaCompare(uint const *,int,uint const *,int)

- ea: `0x10042a7a0`
- end: `0x10042a874`
- name: `?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z`
- size: `212`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100429a30`
- `0x100447050`
- `0x100447250`
- `0x100447890`
- `0x100448790`
- `0x100448990`
- `0x100449070`
- `0x100449c10`
- `0x10044a130`
- `0x10044a510`
- `0x10044a900`
- `0x10044aed0`
- `0x10044b4a0`

## callees

- `0x10042a7a0`

## pseudocode

```c
__int64 __fastcall RobustIntersections::EaCompare(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4)
{
  unsigned int v4; // r11d
  __int64 i; // r10
  bool v8; // zf
  int v9; // r8d
  __int64 j; // rcx
  int v11; // ecx
  __int64 result; // rax
  __int64 v13; // rdx
  __int64 v14; // rbx
  unsigned int *v15; // r9
  unsigned int v16; // r8d
  unsigned int v17; // ecx

  v4 = 0;
  for ( i = a1 + 4LL * a2; a2; --a2 )
  {
    v8 = *(_DWORD *)(i - 4) == 0;
    i -= 4;
    if ( !v8 )
      break;
  }
  v9 = 1;
  if ( a2 )
    v9 = a2;
  for ( j = a3 + 4LL * a4; a4; --a4 )
  {
    v8 = *(_DWORD *)(j - 4) == 0;
    j -= 4;
    if ( !v8 )
      break;
  }
  v11 = 1;
  if ( a4 )
    v11 = a4;
  if ( v9 == v11 )
  {
    v13 = v9;
    v14 = a3 - a1;
    v15 = (unsigned int *)(a1 + 4LL * v9);
    while ( 1 )
    {
      if ( v13 <= 0 )
        return v4;
      v16 = *(unsigned int *)((char *)v15-- + v14 - 4);
      --v13;
      v17 = *v15;
      if ( *v15 > v16 )
        break;
      v4 = -(v16 != v17);
      if ( v17 != v16 )
        return v4;
    }
    return 1;
  }
  else
  {
    result = 0xFFFFFFFFLL;
    if ( v9 > v11 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x10042a7a0  mov     [rsp+arg_0], rbx
0x10042a7a5  mov     [rsp+arg_8], rdi
0x10042a7aa  mov     eax, edx
0x10042a7ac  xor     r11d, r11d
0x10042a7af  mov     rbx, r8
0x10042a7b2  mov     rdi, rcx
0x10042a7b5  lea     r10, [rcx+rax*4]
0x10042a7b9  test    edx, edx
0x10042a7bb  jz      short loc_10042A7CF
0x10042a7bd  nop     dword ptr [rax]
0x10042a7c0  cmp     [r10-4], r11d
0x10042a7c4  lea     r10, [r10-4]
0x10042a7c8  jnz     short loc_10042A7CF
0x10042a7ca  add     edx, 0FFFFFFFFh
0x10042a7cd  jnz     short loc_10042A7C0
0x10042a7cf  test    edx, edx
0x10042a7d1  mov     eax, r9d
0x10042a7d4  mov     r10d, 1
0x10042a7da  mov     r8d, r10d
0x10042a7dd  cmovnz  r8d, edx
0x10042a7e1  lea     rcx, [rbx+rax*4]
0x10042a7e5  test    r9d, r9d
0x10042a7e8  jz      short loc_10042A800
0x10042a7ea  nop     word ptr [rax+rax+00h]
0x10042a7f0  cmp     [rcx-4], r11d
0x10042a7f4  lea     rcx, [rcx-4]
0x10042a7f8  jnz     short loc_10042A800
0x10042a7fa  add     r9d, 0FFFFFFFFh
0x10042a7fe  jnz     short loc_10042A7F0
0x10042a800  test    r9d, r9d
0x10042a803  mov     ecx, r10d
0x10042a806  cmovnz  ecx, r9d
0x10042a80a  cmp     r8d, ecx
0x10042a80d  jz      short loc_10042A823
0x10042a80f  mov     eax, 0FFFFFFFFh
0x10042a814  cmovg   eax, r10d
0x10042a818  mov     rbx, [rsp+arg_0]
0x10042a81d  mov     rdi, [rsp+arg_8]
0x10042a822  retn
0x10042a823  movsxd  rdx, r8d
0x10042a826  sub     rbx, rdi
0x10042a829  lea     r9, [rdi+rdx*4]
0x10042a82d  nop     dword ptr [rax]
0x10042a830  test    rdx, rdx
0x10042a833  jle     short loc_10042A858
0x10042a835  mov     r8d, [rbx+r9-4]
0x10042a83a  sub     r9, 4
0x10042a83e  dec     rdx
0x10042a841  mov     ecx, [r9]
0x10042a844  cmp     ecx, r8d
0x10042a847  ja      short loc_10042A866
0x10042a849  mov     eax, ecx
0x10042a84b  sub     eax, r8d
0x10042a84e  neg     eax
0x10042a850  sbb     r11d, r11d
0x10042a853  cmp     ecx, r8d
0x10042a856  jz      short loc_10042A830
0x10042a858  mov     eax, r11d
0x10042a85b  mov     rbx, [rsp+arg_0]
0x10042a860  mov     rdi, [rsp+arg_8]
0x10042a865  retn
0x10042a866  mov     rbx, [rsp+arg_0]
0x10042a86b  mov     eax, r10d
0x10042a86e  mov     rdi, [rsp+arg_8]
0x10042a873  retn
```
