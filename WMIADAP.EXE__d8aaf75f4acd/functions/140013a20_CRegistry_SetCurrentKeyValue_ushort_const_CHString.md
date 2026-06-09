# CRegistry::SetCurrentKeyValue(ushort const *,CHString &)

- ea: `0x140013a20`
- end: `0x140013a73`
- name: `?SetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z`
- size: `83`
- prototype: `unsigned int __fastcall(CRegistry *__hidden this, const unsigned __int16 *, struct CHString *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000f91c`

## callees

- `0x140010c20`
- `0x140013800`
- `0x140013a20`
- `0x140013aa0`

## pseudocode

```c
unsigned int __fastcall CRegistry::SetCurrentKeyValue(CRegistry *this, const unsigned __int16 *a2, struct CHString *a3)
{
  int v6; // eax
  HKEY v7; // rdx

  v6 = CHString::Find(a3, 0x25u);
  v7 = (HKEY)*((_QWORD *)this + 1);
  if ( v6 == -1 )
    return CRegistry::SetCurrentKeyValue(this, v7, a2, a3);
  else
    return CRegistry::SetCurrentKeyValueExpand(this, v7, a2, a3);
}

```

## disassembly

```asm
0x140013a20  mov     [rsp+arg_0], rbx
0x140013a25  mov     [rsp+arg_8], rsi
0x140013a2a  push    rdi
0x140013a2b  sub     rsp, 20h
0x140013a2f  mov     rsi, rdx
0x140013a32  mov     rdi, rcx
0x140013a35  mov     edx, 25h ; '%'; unsigned __int16
0x140013a3a  mov     rcx, r8; this
0x140013a3d  mov     rbx, r8
0x140013a40  call    ?Find@CHString@@QEBAHG@Z; CHString::Find(ushort)
0x140013a45  mov     rdx, [rdi+8]; HKEY
0x140013a49  mov     r9, rbx; struct CHString *
0x140013a4c  mov     r8, rsi; unsigned __int16 *
0x140013a4f  mov     rcx, rdi; this
0x140013a52  cmp     eax, 0FFFFFFFFh
0x140013a55  jz      short loc_140013A5E
0x140013a57  call    ?SetCurrentKeyValueExpand@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z; CRegistry::SetCurrentKeyValueExpand(HKEY__ *,ushort const *,CHString &)
0x140013a5c  jmp     short loc_140013A63
0x140013a5e  call    ?SetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z; CRegistry::SetCurrentKeyValue(HKEY__ *,ushort const *,CHString &)
0x140013a63  mov     rbx, [rsp+28h+arg_0]
0x140013a68  mov     rsi, [rsp+28h+arg_8]
0x140013a6d  add     rsp, 20h
0x140013a71  pop     rdi
0x140013a72  retn
```
