# IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)

- ea: `0x18000b0ec`
- end: `0x18000b11a`
- name: `??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `46`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ba9c`
- `0x180015370`

## callees

- `0x18000b0ec`
- `0x180019010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(__int64 *a1)
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
0x18000b0ec  push    rbx
0x18000b0ee  sub     rsp, 20h
0x18000b0f2  mov     rbx, rcx
0x18000b0f5  mov     rcx, [rcx]
0x18000b0f8  test    rcx, rcx
0x18000b0fb  jz      short loc_18000B111
0x18000b0fd  mov     qword ptr [rbx], 0
0x18000b104  mov     rax, [rcx]
0x18000b107  mov     rax, [rax+10h]
0x18000b10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b110  nop
0x18000b111  mov     rax, rbx
0x18000b114  add     rsp, 20h
0x18000b118  pop     rbx
0x18000b119  retn
```
