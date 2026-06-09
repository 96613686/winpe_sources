# winrt::com_ptr<IXpsRasterizerNotificationCallback>::~com_ptr<IXpsRasterizerNotificationCallback>(void)

- ea: `0x18000e0d0`
- end: `0x18000e0e4`
- name: `??1?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001068f`
- `0x1800106a5`
- `0x18001073d`
- `0x18001074f`

## callees

- `0x18000e0d0`
- `0x18000f3c0`

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
0x18000e0d0  sub     rsp, 28h
0x18000e0d4  cmp     qword ptr [rcx], 0
0x18000e0d8  jz      short loc_18000E0DF
0x18000e0da  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000e0df  add     rsp, 28h
0x18000e0e3  retn
```
