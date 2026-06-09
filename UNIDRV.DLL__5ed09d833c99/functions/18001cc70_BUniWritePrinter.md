# BUniWritePrinter

- ea: `0x18001cc70`
- end: `0x18001cd99`
- name: `BUniWritePrinter`
- size: `297`
- prototype: `__int64 __fastcall(__int64, void *, DWORD, DWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800124e0`
- `0x180012780`
- `0x180012f00`
- `0x18001bb98`
- `0x18001cb20`
- `0x18001cc14`

## callees

- `0x18001cc70`
- `0x180077010`

## import_xrefs

- `WINSPOOL!WritePrinter` at `0x18001cd75`
- `WINSPOOL!WritePrinter` at `0x18001cd75`

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
0x18001cc70  push    rbx
0x18001cc72  push    rbp
0x18001cc73  push    rsi
0x18001cc74  push    rdi
0x18001cc75  push    r14
0x18001cc77  sub     rsp, 30h
0x18001cc7b  mov     ebp, r8d
0x18001cc7e  mov     rsi, r9
0x18001cc81  mov     r8d, [rcx+74h]
0x18001cc85  mov     r10, rdx
0x18001cc88  mov     rdi, rcx
0x18001cc8b  test    r8b, 2
0x18001cc8f  jz      loc_18001CD6E
0x18001cc95  mov     rax, [rcx+758h]
0x18001cc9c  xor     ebx, ebx
0x18001cc9e  mov     r14, [rcx+8]
0x18001cca2  mov     edx, [rax+8]
0x18001cca5  lea     rcx, [rax+18h]
0x18001cca9  test    edx, edx
0x18001ccab  jz      loc_18001CD4E
0x18001ccb1  mov     rax, [rcx+20h]
0x18001ccb5  test    rax, rax
0x18001ccb8  jz      loc_18001CD60
0x18001ccbe  mov     [rdi+20h], rax
0x18001ccc2  mov     rax, [rcx+28h]
0x18001ccc6  mov     [rdi+8], rax
0x18001ccca  mov     rax, [rcx+38h]
0x18001ccce  mov     [rdi+30h], rax
0x18001ccd2  cmp     [rcx+48h], rbx
0x18001ccd6  jz      loc_18001CD60
0x18001ccdc  test    byte ptr [rcx+30h], 8
0x18001cce0  jz      short loc_18001CD60
0x18001cce2  or      r8d, 4
0x18001cce6  mov     [rdi+74h], r8d
0x18001ccea  mov     rax, [rcx+50h]
0x18001ccee  sub     rax, qword ptr cs:IID_IPrintOemUni2.Data1
0x18001ccf5  jnz     short loc_18001CD02
0x18001ccf7  mov     rax, [rcx+58h]
0x18001ccfb  sub     rax, qword ptr cs:IID_IPrintOemUni2.Data4
0x18001cd02  test    rax, rax
0x18001cd05  jz      short loc_18001CD24
0x18001cd07  mov     rax, [rcx+50h]
0x18001cd0b  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data1
0x18001cd12  jnz     short loc_18001CD1F
0x18001cd14  mov     rax, [rcx+58h]
0x18001cd18  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data4
0x18001cd1f  test    rax, rax
0x18001cd22  jnz     short loc_18001CD92
0x18001cd24  mov     rcx, [rcx+48h]
0x18001cd28  mov     r9d, ebp
0x18001cd2b  mov     r8, r10
0x18001cd2e  mov     [rsp+58h+var_38], rsi
0x18001cd33  mov     rdx, rdi
0x18001cd36  mov     rax, [rcx]
0x18001cd39  mov     rax, [rax+0D0h]
0x18001cd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd45  and     dword ptr [rdi+74h], 0FFFFFFFBh
0x18001cd49  test    eax, eax
0x18001cd4b  setns   bl
0x18001cd4e  mov     [rdi+8], r14
0x18001cd52  mov     eax, ebx
0x18001cd54  add     rsp, 30h
0x18001cd58  pop     r14
0x18001cd5a  pop     rdi
0x18001cd5b  pop     rsi
0x18001cd5c  pop     rbp
0x18001cd5d  pop     rbx
0x18001cd5e  retn
0x18001cd60  dec     edx; pBuf
0x18001cd62  add     rcx, 0B0h
0x18001cd69  jmp     loc_18001CCA9
0x18001cd6e  mov     rcx, [rcx+18h]; hPrinter
0x18001cd72  mov     r8d, ebp; cbBuf
0x18001cd75  call    cs:__imp_WritePrinter
0x18001cd7c  nop     dword ptr [rax+rax+00h]
0x18001cd81  xor     ebx, ebx
0x18001cd83  test    eax, eax
0x18001cd85  jz      short loc_18001CD52
0x18001cd87  cmp     ebp, [rsi]
0x18001cd89  jnz     short loc_18001CD52
0x18001cd8b  mov     ebx, 1
0x18001cd90  jmp     short loc_18001CD52
0x18001cd92  mov     eax, 80004002h
0x18001cd97  jmp     short loc_18001CD45
```
