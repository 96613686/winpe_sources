# CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002b20`
- end: `0x180002b86`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCTempSignedLicenseExchangeTaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002b20`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::QueryInterface(
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
0x180002b20  sub     rsp, 28h
0x180002b24  test    r8, r8
0x180002b27  jnz     short loc_180002B30
0x180002b29  mov     eax, 80070057h
0x180002b2e  jmp     short loc_180002B81
0x180002b30  mov     rax, [rdx]
0x180002b33  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x180002b3a  jnz     short loc_180002B49
0x180002b3c  mov     rax, [rdx+8]
0x180002b40  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180002b47  jz      short loc_180002B62
0x180002b49  mov     rax, [rdx]
0x180002b4c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180002b53  jnz     short loc_180002B75
0x180002b55  mov     rax, [rdx+8]
0x180002b59  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180002b60  jnz     short loc_180002B75
0x180002b62  mov     [r8], rcx
0x180002b65  mov     rax, [rcx]
0x180002b68  mov     rax, [rax+8]
0x180002b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b71  xor     eax, eax
0x180002b73  jmp     short loc_180002B81
0x180002b75  mov     qword ptr [r8], 0
0x180002b7c  mov     eax, 80004002h
0x180002b81  add     rsp, 28h
0x180002b85  retn
```
