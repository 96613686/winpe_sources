# CreateObjectServerTaskBase::Stop(long *)

- ea: `0x140008b20`
- end: `0x140008b3a`
- name: `?Stop@CreateObjectServerTaskBase@@UEAAJPEAJ@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details **this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400089b4`

## pseudocode

```c
__int64 __fastcall CreateObjectServerTaskBase::Stop(wil::details **this, int *a2)
{
  *a2 = 0;
  wil::details::SetEvent(this[11], a2);
  return 0;
}

```

## disassembly

```asm
0x140008b20  sub     rsp, 28h
0x140008b24  mov     dword ptr [rdx], 0
0x140008b2a  mov     rcx, [rcx+58h]; this
0x140008b2e  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x140008b33  xor     eax, eax
0x140008b35  add     rsp, 28h
0x140008b39  retn
```
