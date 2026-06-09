# winrt::com_ptr<IPropertyBag2>::~com_ptr<IPropertyBag2>(void)

- ea: `0x180009cb8`
- end: `0x180009ccc`
- name: `??1?$com_ptr@UIPropertyBag2@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d63f`
- `0x18000d663`
- `0x18000d675`
- `0x18000d74e`
- `0x18000d764`
- `0x18000d803`
- `0x18000d815`

## callees

- `0x180009cb8`
- `0x18000b62c`

## pseudocode

```c
double __fastcall winrt::com_ptr<IPropertyBag2>::~com_ptr<IPropertyBag2>(_QWORD *a1)
{
  double result; // xmm0_8

  if ( *a1 )
    return winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x180009cb8  sub     rsp, 28h
0x180009cbc  cmp     qword ptr [rcx], 0
0x180009cc0  jz      short loc_180009CC7
0x180009cc2  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x180009cc7  add     rsp, 28h
0x180009ccb  retn
```
