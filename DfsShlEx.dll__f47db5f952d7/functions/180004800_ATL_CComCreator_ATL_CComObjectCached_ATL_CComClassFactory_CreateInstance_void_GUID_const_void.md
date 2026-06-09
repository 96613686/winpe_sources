# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004800`
- end: `0x180004926`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001164`
- `0x180004800`
- `0x180004afc`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000490f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000490f`
- `KERNEL32!DeleteCriticalSection` at `0x180004906`
- `KERNEL32!DeleteCriticalSection` at `0x180004906`

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
0x180004800  mov     [rsp+arg_10], r8
0x180004805  mov     [rsp+arg_8], rdx
0x18000480a  mov     [rsp+arg_0], rcx
0x18000480f  push    rbx
0x180004810  push    rsi
0x180004811  push    r12
0x180004813  push    r13
0x180004815  push    r14
0x180004817  push    r15
0x180004819  sub     rsp, 38h
0x18000481d  mov     r15, r8
0x180004820  mov     r12, rdx
0x180004823  mov     r14, rcx
0x180004826  test    r8, r8
0x180004829  jnz     short loc_180004835
0x18000482b  mov     eax, 80004003h
0x180004830  jmp     loc_180004917
0x180004835  mov     qword ptr [r8], 0
0x18000483c  mov     esi, 8007000Eh
0x180004841  mov     [rsp+68h+arg_18], esi
0x180004848  mov     [rsp+68h+var_48], 0
0x180004851  mov     ecx, 48h ; 'H'; Size
0x180004856  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000485b  mov     rbx, rax
0x18000485e  test    rbx, rbx
0x180004861  jz      short loc_180004888
0x180004863  mov     dword ptr [rax+8], 0
0x18000486a  xorps   xmm0, xmm0
0x18000486d  xor     eax, eax
0x18000486f  movups  xmmword ptr [rbx+10h], xmm0
0x180004873  movups  xmmword ptr [rbx+20h], xmm0
0x180004877  mov     [rbx+30h], rax
0x18000487b  mov     [rbx+38h], al
0x18000487e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180004885  mov     [rbx], rax
0x180004888  mov     [rsp+68h+var_48], rbx
0x18000488d  jmp     short loc_1800048AD
0x18000488f  mov     r15, [rsp+68h+arg_10]
0x180004897  mov     r12, [rsp+68h+arg_8]
0x18000489c  mov     r14, [rsp+68h+arg_0]
0x1800048a1  mov     esi, [rsp+68h+arg_18]
0x1800048a8  mov     rbx, [rsp+68h+var_48]
0x1800048ad  test    rbx, rbx
0x1800048b0  jz      short loc_180004915
0x1800048b2  mov     [rbx+40h], r14
0x1800048b6  lea     rcx, [rbx+10h]; this
0x1800048ba  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800048bf  mov     esi, eax
0x1800048c1  lea     r14, [rbx+38h]
0x1800048c5  test    eax, eax
0x1800048c7  js      short loc_1800048E7
0x1800048c9  mov     byte ptr [r14], 1
0x1800048cd  mov     rax, [rbx]
0x1800048d0  mov     r8, r15
0x1800048d3  mov     rdx, r12
0x1800048d6  mov     rcx, rbx
0x1800048d9  mov     rax, [rax]
0x1800048dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e1  mov     esi, eax
0x1800048e3  test    eax, eax
0x1800048e5  jz      short loc_180004915
0x1800048e7  mov     dword ptr [rbx+8], 0C0000001h
0x1800048ee  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800048f5  mov     [rbx], rax
0x1800048f8  cmp     byte ptr [r14], 0
0x1800048fc  jz      short loc_18000490C
0x1800048fe  mov     byte ptr [r14], 0
0x180004902  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004906  call    cs:__imp_DeleteCriticalSection
0x18000490c  mov     rcx, rbx
0x18000490f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004915  mov     eax, esi
0x180004917  add     rsp, 38h
0x18000491b  pop     r15
0x18000491d  pop     r14
0x18000491f  pop     r13
0x180004921  pop     r12
0x180004923  pop     rsi
0x180004924  pop     rbx
0x180004925  retn
```
