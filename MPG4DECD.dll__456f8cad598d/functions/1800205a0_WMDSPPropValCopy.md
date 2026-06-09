# WMDSPPropValCopy

- ea: `0x1800205a0`
- end: `0x180020689`
- name: `WMDSPPropValCopy`
- size: `233`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020450`
- `0x180020970`
- `0x180020ce0`

## callees

- `0x1800205a0`
- `0x180021005`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002065e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002065e`
- `OLEAUT32!__imp_SysFreeString` at `0x180020655`
- `OLEAUT32!__imp_SysFreeString` at `0x180020669`
- `OLEAUT32!__imp_SysFreeString` at `0x180020655`
- `OLEAUT32!__imp_SysFreeString` at `0x180020669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002060e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002060e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020622`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020622`

## pseudocode

```c
void __fastcall WMDSPPropValCopy(__int16 a1, OLECHAR **a2, int *a3)
{
  OLECHAR *v5; // rcx
  unsigned int v6; // eax
  OLECHAR *v7; // rax
  OLECHAR *v8; // rcx
  BSTR v9; // rsi

  switch ( a1 )
  {
    case 3:
    case 4:
      goto LABEL_21;
    case 5:
LABEL_10:
      *a2 = *(OLECHAR **)a3;
      return;
    case 8:
      v8 = *a2;
      v9 = 0;
      if ( *(_QWORD *)a3 )
      {
        SysFreeString(v8);
        v9 = SysAllocString(*(const OLECHAR **)a3);
      }
      else
      {
        SysFreeString(v8);
      }
      *a2 = v9;
      return;
    case 11:
      *(_WORD *)a2 = *(_WORD *)a3;
      return;
    case 19:
LABEL_21:
      *(_DWORD *)a2 = *a3;
      return;
    case 20:
      goto LABEL_10;
  }
  if ( a1 != 65 )
  {
    if ( a1 != 72 )
      return;
    goto LABEL_10;
  }
  v5 = a2[1];
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = *a3;
  *(_DWORD *)a2 = *a3;
  a2[1] = 0;
  if ( v6 )
  {
    v7 = (OLECHAR *)CoTaskMemAlloc(v6);
    a2[1] = v7;
    if ( v7 )
      memcpy_0(v7, *((const void **)a3 + 1), *(unsigned int *)a2);
  }
}

```

## disassembly

```asm
0x1800205a0  mov     [rsp+arg_0], rbx
0x1800205a5  mov     [rsp+arg_8], rsi
0x1800205aa  push    rdi
0x1800205ab  sub     rsp, 20h
0x1800205af  movzx   r9d, cx
0x1800205b3  mov     rdi, r8
0x1800205b6  mov     rbx, rdx
0x1800205b9  sub     r9d, 3
0x1800205bd  jz      loc_180020674
0x1800205c3  sub     r9d, 1
0x1800205c7  jz      loc_180020674
0x1800205cd  sub     r9d, 1
0x1800205d1  jz      short loc_1800205FB
0x1800205d3  sub     r9d, 3
0x1800205d7  jz      short loc_18002064B
0x1800205d9  sub     r9d, 3
0x1800205dd  jz      short loc_180020642
0x1800205df  sub     r9d, 8
0x1800205e3  jz      loc_180020674
0x1800205e9  sub     r9d, 1
0x1800205ed  jz      short loc_1800205FB
0x1800205ef  sub     r9d, 2Dh ; '-'
0x1800205f3  jz      short loc_180020603
0x1800205f5  cmp     r9d, 7
0x1800205f9  jnz     short loc_180020679
0x1800205fb  mov     rax, [r8]
0x1800205fe  mov     [rdx], rax
0x180020601  jmp     short loc_180020679
0x180020603  mov     rcx, [rdx+8]; pv
0x180020607  xor     esi, esi
0x180020609  test    rcx, rcx
0x18002060c  jz      short loc_180020614
0x18002060e  call    cs:__imp_CoTaskMemFree
0x180020614  mov     eax, [rdi]
0x180020616  mov     [rbx], eax
0x180020618  mov     [rbx+8], rsi
0x18002061c  test    eax, eax
0x18002061e  jz      short loc_180020679
0x180020620  mov     ecx, eax; cb
0x180020622  call    cs:__imp_CoTaskMemAlloc
0x180020628  mov     [rbx+8], rax
0x18002062c  test    rax, rax
0x18002062f  jz      short loc_180020679
0x180020631  mov     r8d, [rbx]; Size
0x180020634  mov     rcx, rax; void *
0x180020637  mov     rdx, [rdi+8]; Src
0x18002063b  call    memcpy_0
0x180020640  jmp     short loc_180020679
0x180020642  movzx   eax, word ptr [r8]
0x180020646  mov     [rdx], ax
0x180020649  jmp     short loc_180020679
0x18002064b  mov     rcx, [rdx]; bstrString
0x18002064e  xor     esi, esi
0x180020650  cmp     [r8], rsi
0x180020653  jz      short loc_180020669
0x180020655  call    cs:__imp_SysFreeString
0x18002065b  mov     rcx, [rdi]; psz
0x18002065e  call    cs:__imp_SysAllocString
0x180020664  mov     rsi, rax
0x180020667  jmp     short loc_18002066F
0x180020669  call    cs:__imp_SysFreeString
0x18002066f  mov     [rbx], rsi
0x180020672  jmp     short loc_180020679
0x180020674  mov     eax, [r8]
0x180020677  mov     [rdx], eax
0x180020679  mov     rbx, [rsp+28h+arg_0]
0x18002067e  mov     rsi, [rsp+28h+arg_8]
0x180020683  add     rsp, 20h
0x180020687  pop     rdi
0x180020688  retn
```
