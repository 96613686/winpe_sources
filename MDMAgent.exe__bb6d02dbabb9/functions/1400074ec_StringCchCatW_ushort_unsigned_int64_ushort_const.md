# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400074ec`
- end: `0x140007572`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `134`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140005144`
- `0x140007820`
- `0x14000a1a0`
- `0x14000a374`
- `0x14000bc88`
- `0x14000bdd4`
- `0x140010618`
- `0x140010718`

## callees

- `0x1400074ec`
- `0x14000768c`

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
0x1400074ec  mov     [rsp+arg_0], rbx
0x1400074f1  push    rdi
0x1400074f2  sub     rsp, 30h
0x1400074f6  lea     rax, [rdx-1]
0x1400074fa  mov     rbx, r8
0x1400074fd  mov     r10, rdx
0x140007500  mov     r11, rcx
0x140007503  cmp     rax, 7FFFFFFEh
0x140007509  ja      short loc_14000755F
0x14000750b  mov     r9, rdx
0x14000750e  mov     rax, rcx
0x140007511  xor     edi, edi
0x140007513  cmp     [rax], di
0x140007516  jz      short loc_140007522
0x140007518  add     rax, 2
0x14000751c  sub     r9, 1
0x140007520  jnz     short loc_140007513
0x140007522  mov     rax, r9
0x140007525  mov     rcx, r10
0x140007528  neg     rax
0x14000752b  mov     rax, r9
0x14000752e  sbb     edx, edx
0x140007530  sub     rcx, r9
0x140007533  not     edx
0x140007535  and     edx, 80070057h
0x14000753b  neg     rax
0x14000753e  sbb     r8, r8
0x140007541  and     r8, rcx; pcchNewDestLength
0x140007544  test    r9, r9
0x140007547  jz      short loc_140007564
0x140007549  sub     r10, r8
0x14000754c  lea     rcx, [r11+r8*2]; pszDest
0x140007550  mov     rdx, r10; cchDest
0x140007553  mov     r9, rbx; pszSrc
0x140007556  call    StringCopyWorkerW
0x14000755b  mov     edx, eax
0x14000755d  jmp     short loc_140007564
0x14000755f  mov     edx, 80070057h
0x140007564  mov     rbx, [rsp+38h+arg_0]
0x140007569  mov     eax, edx
0x14000756b  add     rsp, 30h
0x14000756f  pop     rdi
0x140007570  retn
```
