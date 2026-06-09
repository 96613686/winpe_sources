# Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)

- ea: `0x180002974`
- end: `0x1800029bd`
- name: `??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ`
- size: `73`
- prototype: `int __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ae0`
- `0x180008d4c`

## callees

- `0x180002974`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800029a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800029a2`

## pseudocode

```c
int __fastcall Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // r8
  int result; // eax

  v2 = *(void **)a1;
  if ( v2 )
  {
    try
    {
      v3 = *(_QWORD *)(a1 + 16);
      if ( v3 )
        result = (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)v3 + 96LL))(*(_QWORD *)(a1 + 16), v2);
      else
        result = CloseHandle(v2);
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
    }
    catch ( ... )
    {
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002974  push    rbx
0x180002976  sub     rsp, 20h
0x18000297a  mov     rbx, rcx
0x18000297d  mov     rcx, [rcx]; hObject
0x180002980  test    rcx, rcx
0x180002983  jz      short loc_1800029B7
0x180002985  mov     r8, [rbx+10h]
0x180002989  test    r8, r8
0x18000298c  jz      short loc_1800029A2
0x18000298e  mov     rax, [r8]
0x180002991  mov     rdx, rcx
0x180002994  mov     rcx, r8
0x180002997  mov     rax, [rax+60h]
0x18000299b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a0  jmp     short loc_1800029A8
0x1800029a2  call    cs:__imp_CloseHandle
0x1800029a8  mov     qword ptr [rbx], 0
0x1800029af  mov     qword ptr [rbx+8], 0
0x1800029b7  add     rsp, 20h
0x1800029bb  pop     rbx
0x1800029bc  retn
```
