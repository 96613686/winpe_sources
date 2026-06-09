# CRegistry::GetCurrentSubKeyValue(ushort const *,void *,ulong *)

- ea: `0x140012ea0`
- end: `0x140012edd`
- name: `?GetCurrentSubKeyValue@CRegistry@@QEAAKPEBGPEAXPEAK@Z`
- size: `61`
- prototype: `LSTATUS __fastcall(CRegistry *this, const unsigned __int16 *, BYTE *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140012f60`

## callees

- `0x140012c00`
- `0x140012ea0`
- `0x140013440`

## pseudocode

```c
LSTATUS __fastcall CRegistry::GetCurrentSubKeyValue(
        CRegistry *this,
        const unsigned __int16 *a2,
        BYTE *a3,
        unsigned int *a4)
{
  LSTATUS result; // eax

  result = CRegistry::OpenSubKey(this);
  if ( !result )
    return CRegistry::GetCurrentRawSubKeyValue((HKEY *)this, a2, a3, 0, a4);
  return result;
}

```

## disassembly

```asm
0x140012ea0  push    rbx
0x140012ea2  push    rbp
0x140012ea3  push    rsi
0x140012ea4  push    rdi
0x140012ea5  sub     rsp, 38h
0x140012ea9  mov     rdi, r9
0x140012eac  mov     rsi, r8
0x140012eaf  mov     rbp, rdx
0x140012eb2  mov     rbx, rcx
0x140012eb5  call    ?OpenSubKey@CRegistry@@AEAAKXZ; CRegistry::OpenSubKey(void)
0x140012eba  test    eax, eax
0x140012ebc  jnz     short loc_140012ED4
0x140012ebe  xor     r9d, r9d; unsigned int *
0x140012ec1  mov     [rsp+58h+var_38], rdi; unsigned int *
0x140012ec6  mov     r8, rsi; void *
0x140012ec9  mov     rdx, rbp; unsigned __int16 *
0x140012ecc  mov     rcx, rbx; this
0x140012ecf  call    ?GetCurrentRawSubKeyValue@CRegistry@@AEAAKPEBGPEAXPEAK2@Z; CRegistry::GetCurrentRawSubKeyValue(ushort const *,void *,ulong *,ulong *)
0x140012ed4  add     rsp, 38h
0x140012ed8  pop     rdi
0x140012ed9  pop     rsi
0x140012eda  pop     rbp
0x140012edb  pop     rbx
0x140012edc  retn
```
