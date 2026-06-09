# CWinTaskClassFactoryT<CPlutonTasksHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800063f0`
- end: `0x18000645c`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCPlutonTasksHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800063f0`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPlutonTasksHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( !a3 )
    return 2147942487LL;
  v4 = *a2 - *(_QWORD *)&IID_IClassFactory.Data1;
  if ( *a2 == *(_QWORD *)&IID_IClassFactory.Data1 )
    v4 = a2[1] - *(_QWORD *)IID_IClassFactory.Data4;
  if ( !v4 )
    goto LABEL_10;
  v5 = *a2 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *a2 == *(_QWORD *)&IID_IUnknown.Data1 )
    v5 = a2[1] - *(_QWORD *)IID_IUnknown.Data4;
  if ( v5 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
LABEL_10:
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
}

```

## disassembly

```asm
0x1800063f0  sub     rsp, 28h
0x1800063f4  test    r8, r8
0x1800063f7  jnz     short loc_180006400
0x1800063f9  mov     eax, 80070057h
0x1800063fe  jmp     short loc_180006457
0x180006400  mov     rax, [rdx]
0x180006403  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000640a  jnz     short loc_180006417
0x18000640c  mov     rax, [rdx+8]
0x180006410  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x180006417  test    rax, rax
0x18000641a  jz      short loc_180006446
0x18000641c  mov     rax, [rdx]
0x18000641f  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180006426  jnz     short loc_180006433
0x180006428  mov     rax, [rdx+8]
0x18000642c  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180006433  test    rax, rax
0x180006436  jz      short loc_180006446
0x180006438  mov     qword ptr [r8], 0
0x18000643f  mov     eax, 80004002h
0x180006444  jmp     short loc_180006457
0x180006446  mov     [r8], rcx
0x180006449  mov     rax, [rcx]
0x18000644c  mov     rax, [rax+8]
0x180006450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006455  xor     eax, eax
0x180006457  add     rsp, 28h
0x18000645b  retn
```
