# av_buffer_replace

- ea: `0x18002f190`
- end: `0x18002f205`
- name: `av_buffer_replace`
- size: `117`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18003ba10`
- `0x18003bfe0`
- `0x180050880`

## callees

- `0x18002f150`
- `0x18002f190`
- `0x18002f2e8`

## pseudocode

```c
__int64 __fastcall av_buffer_replace(__int64 *a1, _QWORD *a2)
{
  _QWORD *v2; // r8
  __int64 v4; // rdi

  v2 = (_QWORD *)*a1;
  if ( a2 )
  {
    if ( v2 && *v2 == *a2 )
    {
      v2[1] = a2[1];
      v2[2] = a2[2];
    }
    else
    {
      v4 = av_buffer_ref(a2);
      if ( !v4 )
        return 4294967284LL;
      if ( *a1 )
        sub_18002F2E8(a1, 0);
      *a1 = v4;
    }
  }
  else if ( v2 )
  {
    sub_18002F2E8(a1, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18002f190  mov     [rsp+arg_0], rbx
0x18002f195  push    rdi
0x18002f196  sub     rsp, 20h
0x18002f19a  mov     r8, [rcx]
0x18002f19d  mov     rbx, rcx
0x18002f1a0  test    rdx, rdx
0x18002f1a3  jnz     short loc_18002F1B1
0x18002f1a5  test    r8, r8
0x18002f1a8  jz      short loc_18002F1F8
0x18002f1aa  call    sub_18002F2E8
0x18002f1af  jmp     short loc_18002F1F8
0x18002f1b1  test    r8, r8
0x18002f1b4  jz      short loc_18002F1D0
0x18002f1b6  mov     rax, [rdx]
0x18002f1b9  cmp     [r8], rax
0x18002f1bc  jnz     short loc_18002F1D0
0x18002f1be  mov     rax, [rdx+8]
0x18002f1c2  mov     [r8+8], rax
0x18002f1c6  mov     rax, [rdx+10h]
0x18002f1ca  mov     [r8+10h], rax
0x18002f1ce  jmp     short loc_18002F1F8
0x18002f1d0  mov     rcx, rdx
0x18002f1d3  call    av_buffer_ref
0x18002f1d8  mov     rdi, rax
0x18002f1db  test    rax, rax
0x18002f1de  jnz     short loc_18002F1E5
0x18002f1e0  lea     eax, [rdi-0Ch]
0x18002f1e3  jmp     short loc_18002F1FA
0x18002f1e5  cmp     qword ptr [rbx], 0
0x18002f1e9  jz      short loc_18002F1F5
0x18002f1eb  xor     edx, edx
0x18002f1ed  mov     rcx, rbx
0x18002f1f0  call    sub_18002F2E8
0x18002f1f5  mov     [rbx], rdi
0x18002f1f8  xor     eax, eax
0x18002f1fa  mov     rbx, [rsp+28h+arg_0]
0x18002f1ff  add     rsp, 20h
0x18002f203  pop     rdi
0x18002f204  retn
```
