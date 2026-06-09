# ATL::CComCreator<ATL::CComObject<CMsMpComFactoryHome>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003668`
- end: `0x180003789`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMsMpComFactoryHome@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003500`

## callees

- `0x18000126c`
- `0x18000233c`
- `0x180003668`
- `0x180003c74`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMsMpComFactoryHome>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  int v9; // eax
  _DWORD *v12; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x68u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_BYTE *)v7 + 56) = 0;
      *((_QWORD *)v7 + 9) = 0;
      *((_BYTE *)v7 + 96) = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CMsMpComFactoryHome>::`vftable'{for `MP_CComObjectRootEx'};
      *((_QWORD *)v7 + 8) = &ATL::CComObject<CMsMpComFactoryHome>::`vftable'{for `ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v12;
  }
  if ( v8 )
  {
    v9 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v8 + 4));
    if ( v9 >= 0 )
    {
      *((_BYTE *)v8 + 56) = 1;
      v9 = CMsMpComFactory::FinalConstruct((CMsMpComFactory *)v8);
    }
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    if ( v6
      || (v6 = (**((__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v8 + 8))((__int64)(v8 + 16), v4, v3)) != 0 )
    {
      (**(void (__fastcall ***)(_DWORD *, __int64))v8)(v8, 1);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180003668  mov     [rsp+arg_10], r8
0x18000366d  mov     [rsp+arg_8], rdx
0x180003672  mov     [rsp+arg_0], rcx
0x180003677  push    rsi
0x180003678  push    rdi
0x180003679  push    r14
0x18000367b  push    r15
0x18000367d  sub     rsp, 28h
0x180003681  mov     r14, r8
0x180003684  mov     r15, rdx
0x180003687  test    r8, r8
0x18000368a  jnz     short loc_180003696
0x18000368c  mov     eax, 80004003h
0x180003691  jmp     loc_18000377E
0x180003696  mov     qword ptr [r8], 0
0x18000369d  mov     esi, 8007000Eh
0x1800036a2  mov     dword ptr [rsp+48h+arg_0], esi
0x1800036a6  mov     [rsp+48h+arg_18], 0
0x1800036af  mov     ecx, 68h ; 'h'; Size
0x1800036b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800036b9  mov     rdi, rax
0x1800036bc  test    rdi, rdi
0x1800036bf  jz      short loc_18000370B
0x1800036c1  mov     dword ptr [rax+8], 0
0x1800036c8  xorps   xmm0, xmm0
0x1800036cb  xor     eax, eax
0x1800036cd  movups  xmmword ptr [rdi+10h], xmm0
0x1800036d1  movups  xmmword ptr [rdi+20h], xmm0
0x1800036d5  mov     [rdi+30h], rax
0x1800036d9  mov     [rdi+38h], al
0x1800036dc  mov     [rdi+48h], rax
0x1800036e0  mov     [rdi+60h], al
0x1800036e3  lea     rax, ??_7?$CComObject@VCMsMpComFactoryHome@@@ATL@@6BMP_CComObjectRootEx@@@; const ATL::CComObject<CMsMpComFactoryHome>::`vftable'{for `MP_CComObjectRootEx'}
0x1800036ea  mov     [rdi], rax
0x1800036ed  lea     rax, ??_7?$CComObject@VCMsMpComFactoryHome@@@ATL@@6B?$IDispatchImpl@UIMsMpComFactory@@$1?IID_IMsMpComFactory@@3U_GUID@@B$1?LIBID_MpComExportsLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsMpComFactoryHome>::`vftable'{for `ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'}
0x1800036f4  mov     [rdi+40h], rax
0x1800036f8  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800036ff  mov     rax, [rcx]
0x180003702  mov     rax, [rax+8]
0x180003706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370b  mov     [rsp+48h+arg_18], rdi
0x180003710  jmp     short loc_180003725
0x180003712  mov     r14, [rsp+48h+arg_10]
0x180003717  mov     r15, [rsp+48h+arg_8]
0x18000371c  mov     esi, dword ptr [rsp+48h+arg_0]
0x180003720  mov     rdi, [rsp+48h+arg_18]
0x180003725  test    rdi, rdi
0x180003728  jz      short loc_18000377C
0x18000372a  lea     rcx, [rdi+10h]; this
0x18000372e  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003733  test    eax, eax
0x180003735  js      short loc_180003743
0x180003737  mov     byte ptr [rdi+38h], 1
0x18000373b  mov     rcx, rdi; this
0x18000373e  call    ?FinalConstruct@CMsMpComFactory@@QEAAJXZ; CMsMpComFactory::FinalConstruct(void)
0x180003743  xor     esi, esi
0x180003745  test    eax, eax
0x180003747  cmovs   esi, eax
0x18000374a  test    esi, esi
0x18000374c  jnz     short loc_180003769
0x18000374e  lea     rcx, [rdi+40h]
0x180003752  mov     rax, [rcx]
0x180003755  mov     r8, r14
0x180003758  mov     rdx, r15
0x18000375b  mov     rax, [rax]
0x18000375e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003763  mov     esi, eax
0x180003765  test    eax, eax
0x180003767  jz      short loc_18000377C
0x180003769  mov     r8, [rdi]
0x18000376c  mov     edx, 1
0x180003771  mov     rcx, rdi
0x180003774  mov     rax, [r8]
0x180003777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000377c  mov     eax, esi
0x18000377e  add     rsp, 28h
0x180003782  pop     r15
0x180003784  pop     r14
0x180003786  pop     rdi
0x180003787  pop     rsi
0x180003788  retn
```
