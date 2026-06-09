# ATL::CComCreator<ATL::CComAggObject<CTieringEngineTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140002f58`
- end: `0x1400030ad`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCTieringEngineTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140002df0`

## callees

- `0x140001a18`
- `0x140002f58`
- `0x1400035bc`
- `0x14003750c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CTieringEngineTaskHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  char *v8; // rax
  _BYTE *v9; // rdi
  int v10; // ecx
  int v11; // eax
  _BYTE *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x98u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CTieringEngineTaskHandler>::`vftable';
      *(_OWORD *)(v8 + 40) = 0;
      *(_OWORD *)(v8 + 56) = 0;
      *((_QWORD *)v8 + 9) = 0;
      v8[80] = 0;
      *((_QWORD *)v8 + 11) = 0;
      *((_QWORD *)v8 + 12) = 0;
      *((_QWORD *)v8 + 13) = 0;
      *((_QWORD *)v8 + 14) = 0;
      *((_QWORD *)v8 + 15) = 0;
      *((_QWORD *)v8 + 16) = 0;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CTieringEngineTaskHandler>::`vftable';
      *((_QWORD *)v8 + 4) = a1;
      (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 40));
    if ( v10 >= 0 )
      v9[80] = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    if ( v11 >= 0 )
      v11 = CTieringEngineTaskHandler::FinalConstruct(v9 + 24);
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x140002f58  mov     [rsp+arg_0], rsi
0x140002f5d  mov     [rsp+arg_10], r8
0x140002f62  mov     [rsp+arg_8], rdx
0x140002f67  push    rdi
0x140002f68  push    r12
0x140002f6a  push    r13
0x140002f6c  push    r14
0x140002f6e  push    r15
0x140002f70  sub     rsp, 30h
0x140002f74  mov     r14, r8
0x140002f77  mov     r15, rdx
0x140002f7a  mov     r12, rcx
0x140002f7d  test    r8, r8
0x140002f80  jnz     short loc_140002F8C
0x140002f82  mov     eax, 80004003h
0x140002f87  jmp     loc_14000309A
0x140002f8c  mov     qword ptr [r8], 0
0x140002f93  mov     esi, 8007000Eh
0x140002f98  mov     [rsp+58h+arg_18], esi
0x140002f9c  mov     [rsp+58h+var_38], 0
0x140002fa5  mov     ecx, 98h; Size
0x140002faa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002faf  mov     rdi, rax
0x140002fb2  test    rdi, rdi
0x140002fb5  jz      short loc_140003019
0x140002fb7  mov     dword ptr [rax+8], 0
0x140002fbe  lea     rax, ??_7?$CComAggObject@VCTieringEngineTaskHandler@@@ATL@@6B@; const ATL::CComAggObject<CTieringEngineTaskHandler>::`vftable'
0x140002fc5  mov     [rdi], rax
0x140002fc8  xorps   xmm0, xmm0
0x140002fcb  xor     eax, eax
0x140002fcd  movups  xmmword ptr [rdi+28h], xmm0
0x140002fd1  movups  xmmword ptr [rdi+38h], xmm0
0x140002fd5  mov     [rdi+48h], rax
0x140002fd9  mov     [rdi+50h], al
0x140002fdc  mov     [rdi+58h], rax
0x140002fe0  mov     [rdi+60h], rax
0x140002fe4  mov     [rdi+68h], rax
0x140002fe8  mov     [rdi+70h], rax
0x140002fec  mov     [rdi+78h], rax
0x140002ff0  mov     [rdi+80h], rax
0x140002ff7  lea     rax, ??_7?$CComContainedObject@VCTieringEngineTaskHandler@@@ATL@@6B@; const ATL::CComContainedObject<CTieringEngineTaskHandler>::`vftable'
0x140002ffe  mov     [rdi+18h], rax
0x140003002  mov     [rdi+20h], r12
0x140003006  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000300d  mov     rax, [rcx]
0x140003010  mov     rax, [rax+8]
0x140003014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003019  mov     [rsp+58h+var_38], rdi
0x14000301e  jmp     short loc_140003033
0x140003020  mov     r14, [rsp+58h+arg_10]
0x140003025  mov     r15, [rsp+58h+arg_8]
0x14000302a  mov     esi, [rsp+58h+arg_18]
0x14000302e  mov     rdi, [rsp+58h+var_38]
0x140003033  test    rdi, rdi
0x140003036  jz      short loc_140003098
0x140003038  lea     rcx, [rdi+28h]; this
0x14000303c  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140003041  mov     ecx, eax
0x140003043  test    eax, eax
0x140003045  js      short loc_14000304B
0x140003047  mov     byte ptr [rdi+50h], 1
0x14000304b  xor     eax, eax
0x14000304d  test    ecx, ecx
0x14000304f  cmovs   eax, ecx
0x140003052  test    eax, eax
0x140003054  js      short loc_14000305F
0x140003056  lea     rcx, [rdi+18h]; pv
0x14000305a  call    ?FinalConstruct@CTieringEngineTaskHandler@@QEAAJXZ; CTieringEngineTaskHandler::FinalConstruct(void)
0x14000305f  xor     esi, esi
0x140003061  test    eax, eax
0x140003063  cmovs   esi, eax
0x140003066  test    esi, esi
0x140003068  jnz     short loc_140003084
0x14000306a  mov     rax, [rdi]
0x14000306d  mov     r8, r14
0x140003070  mov     rdx, r15
0x140003073  mov     rcx, rdi
0x140003076  mov     rax, [rax]
0x140003079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000307e  mov     esi, eax
0x140003080  test    eax, eax
0x140003082  jz      short loc_140003098
0x140003084  mov     r8, [rdi]
0x140003087  mov     edx, 1
0x14000308c  mov     rcx, rdi
0x14000308f  mov     rax, [r8+18h]
0x140003093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003098  mov     eax, esi
0x14000309a  mov     rsi, [rsp+58h+arg_0]
0x14000309f  add     rsp, 30h
0x1400030a3  pop     r15
0x1400030a5  pop     r14
0x1400030a7  pop     r13
0x1400030a9  pop     r12
0x1400030ab  pop     rdi
0x1400030ac  retn
```
