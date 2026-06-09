# ATL::CComCreator<ATL::CComAggObject<CAxInstaller>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a4e4`
- end: `0x18000a5fa`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCAxInstaller@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000a4d0`

## callees

- `0x18000177c`
- `0x180005cec`
- `0x18000a4e4`
- `0x18000bf48`
- `0x180015010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CAxInstaller>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  _DWORD *v7; // rbx
  int v8; // edi
  _DWORD *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = operator new(0x2E8u);
    v7[2] = 0;
    *(_QWORD *)v7 = &ATL::CComAggObject<CAxInstaller>::`vftable';
    CAxInstaller::CAxInstaller((CAxInstaller *)(v7 + 6));
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CAxInstaller>::`vftable'{for `IeAxiService2'};
    *((_QWORD *)v7 + 4) = &ATL::CComContainedObject<CAxInstaller>::`vftable'{for `IeAxiServiceCallback'};
    *((_QWORD *)v7 + 5) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v7 + 12));
    if ( v8 < 0 || (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a4e4  mov     [rsp+arg_0], rbx
0x18000a4e9  mov     [rsp+arg_10], r8
0x18000a4ee  mov     [rsp+arg_8], rdx
0x18000a4f3  push    rsi
0x18000a4f4  push    rdi
0x18000a4f5  push    r12
0x18000a4f7  push    r14
0x18000a4f9  push    r15
0x18000a4fb  sub     rsp, 30h
0x18000a4ff  mov     rsi, r8
0x18000a502  mov     r14, rdx
0x18000a505  mov     r12, rcx
0x18000a508  test    r8, r8
0x18000a50b  jnz     short loc_18000A517
0x18000a50d  mov     eax, 80004003h
0x18000a512  jmp     loc_18000A5E8
0x18000a517  mov     qword ptr [r8], 0
0x18000a51e  mov     edi, 8007000Eh
0x18000a523  mov     [rsp+58h+arg_18], edi
0x18000a527  mov     [rsp+58h+var_38], 0
0x18000a530  mov     ecx, 2E8h; Size
0x18000a535  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a53a  mov     rbx, rax
0x18000a53d  mov     [rsp+58h+var_30], rax
0x18000a542  mov     dword ptr [rax+8], 0
0x18000a549  lea     rax, ??_7?$CComAggObject@VCAxInstaller@@@ATL@@6B@; const ATL::CComAggObject<CAxInstaller>::`vftable'
0x18000a550  mov     [rbx], rax
0x18000a553  lea     rcx, [rbx+18h]; this
0x18000a557  call    ??0CAxInstaller@@QEAA@XZ; CAxInstaller::CAxInstaller(void)
0x18000a55c  lea     rax, ??_7?$CComContainedObject@VCAxInstaller@@@ATL@@6BIeAxiService2@@@; const ATL::CComContainedObject<CAxInstaller>::`vftable'{for `IeAxiService2'}
0x18000a563  mov     [rbx+18h], rax
0x18000a567  lea     rax, ??_7?$CComContainedObject@VCAxInstaller@@@ATL@@6BIeAxiServiceCallback@@@; const ATL::CComContainedObject<CAxInstaller>::`vftable'{for `IeAxiServiceCallback'}
0x18000a56e  mov     [rbx+20h], rax
0x18000a572  mov     [rbx+28h], r12
0x18000a576  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a57d  mov     rax, [rcx]
0x18000a580  mov     rax, [rax+8]
0x18000a584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a589  nop
0x18000a58a  mov     [rsp+58h+var_38], rbx
0x18000a58f  jmp     short loc_18000A5A4
0x18000a591  mov     rsi, [rsp+58h+arg_10]
0x18000a596  mov     r14, [rsp+58h+arg_8]
0x18000a59b  mov     edi, [rsp+58h+arg_18]
0x18000a59f  mov     rbx, [rsp+58h+var_38]
0x18000a5a4  test    rbx, rbx
0x18000a5a7  jz      short loc_18000A5E6
0x18000a5a9  lea     rcx, [rbx+30h]; this
0x18000a5ad  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000a5b2  mov     edi, eax
0x18000a5b4  test    eax, eax
0x18000a5b6  js      short loc_18000A5D2
0x18000a5b8  mov     rax, [rbx]
0x18000a5bb  mov     r8, rsi
0x18000a5be  mov     rdx, r14
0x18000a5c1  mov     rcx, rbx
0x18000a5c4  mov     rax, [rax]
0x18000a5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5cc  mov     edi, eax
0x18000a5ce  test    eax, eax
0x18000a5d0  jz      short loc_18000A5E6
0x18000a5d2  mov     rdx, [rbx]
0x18000a5d5  mov     rax, [rdx+18h]
0x18000a5d9  mov     edx, 1
0x18000a5de  mov     rcx, rbx
0x18000a5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5e6  mov     eax, edi
0x18000a5e8  mov     rbx, [rsp+58h+arg_0]
0x18000a5ed  add     rsp, 30h
0x18000a5f1  pop     r15
0x18000a5f3  pop     r14
0x18000a5f5  pop     r12
0x18000a5f7  pop     rdi
0x18000a5f8  pop     rsi
0x18000a5f9  retn
```
