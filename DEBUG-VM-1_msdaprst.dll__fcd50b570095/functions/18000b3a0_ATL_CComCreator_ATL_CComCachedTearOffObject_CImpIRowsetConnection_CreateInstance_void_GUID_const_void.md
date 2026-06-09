# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetConnection>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b3a0`
- end: `0x18000b47f`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIRowsetConnection@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1e8`
- `0x18000a860`
- `0x18000b3a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetConnection>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    *((_QWORD *)v9 + 3) = &IRowsetConnection::`vftable';
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIRowsetConnection>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b3a0  mov     [rsp+arg_0], rbx
0x18000b3a5  mov     [rsp+arg_8], rbp
0x18000b3aa  push    rsi
0x18000b3ab  push    rdi
0x18000b3ac  push    r12
0x18000b3ae  push    r14
0x18000b3b0  push    r15
0x18000b3b2  sub     rsp, 20h
0x18000b3b6  mov     r14, r8
0x18000b3b9  mov     r12, rdx
0x18000b3bc  mov     r15, rcx
0x18000b3bf  test    r8, r8
0x18000b3c2  jnz     short loc_18000B3CE
0x18000b3c4  mov     eax, 80004003h
0x18000b3c9  jmp     loc_18000B468
0x18000b3ce  mov     qword ptr [r8], 0
0x18000b3d5  mov     ebp, 8007000Eh
0x18000b3da  mov     ecx, 38h ; '8'; unsigned int
0x18000b3df  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b3e4  mov     rsi, rax
0x18000b3e7  mov     [rsp+48h+arg_10], rax
0x18000b3ec  test    rax, rax
0x18000b3ef  jz      short loc_18000B43D
0x18000b3f1  mov     dword ptr [rax+8], 0
0x18000b3f8  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIRowsetConnection@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`vftable'
0x18000b3ff  mov     [rsi], rax
0x18000b402  mov     rax, [r15]
0x18000b405  mov     rcx, r15
0x18000b408  mov     rax, [rax+20h]
0x18000b40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b411  mov     rdi, rax
0x18000b414  lea     rax, ??_7IRowsetConnection@@6B@; const IRowsetConnection::`vftable'
0x18000b41b  mov     [rsi+18h], rax
0x18000b41f  lea     rcx, [rsi+20h]
0x18000b423  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b428  lea     rax, ??_7?$CComContainedObject@VCImpIRowsetConnection@@@ATL@@6B@; const ATL::CComContainedObject<CImpIRowsetConnection>::`vftable'
0x18000b42f  mov     [rsi+18h], rax
0x18000b433  mov     [rsi+20h], rdi
0x18000b437  mov     [rsi+30h], r15
0x18000b43b  jmp     short loc_18000B43F
0x18000b43d  xor     esi, esi
0x18000b43f  test    rsi, rsi
0x18000b442  jz      short loc_18000B466
0x18000b444  mov     rax, [rsi]
0x18000b447  mov     r8, r14
0x18000b44a  mov     rdx, r12
0x18000b44d  mov     rcx, rsi
0x18000b450  mov     rax, [rax]
0x18000b453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b458  mov     ebp, eax
0x18000b45a  test    eax, eax
0x18000b45c  jz      short loc_18000B466
0x18000b45e  mov     rcx, rsi; unsigned __int8 *
0x18000b461  call    ??_G?$CComCachedTearOffObject@VCImpIRowsetConnection@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`scalar deleting destructor'(uint)
0x18000b466  mov     eax, ebp
0x18000b468  mov     rbx, [rsp+48h+arg_0]
0x18000b46d  mov     rbp, [rsp+48h+arg_8]
0x18000b472  add     rsp, 20h
0x18000b476  pop     r15
0x18000b478  pop     r14
0x18000b47a  pop     r12
0x18000b47c  pop     rdi
0x18000b47d  pop     rsi
0x18000b47e  retn
```
