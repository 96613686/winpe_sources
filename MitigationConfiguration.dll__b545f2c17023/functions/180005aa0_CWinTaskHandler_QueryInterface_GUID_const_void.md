# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180005aa0`
- end: `0x180005b06`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180005aa0`
- `0x180015010`

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
0x180005aa0  sub     rsp, 28h
0x180005aa4  test    r8, r8
0x180005aa7  jnz     short loc_180005AB0
0x180005aa9  mov     eax, 80070057h
0x180005aae  jmp     short loc_180005B01
0x180005ab0  mov     rax, [rdx]
0x180005ab3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x180005aba  jnz     short loc_180005AC9
0x180005abc  mov     rax, [rdx+8]
0x180005ac0  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180005ac7  jz      short loc_180005AE2
0x180005ac9  mov     rax, [rdx]
0x180005acc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180005ad3  jnz     short loc_180005AF5
0x180005ad5  mov     rax, [rdx+8]
0x180005ad9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180005ae0  jnz     short loc_180005AF5
0x180005ae2  mov     [r8], rcx
0x180005ae5  mov     rax, [rcx]
0x180005ae8  mov     rax, [rax+8]
0x180005aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af1  xor     eax, eax
0x180005af3  jmp     short loc_180005B01
0x180005af5  mov     qword ptr [r8], 0
0x180005afc  mov     eax, 80004002h
0x180005b01  add     rsp, 28h
0x180005b05  retn
```
