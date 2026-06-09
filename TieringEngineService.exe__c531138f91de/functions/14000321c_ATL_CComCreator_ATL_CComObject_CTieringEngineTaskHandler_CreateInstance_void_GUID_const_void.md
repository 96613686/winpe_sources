# ATL::CComCreator<ATL::CComObject<CTieringEngineTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x14000321c`
- end: `0x140003379`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCTieringEngineTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `349`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140002df0`

## callees

- `0x140001a18`
- `0x14000321c`
- `0x1400035bc`
- `0x14003750c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CTieringEngineTaskHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  volatile signed __int32 *v7; // rax
  volatile signed __int32 *v8; // rbx
  signed __int32 v9; // eax
  int v10; // eax
  signed __int32 v11; // eax
  volatile signed __int32 *v14; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (volatile signed __int32 *)operator new(0x80u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 2) = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_BYTE *)v7 + 56) = 0;
      *((_QWORD *)v7 + 8) = 0;
      *((_QWORD *)v7 + 9) = 0;
      *((_QWORD *)v7 + 10) = 0;
      *((_QWORD *)v7 + 11) = 0;
      *((_QWORD *)v7 + 12) = 0;
      *((_QWORD *)v7 + 13) = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CTieringEngineTaskHandler>::`vftable';
      (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v14 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v14;
  }
  if ( v8 )
  {
    do
      v9 = *((_DWORD *)v8 + 2);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange(v8 + 2, v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 4));
    if ( v10 >= 0 )
    {
      *((_BYTE *)v8 + 56) = 1;
      v10 = CTieringEngineTaskHandler::FinalConstruct((PVOID)v8);
    }
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    do
      v11 = *((_DWORD *)v8 + 2);
    while ( v11 != 0x7FFFFFFF && v11 != _InterlockedCompareExchange(v8 + 2, v11 - 1, v11) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v8)((void *)v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x14000321c  mov     [rsp+arg_10], r8
0x140003221  mov     [rsp+arg_8], rdx
0x140003226  mov     [rsp+arg_0], rcx
0x14000322b  push    rbx
0x14000322c  push    rsi
0x14000322d  push    r12
0x14000322f  push    r14
0x140003231  push    r15
0x140003233  sub     rsp, 20h
0x140003237  mov     r14, r8
0x14000323a  mov     r15, rdx
0x14000323d  test    r8, r8
0x140003240  jnz     short loc_14000324C
0x140003242  mov     eax, 80004003h
0x140003247  jmp     loc_14000336C
0x14000324c  mov     qword ptr [r8], 0
0x140003253  mov     esi, 8007000Eh
0x140003258  mov     dword ptr [rsp+48h+arg_0], esi
0x14000325c  mov     [rsp+48h+arg_18], 0
0x140003265  mov     ecx, 80h; Size
0x14000326a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000326f  mov     rbx, rax
0x140003272  test    rbx, rbx
0x140003275  jz      short loc_1400032C7
0x140003277  mov     dword ptr [rax+8], 0
0x14000327e  xorps   xmm0, xmm0
0x140003281  xor     eax, eax
0x140003283  movups  xmmword ptr [rbx+10h], xmm0
0x140003287  movups  xmmword ptr [rbx+20h], xmm0
0x14000328b  mov     [rbx+30h], rax
0x14000328f  mov     [rbx+38h], al
0x140003292  mov     [rbx+40h], rax
0x140003296  mov     [rbx+48h], rax
0x14000329a  mov     [rbx+50h], rax
0x14000329e  mov     [rbx+58h], rax
0x1400032a2  mov     [rbx+60h], rax
0x1400032a6  mov     [rbx+68h], rax
0x1400032aa  lea     rax, ??_7?$CComObject@VCTieringEngineTaskHandler@@@ATL@@6B@; const ATL::CComObject<CTieringEngineTaskHandler>::`vftable'
0x1400032b1  mov     [rbx], rax
0x1400032b4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400032bb  mov     rax, [rcx]
0x1400032be  mov     rax, [rax+8]
0x1400032c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032c7  mov     [rsp+48h+arg_18], rbx
0x1400032cc  jmp     short loc_1400032E1
0x1400032ce  mov     r14, [rsp+48h+arg_10]
0x1400032d3  mov     r15, [rsp+48h+arg_8]
0x1400032d8  mov     esi, dword ptr [rsp+48h+arg_0]
0x1400032dc  mov     rbx, [rsp+48h+arg_18]
0x1400032e1  test    rbx, rbx
0x1400032e4  jz      loc_14000336A
0x1400032ea  mov     r12d, 7FFFFFFFh
0x1400032f0  jmp     short loc_1400032FC
0x1400032f2  lea     ecx, [rax+1]
0x1400032f5  lock cmpxchg [rbx+8], ecx
0x1400032fa  jz      short loc_140003304
0x1400032fc  mov     eax, [rbx+8]
0x1400032ff  cmp     eax, r12d
0x140003302  jnz     short loc_1400032F2
0x140003304  lea     rcx, [rbx+10h]; this
0x140003308  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x14000330d  test    eax, eax
0x14000330f  js      short loc_14000331D
0x140003311  mov     byte ptr [rbx+38h], 1
0x140003315  mov     rcx, rbx; pv
0x140003318  call    ?FinalConstruct@CTieringEngineTaskHandler@@QEAAJXZ; CTieringEngineTaskHandler::FinalConstruct(void)
0x14000331d  xor     esi, esi
0x14000331f  test    eax, eax
0x140003321  cmovs   esi, eax
0x140003324  jmp     short loc_140003330
0x140003326  lea     ecx, [rax-1]
0x140003329  lock cmpxchg [rbx+8], ecx
0x14000332e  jz      short loc_140003338
0x140003330  mov     eax, [rbx+8]
0x140003333  cmp     eax, r12d
0x140003336  jnz     short loc_140003326
0x140003338  test    esi, esi
0x14000333a  jnz     short loc_140003356
0x14000333c  mov     rax, [rbx]
0x14000333f  mov     r8, r14
0x140003342  mov     rdx, r15
0x140003345  mov     rcx, rbx
0x140003348  mov     rax, [rax]
0x14000334b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003350  mov     esi, eax
0x140003352  test    eax, eax
0x140003354  jz      short loc_14000336A
0x140003356  mov     r8, [rbx]
0x140003359  mov     edx, 1
0x14000335e  mov     rcx, rbx
0x140003361  mov     rax, [r8+38h]
0x140003365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000336a  mov     eax, esi
0x14000336c  add     rsp, 20h
0x140003370  pop     r15
0x140003372  pop     r14
0x140003374  pop     r12
0x140003376  pop     rsi
0x140003377  pop     rbx
0x140003378  retn
```
