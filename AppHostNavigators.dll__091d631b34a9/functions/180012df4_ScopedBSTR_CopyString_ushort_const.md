# ScopedBSTR::CopyString(ushort const *)

- ea: `0x180012df4`
- end: `0x180012e38`
- name: `?CopyString@ScopedBSTR@@QEAAJPEBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(ScopedBSTR *__hidden this, OLECHAR *psz)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b3b0`
- `0x18000b470`
- `0x18000de58`
- `0x1800105a0`

## callees

- `0x180012df4`
- `0x180012ea8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180012e0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180012e0b`

## pseudocode

```c
__int64 __fastcall ScopedBSTR::CopyString(ScopedBSTR *this, OLECHAR *psz)
{
  BSTR v2; // rbx
  __int64 result; // rax

  v2 = 0;
  if ( psz )
  {
    v2 = SysAllocString(psz);
    if ( !v2 )
      return 2147942414LL;
  }
  ScopedBSTR::Reset(this);
  result = 0;
  *(_QWORD *)this = v2;
  return result;
}

```

## disassembly

```asm
0x180012df4  mov     [rsp+arg_0], rbx
0x180012df9  push    rdi
0x180012dfa  sub     rsp, 20h
0x180012dfe  xor     ebx, ebx
0x180012e00  mov     rdi, rcx
0x180012e03  test    rdx, rdx
0x180012e06  jz      short loc_180012E20
0x180012e08  mov     rcx, rdx; psz
0x180012e0b  call    cs:__imp_SysAllocString
0x180012e11  mov     rbx, rax
0x180012e14  test    rax, rax
0x180012e17  jnz     short loc_180012E20
0x180012e19  mov     eax, 8007000Eh
0x180012e1e  jmp     short loc_180012E2D
0x180012e20  mov     rcx, rdi; this
0x180012e23  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x180012e28  xor     eax, eax
0x180012e2a  mov     [rdi], rbx
0x180012e2d  mov     rbx, [rsp+28h+arg_0]
0x180012e32  add     rsp, 20h
0x180012e36  pop     rdi
0x180012e37  retn
```
