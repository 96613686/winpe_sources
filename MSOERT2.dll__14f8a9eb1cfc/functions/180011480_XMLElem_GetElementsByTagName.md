# XMLElem_GetElementsByTagName

- ea: `0x180011480`
- end: `0x18001150a`
- name: `XMLElem_GetElementsByTagName`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800116c0`

## callees

- `0x180011480`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800114ae`
- `OLEAUT32!__imp_SysAllocString` at `0x1800114ae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800114e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800114e4`

## pseudocode

```c
__int64 __fastcall XMLElem_GetElementsByTagName(__int64 a1, const OLECHAR *a2, _QWORD *a3)
{
  BSTR v5; // rax
  OLECHAR *v6; // rdi
  unsigned int v7; // ebx

  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  v5 = SysAllocString(a2);
  v6 = v5;
  if ( v5 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD *))(*(_QWORD *)a1 + 400LL))(a1, v5, a3);
    if ( v7 == 1 )
      v7 = -2147467259;
    SysFreeString(v6);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x180011480  mov     [rsp+arg_0], rbx
0x180011485  mov     [rsp+arg_8], rsi
0x18001148a  push    rdi
0x18001148b  sub     rsp, 20h
0x18001148f  mov     rbx, r8
0x180011492  mov     rsi, rcx
0x180011495  test    rcx, rcx
0x180011498  jz      short loc_1800114F5
0x18001149a  test    rdx, rdx
0x18001149d  jz      short loc_1800114F5
0x18001149f  test    rbx, rbx
0x1800114a2  jz      short loc_1800114F5
0x1800114a4  mov     rcx, rdx; psz
0x1800114a7  mov     qword ptr [r8], 0
0x1800114ae  call    cs:__imp_SysAllocString
0x1800114b4  mov     rdi, rax
0x1800114b7  test    rax, rax
0x1800114ba  jz      short loc_1800114EC
0x1800114bc  mov     rcx, [rsi]
0x1800114bf  mov     r8, rbx
0x1800114c2  mov     rdx, rdi
0x1800114c5  mov     rax, [rcx+190h]
0x1800114cc  mov     rcx, rsi
0x1800114cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114d4  mov     ebx, eax
0x1800114d6  mov     rcx, rdi; bstrString
0x1800114d9  cmp     ebx, 1
0x1800114dc  mov     eax, 80004005h
0x1800114e1  cmovz   ebx, eax
0x1800114e4  call    cs:__imp_SysFreeString
0x1800114ea  jmp     short loc_1800114F1
0x1800114ec  mov     ebx, 8007000Eh
0x1800114f1  mov     eax, ebx
0x1800114f3  jmp     short loc_1800114FA
0x1800114f5  mov     eax, 80070057h
0x1800114fa  mov     rbx, [rsp+28h+arg_0]
0x1800114ff  mov     rsi, [rsp+28h+arg_8]
0x180011504  add     rsp, 20h
0x180011508  pop     rdi
0x180011509  retn
```
