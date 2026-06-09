# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsInfo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000af00`
- end: `0x18000afd4`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1e8`
- `0x18000a784`
- `0x18000af00`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsInfo>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIColumnsInfo>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000af00  mov     [rsp+arg_0], rbx
0x18000af05  mov     [rsp+arg_8], rbp
0x18000af0a  push    rsi
0x18000af0b  push    rdi
0x18000af0c  push    r12
0x18000af0e  push    r14
0x18000af10  push    r15
0x18000af12  sub     rsp, 20h
0x18000af16  mov     r14, r8
0x18000af19  mov     r12, rdx
0x18000af1c  mov     r15, rcx
0x18000af1f  test    r8, r8
0x18000af22  jnz     short loc_18000AF2E
0x18000af24  mov     eax, 80004003h
0x18000af29  jmp     loc_18000AFBD
0x18000af2e  mov     qword ptr [r8], 0
0x18000af35  mov     ebp, 8007000Eh
0x18000af3a  mov     ecx, 38h ; '8'; unsigned int
0x18000af3f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000af44  mov     rsi, rax
0x18000af47  mov     [rsp+48h+arg_10], rax
0x18000af4c  test    rax, rax
0x18000af4f  jz      short loc_18000AF92
0x18000af51  mov     dword ptr [rax+8], 0
0x18000af58  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`vftable'
0x18000af5f  mov     [rsi], rax
0x18000af62  mov     rax, [r15]
0x18000af65  mov     rcx, r15
0x18000af68  mov     rax, [rax+20h]
0x18000af6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af71  mov     rdi, rax
0x18000af74  lea     rcx, [rsi+20h]
0x18000af78  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000af7d  lea     rax, ??_7?$CComContainedObject@VCImpIColumnsInfo@@@ATL@@6B@; const ATL::CComContainedObject<CImpIColumnsInfo>::`vftable'
0x18000af84  mov     [rsi+18h], rax
0x18000af88  mov     [rsi+20h], rdi
0x18000af8c  mov     [rsi+30h], r15
0x18000af90  jmp     short loc_18000AF94
0x18000af92  xor     esi, esi
0x18000af94  test    rsi, rsi
0x18000af97  jz      short loc_18000AFBB
0x18000af99  mov     rax, [rsi]
0x18000af9c  mov     r8, r14
0x18000af9f  mov     rdx, r12
0x18000afa2  mov     rcx, rsi
0x18000afa5  mov     rax, [rax]
0x18000afa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afad  mov     ebp, eax
0x18000afaf  test    eax, eax
0x18000afb1  jz      short loc_18000AFBB
0x18000afb3  mov     rcx, rsi; unsigned __int8 *
0x18000afb6  call    ??_G?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`scalar deleting destructor'(uint)
0x18000afbb  mov     eax, ebp
0x18000afbd  mov     rbx, [rsp+48h+arg_0]
0x18000afc2  mov     rbp, [rsp+48h+arg_8]
0x18000afc7  add     rsp, 20h
0x18000afcb  pop     r15
0x18000afcd  pop     r14
0x18000afcf  pop     r12
0x18000afd1  pop     rdi
0x18000afd2  pop     rsi
0x18000afd3  retn
```
