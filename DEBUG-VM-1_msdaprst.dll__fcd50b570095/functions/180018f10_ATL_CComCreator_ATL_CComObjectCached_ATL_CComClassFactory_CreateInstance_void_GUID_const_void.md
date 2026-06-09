# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180018f10`
- end: `0x180018fb1`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1c0`
- `0x180018740`
- `0x180018f10`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = MMMAlloc(0x20u, a2);
  v9 = v8;
  if ( v8 )
  {
    ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)v8 + 2);
    *(_QWORD *)v9 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 3) = a1;
    v7 = (**(__int64 (__fastcall ***)(unsigned __int8 *, __int64, _QWORD *))v9)(v9, a2, a3);
    if ( v7 )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x180018f10  mov     [rsp+arg_0], rbx
0x180018f15  mov     [rsp+arg_8], rbp
0x180018f1a  push    rsi
0x180018f1b  push    rdi
0x180018f1c  push    r14
0x180018f1e  sub     rsp, 20h
0x180018f22  mov     rdi, r8
0x180018f25  mov     rbp, rdx
0x180018f28  mov     r14, rcx
0x180018f2b  test    r8, r8
0x180018f2e  jnz     short loc_180018F37
0x180018f30  mov     eax, 80004003h
0x180018f35  jmp     short loc_180018F9E
0x180018f37  mov     qword ptr [r8], 0
0x180018f3e  mov     esi, 8007000Eh
0x180018f43  mov     ecx, 20h ; ' '; unsigned int
0x180018f48  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180018f4d  mov     rbx, rax
0x180018f50  mov     [rsp+38h+arg_10], rax
0x180018f55  test    rax, rax
0x180018f58  jz      short loc_180018F6F
0x180018f5a  lea     rcx, [rax+8]
0x180018f5e  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x180018f63  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180018f6a  mov     [rbx], rax
0x180018f6d  jmp     short loc_180018F71
0x180018f6f  xor     ebx, ebx
0x180018f71  test    rbx, rbx
0x180018f74  jz      short loc_180018F9C
0x180018f76  mov     [rbx+18h], r14
0x180018f7a  mov     rax, [rbx]
0x180018f7d  mov     r8, rdi
0x180018f80  mov     rdx, rbp
0x180018f83  mov     rcx, rbx
0x180018f86  mov     rax, [rax]
0x180018f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f8e  mov     esi, eax
0x180018f90  test    eax, eax
0x180018f92  jz      short loc_180018F9C
0x180018f94  mov     rcx, rbx; unsigned __int8 *
0x180018f97  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180018f9c  mov     eax, esi
0x180018f9e  mov     rbx, [rsp+38h+arg_0]
0x180018fa3  mov     rbp, [rsp+38h+arg_8]
0x180018fa8  add     rsp, 20h
0x180018fac  pop     r14
0x180018fae  pop     rdi
0x180018faf  pop     rsi
0x180018fb0  retn
```
