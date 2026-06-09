# WMDSPPropValCopy

- ea: `0x1800204e0`
- end: `0x1800205c9`
- name: `WMDSPPropValCopy`
- size: `233`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020390`
- `0x1800208b0`
- `0x180020c20`

## callees

- `0x1800204e0`
- `0x180020f45`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002059e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002059e`
- `OLEAUT32!__imp_SysFreeString` at `0x180020595`
- `OLEAUT32!__imp_SysFreeString` at `0x1800205a9`
- `OLEAUT32!__imp_SysFreeString` at `0x180020595`
- `OLEAUT32!__imp_SysFreeString` at `0x1800205a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002054e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002054e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020562`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020562`

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
0x1800204e0  mov     [rsp+arg_0], rbx
0x1800204e5  mov     [rsp+arg_8], rsi
0x1800204ea  push    rdi
0x1800204eb  sub     rsp, 20h
0x1800204ef  movzx   r9d, cx
0x1800204f3  mov     rdi, r8
0x1800204f6  mov     rbx, rdx
0x1800204f9  sub     r9d, 3
0x1800204fd  jz      loc_1800205B4
0x180020503  sub     r9d, 1
0x180020507  jz      loc_1800205B4
0x18002050d  sub     r9d, 1
0x180020511  jz      short loc_18002053B
0x180020513  sub     r9d, 3
0x180020517  jz      short loc_18002058B
0x180020519  sub     r9d, 3
0x18002051d  jz      short loc_180020582
0x18002051f  sub     r9d, 8
0x180020523  jz      loc_1800205B4
0x180020529  sub     r9d, 1
0x18002052d  jz      short loc_18002053B
0x18002052f  sub     r9d, 2Dh ; '-'
0x180020533  jz      short loc_180020543
0x180020535  cmp     r9d, 7
0x180020539  jnz     short loc_1800205B9
0x18002053b  mov     rax, [r8]
0x18002053e  mov     [rdx], rax
0x180020541  jmp     short loc_1800205B9
0x180020543  mov     rcx, [rdx+8]; pv
0x180020547  xor     esi, esi
0x180020549  test    rcx, rcx
0x18002054c  jz      short loc_180020554
0x18002054e  call    cs:__imp_CoTaskMemFree
0x180020554  mov     eax, [rdi]
0x180020556  mov     [rbx], eax
0x180020558  mov     [rbx+8], rsi
0x18002055c  test    eax, eax
0x18002055e  jz      short loc_1800205B9
0x180020560  mov     ecx, eax; cb
0x180020562  call    cs:__imp_CoTaskMemAlloc
0x180020568  mov     [rbx+8], rax
0x18002056c  test    rax, rax
0x18002056f  jz      short loc_1800205B9
0x180020571  mov     r8d, [rbx]; Size
0x180020574  mov     rcx, rax; void *
0x180020577  mov     rdx, [rdi+8]; Src
0x18002057b  call    memcpy_0
0x180020580  jmp     short loc_1800205B9
0x180020582  movzx   eax, word ptr [r8]
0x180020586  mov     [rdx], ax
0x180020589  jmp     short loc_1800205B9
0x18002058b  mov     rcx, [rdx]; bstrString
0x18002058e  xor     esi, esi
0x180020590  cmp     [r8], rsi
0x180020593  jz      short loc_1800205A9
0x180020595  call    cs:__imp_SysFreeString
0x18002059b  mov     rcx, [rdi]; psz
0x18002059e  call    cs:__imp_SysAllocString
0x1800205a4  mov     rsi, rax
0x1800205a7  jmp     short loc_1800205AF
0x1800205a9  call    cs:__imp_SysFreeString
0x1800205af  mov     [rbx], rsi
0x1800205b2  jmp     short loc_1800205B9
0x1800205b4  mov     eax, [r8]
0x1800205b7  mov     [rdx], eax
0x1800205b9  mov     rbx, [rsp+28h+arg_0]
0x1800205be  mov     rsi, [rsp+28h+arg_8]
0x1800205c3  add     rsp, 20h
0x1800205c7  pop     rdi
0x1800205c8  retn
```
