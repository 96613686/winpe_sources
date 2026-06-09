# CRuntimeBroker::QueryInterface(_GUID const &,void * *)

- ea: `0x140003530`
- end: `0x1400035b5`
- name: `?QueryInterface@CRuntimeBroker@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `133`
- prototype: `__int64 __fastcall(CRuntimeBroker *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003530`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::QueryInterface(CRuntimeBroker *this, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax
  __int64 v6; // rax
  __int64 v7; // rcx

  *a3 = 0;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4;
  if ( v4 )
  {
    v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1 )
      v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4;
    if ( v6 )
    {
      v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_6040ec14_6557_41f9_a3f7_b1cab7b42120.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_6040ec14_6557_41f9_a3f7_b1cab7b42120.Data1 )
        v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_6040ec14_6557_41f9_a3f7_b1cab7b42120.Data4;
      if ( v7 )
        return 2147500034LL;
    }
  }
  *a3 = this;
  (*(void (__fastcall **)(CRuntimeBroker *))(*(_QWORD *)this + 8LL))(this);
  return 0;
}

```

## disassembly

```asm
0x140003530  sub     rsp, 28h
0x140003534  mov     qword ptr [r8], 0
0x14000353b  mov     r9, rcx
0x14000353e  mov     rax, [rdx]
0x140003541  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x140003548  jnz     short loc_140003555
0x14000354a  mov     rax, [rdx+8]
0x14000354e  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140003555  test    rax, rax
0x140003558  jnz     short loc_140003573
0x14000355a  mov     [r8], r9
0x14000355d  mov     rcx, r9
0x140003560  mov     rax, [r9]
0x140003563  mov     rax, [rax+8]
0x140003567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000356c  xor     eax, eax
0x14000356e  add     rsp, 28h
0x140003572  retn
0x140003573  mov     rax, [rdx]
0x140003576  sub     rax, qword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x14000357d  jnz     short loc_14000358A
0x14000357f  mov     rax, [rdx+8]
0x140003583  sub     rax, qword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x14000358a  test    rax, rax
0x14000358d  jz      short loc_14000355A
0x14000358f  mov     rcx, [rdx]
0x140003592  sub     rcx, qword ptr cs:_GUID_6040ec14_6557_41f9_a3f7_b1cab7b42120.Data1
0x140003599  jnz     short loc_1400035A6
0x14000359b  mov     rcx, [rdx+8]
0x14000359f  sub     rcx, qword ptr cs:_GUID_6040ec14_6557_41f9_a3f7_b1cab7b42120.Data4
0x1400035a6  test    rcx, rcx
0x1400035a9  jz      short loc_14000355A
0x1400035ab  mov     eax, 80004002h
0x1400035b0  add     rsp, 28h
0x1400035b4  retn
```
