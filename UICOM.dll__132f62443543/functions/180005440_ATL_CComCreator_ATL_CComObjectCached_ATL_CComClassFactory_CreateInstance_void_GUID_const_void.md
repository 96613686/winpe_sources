# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005440`
- end: `0x18000551a`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001170`
- `0x180001194`
- `0x1800038ac`
- `0x180005440`
- `0x180007010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800054fd`
- `KERNEL32!DeleteCriticalSection` at `0x1800054fd`

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
0x180005440  push    rbx
0x180005442  push    rbp
0x180005443  push    rsi
0x180005444  push    rdi
0x180005445  push    r14
0x180005447  push    r15
0x180005449  sub     rsp, 28h
0x18000544d  mov     r14, r8
0x180005450  mov     r15, rdx
0x180005453  mov     rdi, rcx
0x180005456  test    r8, r8
0x180005459  jnz     short loc_180005465
0x18000545b  mov     eax, 80004003h
0x180005460  jmp     loc_18000550D
0x180005465  mov     ecx, 48h ; 'H'; Size
0x18000546a  mov     qword ptr [r8], 0
0x180005471  mov     esi, 8007000Eh
0x180005476  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000547b  mov     rbx, rax
0x18000547e  test    rax, rax
0x180005481  jz      loc_18000550B
0x180005487  mov     dword ptr [rax+8], 0
0x18000548e  lea     rcx, [rbx+10h]; this
0x180005492  xor     eax, eax
0x180005494  xorps   xmm0, xmm0
0x180005497  movups  xmmword ptr [rbx+10h], xmm0
0x18000549b  movups  xmmword ptr [rbx+20h], xmm0
0x18000549f  mov     [rbx+30h], rax
0x1800054a3  mov     [rbx+38h], al
0x1800054a6  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800054ad  mov     [rbx], rax
0x1800054b0  mov     [rbx+40h], rdi
0x1800054b4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800054b9  lea     rdi, [rbx+38h]
0x1800054bd  mov     esi, eax
0x1800054bf  test    eax, eax
0x1800054c1  js      short loc_1800054E0
0x1800054c3  mov     byte ptr [rdi], 1
0x1800054c6  mov     r8, r14
0x1800054c9  mov     rax, [rbx]
0x1800054cc  mov     rdx, r15
0x1800054cf  mov     rcx, rbx
0x1800054d2  mov     rax, [rax]
0x1800054d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054da  mov     esi, eax
0x1800054dc  test    eax, eax
0x1800054de  jz      short loc_18000550B
0x1800054e0  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800054e7  mov     dword ptr [rbx+8], 0C0000001h
0x1800054ee  mov     [rbx], rax
0x1800054f1  cmp     byte ptr [rdi], 0
0x1800054f4  jz      short loc_180005503
0x1800054f6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800054fa  mov     byte ptr [rdi], 0
0x1800054fd  call    cs:__imp_DeleteCriticalSection
0x180005503  mov     rcx, rbx; Block
0x180005506  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000550b  mov     eax, esi
0x18000550d  add     rsp, 28h
0x180005511  pop     r15
0x180005513  pop     r14
0x180005515  pop     rdi
0x180005516  pop     rsi
0x180005517  pop     rbp
0x180005518  pop     rbx
0x180005519  retn
```
