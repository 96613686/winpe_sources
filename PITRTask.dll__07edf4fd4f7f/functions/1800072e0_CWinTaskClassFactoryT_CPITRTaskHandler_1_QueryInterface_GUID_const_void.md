# CWinTaskClassFactoryT<CPITRTaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800072e0`
- end: `0x180007346`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCPITRTaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800072e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPITRTaskHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x1800072e0  sub     rsp, 28h
0x1800072e4  test    r8, r8
0x1800072e7  jnz     short loc_1800072F0
0x1800072e9  mov     eax, 80070057h
0x1800072ee  jmp     short loc_180007341
0x1800072f0  mov     rax, [rdx]
0x1800072f3  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x1800072fa  jnz     short loc_180007309
0x1800072fc  mov     rax, [rdx+8]
0x180007300  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180007307  jz      short loc_180007322
0x180007309  mov     rax, [rdx]
0x18000730c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180007313  jnz     short loc_180007335
0x180007315  mov     rax, [rdx+8]
0x180007319  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180007320  jnz     short loc_180007335
0x180007322  mov     [r8], rcx
0x180007325  mov     rax, [rcx]
0x180007328  mov     rax, [rax+8]
0x18000732c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007331  xor     eax, eax
0x180007333  jmp     short loc_180007341
0x180007335  mov     qword ptr [r8], 0
0x18000733c  mov     eax, 80004002h
0x180007341  add     rsp, 28h
0x180007345  retn
```
