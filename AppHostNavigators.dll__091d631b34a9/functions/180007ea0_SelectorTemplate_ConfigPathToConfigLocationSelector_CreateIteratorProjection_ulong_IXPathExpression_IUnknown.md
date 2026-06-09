# SelectorTemplate<ConfigPathToConfigLocationSelector>::CreateIteratorProjection(ulong,IXPathExpression * *,IUnknown * *)

- ea: `0x180007ea0`
- end: `0x180007f0c`
- name: `?CreateIteratorProjection@?$SelectorTemplate@VConfigPathToConfigLocationSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180007cf0`
- `0x180007ea0`
- `0x18000fd68`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall SelectorTemplate<ConfigPathToConfigLocationSelector>::CreateIteratorProjection(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int Instance; // eax
  unsigned int v5; // ebx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a2)(
               *a2,
               &GUID_d97fe0e8_dc26_49c3_82e2_da894705a4ac,
               &v7);
  if ( Instance >= 0 )
  {
    Instance = ProjectionIterator<ConfigPathToConfigLocationSelector>::CreateInstance(v7, a3);
    if ( Instance >= 0 )
    {
      v5 = 0;
      goto LABEL_7;
    }
  }
  else if ( Instance == -2147467262 )
  {
    Instance = AppHostNavigatorException::SetFunctionInvalidArgumentException(L"get-locations");
  }
  v5 = Instance;
LABEL_7:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  return v5;
}

```

## disassembly

```asm
0x180007ea0  push    rbx
0x180007ea2  sub     rsp, 20h
0x180007ea6  mov     rbx, r8
0x180007ea9  mov     [rsp+28h+arg_8], 0
0x180007eb2  mov     rcx, [rdx]
0x180007eb5  mov     rax, [rcx]
0x180007eb8  lea     r8, [rsp+28h+arg_8]
0x180007ebd  lea     rdx, _GUID_d97fe0e8_dc26_49c3_82e2_da894705a4ac
0x180007ec4  mov     rax, [rax]
0x180007ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ecc  test    eax, eax
0x180007ece  jns     short loc_180007EE7
0x180007ed0  cmp     eax, 80004002h
0x180007ed5  jnz     short loc_180007EE3
0x180007ed7  lea     rcx, aGetLocations; "get-locations"
0x180007ede  call    ?SetFunctionInvalidArgumentException@AppHostNavigatorException@@SAJPEBG@Z; AppHostNavigatorException::SetFunctionInvalidArgumentException(ushort const *)
0x180007ee3  mov     ebx, eax
0x180007ee5  jmp     short loc_180007EFA
0x180007ee7  mov     rdx, rbx
0x180007eea  mov     rcx, [rsp+28h+arg_8]
0x180007eef  call    ?CreateInstance@?$ProjectionIterator@VConfigPathToConfigLocationSelector@@@@SAJPEAUIXPathNodeIterator@@PEAPEAUIUnknown@@@Z; ProjectionIterator<ConfigPathToConfigLocationSelector>::CreateInstance(IXPathNodeIterator *,IUnknown * *)
0x180007ef4  test    eax, eax
0x180007ef6  js      short loc_180007EE3
0x180007ef8  xor     ebx, ebx
0x180007efa  lea     rcx, [rsp+28h+arg_8]
0x180007eff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007f04  mov     eax, ebx
0x180007f06  add     rsp, 20h
0x180007f0a  pop     rbx
0x180007f0b  retn
```
