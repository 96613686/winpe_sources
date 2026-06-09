# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003790`
- end: `0x1800038b6`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000126c`
- `0x18000233c`
- `0x180003790`
- `0x18000a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000389f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000389f`
- `KERNEL32!DeleteCriticalSection` at `0x180003896`
- `KERNEL32!DeleteCriticalSection` at `0x180003896`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r15
  __int64 v4; // r12
  __int64 v5; // r14
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // r14
  char *v11; // [rsp+20h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x48u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      v8[56] = 0;
      *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v11;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 8) = v5;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    v10 = v9 + 56;
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003790  mov     [rsp+arg_10], r8
0x180003795  mov     [rsp+arg_8], rdx
0x18000379a  mov     [rsp+arg_0], rcx
0x18000379f  push    rbx
0x1800037a0  push    rsi
0x1800037a1  push    r12
0x1800037a3  push    r13
0x1800037a5  push    r14
0x1800037a7  push    r15
0x1800037a9  sub     rsp, 38h
0x1800037ad  mov     r15, r8
0x1800037b0  mov     r12, rdx
0x1800037b3  mov     r14, rcx
0x1800037b6  test    r8, r8
0x1800037b9  jnz     short loc_1800037C5
0x1800037bb  mov     eax, 80004003h
0x1800037c0  jmp     loc_1800038A7
0x1800037c5  mov     qword ptr [r8], 0
0x1800037cc  mov     esi, 8007000Eh
0x1800037d1  mov     [rsp+68h+arg_18], esi
0x1800037d8  mov     [rsp+68h+var_48], 0
0x1800037e1  mov     ecx, 48h ; 'H'; Size
0x1800037e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800037eb  mov     rbx, rax
0x1800037ee  test    rbx, rbx
0x1800037f1  jz      short loc_180003818
0x1800037f3  mov     dword ptr [rax+8], 0
0x1800037fa  xorps   xmm0, xmm0
0x1800037fd  xor     eax, eax
0x1800037ff  movups  xmmword ptr [rbx+10h], xmm0
0x180003803  movups  xmmword ptr [rbx+20h], xmm0
0x180003807  mov     [rbx+30h], rax
0x18000380b  mov     [rbx+38h], al
0x18000380e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180003815  mov     [rbx], rax
0x180003818  mov     [rsp+68h+var_48], rbx
0x18000381d  jmp     short loc_18000383D
0x18000381f  mov     r15, [rsp+68h+arg_10]
0x180003827  mov     r12, [rsp+68h+arg_8]
0x18000382c  mov     r14, [rsp+68h+arg_0]
0x180003831  mov     esi, [rsp+68h+arg_18]
0x180003838  mov     rbx, [rsp+68h+var_48]
0x18000383d  test    rbx, rbx
0x180003840  jz      short loc_1800038A5
0x180003842  mov     [rbx+40h], r14
0x180003846  lea     rcx, [rbx+10h]; this
0x18000384a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000384f  mov     esi, eax
0x180003851  lea     r14, [rbx+38h]
0x180003855  test    eax, eax
0x180003857  js      short loc_180003877
0x180003859  mov     byte ptr [r14], 1
0x18000385d  mov     rax, [rbx]
0x180003860  mov     r8, r15
0x180003863  mov     rdx, r12
0x180003866  mov     rcx, rbx
0x180003869  mov     rax, [rax]
0x18000386c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003871  mov     esi, eax
0x180003873  test    eax, eax
0x180003875  jz      short loc_1800038A5
0x180003877  mov     dword ptr [rbx+8], 0C0000001h
0x18000387e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180003885  mov     [rbx], rax
0x180003888  cmp     byte ptr [r14], 0
0x18000388c  jz      short loc_18000389C
0x18000388e  mov     byte ptr [r14], 0
0x180003892  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003896  call    cs:__imp_DeleteCriticalSection
0x18000389c  mov     rcx, rbx
0x18000389f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800038a5  mov     eax, esi
0x1800038a7  add     rsp, 38h
0x1800038ab  pop     r15
0x1800038ad  pop     r14
0x1800038af  pop     r13
0x1800038b1  pop     r12
0x1800038b3  pop     rsi
0x1800038b4  pop     rbx
0x1800038b5  retn
```
