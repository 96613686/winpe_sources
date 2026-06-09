# SelectorTemplate<ConfigPathToConfigLocationSelector>::CreateContextNodeProjection(ulong,IXPathExpression * *,IUnknown * *)

- ea: `0x180007ba0`
- end: `0x180007bf2`
- name: `?CreateContextNodeProjection@?$SelectorTemplate@VConfigPathToConfigLocationSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180007ba0`
- `0x180007cf0`
- `0x18000e198`

## pseudocode

```c
__int64 __fastcall SelectorTemplate<ConfigPathToConfigLocationSelector>::CreateContextNodeProjection(
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
    Instance = ProjectionIterator<ConfigPathToConfigLocationSelector>::CreateInstance((__int64)v6, a3);
    if ( Instance >= 0 )
      Instance = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180007ba0  mov     [rsp+arg_0], rbx
0x180007ba5  push    rdi
0x180007ba6  sub     rsp, 20h
0x180007baa  mov     rdi, r8
0x180007bad  mov     [rsp+28h+arg_18], 0
0x180007bb6  lea     rcx, [rsp+28h+arg_18]; struct ContextNodeIterator **
0x180007bbb  call    ?CreateInstance@ContextNodeIterator@@SAJPEAPEAV1@@Z; ContextNodeIterator::CreateInstance(ContextNodeIterator * *)
0x180007bc0  mov     ebx, eax
0x180007bc2  test    eax, eax
0x180007bc4  js      short loc_180007BDB
0x180007bc6  mov     rdx, rdi
0x180007bc9  mov     rcx, [rsp+28h+arg_18]
0x180007bce  call    ?CreateInstance@?$ProjectionIterator@VConfigPathToConfigLocationSelector@@@@SAJPEAUIXPathNodeIterator@@PEAPEAUIUnknown@@@Z; ProjectionIterator<ConfigPathToConfigLocationSelector>::CreateInstance(IXPathNodeIterator *,IUnknown * *)
0x180007bd3  mov     ebx, eax
0x180007bd5  test    eax, eax
0x180007bd7  js      short loc_180007BDB
0x180007bd9  xor     ebx, ebx
0x180007bdb  lea     rcx, [rsp+28h+arg_18]
0x180007be0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007be5  mov     eax, ebx
0x180007be7  mov     rbx, [rsp+28h+arg_0]
0x180007bec  add     rsp, 20h
0x180007bf0  pop     rdi
0x180007bf1  retn
```
