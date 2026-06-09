# ATL::CRegistryVirtualMachine::QueryInterface(_GUID const &,void * *)

- ea: `0x1800119c0`
- end: `0x180011a10`
- name: `?QueryInterface@CRegistryVirtualMachine@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `80`
- prototype: `__int64 __fastcall(ATL::CRegistryVirtualMachine *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800119c0`

## pseudocode

```c
__int64 __fastcall ATL::CRegistryVirtualMachine::QueryInterface(
        ATL::CRegistryVirtualMachine *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_OWORD *)a2 != *(_OWORD *)&GUID_00000000_0000_0000_c000_000000000046
    && (*(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_e21f8a85_b05d_4243_8183_c7cb405588f7.Data1
     || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_e21f8a85_b05d_4243_8183_c7cb405588f7.Data4) )
  {
    return 2147500034LL;
  }
  *a3 = this;
  return 0;
}

```

## disassembly

```asm
0x1800119c0  test    r8, r8
0x1800119c3  jnz     short loc_1800119CB
0x1800119c5  mov     eax, 80004003h
0x1800119ca  retn
0x1800119cb  mov     qword ptr [r8], 0
0x1800119d2  mov     rax, [rdx]
0x1800119d5  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x1800119dc  jnz     short loc_1800119EB
0x1800119de  mov     rax, [rdx+8]
0x1800119e2  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800119e9  jz      short loc_180011A04
0x1800119eb  mov     rax, [rdx]
0x1800119ee  cmp     rax, qword ptr cs:_GUID_e21f8a85_b05d_4243_8183_c7cb405588f7.Data1
0x1800119f5  jnz     short loc_180011A0A
0x1800119f7  mov     rax, [rdx+8]
0x1800119fb  cmp     rax, qword ptr cs:_GUID_e21f8a85_b05d_4243_8183_c7cb405588f7.Data4
0x180011a02  jnz     short loc_180011A0A
0x180011a04  mov     [r8], rcx
0x180011a07  xor     eax, eax
0x180011a09  retn
0x180011a0a  mov     eax, 80004002h
0x180011a0f  retn
```
