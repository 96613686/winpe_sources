# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140007230`
- end: `0x1400072b5`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `133`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140004fe4`
- `0x140007560`
- `0x140009d3c`
- `0x140009f10`
- `0x14000b754`
- `0x14000b894`
- `0x14000fe10`
- `0x14000ff08`

## callees

- `0x140007230`
- `0x1400073cc`

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
0x140007230  mov     [rsp+arg_0], rbx
0x140007235  push    rdi
0x140007236  sub     rsp, 30h
0x14000723a  lea     rax, [rdx-1]
0x14000723e  mov     rbx, r8
0x140007241  mov     r10, rdx
0x140007244  mov     r11, rcx
0x140007247  cmp     rax, 7FFFFFFEh
0x14000724d  ja      short loc_1400072A3
0x14000724f  mov     r9, rdx
0x140007252  mov     rax, rcx
0x140007255  xor     edi, edi
0x140007257  cmp     [rax], di
0x14000725a  jz      short loc_140007266
0x14000725c  add     rax, 2
0x140007260  sub     r9, 1
0x140007264  jnz     short loc_140007257
0x140007266  mov     rax, r9
0x140007269  mov     rcx, r10
0x14000726c  neg     rax
0x14000726f  mov     rax, r9
0x140007272  sbb     edx, edx
0x140007274  sub     rcx, r9
0x140007277  not     edx
0x140007279  and     edx, 80070057h
0x14000727f  neg     rax
0x140007282  sbb     r8, r8
0x140007285  and     r8, rcx; pcchNewDestLength
0x140007288  test    r9, r9
0x14000728b  jz      short loc_1400072A8
0x14000728d  sub     r10, r8
0x140007290  lea     rcx, [r11+r8*2]; pszDest
0x140007294  mov     rdx, r10; cchDest
0x140007297  mov     r9, rbx; pszSrc
0x14000729a  call    StringCopyWorkerW
0x14000729f  mov     edx, eax
0x1400072a1  jmp     short loc_1400072A8
0x1400072a3  mov     edx, 80070057h
0x1400072a8  mov     rbx, [rsp+38h+arg_0]
0x1400072ad  mov     eax, edx
0x1400072af  add     rsp, 30h
0x1400072b3  pop     rdi
0x1400072b4  retn
```
