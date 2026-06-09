# LocalEpmpSecurityCallback

- ea: `0x180005790`
- end: `0x1800057c8`
- name: `LocalEpmpSecurityCallback`
- size: `56`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005790`

## import_xrefs

- `RPCRT4!I_RpcBindingInqTransportType` at `0x1800057a4`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x1800057a4`

## pseudocode

```c
__int64 __fastcall LocalEpmpSecurityCallback(__int64 a1, void *a2)
{
  unsigned int Type; // [rsp+40h] [rbp+18h] BYREF

  Type = 0;
  if ( I_RpcBindingInqTransportType(a2, &Type) )
    return 5;
  else
    return Type != 4 ? 5 : 0;
}

```

## disassembly

```asm
0x180005790  sub     rsp, 28h
0x180005794  mov     rcx, rdx; Binding
0x180005797  mov     [rsp+28h+Type], 0
0x18000579f  lea     rdx, [rsp+28h+Type]; Type
0x1800057a4  call    cs:__imp_I_RpcBindingInqTransportType
0x1800057aa  test    eax, eax
0x1800057ac  jnz     short loc_1800057C1
0x1800057ae  mov     eax, [rsp+28h+Type]
0x1800057b2  sub     eax, 4
0x1800057b5  neg     eax
0x1800057b7  sbb     eax, eax
0x1800057b9  and     eax, 5
0x1800057bc  add     rsp, 28h
0x1800057c0  retn
0x1800057c1  mov     eax, 5
0x1800057c6  jmp     short loc_1800057BC
```
