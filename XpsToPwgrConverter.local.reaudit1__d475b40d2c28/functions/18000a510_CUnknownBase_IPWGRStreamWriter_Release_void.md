# CUnknownBase<IPWGRStreamWriter>::Release(void)

- ea: `0x18000a510`
- end: `0x18000a53f`
- name: `?Release@?$CUnknownBase@UIPWGRStreamWriter@@@@UEAAKXZ`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a510`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CUnknownBase<IPWGRStreamWriter>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( !v1 && a1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 48LL))(a1, 1);
  return v1;
}

```

## disassembly

```asm
0x18000a510  push    rbx
0x18000a512  sub     rsp, 20h
0x18000a516  or      ebx, 0FFFFFFFFh
0x18000a519  lock xadd [rcx+8], ebx
0x18000a51e  sub     ebx, 1
0x18000a521  jnz     short loc_18000A537
0x18000a523  test    rcx, rcx
0x18000a526  jz      short loc_18000A537
0x18000a528  mov     rdx, [rcx]
0x18000a52b  mov     rax, [rdx+30h]
0x18000a52f  lea     edx, [rbx+1]
0x18000a532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a537  mov     eax, ebx
0x18000a539  add     rsp, 20h
0x18000a53d  pop     rbx
0x18000a53e  retn
```
