# CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x18002bfc0`
- end: `0x18002c026`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCDeferredChargingTaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18002bfc0`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::QueryInterface(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *a2 == *(_QWORD *)&IID_IClassFactory.Data1 && a2[1] == *(_QWORD *)IID_IClassFactory.Data4
    || *a2 == *(_QWORD *)&IID_IUnknown.Data1 && a2[1] == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x18002bfc0  sub     rsp, 28h
0x18002bfc4  test    r8, r8
0x18002bfc7  jnz     short loc_18002BFD0
0x18002bfc9  mov     eax, 80070057h
0x18002bfce  jmp     short loc_18002C021
0x18002bfd0  mov     rax, [rdx]
0x18002bfd3  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18002bfda  jnz     short loc_18002BFE9
0x18002bfdc  mov     rax, [rdx+8]
0x18002bfe0  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x18002bfe7  jz      short loc_18002C002
0x18002bfe9  mov     rax, [rdx]
0x18002bfec  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18002bff3  jnz     short loc_18002C015
0x18002bff5  mov     rax, [rdx+8]
0x18002bff9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18002c000  jnz     short loc_18002C015
0x18002c002  mov     [r8], rcx
0x18002c005  mov     rax, [rcx]
0x18002c008  mov     rax, [rax+8]
0x18002c00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c011  xor     eax, eax
0x18002c013  jmp     short loc_18002C021
0x18002c015  mov     qword ptr [r8], 0
0x18002c01c  mov     eax, 80004002h
0x18002c021  add     rsp, 28h
0x18002c025  retn
```
