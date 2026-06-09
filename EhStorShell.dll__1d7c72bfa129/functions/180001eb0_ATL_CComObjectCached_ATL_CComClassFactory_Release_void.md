# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180001eb0`
- end: `0x180001f13`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `99`
- prototype: `unsigned int __fastcall(volatile int *Block)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001eb0`
- `0x180002300`
- `0x180006b74`
- `0x180009104`
- `0x18000c010`

## pseudocode

```c
unsigned int __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(volatile int *Block)
{
  unsigned int result; // eax
  unsigned int v3; // ebx

  result = ATL::SafeDecrementReferenceMultiThread(Block + 2);
  v3 = result;
  if ( result )
  {
    if ( result == 1 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
      return v3;
    }
  }
  else if ( Block )
  {
    ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>((__int64)Block);
    operator delete((void *)Block);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180001eb0  mov     [rsp+arg_0], rbx
0x180001eb5  push    rdi
0x180001eb6  sub     rsp, 20h
0x180001eba  mov     rdi, rcx
0x180001ebd  add     rcx, 8; volatile int *
0x180001ec1  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180001ec6  mov     ebx, eax
0x180001ec8  test    eax, eax
0x180001eca  jz      short loc_180001EF1
0x180001ecc  cmp     eax, 1
0x180001ecf  jnz     short loc_180001EE6
0x180001ed1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001ed8  mov     rax, [rcx]
0x180001edb  mov     rax, [rax+10h]
0x180001edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ee4  mov     eax, ebx
0x180001ee6  mov     rbx, [rsp+28h+arg_0]
0x180001eeb  add     rsp, 20h
0x180001eef  pop     rdi
0x180001ef0  retn
0x180001ef1  test    rdi, rdi
0x180001ef4  jz      short loc_180001EE6
0x180001ef6  mov     rcx, rdi
0x180001ef9  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x180001efe  mov     rcx, rdi; Block
0x180001f01  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001f06  mov     eax, ebx
0x180001f08  mov     rbx, [rsp+28h+arg_0]
0x180001f0d  add     rsp, 20h
0x180001f11  pop     rdi
0x180001f12  retn
```
