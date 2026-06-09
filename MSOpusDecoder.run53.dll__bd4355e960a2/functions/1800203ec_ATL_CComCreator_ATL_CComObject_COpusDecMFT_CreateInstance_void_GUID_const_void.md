# ATL::CComCreator<ATL::CComObject<COpusDecMFT>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800203ec`
- end: `0x1800204f6`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCOpusDecMFT@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800202a0`

## callees

- `0x1800013f4`
- `0x18001b048`
- `0x1800203ec`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<COpusDecMFT>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  COpusDecMFT *v7; // rax
  COpusDecMFT *v8; // rbx
  int v9; // eax
  COpusDecMFT *v12; // [rsp+78h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (COpusDecMFT *)operator new(0x140u);
    v8 = v7;
    if ( v7 )
    {
      COpusDecMFT::COpusDecMFT(v7);
      *(_QWORD *)v8 = &ATL::CComObject<COpusDecMFT>::`vftable'{for `CMFTSimpleBase'};
      *((_QWORD *)v8 + 19) = &ATL::CComObject<COpusDecMFT>::`vftable'{for `IMFTelemetryComponent'};
      (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
    v9 = (*(__int64 (__fastcall **)(COpusDecMFT *))(*(_QWORD *)v8 + 376LL))(v8);
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(COpusDecMFT *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(COpusDecMFT *, __int64))(*(_QWORD *)v8 + 368LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800203ec  mov     [rsp+arg_10], r8
0x1800203f1  mov     [rsp+arg_8], rdx
0x1800203f6  mov     [rsp+arg_0], rcx
0x1800203fb  push    rbx
0x1800203fc  push    rsi
0x1800203fd  push    rdi
0x1800203fe  push    r14
0x180020400  sub     rsp, 38h
0x180020404  mov     rsi, r8
0x180020407  mov     r14, rdx
0x18002040a  test    r8, r8
0x18002040d  jnz     short loc_180020419
0x18002040f  mov     eax, 80004003h
0x180020414  jmp     loc_1800204EC
0x180020419  mov     qword ptr [r8], 0
0x180020420  mov     edi, 8007000Eh
0x180020425  mov     dword ptr [rsp+58h+arg_0], edi
0x180020429  mov     [rsp+58h+arg_18], 0
0x180020432  mov     ecx, 140h; Size
0x180020437  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002043c  mov     rbx, rax
0x18002043f  mov     [rsp+58h+var_38], rax
0x180020444  test    rbx, rbx
0x180020447  jz      short loc_18002047D
0x180020449  mov     rcx, rax; this
0x18002044c  call    ??0COpusDecMFT@@QEAA@XZ; COpusDecMFT::COpusDecMFT(void)
0x180020451  lea     rax, ??_7?$CComObject@VCOpusDecMFT@@@ATL@@6BCMFTSimpleBase@@@; const ATL::CComObject<COpusDecMFT>::`vftable'{for `CMFTSimpleBase'}
0x180020458  mov     [rbx], rax
0x18002045b  lea     rax, ??_7?$CComObject@VCOpusDecMFT@@@ATL@@6BIMFTelemetryComponent@@@; const ATL::CComObject<COpusDecMFT>::`vftable'{for `IMFTelemetryComponent'}
0x180020462  mov     [rbx+98h], rax
0x180020469  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020470  mov     rax, [rcx]
0x180020473  mov     rax, [rax+8]
0x180020477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002047c  nop
0x18002047d  mov     [rsp+58h+arg_18], rbx
0x180020482  jmp     short loc_180020497
0x180020484  mov     rsi, [rsp+58h+arg_10]
0x180020489  mov     r14, [rsp+58h+arg_8]
0x18002048e  mov     edi, dword ptr [rsp+58h+arg_0]
0x180020492  mov     rbx, [rsp+58h+arg_18]
0x180020497  test    rbx, rbx
0x18002049a  jz      short loc_1800204EA
0x18002049c  mov     rax, [rbx]
0x18002049f  mov     rcx, rbx
0x1800204a2  mov     rax, [rax+178h]
0x1800204a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204ae  xor     edi, edi
0x1800204b0  test    eax, eax
0x1800204b2  cmovs   edi, eax
0x1800204b5  test    edi, edi
0x1800204b7  jnz     short loc_1800204D3
0x1800204b9  mov     rax, [rbx]
0x1800204bc  mov     r8, rsi
0x1800204bf  mov     rdx, r14
0x1800204c2  mov     rcx, rbx
0x1800204c5  mov     rax, [rax]
0x1800204c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204cd  mov     edi, eax
0x1800204cf  test    eax, eax
0x1800204d1  jz      short loc_1800204EA
0x1800204d3  mov     rdx, [rbx]
0x1800204d6  mov     rax, [rdx+170h]
0x1800204dd  mov     edx, 1
0x1800204e2  mov     rcx, rbx
0x1800204e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204ea  mov     eax, edi
0x1800204ec  add     rsp, 38h
0x1800204f0  pop     r14
0x1800204f2  pop     rdi
0x1800204f3  pop     rsi
0x1800204f4  pop     rbx
0x1800204f5  retn
```
