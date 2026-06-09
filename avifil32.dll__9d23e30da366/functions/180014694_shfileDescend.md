# shfileDescend

- ea: `0x180014694`
- end: `0x18001473b`
- name: `shfileDescend`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800059c0`
- `0x18000a060`
- `0x18000d0dc`

## callees

- `0x180014694`
- `0x180014880`
- `0x180014928`

## pseudocode

```c
__int64 __fastcall shfileDescend(__int64 a1, __int64 a2, __int64 a3)
{
  LONG v6; // eax

  *(_DWORD *)(a2 + 16) = 0;
  if ( shfileRead(a1, (char *)a2, 8u) == 8 )
  {
    v6 = shfileSeek(a1, 0, 1);
    *(_DWORD *)(a2 + 12) = v6;
    if ( v6 == -1 )
      return 263;
    if ( !a3 || v6 - 8 < (unsigned int)(*(_DWORD *)(a3 + 4) + *(_DWORD *)(a3 + 12)) )
    {
      if ( *(_DWORD *)a2 != 1179011410 && *(_DWORD *)a2 != 1414744396 )
      {
        *(_DWORD *)(a2 + 8) = 0;
        return 0;
      }
      if ( shfileRead(a1, (char *)(a2 + 8), 4u) == 4 )
        return 0;
    }
  }
  return 265;
}

```

## disassembly

```asm
0x180014694  mov     [rsp+arg_0], rbx
0x180014699  mov     [rsp+arg_8], rsi
0x18001469e  push    rdi
0x18001469f  sub     rsp, 20h
0x1800146a3  mov     rdi, r8
0x1800146a6  mov     dword ptr [rdx+10h], 0
0x1800146ad  mov     r8d, 8
0x1800146b3  mov     rbx, rdx
0x1800146b6  mov     rsi, rcx
0x1800146b9  call    shfileRead
0x1800146be  cmp     eax, 8
0x1800146c1  jnz     short loc_180014726
0x1800146c3  xor     edx, edx
0x1800146c5  lea     r8d, [rax-7]
0x1800146c9  mov     rcx, rsi
0x1800146cc  call    shfileSeek
0x1800146d1  mov     [rbx+0Ch], eax
0x1800146d4  cmp     eax, 0FFFFFFFFh
0x1800146d7  jz      short loc_18001471F
0x1800146d9  test    rdi, rdi
0x1800146dc  jz      short loc_1800146EB
0x1800146de  mov     ecx, [rdi+0Ch]
0x1800146e1  add     eax, 0FFFFFFF8h
0x1800146e4  add     ecx, [rdi+4]
0x1800146e7  cmp     eax, ecx
0x1800146e9  jnb     short loc_180014726
0x1800146eb  cmp     dword ptr [rbx], 46464952h
0x1800146f1  jz      short loc_180014704
0x1800146f3  cmp     dword ptr [rbx], 5453494Ch
0x1800146f9  jz      short loc_180014704
0x1800146fb  mov     dword ptr [rbx+8], 0
0x180014702  jmp     short loc_18001471B
0x180014704  lea     rdx, [rbx+8]
0x180014708  mov     r8d, 4
0x18001470e  mov     rcx, rsi
0x180014711  call    shfileRead
0x180014716  cmp     eax, 4
0x180014719  jnz     short loc_180014726
0x18001471b  xor     eax, eax
0x18001471d  jmp     short loc_18001472B
0x18001471f  mov     eax, 107h
0x180014724  jmp     short loc_18001472B
0x180014726  mov     eax, 109h
0x18001472b  mov     rbx, [rsp+28h+arg_0]
0x180014730  mov     rsi, [rsp+28h+arg_8]
0x180014735  add     rsp, 20h
0x180014739  pop     rdi
0x18001473a  retn
```
