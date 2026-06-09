# WMDSPPropValFromVar

- ea: `0x1800206e0`
- end: `0x1800207d1`
- name: `WMDSPPropValFromVar`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fec0`
- `0x1800209f0`

## callees

- `0x1800206e0`
- `0x180020f45`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800207a6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800207a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002079c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800207b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002079c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800207b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020753`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020753`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020768`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020768`

## pseudocode

```c
void __fastcall WMDSPPropValFromVar(__int64 a1, OLECHAR **a2)
{
  OLECHAR *v4; // rcx
  unsigned int v5; // eax
  OLECHAR *v6; // rax
  BSTR v7; // rsi
  bool v8; // zf
  OLECHAR *v9; // rcx

  switch ( *(_WORD *)a1 )
  {
    case 3:
    case 4:
      goto LABEL_21;
    case 5:
LABEL_10:
      *a2 = *(OLECHAR **)(a1 + 8);
      return;
    case 8:
      v7 = 0;
      v8 = *(_QWORD *)(a1 + 8) == 0;
      v9 = *a2;
      if ( v8 )
      {
        SysFreeString(v9);
      }
      else
      {
        SysFreeString(v9);
        v7 = SysAllocString(*(const OLECHAR **)(a1 + 8));
      }
      *a2 = v7;
      return;
    case 0xB:
      *(_WORD *)a2 = *(_WORD *)(a1 + 8);
      return;
    case 0x13:
LABEL_21:
      *(_DWORD *)a2 = *(_DWORD *)(a1 + 8);
      return;
    case 0x14:
      goto LABEL_10;
  }
  if ( *(_WORD *)a1 != 65 )
  {
    if ( *(_WORD *)a1 != 72 )
      return;
    goto LABEL_10;
  }
  v4 = a2[1];
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = *(_DWORD *)(a1 + 8);
  *(_DWORD *)a2 = v5;
  a2[1] = 0;
  if ( v5 )
  {
    v6 = (OLECHAR *)CoTaskMemAlloc(v5);
    a2[1] = v6;
    if ( v6 )
      memcpy_0(v6, *(const void **)(a1 + 16), *(unsigned int *)a2);
  }
}

```

## disassembly

```asm
0x1800206e0  mov     [rsp+arg_0], rbx
0x1800206e5  mov     [rsp+arg_8], rsi
0x1800206ea  push    rdi
0x1800206eb  sub     rsp, 20h
0x1800206ef  movzx   r8d, word ptr [rcx]
0x1800206f3  mov     rbx, rdx
0x1800206f6  mov     rdi, rcx
0x1800206f9  sub     r8d, 3
0x1800206fd  jz      loc_1800207BC
0x180020703  sub     r8d, 1
0x180020707  jz      loc_1800207BC
0x18002070d  sub     r8d, 1
0x180020711  jz      short loc_18002073F
0x180020713  sub     r8d, 3
0x180020717  jz      short loc_180020791
0x180020719  sub     r8d, 3
0x18002071d  jz      short loc_180020788
0x18002071f  sub     r8d, 8
0x180020723  jz      loc_1800207BC
0x180020729  sub     r8d, 1
0x18002072d  jz      short loc_18002073F
0x18002072f  sub     r8d, 2Dh ; '-'
0x180020733  jz      short loc_180020748
0x180020735  cmp     r8d, 7
0x180020739  jnz     loc_1800207C1
0x18002073f  mov     rax, [rcx+8]
0x180020743  mov     [rdx], rax
0x180020746  jmp     short loc_1800207C1
0x180020748  mov     rcx, [rdx+8]; pv
0x18002074c  xor     esi, esi
0x18002074e  test    rcx, rcx
0x180020751  jz      short loc_180020759
0x180020753  call    cs:__imp_CoTaskMemFree
0x180020759  mov     eax, [rdi+8]
0x18002075c  mov     [rbx], eax
0x18002075e  mov     [rbx+8], rsi
0x180020762  test    eax, eax
0x180020764  jz      short loc_1800207C1
0x180020766  mov     ecx, eax; cb
0x180020768  call    cs:__imp_CoTaskMemAlloc
0x18002076e  mov     [rbx+8], rax
0x180020772  test    rax, rax
0x180020775  jz      short loc_1800207C1
0x180020777  mov     r8d, [rbx]; Size
0x18002077a  mov     rcx, rax; void *
0x18002077d  mov     rdx, [rdi+10h]; Src
0x180020781  call    memcpy_0
0x180020786  jmp     short loc_1800207C1
0x180020788  movzx   eax, word ptr [rcx+8]
0x18002078c  mov     [rdx], ax
0x18002078f  jmp     short loc_1800207C1
0x180020791  xor     esi, esi
0x180020793  cmp     [rcx+8], rsi
0x180020797  mov     rcx, [rdx]; bstrString
0x18002079a  jz      short loc_1800207B1
0x18002079c  call    cs:__imp_SysFreeString
0x1800207a2  mov     rcx, [rdi+8]; psz
0x1800207a6  call    cs:__imp_SysAllocString
0x1800207ac  mov     rsi, rax
0x1800207af  jmp     short loc_1800207B7
0x1800207b1  call    cs:__imp_SysFreeString
0x1800207b7  mov     [rbx], rsi
0x1800207ba  jmp     short loc_1800207C1
0x1800207bc  mov     eax, [rcx+8]
0x1800207bf  mov     [rdx], eax
0x1800207c1  mov     rbx, [rsp+28h+arg_0]
0x1800207c6  mov     rsi, [rsp+28h+arg_8]
0x1800207cb  add     rsp, 20h
0x1800207cf  pop     rdi
0x1800207d0  retn
```
