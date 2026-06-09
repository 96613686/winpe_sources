# ATL::CComCreator<ATL::CComAggObject<CMsMpComFactoryHome>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003514`
- end: `0x180003660`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMsMpComFactoryHome@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003500`

## callees

- `0x18000126c`
- `0x18000233c`
- `0x180003514`
- `0x180003c74`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMsMpComFactoryHome>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  char *v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  int v10; // ecx
  int v11; // eax
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x80u);
    v9 = (struct _RTL_CRITICAL_SECTION *)v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CMsMpComFactoryHome>::`vftable';
      *(_OWORD *)(v8 + 40) = 0;
      *(_OWORD *)(v8 + 56) = 0;
      *((_QWORD *)v8 + 9) = 0;
      v8[80] = 0;
      *((_QWORD *)v8 + 12) = 0;
      v8[120] = 0;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CMsMpComFactoryHome>::`vftable'{for `MP_CComObjectRootEx'};
      *((_QWORD *)v8 + 11) = &ATL::CComContainedObject<CMsMpComFactoryHome>::`vftable'{for `ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v8 + 4) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v10 = ATL::CComCriticalSection::Init(v9 + 1);
    if ( v10 >= 0 )
      LOBYTE(v9[2].DebugInfo) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    if ( v11 >= 0 )
      v11 = CMsMpComFactory::FinalConstruct((CMsMpComFactory *)&v9->LockSemaphore);
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7
      || (v7 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, _QWORD *))v9->DebugInfo->Type)(
                 v9,
                 v4,
                 v3)) != 0 )
    {
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v9->DebugInfo->ProcessLocksList.Blink)(v9, 1);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180003514  mov     [rsp+arg_0], rsi
0x180003519  mov     [rsp+arg_10], r8
0x18000351e  mov     [rsp+arg_8], rdx
0x180003523  push    rdi
0x180003524  push    r12
0x180003526  push    r13
0x180003528  push    r14
0x18000352a  push    r15
0x18000352c  sub     rsp, 30h
0x180003530  mov     r14, r8
0x180003533  mov     r15, rdx
0x180003536  mov     r12, rcx
0x180003539  test    r8, r8
0x18000353c  jnz     short loc_180003548
0x18000353e  mov     eax, 80004003h
0x180003543  jmp     loc_18000364D
0x180003548  mov     qword ptr [r8], 0
0x18000354f  mov     esi, 8007000Eh
0x180003554  mov     [rsp+58h+arg_18], esi
0x180003558  mov     [rsp+58h+var_38], 0
0x180003561  mov     ecx, 80h; Size
0x180003566  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000356b  mov     rdi, rax
0x18000356e  test    rdi, rdi
0x180003571  jz      short loc_1800035CC
0x180003573  mov     dword ptr [rax+8], 0
0x18000357a  lea     rax, ??_7?$CComAggObject@VCMsMpComFactoryHome@@@ATL@@6B@; const ATL::CComAggObject<CMsMpComFactoryHome>::`vftable'
0x180003581  mov     [rdi], rax
0x180003584  xorps   xmm0, xmm0
0x180003587  xor     eax, eax
0x180003589  movups  xmmword ptr [rdi+28h], xmm0
0x18000358d  movups  xmmword ptr [rdi+38h], xmm0
0x180003591  mov     [rdi+48h], rax
0x180003595  mov     [rdi+50h], al
0x180003598  mov     [rdi+60h], rax
0x18000359c  mov     [rdi+78h], al
0x18000359f  lea     rax, ??_7?$CComContainedObject@VCMsMpComFactoryHome@@@ATL@@6BMP_CComObjectRootEx@@@; const ATL::CComContainedObject<CMsMpComFactoryHome>::`vftable'{for `MP_CComObjectRootEx'}
0x1800035a6  mov     [rdi+18h], rax
0x1800035aa  lea     rax, ??_7?$CComContainedObject@VCMsMpComFactoryHome@@@ATL@@6B?$IDispatchImpl@UIMsMpComFactory@@$1?IID_IMsMpComFactory@@3U_GUID@@B$1?LIBID_MpComExportsLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMsMpComFactoryHome>::`vftable'{for `ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'}
0x1800035b1  mov     [rdi+58h], rax
0x1800035b5  mov     [rdi+20h], r12
0x1800035b9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800035c0  mov     rax, [rcx]
0x1800035c3  mov     rax, [rax+8]
0x1800035c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035cc  mov     [rsp+58h+var_38], rdi
0x1800035d1  jmp     short loc_1800035E6
0x1800035d3  mov     r14, [rsp+58h+arg_10]
0x1800035d8  mov     r15, [rsp+58h+arg_8]
0x1800035dd  mov     esi, [rsp+58h+arg_18]
0x1800035e1  mov     rdi, [rsp+58h+var_38]
0x1800035e6  test    rdi, rdi
0x1800035e9  jz      short loc_18000364B
0x1800035eb  lea     rcx, [rdi+28h]; this
0x1800035ef  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800035f4  mov     ecx, eax
0x1800035f6  test    eax, eax
0x1800035f8  js      short loc_1800035FE
0x1800035fa  mov     byte ptr [rdi+50h], 1
0x1800035fe  xor     eax, eax
0x180003600  test    ecx, ecx
0x180003602  cmovs   eax, ecx
0x180003605  test    eax, eax
0x180003607  js      short loc_180003612
0x180003609  lea     rcx, [rdi+18h]; this
0x18000360d  call    ?FinalConstruct@CMsMpComFactory@@QEAAJXZ; CMsMpComFactory::FinalConstruct(void)
0x180003612  xor     esi, esi
0x180003614  test    eax, eax
0x180003616  cmovs   esi, eax
0x180003619  test    esi, esi
0x18000361b  jnz     short loc_180003637
0x18000361d  mov     rax, [rdi]
0x180003620  mov     r8, r14
0x180003623  mov     rdx, r15
0x180003626  mov     rcx, rdi
0x180003629  mov     rax, [rax]
0x18000362c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003631  mov     esi, eax
0x180003633  test    eax, eax
0x180003635  jz      short loc_18000364B
0x180003637  mov     r8, [rdi]
0x18000363a  mov     edx, 1
0x18000363f  mov     rcx, rdi
0x180003642  mov     rax, [r8+18h]
0x180003646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000364b  mov     eax, esi
0x18000364d  mov     rsi, [rsp+58h+arg_0]
0x180003652  add     rsp, 30h
0x180003656  pop     r15
0x180003658  pop     r14
0x18000365a  pop     r13
0x18000365c  pop     r12
0x18000365e  pop     rdi
0x18000365f  retn
```
