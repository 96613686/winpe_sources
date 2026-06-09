# I_CryptXmlRelease

- ea: `0x180004f60`
- end: `0x180004f87`
- name: `I_CryptXmlRelease`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001fe0`
- `0x1800029b0`
- `0x1800031b0`
- `0x180003650`
- `0x180003fb0`
- `0x1800049c0`
- `0x18000fcc0`
- `0x180010bd0`
- `0x1800110e0`
- `0x180012350`
- `0x1800125a0`
- `0x180016a0c`

## callees

- `0x180004f60`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall I_CryptXmlRelease(__int64 a1)
{
  signed __int32 v1; // ebx
  bool v2; // cc
  unsigned __int32 v3; // ebx

  v1 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 56), 0xFFFFFFFF);
  v2 = v1 <= 1;
  v3 = v1 - 1;
  if ( v2 )
    (*(void (**)(void))(a1 + 112))();
  return v3;
}

```

## disassembly

```asm
0x180004f60  push    rbx
0x180004f62  sub     rsp, 20h
0x180004f66  mov     ebx, 0FFFFFFFFh
0x180004f6b  lock xadd [rcx+38h], ebx
0x180004f70  sub     ebx, 1
0x180004f73  jg      short loc_180004F7E
0x180004f75  mov     rax, [rcx+70h]
0x180004f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f7e  mov     eax, ebx
0x180004f80  add     rsp, 20h
0x180004f84  pop     rbx
0x180004f85  retn
```
