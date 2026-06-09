# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsRowset>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000afe0`
- end: `0x18000b0b4`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1e8`
- `0x18000a7b0`
- `0x18000afe0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsRowset>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIColumnsRowset>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000afe0  mov     [rsp+arg_0], rbx
0x18000afe5  mov     [rsp+arg_8], rbp
0x18000afea  push    rsi
0x18000afeb  push    rdi
0x18000afec  push    r12
0x18000afee  push    r14
0x18000aff0  push    r15
0x18000aff2  sub     rsp, 20h
0x18000aff6  mov     r14, r8
0x18000aff9  mov     r12, rdx
0x18000affc  mov     r15, rcx
0x18000afff  test    r8, r8
0x18000b002  jnz     short loc_18000B00E
0x18000b004  mov     eax, 80004003h
0x18000b009  jmp     loc_18000B09D
0x18000b00e  mov     qword ptr [r8], 0
0x18000b015  mov     ebp, 8007000Eh
0x18000b01a  mov     ecx, 38h ; '8'; unsigned int
0x18000b01f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b024  mov     rsi, rax
0x18000b027  mov     [rsp+48h+arg_10], rax
0x18000b02c  test    rax, rax
0x18000b02f  jz      short loc_18000B072
0x18000b031  mov     dword ptr [rax+8], 0
0x18000b038  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`vftable'
0x18000b03f  mov     [rsi], rax
0x18000b042  mov     rax, [r15]
0x18000b045  mov     rcx, r15
0x18000b048  mov     rax, [rax+20h]
0x18000b04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b051  mov     rdi, rax
0x18000b054  lea     rcx, [rsi+20h]
0x18000b058  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b05d  lea     rax, ??_7?$CComContainedObject@VCImpIColumnsRowset@@@ATL@@6B@; const ATL::CComContainedObject<CImpIColumnsRowset>::`vftable'
0x18000b064  mov     [rsi+18h], rax
0x18000b068  mov     [rsi+20h], rdi
0x18000b06c  mov     [rsi+30h], r15
0x18000b070  jmp     short loc_18000B074
0x18000b072  xor     esi, esi
0x18000b074  test    rsi, rsi
0x18000b077  jz      short loc_18000B09B
0x18000b079  mov     rax, [rsi]
0x18000b07c  mov     r8, r14
0x18000b07f  mov     rdx, r12
0x18000b082  mov     rcx, rsi
0x18000b085  mov     rax, [rax]
0x18000b088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b08d  mov     ebp, eax
0x18000b08f  test    eax, eax
0x18000b091  jz      short loc_18000B09B
0x18000b093  mov     rcx, rsi; unsigned __int8 *
0x18000b096  call    ??_G?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`scalar deleting destructor'(uint)
0x18000b09b  mov     eax, ebp
0x18000b09d  mov     rbx, [rsp+48h+arg_0]
0x18000b0a2  mov     rbp, [rsp+48h+arg_8]
0x18000b0a7  add     rsp, 20h
0x18000b0ab  pop     r15
0x18000b0ad  pop     r14
0x18000b0af  pop     r12
0x18000b0b1  pop     rdi
0x18000b0b2  pop     rsi
0x18000b0b3  retn
```
