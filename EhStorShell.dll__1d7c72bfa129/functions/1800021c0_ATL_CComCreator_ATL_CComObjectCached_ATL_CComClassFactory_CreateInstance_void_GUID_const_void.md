# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800021c0`
- end: `0x1800022d1`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `273`
- prototype: `__int64 __fastcall(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *), __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800021c0`
- `0x1800022d8`
- `0x180002300`
- `0x180006b74`
- `0x180006b8c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 (__fastcall **a1)(_QWORD, __int64, _QWORD *),
        __int64 a2,
        _QWORD *a3)
{
  int v6; // edi
  void *v7; // rax
  __int64 (__fastcall ***v8)(_QWORD, __int64, _QWORD *); // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x48u);
  v8 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 2) = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v8[8] = a1;
    v6 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 2));
    if ( v6 < 0 || (*((_BYTE *)v8 + 56) = 1, (v6 = (**v8)(v8, a2, a3)) != 0) )
    {
      ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>((__int64)v8);
      operator delete(v8);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800021c0  mov     [rsp+arg_10], r8
0x1800021c5  mov     [rsp+arg_8], rdx
0x1800021ca  mov     [rsp+arg_0], rcx
0x1800021cf  push    rbx
0x1800021d0  push    rsi
0x1800021d1  push    rdi
0x1800021d2  push    r12
0x1800021d4  push    r14
0x1800021d6  push    r15
0x1800021d8  sub     rsp, 38h
0x1800021dc  mov     rsi, r8
0x1800021df  mov     r15, rdx
0x1800021e2  mov     r14, rcx
0x1800021e5  test    r8, r8
0x1800021e8  jz      loc_18000227B
0x1800021ee  xor     r12d, r12d
0x1800021f1  mov     [r8], r12
0x1800021f4  mov     edi, 8007000Eh
0x1800021f9  mov     [rsp+68h+arg_18], edi
0x180002200  mov     [rsp+68h+var_48], r12
0x180002205  mov     ecx, 48h ; 'H'; Size
0x18000220a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000220f  mov     rbx, rax
0x180002212  test    rax, rax
0x180002215  jz      short loc_180002276
0x180002217  mov     [rax+8], r12d
0x18000221b  xorps   xmm0, xmm0
0x18000221e  xor     eax, eax
0x180002220  movups  xmmword ptr [rbx+10h], xmm0
0x180002224  movups  xmmword ptr [rbx+20h], xmm0
0x180002228  mov     [rbx+30h], rax
0x18000222c  mov     [rbx+38h], al
0x18000222f  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180002236  mov     [rbx], rax
0x180002239  mov     [rsp+68h+var_48], rbx
0x18000223e  test    rbx, rbx
0x180002241  jz      short loc_180002266
0x180002243  mov     [rbx+40h], r14
0x180002247  lea     rcx, [rbx+10h]; this
0x18000224b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002250  mov     edi, eax
0x180002252  test    eax, eax
0x180002254  jns     short loc_18000228E
0x180002256  mov     rcx, rbx
0x180002259  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x18000225e  mov     rcx, rbx; Block
0x180002261  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002266  mov     eax, edi
0x180002268  add     rsp, 38h
0x18000226c  pop     r15
0x18000226e  pop     r14
0x180002270  pop     r12
0x180002272  pop     rdi
0x180002273  pop     rsi
0x180002274  pop     rbx
0x180002275  retn
0x180002276  mov     rbx, r12
0x180002279  jmp     short loc_180002239
0x18000227b  mov     eax, 80004003h
0x180002280  add     rsp, 38h
0x180002284  pop     r15
0x180002286  pop     r14
0x180002288  pop     r12
0x18000228a  pop     rdi
0x18000228b  pop     rsi
0x18000228c  pop     rbx
0x18000228d  retn
0x18000228e  mov     byte ptr [rbx+38h], 1
0x180002292  mov     rax, [rbx]
0x180002295  mov     r8, rsi
0x180002298  mov     rdx, r15
0x18000229b  mov     rcx, rbx
0x18000229e  mov     rax, [rax]
0x1800022a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a6  mov     edi, eax
0x1800022a8  test    eax, eax
0x1800022aa  jz      short loc_180002266
0x1800022ac  jmp     short loc_180002256
0x1800022ae  mov     rsi, [rsp+68h+arg_10]
0x1800022b6  mov     r15, [rsp+68h+arg_8]
0x1800022bb  mov     r14, [rsp+68h+arg_0]
0x1800022c0  mov     edi, [rsp+68h+arg_18]
0x1800022c7  mov     rbx, [rsp+68h+var_48]
0x1800022cc  jmp     loc_18000223E
```
