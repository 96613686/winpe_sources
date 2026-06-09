# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004d70`
- end: `0x180004e84`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001f14`
- `0x180001f40`
- `0x180004d70`
- `0x180005bf8`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004e62`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004e62`

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
0x180004d70  mov     [rsp+arg_10], r8
0x180004d75  mov     [rsp+arg_8], rdx
0x180004d7a  mov     [rsp+arg_0], rcx
0x180004d7f  push    rbx
0x180004d80  push    rsi
0x180004d81  push    r12
0x180004d83  push    r14
0x180004d85  push    r15
0x180004d87  sub     rsp, 30h
0x180004d8b  mov     r14, r8
0x180004d8e  mov     r12, rdx
0x180004d91  mov     r15, rcx
0x180004d94  test    r8, r8
0x180004d97  jnz     short loc_180004DA3
0x180004d99  mov     eax, 80004003h
0x180004d9e  jmp     loc_180004E77
0x180004da3  mov     qword ptr [r8], 0
0x180004daa  mov     esi, 8007000Eh
0x180004daf  mov     [rsp+58h+arg_18], esi
0x180004db3  mov     [rsp+58h+var_38], 0
0x180004dbc  mov     ecx, 48h ; 'H'; Size
0x180004dc1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004dc6  mov     rbx, rax
0x180004dc9  mov     dword ptr [rax+8], 0
0x180004dd0  xorps   xmm0, xmm0
0x180004dd3  xor     eax, eax
0x180004dd5  movups  xmmword ptr [rbx+10h], xmm0
0x180004dd9  movups  xmmword ptr [rbx+20h], xmm0
0x180004ddd  mov     [rbx+30h], rax
0x180004de1  mov     [rbx+38h], al
0x180004de4  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180004deb  mov     [rbx], rax
0x180004dee  mov     [rsp+58h+var_38], rbx
0x180004df3  jmp     short loc_180004E0D
0x180004df5  mov     r14, [rsp+58h+arg_10]
0x180004dfa  mov     r12, [rsp+58h+arg_8]
0x180004dff  mov     r15, [rsp+58h+arg_0]
0x180004e04  mov     esi, [rsp+58h+arg_18]
0x180004e08  mov     rbx, [rsp+58h+var_38]
0x180004e0d  test    rbx, rbx
0x180004e10  jz      short loc_180004E75
0x180004e12  mov     [rbx+40h], r15
0x180004e16  lea     rcx, [rbx+10h]; this
0x180004e1a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004e1f  mov     esi, eax
0x180004e21  test    eax, eax
0x180004e23  js      short loc_180004E43
0x180004e25  mov     byte ptr [rbx+38h], 1
0x180004e29  mov     rax, [rbx]
0x180004e2c  mov     r8, r14
0x180004e2f  mov     rdx, r12
0x180004e32  mov     rcx, rbx
0x180004e35  mov     rax, [rax]
0x180004e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e3d  mov     esi, eax
0x180004e3f  test    eax, eax
0x180004e41  jz      short loc_180004E75
0x180004e43  mov     dword ptr [rbx+8], 0C0000001h
0x180004e4a  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004e51  mov     [rbx], rax
0x180004e54  cmp     byte ptr [rbx+38h], 0
0x180004e58  jz      short loc_180004E68
0x180004e5a  mov     byte ptr [rbx+38h], 0
0x180004e5e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004e62  call    cs:__imp_DeleteCriticalSection
0x180004e68  mov     edx, 48h ; 'H'
0x180004e6d  mov     rcx, rbx; Block
0x180004e70  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004e75  mov     eax, esi
0x180004e77  add     rsp, 30h
0x180004e7b  pop     r15
0x180004e7d  pop     r14
0x180004e7f  pop     r12
0x180004e81  pop     rsi
0x180004e82  pop     rbx
0x180004e83  retn
```
