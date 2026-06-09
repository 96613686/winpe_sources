# CRegistry::DeleteKey(CHString *)

- ea: `0x140012270`
- end: `0x1400122a8`
- name: `?DeleteKey@CRegistry@@QEAAJPEAVCHString@@@Z`
- size: `56`
- prototype: `LSTATUS __fastcall(HKEY *this, struct CHString *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000f91c`

## callees

- `0x1400111d0`
- `0x140012270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1400122a1`

## pseudocode

```c
LSTATUS __fastcall CRegistry::DeleteKey(HKEY *this, struct CHString *a2)
{
  CHString *v2; // rax
  const WCHAR *Buffer; // rax

  v2 = a2;
  if ( !a2 )
    v2 = (CHString *)(this + 3);
  Buffer = CHString::GetBuffer(v2, 0);
  return RegDeleteKeyExW(this[1], Buffer, 0, 0);
}

```

## disassembly

```asm
0x140012270  push    rbx
0x140012272  sub     rsp, 20h
0x140012276  mov     rax, rdx
0x140012279  mov     rbx, rcx
0x14001227c  test    rdx, rdx
0x14001227f  jnz     short loc_140012285
0x140012281  lea     rax, [rcx+18h]
0x140012285  xor     edx, edx; int
0x140012287  mov     rcx, rax; this
0x14001228a  call    ?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x14001228f  mov     rcx, [rbx+8]
0x140012293  xor     r9d, r9d
0x140012296  xor     r8d, r8d
0x140012299  mov     rdx, rax
0x14001229c  add     rsp, 20h
0x1400122a0  pop     rbx
0x1400122a1  jmp     cs:__imp_RegDeleteKeyExW
```
