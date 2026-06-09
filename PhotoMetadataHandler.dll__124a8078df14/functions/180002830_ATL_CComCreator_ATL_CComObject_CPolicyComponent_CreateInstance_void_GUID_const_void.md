# ATL::CComCreator<ATL::CComObject<CPolicyComponent>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002830`
- end: `0x18000294b`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPolicyComponent@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800027d0`

## callees

- `0x180002830`
- `0x180002960`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002872`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002872`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPolicyComponent>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v5; // edi
  _DWORD *v6; // rax
  _DWORD *v7; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  v6 = LocalAlloc(0x40u, 0x48u);
  v7 = v6;
  if ( v6 )
  {
    v6[2] = 0;
    *((_OWORD *)v6 + 1) = 0;
    *((_OWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 6) = 0;
    *((_BYTE *)v6 + 56) = 0;
    *((_BYTE *)v6 + 64) = 0;
    v6[17] = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CPolicyComponent>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v7 = 0;
  }
  if ( v7 )
  {
    v5 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v7 + 4));
    if ( v5 < 0
      || (*((_BYTE *)v7 + 56) = 1, (v5 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0) )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 72LL))(v7, 1);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002830  mov     [rsp+arg_10], r8
0x180002835  mov     [rsp+arg_8], rdx
0x18000283a  mov     [rsp+arg_0], rcx
0x18000283f  push    rbx
0x180002840  push    rsi
0x180002841  push    rdi
0x180002842  push    r14
0x180002844  push    r15
0x180002846  sub     rsp, 20h
0x18000284a  mov     rsi, r8
0x18000284d  mov     r15, rdx
0x180002850  test    r8, r8
0x180002853  jz      loc_18000290F
0x180002859  xor     r14d, r14d
0x18000285c  mov     [r8], r14
0x18000285f  mov     edi, 8007000Eh
0x180002864  mov     dword ptr [rsp+48h+arg_0], edi
0x180002868  mov     edx, 48h ; 'H'; uBytes
0x18000286d  mov     ecx, 40h ; '@'; uFlags
0x180002872  call    cs:__imp_LocalAlloc
0x180002878  mov     rbx, rax
0x18000287b  mov     [rsp+48h+arg_18], rax
0x180002880  test    rax, rax
0x180002883  jz      loc_18000290A
0x180002889  mov     [rax+8], r14d
0x18000288d  xorps   xmm0, xmm0
0x180002890  xor     eax, eax
0x180002892  movups  xmmword ptr [rbx+10h], xmm0
0x180002896  movups  xmmword ptr [rbx+20h], xmm0
0x18000289a  mov     [rbx+30h], rax
0x18000289e  mov     [rbx+38h], al
0x1800028a1  mov     [rbx+40h], al
0x1800028a4  mov     [rbx+44h], r14d
0x1800028a8  lea     rax, ??_7?$CComObject@VCPolicyComponent@@@ATL@@6B@; const ATL::CComObject<CPolicyComponent>::`vftable'
0x1800028af  mov     [rbx], rax
0x1800028b2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800028b9  mov     rax, [rcx]
0x1800028bc  mov     rax, [rax+8]
0x1800028c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028c5  mov     [rsp+48h+arg_18], rbx
0x1800028ca  test    rbx, rbx
0x1800028cd  jz      short loc_1800028FC
0x1800028cf  lea     rcx, [rbx+10h]; this
0x1800028d3  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800028d8  mov     edi, eax
0x1800028da  test    eax, eax
0x1800028dc  js      short loc_180002935
0x1800028de  mov     byte ptr [rbx+38h], 1
0x1800028e2  mov     rax, [rbx]
0x1800028e5  mov     r8, rsi
0x1800028e8  mov     rdx, r15
0x1800028eb  mov     rcx, rbx
0x1800028ee  mov     rax, [rax]
0x1800028f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f6  mov     edi, eax
0x1800028f8  test    eax, eax
0x1800028fa  jnz     short loc_180002935
0x1800028fc  mov     eax, edi
0x1800028fe  add     rsp, 20h
0x180002902  pop     r15
0x180002904  pop     r14
0x180002906  pop     rdi
0x180002907  pop     rsi
0x180002908  pop     rbx
0x180002909  retn
0x18000290a  mov     rbx, r14
0x18000290d  jmp     short loc_1800028C5
0x18000290f  mov     eax, 80004003h
0x180002914  add     rsp, 20h
0x180002918  pop     r15
0x18000291a  pop     r14
0x18000291c  pop     rdi
0x18000291d  pop     rsi
0x18000291e  pop     rbx
0x18000291f  retn
0x180002920  mov     rsi, [rsp+48h+arg_10]
0x180002925  mov     r15, [rsp+48h+arg_8]
0x18000292a  mov     edi, dword ptr [rsp+48h+arg_0]
0x18000292e  mov     rbx, [rsp+48h+arg_18]
0x180002933  jmp     short loc_1800028CA
0x180002935  mov     rax, [rbx]
0x180002938  mov     edx, 1
0x18000293d  mov     rcx, rbx
0x180002940  mov     rax, [rax+48h]
0x180002944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002949  jmp     short loc_1800028FC
```
