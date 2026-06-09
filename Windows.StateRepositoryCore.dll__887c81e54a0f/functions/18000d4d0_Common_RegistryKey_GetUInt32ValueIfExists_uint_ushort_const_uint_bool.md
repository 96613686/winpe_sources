# Common::RegistryKey::GetUInt32ValueIfExists<uint>(ushort const *,uint *,bool *)

- ea: `0x18000d4d0`
- end: `0x18000d4fc`
- name: `??$GetUInt32ValueIfExists@I@RegistryKey@Common@@QEAAJPEBGPEAIPEA_N@Z`
- size: `44`
- prototype: `int __fastcall(Common::RegistryKey *, const unsigned __int16 *, unsigned int *, bool *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d560`
- `0x18000d790`

## callees

- `0x18000fbe8`

## pseudocode

```c
int __fastcall Common::RegistryKey::GetUInt32ValueIfExists<unsigned int>(
        Common::RegistryKey *a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        bool *a4)
{
  int result; // eax

  result = Common::RegistryKey::GetUInt32Value(a1, a2, a3);
  *a4 = result >= 0;
  if ( (unsigned int)(result + 2147024894) <= 1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000d4d0  push    rbx
0x18000d4d2  sub     rsp, 20h
0x18000d4d6  mov     rbx, r9
0x18000d4d9  call    ?GetUInt32Value@RegistryKey@Common@@QEAAJPEBGPEAI@Z; Common::RegistryKey::GetUInt32Value(ushort const *,uint *)
0x18000d4de  mov     ecx, eax
0x18000d4e0  xor     edx, edx
0x18000d4e2  shr     ecx, 1Fh
0x18000d4e5  xor     cl, 1
0x18000d4e8  mov     [rbx], cl
0x18000d4ea  lea     ecx, [rax+7FF8FFFEh]
0x18000d4f0  cmp     ecx, 1
0x18000d4f3  cmovbe  eax, edx
0x18000d4f6  add     rsp, 20h
0x18000d4fa  pop     rbx
0x18000d4fb  retn
```
