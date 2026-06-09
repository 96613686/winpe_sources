# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIUpdateInfo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b650`
- end: `0x18000b72f`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIUpdateInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1e8`
- `0x18000a8e4`
- `0x18000b650`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIUpdateInfo>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    *((_QWORD *)v9 + 3) = &IUpdateInfo::`vftable';
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIUpdateInfo>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b650  mov     [rsp+arg_0], rbx
0x18000b655  mov     [rsp+arg_8], rbp
0x18000b65a  push    rsi
0x18000b65b  push    rdi
0x18000b65c  push    r12
0x18000b65e  push    r14
0x18000b660  push    r15
0x18000b662  sub     rsp, 20h
0x18000b666  mov     r14, r8
0x18000b669  mov     r12, rdx
0x18000b66c  mov     r15, rcx
0x18000b66f  test    r8, r8
0x18000b672  jnz     short loc_18000B67E
0x18000b674  mov     eax, 80004003h
0x18000b679  jmp     loc_18000B718
0x18000b67e  mov     qword ptr [r8], 0
0x18000b685  mov     ebp, 8007000Eh
0x18000b68a  mov     ecx, 38h ; '8'; unsigned int
0x18000b68f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b694  mov     rsi, rax
0x18000b697  mov     [rsp+48h+arg_10], rax
0x18000b69c  test    rax, rax
0x18000b69f  jz      short loc_18000B6ED
0x18000b6a1  mov     dword ptr [rax+8], 0
0x18000b6a8  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIUpdateInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`vftable'
0x18000b6af  mov     [rsi], rax
0x18000b6b2  mov     rax, [r15]
0x18000b6b5  mov     rcx, r15
0x18000b6b8  mov     rax, [rax+20h]
0x18000b6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6c1  mov     rdi, rax
0x18000b6c4  lea     rax, ??_7IUpdateInfo@@6B@; const IUpdateInfo::`vftable'
0x18000b6cb  mov     [rsi+18h], rax
0x18000b6cf  lea     rcx, [rsi+20h]
0x18000b6d3  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b6d8  lea     rax, ??_7?$CComContainedObject@VCImpIUpdateInfo@@@ATL@@6B@; const ATL::CComContainedObject<CImpIUpdateInfo>::`vftable'
0x18000b6df  mov     [rsi+18h], rax
0x18000b6e3  mov     [rsi+20h], rdi
0x18000b6e7  mov     [rsi+30h], r15
0x18000b6eb  jmp     short loc_18000B6EF
0x18000b6ed  xor     esi, esi
0x18000b6ef  test    rsi, rsi
0x18000b6f2  jz      short loc_18000B716
0x18000b6f4  mov     rax, [rsi]
0x18000b6f7  mov     r8, r14
0x18000b6fa  mov     rdx, r12
0x18000b6fd  mov     rcx, rsi
0x18000b700  mov     rax, [rax]
0x18000b703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b708  mov     ebp, eax
0x18000b70a  test    eax, eax
0x18000b70c  jz      short loc_18000B716
0x18000b70e  mov     rcx, rsi; unsigned __int8 *
0x18000b711  call    ??_G?$CComCachedTearOffObject@VCImpIUpdateInfo@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`scalar deleting destructor'(uint)
0x18000b716  mov     eax, ebp
0x18000b718  mov     rbx, [rsp+48h+arg_0]
0x18000b71d  mov     rbp, [rsp+48h+arg_8]
0x18000b722  add     rsp, 20h
0x18000b726  pop     r15
0x18000b728  pop     r14
0x18000b72a  pop     r12
0x18000b72c  pop     rdi
0x18000b72d  pop     rsi
0x18000b72e  retn
```
