# CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002930`
- end: `0x180002996`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCTimeSyncTaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002930`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x180002930  sub     rsp, 28h
0x180002934  test    r8, r8
0x180002937  jnz     short loc_180002940
0x180002939  mov     eax, 80070057h
0x18000293e  jmp     short loc_180002991
0x180002940  mov     rax, [rdx]
0x180002943  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000294a  jnz     short loc_180002959
0x18000294c  mov     rax, [rdx+8]
0x180002950  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180002957  jz      short loc_180002972
0x180002959  mov     rax, [rdx]
0x18000295c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180002963  jnz     short loc_180002985
0x180002965  mov     rax, [rdx+8]
0x180002969  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180002970  jnz     short loc_180002985
0x180002972  mov     [r8], rcx
0x180002975  mov     rax, [rcx]
0x180002978  mov     rax, [rax+8]
0x18000297c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002981  xor     eax, eax
0x180002983  jmp     short loc_180002991
0x180002985  mov     qword ptr [r8], 0
0x18000298c  mov     eax, 80004002h
0x180002991  add     rsp, 28h
0x180002995  retn
```
