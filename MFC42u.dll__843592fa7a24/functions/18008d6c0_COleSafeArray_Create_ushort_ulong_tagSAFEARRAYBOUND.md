# COleSafeArray::Create(ushort,ulong,tagSAFEARRAYBOUND *)

- ea: `0x18008d6c0`
- end: `0x18008d738`
- name: `?Create@COleSafeArray@@QEAAXGKPEAUtagSAFEARRAYBOUND@@@Z`
- size: `120`
- prototype: `void(COleSafeArray *__hidden this, unsigned __int16, unsigned int, struct tagSAFEARRAYBOUND *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18008d620`
- `0x18008d740`

## callees

- `0x18002d800`
- `0x18002da20`
- `0x18008d6c0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18008d6ef`
- `OLEAUT32!__imp_VariantClear` at `0x18008d6ef`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18008d6fd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18008d6fd`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18008d720`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18008d720`

## pseudocode

```c
void __fastcall COleSafeArray::Create(VARIANTARG *this, VARTYPE a2, UINT a3, struct tagSAFEARRAYBOUND *a4)
{
  SAFEARRAY *v8; // rax

  if ( !a3 || !a4 || (a2 & 0x7000) != 0 || a2 < 2u )
    AfxThrowInvalidArgException();
  VariantClear(this);
  v8 = SafeArrayCreate(a2, a3, a4);
  this->llVal = (LONGLONG)v8;
  if ( !v8 )
    AfxThrowMemoryException();
  this[1].decVal.Hi32 = a3;
  this->vt = a2 | 0x2000;
  *(_DWORD *)&this[1].vt = SafeArrayGetElemsize(v8);
}

```

## disassembly

```asm
0x18008d6c0  push    rbx
0x18008d6c2  push    rbp
0x18008d6c3  push    rsi
0x18008d6c4  push    rdi
0x18008d6c5  sub     rsp, 28h
0x18008d6c9  mov     rbp, r9
0x18008d6cc  mov     esi, r8d
0x18008d6cf  movzx   ebx, dx
0x18008d6d2  mov     rdi, rcx
0x18008d6d5  test    r8d, r8d
0x18008d6d8  jz      short loc_18008D732
0x18008d6da  test    r9, r9
0x18008d6dd  jz      short loc_18008D732
0x18008d6df  mov     eax, 7000h
0x18008d6e4  test    ax, dx
0x18008d6e7  jnz     short loc_18008D732
0x18008d6e9  cmp     dx, 2
0x18008d6ed  jb      short loc_18008D732
0x18008d6ef  call    cs:__imp_VariantClear
0x18008d6f5  mov     r8, rbp; rgsabound
0x18008d6f8  mov     edx, esi; cDims
0x18008d6fa  movzx   ecx, bx; vt
0x18008d6fd  call    cs:__imp_SafeArrayCreate
0x18008d703  mov     [rdi+8], rax
0x18008d707  test    rax, rax
0x18008d70a  jnz     short loc_18008D712
0x18008d70c  call    ?AfxThrowMemoryException@@YAXXZ; AfxThrowMemoryException(void)
0x18008d712  or      bx, 2000h
0x18008d717  mov     [rdi+1Ch], esi
0x18008d71a  mov     rcx, rax; psa
0x18008d71d  mov     [rdi], bx
0x18008d720  call    cs:__imp_SafeArrayGetElemsize
0x18008d726  mov     [rdi+18h], eax
0x18008d729  add     rsp, 28h
0x18008d72d  pop     rdi
0x18008d72e  pop     rsi
0x18008d72f  pop     rbp
0x18008d730  pop     rbx
0x18008d731  retn
0x18008d732  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
