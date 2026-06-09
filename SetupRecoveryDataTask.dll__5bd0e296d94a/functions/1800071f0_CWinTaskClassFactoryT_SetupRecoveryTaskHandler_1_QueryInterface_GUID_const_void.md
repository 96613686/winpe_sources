# CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800071f0`
- end: `0x180007256`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VSetupRecoveryTaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800071f0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::QueryInterface(
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
0x1800071f0  sub     rsp, 28h
0x1800071f4  test    r8, r8
0x1800071f7  jnz     short loc_180007200
0x1800071f9  mov     eax, 80070057h
0x1800071fe  jmp     short loc_180007251
0x180007200  mov     rax, [rdx]
0x180007203  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000720a  jnz     short loc_180007219
0x18000720c  mov     rax, [rdx+8]
0x180007210  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180007217  jz      short loc_180007232
0x180007219  mov     rax, [rdx]
0x18000721c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180007223  jnz     short loc_180007245
0x180007225  mov     rax, [rdx+8]
0x180007229  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180007230  jnz     short loc_180007245
0x180007232  mov     [r8], rcx
0x180007235  mov     rax, [rcx]
0x180007238  mov     rax, [rax+8]
0x18000723c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007241  xor     eax, eax
0x180007243  jmp     short loc_180007251
0x180007245  mov     qword ptr [r8], 0
0x18000724c  mov     eax, 80004002h
0x180007251  add     rsp, 28h
0x180007255  retn
```
