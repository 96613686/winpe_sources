# CommonUtil::VariantExtractBinaryBuffer(tagVARIANT const &,void const * *,unsigned __int64 *)

- ea: `0x180008de0`
- end: `0x180008e45`
- name: `?VariantExtractBinaryBuffer@CommonUtil@@YAJAEBUtagVARIANT@@PEAPEBXPEA_K@Z`
- size: `101`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, const struct tagVARIANT *, const void **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002c08`
- `0x180005010`

## callees

- `0x180008de0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180008e14`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180008e14`

## pseudocode

```c
__int64 __fastcall CommonUtil::VariantExtractBinaryBuffer(
        CommonUtil *this,
        const struct tagVARIANT *a2,
        const void **a3,
        unsigned __int64 *a4)
{
  SAFEARRAY *v6; // rbx

  *(_QWORD *)&a2->vt = 0;
  *a3 = 0;
  if ( *(_WORD *)this != 8209 )
    return 2147942487LL;
  v6 = (SAFEARRAY *)*((_QWORD *)this + 1);
  if ( SafeArrayGetDim(v6) != 1 )
    return 2147942487LL;
  *(_QWORD *)&a2->vt = v6->pvData;
  *a3 = (const void *)v6->rgsabound[0].cElements;
  return 0;
}

```

## disassembly

```asm
0x180008de0  mov     [rsp+arg_0], rbx
0x180008de5  mov     [rsp+arg_8], rsi
0x180008dea  push    rdi
0x180008deb  sub     rsp, 20h
0x180008def  mov     eax, 2011h
0x180008df4  mov     qword ptr [rdx], 0
0x180008dfb  mov     rdi, r8
0x180008dfe  mov     rsi, rdx
0x180008e01  mov     qword ptr [r8], 0
0x180008e08  cmp     [rcx], ax
0x180008e0b  jnz     short loc_180008E30
0x180008e0d  mov     rbx, [rcx+8]
0x180008e11  mov     rcx, rbx; psa
0x180008e14  call    cs:__imp_SafeArrayGetDim
0x180008e1a  cmp     eax, 1
0x180008e1d  jnz     short loc_180008E30
0x180008e1f  mov     rax, [rbx+10h]
0x180008e23  mov     [rsi], rax
0x180008e26  mov     eax, [rbx+18h]
0x180008e29  mov     [rdi], rax
0x180008e2c  xor     eax, eax
0x180008e2e  jmp     short loc_180008E35
0x180008e30  mov     eax, 80070057h
0x180008e35  mov     rbx, [rsp+28h+arg_0]
0x180008e3a  mov     rsi, [rsp+28h+arg_8]
0x180008e3f  add     rsp, 20h
0x180008e43  pop     rdi
0x180008e44  retn
```
