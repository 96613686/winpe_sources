# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180013fc0`
- end: `0x1800140d4`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001900`
- `0x18000193c`
- `0x18000e1e4`
- `0x180013fc0`
- `0x180035010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800140b2`
- `KERNEL32!DeleteCriticalSection` at `0x1800140b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180013fc0  mov     [rsp+arg_10], r8
0x180013fc5  mov     [rsp+arg_8], rdx
0x180013fca  mov     [rsp+arg_0], rcx
0x180013fcf  push    rbx
0x180013fd0  push    rsi
0x180013fd1  push    r12
0x180013fd3  push    r14
0x180013fd5  push    r15
0x180013fd7  sub     rsp, 30h
0x180013fdb  mov     r14, r8
0x180013fde  mov     r12, rdx
0x180013fe1  mov     r15, rcx
0x180013fe4  test    r8, r8
0x180013fe7  jnz     short loc_180013FF3
0x180013fe9  mov     eax, 80004003h
0x180013fee  jmp     loc_1800140C7
0x180013ff3  mov     qword ptr [r8], 0
0x180013ffa  mov     esi, 8007000Eh
0x180013fff  mov     [rsp+58h+arg_18], esi
0x180014003  mov     [rsp+58h+var_38], 0
0x18001400c  mov     ecx, 48h ; 'H'; Size
0x180014011  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014016  mov     rbx, rax
0x180014019  mov     dword ptr [rax+8], 0
0x180014020  xorps   xmm0, xmm0
0x180014023  xor     eax, eax
0x180014025  movups  xmmword ptr [rbx+10h], xmm0
0x180014029  movups  xmmword ptr [rbx+20h], xmm0
0x18001402d  mov     [rbx+30h], rax
0x180014031  mov     [rbx+38h], al
0x180014034  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18001403b  mov     [rbx], rax
0x18001403e  mov     [rsp+58h+var_38], rbx
0x180014043  jmp     short loc_18001405D
0x180014045  mov     r14, [rsp+58h+arg_10]
0x18001404a  mov     r12, [rsp+58h+arg_8]
0x18001404f  mov     r15, [rsp+58h+arg_0]
0x180014054  mov     esi, [rsp+58h+arg_18]
0x180014058  mov     rbx, [rsp+58h+var_38]
0x18001405d  test    rbx, rbx
0x180014060  jz      short loc_1800140C5
0x180014062  mov     [rbx+40h], r15
0x180014066  lea     rcx, [rbx+10h]; this
0x18001406a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18001406f  mov     esi, eax
0x180014071  test    eax, eax
0x180014073  js      short loc_180014093
0x180014075  mov     byte ptr [rbx+38h], 1
0x180014079  mov     rax, [rbx]
0x18001407c  mov     r8, r14
0x18001407f  mov     rdx, r12
0x180014082  mov     rcx, rbx
0x180014085  mov     rax, [rax]
0x180014088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001408d  mov     esi, eax
0x18001408f  test    eax, eax
0x180014091  jz      short loc_1800140C5
0x180014093  mov     dword ptr [rbx+8], 0C0000001h
0x18001409a  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800140a1  mov     [rbx], rax
0x1800140a4  cmp     byte ptr [rbx+38h], 0
0x1800140a8  jz      short loc_1800140B8
0x1800140aa  mov     byte ptr [rbx+38h], 0
0x1800140ae  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800140b2  call    cs:__imp_DeleteCriticalSection
0x1800140b8  mov     edx, 48h ; 'H'
0x1800140bd  mov     rcx, rbx; Block
0x1800140c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800140c5  mov     eax, esi
0x1800140c7  add     rsp, 30h
0x1800140cb  pop     r15
0x1800140cd  pop     r14
0x1800140cf  pop     r12
0x1800140d1  pop     rsi
0x1800140d2  pop     rbx
0x1800140d3  retn
```
