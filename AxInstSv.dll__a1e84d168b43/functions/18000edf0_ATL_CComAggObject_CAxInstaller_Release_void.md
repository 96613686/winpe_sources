# ATL::CComAggObject<CAxInstaller>::Release(void)

- ea: `0x18000edf0`
- end: `0x18000ee4d`
- name: `?Release@?$CComAggObject@VCAxInstaller@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008030`
- `0x18000edf0`
- `0x18000f460`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CAxInstaller>::Release(volatile int *a1)
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
0x18000edf0  mov     [rsp+arg_8], rbx
0x18000edf5  push    rdi
0x18000edf6  sub     rsp, 20h
0x18000edfa  mov     rbx, rcx
0x18000edfd  add     rcx, 8; volatile int *
0x18000ee01  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000ee06  mov     edi, eax
0x18000ee08  test    eax, eax
0x18000ee0a  jnz     short loc_18000EE40
0x18000ee0c  lea     rcx, [rsp+28h+arg_0]; this
0x18000ee11  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x18000ee16  test    rbx, rbx
0x18000ee19  jz      short loc_18000EE2D
0x18000ee1b  mov     rdx, [rbx]
0x18000ee1e  mov     rcx, rbx
0x18000ee21  mov     rax, [rdx+18h]
0x18000ee25  lea     edx, [rdi+1]
0x18000ee28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee2d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ee34  mov     rax, [rcx]
0x18000ee37  mov     rax, [rax+10h]
0x18000ee3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee40  mov     rbx, [rsp+28h+arg_8]
0x18000ee45  mov     eax, edi
0x18000ee47  add     rsp, 20h
0x18000ee4b  pop     rdi
0x18000ee4c  retn
```
