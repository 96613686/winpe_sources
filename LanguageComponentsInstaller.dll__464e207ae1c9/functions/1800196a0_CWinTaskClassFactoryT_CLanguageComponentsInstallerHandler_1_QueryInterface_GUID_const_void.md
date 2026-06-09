# CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800196a0`
- end: `0x180019706`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCLanguageComponentsInstallerHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800196a0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::QueryInterface(
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
0x1800196a0  sub     rsp, 28h
0x1800196a4  test    r8, r8
0x1800196a7  jnz     short loc_1800196B0
0x1800196a9  mov     eax, 80070057h
0x1800196ae  jmp     short loc_180019701
0x1800196b0  mov     rax, [rdx]
0x1800196b3  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x1800196ba  jnz     short loc_1800196C9
0x1800196bc  mov     rax, [rdx+8]
0x1800196c0  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x1800196c7  jz      short loc_1800196E2
0x1800196c9  mov     rax, [rdx]
0x1800196cc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800196d3  jnz     short loc_1800196F5
0x1800196d5  mov     rax, [rdx+8]
0x1800196d9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800196e0  jnz     short loc_1800196F5
0x1800196e2  mov     [r8], rcx
0x1800196e5  mov     rax, [rcx]
0x1800196e8  mov     rax, [rax+8]
0x1800196ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196f1  xor     eax, eax
0x1800196f3  jmp     short loc_180019701
0x1800196f5  mov     qword ptr [r8], 0
0x1800196fc  mov     eax, 80004002h
0x180019701  add     rsp, 28h
0x180019705  retn
```
