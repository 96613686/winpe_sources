# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180007a10`
- end: `0x180007b16`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180006230`
- `0x180007a10`
- `0x18000c528`
- `0x18000f088`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x48u);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    *((_QWORD *)v8 + 8) = a1;
    v6 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 4));
    if ( v6 < 0
      || (*((_BYTE *)v8 + 56) = 1, (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0) )
    {
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v8);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007a10  mov     [rsp+arg_10], r8
0x180007a15  mov     [rsp+arg_8], rdx
0x180007a1a  mov     [rsp+arg_0], rcx
0x180007a1f  push    rbx
0x180007a20  push    rsi
0x180007a21  push    rdi
0x180007a22  push    r12
0x180007a24  push    r14
0x180007a26  push    r15
0x180007a28  sub     rsp, 38h
0x180007a2c  mov     rsi, r8
0x180007a2f  mov     r15, rdx
0x180007a32  mov     r14, rcx
0x180007a35  test    r8, r8
0x180007a38  jz      loc_180007AD9
0x180007a3e  xor     r12d, r12d
0x180007a41  mov     [r8], r12
0x180007a44  mov     edi, 8007000Eh
0x180007a49  mov     dword ptr [rsp+68h+arg_18], edi
0x180007a50  mov     [rsp+68h+var_48], r12
0x180007a55  mov     ecx, 48h ; 'H'; Size
0x180007a5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007a5f  mov     rbx, rax
0x180007a62  test    rax, rax
0x180007a65  jz      short loc_180007AD4
0x180007a67  mov     [rax+8], r12d
0x180007a6b  xorps   xmm0, xmm0
0x180007a6e  xor     eax, eax
0x180007a70  movups  xmmword ptr [rbx+10h], xmm0
0x180007a74  movups  xmmword ptr [rbx+20h], xmm0
0x180007a78  mov     [rbx+30h], rax
0x180007a7c  mov     [rbx+38h], al
0x180007a7f  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180007a86  mov     [rbx], rax
0x180007a89  mov     [rsp+68h+var_48], rbx
0x180007a8e  test    rbx, rbx
0x180007a91  jz      short loc_180007AC4
0x180007a93  mov     [rbx+40h], r14
0x180007a97  lea     rcx, [rbx+10h]; this
0x180007a9b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180007aa0  mov     edi, eax
0x180007aa2  test    eax, eax
0x180007aa4  js      short loc_180007B0C
0x180007aa6  mov     byte ptr [rbx+38h], 1
0x180007aaa  mov     rax, [rbx]
0x180007aad  mov     r8, rsi
0x180007ab0  mov     rdx, r15
0x180007ab3  mov     rcx, rbx
0x180007ab6  mov     rax, [rax]
0x180007ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007abe  mov     edi, eax
0x180007ac0  test    eax, eax
0x180007ac2  jnz     short loc_180007B0C
0x180007ac4  mov     eax, edi
0x180007ac6  add     rsp, 38h
0x180007aca  pop     r15
0x180007acc  pop     r14
0x180007ace  pop     r12
0x180007ad0  pop     rdi
0x180007ad1  pop     rsi
0x180007ad2  pop     rbx
0x180007ad3  retn
0x180007ad4  mov     rbx, r12
0x180007ad7  jmp     short loc_180007A89
0x180007ad9  mov     eax, 80004003h
0x180007ade  add     rsp, 38h
0x180007ae2  pop     r15
0x180007ae4  pop     r14
0x180007ae6  pop     r12
0x180007ae8  pop     rdi
0x180007ae9  pop     rsi
0x180007aea  pop     rbx
0x180007aeb  retn
0x180007aec  mov     rsi, [rsp+68h+arg_10]
0x180007af4  mov     r15, [rsp+68h+arg_8]
0x180007af9  mov     r14, [rsp+68h+arg_0]
0x180007afe  mov     edi, dword ptr [rsp+68h+arg_18]
0x180007b05  mov     rbx, [rsp+68h+var_48]
0x180007b0a  jmp     short loc_180007A8E
0x180007b0c  mov     rcx, rbx
0x180007b0f  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180007b14  jmp     short loc_180007AC4
```
