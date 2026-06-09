# CRegistry::GetCurrentSubKeyValue(ushort const *,CHString &)

- ea: `0x140012e50`
- end: `0x140012e93`
- name: `?GetCurrentSubKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z`
- size: `67`
- prototype: `unsigned int __fastcall(HKEY *this, const unsigned __int16 *, struct CHString *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140011ee0`

## callees

- `0x140012720`
- `0x140012e50`
- `0x140013440`

## pseudocode

```c
unsigned int __fastcall CRegistry::GetCurrentSubKeyValue(HKEY *this, const unsigned __int16 *a2, struct CHString *a3)
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
0x140012e50  mov     [rsp+arg_0], rbx
0x140012e55  mov     [rsp+arg_8], rsi
0x140012e5a  push    rdi
0x140012e5b  sub     rsp, 20h
0x140012e5f  mov     rdi, r8
0x140012e62  mov     rsi, rdx
0x140012e65  mov     rbx, rcx
0x140012e68  call    ?OpenSubKey@CRegistry@@AEAAKXZ; CRegistry::OpenSubKey(void)
0x140012e6d  test    eax, eax
0x140012e6f  jnz     short loc_140012E83
0x140012e71  mov     rdx, [rbx+10h]; HKEY
0x140012e75  mov     r9, rdi; struct CHString *
0x140012e78  mov     r8, rsi; unsigned __int16 *
0x140012e7b  mov     rcx, rbx; this
0x140012e7e  call    ?GetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(HKEY__ *,ushort const *,CHString &)
0x140012e83  mov     rbx, [rsp+28h+arg_0]
0x140012e88  mov     rsi, [rsp+28h+arg_8]
0x140012e8d  add     rsp, 20h
0x140012e91  pop     rdi
0x140012e92  retn
```
