# CRegistry::GetCurrentBinaryKeyValue(ushort const *,uchar *,ulong *)

- ea: `0x140012620`
- end: `0x14001264f`
- name: `?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z`
- size: `47`
- prototype: `unsigned int __fastcall(HKEY *this, const unsigned __int16 *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140012bc0`

## pseudocode

```c
unsigned int __fastcall CRegistry::GetCurrentBinaryKeyValue(
        HKEY *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned int v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  return CRegistry::GetCurrentRawKeyValue((CRegistry *)this, this[1], a2, a3, &v5, a4);
}

```

## disassembly

```asm
0x140012620  sub     rsp, 38h
0x140012624  mov     [rsp+38h+var_10], r9; unsigned int *
0x140012629  lea     rax, [rsp+38h+arg_0]
0x14001262e  mov     r9, r8; void *
0x140012631  mov     [rsp+38h+arg_0], 0
0x140012639  mov     r8, rdx; unsigned __int16 *
0x14001263c  mov     [rsp+38h+var_18], rax; unsigned int *
0x140012641  mov     rdx, [rcx+8]; HKEY
0x140012645  call    ?GetCurrentRawKeyValue@CRegistry@@AEAAKPEAUHKEY__@@PEBGPEAXPEAK3@Z; CRegistry::GetCurrentRawKeyValue(HKEY__ *,ushort const *,void *,ulong *,ulong *)
0x14001264a  add     rsp, 38h
0x14001264e  retn
```
