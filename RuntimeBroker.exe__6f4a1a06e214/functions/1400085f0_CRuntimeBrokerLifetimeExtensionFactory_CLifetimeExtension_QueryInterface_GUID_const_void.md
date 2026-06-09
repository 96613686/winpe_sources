# CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::QueryInterface(_GUID const &,void * *)

- ea: `0x1400085f0`
- end: `0x14000865f`
- name: `?QueryInterface@CLifetimeExtension@CRuntimeBrokerLifetimeExtensionFactory@@EEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `111`
- prototype: `__int64 __fastcall(CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400085f0`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::QueryInterface(
        CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned int v6; // edx
  __int64 v7; // rax

  *a3 = 0;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4;
  if ( !v4 )
    goto LABEL_10;
  v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_ecc8691b_c1db_4dc0_855e_65f6c551af49.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_ecc8691b_c1db_4dc0_855e_65f6c551af49.Data1 )
    v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_ecc8691b_c1db_4dc0_855e_65f6c551af49.Data4;
  if ( !v5 )
    goto LABEL_10;
  v6 = -2147467262;
  v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data1 )
    v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4;
  if ( !v7 )
  {
LABEL_10:
    *a3 = this;
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1400085f0  mov     qword ptr [r8], 0
0x1400085f7  mov     r9, rdx
0x1400085fa  mov     rax, [rdx]
0x1400085fd  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x140008604  jnz     short loc_140008611
0x140008606  mov     rax, [rdx+8]
0x14000860a  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140008611  test    rax, rax
0x140008614  jz      short loc_140008653
0x140008616  mov     rax, [rdx]
0x140008619  sub     rax, qword ptr cs:_GUID_ecc8691b_c1db_4dc0_855e_65f6c551af49.Data1
0x140008620  jnz     short loc_14000862D
0x140008622  mov     rax, [rdx+8]
0x140008626  sub     rax, qword ptr cs:_GUID_ecc8691b_c1db_4dc0_855e_65f6c551af49.Data4
0x14000862d  test    rax, rax
0x140008630  jz      short loc_140008653
0x140008632  mov     rax, [r9]
0x140008635  mov     edx, 80004002h
0x14000863a  sub     rax, qword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data1
0x140008641  jnz     short loc_14000864E
0x140008643  mov     rax, [r9+8]
0x140008647  sub     rax, qword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x14000864e  test    rax, rax
0x140008651  jnz     short loc_14000865C
0x140008653  mov     [r8], rcx
0x140008656  lock inc dword ptr [rcx+8]
0x14000865a  xor     edx, edx
0x14000865c  mov     eax, edx
0x14000865e  retn
```
