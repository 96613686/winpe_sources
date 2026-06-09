# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180006470`
- end: `0x1800064dc`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180006470`
- `0x18000a010`

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
0x180006470  sub     rsp, 28h
0x180006474  test    r8, r8
0x180006477  jnz     short loc_180006480
0x180006479  mov     eax, 80070057h
0x18000647e  jmp     short loc_1800064D7
0x180006480  mov     rax, [rdx]
0x180006483  sub     rax, qword ptr cs:IID_ITaskHandler.Data1
0x18000648a  jnz     short loc_180006497
0x18000648c  mov     rax, [rdx+8]
0x180006490  sub     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180006497  test    rax, rax
0x18000649a  jz      short loc_1800064C6
0x18000649c  mov     rax, [rdx]
0x18000649f  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800064a6  jnz     short loc_1800064B3
0x1800064a8  mov     rax, [rdx+8]
0x1800064ac  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800064b3  test    rax, rax
0x1800064b6  jz      short loc_1800064C6
0x1800064b8  mov     qword ptr [r8], 0
0x1800064bf  mov     eax, 80004002h
0x1800064c4  jmp     short loc_1800064D7
0x1800064c6  mov     [r8], rcx
0x1800064c9  mov     rax, [rcx]
0x1800064cc  mov     rax, [rax+8]
0x1800064d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064d5  xor     eax, eax
0x1800064d7  add     rsp, 28h
0x1800064db  retn
```
