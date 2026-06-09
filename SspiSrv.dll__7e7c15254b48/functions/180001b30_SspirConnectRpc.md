# SspirConnectRpc

- ea: `0x180001b30`
- end: `0x180001b82`
- name: `SspirConnectRpc`
- size: `82`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001b30`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirConnectRpc(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 (__fastcall *v6)(__int64, _QWORD, __int64, __int64, __int64); // rax

  if ( gLsapSspiExtension
    && (v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64))(gLsapSspiExtension + 24)) != 0 )
  {
    return v6(a2, a3, a4, a5, a6);
  }
  else
  {
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x180001b30  push    rbx
0x180001b32  sub     rsp, 30h
0x180001b36  mov     rax, cs:gLsapSspiExtension
0x180001b3d  mov     r10, r9
0x180001b40  mov     r11d, r8d
0x180001b43  mov     rbx, rdx
0x180001b46  test    rax, rax
0x180001b49  jz      short loc_180001B54
0x180001b4b  mov     rax, [rax+18h]
0x180001b4f  test    rax, rax
0x180001b52  jnz     short loc_180001B5F
0x180001b54  mov     eax, 0C00000BBh
0x180001b59  add     rsp, 30h
0x180001b5d  pop     rbx
0x180001b5e  retn
0x180001b5f  mov     rcx, [rsp+38h+arg_28]
0x180001b64  mov     r8, r10
0x180001b67  mov     r9, [rsp+38h+arg_20]
0x180001b6c  mov     edx, r11d
0x180001b6f  mov     [rsp+38h+var_18], rcx
0x180001b74  mov     rcx, rbx
0x180001b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b7c  add     rsp, 30h
0x180001b80  pop     rbx
0x180001b81  retn
```
