# BUniWritePrinter

- ea: `0x18001c8e0`
- end: `0x18001ca02`
- name: `BUniWritePrinter`
- size: `290`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180012328`
- `0x180012590`
- `0x180012cf0`
- `0x18001b818`
- `0x18001c790`
- `0x18001c884`

## callees

- `0x18001c8e0`
- `0x180075010`

## import_xrefs

- `WINSPOOL!WritePrinter` at `0x18001c9e4`
- `WINSPOOL!WritePrinter` at `0x18001c9e4`

## pseudocode

```c
__int64 __fastcall BUniWritePrinter(__int64 a1, void *a2, DWORD a3, DWORD *a4)
{
  int v6; // r8d
  __int64 v9; // rax
  unsigned int v10; // ebx
  __int64 v11; // r14
  int v12; // edx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // eax

  v6 = *(_DWORD *)(a1 + 116);
  if ( (v6 & 2) != 0 )
  {
    v9 = *(_QWORD *)(a1 + 1880);
    v10 = 0;
    v11 = *(_QWORD *)(a1 + 8);
    v12 = *(_DWORD *)(v9 + 8);
    v13 = v9 + 24;
    while ( v12 )
    {
      v14 = *(_QWORD *)(v13 + 32);
      if ( v14 )
      {
        *(_QWORD *)(a1 + 32) = v14;
        *(_QWORD *)(a1 + 8) = *(_QWORD *)(v13 + 40);
        *(_QWORD *)(a1 + 48) = *(_QWORD *)(v13 + 56);
        if ( *(_QWORD *)(v13 + 72) )
        {
          if ( (*(_BYTE *)(v13 + 48) & 8) != 0 )
          {
            *(_DWORD *)(a1 + 116) = v6 | 4;
            v15 = *(_QWORD *)(v13 + 80) - *(_QWORD *)&IID_IPrintOemUni2.Data1;
            if ( !v15 )
              v15 = *(_QWORD *)(v13 + 88) - *(_QWORD *)IID_IPrintOemUni2.Data4;
            if ( !v15 )
              goto LABEL_13;
            v16 = *(_QWORD *)(v13 + 80) - *(_QWORD *)&IID_IPrintOemUni3.Data1;
            if ( !v16 )
              v16 = *(_QWORD *)(v13 + 88) - *(_QWORD *)IID_IPrintOemUni3.Data4;
            if ( v16 )
              v17 = -2147467262;
            else
LABEL_13:
              v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, void *, _QWORD, DWORD *))(**(_QWORD **)(v13 + 72) + 208LL))(
                      *(_QWORD *)(v13 + 72),
                      a1,
                      a2,
                      a3,
                      a4);
            *(_DWORD *)(a1 + 116) &= ~4u;
            LOBYTE(v10) = v17 >= 0;
            break;
          }
        }
      }
      --v12;
      v13 += 176;
    }
    *(_QWORD *)(a1 + 8) = v11;
  }
  else
  {
    v10 = 0;
    if ( WritePrinter(*(HANDLE *)(a1 + 24), a2, a3, a4) )
      return a3 == *a4;
  }
  return v10;
}

```

## disassembly

```asm
0x18001c8e0  push    rbx
0x18001c8e2  push    rbp
0x18001c8e3  push    rsi
0x18001c8e4  push    rdi
0x18001c8e5  push    r14
0x18001c8e7  sub     rsp, 30h
0x18001c8eb  mov     ebp, r8d
0x18001c8ee  mov     rsi, r9
0x18001c8f1  mov     r8d, [rcx+74h]
0x18001c8f5  mov     r10, rdx
0x18001c8f8  mov     rdi, rcx
0x18001c8fb  test    r8b, 2
0x18001c8ff  jz      loc_18001C9DD
0x18001c905  mov     rax, [rcx+758h]
0x18001c90c  xor     ebx, ebx
0x18001c90e  mov     r14, [rcx+8]
0x18001c912  mov     edx, [rax+8]
0x18001c915  lea     rcx, [rax+18h]
0x18001c919  test    edx, edx
0x18001c91b  jz      loc_18001C9BE
0x18001c921  mov     rax, [rcx+20h]
0x18001c925  test    rax, rax
0x18001c928  jz      loc_18001C9CF
0x18001c92e  mov     [rdi+20h], rax
0x18001c932  mov     rax, [rcx+28h]
0x18001c936  mov     [rdi+8], rax
0x18001c93a  mov     rax, [rcx+38h]
0x18001c93e  mov     [rdi+30h], rax
0x18001c942  cmp     [rcx+48h], rbx
0x18001c946  jz      loc_18001C9CF
0x18001c94c  test    byte ptr [rcx+30h], 8
0x18001c950  jz      short loc_18001C9CF
0x18001c952  or      r8d, 4
0x18001c956  mov     [rdi+74h], r8d
0x18001c95a  mov     rax, [rcx+50h]
0x18001c95e  sub     rax, qword ptr cs:IID_IPrintOemUni2.Data1
0x18001c965  jnz     short loc_18001C972
0x18001c967  mov     rax, [rcx+58h]
0x18001c96b  sub     rax, qword ptr cs:IID_IPrintOemUni2.Data4
0x18001c972  test    rax, rax
0x18001c975  jz      short loc_18001C994
0x18001c977  mov     rax, [rcx+50h]
0x18001c97b  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data1
0x18001c982  jnz     short loc_18001C98F
0x18001c984  mov     rax, [rcx+58h]
0x18001c988  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data4
0x18001c98f  test    rax, rax
0x18001c992  jnz     short loc_18001C9FB
0x18001c994  mov     rcx, [rcx+48h]
0x18001c998  mov     r9d, ebp
0x18001c99b  mov     r8, r10
0x18001c99e  mov     [rsp+58h+var_38], rsi
0x18001c9a3  mov     rdx, rdi
0x18001c9a6  mov     rax, [rcx]
0x18001c9a9  mov     rax, [rax+0D0h]
0x18001c9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9b5  and     dword ptr [rdi+74h], 0FFFFFFFBh
0x18001c9b9  test    eax, eax
0x18001c9bb  setns   bl
0x18001c9be  mov     [rdi+8], r14
0x18001c9c2  mov     eax, ebx
0x18001c9c4  add     rsp, 30h
0x18001c9c8  pop     r14
0x18001c9ca  pop     rdi
0x18001c9cb  pop     rsi
0x18001c9cc  pop     rbp
0x18001c9cd  pop     rbx
0x18001c9ce  retn
0x18001c9cf  dec     edx; pBuf
0x18001c9d1  add     rcx, 0B0h
0x18001c9d8  jmp     loc_18001C919
0x18001c9dd  mov     rcx, [rcx+18h]; hPrinter
0x18001c9e1  mov     r8d, ebp; cbBuf
0x18001c9e4  call    cs:__imp_WritePrinter
0x18001c9ea  xor     ebx, ebx
0x18001c9ec  test    eax, eax
0x18001c9ee  jz      short loc_18001C9C2
0x18001c9f0  cmp     ebp, [rsi]
0x18001c9f2  jnz     short loc_18001C9C2
0x18001c9f4  mov     ebx, 1
0x18001c9f9  jmp     short loc_18001C9C2
0x18001c9fb  mov     eax, 80004002h
0x18001ca00  jmp     short loc_18001C9B5
```
