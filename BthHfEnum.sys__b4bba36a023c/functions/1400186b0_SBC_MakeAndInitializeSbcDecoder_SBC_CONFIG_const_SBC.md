# SBC::MakeAndInitializeSbcDecoder(SBC_CONFIG const &,SBC * *)

- ea: `0x1400186b0`
- end: `0x140018738`
- name: `?MakeAndInitializeSbcDecoder@SBC@@SAJAEBUSBC_CONFIG@@PEAPEAV1@@Z`
- size: `136`
- prototype: `__int64 __fastcall(const struct SBC_CONFIG *, struct SBC **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x140017988`

## callees

- `0x140015d00`
- `0x140017fe8`
- `0x1400186b0`
- `0x14001b2c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400186dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400186dc`

## pseudocode

```c
__int64 __fastcall SBC::MakeAndInitializeSbcDecoder(const struct SBC_CONFIG *a1, struct SBC **a2)
{
  SBC *Pool2; // rax
  SBC *v5; // rbx
  int v6; // edi

  *a2 = 0;
  Pool2 = (SBC *)ExAllocatePool2(64, 5416, 1684882288);
  v5 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x1528u);
    v6 = SBC::ConfigDecode(v5, a1);
    if ( v6 < 0 )
      operator delete(v5);
    else
      *a2 = v5;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400186b0  mov     [rsp+arg_0], rbx
0x1400186b5  mov     [rsp+arg_8], rsi
0x1400186ba  push    rdi
0x1400186bb  sub     rsp, 20h
0x1400186bf  mov     rsi, rdx
0x1400186c2  mov     qword ptr [rdx], 0
0x1400186c9  mov     rdi, rcx
0x1400186cc  mov     edx, 1528h
0x1400186d1  mov     ecx, 40h ; '@'
0x1400186d6  mov     r8d, 646D4370h
0x1400186dc  call    cs:__imp_ExAllocatePool2
0x1400186e3  nop     dword ptr [rax+rax+00h]
0x1400186e8  mov     rbx, rax
0x1400186eb  test    rax, rax
0x1400186ee  jz      short loc_140018720
0x1400186f0  xor     edx, edx; Val
0x1400186f2  mov     r8d, 1528h; Size
0x1400186f8  mov     rcx, rax; void *
0x1400186fb  call    memset
0x140018700  mov     rdx, rdi; struct SBC_CONFIG *
0x140018703  mov     rcx, rbx; this
0x140018706  call    ?ConfigDecode@SBC@@QEAAJAEBUSBC_CONFIG@@@Z; SBC::ConfigDecode(SBC_CONFIG const &)
0x14001870b  mov     edi, eax
0x14001870d  test    eax, eax
0x14001870f  js      short loc_140018716
0x140018711  mov     [rsi], rbx
0x140018714  jmp     short loc_140018725
0x140018716  mov     rcx, rbx; void *
0x140018719  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001871e  jmp     short loc_140018725
0x140018720  mov     edi, 0C000009Ah
0x140018725  mov     rbx, [rsp+28h+arg_0]
0x14001872a  mov     eax, edi
0x14001872c  mov     rsi, [rsp+28h+arg_8]
0x140018731  add     rsp, 20h
0x140018735  pop     rdi
0x140018736  retn
```
