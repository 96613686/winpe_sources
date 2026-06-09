# ATL::CComAggObject<CRASrv>::Release(void)

- ea: `0x140009d40`
- end: `0x140009d9d`
- name: `?Release@?$CComAggObject@VCRASrv@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140003058`
- `0x140009d40`
- `0x14000a230`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CRASrv>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x140009d40  mov     [rsp+arg_8], rbx
0x140009d45  push    rdi
0x140009d46  sub     rsp, 20h
0x140009d4a  mov     rbx, rcx
0x140009d4d  add     rcx, 8; volatile int *
0x140009d51  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x140009d56  mov     edi, eax
0x140009d58  test    eax, eax
0x140009d5a  jnz     short loc_140009D90
0x140009d5c  lea     rcx, [rsp+28h+arg_0]; this
0x140009d61  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x140009d66  test    rbx, rbx
0x140009d69  jz      short loc_140009D7D
0x140009d6b  mov     rdx, [rbx]
0x140009d6e  mov     rcx, rbx
0x140009d71  mov     rax, [rdx+18h]
0x140009d75  lea     edx, [rdi+1]
0x140009d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d7d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140009d84  mov     rax, [rcx]
0x140009d87  mov     rax, [rax+10h]
0x140009d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d90  mov     rbx, [rsp+28h+arg_8]
0x140009d95  mov     eax, edi
0x140009d97  add     rsp, 20h
0x140009d9b  pop     rdi
0x140009d9c  retn
```
