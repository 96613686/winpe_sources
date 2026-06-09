# ATL::CComCreator<ATL::CComObject<CRASrv>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140005818`
- end: `0x14000593d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCRASrv@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `293`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005440`

## callees

- `0x1400012d4`
- `0x140005818`
- `0x140007304`
- `0x14000a230`
- `0x14000a258`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CRASrv>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  char *v7; // rax
  volatile int *v8; // rdi
  int v9; // eax
  int v10; // edx
  volatile int *v13; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (char *)operator new(0x48u);
    v8 = (volatile int *)v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 4) = 0;
      *(_OWORD *)(v7 + 24) = 0;
      *(_OWORD *)(v7 + 40) = 0;
      *((_QWORD *)v7 + 7) = 0;
      v7[64] = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CRASrv>::`vftable'{for `ATL::IDispatchImpl<IRASrv,&_GUID const IID_IRASrv,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v7 + 1) = &ATL::CComObject<CRASrv>::`vftable'{for `ISupportErrorInfo'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread(v8 + 4);
    v9 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v8 + 6));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    ATL::SafeDecrementReferenceMultiThread(v8 + 4);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile int *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v8 + 72LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x140005818  mov     [rsp+arg_10], r8
0x14000581d  mov     [rsp+arg_8], rdx
0x140005822  mov     [rsp+arg_0], rcx
0x140005827  push    rbx
0x140005828  push    rsi
0x140005829  push    rdi
0x14000582a  push    r14
0x14000582c  push    r15
0x14000582e  sub     rsp, 20h
0x140005832  mov     r14, r8
0x140005835  mov     r15, rdx
0x140005838  test    r8, r8
0x14000583b  jnz     short loc_140005847
0x14000583d  mov     eax, 80004003h
0x140005842  jmp     loc_140005931
0x140005847  mov     qword ptr [r8], 0
0x14000584e  mov     esi, 8007000Eh
0x140005853  mov     dword ptr [rsp+48h+arg_0], esi
0x140005857  mov     [rsp+48h+arg_18], 0
0x140005860  mov     ecx, 48h ; 'H'; Size
0x140005865  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000586a  mov     rdi, rax
0x14000586d  test    rdi, rdi
0x140005870  jz      short loc_1400058B5
0x140005872  mov     dword ptr [rax+10h], 0
0x140005879  xorps   xmm0, xmm0
0x14000587c  xor     eax, eax
0x14000587e  movups  xmmword ptr [rdi+18h], xmm0
0x140005882  movups  xmmword ptr [rdi+28h], xmm0
0x140005886  mov     [rdi+38h], rax
0x14000588a  mov     [rdi+40h], al
0x14000588d  lea     rax, ??_7?$CComObject@VCRASrv@@@ATL@@6B?$IDispatchImpl@UIRASrv@@$1?IID_IRASrv@@3U_GUID@@B$1?LIBID_RAServerLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CRASrv>::`vftable'{for `ATL::IDispatchImpl<IRASrv,&_GUID const IID_IRASrv,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'}
0x140005894  mov     [rdi], rax
0x140005897  lea     rax, ??_7?$CComObject@VCRASrv@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CRASrv>::`vftable'{for `ISupportErrorInfo'}
0x14000589e  mov     [rdi+8], rax
0x1400058a2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400058a9  mov     rax, [rcx]
0x1400058ac  mov     rax, [rax+8]
0x1400058b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058b5  mov     [rsp+48h+arg_18], rdi
0x1400058ba  jmp     short loc_1400058CF
0x1400058bc  mov     r14, [rsp+48h+arg_10]
0x1400058c1  mov     r15, [rsp+48h+arg_8]
0x1400058c6  mov     esi, dword ptr [rsp+48h+arg_0]
0x1400058ca  mov     rdi, [rsp+48h+arg_18]
0x1400058cf  test    rdi, rdi
0x1400058d2  jz      short loc_14000592F
0x1400058d4  lea     rcx, [rdi+10h]; volatile int *
0x1400058d8  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1400058dd  lea     rcx, [rdi+18h]; this
0x1400058e1  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1400058e6  xor     edx, edx
0x1400058e8  test    eax, eax
0x1400058ea  cmovs   edx, eax
0x1400058ed  xor     esi, esi
0x1400058ef  test    edx, edx
0x1400058f1  cmovs   esi, edx
0x1400058f4  lea     rcx, [rdi+10h]; volatile int *
0x1400058f8  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1400058fd  test    esi, esi
0x1400058ff  jnz     short loc_14000591B
0x140005901  mov     rax, [rdi]
0x140005904  mov     r8, r14
0x140005907  mov     rdx, r15
0x14000590a  mov     rcx, rdi
0x14000590d  mov     rax, [rax]
0x140005910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005915  mov     esi, eax
0x140005917  test    eax, eax
0x140005919  jz      short loc_14000592F
0x14000591b  mov     rdx, [rdi]
0x14000591e  mov     rax, [rdx+48h]
0x140005922  mov     edx, 1
0x140005927  mov     rcx, rdi
0x14000592a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000592f  mov     eax, esi
0x140005931  add     rsp, 20h
0x140005935  pop     r15
0x140005937  pop     r14
0x140005939  pop     rdi
0x14000593a  pop     rsi
0x14000593b  pop     rbx
0x14000593c  retn
```
