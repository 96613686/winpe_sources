# ATL::CComCreator<ATL::CComObject<CAxInstaller>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a600`
- end: `0x18000a70c`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCAxInstaller@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000a4d0`

## callees

- `0x18000177c`
- `0x180005cec`
- `0x18000a600`
- `0x18000bf48`
- `0x18000f460`
- `0x18000f488`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CAxInstaller>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  volatile int *v6; // rdi
  int v7; // eax
  unsigned int v8; // esi
  volatile int *v11; // [rsp+78h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v6 = (volatile int *)operator new(0x2D0u);
    CAxInstaller::CAxInstaller((CAxInstaller *)v6);
    *(_QWORD *)v6 = &ATL::CComObject<CAxInstaller>::`vftable'{for `IeAxiService2'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CAxInstaller>::`vftable'{for `IeAxiServiceCallback'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v11 = v6;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v6 = v11;
  }
  if ( v6 )
  {
    ATL::SafeIncrementReferenceMultiThread(v6 + 4);
    v7 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v6 + 6));
    v8 = 0;
    if ( v7 < 0 )
      v8 = v7;
    ATL::SafeDecrementReferenceMultiThread(v6 + 4);
    if ( v8 || (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)((void *)v6, v4, v3)) != 0 )
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 1);
  }
  return v8;
}

```

## disassembly

```asm
0x18000a600  mov     [rsp+arg_10], r8
0x18000a605  mov     [rsp+arg_8], rdx
0x18000a60a  mov     [rsp+arg_0], rcx
0x18000a60f  push    rbx
0x18000a610  push    rsi
0x18000a611  push    rdi
0x18000a612  push    r14
0x18000a614  push    r15
0x18000a616  sub     rsp, 30h
0x18000a61a  mov     r14, r8
0x18000a61d  mov     r15, rdx
0x18000a620  test    r8, r8
0x18000a623  jnz     short loc_18000A62F
0x18000a625  mov     eax, 80004003h
0x18000a62a  jmp     loc_18000A700
0x18000a62f  mov     qword ptr [r8], 0
0x18000a636  mov     esi, 8007000Eh
0x18000a63b  mov     dword ptr [rsp+58h+arg_0], esi
0x18000a63f  mov     [rsp+58h+arg_18], 0
0x18000a648  mov     ecx, 2D0h; Size
0x18000a64d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a652  mov     rdi, rax
0x18000a655  mov     [rsp+58h+var_38], rax
0x18000a65a  mov     rcx, rax; this
0x18000a65d  call    ??0CAxInstaller@@QEAA@XZ; CAxInstaller::CAxInstaller(void)
0x18000a662  lea     rax, ??_7?$CComObject@VCAxInstaller@@@ATL@@6BIeAxiService2@@@; const ATL::CComObject<CAxInstaller>::`vftable'{for `IeAxiService2'}
0x18000a669  mov     [rdi], rax
0x18000a66c  lea     rax, ??_7?$CComObject@VCAxInstaller@@@ATL@@6BIeAxiServiceCallback@@@; const ATL::CComObject<CAxInstaller>::`vftable'{for `IeAxiServiceCallback'}
0x18000a673  mov     [rdi+8], rax
0x18000a677  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a67e  mov     rax, [rcx]
0x18000a681  mov     rax, [rax+8]
0x18000a685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a68a  nop
0x18000a68b  mov     [rsp+58h+arg_18], rdi
0x18000a690  jmp     short loc_18000A6A5
0x18000a692  mov     r14, [rsp+58h+arg_10]
0x18000a697  mov     r15, [rsp+58h+arg_8]
0x18000a69c  mov     esi, dword ptr [rsp+58h+arg_0]
0x18000a6a0  mov     rdi, [rsp+58h+arg_18]
0x18000a6a5  test    rdi, rdi
0x18000a6a8  jz      short loc_18000A6FE
0x18000a6aa  lea     rcx, [rdi+10h]; volatile int *
0x18000a6ae  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000a6b3  lea     rcx, [rdi+18h]; this
0x18000a6b7  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000a6bc  xor     esi, esi
0x18000a6be  test    eax, eax
0x18000a6c0  cmovs   esi, eax
0x18000a6c3  lea     rcx, [rdi+10h]; volatile int *
0x18000a6c7  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000a6cc  test    esi, esi
0x18000a6ce  jnz     short loc_18000A6EA
0x18000a6d0  mov     rax, [rdi]
0x18000a6d3  mov     r8, r14
0x18000a6d6  mov     rdx, r15
0x18000a6d9  mov     rcx, rdi
0x18000a6dc  mov     rax, [rax]
0x18000a6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6e4  mov     esi, eax
0x18000a6e6  test    eax, eax
0x18000a6e8  jz      short loc_18000A6FE
0x18000a6ea  mov     rax, [rdi]
0x18000a6ed  mov     edx, 1
0x18000a6f2  mov     rcx, rdi
0x18000a6f5  mov     rax, [rax+30h]
0x18000a6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6fe  mov     eax, esi
0x18000a700  add     rsp, 30h
0x18000a704  pop     r15
0x18000a706  pop     r14
0x18000a708  pop     rdi
0x18000a709  pop     rsi
0x18000a70a  pop     rbx
0x18000a70b  retn
```
