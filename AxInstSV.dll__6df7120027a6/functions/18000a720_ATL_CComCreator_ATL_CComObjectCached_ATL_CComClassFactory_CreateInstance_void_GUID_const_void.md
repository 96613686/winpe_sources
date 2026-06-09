# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a720`
- end: `0x18000a804`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `228`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000177c`
- `0x180008cfc`
- `0x18000a720`
- `0x18000bf48`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  __int64 v5; // r14
  _DWORD *v7; // rbx
  int v8; // edi
  _DWORD *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = operator new(0x48u);
    v7[2] = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    *((_QWORD *)v7 + 8) = v5;
    v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v7 + 4));
    if ( v8 < 0 || (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0 )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a720  mov     [rsp+arg_10], r8
0x18000a725  mov     [rsp+arg_8], rdx
0x18000a72a  mov     [rsp+arg_0], rcx
0x18000a72f  push    rbx
0x18000a730  push    rsi
0x18000a731  push    rdi
0x18000a732  push    r14
0x18000a734  push    r15
0x18000a736  sub     rsp, 30h
0x18000a73a  mov     rsi, r8
0x18000a73d  mov     r15, rdx
0x18000a740  mov     r14, rcx
0x18000a743  test    r8, r8
0x18000a746  jnz     short loc_18000A752
0x18000a748  mov     eax, 80004003h
0x18000a74d  jmp     loc_18000A7F8
0x18000a752  mov     qword ptr [r8], 0
0x18000a759  mov     edi, 8007000Eh
0x18000a75e  mov     [rsp+58h+arg_18], edi
0x18000a762  mov     [rsp+58h+var_38], 0
0x18000a76b  mov     ecx, 48h ; 'H'; Size
0x18000a770  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a775  mov     rbx, rax
0x18000a778  mov     dword ptr [rax+8], 0
0x18000a77f  xorps   xmm0, xmm0
0x18000a782  xor     eax, eax
0x18000a784  movups  xmmword ptr [rbx+10h], xmm0
0x18000a788  movups  xmmword ptr [rbx+20h], xmm0
0x18000a78c  mov     [rbx+30h], rax
0x18000a790  mov     [rbx+38h], al
0x18000a793  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000a79a  mov     [rbx], rax
0x18000a79d  mov     [rsp+58h+var_38], rbx
0x18000a7a2  jmp     short loc_18000A7BC
0x18000a7a4  mov     rsi, [rsp+58h+arg_10]
0x18000a7a9  mov     r15, [rsp+58h+arg_8]
0x18000a7ae  mov     r14, [rsp+58h+arg_0]
0x18000a7b3  mov     edi, [rsp+58h+arg_18]
0x18000a7b7  mov     rbx, [rsp+58h+var_38]
0x18000a7bc  test    rbx, rbx
0x18000a7bf  jz      short loc_18000A7F6
0x18000a7c1  mov     [rbx+40h], r14
0x18000a7c5  lea     rcx, [rbx+10h]; this
0x18000a7c9  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000a7ce  mov     edi, eax
0x18000a7d0  test    eax, eax
0x18000a7d2  js      short loc_18000A7EE
0x18000a7d4  mov     rax, [rbx]
0x18000a7d7  mov     r8, rsi
0x18000a7da  mov     rdx, r15
0x18000a7dd  mov     rcx, rbx
0x18000a7e0  mov     rax, [rax]
0x18000a7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7e8  mov     edi, eax
0x18000a7ea  test    eax, eax
0x18000a7ec  jz      short loc_18000A7F6
0x18000a7ee  mov     rcx, rbx; Block
0x18000a7f1  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x18000a7f6  mov     eax, edi
0x18000a7f8  add     rsp, 30h
0x18000a7fc  pop     r15
0x18000a7fe  pop     r14
0x18000a800  pop     rdi
0x18000a801  pop     rsi
0x18000a802  pop     rbx
0x18000a803  retn
```
