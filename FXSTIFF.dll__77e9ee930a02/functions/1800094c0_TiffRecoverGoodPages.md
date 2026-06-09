# TiffRecoverGoodPages

- ea: `0x1800094c0`
- end: `0x1800095eb`
- name: `TiffRecoverGoodPages`
- size: `299`
- prototype: `__int64 __fastcall(const WCHAR *, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007fd0`
- `0x180008b70`
- `0x1800094c0`
- `0x18000b120`
- `0x18000bb50`
- `0x1800174d8`

## string_xrefs

- `0x180009572`: `TiffRecoverGoodPages: %s: Unexpected Compression type %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TiffRecoverGoodPages(const WCHAR *a1, _DWORD *a2, _DWORD *a3)
{
  char *v5; // rax
  char *v6; // rsi
  int v8; // r15d
  unsigned int v9; // r14d
  int v10; // ecx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int128 v14; // [rsp+20h] [rbp-48h] BYREF
  __int128 v15; // [rsp+30h] [rbp-38h]
  __int128 v16; // [rsp+40h] [rbp-28h] BYREF
  __int128 v17; // [rsp+50h] [rbp-18h]

  v14 = 0;
  v15 = 0;
  if ( !a1 || !a2 || !a3 )
    return 0;
  *a2 = 0;
  *a3 = 0;
  v5 = TiffOpen(a1, &v14, 0, 2u);
  v6 = v5;
  if ( !v5 )
  {
    *a3 = 0;
    return 0;
  }
  v8 = DWORD2(v14);
  *a3 = DWORD2(v14);
  if ( *((_DWORD *)v5 + 392) )
  {
    v9 = 1;
LABEL_19:
    TiffClose(v6);
    return v9;
  }
  v9 = 0;
  if ( !v8 )
    goto LABEL_19;
  v10 = 1;
  v11 = *((_DWORD *)v5 + 213) - 2;
  if ( !v11 )
  {
    v16 = v14;
    v17 = v15;
    v13 = PostProcessMhToMmr(v6, &v16, 0);
    goto LABEL_16;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v16 = v14;
    v17 = v15;
    v13 = PostProcessMrToMmr(v6, &v16, 0);
LABEL_16:
    if ( !v13 )
      return 0;
    v10 = 0;
    goto LABEL_18;
  }
  if ( v12 != 1 )
  {
    fax_dprintf(L"TiffRecoverGoodPages: %s: Unexpected Compression type %d\n", v6 + 44);
    goto LABEL_19;
  }
LABEL_18:
  *a2 = v8;
  v9 = 1;
  ++*a3;
  if ( v10 == 1 )
    goto LABEL_19;
  return v9;
}

```

## disassembly

```asm
0x1800094c0  push    rbp
0x1800094c2  push    rsi
0x1800094c3  push    rdi
0x1800094c4  push    r12
0x1800094c6  push    r14
0x1800094c8  push    r15
0x1800094ca  mov     rbp, rsp
0x1800094cd  sub     rsp, 68h
0x1800094d1  xorps   xmm0, xmm0
0x1800094d4  mov     rdi, r8
0x1800094d7  mov     r12, rdx
0x1800094da  movups  [rbp+var_48], xmm0
0x1800094de  movups  [rbp+var_38], xmm0
0x1800094e2  test    rcx, rcx
0x1800094e5  jz      short loc_18000951A
0x1800094e7  test    rdx, rdx
0x1800094ea  jz      short loc_18000951A
0x1800094ec  test    r8, r8
0x1800094ef  jz      short loc_18000951A
0x1800094f1  mov     dword ptr [rdx], 0
0x1800094f7  mov     r9d, 2
0x1800094fd  mov     dword ptr [r8], 0
0x180009504  lea     rdx, [rbp+var_48]
0x180009508  xor     r8d, r8d
0x18000950b  call    TiffOpen
0x180009510  mov     rsi, rax
0x180009513  test    rax, rax
0x180009516  jnz     short loc_18000952B
0x180009518  mov     [rdi], eax
0x18000951a  xor     eax, eax
0x18000951c  add     rsp, 68h
0x180009520  pop     r15
0x180009522  pop     r14
0x180009524  pop     r12
0x180009526  pop     rdi
0x180009527  pop     rsi
0x180009528  pop     rbp
0x180009529  retn
0x18000952b  mov     r15d, dword ptr [rbp+var_48+8]
0x18000952f  mov     [rdi], r15d
0x180009532  cmp     dword ptr [rax+620h], 0
0x180009539  jz      short loc_180009546
0x18000953b  mov     r14d, 1
0x180009541  jmp     loc_1800095DB
0x180009546  xor     r14d, r14d
0x180009549  cmp     r15d, 1
0x18000954d  jb      loc_1800095DB
0x180009553  mov     r8d, [rax+354h]
0x18000955a  lea     ecx, [r14+1]
0x18000955e  mov     eax, r8d
0x180009561  sub     eax, 2
0x180009564  jz      short loc_1800095A1
0x180009566  sub     eax, ecx
0x180009568  jz      short loc_180009580
0x18000956a  cmp     eax, ecx
0x18000956c  jz      short loc_1800095CA
0x18000956e  lea     rdx, [rsi+2Ch]
0x180009572  lea     rcx, aTiffrecovergoo_0; "TiffRecoverGoodPages: %s: Unexpected Co"...
0x180009579  call    fax_dprintf
0x18000957e  jmp     short loc_1800095DB
0x180009580  movups  xmm0, [rbp+var_48]
0x180009584  xor     r8d, r8d
0x180009587  lea     rdx, [rbp+var_28]
0x18000958b  movups  xmm1, [rbp+var_38]
0x18000958f  mov     rcx, rsi
0x180009592  movaps  [rbp+var_28], xmm0
0x180009596  movaps  [rbp+var_18], xmm1
0x18000959a  call    PostProcessMrToMmr
0x18000959f  jmp     short loc_1800095C0
0x1800095a1  movups  xmm0, [rbp+var_48]
0x1800095a5  xor     r8d, r8d
0x1800095a8  lea     rdx, [rbp+var_28]
0x1800095ac  movups  xmm1, [rbp+var_38]
0x1800095b0  mov     rcx, rsi
0x1800095b3  movaps  [rbp+var_28], xmm0
0x1800095b7  movaps  [rbp+var_18], xmm1
0x1800095bb  call    PostProcessMhToMmr
0x1800095c0  test    eax, eax
0x1800095c2  jz      loc_18000951A
0x1800095c8  xor     ecx, ecx
0x1800095ca  mov     [r12], r15d
0x1800095ce  mov     r14d, 1
0x1800095d4  inc     dword ptr [rdi]
0x1800095d6  cmp     ecx, r14d
0x1800095d9  jnz     short loc_1800095E3
0x1800095db  mov     rcx, rsi; lpMem
0x1800095de  call    TiffClose
0x1800095e3  mov     eax, r14d
0x1800095e6  jmp     loc_18000951C
```
