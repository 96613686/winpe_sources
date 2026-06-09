# CRegistry::GetCurrentSubKeyValue(ushort const *,ulong &)

- ea: `0x140012e00`
- end: `0x140012e43`
- name: `?GetCurrentSubKeyValue@CRegistry@@QEAAKPEBGAEAK@Z`
- size: `67`
- prototype: `unsigned int __fastcall(HKEY *this, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140012660`
- `0x140012e00`
- `0x140013440`

## pseudocode

```c
unsigned int __fastcall CRegistry::GetCurrentSubKeyValue(HKEY *this, const unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int result; // eax

  result = CRegistry::OpenSubKey((CRegistry *)this);
  if ( !result )
    return CRegistry::GetCurrentKeyValue((CRegistry *)this, this[2], a2, a3);
  return result;
}

```

## disassembly

```asm
0x140012e00  mov     [rsp+arg_0], rbx
0x140012e05  mov     [rsp+arg_8], rsi
0x140012e0a  push    rdi
0x140012e0b  sub     rsp, 20h
0x140012e0f  mov     rdi, r8
0x140012e12  mov     rsi, rdx
0x140012e15  mov     rbx, rcx
0x140012e18  call    ?OpenSubKey@CRegistry@@AEAAKXZ; CRegistry::OpenSubKey(void)
0x140012e1d  test    eax, eax
0x140012e1f  jnz     short loc_140012E33
0x140012e21  mov     rdx, [rbx+10h]; HKEY
0x140012e25  mov     r9, rdi; unsigned int *
0x140012e28  mov     r8, rsi; unsigned __int16 *
0x140012e2b  mov     rcx, rbx; this
0x140012e2e  call    ?GetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAK@Z; CRegistry::GetCurrentKeyValue(HKEY__ *,ushort const *,ulong &)
0x140012e33  mov     rbx, [rsp+28h+arg_0]
0x140012e38  mov     rsi, [rsp+28h+arg_8]
0x140012e3d  add     rsp, 20h
0x140012e41  pop     rdi
0x140012e42  retn
```
