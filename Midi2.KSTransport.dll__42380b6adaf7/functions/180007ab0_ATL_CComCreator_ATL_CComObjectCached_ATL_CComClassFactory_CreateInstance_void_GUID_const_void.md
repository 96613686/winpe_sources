# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180007ab0`
- end: `0x180007bc4`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004434`
- `0x180004460`
- `0x180007ab0`
- `0x180008a14`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007ba2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007ba2`

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
0x180007ab0  mov     [rsp+arg_10], r8
0x180007ab5  mov     [rsp+arg_8], rdx
0x180007aba  mov     [rsp+arg_0], rcx
0x180007abf  push    rbx
0x180007ac0  push    rsi
0x180007ac1  push    r12
0x180007ac3  push    r14
0x180007ac5  push    r15
0x180007ac7  sub     rsp, 30h
0x180007acb  mov     r14, r8
0x180007ace  mov     r12, rdx
0x180007ad1  mov     r15, rcx
0x180007ad4  test    r8, r8
0x180007ad7  jnz     short loc_180007AE3
0x180007ad9  mov     eax, 80004003h
0x180007ade  jmp     loc_180007BB7
0x180007ae3  mov     qword ptr [r8], 0
0x180007aea  mov     esi, 8007000Eh
0x180007aef  mov     [rsp+58h+arg_18], esi
0x180007af3  mov     [rsp+58h+var_38], 0
0x180007afc  mov     ecx, 48h ; 'H'; Size
0x180007b01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b06  mov     rbx, rax
0x180007b09  mov     dword ptr [rax+8], 0
0x180007b10  xorps   xmm0, xmm0
0x180007b13  xor     eax, eax
0x180007b15  movups  xmmword ptr [rbx+10h], xmm0
0x180007b19  movups  xmmword ptr [rbx+20h], xmm0
0x180007b1d  mov     [rbx+30h], rax
0x180007b21  mov     [rbx+38h], al
0x180007b24  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180007b2b  mov     [rbx], rax
0x180007b2e  mov     [rsp+58h+var_38], rbx
0x180007b33  jmp     short loc_180007B4D
0x180007b35  mov     r14, [rsp+58h+arg_10]
0x180007b3a  mov     r12, [rsp+58h+arg_8]
0x180007b3f  mov     r15, [rsp+58h+arg_0]
0x180007b44  mov     esi, [rsp+58h+arg_18]
0x180007b48  mov     rbx, [rsp+58h+var_38]
0x180007b4d  test    rbx, rbx
0x180007b50  jz      short loc_180007BB5
0x180007b52  mov     [rbx+40h], r15
0x180007b56  lea     rcx, [rbx+10h]; this
0x180007b5a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180007b5f  mov     esi, eax
0x180007b61  test    eax, eax
0x180007b63  js      short loc_180007B83
0x180007b65  mov     byte ptr [rbx+38h], 1
0x180007b69  mov     rax, [rbx]
0x180007b6c  mov     r8, r14
0x180007b6f  mov     rdx, r12
0x180007b72  mov     rcx, rbx
0x180007b75  mov     rax, [rax]
0x180007b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b7d  mov     esi, eax
0x180007b7f  test    eax, eax
0x180007b81  jz      short loc_180007BB5
0x180007b83  mov     dword ptr [rbx+8], 0C0000001h
0x180007b8a  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180007b91  mov     [rbx], rax
0x180007b94  cmp     byte ptr [rbx+38h], 0
0x180007b98  jz      short loc_180007BA8
0x180007b9a  mov     byte ptr [rbx+38h], 0
0x180007b9e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180007ba2  call    cs:__imp_DeleteCriticalSection
0x180007ba8  mov     edx, 48h ; 'H'
0x180007bad  mov     rcx, rbx; Block
0x180007bb0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007bb5  mov     eax, esi
0x180007bb7  add     rsp, 30h
0x180007bbb  pop     r15
0x180007bbd  pop     r14
0x180007bbf  pop     r12
0x180007bc1  pop     rsi
0x180007bc2  pop     rbx
0x180007bc3  retn
```
