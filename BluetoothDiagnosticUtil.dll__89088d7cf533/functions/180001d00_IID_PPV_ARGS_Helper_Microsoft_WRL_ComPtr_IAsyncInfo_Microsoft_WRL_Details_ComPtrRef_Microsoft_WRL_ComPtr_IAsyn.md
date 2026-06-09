# IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)

- ea: `0x180001d00`
- end: `0x180001d2f`
- name: `??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `47`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002b50`
- `0x180002df8`
- `0x1800030a0`

## callees

- `0x180001d00`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return a1;
}

```

## disassembly

```asm
0x180001d00  push    rbx
0x180001d02  sub     rsp, 20h
0x180001d06  mov     rbx, rcx
0x180001d09  mov     rcx, [rcx]
0x180001d0c  test    rcx, rcx
0x180001d0f  jz      short loc_180001D25
0x180001d11  mov     qword ptr [rbx], 0
0x180001d18  mov     rax, [rcx]
0x180001d1b  mov     rax, [rax+10h]
0x180001d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d24  nop
0x180001d25  mov     rax, rbx
0x180001d28  add     rsp, 20h
0x180001d2c  pop     rbx
0x180001d2d  retn
```
