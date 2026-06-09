# CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>::_InternalQueryInterface(_GUID const &,void * *)

- ea: `0x180017a40`
- end: `0x180017aa6`
- name: `?_InternalQueryInterface@?$CComClassFactoryT@VCEditionUpgradeManager@@VCComInternalCreatorInitializerT@@$0A@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800090dc`
- `0x180017a40`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>::_InternalQueryInterface(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // ecx

  if ( !a3 )
  {
    v5 = 2147500035LL;
LABEL_7:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    return v6;
  }
  if ( *a2 != *(_QWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data1
    || a2[1] != *(_QWORD *)GUID_00000001_0000_0000_c000_000000000046.Data4 )
  {
    v5 = 2147500034LL;
    *a3 = 0;
    goto LABEL_7;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v6 = 0;
  *a3 = a1;
  return v6;
}

```

## disassembly

```asm
0x180017a40  mov     [rsp+arg_0], rbx
0x180017a45  push    rdi
0x180017a46  sub     rsp, 20h
0x180017a4a  mov     rbx, r8
0x180017a4d  mov     rdi, rcx
0x180017a50  test    r8, r8
0x180017a53  jnz     short loc_180017A5C
0x180017a55  mov     ecx, 80004003h
0x180017a5a  jmp     short loc_180017A94
0x180017a5c  mov     rax, [rdx]
0x180017a5f  cmp     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data1
0x180017a66  jnz     short loc_180017A88
0x180017a68  mov     rax, [rdx+8]
0x180017a6c  cmp     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data4
0x180017a73  jnz     short loc_180017A88
0x180017a75  mov     rax, [rcx]
0x180017a78  mov     rax, [rax+8]
0x180017a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a81  xor     ecx, ecx
0x180017a83  mov     [rbx], rdi
0x180017a86  jmp     short loc_180017A99
0x180017a88  mov     ecx, 80004002h
0x180017a8d  mov     qword ptr [r8], 0
0x180017a94  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180017a99  mov     rbx, [rsp+28h+arg_0]
0x180017a9e  mov     eax, ecx
0x180017aa0  add     rsp, 20h
0x180017aa4  pop     rdi
0x180017aa5  retn
```
