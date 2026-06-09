# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetUpdate>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b570`
- end: `0x18000b644`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIRowsetUpdate@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1e8`
- `0x18000a8b8`
- `0x18000b570`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetUpdate>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIRowsetUpdate>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b570  mov     [rsp+arg_0], rbx
0x18000b575  mov     [rsp+arg_8], rbp
0x18000b57a  push    rsi
0x18000b57b  push    rdi
0x18000b57c  push    r12
0x18000b57e  push    r14
0x18000b580  push    r15
0x18000b582  sub     rsp, 20h
0x18000b586  mov     r14, r8
0x18000b589  mov     r12, rdx
0x18000b58c  mov     r15, rcx
0x18000b58f  test    r8, r8
0x18000b592  jnz     short loc_18000B59E
0x18000b594  mov     eax, 80004003h
0x18000b599  jmp     loc_18000B62D
0x18000b59e  mov     qword ptr [r8], 0
0x18000b5a5  mov     ebp, 8007000Eh
0x18000b5aa  mov     ecx, 38h ; '8'; unsigned int
0x18000b5af  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b5b4  mov     rsi, rax
0x18000b5b7  mov     [rsp+48h+arg_10], rax
0x18000b5bc  test    rax, rax
0x18000b5bf  jz      short loc_18000B602
0x18000b5c1  mov     dword ptr [rax+8], 0
0x18000b5c8  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIRowsetUpdate@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`vftable'
0x18000b5cf  mov     [rsi], rax
0x18000b5d2  mov     rax, [r15]
0x18000b5d5  mov     rcx, r15
0x18000b5d8  mov     rax, [rax+20h]
0x18000b5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5e1  mov     rdi, rax
0x18000b5e4  lea     rcx, [rsi+20h]
0x18000b5e8  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b5ed  lea     rax, ??_7?$CComContainedObject@VCImpIRowsetUpdate@@@ATL@@6B@; const ATL::CComContainedObject<CImpIRowsetUpdate>::`vftable'
0x18000b5f4  mov     [rsi+18h], rax
0x18000b5f8  mov     [rsi+20h], rdi
0x18000b5fc  mov     [rsi+30h], r15
0x18000b600  jmp     short loc_18000B604
0x18000b602  xor     esi, esi
0x18000b604  test    rsi, rsi
0x18000b607  jz      short loc_18000B62B
0x18000b609  mov     rax, [rsi]
0x18000b60c  mov     r8, r14
0x18000b60f  mov     rdx, r12
0x18000b612  mov     rcx, rsi
0x18000b615  mov     rax, [rax]
0x18000b618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b61d  mov     ebp, eax
0x18000b61f  test    eax, eax
0x18000b621  jz      short loc_18000B62B
0x18000b623  mov     rcx, rsi; unsigned __int8 *
0x18000b626  call    ??_G?$CComCachedTearOffObject@VCImpIRowsetUpdate@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`scalar deleting destructor'(uint)
0x18000b62b  mov     eax, ebp
0x18000b62d  mov     rbx, [rsp+48h+arg_0]
0x18000b632  mov     rbp, [rsp+48h+arg_8]
0x18000b637  add     rsp, 20h
0x18000b63b  pop     r15
0x18000b63d  pop     r14
0x18000b63f  pop     r12
0x18000b641  pop     rdi
0x18000b642  pop     rsi
0x18000b643  retn
```
