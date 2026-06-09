# CRuntimeBroker::CFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x140005cb0`
- end: `0x140005d19`
- name: `?QueryInterface@CFactory@CRuntimeBroker@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `105`
- prototype: `__int64 __fastcall(CRuntimeBroker::CFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005cb0`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::CFactory::QueryInterface(
        CRuntimeBroker::CFactory *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v4; // rax
  __int64 v6; // rcx

  *a3 = 0;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4;
  if ( v4 )
  {
    v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data1 )
      v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000001_0000_0000_c000_000000000046.Data4;
    if ( v6 )
      return 2147500034LL;
  }
  *a3 = this;
  (*(void (__fastcall **)(CRuntimeBroker::CFactory *))(*(_QWORD *)this + 8LL))(this);
  return 0;
}

```

## disassembly

```asm
0x140005cb0  sub     rsp, 28h
0x140005cb4  mov     qword ptr [r8], 0
0x140005cbb  mov     r9, rcx
0x140005cbe  mov     rax, [rdx]
0x140005cc1  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x140005cc8  jnz     short loc_140005CD5
0x140005cca  mov     rax, [rdx+8]
0x140005cce  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140005cd5  test    rax, rax
0x140005cd8  jnz     short loc_140005CF3
0x140005cda  mov     [r8], r9
0x140005cdd  mov     rcx, r9
0x140005ce0  mov     rax, [r9]
0x140005ce3  mov     rax, [rax+8]
0x140005ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cec  xor     eax, eax
0x140005cee  add     rsp, 28h
0x140005cf2  retn
0x140005cf3  mov     rcx, [rdx]
0x140005cf6  sub     rcx, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data1
0x140005cfd  jnz     short loc_140005D0A
0x140005cff  mov     rcx, [rdx+8]
0x140005d03  sub     rcx, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data4
0x140005d0a  test    rcx, rcx
0x140005d0d  jz      short loc_140005CDA
0x140005d0f  mov     eax, 80004002h
0x140005d14  add     rsp, 28h
0x140005d18  retn
```
