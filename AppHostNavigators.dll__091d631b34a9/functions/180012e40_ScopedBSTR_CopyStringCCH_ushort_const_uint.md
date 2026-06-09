# ScopedBSTR::CopyStringCCH(ushort const *,uint)

- ea: `0x180012e40`
- end: `0x180012e8a`
- name: `?CopyStringCCH@ScopedBSTR@@QEAAJPEBGI@Z`
- size: `74`
- prototype: `__int64 __fastcall(ScopedBSTR *__hidden this, OLECHAR *strIn, UINT ui)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010920`
- `0x180010e40`

## callees

- `0x180012e40`
- `0x180012ea8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180012e5d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180012e5d`

## pseudocode

```c
__int64 __fastcall ScopedBSTR::CopyStringCCH(ScopedBSTR *this, OLECHAR *strIn, UINT ui)
{
  BSTR v3; // rdi
  __int64 result; // rax

  v3 = 0;
  if ( strIn )
  {
    v3 = SysAllocStringLen(strIn, ui);
    if ( !v3 )
      return 2147942414LL;
  }
  ScopedBSTR::Reset(this);
  result = 0;
  *(_QWORD *)this = v3;
  return result;
}

```

## disassembly

```asm
0x180012e40  mov     [rsp+arg_0], rbx
0x180012e45  push    rdi
0x180012e46  sub     rsp, 20h
0x180012e4a  xor     edi, edi
0x180012e4c  mov     rax, rdx
0x180012e4f  mov     rbx, rcx
0x180012e52  test    rdx, rdx
0x180012e55  jz      short loc_180012E72
0x180012e57  mov     edx, r8d; ui
0x180012e5a  mov     rcx, rax; strIn
0x180012e5d  call    cs:__imp_SysAllocStringLen
0x180012e63  mov     rdi, rax
0x180012e66  test    rax, rax
0x180012e69  jnz     short loc_180012E72
0x180012e6b  mov     eax, 8007000Eh
0x180012e70  jmp     short loc_180012E7F
0x180012e72  mov     rcx, rbx; this
0x180012e75  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x180012e7a  xor     eax, eax
0x180012e7c  mov     [rbx], rdi
0x180012e7f  mov     rbx, [rsp+28h+arg_0]
0x180012e84  add     rsp, 20h
0x180012e88  pop     rdi
0x180012e89  retn
```
