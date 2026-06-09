# WMDSPPropValCopy

- ea: `0x180010c74`
- end: `0x180010d5d`
- name: `WMDSPPropValCopy`
- size: `233`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800109e0`
- `0x180011050`
- `0x1800112f0`

## callees

- `0x180010c74`
- `0x1800114b1`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010d32`
- `OLEAUT32!__imp_SysAllocString` at `0x180010d32`
- `OLEAUT32!__imp_SysFreeString` at `0x180010d29`
- `OLEAUT32!__imp_SysFreeString` at `0x180010d3d`
- `OLEAUT32!__imp_SysFreeString` at `0x180010d29`
- `OLEAUT32!__imp_SysFreeString` at `0x180010d3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010cf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010cf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ce2`

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
0x180010c74  mov     [rsp+arg_0], rbx
0x180010c79  mov     [rsp+arg_8], rsi
0x180010c7e  push    rdi
0x180010c7f  sub     rsp, 20h
0x180010c83  movzx   r9d, cx
0x180010c87  mov     rdi, r8
0x180010c8a  mov     rbx, rdx
0x180010c8d  sub     r9d, 3
0x180010c91  jz      loc_180010D48
0x180010c97  sub     r9d, 1
0x180010c9b  jz      loc_180010D48
0x180010ca1  sub     r9d, 1
0x180010ca5  jz      short loc_180010CCF
0x180010ca7  sub     r9d, 3
0x180010cab  jz      short loc_180010D1F
0x180010cad  sub     r9d, 3
0x180010cb1  jz      short loc_180010D16
0x180010cb3  sub     r9d, 8
0x180010cb7  jz      loc_180010D48
0x180010cbd  sub     r9d, 1
0x180010cc1  jz      short loc_180010CCF
0x180010cc3  sub     r9d, 2Dh ; '-'
0x180010cc7  jz      short loc_180010CD7
0x180010cc9  cmp     r9d, 7
0x180010ccd  jnz     short loc_180010D4D
0x180010ccf  mov     rax, [r8]
0x180010cd2  mov     [rdx], rax
0x180010cd5  jmp     short loc_180010D4D
0x180010cd7  mov     rcx, [rdx+8]; pv
0x180010cdb  xor     esi, esi
0x180010cdd  test    rcx, rcx
0x180010ce0  jz      short loc_180010CE8
0x180010ce2  call    cs:__imp_CoTaskMemFree
0x180010ce8  mov     eax, [rdi]
0x180010cea  mov     [rbx], eax
0x180010cec  mov     [rbx+8], rsi
0x180010cf0  test    eax, eax
0x180010cf2  jz      short loc_180010D4D
0x180010cf4  mov     ecx, eax; cb
0x180010cf6  call    cs:__imp_CoTaskMemAlloc
0x180010cfc  mov     [rbx+8], rax
0x180010d00  test    rax, rax
0x180010d03  jz      short loc_180010D4D
0x180010d05  mov     r8d, [rbx]; Size
0x180010d08  mov     rcx, rax; void *
0x180010d0b  mov     rdx, [rdi+8]; Src
0x180010d0f  call    memcpy_0
0x180010d14  jmp     short loc_180010D4D
0x180010d16  movzx   eax, word ptr [r8]
0x180010d1a  mov     [rdx], ax
0x180010d1d  jmp     short loc_180010D4D
0x180010d1f  mov     rcx, [rdx]; bstrString
0x180010d22  xor     esi, esi
0x180010d24  cmp     [r8], rsi
0x180010d27  jz      short loc_180010D3D
0x180010d29  call    cs:__imp_SysFreeString
0x180010d2f  mov     rcx, [rdi]; psz
0x180010d32  call    cs:__imp_SysAllocString
0x180010d38  mov     rsi, rax
0x180010d3b  jmp     short loc_180010D43
0x180010d3d  call    cs:__imp_SysFreeString
0x180010d43  mov     [rbx], rsi
0x180010d46  jmp     short loc_180010D4D
0x180010d48  mov     eax, [r8]
0x180010d4b  mov     [rdx], eax
0x180010d4d  mov     rbx, [rsp+28h+arg_0]
0x180010d52  mov     rsi, [rsp+28h+arg_8]
0x180010d57  add     rsp, 20h
0x180010d5b  pop     rdi
0x180010d5c  retn
```
