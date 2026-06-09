# Common::RegistryKey::GetValue(ushort const *,ulong,ulong *,void *,ulong *)

- ea: `0x18000fc70`
- end: `0x18000fcb6`
- name: `?GetValue@RegistryKey@Common@@QEAAJPEBGKPEAKPEAX1@Z`
- size: `70`
- prototype: `int __fastcall(Common::RegistryKey *this, const unsigned __int16 *, unsigned int, unsigned int *, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c52c`

## callees

- `0x18000fc70`
- `0x18000fcbc`

## pseudocode

```c
int __fastcall Common::RegistryKey::GetValue(
        Common::RegistryKey *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int *a4,
        void *a5,
        unsigned int *a6)
{
  int result; // eax
  unsigned int v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = a3;
  result = Common::RegistryKey::GetValue(this, a2, a5, &v8, a6);
  if ( (int)(result + 0x80000000) < 0 || result == -2147024662 )
    *a4 = v8;
  return result;
}

```

## disassembly

```asm
0x18000fc70  push    rbx
0x18000fc72  sub     rsp, 30h
0x18000fc76  mov     rax, [rsp+38h+arg_28]
0x18000fc7b  mov     rbx, r9
0x18000fc7e  mov     [rsp+38h+arg_10], r8d
0x18000fc83  lea     r9, [rsp+38h+arg_10]; unsigned int *
0x18000fc88  mov     r8, [rsp+38h+arg_20]; void *
0x18000fc8d  mov     [rsp+38h+var_18], rax; unsigned int *
0x18000fc92  call    ?GetValue@RegistryKey@Common@@QEAAJPEBGPEAXPEAK2@Z; Common::RegistryKey::GetValue(ushort const *,void *,ulong *,ulong *)
0x18000fc97  mov     edx, 80000000h
0x18000fc9c  lea     ecx, [rax+rdx]
0x18000fc9f  test    edx, ecx
0x18000fca1  jnz     short loc_18000FCAA
0x18000fca3  cmp     eax, 800700EAh
0x18000fca8  jnz     short loc_18000FCB0
0x18000fcaa  mov     ecx, [rsp+38h+arg_10]
0x18000fcae  mov     [rbx], ecx
0x18000fcb0  add     rsp, 30h
0x18000fcb4  pop     rbx
0x18000fcb5  retn
```
