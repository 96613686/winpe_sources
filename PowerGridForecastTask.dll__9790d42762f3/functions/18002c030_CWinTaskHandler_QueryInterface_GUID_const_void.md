# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x18002c030`
- end: `0x18002c096`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18002c030`
- `0x180037010`

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
0x18002c030  sub     rsp, 28h
0x18002c034  test    r8, r8
0x18002c037  jnz     short loc_18002C040
0x18002c039  mov     eax, 80070057h
0x18002c03e  jmp     short loc_18002C091
0x18002c040  mov     rax, [rdx]
0x18002c043  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x18002c04a  jnz     short loc_18002C059
0x18002c04c  mov     rax, [rdx+8]
0x18002c050  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x18002c057  jz      short loc_18002C072
0x18002c059  mov     rax, [rdx]
0x18002c05c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18002c063  jnz     short loc_18002C085
0x18002c065  mov     rax, [rdx+8]
0x18002c069  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18002c070  jnz     short loc_18002C085
0x18002c072  mov     [r8], rcx
0x18002c075  mov     rax, [rcx]
0x18002c078  mov     rax, [rax+8]
0x18002c07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c081  xor     eax, eax
0x18002c083  jmp     short loc_18002C091
0x18002c085  mov     qword ptr [r8], 0
0x18002c08c  mov     eax, 80004002h
0x18002c091  add     rsp, 28h
0x18002c095  retn
```
