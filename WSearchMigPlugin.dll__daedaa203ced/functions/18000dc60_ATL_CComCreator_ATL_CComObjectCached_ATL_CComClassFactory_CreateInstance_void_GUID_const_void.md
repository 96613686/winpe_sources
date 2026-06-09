# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000dc60`
- end: `0x18000dd7c`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002b9c`
- `0x180002c0c`
- `0x18000b69c`
- `0x18000dc60`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dd5a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dd5a`

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
0x18000dc60  mov     rax, rsp
0x18000dc63  mov     [rax+18h], r8
0x18000dc67  mov     [rax+10h], rdx
0x18000dc6b  mov     [rax+8], rcx
0x18000dc6f  push    rbx
0x18000dc70  push    rsi
0x18000dc71  push    r12
0x18000dc73  push    r14
0x18000dc75  push    r15
0x18000dc77  sub     rsp, 30h
0x18000dc7b  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x18000dc83  mov     r14, r8
0x18000dc86  mov     r12, rdx
0x18000dc89  mov     r15, rcx
0x18000dc8c  test    r8, r8
0x18000dc8f  jnz     short loc_18000DC9B
0x18000dc91  mov     eax, 80004003h
0x18000dc96  jmp     loc_18000DD6F
0x18000dc9b  mov     qword ptr [r8], 0
0x18000dca2  mov     esi, 8007000Eh
0x18000dca7  mov     [rsp+58h+arg_18], esi
0x18000dcab  mov     [rsp+58h+var_38], 0
0x18000dcb4  mov     ecx, 48h ; 'H'; Size
0x18000dcb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dcbe  mov     rbx, rax
0x18000dcc1  mov     dword ptr [rax+8], 0
0x18000dcc8  xorps   xmm0, xmm0
0x18000dccb  xor     eax, eax
0x18000dccd  movups  xmmword ptr [rbx+10h], xmm0
0x18000dcd1  movups  xmmword ptr [rbx+20h], xmm0
0x18000dcd5  mov     [rbx+30h], rax
0x18000dcd9  mov     [rbx+38h], al
0x18000dcdc  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000dce3  mov     [rbx], rax
0x18000dce6  mov     [rsp+58h+var_38], rbx
0x18000dceb  jmp     short loc_18000DD05
0x18000dced  mov     r14, [rsp+58h+arg_10]
0x18000dcf2  mov     r12, [rsp+58h+arg_8]
0x18000dcf7  mov     r15, [rsp+58h+arg_0]
0x18000dcfc  mov     esi, [rsp+58h+arg_18]
0x18000dd00  mov     rbx, [rsp+58h+var_38]
0x18000dd05  test    rbx, rbx
0x18000dd08  jz      short loc_18000DD6D
0x18000dd0a  mov     [rbx+40h], r15
0x18000dd0e  lea     rcx, [rbx+10h]; this
0x18000dd12  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000dd17  mov     esi, eax
0x18000dd19  test    eax, eax
0x18000dd1b  js      short loc_18000DD3B
0x18000dd1d  mov     byte ptr [rbx+38h], 1
0x18000dd21  mov     rax, [rbx]
0x18000dd24  mov     r8, r14
0x18000dd27  mov     rdx, r12
0x18000dd2a  mov     rcx, rbx
0x18000dd2d  mov     rax, [rax]
0x18000dd30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd35  mov     esi, eax
0x18000dd37  test    eax, eax
0x18000dd39  jz      short loc_18000DD6D
0x18000dd3b  mov     dword ptr [rbx+8], 0C0000001h
0x18000dd42  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000dd49  mov     [rbx], rax
0x18000dd4c  cmp     byte ptr [rbx+38h], 0
0x18000dd50  jz      short loc_18000DD60
0x18000dd52  mov     byte ptr [rbx+38h], 0
0x18000dd56  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000dd5a  call    cs:__imp_DeleteCriticalSection
0x18000dd60  mov     edx, 48h ; 'H'
0x18000dd65  mov     rcx, rbx; Block
0x18000dd68  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dd6d  mov     eax, esi
0x18000dd6f  add     rsp, 30h
0x18000dd73  pop     r15
0x18000dd75  pop     r14
0x18000dd77  pop     r12
0x18000dd79  pop     rsi
0x18000dd7a  pop     rbx
0x18000dd7b  retn
```
