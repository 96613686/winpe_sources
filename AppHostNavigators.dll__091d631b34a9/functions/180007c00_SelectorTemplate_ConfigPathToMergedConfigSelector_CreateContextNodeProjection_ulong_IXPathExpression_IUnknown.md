# SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateContextNodeProjection(ulong,IXPathExpression * *,IUnknown * *)

- ea: `0x180007c00`
- end: `0x180007c52`
- name: `?CreateContextNodeProjection@?$SelectorTemplate@VConfigPathToMergedConfigSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180007c00`
- `0x180007d88`
- `0x18000e198`

## pseudocode

```c
__int64 __fastcall SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateContextNodeProjection(
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
    Instance = ProjectionIterator<ConfigPathToMergedConfigSelector>::CreateInstance((__int64)v6, a3);
    if ( Instance >= 0 )
      Instance = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180007c00  mov     [rsp+arg_0], rbx
0x180007c05  push    rdi
0x180007c06  sub     rsp, 20h
0x180007c0a  mov     rdi, r8
0x180007c0d  mov     [rsp+28h+arg_18], 0
0x180007c16  lea     rcx, [rsp+28h+arg_18]; struct ContextNodeIterator **
0x180007c1b  call    ?CreateInstance@ContextNodeIterator@@SAJPEAPEAV1@@Z; ContextNodeIterator::CreateInstance(ContextNodeIterator * *)
0x180007c20  mov     ebx, eax
0x180007c22  test    eax, eax
0x180007c24  js      short loc_180007C3B
0x180007c26  mov     rdx, rdi
0x180007c29  mov     rcx, [rsp+28h+arg_18]
0x180007c2e  call    ?CreateInstance@?$ProjectionIterator@VConfigPathToMergedConfigSelector@@@@SAJPEAUIXPathNodeIterator@@PEAPEAUIUnknown@@@Z; ProjectionIterator<ConfigPathToMergedConfigSelector>::CreateInstance(IXPathNodeIterator *,IUnknown * *)
0x180007c33  mov     ebx, eax
0x180007c35  test    eax, eax
0x180007c37  js      short loc_180007C3B
0x180007c39  xor     ebx, ebx
0x180007c3b  lea     rcx, [rsp+28h+arg_18]
0x180007c40  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007c45  mov     eax, ebx
0x180007c47  mov     rbx, [rsp+28h+arg_0]
0x180007c4c  add     rsp, 20h
0x180007c50  pop     rdi
0x180007c51  retn
```
