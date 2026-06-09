# WMDSPPropValFromVar

- ea: `0x18008389c`
- end: `0x18008398d`
- name: `WMDSPPropValFromVar`
- size: `241`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800833d0`
- `0x180083cd0`
- `0x180083e60`

## callees

- `0x18008389c`
- `0x180084690`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180083962`
- `OLEAUT32!__imp_SysAllocString` at `0x180083962`
- `OLEAUT32!__imp_SysFreeString` at `0x180083958`
- `OLEAUT32!__imp_SysFreeString` at `0x18008396d`
- `OLEAUT32!__imp_SysFreeString` at `0x180083958`
- `OLEAUT32!__imp_SysFreeString` at `0x18008396d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083924`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083924`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008390f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008390f`

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
0x18008389c  mov     [rsp+arg_0], rbx
0x1800838a1  mov     [rsp+arg_8], rsi
0x1800838a6  push    rdi
0x1800838a7  sub     rsp, 20h
0x1800838ab  movzx   r8d, word ptr [rcx]
0x1800838af  mov     rbx, rdx
0x1800838b2  mov     rdi, rcx
0x1800838b5  sub     r8d, 3
0x1800838b9  jz      loc_180083978
0x1800838bf  sub     r8d, 1
0x1800838c3  jz      loc_180083978
0x1800838c9  sub     r8d, 1
0x1800838cd  jz      short loc_1800838FB
0x1800838cf  sub     r8d, 3
0x1800838d3  jz      short loc_18008394D
0x1800838d5  sub     r8d, 3
0x1800838d9  jz      short loc_180083944
0x1800838db  sub     r8d, 8
0x1800838df  jz      loc_180083978
0x1800838e5  sub     r8d, 1
0x1800838e9  jz      short loc_1800838FB
0x1800838eb  sub     r8d, 2Dh ; '-'
0x1800838ef  jz      short loc_180083904
0x1800838f1  cmp     r8d, 7
0x1800838f5  jnz     loc_18008397D
0x1800838fb  mov     rax, [rcx+8]
0x1800838ff  mov     [rdx], rax
0x180083902  jmp     short loc_18008397D
0x180083904  mov     rcx, [rdx+8]; pv
0x180083908  xor     esi, esi
0x18008390a  test    rcx, rcx
0x18008390d  jz      short loc_180083915
0x18008390f  call    cs:__imp_CoTaskMemFree
0x180083915  mov     eax, [rdi+8]
0x180083918  mov     [rbx], eax
0x18008391a  mov     [rbx+8], rsi
0x18008391e  test    eax, eax
0x180083920  jz      short loc_18008397D
0x180083922  mov     ecx, eax; cb
0x180083924  call    cs:__imp_CoTaskMemAlloc
0x18008392a  mov     [rbx+8], rax
0x18008392e  test    rax, rax
0x180083931  jz      short loc_18008397D
0x180083933  mov     r8d, [rbx]; Size
0x180083936  mov     rcx, rax; void *
0x180083939  mov     rdx, [rdi+10h]; Src
0x18008393d  call    memcpy_0
0x180083942  jmp     short loc_18008397D
0x180083944  movzx   eax, word ptr [rcx+8]
0x180083948  mov     [rdx], ax
0x18008394b  jmp     short loc_18008397D
0x18008394d  xor     esi, esi
0x18008394f  cmp     [rcx+8], rsi
0x180083953  mov     rcx, [rdx]; bstrString
0x180083956  jz      short loc_18008396D
0x180083958  call    cs:__imp_SysFreeString
0x18008395e  mov     rcx, [rdi+8]; psz
0x180083962  call    cs:__imp_SysAllocString
0x180083968  mov     rsi, rax
0x18008396b  jmp     short loc_180083973
0x18008396d  call    cs:__imp_SysFreeString
0x180083973  mov     [rbx], rsi
0x180083976  jmp     short loc_18008397D
0x180083978  mov     eax, [rcx+8]
0x18008397b  mov     [rdx], eax
0x18008397d  mov     rbx, [rsp+28h+arg_0]
0x180083982  mov     rsi, [rsp+28h+arg_8]
0x180083987  add     rsp, 20h
0x18008398b  pop     rdi
0x18008398c  retn
```
