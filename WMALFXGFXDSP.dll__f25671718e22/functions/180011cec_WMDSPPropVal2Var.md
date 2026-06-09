# WMDSPPropVal2Var

- ea: `0x180011cec`
- end: `0x180011dd8`
- name: `WMDSPPropVal2Var`
- size: `236`
- prototype: `void __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011cc0`

## callees

- `0x180011cec`
- `0x180016ac1`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d6d`
- `OLEAUT32!__imp_SysAllocString` at `0x180011dbe`
- `OLEAUT32!__imp_SysAllocString` at `0x180011dbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180011db5`
- `OLEAUT32!__imp_SysFreeString` at `0x180011dc9`
- `OLEAUT32!__imp_SysFreeString` at `0x180011db5`
- `OLEAUT32!__imp_SysFreeString` at `0x180011dc9`

## pseudocode

```c
void __fastcall WMDSPPropVal2Var(__int64 a1, int *a2)
{
  void *v4; // rcx
  unsigned int v5; // eax
  void *v6; // rax
  OLECHAR *v7; // rcx
  BSTR v8; // rsi

  switch ( *(_WORD *)a1 )
  {
    case 3:
    case 4:
      goto LABEL_2;
    case 5:
LABEL_13:
      *(_QWORD *)(a1 + 8) = *(_QWORD *)a2;
      return;
    case 8:
      v7 = *(OLECHAR **)(a1 + 8);
      v8 = 0;
      if ( *(_QWORD *)a2 )
      {
        SysFreeString(v7);
        v8 = SysAllocString(*(const OLECHAR **)a2);
      }
      else
      {
        SysFreeString(v7);
      }
      *(_QWORD *)(a1 + 8) = v8;
      return;
    case 0xB:
      *(_WORD *)(a1 + 8) = *(_WORD *)a2;
      return;
    case 0x13:
LABEL_2:
      *(_DWORD *)(a1 + 8) = *a2;
      return;
    case 0x14:
      goto LABEL_13;
    case 0x41:
      v4 = *(void **)(a1 + 16);
      if ( v4 )
        CoTaskMemFree(v4);
      v5 = *a2;
      *(_DWORD *)(a1 + 8) = *a2;
      *(_QWORD *)(a1 + 16) = 0;
      if ( v5 )
      {
        v6 = CoTaskMemAlloc(v5);
        *(_QWORD *)(a1 + 16) = v6;
        if ( v6 )
          memcpy_0(v6, *((const void **)a2 + 1), *(unsigned int *)(a1 + 8));
      }
      break;
    case 0x48:
      goto LABEL_13;
  }
}

```

## disassembly

```asm
0x180011cec  mov     [rsp+arg_0], rbx
0x180011cf1  mov     [rsp+arg_8], rsi
0x180011cf6  push    rdi
0x180011cf7  sub     rsp, 20h
0x180011cfb  movzx   r8d, word ptr [rcx]
0x180011cff  mov     rdi, rdx
0x180011d02  mov     rbx, rcx
0x180011d05  sub     r8d, 3
0x180011d09  jnz     short loc_180011D20
0x180011d0b  mov     eax, [rdx]
0x180011d0d  mov     [rcx+8], eax
0x180011d10  mov     rbx, [rsp+28h+arg_0]
0x180011d15  mov     rsi, [rsp+28h+arg_8]
0x180011d1a  add     rsp, 20h
0x180011d1e  pop     rdi
0x180011d1f  retn
0x180011d20  sub     r8d, 1
0x180011d24  jz      short loc_180011D0B
0x180011d26  sub     r8d, 1
0x180011d2a  jz      short loc_180011D59
0x180011d2c  sub     r8d, 3
0x180011d30  jz      short loc_180011DAA
0x180011d32  sub     r8d, 3
0x180011d36  jnz     short loc_180011D41
0x180011d38  movzx   eax, word ptr [rdx]
0x180011d3b  mov     [rcx+8], ax
0x180011d3f  jmp     short loc_180011D10
0x180011d41  sub     r8d, 8
0x180011d45  jz      short loc_180011D0B
0x180011d47  sub     r8d, 1
0x180011d4b  jz      short loc_180011D59
0x180011d4d  sub     r8d, 2Dh ; '-'
0x180011d51  jz      short loc_180011D62
0x180011d53  cmp     r8d, 7
0x180011d57  jnz     short loc_180011D10
0x180011d59  mov     rax, [rdx]
0x180011d5c  mov     [rcx+8], rax
0x180011d60  jmp     short loc_180011D10
0x180011d62  mov     rcx, [rcx+10h]; pv
0x180011d66  xor     esi, esi
0x180011d68  test    rcx, rcx
0x180011d6b  jz      short loc_180011D73
0x180011d6d  call    cs:__imp_CoTaskMemFree
0x180011d73  mov     eax, [rdi]
0x180011d75  mov     [rbx+8], eax
0x180011d78  mov     [rbx+10h], rsi
0x180011d7c  test    eax, eax
0x180011d7e  jz      short loc_180011D10
0x180011d80  mov     ecx, eax; cb
0x180011d82  call    cs:__imp_CoTaskMemAlloc
0x180011d88  mov     [rbx+10h], rax
0x180011d8c  test    rax, rax
0x180011d8f  jz      loc_180011D10
0x180011d95  mov     r8d, [rbx+8]; Size
0x180011d99  mov     rcx, rax; void *
0x180011d9c  mov     rdx, [rdi+8]; Src
0x180011da0  call    memcpy_0
0x180011da5  jmp     loc_180011D10
0x180011daa  mov     rcx, [rcx+8]; bstrString
0x180011dae  xor     esi, esi
0x180011db0  cmp     [rdx], rsi
0x180011db3  jz      short loc_180011DC9
0x180011db5  call    cs:__imp_SysFreeString
0x180011dbb  mov     rcx, [rdi]; psz
0x180011dbe  call    cs:__imp_SysAllocString
0x180011dc4  mov     rsi, rax
0x180011dc7  jmp     short loc_180011DCF
0x180011dc9  call    cs:__imp_SysFreeString
0x180011dcf  mov     [rbx+8], rsi
0x180011dd3  jmp     loc_180011D10
```
