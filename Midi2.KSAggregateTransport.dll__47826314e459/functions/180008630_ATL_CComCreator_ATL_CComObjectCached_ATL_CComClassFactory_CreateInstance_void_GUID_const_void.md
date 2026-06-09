# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180008630`
- end: `0x180008744`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005044`
- `0x180005070`
- `0x180008630`
- `0x180009594`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008722`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008722`

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
0x180008630  mov     [rsp+arg_10], r8
0x180008635  mov     [rsp+arg_8], rdx
0x18000863a  mov     [rsp+arg_0], rcx
0x18000863f  push    rbx
0x180008640  push    rsi
0x180008641  push    r12
0x180008643  push    r14
0x180008645  push    r15
0x180008647  sub     rsp, 30h
0x18000864b  mov     r14, r8
0x18000864e  mov     r12, rdx
0x180008651  mov     r15, rcx
0x180008654  test    r8, r8
0x180008657  jnz     short loc_180008663
0x180008659  mov     eax, 80004003h
0x18000865e  jmp     loc_180008737
0x180008663  mov     qword ptr [r8], 0
0x18000866a  mov     esi, 8007000Eh
0x18000866f  mov     [rsp+58h+arg_18], esi
0x180008673  mov     [rsp+58h+var_38], 0
0x18000867c  mov     ecx, 48h ; 'H'; Size
0x180008681  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008686  mov     rbx, rax
0x180008689  mov     dword ptr [rax+8], 0
0x180008690  xorps   xmm0, xmm0
0x180008693  xor     eax, eax
0x180008695  movups  xmmword ptr [rbx+10h], xmm0
0x180008699  movups  xmmword ptr [rbx+20h], xmm0
0x18000869d  mov     [rbx+30h], rax
0x1800086a1  mov     [rbx+38h], al
0x1800086a4  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800086ab  mov     [rbx], rax
0x1800086ae  mov     [rsp+58h+var_38], rbx
0x1800086b3  jmp     short loc_1800086CD
0x1800086b5  mov     r14, [rsp+58h+arg_10]
0x1800086ba  mov     r12, [rsp+58h+arg_8]
0x1800086bf  mov     r15, [rsp+58h+arg_0]
0x1800086c4  mov     esi, [rsp+58h+arg_18]
0x1800086c8  mov     rbx, [rsp+58h+var_38]
0x1800086cd  test    rbx, rbx
0x1800086d0  jz      short loc_180008735
0x1800086d2  mov     [rbx+40h], r15
0x1800086d6  lea     rcx, [rbx+10h]; this
0x1800086da  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800086df  mov     esi, eax
0x1800086e1  test    eax, eax
0x1800086e3  js      short loc_180008703
0x1800086e5  mov     byte ptr [rbx+38h], 1
0x1800086e9  mov     rax, [rbx]
0x1800086ec  mov     r8, r14
0x1800086ef  mov     rdx, r12
0x1800086f2  mov     rcx, rbx
0x1800086f5  mov     rax, [rax]
0x1800086f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086fd  mov     esi, eax
0x1800086ff  test    eax, eax
0x180008701  jz      short loc_180008735
0x180008703  mov     dword ptr [rbx+8], 0C0000001h
0x18000870a  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180008711  mov     [rbx], rax
0x180008714  cmp     byte ptr [rbx+38h], 0
0x180008718  jz      short loc_180008728
0x18000871a  mov     byte ptr [rbx+38h], 0
0x18000871e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180008722  call    cs:__imp_DeleteCriticalSection
0x180008728  mov     edx, 48h ; 'H'
0x18000872d  mov     rcx, rbx; Block
0x180008730  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008735  mov     eax, esi
0x180008737  add     rsp, 30h
0x18000873b  pop     r15
0x18000873d  pop     r14
0x18000873f  pop     r12
0x180008741  pop     rsi
0x180008742  pop     rbx
0x180008743  retn
```
