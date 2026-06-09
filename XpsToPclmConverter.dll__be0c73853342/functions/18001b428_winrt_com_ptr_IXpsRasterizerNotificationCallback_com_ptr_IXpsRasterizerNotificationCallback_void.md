# winrt::com_ptr<IXpsRasterizerNotificationCallback>::~com_ptr<IXpsRasterizerNotificationCallback>(void)

- ea: `0x18001b428`
- end: `0x18001b43c`
- name: `??1?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e12c`
- `0x18001e142`
- `0x18001e1a2`
- `0x18001e1b4`

## callees

- `0x18001b428`
- `0x18001c7b0`

## pseudocode

```c
double __fastcall winrt::com_ptr<IXpsRasterizerNotificationCallback>::~com_ptr<IXpsRasterizerNotificationCallback>(
        _QWORD *a1)
{
  double result; // xmm0_8

  if ( *a1 )
    return winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x18001b428  sub     rsp, 28h
0x18001b42c  cmp     qword ptr [rcx], 0
0x18001b430  jz      short loc_18001B437
0x18001b432  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18001b437  add     rsp, 28h
0x18001b43b  retn
```
