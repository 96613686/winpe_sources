# CWinTaskClassFactoryT<WhesvcUXHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c660`
- end: `0x18000c6cc`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VWhesvcUXHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000c660`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<WhesvcUXHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x18000c660  sub     rsp, 28h
0x18000c664  test    r8, r8
0x18000c667  jnz     short loc_18000C670
0x18000c669  mov     eax, 80070057h
0x18000c66e  jmp     short loc_18000C6C7
0x18000c670  mov     rax, [rdx]
0x18000c673  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000c67a  jnz     short loc_18000C687
0x18000c67c  mov     rax, [rdx+8]
0x18000c680  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x18000c687  test    rax, rax
0x18000c68a  jz      short loc_18000C6B6
0x18000c68c  mov     rax, [rdx]
0x18000c68f  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c696  jnz     short loc_18000C6A3
0x18000c698  mov     rax, [rdx+8]
0x18000c69c  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c6a3  test    rax, rax
0x18000c6a6  jz      short loc_18000C6B6
0x18000c6a8  mov     qword ptr [r8], 0
0x18000c6af  mov     eax, 80004002h
0x18000c6b4  jmp     short loc_18000C6C7
0x18000c6b6  mov     [r8], rcx
0x18000c6b9  mov     rax, [rcx]
0x18000c6bc  mov     rax, [rax+8]
0x18000c6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6c5  xor     eax, eax
0x18000c6c7  add     rsp, 28h
0x18000c6cb  retn
```
