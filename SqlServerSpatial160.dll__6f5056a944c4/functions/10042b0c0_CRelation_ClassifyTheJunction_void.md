# CRelation::ClassifyTheJunction(void)

- ea: `0x10042b0c0`
- end: `0x10042b15d`
- name: `?ClassifyTheJunction@CRelation@@MEAAXXZ`
- size: `157`
- prototype: `void __fastcall(CRelation *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path`

## callees

- `0x10042b0c0`

## pseudocode

```c
void __fastcall CRelation::ClassifyTheJunction(CRelation *this)
{
  __int64 v1; // rax
  __int64 v2; // rdx

  v1 = *((_QWORD *)this + 38);
  if ( v1 )
  {
    do
    {
      if ( (*(_WORD *)(v1 + 72) & 0x2600) == 0 )
        break;
      v1 = *(_QWORD *)(v1 + 24);
    }
    while ( v1 );
    while ( v1 )
    {
      v2 = *(_WORD *)(v1 + 72) & 1;
      if ( (*(_WORD *)(v1 + 72) & 0x4840) != 0 )
        ++*((_DWORD *)this + v2 + 143);
      else
        *((_BYTE *)this + v2 + 568) = 1;
      v1 = *(_QWORD *)(v1 + 24);
      if ( !v1 )
        break;
      do
      {
        if ( (*(_WORD *)(v1 + 72) & 0x2600) == 0 )
          break;
        v1 = *(_QWORD *)(v1 + 24);
      }
      while ( v1 );
    }
  }
}

```

## disassembly

```asm
0x10042b0c0  mov     rax, [rcx+130h]
0x10042b0c7  xor     r10d, r10d
0x10042b0ca  mov     r8, rcx
0x10042b0cd  mov     r9d, 2600h
0x10042b0d3  test    rax, rax
0x10042b0d6  jz      locret_10042B15C
0x10042b0dc  nop     dword ptr [rax+00h]
0x10042b0e0  movzx   edx, word ptr [rax+48h]
0x10042b0e4  and     dx, r9w
0x10042b0e8  cmp     r10w, dx
0x10042b0ec  jz      short loc_10042B0F7
0x10042b0ee  mov     rax, [rax+18h]
0x10042b0f2  test    rax, rax
0x10042b0f5  jnz     short loc_10042B0E0
0x10042b0f7  test    rax, rax
0x10042b0fa  jz      short locret_10042B15C
0x10042b0fc  mov     r11d, 4840h
0x10042b102  nop     dword ptr [rax+00h]
0x10042b106  nop     word ptr [rax+rax+00000000h]
0x10042b110  movzx   ecx, word ptr [rax+48h]
0x10042b114  mov     edx, ecx
0x10042b116  and     edx, 1
0x10042b119  test    r11w, cx
0x10042b11d  jz      short loc_10042B129
0x10042b11f  inc     dword ptr [r8+rdx*4+23Ch]
0x10042b127  jmp     short loc_10042B132
0x10042b129  mov     byte ptr [rdx+r8+238h], 1
0x10042b132  mov     rax, [rax+18h]
0x10042b136  test    rax, rax
0x10042b139  jz      short locret_10042B15C
0x10042b13b  nop     dword ptr [rax+rax+00h]
0x10042b140  movzx   ecx, word ptr [rax+48h]
0x10042b144  and     cx, r9w
0x10042b148  cmp     r10w, cx
0x10042b14c  jz      short loc_10042B157
0x10042b14e  mov     rax, [rax+18h]
0x10042b152  test    rax, rax
0x10042b155  jnz     short loc_10042B140
0x10042b157  test    rax, rax
0x10042b15a  jnz     short loc_10042B110
0x10042b15c  retn
```
