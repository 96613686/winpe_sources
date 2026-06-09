# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPnpxPairingHandler>>,ATL::CComCreator<ATL::CComAggObject<CPnpxPairingHandler>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006890`
- end: `0x18000697b`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPnpxPairingHandler@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCPnpxPairingHandler@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800019d4`
- `0x180006890`
- `0x180006a8c`
- `0x180006f6c`
- `0x18000d500`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPnpxPairingHandler>>,ATL::CComCreator<ATL::CComAggObject<CPnpxPairingHandler>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  CPnpxPairingHandler *v6; // rax
  CPnpxPairingHandler *v7; // rdi
  struct ATL::CAtlModule *v8; // rcx
  int v9; // ecx
  int v10; // eax

  if ( a1 )
  {
    return (unsigned int)ATL::CComCreator<ATL::CComAggObject<CPnpxPairingHandler>>::CreateInstance();
  }
  else if ( a3 )
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = (CPnpxPairingHandler *)operator new(0x80u);
    v7 = v6;
    if ( v6 )
    {
      CPnpxPairingHandler::CPnpxPairingHandler(v6);
      v8 = ATL::_pAtlModule;
      *(_QWORD *)v7 = &ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryServiceProvider'};
      *((_QWORD *)v7 + 1) = &ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IPairingHandler'};
      *((_QWORD *)v7 + 2) = &ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryNotification'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
      v9 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)((char *)v7 + 32));
      if ( v9 >= 0 )
        *((_BYTE *)v7 + 72) = 1;
      v10 = 0;
      if ( v9 < 0 )
        v10 = v9;
      v5 = 0;
      if ( v10 < 0 )
        v5 = v10;
      if ( v5 || (v5 = (**(__int64 (__fastcall ***)(CPnpxPairingHandler *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0 )
        (*(void (__fastcall **)(CPnpxPairingHandler *, __int64))(*(_QWORD *)v7 + 32LL))(v7, 1);
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
0x180006890  push    rbx
0x180006892  push    rbp
0x180006893  push    rsi
0x180006894  push    rdi
0x180006895  sub     rsp, 28h
0x180006899  mov     rsi, r8
0x18000689c  mov     rbp, rdx
0x18000689f  test    rcx, rcx
0x1800068a2  jnz     loc_180006969
0x1800068a8  test    r8, r8
0x1800068ab  jnz     short loc_1800068B7
0x1800068ad  mov     ebx, 80004003h
0x1800068b2  jmp     loc_180006970
0x1800068b7  mov     ecx, 80h; Size
0x1800068bc  mov     qword ptr [r8], 0
0x1800068c3  mov     ebx, 8007000Eh
0x1800068c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800068cd  mov     rdi, rax
0x1800068d0  test    rax, rax
0x1800068d3  jz      loc_180006970
0x1800068d9  mov     rcx, rax; this
0x1800068dc  call    ??0CPnpxPairingHandler@@QEAA@XZ; CPnpxPairingHandler::CPnpxPairingHandler(void)
0x1800068e1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800068e8  lea     rax, ??_7?$CComObject@VCPnpxPairingHandler@@@ATL@@6BIFunctionDiscoveryServiceProvider@@@; const ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryServiceProvider'}
0x1800068ef  mov     [rdi], rax
0x1800068f2  lea     rax, ??_7?$CComObject@VCPnpxPairingHandler@@@ATL@@6BIPairingHandler@@@; const ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IPairingHandler'}
0x1800068f9  mov     [rdi+8], rax
0x1800068fd  lea     rax, ??_7?$CComObject@VCPnpxPairingHandler@@@ATL@@6BIFunctionDiscoveryNotification@@@; const ATL::CComObject<CPnpxPairingHandler>::`vftable'{for `IFunctionDiscoveryNotification'}
0x180006904  mov     [rdi+10h], rax
0x180006908  mov     rax, [rcx]
0x18000690b  mov     rax, [rax+8]
0x18000690f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006914  lea     rcx, [rdi+20h]; this
0x180006918  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000691d  mov     ecx, eax
0x18000691f  test    eax, eax
0x180006921  js      short loc_180006927
0x180006923  mov     byte ptr [rdi+48h], 1
0x180006927  xor     eax, eax
0x180006929  test    ecx, ecx
0x18000692b  cmovs   eax, ecx
0x18000692e  xor     ebx, ebx
0x180006930  test    eax, eax
0x180006932  cmovs   ebx, eax
0x180006935  test    ebx, ebx
0x180006937  jnz     short loc_180006953
0x180006939  mov     rax, [rdi]
0x18000693c  mov     r8, rsi
0x18000693f  mov     rdx, rbp
0x180006942  mov     rcx, rdi
0x180006945  mov     rax, [rax]
0x180006948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000694d  mov     ebx, eax
0x18000694f  test    eax, eax
0x180006951  jz      short loc_180006970
0x180006953  mov     rax, [rdi]
0x180006956  mov     edx, 1
0x18000695b  mov     rcx, rdi
0x18000695e  mov     rax, [rax+20h]
0x180006962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006967  jmp     short loc_180006970
0x180006969  call    ?CreateInstance@?$CComCreator@V?$CComAggObject@VCPnpxPairingHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CPnpxPairingHandler>>::CreateInstance(void *,_GUID const &,void * *)
0x18000696e  mov     ebx, eax
0x180006970  mov     eax, ebx
0x180006972  add     rsp, 28h
0x180006976  pop     rdi
0x180006977  pop     rsi
0x180006978  pop     rbp
0x180006979  pop     rbx
0x18000697a  retn
```
