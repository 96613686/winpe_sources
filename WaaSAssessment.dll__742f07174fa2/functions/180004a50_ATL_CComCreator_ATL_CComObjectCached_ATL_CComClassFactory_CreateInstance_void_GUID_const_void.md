# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004a50`
- end: `0x180004b76`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180004a50`
- `0x180004d6c`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004b5f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004b5f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004b56`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004b56`

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
0x180004a50  mov     [rsp+arg_10], r8
0x180004a55  mov     [rsp+arg_8], rdx
0x180004a5a  mov     [rsp+arg_0], rcx
0x180004a5f  push    rbx
0x180004a60  push    rsi
0x180004a61  push    r12
0x180004a63  push    r13
0x180004a65  push    r14
0x180004a67  push    r15
0x180004a69  sub     rsp, 38h
0x180004a6d  mov     r15, r8
0x180004a70  mov     r12, rdx
0x180004a73  mov     r14, rcx
0x180004a76  test    r8, r8
0x180004a79  jnz     short loc_180004A85
0x180004a7b  mov     eax, 80004003h
0x180004a80  jmp     loc_180004B67
0x180004a85  mov     qword ptr [r8], 0
0x180004a8c  mov     esi, 8007000Eh
0x180004a91  mov     [rsp+68h+arg_18], esi
0x180004a98  mov     [rsp+68h+var_48], 0
0x180004aa1  mov     ecx, 48h ; 'H'; Size
0x180004aa6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004aab  mov     rbx, rax
0x180004aae  test    rbx, rbx
0x180004ab1  jz      short loc_180004AD8
0x180004ab3  mov     dword ptr [rax+8], 0
0x180004aba  xorps   xmm0, xmm0
0x180004abd  xor     eax, eax
0x180004abf  movups  xmmword ptr [rbx+10h], xmm0
0x180004ac3  movups  xmmword ptr [rbx+20h], xmm0
0x180004ac7  mov     [rbx+30h], rax
0x180004acb  mov     [rbx+38h], al
0x180004ace  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180004ad5  mov     [rbx], rax
0x180004ad8  mov     [rsp+68h+var_48], rbx
0x180004add  jmp     short loc_180004AFD
0x180004adf  mov     r15, [rsp+68h+arg_10]
0x180004ae7  mov     r12, [rsp+68h+arg_8]
0x180004aec  mov     r14, [rsp+68h+arg_0]
0x180004af1  mov     esi, [rsp+68h+arg_18]
0x180004af8  mov     rbx, [rsp+68h+var_48]
0x180004afd  test    rbx, rbx
0x180004b00  jz      short loc_180004B65
0x180004b02  mov     [rbx+40h], r14
0x180004b06  lea     rcx, [rbx+10h]; this
0x180004b0a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004b0f  mov     esi, eax
0x180004b11  lea     r14, [rbx+38h]
0x180004b15  test    eax, eax
0x180004b17  js      short loc_180004B37
0x180004b19  mov     byte ptr [r14], 1
0x180004b1d  mov     rax, [rbx]
0x180004b20  mov     r8, r15
0x180004b23  mov     rdx, r12
0x180004b26  mov     rcx, rbx
0x180004b29  mov     rax, [rax]
0x180004b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b31  mov     esi, eax
0x180004b33  test    eax, eax
0x180004b35  jz      short loc_180004B65
0x180004b37  mov     dword ptr [rbx+8], 0C0000001h
0x180004b3e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004b45  mov     [rbx], rax
0x180004b48  cmp     byte ptr [r14], 0
0x180004b4c  jz      short loc_180004B5C
0x180004b4e  mov     byte ptr [r14], 0
0x180004b52  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004b56  call    cs:__imp_DeleteCriticalSection
0x180004b5c  mov     rcx, rbx
0x180004b5f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004b65  mov     eax, esi
0x180004b67  add     rsp, 38h
0x180004b6b  pop     r15
0x180004b6d  pop     r14
0x180004b6f  pop     r13
0x180004b71  pop     r12
0x180004b73  pop     rsi
0x180004b74  pop     rbx
0x180004b75  retn
```
