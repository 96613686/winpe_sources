# CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000dd40`
- end: `0x18000dda6`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCDrvRecoveryOnRebootHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000dd40`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::QueryInterface(
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
0x18000dd40  sub     rsp, 28h
0x18000dd44  test    r8, r8
0x18000dd47  jnz     short loc_18000DD50
0x18000dd49  mov     eax, 80070057h
0x18000dd4e  jmp     short loc_18000DDA1
0x18000dd50  mov     rax, [rdx]
0x18000dd53  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000dd5a  jnz     short loc_18000DD69
0x18000dd5c  mov     rax, [rdx+8]
0x18000dd60  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x18000dd67  jz      short loc_18000DD82
0x18000dd69  mov     rax, [rdx]
0x18000dd6c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000dd73  jnz     short loc_18000DD95
0x18000dd75  mov     rax, [rdx+8]
0x18000dd79  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000dd80  jnz     short loc_18000DD95
0x18000dd82  mov     [r8], rcx
0x18000dd85  mov     rax, [rcx]
0x18000dd88  mov     rax, [rax+8]
0x18000dd8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd91  xor     eax, eax
0x18000dd93  jmp     short loc_18000DDA1
0x18000dd95  mov     qword ptr [r8], 0
0x18000dd9c  mov     eax, 80004002h
0x18000dda1  add     rsp, 28h
0x18000dda5  retn
```
