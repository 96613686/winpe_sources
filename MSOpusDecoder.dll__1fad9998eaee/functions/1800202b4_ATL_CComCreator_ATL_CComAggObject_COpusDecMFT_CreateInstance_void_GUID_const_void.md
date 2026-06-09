# ATL::CComCreator<ATL::CComAggObject<COpusDecMFT>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800202b4`
- end: `0x1800203e4`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCOpusDecMFT@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800202a0`

## callees

- `0x1800013f4`
- `0x18001b048`
- `0x1800202b4`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<COpusDecMFT>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  int v10; // eax
  _QWORD *v11; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x158u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *v8 = &ATL::CComAggObject<COpusDecMFT>::`vftable';
      COpusDecMFT::COpusDecMFT((COpusDecMFT *)(v8 + 3));
      v9[3] = &ATL::CComContainedObject<COpusDecMFT>::`vftable'{for `CMFTSimpleBase'};
      v9[22] = &ATL::CComContainedObject<COpusDecMFT>::`vftable'{for `IMFTelemetryComponent'};
      v9[23] = a1;
      (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v11 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v11;
  }
  if ( v9 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD *))(v9[3] + 376LL))(v9 + 3);
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x1800202b4  mov     [rsp+arg_0], rbx
0x1800202b9  mov     [rsp+arg_10], r8
0x1800202be  mov     [rsp+arg_8], rdx
0x1800202c3  push    rsi
0x1800202c4  push    rdi
0x1800202c5  push    r12
0x1800202c7  push    r14
0x1800202c9  push    r15
0x1800202cb  sub     rsp, 30h
0x1800202cf  mov     rsi, r8
0x1800202d2  mov     r14, rdx
0x1800202d5  mov     r12, rcx
0x1800202d8  test    r8, r8
0x1800202db  jnz     short loc_1800202E7
0x1800202dd  mov     eax, 80004003h
0x1800202e2  jmp     loc_1800203D2
0x1800202e7  mov     qword ptr [r8], 0
0x1800202ee  mov     edi, 8007000Eh
0x1800202f3  mov     [rsp+58h+arg_18], edi
0x1800202f7  mov     [rsp+58h+var_38], 0
0x180020300  mov     ecx, 158h; Size
0x180020305  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002030a  mov     rbx, rax
0x18002030d  mov     [rsp+58h+var_30], rax
0x180020312  test    rbx, rbx
0x180020315  jz      short loc_180020365
0x180020317  mov     dword ptr [rax+8], 0
0x18002031e  lea     rax, ??_7?$CComAggObject@VCOpusDecMFT@@@ATL@@6B@; const ATL::CComAggObject<COpusDecMFT>::`vftable'
0x180020325  mov     [rbx], rax
0x180020328  lea     rcx, [rbx+18h]; this
0x18002032c  call    ??0COpusDecMFT@@QEAA@XZ; COpusDecMFT::COpusDecMFT(void)
0x180020331  lea     rax, ??_7?$CComContainedObject@VCOpusDecMFT@@@ATL@@6BCMFTSimpleBase@@@; const ATL::CComContainedObject<COpusDecMFT>::`vftable'{for `CMFTSimpleBase'}
0x180020338  mov     [rbx+18h], rax
0x18002033c  lea     rax, ??_7?$CComContainedObject@VCOpusDecMFT@@@ATL@@6BIMFTelemetryComponent@@@; const ATL::CComContainedObject<COpusDecMFT>::`vftable'{for `IMFTelemetryComponent'}
0x180020343  mov     [rbx+0B0h], rax
0x18002034a  mov     [rbx+0B8h], r12
0x180020351  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020358  mov     rax, [rcx]
0x18002035b  mov     rax, [rax+8]
0x18002035f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020364  nop
0x180020365  mov     [rsp+58h+var_38], rbx
0x18002036a  jmp     short loc_18002037F
0x18002036c  mov     rsi, [rsp+58h+arg_10]
0x180020371  mov     r14, [rsp+58h+arg_8]
0x180020376  mov     edi, [rsp+58h+arg_18]
0x18002037a  mov     rbx, [rsp+58h+var_38]
0x18002037f  test    rbx, rbx
0x180020382  jz      short loc_1800203D0
0x180020384  lea     rcx, [rbx+18h]
0x180020388  mov     rax, [rcx]
0x18002038b  mov     rax, [rax+178h]
0x180020392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020397  xor     edi, edi
0x180020399  test    eax, eax
0x18002039b  cmovs   edi, eax
0x18002039e  test    edi, edi
0x1800203a0  jnz     short loc_1800203BC
0x1800203a2  mov     rax, [rbx]
0x1800203a5  mov     r8, rsi
0x1800203a8  mov     rdx, r14
0x1800203ab  mov     rcx, rbx
0x1800203ae  mov     rax, [rax]
0x1800203b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203b6  mov     edi, eax
0x1800203b8  test    eax, eax
0x1800203ba  jz      short loc_1800203D0
0x1800203bc  mov     rdx, [rbx]
0x1800203bf  mov     rax, [rdx+18h]
0x1800203c3  mov     edx, 1
0x1800203c8  mov     rcx, rbx
0x1800203cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203d0  mov     eax, edi
0x1800203d2  mov     rbx, [rsp+58h+arg_0]
0x1800203d7  add     rsp, 30h
0x1800203db  pop     r15
0x1800203dd  pop     r14
0x1800203df  pop     r12
0x1800203e1  pop     rdi
0x1800203e2  pop     rsi
0x1800203e3  retn
```
