# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIAccessor>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000ad40`
- end: `0x18000ae14`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1e8`
- `0x18000a72c`
- `0x18000ad40`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIAccessor>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIAccessor>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIAccessor>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIAccessor>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000ad40  mov     [rsp+arg_0], rbx
0x18000ad45  mov     [rsp+arg_8], rbp
0x18000ad4a  push    rsi
0x18000ad4b  push    rdi
0x18000ad4c  push    r12
0x18000ad4e  push    r14
0x18000ad50  push    r15
0x18000ad52  sub     rsp, 20h
0x18000ad56  mov     r14, r8
0x18000ad59  mov     r12, rdx
0x18000ad5c  mov     r15, rcx
0x18000ad5f  test    r8, r8
0x18000ad62  jnz     short loc_18000AD6E
0x18000ad64  mov     eax, 80004003h
0x18000ad69  jmp     loc_18000ADFD
0x18000ad6e  mov     qword ptr [r8], 0
0x18000ad75  mov     ebp, 8007000Eh
0x18000ad7a  mov     ecx, 38h ; '8'; unsigned int
0x18000ad7f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000ad84  mov     rsi, rax
0x18000ad87  mov     [rsp+48h+arg_10], rax
0x18000ad8c  test    rax, rax
0x18000ad8f  jz      short loc_18000ADD2
0x18000ad91  mov     dword ptr [rax+8], 0
0x18000ad98  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIAccessor>::`vftable'
0x18000ad9f  mov     [rsi], rax
0x18000ada2  mov     rax, [r15]
0x18000ada5  mov     rcx, r15
0x18000ada8  mov     rax, [rax+20h]
0x18000adac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb1  mov     rdi, rax
0x18000adb4  lea     rcx, [rsi+20h]
0x18000adb8  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000adbd  lea     rax, ??_7?$CComContainedObject@VCImpIAccessor@@@ATL@@6B@; const ATL::CComContainedObject<CImpIAccessor>::`vftable'
0x18000adc4  mov     [rsi+18h], rax
0x18000adc8  mov     [rsi+20h], rdi
0x18000adcc  mov     [rsi+30h], r15
0x18000add0  jmp     short loc_18000ADD4
0x18000add2  xor     esi, esi
0x18000add4  test    rsi, rsi
0x18000add7  jz      short loc_18000ADFB
0x18000add9  mov     rax, [rsi]
0x18000addc  mov     r8, r14
0x18000addf  mov     rdx, r12
0x18000ade2  mov     rcx, rsi
0x18000ade5  mov     rax, [rax]
0x18000ade8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aded  mov     ebp, eax
0x18000adef  test    eax, eax
0x18000adf1  jz      short loc_18000ADFB
0x18000adf3  mov     rcx, rsi; unsigned __int8 *
0x18000adf6  call    ??_G?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIAccessor>::`scalar deleting destructor'(uint)
0x18000adfb  mov     eax, ebp
0x18000adfd  mov     rbx, [rsp+48h+arg_0]
0x18000ae02  mov     rbp, [rsp+48h+arg_8]
0x18000ae07  add     rsp, 20h
0x18000ae0b  pop     r15
0x18000ae0d  pop     r14
0x18000ae0f  pop     r12
0x18000ae11  pop     rdi
0x18000ae12  pop     rsi
0x18000ae13  retn
```
