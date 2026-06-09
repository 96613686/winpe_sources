# CRegistry::OpenLocalMachineKeyAndReadValue(ushort const *,ushort const *,CHString &)

- ea: `0x1400133e0`
- end: `0x140013433`
- name: `?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z`
- size: `83`
- prototype: `LSTATUS __fastcall(HKEY *this, WCHAR *, const unsigned __int16 *, struct CHString *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140012720`
- `0x1400131d0`
- `0x1400133e0`

## pseudocode

```c
LSTATUS __fastcall CRegistry::OpenLocalMachineKeyAndReadValue(
        HKEY *this,
        WCHAR *a2,
        const unsigned __int16 *a3,
        struct CHString *a4)
{
  LSTATUS result; // eax

  result = CRegistry::Open((CRegistry *)this, HKEY_LOCAL_MACHINE, a2, 0x20019u);
  if ( !result )
    return CRegistry::GetCurrentKeyValue((CRegistry *)this, this[1], a3, a4);
  return result;
}

```

## disassembly

```asm
0x1400133e0  mov     [rsp+arg_0], rbx
0x1400133e5  mov     [rsp+arg_8], rsi
0x1400133ea  push    rdi
0x1400133eb  sub     rsp, 20h
0x1400133ef  mov     rsi, r8
0x1400133f2  mov     rdi, r9
0x1400133f5  mov     r8, rdx; unsigned __int16 *
0x1400133f8  mov     r9d, 20019h; unsigned int
0x1400133fe  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x140013405  mov     rbx, rcx
0x140013408  call    ?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x14001340d  test    eax, eax
0x14001340f  jnz     short loc_140013423
0x140013411  mov     rdx, [rbx+8]; HKEY
0x140013415  mov     r9, rdi; struct CHString *
0x140013418  mov     r8, rsi; unsigned __int16 *
0x14001341b  mov     rcx, rbx; this
0x14001341e  call    ?GetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(HKEY__ *,ushort const *,CHString &)
0x140013423  mov     rbx, [rsp+28h+arg_0]
0x140013428  mov     rsi, [rsp+28h+arg_8]
0x14001342d  add     rsp, 20h
0x140013431  pop     rdi
0x140013432  retn
```
