# SelectorTemplate<ConfigLocationToRawConfigSelector>::CreateContextNodeProjection(ulong,IXPathExpression * *,IUnknown * *)

- ea: `0x180007b40`
- end: `0x180007b92`
- name: `?CreateContextNodeProjection@?$SelectorTemplate@VConfigLocationToRawConfigSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180007b40`
- `0x180007c58`
- `0x18000e198`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SelectorTemplate<ConfigLocationToRawConfigSelector>::CreateContextNodeProjection(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int Instance; // ebx
  struct ContextNodeIterator *v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  Instance = ContextNodeIterator::CreateInstance(&v6);
  if ( Instance >= 0 )
  {
    Instance = ProjectionIterator<ConfigLocationToRawConfigSelector>::CreateInstance((__int64)v6, a3);
    if ( Instance >= 0 )
      Instance = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180007b40  mov     [rsp+arg_0], rbx
0x180007b45  push    rdi
0x180007b46  sub     rsp, 20h
0x180007b4a  mov     rdi, r8
0x180007b4d  mov     [rsp+28h+arg_18], 0
0x180007b56  lea     rcx, [rsp+28h+arg_18]; struct ContextNodeIterator **
0x180007b5b  call    ?CreateInstance@ContextNodeIterator@@SAJPEAPEAV1@@Z; ContextNodeIterator::CreateInstance(ContextNodeIterator * *)
0x180007b60  mov     ebx, eax
0x180007b62  test    eax, eax
0x180007b64  js      short loc_180007B7B
0x180007b66  mov     rdx, rdi
0x180007b69  mov     rcx, [rsp+28h+arg_18]
0x180007b6e  call    ?CreateInstance@?$ProjectionIterator@VConfigLocationToRawConfigSelector@@@@SAJPEAUIXPathNodeIterator@@PEAPEAUIUnknown@@@Z; ProjectionIterator<ConfigLocationToRawConfigSelector>::CreateInstance(IXPathNodeIterator *,IUnknown * *)
0x180007b73  mov     ebx, eax
0x180007b75  test    eax, eax
0x180007b77  js      short loc_180007B7B
0x180007b79  xor     ebx, ebx
0x180007b7b  lea     rcx, [rsp+28h+arg_18]
0x180007b80  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007b85  mov     eax, ebx
0x180007b87  mov     rbx, [rsp+28h+arg_0]
0x180007b8c  add     rsp, 20h
0x180007b90  pop     rdi
0x180007b91  retn
```
