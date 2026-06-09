# IIsSchemaClass::IIsSchemaClass(ushort const *)

- ea: `0x180019a80`
- end: `0x180019aeb`
- name: `??0IIsSchemaClass@@QEAA@PEBG@Z`
- size: `107`
- prototype: `IIsSchemaClass *(IIsSchemaClass *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001a578`
- `0x18001b62c`

## callees

- `0x1800010fc`
- `0x180019990`
- `0x180019a80`
- `0x18001d66a`

## pseudocode

```c
IIsSchemaClass *__fastcall IIsSchemaClass::IIsSchemaClass(IIsSchemaClass *this, unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned __int64 v5; // rsi
  unsigned __int16 *v6; // rax

  memset_0((char *)this + 8, 0, 0x60u);
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = (int)v4 + 1;
  v6 = (unsigned __int16 *)operator new[](saturated_mul(v5, 2u));
  *(_QWORD *)this = v6;
  if ( v6 )
    StringCchCopyW(v6, v5, a2);
  return this;
}

```

## disassembly

```asm
0x180019a80  push    rbx
0x180019a82  push    rbp
0x180019a83  push    rsi
0x180019a84  push    rdi
0x180019a85  sub     rsp, 28h
0x180019a89  mov     rdi, rdx
0x180019a8c  mov     rbx, rcx
0x180019a8f  xor     edx, edx; Val
0x180019a91  add     rcx, 8; void *
0x180019a95  lea     r8d, [rdx+60h]; Size
0x180019a99  call    memset_0
0x180019a9e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180019aa2  mov     rax, rcx
0x180019aa5  xor     ebp, ebp
0x180019aa7  inc     rax
0x180019aaa  cmp     [rdi+rax*2], bp
0x180019aae  jnz     short loc_180019AA7
0x180019ab0  inc     eax
0x180019ab2  movsxd  rsi, eax
0x180019ab5  mov     eax, 2
0x180019aba  mul     rsi
0x180019abd  cmovb   rax, rcx
0x180019ac1  mov     rcx, rax; unsigned __int64
0x180019ac4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019ac9  mov     [rbx], rax
0x180019acc  test    rax, rax
0x180019acf  jz      short loc_180019ADF
0x180019ad1  mov     r8, rdi; unsigned __int16 *
0x180019ad4  mov     rdx, rsi; unsigned __int64
0x180019ad7  mov     rcx, rax; unsigned __int16 *
0x180019ada  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019adf  mov     rax, rbx
0x180019ae2  add     rsp, 28h
0x180019ae6  pop     rdi
0x180019ae7  pop     rsi
0x180019ae8  pop     rbp
0x180019ae9  pop     rbx
0x180019aea  retn
```
