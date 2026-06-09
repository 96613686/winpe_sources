# WMDSPPropValFromVar

- ea: `0x1800207a0`
- end: `0x180020891`
- name: `WMDSPPropValFromVar`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ff80`
- `0x180020ab0`

## callees

- `0x1800207a0`
- `0x180021005`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180020866`
- `OLEAUT32!__imp_SysAllocString` at `0x180020866`
- `OLEAUT32!__imp_SysFreeString` at `0x18002085c`
- `OLEAUT32!__imp_SysFreeString` at `0x180020871`
- `OLEAUT32!__imp_SysFreeString` at `0x18002085c`
- `OLEAUT32!__imp_SysFreeString` at `0x180020871`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020828`

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
0x1800207a0  mov     [rsp+arg_0], rbx
0x1800207a5  mov     [rsp+arg_8], rsi
0x1800207aa  push    rdi
0x1800207ab  sub     rsp, 20h
0x1800207af  movzx   r8d, word ptr [rcx]
0x1800207b3  mov     rbx, rdx
0x1800207b6  mov     rdi, rcx
0x1800207b9  sub     r8d, 3
0x1800207bd  jz      loc_18002087C
0x1800207c3  sub     r8d, 1
0x1800207c7  jz      loc_18002087C
0x1800207cd  sub     r8d, 1
0x1800207d1  jz      short loc_1800207FF
0x1800207d3  sub     r8d, 3
0x1800207d7  jz      short loc_180020851
0x1800207d9  sub     r8d, 3
0x1800207dd  jz      short loc_180020848
0x1800207df  sub     r8d, 8
0x1800207e3  jz      loc_18002087C
0x1800207e9  sub     r8d, 1
0x1800207ed  jz      short loc_1800207FF
0x1800207ef  sub     r8d, 2Dh ; '-'
0x1800207f3  jz      short loc_180020808
0x1800207f5  cmp     r8d, 7
0x1800207f9  jnz     loc_180020881
0x1800207ff  mov     rax, [rcx+8]
0x180020803  mov     [rdx], rax
0x180020806  jmp     short loc_180020881
0x180020808  mov     rcx, [rdx+8]; pv
0x18002080c  xor     esi, esi
0x18002080e  test    rcx, rcx
0x180020811  jz      short loc_180020819
0x180020813  call    cs:__imp_CoTaskMemFree
0x180020819  mov     eax, [rdi+8]
0x18002081c  mov     [rbx], eax
0x18002081e  mov     [rbx+8], rsi
0x180020822  test    eax, eax
0x180020824  jz      short loc_180020881
0x180020826  mov     ecx, eax; cb
0x180020828  call    cs:__imp_CoTaskMemAlloc
0x18002082e  mov     [rbx+8], rax
0x180020832  test    rax, rax
0x180020835  jz      short loc_180020881
0x180020837  mov     r8d, [rbx]; Size
0x18002083a  mov     rcx, rax; void *
0x18002083d  mov     rdx, [rdi+10h]; Src
0x180020841  call    memcpy_0
0x180020846  jmp     short loc_180020881
0x180020848  movzx   eax, word ptr [rcx+8]
0x18002084c  mov     [rdx], ax
0x18002084f  jmp     short loc_180020881
0x180020851  xor     esi, esi
0x180020853  cmp     [rcx+8], rsi
0x180020857  mov     rcx, [rdx]; bstrString
0x18002085a  jz      short loc_180020871
0x18002085c  call    cs:__imp_SysFreeString
0x180020862  mov     rcx, [rdi+8]; psz
0x180020866  call    cs:__imp_SysAllocString
0x18002086c  mov     rsi, rax
0x18002086f  jmp     short loc_180020877
0x180020871  call    cs:__imp_SysFreeString
0x180020877  mov     [rbx], rsi
0x18002087a  jmp     short loc_180020881
0x18002087c  mov     eax, [rcx+8]
0x18002087f  mov     [rdx], eax
0x180020881  mov     rbx, [rsp+28h+arg_0]
0x180020886  mov     rsi, [rsp+28h+arg_8]
0x18002088b  add     rsp, 20h
0x18002088f  pop     rdi
0x180020890  retn
```
