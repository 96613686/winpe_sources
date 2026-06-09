# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b0c0`
- end: `0x18000b19f`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1e8`
- `0x18000a7dc`
- `0x18000b0c0`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    *((_QWORD *)v9 + 3) = &CProviderDSO::`vftable'{for `IPersist'};
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIColumnsUpdateInfo>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b0c0  mov     [rsp+arg_0], rbx
0x18000b0c5  mov     [rsp+arg_8], rbp
0x18000b0ca  push    rsi
0x18000b0cb  push    rdi
0x18000b0cc  push    r12
0x18000b0ce  push    r14
0x18000b0d0  push    r15
0x18000b0d2  sub     rsp, 20h
0x18000b0d6  mov     r14, r8
0x18000b0d9  mov     r12, rdx
0x18000b0dc  mov     r15, rcx
0x18000b0df  test    r8, r8
0x18000b0e2  jnz     short loc_18000B0EE
0x18000b0e4  mov     eax, 80004003h
0x18000b0e9  jmp     loc_18000B188
0x18000b0ee  mov     qword ptr [r8], 0
0x18000b0f5  mov     ebp, 8007000Eh
0x18000b0fa  mov     ecx, 38h ; '8'; unsigned int
0x18000b0ff  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b104  mov     rsi, rax
0x18000b107  mov     [rsp+48h+arg_10], rax
0x18000b10c  test    rax, rax
0x18000b10f  jz      short loc_18000B15D
0x18000b111  mov     dword ptr [rax+8], 0
0x18000b118  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`vftable'
0x18000b11f  mov     [rsi], rax
0x18000b122  mov     rax, [r15]
0x18000b125  mov     rcx, r15
0x18000b128  mov     rax, [rax+20h]
0x18000b12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b131  mov     rdi, rax
0x18000b134  lea     rax, ??_7CProviderDSO@@6BIPersist@@@; const CProviderDSO::`vftable'{for `IPersist'}
0x18000b13b  mov     [rsi+18h], rax
0x18000b13f  lea     rcx, [rsi+20h]
0x18000b143  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b148  lea     rax, ??_7?$CComContainedObject@VCImpIColumnsUpdateInfo@@@ATL@@6B@; const ATL::CComContainedObject<CImpIColumnsUpdateInfo>::`vftable'
0x18000b14f  mov     [rsi+18h], rax
0x18000b153  mov     [rsi+20h], rdi
0x18000b157  mov     [rsi+30h], r15
0x18000b15b  jmp     short loc_18000B15F
0x18000b15d  xor     esi, esi
0x18000b15f  test    rsi, rsi
0x18000b162  jz      short loc_18000B186
0x18000b164  mov     rax, [rsi]
0x18000b167  mov     r8, r14
0x18000b16a  mov     rdx, r12
0x18000b16d  mov     rcx, rsi
0x18000b170  mov     rax, [rax]
0x18000b173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b178  mov     ebp, eax
0x18000b17a  test    eax, eax
0x18000b17c  jz      short loc_18000B186
0x18000b17e  mov     rcx, rsi; unsigned __int8 *
0x18000b181  call    ??_G?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`scalar deleting destructor'(uint)
0x18000b186  mov     eax, ebp
0x18000b188  mov     rbx, [rsp+48h+arg_0]
0x18000b18d  mov     rbp, [rsp+48h+arg_8]
0x18000b192  add     rsp, 20h
0x18000b196  pop     r15
0x18000b198  pop     r14
0x18000b19a  pop     r12
0x18000b19c  pop     rdi
0x18000b19d  pop     rsi
0x18000b19e  retn
```
