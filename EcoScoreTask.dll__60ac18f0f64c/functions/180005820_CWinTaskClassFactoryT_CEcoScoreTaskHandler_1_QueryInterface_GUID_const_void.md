# CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005820`
- end: `0x180005886`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCEcoScoreTaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180005820`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x180005820  sub     rsp, 28h
0x180005824  test    r8, r8
0x180005827  jnz     short loc_180005830
0x180005829  mov     eax, 80070057h
0x18000582e  jmp     short loc_180005881
0x180005830  mov     rax, [rdx]
0x180005833  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000583a  jnz     short loc_180005849
0x18000583c  mov     rax, [rdx+8]
0x180005840  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180005847  jz      short loc_180005862
0x180005849  mov     rax, [rdx]
0x18000584c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180005853  jnz     short loc_180005875
0x180005855  mov     rax, [rdx+8]
0x180005859  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180005860  jnz     short loc_180005875
0x180005862  mov     [r8], rcx
0x180005865  mov     rax, [rcx]
0x180005868  mov     rax, [rax+8]
0x18000586c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005871  xor     eax, eax
0x180005873  jmp     short loc_180005881
0x180005875  mov     qword ptr [r8], 0
0x18000587c  mov     eax, 80004002h
0x180005881  add     rsp, 28h
0x180005885  retn
```
