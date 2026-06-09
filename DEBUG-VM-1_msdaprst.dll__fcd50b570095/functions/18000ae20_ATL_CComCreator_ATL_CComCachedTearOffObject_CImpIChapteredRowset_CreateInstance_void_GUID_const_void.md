# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIChapteredRowset>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000ae20`
- end: `0x18000aef4`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1e8`
- `0x18000a758`
- `0x18000ae20`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIChapteredRowset>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebp
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rsi
  __int64 v10; // rdi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = MMMAlloc(0x38u, a2);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIChapteredRowset>::`vftable';
    *((_QWORD *)v9 + 4) = v10;
    *((_QWORD *)v9 + 6) = a1;
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v7 = (**(__int64 (__fastcall ***)(unsigned __int8 *, __int64, _QWORD *))v9)(v9, a2, a3);
    if ( v7 )
      ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000ae20  mov     [rsp+arg_0], rbx
0x18000ae25  mov     [rsp+arg_8], rbp
0x18000ae2a  push    rsi
0x18000ae2b  push    rdi
0x18000ae2c  push    r12
0x18000ae2e  push    r14
0x18000ae30  push    r15
0x18000ae32  sub     rsp, 20h
0x18000ae36  mov     r14, r8
0x18000ae39  mov     r12, rdx
0x18000ae3c  mov     r15, rcx
0x18000ae3f  test    r8, r8
0x18000ae42  jnz     short loc_18000AE4E
0x18000ae44  mov     eax, 80004003h
0x18000ae49  jmp     loc_18000AEDD
0x18000ae4e  mov     qword ptr [r8], 0
0x18000ae55  mov     ebp, 8007000Eh
0x18000ae5a  mov     ecx, 38h ; '8'; unsigned int
0x18000ae5f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000ae64  mov     rsi, rax
0x18000ae67  mov     [rsp+48h+arg_10], rax
0x18000ae6c  test    rax, rax
0x18000ae6f  jz      short loc_18000AEB2
0x18000ae71  mov     dword ptr [rax+8], 0
0x18000ae78  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`vftable'
0x18000ae7f  mov     [rsi], rax
0x18000ae82  mov     rax, [r15]
0x18000ae85  mov     rcx, r15
0x18000ae88  mov     rax, [rax+20h]
0x18000ae8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae91  mov     rdi, rax
0x18000ae94  lea     rcx, [rsi+20h]
0x18000ae98  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000ae9d  lea     rax, ??_7?$CComContainedObject@VCImpIChapteredRowset@@@ATL@@6B@; const ATL::CComContainedObject<CImpIChapteredRowset>::`vftable'
0x18000aea4  mov     [rsi+18h], rax
0x18000aea8  mov     [rsi+20h], rdi
0x18000aeac  mov     [rsi+30h], r15
0x18000aeb0  jmp     short loc_18000AEB4
0x18000aeb2  xor     esi, esi
0x18000aeb4  test    rsi, rsi
0x18000aeb7  jz      short loc_18000AEDB
0x18000aeb9  mov     rax, [rsi]
0x18000aebc  mov     r8, r14
0x18000aebf  mov     rdx, r12
0x18000aec2  mov     rcx, rsi
0x18000aec5  mov     rax, [rax]
0x18000aec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aecd  mov     ebp, eax
0x18000aecf  test    eax, eax
0x18000aed1  jz      short loc_18000AEDB
0x18000aed3  mov     rcx, rsi; unsigned __int8 *
0x18000aed6  call    ??_G?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`scalar deleting destructor'(uint)
0x18000aedb  mov     eax, ebp
0x18000aedd  mov     rbx, [rsp+48h+arg_0]
0x18000aee2  mov     rbp, [rsp+48h+arg_8]
0x18000aee7  add     rsp, 20h
0x18000aeeb  pop     r15
0x18000aeed  pop     r14
0x18000aeef  pop     r12
0x18000aef1  pop     rdi
0x18000aef2  pop     rsi
0x18000aef3  retn
```
