# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004e80`
- end: `0x180004f94`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002024`
- `0x180002050`
- `0x180004e80`
- `0x180005d08`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004f72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004f72`

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
0x180004e80  mov     [rsp+arg_10], r8
0x180004e85  mov     [rsp+arg_8], rdx
0x180004e8a  mov     [rsp+arg_0], rcx
0x180004e8f  push    rbx
0x180004e90  push    rsi
0x180004e91  push    r12
0x180004e93  push    r14
0x180004e95  push    r15
0x180004e97  sub     rsp, 30h
0x180004e9b  mov     r14, r8
0x180004e9e  mov     r12, rdx
0x180004ea1  mov     r15, rcx
0x180004ea4  test    r8, r8
0x180004ea7  jnz     short loc_180004EB3
0x180004ea9  mov     eax, 80004003h
0x180004eae  jmp     loc_180004F87
0x180004eb3  mov     qword ptr [r8], 0
0x180004eba  mov     esi, 8007000Eh
0x180004ebf  mov     [rsp+58h+arg_18], esi
0x180004ec3  mov     [rsp+58h+var_38], 0
0x180004ecc  mov     ecx, 48h ; 'H'; Size
0x180004ed1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004ed6  mov     rbx, rax
0x180004ed9  mov     dword ptr [rax+8], 0
0x180004ee0  xorps   xmm0, xmm0
0x180004ee3  xor     eax, eax
0x180004ee5  movups  xmmword ptr [rbx+10h], xmm0
0x180004ee9  movups  xmmword ptr [rbx+20h], xmm0
0x180004eed  mov     [rbx+30h], rax
0x180004ef1  mov     [rbx+38h], al
0x180004ef4  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180004efb  mov     [rbx], rax
0x180004efe  mov     [rsp+58h+var_38], rbx
0x180004f03  jmp     short loc_180004F1D
0x180004f05  mov     r14, [rsp+58h+arg_10]
0x180004f0a  mov     r12, [rsp+58h+arg_8]
0x180004f0f  mov     r15, [rsp+58h+arg_0]
0x180004f14  mov     esi, [rsp+58h+arg_18]
0x180004f18  mov     rbx, [rsp+58h+var_38]
0x180004f1d  test    rbx, rbx
0x180004f20  jz      short loc_180004F85
0x180004f22  mov     [rbx+40h], r15
0x180004f26  lea     rcx, [rbx+10h]; this
0x180004f2a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004f2f  mov     esi, eax
0x180004f31  test    eax, eax
0x180004f33  js      short loc_180004F53
0x180004f35  mov     byte ptr [rbx+38h], 1
0x180004f39  mov     rax, [rbx]
0x180004f3c  mov     r8, r14
0x180004f3f  mov     rdx, r12
0x180004f42  mov     rcx, rbx
0x180004f45  mov     rax, [rax]
0x180004f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4d  mov     esi, eax
0x180004f4f  test    eax, eax
0x180004f51  jz      short loc_180004F85
0x180004f53  mov     dword ptr [rbx+8], 0C0000001h
0x180004f5a  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004f61  mov     [rbx], rax
0x180004f64  cmp     byte ptr [rbx+38h], 0
0x180004f68  jz      short loc_180004F78
0x180004f6a  mov     byte ptr [rbx+38h], 0
0x180004f6e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004f72  call    cs:__imp_DeleteCriticalSection
0x180004f78  mov     edx, 48h ; 'H'
0x180004f7d  mov     rcx, rbx; Block
0x180004f80  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004f85  mov     eax, esi
0x180004f87  add     rsp, 30h
0x180004f8b  pop     r15
0x180004f8d  pop     r14
0x180004f8f  pop     r12
0x180004f91  pop     rsi
0x180004f92  pop     rbx
0x180004f93  retn
```
