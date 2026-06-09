# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140003380`
- end: `0x1400034a5`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `293`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001a00`
- `0x140001a18`
- `0x140003380`
- `0x1400035bc`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003486`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003486`

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
0x140003380  mov     [rsp+arg_10], r8
0x140003385  mov     [rsp+arg_8], rdx
0x14000338a  mov     [rsp+arg_0], rcx
0x14000338f  push    rbx
0x140003390  push    rsi
0x140003391  push    r12
0x140003393  push    r13
0x140003395  push    r14
0x140003397  push    r15
0x140003399  sub     rsp, 38h
0x14000339d  mov     r15, r8
0x1400033a0  mov     r12, rdx
0x1400033a3  mov     r14, rcx
0x1400033a6  test    r8, r8
0x1400033a9  jnz     short loc_1400033B5
0x1400033ab  mov     eax, 80004003h
0x1400033b0  jmp     loc_140003496
0x1400033b5  mov     qword ptr [r8], 0
0x1400033bc  mov     esi, 8007000Eh
0x1400033c1  mov     [rsp+68h+arg_18], esi
0x1400033c8  mov     [rsp+68h+var_48], 0
0x1400033d1  mov     ecx, 48h ; 'H'; Size
0x1400033d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400033db  mov     rbx, rax
0x1400033de  test    rbx, rbx
0x1400033e1  jz      short loc_140003408
0x1400033e3  mov     dword ptr [rax+8], 0
0x1400033ea  xorps   xmm0, xmm0
0x1400033ed  xor     eax, eax
0x1400033ef  movups  xmmword ptr [rbx+10h], xmm0
0x1400033f3  movups  xmmword ptr [rbx+20h], xmm0
0x1400033f7  mov     [rbx+30h], rax
0x1400033fb  mov     [rbx+38h], al
0x1400033fe  lea     rax, ??_7?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable'
0x140003405  mov     [rbx], rax
0x140003408  mov     [rsp+68h+var_48], rbx
0x14000340d  jmp     short loc_14000342D
0x14000340f  mov     r15, [rsp+68h+arg_10]
0x140003417  mov     r12, [rsp+68h+arg_8]
0x14000341c  mov     r14, [rsp+68h+arg_0]
0x140003421  mov     esi, [rsp+68h+arg_18]
0x140003428  mov     rbx, [rsp+68h+var_48]
0x14000342d  test    rbx, rbx
0x140003430  jz      short loc_140003494
0x140003432  mov     [rbx+40h], r14
0x140003436  lea     rcx, [rbx+10h]; this
0x14000343a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x14000343f  mov     esi, eax
0x140003441  lea     r14, [rbx+38h]
0x140003445  test    eax, eax
0x140003447  js      short loc_140003467
0x140003449  mov     byte ptr [r14], 1
0x14000344d  mov     rax, [rbx]
0x140003450  mov     r8, r15
0x140003453  mov     rdx, r12
0x140003456  mov     rcx, rbx
0x140003459  mov     rax, [rax]
0x14000345c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003461  mov     esi, eax
0x140003463  test    eax, eax
0x140003465  jz      short loc_140003494
0x140003467  mov     dword ptr [rbx+8], 0C0000001h
0x14000346e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x140003475  mov     [rbx], rax
0x140003478  cmp     byte ptr [r14], 0
0x14000347c  jz      short loc_14000348C
0x14000347e  mov     byte ptr [r14], 0
0x140003482  lea     rcx, [rbx+10h]; lpCriticalSection
0x140003486  call    cs:__imp_DeleteCriticalSection
0x14000348c  mov     rcx, rbx; Block
0x14000348f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003494  mov     eax, esi
0x140003496  add     rsp, 38h
0x14000349a  pop     r15
0x14000349c  pop     r14
0x14000349e  pop     r13
0x1400034a0  pop     r12
0x1400034a2  pop     rsi
0x1400034a3  pop     rbx
0x1400034a4  retn
```
