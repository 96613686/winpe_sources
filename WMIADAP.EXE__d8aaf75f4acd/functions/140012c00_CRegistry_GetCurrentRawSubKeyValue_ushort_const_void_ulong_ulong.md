# CRegistry::GetCurrentRawSubKeyValue(ushort const *,void *,ulong *,ulong *)

- ea: `0x140012c00`
- end: `0x140012c4b`
- name: `?GetCurrentRawSubKeyValue@CRegistry@@AEAAKPEBGPEAXPEAK2@Z`
- size: `75`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *, BYTE *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140012ea0`

## callees

- `0x140012bc0`
- `0x140012c00`
- `0x140013440`

## pseudocode

```c
LSTATUS __fastcall CRegistry::GetCurrentRawSubKeyValue(
        HKEY *this,
        const unsigned __int16 *a2,
        BYTE *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  LSTATUS result; // eax

  result = CRegistry::OpenSubKey((CRegistry *)this);
  if ( !result )
    return CRegistry::GetCurrentRawKeyValue((CRegistry *)this, this[2], a2, a3, a4, a5);
  return result;
}

```

## disassembly

```asm
0x140012c00  push    rbx
0x140012c02  push    rbp
0x140012c03  push    rsi
0x140012c04  push    rdi
0x140012c05  sub     rsp, 38h
0x140012c09  mov     rdi, r9
0x140012c0c  mov     rsi, r8
0x140012c0f  mov     rbp, rdx
0x140012c12  mov     rbx, rcx
0x140012c15  call    ?OpenSubKey@CRegistry@@AEAAKXZ; CRegistry::OpenSubKey(void)
0x140012c1a  test    eax, eax
0x140012c1c  jnz     short loc_140012C42
0x140012c1e  mov     rax, [rsp+58h+arg_20]
0x140012c26  mov     r9, rsi; void *
0x140012c29  mov     rdx, [rbx+10h]; HKEY
0x140012c2d  mov     r8, rbp; unsigned __int16 *
0x140012c30  mov     [rsp+58h+var_30], rax; unsigned int *
0x140012c35  mov     rcx, rbx; this
0x140012c38  mov     [rsp+58h+var_38], rdi; unsigned int *
0x140012c3d  call    ?GetCurrentRawKeyValue@CRegistry@@AEAAKPEAUHKEY__@@PEBGPEAXPEAK3@Z; CRegistry::GetCurrentRawKeyValue(HKEY__ *,ushort const *,void *,ulong *,ulong *)
0x140012c42  add     rsp, 38h
0x140012c46  pop     rdi
0x140012c47  pop     rsi
0x140012c48  pop     rbp
0x140012c49  pop     rbx
0x140012c4a  retn
```
