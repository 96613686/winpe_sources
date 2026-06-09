# ATL::CComCreator<ATL::CComAggObject<CRASrv>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140005488`
- end: `0x1400055af`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCRASrv@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `295`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005440`

## callees

- `0x1400012d4`
- `0x140005488`
- `0x140007304`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CRASrv>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  _DWORD *v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x60u);
    v9 = v8;
    if ( v8 )
    {
      v8[2] = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CRASrv>::`vftable';
      *((_OWORD *)v8 + 3) = 0;
      *((_OWORD *)v8 + 4) = 0;
      *((_QWORD *)v8 + 10) = 0;
      *((_BYTE *)v8 + 88) = 0;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CRASrv>::`vftable'{for `ATL::IDispatchImpl<IRASrv,&_GUID const IID_IRASrv,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v8 + 4) = &ATL::CComContainedObject<CRASrv>::`vftable'{for `ISupportErrorInfo'};
      *((_QWORD *)v8 + 5) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v13;
  }
  if ( v9 )
  {
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 12));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x140005488  mov     [rsp+arg_10], r8
0x14000548d  mov     [rsp+arg_8], rdx
0x140005492  push    rbx
0x140005493  push    rsi
0x140005494  push    rdi
0x140005495  push    r14
0x140005497  push    r15
0x140005499  sub     rsp, 30h
0x14000549d  mov     rsi, r8
0x1400054a0  mov     r14, rdx
0x1400054a3  mov     r15, rcx
0x1400054a6  test    r8, r8
0x1400054a9  jnz     short loc_1400054B5
0x1400054ab  mov     eax, 80004003h
0x1400054b0  jmp     loc_1400055A3
0x1400054b5  mov     qword ptr [r8], 0
0x1400054bc  mov     edi, 8007000Eh
0x1400054c1  mov     [rsp+58h+arg_18], edi
0x1400054c5  mov     [rsp+58h+var_38], 0
0x1400054ce  mov     ecx, 60h ; '`'; Size
0x1400054d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400054d8  mov     rbx, rax
0x1400054db  test    rbx, rbx
0x1400054de  jz      short loc_140005532
0x1400054e0  mov     dword ptr [rax+8], 0
0x1400054e7  lea     rax, ??_7?$CComAggObject@VCRASrv@@@ATL@@6B@; const ATL::CComAggObject<CRASrv>::`vftable'
0x1400054ee  mov     [rbx], rax
0x1400054f1  xorps   xmm0, xmm0
0x1400054f4  xor     eax, eax
0x1400054f6  movups  xmmword ptr [rbx+30h], xmm0
0x1400054fa  movups  xmmword ptr [rbx+40h], xmm0
0x1400054fe  mov     [rbx+50h], rax
0x140005502  mov     [rbx+58h], al
0x140005505  lea     rax, ??_7?$CComContainedObject@VCRASrv@@@ATL@@6B?$IDispatchImpl@UIRASrv@@$1?IID_IRASrv@@3U_GUID@@B$1?LIBID_RAServerLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CRASrv>::`vftable'{for `ATL::IDispatchImpl<IRASrv,&_GUID const IID_IRASrv,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'}
0x14000550c  mov     [rbx+18h], rax
0x140005510  lea     rax, ??_7?$CComContainedObject@VCRASrv@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CRASrv>::`vftable'{for `ISupportErrorInfo'}
0x140005517  mov     [rbx+20h], rax
0x14000551b  mov     [rbx+28h], r15
0x14000551f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140005526  mov     rax, [rcx]
0x140005529  mov     rax, [rax+8]
0x14000552d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005532  mov     [rsp+58h+var_38], rbx
0x140005537  jmp     short loc_14000554C
0x140005539  mov     rsi, [rsp+58h+arg_10]
0x14000553e  mov     r14, [rsp+58h+arg_8]
0x140005543  mov     edi, [rsp+58h+arg_18]
0x140005547  mov     rbx, [rsp+58h+var_38]
0x14000554c  test    rbx, rbx
0x14000554f  jz      short loc_1400055A1
0x140005551  lea     rcx, [rbx+30h]; this
0x140005555  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x14000555a  xor     ecx, ecx
0x14000555c  test    eax, eax
0x14000555e  cmovs   ecx, eax
0x140005561  xor     eax, eax
0x140005563  test    ecx, ecx
0x140005565  cmovs   eax, ecx
0x140005568  xor     edi, edi
0x14000556a  test    eax, eax
0x14000556c  cmovs   edi, eax
0x14000556f  test    edi, edi
0x140005571  jnz     short loc_14000558D
0x140005573  mov     rax, [rbx]
0x140005576  mov     r8, rsi
0x140005579  mov     rdx, r14
0x14000557c  mov     rcx, rbx
0x14000557f  mov     rax, [rax]
0x140005582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005587  mov     edi, eax
0x140005589  test    eax, eax
0x14000558b  jz      short loc_1400055A1
0x14000558d  mov     rdx, [rbx]
0x140005590  mov     rax, [rdx+18h]
0x140005594  mov     edx, 1
0x140005599  mov     rcx, rbx
0x14000559c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055a1  mov     eax, edi
0x1400055a3  add     rsp, 30h
0x1400055a7  pop     r15
0x1400055a9  pop     r14
0x1400055ab  pop     rdi
0x1400055ac  pop     rsi
0x1400055ad  pop     rbx
0x1400055ae  retn
```
