# CWinTaskClassFactoryT<CWofTasksHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180003540`
- end: `0x1800035a6`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCWofTasksHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003540`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CWofTasksHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x180003540  sub     rsp, 28h
0x180003544  test    r8, r8
0x180003547  jnz     short loc_180003550
0x180003549  mov     eax, 80070057h
0x18000354e  jmp     short loc_1800035A1
0x180003550  mov     rax, [rdx]
0x180003553  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000355a  jnz     short loc_180003569
0x18000355c  mov     rax, [rdx+8]
0x180003560  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180003567  jz      short loc_180003582
0x180003569  mov     rax, [rdx]
0x18000356c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180003573  jnz     short loc_180003595
0x180003575  mov     rax, [rdx+8]
0x180003579  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180003580  jnz     short loc_180003595
0x180003582  mov     [r8], rcx
0x180003585  mov     rax, [rcx]
0x180003588  mov     rax, [rax+8]
0x18000358c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003591  xor     eax, eax
0x180003593  jmp     short loc_1800035A1
0x180003595  mov     qword ptr [r8], 0
0x18000359c  mov     eax, 80004002h
0x1800035a1  add     rsp, 28h
0x1800035a5  retn
```
