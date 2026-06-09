# std::istreambuf_iterator<wchar_t,std::char_traits<wchar_t>>::equal(std::istreambuf_iterator<wchar_t,std::char_traits<wchar_t>> const &)

- ea: `0x18001c5d8`
- end: `0x18001c6ab`
- name: `?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z`
- size: `211`
- prototype: `char __fastcall(__int64 *, __int64 *)`
- caller_count: `43`
- callee_count: `2`
- tags: ``

## callers

- `0x180008c34`
- `0x180008e00`
- `0x18000d948`
- `0x18000e050`
- `0x18000e758`
- `0x18000eee8`
- `0x18000f678`
- `0x18000f850`
- `0x18000fa28`
- `0x18000fe64`
- `0x1800102a0`
- `0x18001046c`
- `0x18001108c`
- `0x180016290`
- `0x1800163a0`
- `0x180016500`
- `0x180016610`
- `0x180016770`
- `0x1800168c0`
- `0x180016a10`
- `0x180016b40`
- `0x180016c70`
- `0x180016d70`
- `0x180016e70`
- `0x180016f70`
- `0x1800170a0`
- `0x1800171d0`
- `0x180017300`
- `0x180017580`
- `0x1800176d0`
- `0x180017820`
- `0x180017950`
- `0x180017a80`
- `0x180017b80`
- `0x180017c80`
- `0x180017d80`
- `0x180017eb0`
- `0x180017fe0`
- `0x180018110`
- `0x180018390`
- `0x180018890`
- `0x180018d90`
- `0x180019340`

## callees

- `0x18001c5d8`
- `0x180037010`

## pseudocode

```c
char __fastcall std::istreambuf_iterator<wchar_t>::equal(__int64 *a1, __int64 *a2)
{
  char v4; // si
  __int64 v5; // rcx
  __int16 *v6; // rdx
  __int16 v7; // ax
  __int64 v8; // rcx
  __int16 *v9; // rdx
  __int16 v10; // ax

  v4 = 1;
  if ( !*((_BYTE *)a1 + 8) )
  {
    v5 = *a1;
    if ( !v5
      || ((v6 = **(__int16 ***)(v5 + 56)) == 0 || **(int **)(v5 + 80) <= 0
        ? (v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 48LL))(v5))
        : (v7 = *v6),
          v7 == -1) )
    {
      *a1 = 0;
    }
    else
    {
      *((_WORD *)a1 + 5) = v7;
    }
    *((_BYTE *)a1 + 8) = 1;
  }
  if ( !*((_BYTE *)a2 + 8) )
  {
    v8 = *a2;
    if ( !*a2
      || ((v9 = **(__int16 ***)(v8 + 56)) == 0 || **(int **)(v8 + 80) <= 0
        ? (v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 48LL))(v8))
        : (v10 = *v9),
          v10 == -1) )
    {
      *a2 = 0;
    }
    else
    {
      *((_WORD *)a2 + 5) = v10;
    }
    *((_BYTE *)a2 + 8) = 1;
  }
  if ( *a1 )
  {
    if ( !*a2 )
      return 0;
  }
  else if ( *a2 )
  {
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18001c5d8  push    rbx
0x18001c5da  push    rsi
0x18001c5db  push    rdi
0x18001c5dc  push    r14
0x18001c5de  sub     rsp, 28h
0x18001c5e2  cmp     byte ptr [rcx+8], 0
0x18001c5e6  mov     rbx, rdx
0x18001c5e9  mov     rdi, rcx
0x18001c5ec  mov     r14d, 0FFFFh
0x18001c5f2  mov     sil, 1
0x18001c5f5  jnz     short loc_18001C63C
0x18001c5f7  mov     rcx, [rcx]
0x18001c5fa  test    rcx, rcx
0x18001c5fd  jz      short loc_18001C631
0x18001c5ff  mov     rax, [rcx+38h]
0x18001c603  mov     rdx, [rax]
0x18001c606  test    rdx, rdx
0x18001c609  jz      short loc_18001C619
0x18001c60b  mov     rax, [rcx+50h]
0x18001c60f  cmp     dword ptr [rax], 0
0x18001c612  jle     short loc_18001C619
0x18001c614  movzx   eax, word ptr [rdx]
0x18001c617  jmp     short loc_18001C625
0x18001c619  mov     rax, [rcx]
0x18001c61c  mov     rax, [rax+30h]
0x18001c620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c625  cmp     ax, r14w
0x18001c629  jz      short loc_18001C631
0x18001c62b  mov     [rdi+0Ah], ax
0x18001c62f  jmp     short loc_18001C638
0x18001c631  mov     qword ptr [rdi], 0
0x18001c638  mov     [rdi+8], sil
0x18001c63c  cmp     byte ptr [rbx+8], 0
0x18001c640  jnz     short loc_18001C687
0x18001c642  mov     rcx, [rbx]
0x18001c645  test    rcx, rcx
0x18001c648  jz      short loc_18001C67C
0x18001c64a  mov     rax, [rcx+38h]
0x18001c64e  mov     rdx, [rax]
0x18001c651  test    rdx, rdx
0x18001c654  jz      short loc_18001C664
0x18001c656  mov     rax, [rcx+50h]
0x18001c65a  cmp     dword ptr [rax], 0
0x18001c65d  jle     short loc_18001C664
0x18001c65f  movzx   eax, word ptr [rdx]
0x18001c662  jmp     short loc_18001C670
0x18001c664  mov     rax, [rcx]
0x18001c667  mov     rax, [rax+30h]
0x18001c66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c670  cmp     ax, r14w
0x18001c674  jz      short loc_18001C67C
0x18001c676  mov     [rbx+0Ah], ax
0x18001c67a  jmp     short loc_18001C683
0x18001c67c  mov     qword ptr [rbx], 0
0x18001c683  mov     [rbx+8], sil
0x18001c687  cmp     qword ptr [rdi], 0
0x18001c68b  jnz     short loc_18001C695
0x18001c68d  cmp     qword ptr [rbx], 0
0x18001c691  jz      short loc_18001C69E
0x18001c693  jmp     short loc_18001C69B
0x18001c695  cmp     qword ptr [rbx], 0
0x18001c699  jnz     short loc_18001C69E
0x18001c69b  xor     sil, sil
0x18001c69e  mov     al, sil
0x18001c6a1  add     rsp, 28h
0x18001c6a5  pop     r14
0x18001c6a7  pop     rdi
0x18001c6a8  pop     rsi
0x18001c6a9  pop     rbx
0x18001c6aa  retn
```
