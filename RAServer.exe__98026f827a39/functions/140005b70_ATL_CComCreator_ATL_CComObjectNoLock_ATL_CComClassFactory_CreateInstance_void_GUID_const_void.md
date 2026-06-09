# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140005b70`
- end: `0x140005c65`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400012d4`
- `0x140003f28`
- `0x140005b70`
- `0x140007304`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  __int64 v5; // r14
  unsigned int v7; // edi
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  int v10; // eax
  int v11; // ecx
  _QWORD *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x48u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      v8[6] = 0;
      *((_BYTE *)v8 + 56) = 0;
      *v8 = &ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable';
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v9[8] = v5;
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 2));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, v4, v3)) != 0 )
      ATL::CComObjectNoLock<ATL::CComClassFactory>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x140005b70  mov     [rsp+arg_10], r8
0x140005b75  mov     [rsp+arg_8], rdx
0x140005b7a  mov     [rsp+arg_0], rcx
0x140005b7f  push    rbx
0x140005b80  push    rsi
0x140005b81  push    rdi
0x140005b82  push    r14
0x140005b84  push    r15
0x140005b86  sub     rsp, 30h
0x140005b8a  mov     rsi, r8
0x140005b8d  mov     r15, rdx
0x140005b90  mov     r14, rcx
0x140005b93  test    r8, r8
0x140005b96  jnz     short loc_140005BA2
0x140005b98  mov     eax, 80004003h
0x140005b9d  jmp     loc_140005C59
0x140005ba2  mov     qword ptr [r8], 0
0x140005ba9  mov     edi, 8007000Eh
0x140005bae  mov     [rsp+58h+arg_18], edi
0x140005bb2  mov     [rsp+58h+var_38], 0
0x140005bbb  mov     ecx, 48h ; 'H'; Size
0x140005bc0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005bc5  mov     rbx, rax
0x140005bc8  test    rbx, rbx
0x140005bcb  jz      short loc_140005BF2
0x140005bcd  mov     dword ptr [rax+8], 0
0x140005bd4  xorps   xmm0, xmm0
0x140005bd7  xor     eax, eax
0x140005bd9  movups  xmmword ptr [rbx+10h], xmm0
0x140005bdd  movups  xmmword ptr [rbx+20h], xmm0
0x140005be1  mov     [rbx+30h], rax
0x140005be5  mov     [rbx+38h], al
0x140005be8  lea     rax, ??_7?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable'
0x140005bef  mov     [rbx], rax
0x140005bf2  mov     [rsp+58h+var_38], rbx
0x140005bf7  jmp     short loc_140005C11
0x140005bf9  mov     rsi, [rsp+58h+arg_10]
0x140005bfe  mov     r15, [rsp+58h+arg_8]
0x140005c03  mov     r14, [rsp+58h+arg_0]
0x140005c08  mov     edi, [rsp+58h+arg_18]
0x140005c0c  mov     rbx, [rsp+58h+var_38]
0x140005c11  test    rbx, rbx
0x140005c14  jz      short loc_140005C57
0x140005c16  mov     [rbx+40h], r14
0x140005c1a  lea     rcx, [rbx+10h]; this
0x140005c1e  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x140005c23  xor     ecx, ecx
0x140005c25  test    eax, eax
0x140005c27  cmovs   ecx, eax
0x140005c2a  xor     edi, edi
0x140005c2c  test    ecx, ecx
0x140005c2e  cmovs   edi, ecx
0x140005c31  test    edi, edi
0x140005c33  jnz     short loc_140005C4F
0x140005c35  mov     rax, [rbx]
0x140005c38  mov     r8, rsi
0x140005c3b  mov     rdx, r15
0x140005c3e  mov     rcx, rbx
0x140005c41  mov     rax, [rax]
0x140005c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c49  mov     edi, eax
0x140005c4b  test    eax, eax
0x140005c4d  jz      short loc_140005C57
0x140005c4f  mov     rcx, rbx
0x140005c52  call    ??_G?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectNoLock<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x140005c57  mov     eax, edi
0x140005c59  add     rsp, 30h
0x140005c5d  pop     r15
0x140005c5f  pop     r14
0x140005c61  pop     rdi
0x140005c62  pop     rsi
0x140005c63  pop     rbx
0x140005c64  retn
```
