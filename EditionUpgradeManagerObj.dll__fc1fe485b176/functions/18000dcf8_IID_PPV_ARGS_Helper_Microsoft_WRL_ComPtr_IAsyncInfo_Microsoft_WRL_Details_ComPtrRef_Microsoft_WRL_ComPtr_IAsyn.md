# IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)

- ea: `0x18000dcf8`
- end: `0x18000dd25`
- name: `??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `45`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000de6c`
- `0x18000e0b4`
- `0x18000e2fc`
- `0x18000e544`
- `0x18000e78c`
- `0x18000ea14`

## callees

- `0x18000dcf8`
- `0x180023010`

## pseudocode

```c
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
0x18000dcf8  push    rbx
0x18000dcfa  sub     rsp, 20h
0x18000dcfe  mov     rbx, rcx
0x18000dd01  mov     rcx, [rcx]
0x18000dd04  test    rcx, rcx
0x18000dd07  jz      short loc_18000DD1C
0x18000dd09  mov     qword ptr [rbx], 0
0x18000dd10  mov     rax, [rcx]
0x18000dd13  mov     rax, [rax+10h]
0x18000dd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd1c  mov     rax, rbx
0x18000dd1f  add     rsp, 20h
0x18000dd23  pop     rbx
0x18000dd24  retn
```
