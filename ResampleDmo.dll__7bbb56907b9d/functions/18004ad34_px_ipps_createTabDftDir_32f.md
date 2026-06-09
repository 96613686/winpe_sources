# px_ipps_createTabDftDir_32f

- ea: `0x18004ad34`
- end: `0x18004ad96`
- name: `px_ipps_createTabDftDir_32f`
- size: `98`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180047f10`
- `0x180048120`
- `0x18004f898`

## callees

- `0x180011040`
- `0x18004ad34`

## pseudocode

```c
__int64 __fastcall px_ipps_createTabDftDir_32f(int a1, __int64 *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  __int64 v7; // r9
  __int64 v8; // r10
  __int64 v9; // rax

  v3 = a1;
  result = px_ippsMalloc_8u((unsigned int)(8 * a1));
  v7 = 0;
  v8 = result;
  if ( result )
  {
    if ( (int)v3 > 0 )
    {
      do
      {
        v9 = *a2;
        a2 += a3 / (int)v3;
        *(_QWORD *)(v8 + 8 * v7++) = v9;
      }
      while ( v7 < v3 );
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18004ad34  mov     [rsp+arg_0], rbx
0x18004ad39  mov     [rsp+arg_8], rsi
0x18004ad3e  push    rdi
0x18004ad3f  sub     rsp, 20h
0x18004ad43  movsxd  rdi, ecx
0x18004ad46  mov     esi, r8d
0x18004ad49  mov     rbx, rdx
0x18004ad4c  mov     ecx, edi
0x18004ad4e  shl     ecx, 3
0x18004ad51  call    px_ippsMalloc_8u
0x18004ad56  xor     r9d, r9d
0x18004ad59  mov     r10, rax
0x18004ad5c  test    rax, rax
0x18004ad5f  jz      short loc_18004AD86
0x18004ad61  test    edi, edi
0x18004ad63  jle     short loc_18004AD83
0x18004ad65  mov     eax, esi
0x18004ad67  cdq
0x18004ad68  idiv    edi
0x18004ad6a  movsxd  rcx, eax
0x18004ad6d  shl     rcx, 3
0x18004ad71  mov     rax, [rbx]
0x18004ad74  add     rbx, rcx
0x18004ad77  mov     [r10+r9*8], rax
0x18004ad7b  inc     r9
0x18004ad7e  cmp     r9, rdi
0x18004ad81  jl      short loc_18004AD71
0x18004ad83  mov     rax, r10
0x18004ad86  mov     rbx, [rsp+28h+arg_0]
0x18004ad8b  mov     rsi, [rsp+28h+arg_8]
0x18004ad90  add     rsp, 20h
0x18004ad94  pop     rdi
0x18004ad95  retn
```
