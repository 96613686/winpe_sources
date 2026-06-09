# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180008fe0`
- end: `0x1800090ba`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001790`
- `0x18000179c`
- `0x180005670`
- `0x180008fe0`
- `0x180017010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000909d`
- `KERNEL32!DeleteCriticalSection` at `0x18000909d`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // rdi

  if ( !a3 )
    return 2147500035LL;
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
    *((_QWORD *)v8 + 8) = a1;
    v10 = v8 + 56;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0) )
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
0x180008fe0  push    rbx
0x180008fe2  push    rbp
0x180008fe3  push    rsi
0x180008fe4  push    rdi
0x180008fe5  push    r14
0x180008fe7  push    r15
0x180008fe9  sub     rsp, 28h
0x180008fed  mov     r14, r8
0x180008ff0  mov     r15, rdx
0x180008ff3  mov     rdi, rcx
0x180008ff6  test    r8, r8
0x180008ff9  jnz     short loc_180009005
0x180008ffb  mov     eax, 80004003h
0x180009000  jmp     loc_1800090AD
0x180009005  mov     ecx, 48h ; 'H'; Size
0x18000900a  mov     qword ptr [r8], 0
0x180009011  mov     esi, 8007000Eh
0x180009016  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000901b  mov     rbx, rax
0x18000901e  test    rax, rax
0x180009021  jz      loc_1800090AB
0x180009027  mov     dword ptr [rax+8], 0
0x18000902e  lea     rcx, [rbx+10h]; this
0x180009032  xor     eax, eax
0x180009034  xorps   xmm0, xmm0
0x180009037  movups  xmmword ptr [rbx+10h], xmm0
0x18000903b  movups  xmmword ptr [rbx+20h], xmm0
0x18000903f  mov     [rbx+30h], rax
0x180009043  mov     [rbx+38h], al
0x180009046  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000904d  mov     [rbx], rax
0x180009050  mov     [rbx+40h], rdi
0x180009054  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180009059  lea     rdi, [rbx+38h]
0x18000905d  mov     esi, eax
0x18000905f  test    eax, eax
0x180009061  js      short loc_180009080
0x180009063  mov     byte ptr [rdi], 1
0x180009066  mov     r8, r14
0x180009069  mov     rax, [rbx]
0x18000906c  mov     rdx, r15
0x18000906f  mov     rcx, rbx
0x180009072  mov     rax, [rax]
0x180009075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000907a  mov     esi, eax
0x18000907c  test    eax, eax
0x18000907e  jz      short loc_1800090AB
0x180009080  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180009087  mov     dword ptr [rbx+8], 0C0000001h
0x18000908e  mov     [rbx], rax
0x180009091  cmp     byte ptr [rdi], 0
0x180009094  jz      short loc_1800090A3
0x180009096  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000909a  mov     byte ptr [rdi], 0
0x18000909d  call    cs:__imp_DeleteCriticalSection
0x1800090a3  mov     rcx, rbx; Block
0x1800090a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800090ab  mov     eax, esi
0x1800090ad  add     rsp, 28h
0x1800090b1  pop     r15
0x1800090b3  pop     r14
0x1800090b5  pop     rdi
0x1800090b6  pop     rsi
0x1800090b7  pop     rbp
0x1800090b8  pop     rbx
0x1800090b9  retn
```
