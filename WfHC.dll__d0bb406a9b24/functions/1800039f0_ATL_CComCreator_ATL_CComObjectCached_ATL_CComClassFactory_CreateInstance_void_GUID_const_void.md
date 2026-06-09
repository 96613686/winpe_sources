# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800039f0`
- end: `0x180003af9`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `265`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001250`
- `0x180002b00`
- `0x1800039f0`
- `0x180004370`
- `0x18000e010`

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
  unsigned int v7; // edi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  int v10; // ecx
  int v11; // eax
  _DWORD *v12; // [rsp+20h] [rbp-38h]

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
      v8[2] = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      *((_BYTE *)v8 + 56) = 0;
      *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
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
    *((_QWORD *)v9 + 8) = v5;
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 4));
    if ( v10 >= 0 )
      *((_BYTE *)v9 + 56) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x1800039f0  mov     [rsp+arg_10], r8
0x1800039f5  mov     [rsp+arg_8], rdx
0x1800039fa  mov     [rsp+arg_0], rcx
0x1800039ff  push    rbx
0x180003a00  push    rdi
0x180003a01  push    r12
0x180003a03  push    r14
0x180003a05  push    r15
0x180003a07  sub     rsp, 30h
0x180003a0b  mov     r14, r8
0x180003a0e  mov     r12, rdx
0x180003a11  mov     r15, rcx
0x180003a14  test    r8, r8
0x180003a17  jnz     short loc_180003A2B
0x180003a19  mov     eax, 80004003h
0x180003a1e  add     rsp, 30h
0x180003a22  pop     r15
0x180003a24  pop     r14
0x180003a26  pop     r12
0x180003a28  pop     rdi
0x180003a29  pop     rbx
0x180003a2a  retn
0x180003a2b  mov     qword ptr [r8], 0
0x180003a32  mov     edi, 8007000Eh
0x180003a37  mov     [rsp+58h+arg_18], edi
0x180003a3b  mov     [rsp+58h+var_38], 0
0x180003a44  mov     ecx, 48h ; 'H'; Size
0x180003a49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a4e  mov     rbx, rax
0x180003a51  test    rbx, rbx
0x180003a54  jz      short loc_180003A7B
0x180003a56  mov     dword ptr [rax+8], 0
0x180003a5d  xorps   xmm0, xmm0
0x180003a60  xor     eax, eax
0x180003a62  movups  xmmword ptr [rbx+10h], xmm0
0x180003a66  movups  xmmword ptr [rbx+20h], xmm0
0x180003a6a  mov     [rbx+30h], rax
0x180003a6e  mov     [rbx+38h], al
0x180003a71  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180003a78  mov     [rbx], rax
0x180003a7b  mov     [rsp+58h+var_38], rbx
0x180003a80  jmp     short loc_180003A9A
0x180003a82  mov     r14, [rsp+58h+arg_10]
0x180003a87  mov     r12, [rsp+58h+arg_8]
0x180003a8c  mov     r15, [rsp+58h+arg_0]
0x180003a91  mov     edi, [rsp+58h+arg_18]
0x180003a95  mov     rbx, [rsp+58h+var_38]
0x180003a9a  test    rbx, rbx
0x180003a9d  jz      short loc_180003AEA
0x180003a9f  mov     [rbx+40h], r15
0x180003aa3  lea     rcx, [rbx+10h]; this
0x180003aa7  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003aac  mov     ecx, eax
0x180003aae  test    eax, eax
0x180003ab0  js      short loc_180003AB6
0x180003ab2  mov     byte ptr [rbx+38h], 1
0x180003ab6  xor     eax, eax
0x180003ab8  test    ecx, ecx
0x180003aba  cmovs   eax, ecx
0x180003abd  xor     edi, edi
0x180003abf  test    eax, eax
0x180003ac1  cmovs   edi, eax
0x180003ac4  test    edi, edi
0x180003ac6  jnz     short loc_180003AE2
0x180003ac8  mov     rax, [rbx]
0x180003acb  mov     r8, r14
0x180003ace  mov     rdx, r12
0x180003ad1  mov     rcx, rbx
0x180003ad4  mov     rax, [rax]
0x180003ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003adc  mov     edi, eax
0x180003ade  test    eax, eax
0x180003ae0  jz      short loc_180003AEA
0x180003ae2  mov     rcx, rbx
0x180003ae5  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180003aea  mov     eax, edi
0x180003aec  add     rsp, 30h
0x180003af0  pop     r15
0x180003af2  pop     r14
0x180003af4  pop     r12
0x180003af6  pop     rdi
0x180003af7  pop     rbx
0x180003af8  retn
```
