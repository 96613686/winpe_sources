# RemoteFinishRPCDebugThreadInfoEnumeration

- ea: `0x1800075b0`
- end: `0x1800075ed`
- name: `RemoteFinishRPCDebugThreadInfoEnumeration`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007410`
- `0x1800075b0`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x1800075c6`
- `RPCRT4!RpcRaiseException` at `0x1800075c6`

## pseudocode

```c
__int64 __fastcall RemoteFinishRPCDebugThreadInfoEnumeration(_QWORD **a1)
{
  _QWORD *v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( !v2 )
    RpcRaiseException(87);
  if ( *(_DWORD *)v2 != 2 )
    return 6;
  DbgThreadEnumHandle_rundown(v2);
  result = 0;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800075b0  push    rbx
0x1800075b2  sub     rsp, 20h
0x1800075b6  mov     rbx, rcx
0x1800075b9  mov     rcx, [rcx]; void *
0x1800075bc  test    rcx, rcx
0x1800075bf  jnz     short loc_1800075CD
0x1800075c1  mov     ecx, 57h ; 'W'; exception
0x1800075c6  call    cs:__imp_RpcRaiseException
0x1800075cc  int     3; Trap to Debugger
0x1800075cd  cmp     dword ptr [rcx], 2
0x1800075d0  jz      short loc_1800075D9
0x1800075d2  mov     eax, 6
0x1800075d7  jmp     short loc_1800075E7
0x1800075d9  call    DbgThreadEnumHandle_rundown
0x1800075de  xor     eax, eax
0x1800075e0  mov     qword ptr [rbx], 0
0x1800075e7  add     rsp, 20h
0x1800075eb  pop     rbx
0x1800075ec  retn
```
