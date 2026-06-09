# WMDSPPropValFromVar

- ea: `0x180009574`
- end: `0x18000965c`
- name: `WMDSPPropValFromVar`
- size: `232`
- prototype: `void __fastcall(__int64, OLECHAR **)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008dc0`
- `0x180008df0`
- `0x1800094e0`

## callees

- `0x180009574`
- `0x180016ac1`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000960e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000960e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800095f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800095f9`
- `OLEAUT32!__imp_SysAllocString` at `0x180009643`
- `OLEAUT32!__imp_SysAllocString` at `0x180009643`
- `OLEAUT32!__imp_SysFreeString` at `0x180009639`
- `OLEAUT32!__imp_SysFreeString` at `0x18000964e`
- `OLEAUT32!__imp_SysFreeString` at `0x180009639`
- `OLEAUT32!__imp_SysFreeString` at `0x18000964e`

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
      goto LABEL_8;
    case 5:
LABEL_13:
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
LABEL_8:
      *(_DWORD *)a2 = *(_DWORD *)(a1 + 8);
      return;
    case 0x14:
      goto LABEL_13;
    case 0x41:
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
      break;
    case 0x48:
      goto LABEL_13;
  }
}

```

## disassembly

```asm
0x180009574  mov     [rsp+arg_0], rbx
0x180009579  mov     [rsp+arg_8], rsi
0x18000957e  push    rdi
0x18000957f  sub     rsp, 20h
0x180009583  movzx   r8d, word ptr [rcx]
0x180009587  mov     rbx, rdx
0x18000958a  mov     rdi, rcx
0x18000958d  sub     r8d, 3
0x180009591  jz      short loc_1800095C6
0x180009593  sub     r8d, 1
0x180009597  jz      short loc_1800095C6
0x180009599  sub     r8d, 1
0x18000959d  jz      short loc_1800095E5
0x18000959f  sub     r8d, 3
0x1800095a3  jz      loc_18000962E
0x1800095a9  sub     r8d, 3
0x1800095ad  jnz     short loc_1800095CD
0x1800095af  movzx   eax, word ptr [rcx+8]
0x1800095b3  mov     [rdx], ax
0x1800095b6  mov     rbx, [rsp+28h+arg_0]
0x1800095bb  mov     rsi, [rsp+28h+arg_8]
0x1800095c0  add     rsp, 20h
0x1800095c4  pop     rdi
0x1800095c5  retn
0x1800095c6  mov     eax, [rcx+8]
0x1800095c9  mov     [rdx], eax
0x1800095cb  jmp     short loc_1800095B6
0x1800095cd  sub     r8d, 8
0x1800095d1  jz      short loc_1800095C6
0x1800095d3  sub     r8d, 1
0x1800095d7  jz      short loc_1800095E5
0x1800095d9  sub     r8d, 2Dh ; '-'
0x1800095dd  jz      short loc_1800095EE
0x1800095df  cmp     r8d, 7
0x1800095e3  jnz     short loc_1800095B6
0x1800095e5  mov     rax, [rcx+8]
0x1800095e9  mov     [rdx], rax
0x1800095ec  jmp     short loc_1800095B6
0x1800095ee  mov     rcx, [rdx+8]; pv
0x1800095f2  xor     esi, esi
0x1800095f4  test    rcx, rcx
0x1800095f7  jz      short loc_1800095FF
0x1800095f9  call    cs:__imp_CoTaskMemFree
0x1800095ff  mov     eax, [rdi+8]
0x180009602  mov     [rbx], eax
0x180009604  mov     [rbx+8], rsi
0x180009608  test    eax, eax
0x18000960a  jz      short loc_1800095B6
0x18000960c  mov     ecx, eax; cb
0x18000960e  call    cs:__imp_CoTaskMemAlloc
0x180009614  mov     [rbx+8], rax
0x180009618  test    rax, rax
0x18000961b  jz      short loc_1800095B6
0x18000961d  mov     r8d, [rbx]; Size
0x180009620  mov     rcx, rax; void *
0x180009623  mov     rdx, [rdi+10h]; Src
0x180009627  call    memcpy_0
0x18000962c  jmp     short loc_1800095B6
0x18000962e  xor     esi, esi
0x180009630  cmp     [rcx+8], rsi
0x180009634  mov     rcx, [rdx]; bstrString
0x180009637  jz      short loc_18000964E
0x180009639  call    cs:__imp_SysFreeString
0x18000963f  mov     rcx, [rdi+8]; psz
0x180009643  call    cs:__imp_SysAllocString
0x180009649  mov     rsi, rax
0x18000964c  jmp     short loc_180009654
0x18000964e  call    cs:__imp_SysFreeString
0x180009654  mov     [rbx], rsi
0x180009657  jmp     loc_1800095B6
```
