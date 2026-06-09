# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetInfo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b490`
- end: `0x18000b564`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIRowsetInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1e8`
- `0x18000a88c`
- `0x18000b490`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetInfo>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIRowsetInfo>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b490  mov     [rsp+arg_0], rbx
0x18000b495  mov     [rsp+arg_8], rbp
0x18000b49a  push    rsi
0x18000b49b  push    rdi
0x18000b49c  push    r12
0x18000b49e  push    r14
0x18000b4a0  push    r15
0x18000b4a2  sub     rsp, 20h
0x18000b4a6  mov     r14, r8
0x18000b4a9  mov     r12, rdx
0x18000b4ac  mov     r15, rcx
0x18000b4af  test    r8, r8
0x18000b4b2  jnz     short loc_18000B4BE
0x18000b4b4  mov     eax, 80004003h
0x18000b4b9  jmp     loc_18000B54D
0x18000b4be  mov     qword ptr [r8], 0
0x18000b4c5  mov     ebp, 8007000Eh
0x18000b4ca  mov     ecx, 38h ; '8'; unsigned int
0x18000b4cf  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b4d4  mov     rsi, rax
0x18000b4d7  mov     [rsp+48h+arg_10], rax
0x18000b4dc  test    rax, rax
0x18000b4df  jz      short loc_18000B522
0x18000b4e1  mov     dword ptr [rax+8], 0
0x18000b4e8  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIRowsetInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`vftable'
0x18000b4ef  mov     [rsi], rax
0x18000b4f2  mov     rax, [r15]
0x18000b4f5  mov     rcx, r15
0x18000b4f8  mov     rax, [rax+20h]
0x18000b4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b501  mov     rdi, rax
0x18000b504  lea     rcx, [rsi+20h]
0x18000b508  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b50d  lea     rax, ??_7?$CComContainedObject@VCImpIRowsetInfo@@@ATL@@6B@; const ATL::CComContainedObject<CImpIRowsetInfo>::`vftable'
0x18000b514  mov     [rsi+18h], rax
0x18000b518  mov     [rsi+20h], rdi
0x18000b51c  mov     [rsi+30h], r15
0x18000b520  jmp     short loc_18000B524
0x18000b522  xor     esi, esi
0x18000b524  test    rsi, rsi
0x18000b527  jz      short loc_18000B54B
0x18000b529  mov     rax, [rsi]
0x18000b52c  mov     r8, r14
0x18000b52f  mov     rdx, r12
0x18000b532  mov     rcx, rsi
0x18000b535  mov     rax, [rax]
0x18000b538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b53d  mov     ebp, eax
0x18000b53f  test    eax, eax
0x18000b541  jz      short loc_18000B54B
0x18000b543  mov     rcx, rsi; unsigned __int8 *
0x18000b546  call    ??_G?$CComCachedTearOffObject@VCImpIRowsetInfo@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`scalar deleting destructor'(uint)
0x18000b54b  mov     eax, ebp
0x18000b54d  mov     rbx, [rsp+48h+arg_0]
0x18000b552  mov     rbp, [rsp+48h+arg_8]
0x18000b557  add     rsp, 20h
0x18000b55b  pop     r15
0x18000b55d  pop     r14
0x18000b55f  pop     r12
0x18000b561  pop     rdi
0x18000b562  pop     rsi
0x18000b563  retn
```
