# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIConvertType>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b1b0`
- end: `0x18000b284`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1e8`
- `0x18000a808`
- `0x18000b1b0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIConvertType>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIConvertType>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIConvertType>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIConvertType>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b1b0  mov     [rsp+arg_0], rbx
0x18000b1b5  mov     [rsp+arg_8], rbp
0x18000b1ba  push    rsi
0x18000b1bb  push    rdi
0x18000b1bc  push    r12
0x18000b1be  push    r14
0x18000b1c0  push    r15
0x18000b1c2  sub     rsp, 20h
0x18000b1c6  mov     r14, r8
0x18000b1c9  mov     r12, rdx
0x18000b1cc  mov     r15, rcx
0x18000b1cf  test    r8, r8
0x18000b1d2  jnz     short loc_18000B1DE
0x18000b1d4  mov     eax, 80004003h
0x18000b1d9  jmp     loc_18000B26D
0x18000b1de  mov     qword ptr [r8], 0
0x18000b1e5  mov     ebp, 8007000Eh
0x18000b1ea  mov     ecx, 38h ; '8'; unsigned int
0x18000b1ef  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b1f4  mov     rsi, rax
0x18000b1f7  mov     [rsp+48h+arg_10], rax
0x18000b1fc  test    rax, rax
0x18000b1ff  jz      short loc_18000B242
0x18000b201  mov     dword ptr [rax+8], 0
0x18000b208  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIConvertType>::`vftable'
0x18000b20f  mov     [rsi], rax
0x18000b212  mov     rax, [r15]
0x18000b215  mov     rcx, r15
0x18000b218  mov     rax, [rax+20h]
0x18000b21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b221  mov     rdi, rax
0x18000b224  lea     rcx, [rsi+20h]
0x18000b228  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b22d  lea     rax, ??_7?$CComContainedObject@VCImpIConvertType@@@ATL@@6B@; const ATL::CComContainedObject<CImpIConvertType>::`vftable'
0x18000b234  mov     [rsi+18h], rax
0x18000b238  mov     [rsi+20h], rdi
0x18000b23c  mov     [rsi+30h], r15
0x18000b240  jmp     short loc_18000B244
0x18000b242  xor     esi, esi
0x18000b244  test    rsi, rsi
0x18000b247  jz      short loc_18000B26B
0x18000b249  mov     rax, [rsi]
0x18000b24c  mov     r8, r14
0x18000b24f  mov     rdx, r12
0x18000b252  mov     rcx, rsi
0x18000b255  mov     rax, [rax]
0x18000b258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b25d  mov     ebp, eax
0x18000b25f  test    eax, eax
0x18000b261  jz      short loc_18000B26B
0x18000b263  mov     rcx, rsi; unsigned __int8 *
0x18000b266  call    ??_G?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIConvertType>::`scalar deleting destructor'(uint)
0x18000b26b  mov     eax, ebp
0x18000b26d  mov     rbx, [rsp+48h+arg_0]
0x18000b272  mov     rbp, [rsp+48h+arg_8]
0x18000b277  add     rsp, 20h
0x18000b27b  pop     r15
0x18000b27d  pop     r14
0x18000b27f  pop     r12
0x18000b281  pop     rdi
0x18000b282  pop     rsi
0x18000b283  retn
```
