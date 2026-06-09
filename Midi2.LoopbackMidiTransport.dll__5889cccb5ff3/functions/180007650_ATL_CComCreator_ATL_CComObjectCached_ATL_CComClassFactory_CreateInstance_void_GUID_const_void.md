# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180007650`
- end: `0x180007764`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800041a4`
- `0x1800041d0`
- `0x180007650`
- `0x1800084d8`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007742`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007742`

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
0x180007650  mov     [rsp+arg_10], r8
0x180007655  mov     [rsp+arg_8], rdx
0x18000765a  mov     [rsp+arg_0], rcx
0x18000765f  push    rbx
0x180007660  push    rsi
0x180007661  push    r12
0x180007663  push    r14
0x180007665  push    r15
0x180007667  sub     rsp, 30h
0x18000766b  mov     r14, r8
0x18000766e  mov     r12, rdx
0x180007671  mov     r15, rcx
0x180007674  test    r8, r8
0x180007677  jnz     short loc_180007683
0x180007679  mov     eax, 80004003h
0x18000767e  jmp     loc_180007757
0x180007683  mov     qword ptr [r8], 0
0x18000768a  mov     esi, 8007000Eh
0x18000768f  mov     [rsp+58h+arg_18], esi
0x180007693  mov     [rsp+58h+var_38], 0
0x18000769c  mov     ecx, 48h ; 'H'; Size
0x1800076a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800076a6  mov     rbx, rax
0x1800076a9  mov     dword ptr [rax+8], 0
0x1800076b0  xorps   xmm0, xmm0
0x1800076b3  xor     eax, eax
0x1800076b5  movups  xmmword ptr [rbx+10h], xmm0
0x1800076b9  movups  xmmword ptr [rbx+20h], xmm0
0x1800076bd  mov     [rbx+30h], rax
0x1800076c1  mov     [rbx+38h], al
0x1800076c4  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800076cb  mov     [rbx], rax
0x1800076ce  mov     [rsp+58h+var_38], rbx
0x1800076d3  jmp     short loc_1800076ED
0x1800076d5  mov     r14, [rsp+58h+arg_10]
0x1800076da  mov     r12, [rsp+58h+arg_8]
0x1800076df  mov     r15, [rsp+58h+arg_0]
0x1800076e4  mov     esi, [rsp+58h+arg_18]
0x1800076e8  mov     rbx, [rsp+58h+var_38]
0x1800076ed  test    rbx, rbx
0x1800076f0  jz      short loc_180007755
0x1800076f2  mov     [rbx+40h], r15
0x1800076f6  lea     rcx, [rbx+10h]; this
0x1800076fa  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800076ff  mov     esi, eax
0x180007701  test    eax, eax
0x180007703  js      short loc_180007723
0x180007705  mov     byte ptr [rbx+38h], 1
0x180007709  mov     rax, [rbx]
0x18000770c  mov     r8, r14
0x18000770f  mov     rdx, r12
0x180007712  mov     rcx, rbx
0x180007715  mov     rax, [rax]
0x180007718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000771d  mov     esi, eax
0x18000771f  test    eax, eax
0x180007721  jz      short loc_180007755
0x180007723  mov     dword ptr [rbx+8], 0C0000001h
0x18000772a  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180007731  mov     [rbx], rax
0x180007734  cmp     byte ptr [rbx+38h], 0
0x180007738  jz      short loc_180007748
0x18000773a  mov     byte ptr [rbx+38h], 0
0x18000773e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180007742  call    cs:__imp_DeleteCriticalSection
0x180007748  mov     edx, 48h ; 'H'
0x18000774d  mov     rcx, rbx; Block
0x180007750  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007755  mov     eax, esi
0x180007757  add     rsp, 30h
0x18000775b  pop     r15
0x18000775d  pop     r14
0x18000775f  pop     r12
0x180007761  pop     rsi
0x180007762  pop     rbx
0x180007763  retn
```
