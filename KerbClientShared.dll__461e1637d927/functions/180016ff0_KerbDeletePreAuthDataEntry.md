# KerbDeletePreAuthDataEntry

- ea: `0x180016ff0`
- end: `0x18001703e`
- name: `KerbDeletePreAuthDataEntry`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016328`
- `0x180016680`

## callees

- `0x180007e10`
- `0x180016ff0`

## pseudocode

```c
void __fastcall KerbDeletePreAuthDataEntry(int a1, void **a2)
{
  void *v2; // rbx
  _QWORD *v3; // r8
  void *v4; // rax

  v2 = *a2;
  v3 = 0;
  if ( *a2 )
  {
    while ( 1 )
    {
      v4 = *(void **)v2;
      if ( *((_DWORD *)v2 + 2) == a1 )
        break;
      v3 = v2;
      v2 = *(void **)v2;
      if ( !v4 )
        return;
    }
    if ( v3 )
      *v3 = v4;
    else
      *a2 = v4;
    MIDL_user_free(*((void **)v2 + 3));
    MIDL_user_free(v2);
  }
}

```

## disassembly

```asm
0x180016ff0  push    rbx
0x180016ff2  sub     rsp, 20h
0x180016ff6  mov     rbx, [rdx]
0x180016ff9  xor     r8d, r8d
0x180016ffc  test    rbx, rbx
0x180016fff  jz      short loc_180017038
0x180017001  mov     rax, [rbx]
0x180017004  cmp     [rbx+8], ecx
0x180017007  jz      short loc_18001701A
0x180017009  mov     r8, rbx
0x18001700c  mov     rbx, rax
0x18001700f  test    rax, rax
0x180017012  jnz     short loc_180017001
0x180017014  add     rsp, 20h
0x180017018  pop     rbx
0x180017019  retn
0x18001701a  test    r8, r8
0x18001701d  jz      short loc_180017024
0x18001701f  mov     [r8], rax
0x180017022  jmp     short loc_180017027
0x180017024  mov     [rdx], rax
0x180017027  mov     rcx, [rbx+18h]; void *
0x18001702b  call    MIDL_user_free
0x180017030  mov     rcx, rbx; void *
0x180017033  call    MIDL_user_free
0x180017038  add     rsp, 20h
0x18001703c  pop     rbx
0x18001703d  retn
```
