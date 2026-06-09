# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006590`
- end: `0x1800066a4`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800033f4`
- `0x180003420`
- `0x180006590`
- `0x180007418`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006682`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006682`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r12
  __int64 v5; // r15
  _BYTE *v7; // rbx
  int v8; // esi
  _BYTE *v9; // [rsp+20h] [rbp-38h]

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
    *((_DWORD *)v7 + 2) = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    v7[56] = 0;
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
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 16));
    if ( v8 < 0 || (v7[56] = 1, (v8 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
    {
      *((_DWORD *)v7 + 2) = -1073741823;
      *(_QWORD *)v7 = &ATL::CComClassFactory::`vftable';
      if ( v7[56] )
      {
        v7[56] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
      }
      operator delete(v7);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006590  mov     [rsp+arg_10], r8
0x180006595  mov     [rsp+arg_8], rdx
0x18000659a  mov     [rsp+arg_0], rcx
0x18000659f  push    rbx
0x1800065a0  push    rsi
0x1800065a1  push    r12
0x1800065a3  push    r14
0x1800065a5  push    r15
0x1800065a7  sub     rsp, 30h
0x1800065ab  mov     r14, r8
0x1800065ae  mov     r12, rdx
0x1800065b1  mov     r15, rcx
0x1800065b4  test    r8, r8
0x1800065b7  jnz     short loc_1800065C3
0x1800065b9  mov     eax, 80004003h
0x1800065be  jmp     loc_180006697
0x1800065c3  mov     qword ptr [r8], 0
0x1800065ca  mov     esi, 8007000Eh
0x1800065cf  mov     [rsp+58h+arg_18], esi
0x1800065d3  mov     [rsp+58h+var_38], 0
0x1800065dc  mov     ecx, 48h ; 'H'; Size
0x1800065e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800065e6  mov     rbx, rax
0x1800065e9  mov     dword ptr [rax+8], 0
0x1800065f0  xorps   xmm0, xmm0
0x1800065f3  xor     eax, eax
0x1800065f5  movups  xmmword ptr [rbx+10h], xmm0
0x1800065f9  movups  xmmword ptr [rbx+20h], xmm0
0x1800065fd  mov     [rbx+30h], rax
0x180006601  mov     [rbx+38h], al
0x180006604  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000660b  mov     [rbx], rax
0x18000660e  mov     [rsp+58h+var_38], rbx
0x180006613  jmp     short loc_18000662D
0x180006615  mov     r14, [rsp+58h+arg_10]
0x18000661a  mov     r12, [rsp+58h+arg_8]
0x18000661f  mov     r15, [rsp+58h+arg_0]
0x180006624  mov     esi, [rsp+58h+arg_18]
0x180006628  mov     rbx, [rsp+58h+var_38]
0x18000662d  test    rbx, rbx
0x180006630  jz      short loc_180006695
0x180006632  mov     [rbx+40h], r15
0x180006636  lea     rcx, [rbx+10h]; this
0x18000663a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000663f  mov     esi, eax
0x180006641  test    eax, eax
0x180006643  js      short loc_180006663
0x180006645  mov     byte ptr [rbx+38h], 1
0x180006649  mov     rax, [rbx]
0x18000664c  mov     r8, r14
0x18000664f  mov     rdx, r12
0x180006652  mov     rcx, rbx
0x180006655  mov     rax, [rax]
0x180006658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000665d  mov     esi, eax
0x18000665f  test    eax, eax
0x180006661  jz      short loc_180006695
0x180006663  mov     dword ptr [rbx+8], 0C0000001h
0x18000666a  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180006671  mov     [rbx], rax
0x180006674  cmp     byte ptr [rbx+38h], 0
0x180006678  jz      short loc_180006688
0x18000667a  mov     byte ptr [rbx+38h], 0
0x18000667e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180006682  call    cs:__imp_DeleteCriticalSection
0x180006688  mov     edx, 48h ; 'H'
0x18000668d  mov     rcx, rbx; Block
0x180006690  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006695  mov     eax, esi
0x180006697  add     rsp, 30h
0x18000669b  pop     r15
0x18000669d  pop     r14
0x18000669f  pop     r12
0x1800066a1  pop     rsi
0x1800066a2  pop     rbx
0x1800066a3  retn
```
