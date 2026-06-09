# WMDSPPropValFromVar

- ea: `0x180045064`
- end: `0x180045155`
- name: `WMDSPPropValFromVar`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044830`
- `0x1800452b0`

## callees

- `0x180045064`
- `0x180045805`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800450d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800450d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800450ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800450ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18004512a`
- `OLEAUT32!__imp_SysAllocString` at `0x18004512a`
- `OLEAUT32!__imp_SysFreeString` at `0x180045120`
- `OLEAUT32!__imp_SysFreeString` at `0x180045135`
- `OLEAUT32!__imp_SysFreeString` at `0x180045120`
- `OLEAUT32!__imp_SysFreeString` at `0x180045135`

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
0x180045064  mov     [rsp+arg_0], rbx
0x180045069  mov     [rsp+arg_8], rsi
0x18004506e  push    rdi
0x18004506f  sub     rsp, 20h
0x180045073  movzx   r8d, word ptr [rcx]
0x180045077  mov     rbx, rdx
0x18004507a  mov     rdi, rcx
0x18004507d  sub     r8d, 3
0x180045081  jz      loc_180045140
0x180045087  sub     r8d, 1
0x18004508b  jz      loc_180045140
0x180045091  sub     r8d, 1
0x180045095  jz      short loc_1800450C3
0x180045097  sub     r8d, 3
0x18004509b  jz      short loc_180045115
0x18004509d  sub     r8d, 3
0x1800450a1  jz      short loc_18004510C
0x1800450a3  sub     r8d, 8
0x1800450a7  jz      loc_180045140
0x1800450ad  sub     r8d, 1
0x1800450b1  jz      short loc_1800450C3
0x1800450b3  sub     r8d, 2Dh ; '-'
0x1800450b7  jz      short loc_1800450CC
0x1800450b9  cmp     r8d, 7
0x1800450bd  jnz     loc_180045145
0x1800450c3  mov     rax, [rcx+8]
0x1800450c7  mov     [rdx], rax
0x1800450ca  jmp     short loc_180045145
0x1800450cc  mov     rcx, [rdx+8]; pv
0x1800450d0  xor     esi, esi
0x1800450d2  test    rcx, rcx
0x1800450d5  jz      short loc_1800450DD
0x1800450d7  call    cs:__imp_CoTaskMemFree
0x1800450dd  mov     eax, [rdi+8]
0x1800450e0  mov     [rbx], eax
0x1800450e2  mov     [rbx+8], rsi
0x1800450e6  test    eax, eax
0x1800450e8  jz      short loc_180045145
0x1800450ea  mov     ecx, eax; cb
0x1800450ec  call    cs:__imp_CoTaskMemAlloc
0x1800450f2  mov     [rbx+8], rax
0x1800450f6  test    rax, rax
0x1800450f9  jz      short loc_180045145
0x1800450fb  mov     r8d, [rbx]; Size
0x1800450fe  mov     rcx, rax; void *
0x180045101  mov     rdx, [rdi+10h]; Src
0x180045105  call    memcpy_0
0x18004510a  jmp     short loc_180045145
0x18004510c  movzx   eax, word ptr [rcx+8]
0x180045110  mov     [rdx], ax
0x180045113  jmp     short loc_180045145
0x180045115  xor     esi, esi
0x180045117  cmp     [rcx+8], rsi
0x18004511b  mov     rcx, [rdx]; bstrString
0x18004511e  jz      short loc_180045135
0x180045120  call    cs:__imp_SysFreeString
0x180045126  mov     rcx, [rdi+8]; psz
0x18004512a  call    cs:__imp_SysAllocString
0x180045130  mov     rsi, rax
0x180045133  jmp     short loc_18004513B
0x180045135  call    cs:__imp_SysFreeString
0x18004513b  mov     [rbx], rsi
0x18004513e  jmp     short loc_180045145
0x180045140  mov     eax, [rcx+8]
0x180045143  mov     [rdx], eax
0x180045145  mov     rbx, [rsp+28h+arg_0]
0x18004514a  mov     rsi, [rsp+28h+arg_8]
0x18004514f  add     rsp, 20h
0x180045153  pop     rdi
0x180045154  retn
```
