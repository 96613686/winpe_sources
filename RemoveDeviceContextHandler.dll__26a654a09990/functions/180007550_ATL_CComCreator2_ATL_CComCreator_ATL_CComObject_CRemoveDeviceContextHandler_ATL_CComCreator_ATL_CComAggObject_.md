# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRemoveDeviceContextHandler>>,ATL::CComCreator<ATL::CComAggObject<CRemoveDeviceContextHandler>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180007550`
- end: `0x1800076a9`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCRemoveDeviceContextHandler@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c04`
- `0x180007550`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRemoveDeviceContextHandler>>,ATL::CComCreator<ATL::CComAggObject<CRemoveDeviceContextHandler>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  struct ATL::CAtlModule *v9; // rcx
  int v10; // ecx
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  struct ATL::CAtlModule *v13; // rcx

  if ( !a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      v6 = -2147024882;
      v7 = operator new(0x18u);
      v8 = v7;
      if ( v7 )
      {
        v9 = ATL::_pAtlModule;
        v7[4] = 0;
        *(_QWORD *)v7 = &ATL::CComObject<CRemoveDeviceContextHandler>::`vftable'{for `IExplorerCommand'};
        *((_QWORD *)v7 + 1) = &ATL::CComObject<CRemoveDeviceContextHandler>::`vftable'{for `IInitializeCommand'};
        (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
        v10 = v8[4];
        if ( v10 != 0x7FFFFFFF )
        {
          v8[4] = v10 + 1;
          if ( v10 != 2147483646 )
            v8[4] = v10;
        }
        v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3);
        if ( v6 )
          (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 88LL))(v8, 1);
      }
      return v6;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v6 = -2147024882;
  v11 = operator new(0x28u);
  v12 = v11;
  if ( v11 )
  {
    v13 = ATL::_pAtlModule;
    v11[2] = 0;
    *(_QWORD *)v11 = &ATL::CComAggObject<CRemoveDeviceContextHandler>::`vftable';
    *((_QWORD *)v11 + 2) = &ATL::CComContainedObject<CRemoveDeviceContextHandler>::`vftable'{for `IExplorerCommand'};
    *((_QWORD *)v11 + 3) = &ATL::CComContainedObject<CRemoveDeviceContextHandler>::`vftable'{for `IInitializeCommand'};
    *((_QWORD *)v11 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v13 + 8LL))(v13);
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v12)(v12, a2, a3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v12 + 24LL))(v12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180007550  push    rbx
0x180007552  push    rbp
0x180007553  push    rsi
0x180007554  push    rdi
0x180007555  push    r14
0x180007557  sub     rsp, 20h
0x18000755b  mov     rsi, r8
0x18000755e  mov     r14, rdx
0x180007561  mov     rbp, rcx
0x180007564  test    rcx, rcx
0x180007567  jnz     loc_180007603
0x18000756d  test    r8, r8
0x180007570  jz      loc_180007608
0x180007576  mov     [r8], rcx
0x180007579  mov     ebx, 8007000Eh
0x18000757e  lea     ecx, [rbp+18h]; Size
0x180007581  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007586  mov     rdi, rax
0x180007589  test    rax, rax
0x18000758c  jz      loc_18000769C
0x180007592  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007599  mov     [rax+10h], ebp
0x18000759c  lea     rax, ??_7?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@6BIExplorerCommand@@@; const ATL::CComObject<CRemoveDeviceContextHandler>::`vftable'{for `IExplorerCommand'}
0x1800075a3  mov     [rdi], rax
0x1800075a6  lea     rax, ??_7?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@6BIInitializeCommand@@@; const ATL::CComObject<CRemoveDeviceContextHandler>::`vftable'{for `IInitializeCommand'}
0x1800075ad  mov     [rdi+8], rax
0x1800075b1  mov     rdx, [rcx]
0x1800075b4  mov     rax, [rdx+8]
0x1800075b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075bd  mov     ecx, [rdi+10h]
0x1800075c0  cmp     ecx, 7FFFFFFFh
0x1800075c6  jz      short loc_1800075D9
0x1800075c8  lea     eax, [rcx+1]
0x1800075cb  mov     [rdi+10h], eax
0x1800075ce  cmp     ecx, 7FFFFFFEh
0x1800075d4  jz      short loc_1800075D9
0x1800075d6  mov     [rdi+10h], ecx
0x1800075d9  mov     rax, [rdi]
0x1800075dc  mov     r8, rsi
0x1800075df  mov     rdx, r14
0x1800075e2  mov     rcx, rdi
0x1800075e5  mov     rax, [rax]
0x1800075e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075ed  mov     ebx, eax
0x1800075ef  test    eax, eax
0x1800075f1  jz      loc_18000769C
0x1800075f7  mov     rcx, [rdi]
0x1800075fa  mov     rax, [rcx+58h]
0x1800075fe  jmp     loc_18000768F
0x180007603  test    rsi, rsi
0x180007606  jnz     short loc_180007612
0x180007608  mov     ebx, 80004003h
0x18000760d  jmp     loc_18000769C
0x180007612  mov     ecx, 28h ; '('; Size
0x180007617  mov     qword ptr [r8], 0
0x18000761e  mov     ebx, 8007000Eh
0x180007623  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007628  mov     rdi, rax
0x18000762b  test    rax, rax
0x18000762e  jz      short loc_18000769C
0x180007630  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007637  mov     dword ptr [rax+8], 0
0x18000763e  lea     rax, ??_7?$CComAggObject@VCRemoveDeviceContextHandler@@@ATL@@6B@; const ATL::CComAggObject<CRemoveDeviceContextHandler>::`vftable'
0x180007645  mov     [rdi], rax
0x180007648  lea     rax, ??_7?$CComContainedObject@VCRemoveDeviceContextHandler@@@ATL@@6BIExplorerCommand@@@; const ATL::CComContainedObject<CRemoveDeviceContextHandler>::`vftable'{for `IExplorerCommand'}
0x18000764f  mov     [rdi+10h], rax
0x180007653  lea     rax, ??_7?$CComContainedObject@VCRemoveDeviceContextHandler@@@ATL@@6BIInitializeCommand@@@; const ATL::CComContainedObject<CRemoveDeviceContextHandler>::`vftable'{for `IInitializeCommand'}
0x18000765a  mov     [rdi+18h], rax
0x18000765e  mov     [rdi+20h], rbp
0x180007662  mov     rdx, [rcx]
0x180007665  mov     rax, [rdx+8]
0x180007669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000766e  mov     rax, [rdi]
0x180007671  mov     r8, rsi
0x180007674  mov     rdx, r14
0x180007677  mov     rcx, rdi
0x18000767a  mov     rax, [rax]
0x18000767d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007682  mov     ebx, eax
0x180007684  test    eax, eax
0x180007686  jz      short loc_18000769C
0x180007688  mov     rax, [rdi]
0x18000768b  mov     rax, [rax+18h]
0x18000768f  mov     edx, 1
0x180007694  mov     rcx, rdi
0x180007697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000769c  mov     eax, ebx
0x18000769e  add     rsp, 20h
0x1800076a2  pop     r14
0x1800076a4  pop     rdi
0x1800076a5  pop     rsi
0x1800076a6  pop     rbp
0x1800076a7  pop     rbx
0x1800076a8  retn
```
