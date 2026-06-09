# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005430`
- end: `0x180005544`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002494`
- `0x1800024c0`
- `0x180005430`
- `0x1800062c0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005522`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005522`

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
0x180005430  mov     [rsp+arg_10], r8
0x180005435  mov     [rsp+arg_8], rdx
0x18000543a  mov     [rsp+arg_0], rcx
0x18000543f  push    rbx
0x180005440  push    rsi
0x180005441  push    r12
0x180005443  push    r14
0x180005445  push    r15
0x180005447  sub     rsp, 30h
0x18000544b  mov     r14, r8
0x18000544e  mov     r12, rdx
0x180005451  mov     r15, rcx
0x180005454  test    r8, r8
0x180005457  jnz     short loc_180005463
0x180005459  mov     eax, 80004003h
0x18000545e  jmp     loc_180005537
0x180005463  mov     qword ptr [r8], 0
0x18000546a  mov     esi, 8007000Eh
0x18000546f  mov     [rsp+58h+arg_18], esi
0x180005473  mov     [rsp+58h+var_38], 0
0x18000547c  mov     ecx, 48h ; 'H'; Size
0x180005481  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005486  mov     rbx, rax
0x180005489  mov     dword ptr [rax+8], 0
0x180005490  xorps   xmm0, xmm0
0x180005493  xor     eax, eax
0x180005495  movups  xmmword ptr [rbx+10h], xmm0
0x180005499  movups  xmmword ptr [rbx+20h], xmm0
0x18000549d  mov     [rbx+30h], rax
0x1800054a1  mov     [rbx+38h], al
0x1800054a4  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800054ab  mov     [rbx], rax
0x1800054ae  mov     [rsp+58h+var_38], rbx
0x1800054b3  jmp     short loc_1800054CD
0x1800054b5  mov     r14, [rsp+58h+arg_10]
0x1800054ba  mov     r12, [rsp+58h+arg_8]
0x1800054bf  mov     r15, [rsp+58h+arg_0]
0x1800054c4  mov     esi, [rsp+58h+arg_18]
0x1800054c8  mov     rbx, [rsp+58h+var_38]
0x1800054cd  test    rbx, rbx
0x1800054d0  jz      short loc_180005535
0x1800054d2  mov     [rbx+40h], r15
0x1800054d6  lea     rcx, [rbx+10h]; this
0x1800054da  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800054df  mov     esi, eax
0x1800054e1  test    eax, eax
0x1800054e3  js      short loc_180005503
0x1800054e5  mov     byte ptr [rbx+38h], 1
0x1800054e9  mov     rax, [rbx]
0x1800054ec  mov     r8, r14
0x1800054ef  mov     rdx, r12
0x1800054f2  mov     rcx, rbx
0x1800054f5  mov     rax, [rax]
0x1800054f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054fd  mov     esi, eax
0x1800054ff  test    eax, eax
0x180005501  jz      short loc_180005535
0x180005503  mov     dword ptr [rbx+8], 0C0000001h
0x18000550a  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180005511  mov     [rbx], rax
0x180005514  cmp     byte ptr [rbx+38h], 0
0x180005518  jz      short loc_180005528
0x18000551a  mov     byte ptr [rbx+38h], 0
0x18000551e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005522  call    cs:__imp_DeleteCriticalSection
0x180005528  mov     edx, 48h ; 'H'
0x18000552d  mov     rcx, rbx; Block
0x180005530  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005535  mov     eax, esi
0x180005537  add     rsp, 30h
0x18000553b  pop     r15
0x18000553d  pop     r14
0x18000553f  pop     r12
0x180005541  pop     rsi
0x180005542  pop     rbx
0x180005543  retn
```
