# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800095f0`
- end: `0x18000971a`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `298`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000137c`
- `0x180001c6c`
- `0x180008efc`
- `0x1800095f0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096f6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096f6`

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
0x1800095f0  mov     [rsp+arg_10], r8
0x1800095f5  mov     [rsp+arg_8], rdx
0x1800095fa  mov     [rsp+arg_0], rcx
0x1800095ff  push    rbx
0x180009600  push    rsi
0x180009601  push    r12
0x180009603  push    r13
0x180009605  push    r14
0x180009607  push    r15
0x180009609  sub     rsp, 38h
0x18000960d  mov     r15, r8
0x180009610  mov     r12, rdx
0x180009613  mov     r14, rcx
0x180009616  test    r8, r8
0x180009619  jnz     short loc_180009625
0x18000961b  mov     eax, 80004003h
0x180009620  jmp     loc_18000970B
0x180009625  mov     qword ptr [r8], 0
0x18000962c  mov     esi, 8007000Eh
0x180009631  mov     [rsp+68h+arg_18], esi
0x180009638  mov     [rsp+68h+var_48], 0
0x180009641  mov     ecx, 48h ; 'H'; Size
0x180009646  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000964b  mov     rbx, rax
0x18000964e  test    rbx, rbx
0x180009651  jz      short loc_180009678
0x180009653  mov     dword ptr [rax+8], 0
0x18000965a  xorps   xmm0, xmm0
0x18000965d  xor     eax, eax
0x18000965f  movups  xmmword ptr [rbx+10h], xmm0
0x180009663  movups  xmmword ptr [rbx+20h], xmm0
0x180009667  mov     [rbx+30h], rax
0x18000966b  mov     [rbx+38h], al
0x18000966e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180009675  mov     [rbx], rax
0x180009678  mov     [rsp+68h+var_48], rbx
0x18000967d  jmp     short loc_18000969D
0x18000967f  mov     r15, [rsp+68h+arg_10]
0x180009687  mov     r12, [rsp+68h+arg_8]
0x18000968c  mov     r14, [rsp+68h+arg_0]
0x180009691  mov     esi, [rsp+68h+arg_18]
0x180009698  mov     rbx, [rsp+68h+var_48]
0x18000969d  test    rbx, rbx
0x1800096a0  jz      short loc_180009709
0x1800096a2  mov     [rbx+40h], r14
0x1800096a6  lea     rcx, [rbx+10h]; this
0x1800096aa  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800096af  mov     esi, eax
0x1800096b1  lea     r14, [rbx+38h]
0x1800096b5  test    eax, eax
0x1800096b7  js      short loc_1800096D7
0x1800096b9  mov     byte ptr [r14], 1
0x1800096bd  mov     rax, [rbx]
0x1800096c0  mov     r8, r15
0x1800096c3  mov     rdx, r12
0x1800096c6  mov     rcx, rbx
0x1800096c9  mov     rax, [rax]
0x1800096cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096d1  mov     esi, eax
0x1800096d3  test    eax, eax
0x1800096d5  jz      short loc_180009709
0x1800096d7  mov     dword ptr [rbx+8], 0C0000001h
0x1800096de  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800096e5  mov     [rbx], rax
0x1800096e8  cmp     byte ptr [r14], 0
0x1800096ec  jz      short loc_1800096FC
0x1800096ee  mov     byte ptr [r14], 0
0x1800096f2  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800096f6  call    cs:__imp_DeleteCriticalSection
0x1800096fc  mov     edx, 48h ; 'H'
0x180009701  mov     rcx, rbx; Block
0x180009704  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009709  mov     eax, esi
0x18000970b  add     rsp, 38h
0x18000970f  pop     r15
0x180009711  pop     r14
0x180009713  pop     r13
0x180009715  pop     r12
0x180009717  pop     rsi
0x180009718  pop     rbx
0x180009719  retn
```
