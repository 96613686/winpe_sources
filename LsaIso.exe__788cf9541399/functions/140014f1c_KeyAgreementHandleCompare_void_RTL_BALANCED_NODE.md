# KeyAgreementHandleCompare(void *,_RTL_BALANCED_NODE *)

- ea: `0x140014f1c`
- end: `0x140014f32`
- name: `?KeyAgreementHandleCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(void *, struct _RTL_BALANCED_NODE *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001489c`
- `0x140014f5c`
- `0x140017be0`
- `0x140017e00`
- `0x140018540`

## callees

- `0x140014f1c`

## pseudocode

```c
__int64 __fastcall KeyAgreementHandleCompare(_QWORD *a1, struct _RTL_BALANCED_NODE *a2)
{
  struct _RTL_BALANCED_NODE *v2; // r8

  v2 = a2[1].Children[0];
  if ( *a1 >= (__int64)v2 )
    return *a1 > (__int64)v2;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140014f1c  mov     r8, [rdx+18h]
0x140014f20  cmp     [rcx], r8
0x140014f23  jge     short loc_140014F29
0x140014f25  or      eax, 0FFFFFFFFh
0x140014f28  retn
0x140014f29  xor     eax, eax
0x140014f2b  cmp     [rcx], r8
0x140014f2e  setnle  al
0x140014f31  retn
```
