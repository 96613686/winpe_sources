# CRegistry::GetCurrentBinaryKeyValue(HKEY__ *,ushort const *,uchar *,ulong *)

- ea: `0x1400124d0`
- end: `0x1400124fa`
- name: `?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGPEAEPEAK@Z`
- size: `42`
- prototype: `unsigned int __fastcall(CRegistry *__hidden this, HKEY, const unsigned __int16 *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140012bc0`

## pseudocode

```c
unsigned int __fastcall CRegistry::GetCurrentBinaryKeyValue(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  unsigned int v6[6]; // [rsp+30h] [rbp-18h] BYREF

  v6[0] = 0;
  return CRegistry::GetCurrentRawKeyValue(this, a2, a3, a4, v6, a5);
}

```

## disassembly

```asm
0x1400124d0  sub     rsp, 48h
0x1400124d4  mov     rax, [rsp+48h+arg_20]
0x1400124d9  mov     [rsp+48h+var_20], rax; unsigned int *
0x1400124de  lea     rax, [rsp+48h+var_18]
0x1400124e3  mov     [rsp+48h+var_28], rax; unsigned int *
0x1400124e8  mov     [rsp+48h+var_18], 0
0x1400124f0  call    ?GetCurrentRawKeyValue@CRegistry@@AEAAKPEAUHKEY__@@PEBGPEAXPEAK3@Z; CRegistry::GetCurrentRawKeyValue(HKEY__ *,ushort const *,void *,ulong *,ulong *)
0x1400124f5  add     rsp, 48h
0x1400124f9  retn
```
