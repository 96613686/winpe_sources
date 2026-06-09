# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006c20`
- end: `0x180006d34`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003914`
- `0x180003940`
- `0x180006c20`
- `0x180007aa8`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006d12`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006d12`

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
0x180006c20  mov     [rsp+arg_10], r8
0x180006c25  mov     [rsp+arg_8], rdx
0x180006c2a  mov     [rsp+arg_0], rcx
0x180006c2f  push    rbx
0x180006c30  push    rsi
0x180006c31  push    r12
0x180006c33  push    r14
0x180006c35  push    r15
0x180006c37  sub     rsp, 30h
0x180006c3b  mov     r14, r8
0x180006c3e  mov     r12, rdx
0x180006c41  mov     r15, rcx
0x180006c44  test    r8, r8
0x180006c47  jnz     short loc_180006C53
0x180006c49  mov     eax, 80004003h
0x180006c4e  jmp     loc_180006D27
0x180006c53  mov     qword ptr [r8], 0
0x180006c5a  mov     esi, 8007000Eh
0x180006c5f  mov     [rsp+58h+arg_18], esi
0x180006c63  mov     [rsp+58h+var_38], 0
0x180006c6c  mov     ecx, 48h ; 'H'; Size
0x180006c71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006c76  mov     rbx, rax
0x180006c79  mov     dword ptr [rax+8], 0
0x180006c80  xorps   xmm0, xmm0
0x180006c83  xor     eax, eax
0x180006c85  movups  xmmword ptr [rbx+10h], xmm0
0x180006c89  movups  xmmword ptr [rbx+20h], xmm0
0x180006c8d  mov     [rbx+30h], rax
0x180006c91  mov     [rbx+38h], al
0x180006c94  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180006c9b  mov     [rbx], rax
0x180006c9e  mov     [rsp+58h+var_38], rbx
0x180006ca3  jmp     short loc_180006CBD
0x180006ca5  mov     r14, [rsp+58h+arg_10]
0x180006caa  mov     r12, [rsp+58h+arg_8]
0x180006caf  mov     r15, [rsp+58h+arg_0]
0x180006cb4  mov     esi, [rsp+58h+arg_18]
0x180006cb8  mov     rbx, [rsp+58h+var_38]
0x180006cbd  test    rbx, rbx
0x180006cc0  jz      short loc_180006D25
0x180006cc2  mov     [rbx+40h], r15
0x180006cc6  lea     rcx, [rbx+10h]; this
0x180006cca  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006ccf  mov     esi, eax
0x180006cd1  test    eax, eax
0x180006cd3  js      short loc_180006CF3
0x180006cd5  mov     byte ptr [rbx+38h], 1
0x180006cd9  mov     rax, [rbx]
0x180006cdc  mov     r8, r14
0x180006cdf  mov     rdx, r12
0x180006ce2  mov     rcx, rbx
0x180006ce5  mov     rax, [rax]
0x180006ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ced  mov     esi, eax
0x180006cef  test    eax, eax
0x180006cf1  jz      short loc_180006D25
0x180006cf3  mov     dword ptr [rbx+8], 0C0000001h
0x180006cfa  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180006d01  mov     [rbx], rax
0x180006d04  cmp     byte ptr [rbx+38h], 0
0x180006d08  jz      short loc_180006D18
0x180006d0a  mov     byte ptr [rbx+38h], 0
0x180006d0e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180006d12  call    cs:__imp_DeleteCriticalSection
0x180006d18  mov     edx, 48h ; 'H'
0x180006d1d  mov     rcx, rbx; Block
0x180006d20  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006d25  mov     eax, esi
0x180006d27  add     rsp, 30h
0x180006d2b  pop     r15
0x180006d2d  pop     r14
0x180006d2f  pop     r12
0x180006d31  pop     rsi
0x180006d32  pop     rbx
0x180006d33  retn
```
