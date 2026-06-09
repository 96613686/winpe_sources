# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180005890`
- end: `0x1800058f6`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180005890`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::QueryInterface(CWinTaskHandler *this, const struct _GUID *a2, void **a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITaskHandler.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ITaskHandler.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 8LL))(this);
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
0x180005890  sub     rsp, 28h
0x180005894  test    r8, r8
0x180005897  jnz     short loc_1800058A0
0x180005899  mov     eax, 80070057h
0x18000589e  jmp     short loc_1800058F1
0x1800058a0  mov     rax, [rdx]
0x1800058a3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x1800058aa  jnz     short loc_1800058B9
0x1800058ac  mov     rax, [rdx+8]
0x1800058b0  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x1800058b7  jz      short loc_1800058D2
0x1800058b9  mov     rax, [rdx]
0x1800058bc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800058c3  jnz     short loc_1800058E5
0x1800058c5  mov     rax, [rdx+8]
0x1800058c9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800058d0  jnz     short loc_1800058E5
0x1800058d2  mov     [r8], rcx
0x1800058d5  mov     rax, [rcx]
0x1800058d8  mov     rax, [rax+8]
0x1800058dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e1  xor     eax, eax
0x1800058e3  jmp     short loc_1800058F1
0x1800058e5  mov     qword ptr [r8], 0
0x1800058ec  mov     eax, 80004002h
0x1800058f1  add     rsp, 28h
0x1800058f5  retn
```
