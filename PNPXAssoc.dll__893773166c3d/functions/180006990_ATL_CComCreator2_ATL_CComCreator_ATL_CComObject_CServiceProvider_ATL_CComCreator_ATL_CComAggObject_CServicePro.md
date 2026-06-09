# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CServiceProvider>>,ATL::CComCreator<ATL::CComAggObject<CServiceProvider>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006990`
- end: `0x180006a86`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCServiceProvider@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCServiceProvider@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800019d4`
- `0x180006990`
- `0x180006b90`
- `0x180006f6c`
- `0x1800098c8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CServiceProvider>>,ATL::CComCreator<ATL::CComAggObject<CServiceProvider>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  CServiceProvider *v6; // rax
  CServiceProvider *v7; // rdi
  struct ATL::CAtlModule *v8; // rcx
  int v9; // ecx
  int v10; // eax

  if ( a1 )
  {
    return (unsigned int)ATL::CComCreator<ATL::CComAggObject<CServiceProvider>>::CreateInstance(a1, a2, a3);
  }
  else if ( a3 )
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = (CServiceProvider *)operator new(0xB0u);
    v7 = v6;
    if ( v6 )
    {
      CServiceProvider::CServiceProvider(v6);
      v8 = ATL::_pAtlModule;
      *(_QWORD *)v7 = &ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXDeviceAssociation'};
      *((_QWORD *)v7 + 1) = &ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXAssociation'};
      *((_QWORD *)v7 + 2) = &ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXAssociationAsync'};
      *((_QWORD *)v7 + 3) = &ATL::CComObject<CServiceProvider>::`vftable'{for `IFunctionDiscoveryServiceProvider'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
      v9 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)v7 + 1);
      if ( v9 >= 0 )
        *((_BYTE *)v7 + 80) = 1;
      v10 = 0;
      if ( v9 < 0 )
        v10 = v9;
      v5 = 0;
      if ( v10 < 0 )
        v5 = v10;
      if ( v5 || (v5 = (**(__int64 (__fastcall ***)(CServiceProvider *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0 )
        (*(void (__fastcall **)(CServiceProvider *, __int64))(*(_QWORD *)v7 + 48LL))(v7, 1);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v5;
}

```

## disassembly

```asm
0x180006990  push    rbx
0x180006992  push    rbp
0x180006993  push    rsi
0x180006994  push    rdi
0x180006995  sub     rsp, 28h
0x180006999  mov     rsi, r8
0x18000699c  mov     rbp, rdx
0x18000699f  test    rcx, rcx
0x1800069a2  jnz     loc_180006A74
0x1800069a8  test    r8, r8
0x1800069ab  jnz     short loc_1800069B7
0x1800069ad  mov     ebx, 80004003h
0x1800069b2  jmp     loc_180006A7B
0x1800069b7  mov     ecx, 0B0h; Size
0x1800069bc  mov     qword ptr [r8], 0
0x1800069c3  mov     ebx, 8007000Eh
0x1800069c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800069cd  mov     rdi, rax
0x1800069d0  test    rax, rax
0x1800069d3  jz      loc_180006A7B
0x1800069d9  mov     rcx, rax; this
0x1800069dc  call    ??0CServiceProvider@@QEAA@XZ; CServiceProvider::CServiceProvider(void)
0x1800069e1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800069e8  lea     rax, ??_7?$CComObject@VCServiceProvider@@@ATL@@6BIPNPXDeviceAssociation@@@; const ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXDeviceAssociation'}
0x1800069ef  mov     [rdi], rax
0x1800069f2  lea     rax, ??_7?$CComObject@VCServiceProvider@@@ATL@@6BIPNPXAssociation@@@; const ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXAssociation'}
0x1800069f9  mov     [rdi+8], rax
0x1800069fd  lea     rax, ??_7?$CComObject@VCServiceProvider@@@ATL@@6BIPNPXAssociationAsync@@@; const ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXAssociationAsync'}
0x180006a04  mov     [rdi+10h], rax
0x180006a08  lea     rax, ??_7?$CComObject@VCServiceProvider@@@ATL@@6BIFunctionDiscoveryServiceProvider@@@; const ATL::CComObject<CServiceProvider>::`vftable'{for `IFunctionDiscoveryServiceProvider'}
0x180006a0f  mov     [rdi+18h], rax
0x180006a13  mov     rax, [rcx]
0x180006a16  mov     rax, [rax+8]
0x180006a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a1f  lea     rcx, [rdi+28h]; this
0x180006a23  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006a28  mov     ecx, eax
0x180006a2a  test    eax, eax
0x180006a2c  js      short loc_180006A32
0x180006a2e  mov     byte ptr [rdi+50h], 1
0x180006a32  xor     eax, eax
0x180006a34  test    ecx, ecx
0x180006a36  cmovs   eax, ecx
0x180006a39  xor     ebx, ebx
0x180006a3b  test    eax, eax
0x180006a3d  cmovs   ebx, eax
0x180006a40  test    ebx, ebx
0x180006a42  jnz     short loc_180006A5E
0x180006a44  mov     rax, [rdi]
0x180006a47  mov     r8, rsi
0x180006a4a  mov     rdx, rbp
0x180006a4d  mov     rcx, rdi
0x180006a50  mov     rax, [rax]
0x180006a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a58  mov     ebx, eax
0x180006a5a  test    eax, eax
0x180006a5c  jz      short loc_180006A7B
0x180006a5e  mov     rax, [rdi]
0x180006a61  mov     edx, 1
0x180006a66  mov     rcx, rdi
0x180006a69  mov     rax, [rax+30h]
0x180006a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a72  jmp     short loc_180006A7B
0x180006a74  call    ?CreateInstance@?$CComCreator@V?$CComAggObject@VCServiceProvider@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CServiceProvider>>::CreateInstance(void *,_GUID const &,void * *)
0x180006a79  mov     ebx, eax
0x180006a7b  mov     eax, ebx
0x180006a7d  add     rsp, 28h
0x180006a81  pop     rdi
0x180006a82  pop     rsi
0x180006a83  pop     rbp
0x180006a84  pop     rbx
0x180006a85  retn
```
