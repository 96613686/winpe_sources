# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180011730`
- end: `0x18001180a`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001520`
- `0x18000152c`
- `0x180011730`
- `0x1800119c0`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800117ed`
- `KERNEL32!DeleteCriticalSection` at `0x1800117ed`

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
0x180011730  push    rbx
0x180011732  push    rbp
0x180011733  push    rsi
0x180011734  push    rdi
0x180011735  push    r14
0x180011737  push    r15
0x180011739  sub     rsp, 28h
0x18001173d  mov     r14, r8
0x180011740  mov     r15, rdx
0x180011743  mov     rdi, rcx
0x180011746  test    r8, r8
0x180011749  jnz     short loc_180011755
0x18001174b  mov     eax, 80004003h
0x180011750  jmp     loc_1800117FD
0x180011755  mov     ecx, 48h ; 'H'; Size
0x18001175a  mov     qword ptr [r8], 0
0x180011761  mov     esi, 8007000Eh
0x180011766  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001176b  mov     rbx, rax
0x18001176e  test    rax, rax
0x180011771  jz      loc_1800117FB
0x180011777  mov     dword ptr [rax+8], 0
0x18001177e  lea     rcx, [rbx+10h]; this
0x180011782  xor     eax, eax
0x180011784  xorps   xmm0, xmm0
0x180011787  movups  xmmword ptr [rbx+10h], xmm0
0x18001178b  movups  xmmword ptr [rbx+20h], xmm0
0x18001178f  mov     [rbx+30h], rax
0x180011793  mov     [rbx+38h], al
0x180011796  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18001179d  mov     [rbx], rax
0x1800117a0  mov     [rbx+40h], rdi
0x1800117a4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800117a9  lea     rdi, [rbx+38h]
0x1800117ad  mov     esi, eax
0x1800117af  test    eax, eax
0x1800117b1  js      short loc_1800117D0
0x1800117b3  mov     byte ptr [rdi], 1
0x1800117b6  mov     r8, r14
0x1800117b9  mov     rax, [rbx]
0x1800117bc  mov     rdx, r15
0x1800117bf  mov     rcx, rbx
0x1800117c2  mov     rax, [rax]
0x1800117c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117ca  mov     esi, eax
0x1800117cc  test    eax, eax
0x1800117ce  jz      short loc_1800117FB
0x1800117d0  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800117d7  mov     dword ptr [rbx+8], 0C0000001h
0x1800117de  mov     [rbx], rax
0x1800117e1  cmp     byte ptr [rdi], 0
0x1800117e4  jz      short loc_1800117F3
0x1800117e6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800117ea  mov     byte ptr [rdi], 0
0x1800117ed  call    cs:__imp_DeleteCriticalSection
0x1800117f3  mov     rcx, rbx; Block
0x1800117f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800117fb  mov     eax, esi
0x1800117fd  add     rsp, 28h
0x180011801  pop     r15
0x180011803  pop     r14
0x180011805  pop     rdi
0x180011806  pop     rsi
0x180011807  pop     rbp
0x180011808  pop     rbx
0x180011809  retn
```
