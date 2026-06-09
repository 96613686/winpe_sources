# WMDSPPropVal2Var

- ea: `0x180010b7c`
- end: `0x180010c6e`
- name: `WMDSPPropVal2Var`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011090`

## callees

- `0x180010b7c`
- `0x1800114b1`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010c42`
- `OLEAUT32!__imp_SysAllocString` at `0x180010c42`
- `OLEAUT32!__imp_SysFreeString` at `0x180010c39`
- `OLEAUT32!__imp_SysFreeString` at `0x180010c4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180010c39`
- `OLEAUT32!__imp_SysFreeString` at `0x180010c4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010bef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010bef`

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
      goto LABEL_21;
    case 5:
LABEL_10:
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
LABEL_21:
      *(_DWORD *)(a1 + 8) = *a2;
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
}

```

## disassembly

```asm
0x180010b7c  mov     [rsp+arg_0], rbx
0x180010b81  mov     [rsp+arg_8], rsi
0x180010b86  push    rdi
0x180010b87  sub     rsp, 20h
0x180010b8b  movzx   r8d, word ptr [rcx]
0x180010b8f  mov     rdi, rdx
0x180010b92  mov     rbx, rcx
0x180010b95  sub     r8d, 3
0x180010b99  jz      loc_180010C59
0x180010b9f  sub     r8d, 1
0x180010ba3  jz      loc_180010C59
0x180010ba9  sub     r8d, 1
0x180010bad  jz      short loc_180010BDB
0x180010baf  sub     r8d, 3
0x180010bb3  jz      short loc_180010C2E
0x180010bb5  sub     r8d, 3
0x180010bb9  jz      short loc_180010C25
0x180010bbb  sub     r8d, 8
0x180010bbf  jz      loc_180010C59
0x180010bc5  sub     r8d, 1
0x180010bc9  jz      short loc_180010BDB
0x180010bcb  sub     r8d, 2Dh ; '-'
0x180010bcf  jz      short loc_180010BE4
0x180010bd1  cmp     r8d, 7
0x180010bd5  jnz     loc_180010C5E
0x180010bdb  mov     rax, [rdx]
0x180010bde  mov     [rcx+8], rax
0x180010be2  jmp     short loc_180010C5E
0x180010be4  mov     rcx, [rcx+10h]; pv
0x180010be8  xor     esi, esi
0x180010bea  test    rcx, rcx
0x180010bed  jz      short loc_180010BF5
0x180010bef  call    cs:__imp_CoTaskMemFree
0x180010bf5  mov     eax, [rdi]
0x180010bf7  mov     [rbx+8], eax
0x180010bfa  mov     [rbx+10h], rsi
0x180010bfe  test    eax, eax
0x180010c00  jz      short loc_180010C5E
0x180010c02  mov     ecx, eax; cb
0x180010c04  call    cs:__imp_CoTaskMemAlloc
0x180010c0a  mov     [rbx+10h], rax
0x180010c0e  test    rax, rax
0x180010c11  jz      short loc_180010C5E
0x180010c13  mov     r8d, [rbx+8]; Size
0x180010c17  mov     rcx, rax; void *
0x180010c1a  mov     rdx, [rdi+8]; Src
0x180010c1e  call    memcpy_0
0x180010c23  jmp     short loc_180010C5E
0x180010c25  movzx   eax, word ptr [rdx]
0x180010c28  mov     [rcx+8], ax
0x180010c2c  jmp     short loc_180010C5E
0x180010c2e  mov     rcx, [rcx+8]; bstrString
0x180010c32  xor     esi, esi
0x180010c34  cmp     [rdx], rsi
0x180010c37  jz      short loc_180010C4D
0x180010c39  call    cs:__imp_SysFreeString
0x180010c3f  mov     rcx, [rdi]; psz
0x180010c42  call    cs:__imp_SysAllocString
0x180010c48  mov     rsi, rax
0x180010c4b  jmp     short loc_180010C53
0x180010c4d  call    cs:__imp_SysFreeString
0x180010c53  mov     [rbx+8], rsi
0x180010c57  jmp     short loc_180010C5E
0x180010c59  mov     eax, [rdx]
0x180010c5b  mov     [rcx+8], eax
0x180010c5e  mov     rbx, [rsp+28h+arg_0]
0x180010c63  mov     rsi, [rsp+28h+arg_8]
0x180010c68  add     rsp, 20h
0x180010c6c  pop     rdi
0x180010c6d  retn
```
