# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800052f8`
- end: `0x18000537e`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `134`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003470`
- `0x180005548`
- `0x180008e10`

## callees

- `0x1800052f8`
- `0x18000542c`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v5; // r9
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // r8
  size_t v10; // [rsp+20h] [rbp-18h]

  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    if ( v5 )
    {
      v8 = (a2 - v5) & -(__int64)(v5 != 0);
      return (unsigned int)StringCopyWorkerW(&a1[v8], a2 - v8, (size_t *)v8, a3, v10);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800052f8  mov     [rsp+arg_0], rbx
0x1800052fd  push    rdi
0x1800052fe  sub     rsp, 30h
0x180005302  lea     rax, [rdx-1]
0x180005306  mov     rbx, r8
0x180005309  mov     r10, rdx
0x18000530c  mov     r11, rcx
0x18000530f  cmp     rax, 7FFFFFFEh
0x180005315  ja      short loc_18000536B
0x180005317  mov     r9, rdx
0x18000531a  mov     rax, rcx
0x18000531d  xor     edi, edi
0x18000531f  cmp     [rax], di
0x180005322  jz      short loc_18000532E
0x180005324  add     rax, 2
0x180005328  sub     r9, 1
0x18000532c  jnz     short loc_18000531F
0x18000532e  mov     rax, r9
0x180005331  mov     rcx, r10
0x180005334  neg     rax
0x180005337  mov     rax, r9
0x18000533a  sbb     edx, edx
0x18000533c  sub     rcx, r9
0x18000533f  not     edx
0x180005341  and     edx, 80070057h
0x180005347  neg     rax
0x18000534a  sbb     r8, r8
0x18000534d  and     r8, rcx; pcchNewDestLength
0x180005350  test    r9, r9
0x180005353  jz      short loc_180005370
0x180005355  sub     r10, r8
0x180005358  lea     rcx, [r11+r8*2]; pszDest
0x18000535c  mov     rdx, r10; cchDest
0x18000535f  mov     r9, rbx; pszSrc
0x180005362  call    StringCopyWorkerW
0x180005367  mov     edx, eax
0x180005369  jmp     short loc_180005370
0x18000536b  mov     edx, 80070057h
0x180005370  mov     rbx, [rsp+38h+arg_0]
0x180005375  mov     eax, edx
0x180005377  add     rsp, 30h
0x18000537b  pop     rdi
0x18000537c  retn
```
