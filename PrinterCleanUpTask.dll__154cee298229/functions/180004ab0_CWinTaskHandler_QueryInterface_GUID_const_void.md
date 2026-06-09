# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180004ab0`
- end: `0x180004b1c`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180004ab0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::QueryInterface(CWinTaskHandler *this, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( !a3 )
    return 2147942487LL;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ITaskHandler.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITaskHandler.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ITaskHandler.Data4;
  if ( !v4 )
    goto LABEL_10;
  v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( v5 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
LABEL_10:
    *a3 = this;
    (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
}

```

## disassembly

```asm
0x180004ab0  sub     rsp, 28h
0x180004ab4  test    r8, r8
0x180004ab7  jnz     short loc_180004AC0
0x180004ab9  mov     eax, 80070057h
0x180004abe  jmp     short loc_180004B17
0x180004ac0  mov     rax, [rdx]
0x180004ac3  sub     rax, qword ptr cs:IID_ITaskHandler.Data1
0x180004aca  jnz     short loc_180004AD7
0x180004acc  mov     rax, [rdx+8]
0x180004ad0  sub     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180004ad7  test    rax, rax
0x180004ada  jz      short loc_180004B06
0x180004adc  mov     rax, [rdx]
0x180004adf  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180004ae6  jnz     short loc_180004AF3
0x180004ae8  mov     rax, [rdx+8]
0x180004aec  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180004af3  test    rax, rax
0x180004af6  jz      short loc_180004B06
0x180004af8  mov     qword ptr [r8], 0
0x180004aff  mov     eax, 80004002h
0x180004b04  jmp     short loc_180004B17
0x180004b06  mov     [r8], rcx
0x180004b09  mov     rax, [rcx]
0x180004b0c  mov     rax, [rax+8]
0x180004b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b15  xor     eax, eax
0x180004b17  add     rsp, 28h
0x180004b1b  retn
```
