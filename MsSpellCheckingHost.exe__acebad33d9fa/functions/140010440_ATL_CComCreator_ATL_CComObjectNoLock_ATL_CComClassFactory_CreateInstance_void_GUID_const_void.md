# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140010440`
- end: `0x140010566`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400014fc`
- `0x140003dfc`
- `0x140010440`
- `0x140013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14001054f`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001054f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140010546`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140010546`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(
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
      *(_QWORD *)v8 = &ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable';
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
0x140010440  mov     [rsp+arg_10], r8
0x140010445  mov     [rsp+arg_8], rdx
0x14001044a  mov     [rsp+arg_0], rcx
0x14001044f  push    rbx
0x140010450  push    rsi
0x140010451  push    r12
0x140010453  push    r13
0x140010455  push    r14
0x140010457  push    r15
0x140010459  sub     rsp, 38h
0x14001045d  mov     r15, r8
0x140010460  mov     r12, rdx
0x140010463  mov     r14, rcx
0x140010466  test    r8, r8
0x140010469  jnz     short loc_140010475
0x14001046b  mov     eax, 80004003h
0x140010470  jmp     loc_140010557
0x140010475  mov     qword ptr [r8], 0
0x14001047c  mov     esi, 8007000Eh
0x140010481  mov     [rsp+68h+arg_18], esi
0x140010488  mov     [rsp+68h+var_48], 0
0x140010491  mov     ecx, 48h ; 'H'; Size
0x140010496  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001049b  mov     rbx, rax
0x14001049e  test    rbx, rbx
0x1400104a1  jz      short loc_1400104C8
0x1400104a3  mov     dword ptr [rax+8], 0
0x1400104aa  xorps   xmm0, xmm0
0x1400104ad  xor     eax, eax
0x1400104af  movups  xmmword ptr [rbx+10h], xmm0
0x1400104b3  movups  xmmword ptr [rbx+20h], xmm0
0x1400104b7  mov     [rbx+30h], rax
0x1400104bb  mov     [rbx+38h], al
0x1400104be  lea     rax, ??_7?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable'
0x1400104c5  mov     [rbx], rax
0x1400104c8  mov     [rsp+68h+var_48], rbx
0x1400104cd  jmp     short loc_1400104ED
0x1400104cf  mov     r15, [rsp+68h+arg_10]
0x1400104d7  mov     r12, [rsp+68h+arg_8]
0x1400104dc  mov     r14, [rsp+68h+arg_0]
0x1400104e1  mov     esi, [rsp+68h+arg_18]
0x1400104e8  mov     rbx, [rsp+68h+var_48]
0x1400104ed  test    rbx, rbx
0x1400104f0  jz      short loc_140010555
0x1400104f2  mov     [rbx+40h], r14
0x1400104f6  lea     rcx, [rbx+10h]; this
0x1400104fa  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1400104ff  mov     esi, eax
0x140010501  lea     r14, [rbx+38h]
0x140010505  test    eax, eax
0x140010507  js      short loc_140010527
0x140010509  mov     byte ptr [r14], 1
0x14001050d  mov     rax, [rbx]
0x140010510  mov     r8, r15
0x140010513  mov     rdx, r12
0x140010516  mov     rcx, rbx
0x140010519  mov     rax, [rax]
0x14001051c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010521  mov     esi, eax
0x140010523  test    eax, eax
0x140010525  jz      short loc_140010555
0x140010527  mov     dword ptr [rbx+8], 0C0000001h
0x14001052e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x140010535  mov     [rbx], rax
0x140010538  cmp     byte ptr [r14], 0
0x14001053c  jz      short loc_14001054C
0x14001053e  mov     byte ptr [r14], 0
0x140010542  lea     rcx, [rbx+10h]; lpCriticalSection
0x140010546  call    cs:__imp_DeleteCriticalSection
0x14001054c  mov     rcx, rbx
0x14001054f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140010555  mov     eax, esi
0x140010557  add     rsp, 38h
0x14001055b  pop     r15
0x14001055d  pop     r14
0x14001055f  pop     r13
0x140010561  pop     r12
0x140010563  pop     rsi
0x140010564  pop     rbx
0x140010565  retn
```
