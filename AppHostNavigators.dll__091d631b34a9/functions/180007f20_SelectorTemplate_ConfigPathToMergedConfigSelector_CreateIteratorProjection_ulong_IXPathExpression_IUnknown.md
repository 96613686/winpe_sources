# SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateIteratorProjection(ulong,IXPathExpression * *,IUnknown * *)

- ea: `0x180007f20`
- end: `0x180007f8c`
- name: `?CreateIteratorProjection@?$SelectorTemplate@VConfigPathToMergedConfigSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180007d88`
- `0x180007f20`
- `0x18000fd68`
- `0x180014010`

## string_xrefs

- `0x180007f57`: `get-config`

## pseudocode

```c
__int64 __fastcall SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateIteratorProjection(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
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
    Instance = ProjectionIterator<ConfigPathToMergedConfigSelector>::CreateInstance(v7, a3);
    if ( Instance >= 0 )
    {
      v5 = 0;
      goto LABEL_7;
    }
  }
  else if ( Instance == -2147467262 )
  {
    Instance = AppHostNavigatorException::SetFunctionInvalidArgumentException(L"get-config");
  }
  v5 = Instance;
LABEL_7:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  return v5;
}

```

## disassembly

```asm
0x180007f20  push    rbx
0x180007f22  sub     rsp, 20h
0x180007f26  mov     rbx, r8
0x180007f29  mov     [rsp+28h+arg_8], 0
0x180007f32  mov     rcx, [rdx]
0x180007f35  mov     rax, [rcx]
0x180007f38  lea     r8, [rsp+28h+arg_8]
0x180007f3d  lea     rdx, _GUID_d97fe0e8_dc26_49c3_82e2_da894705a4ac
0x180007f44  mov     rax, [rax]
0x180007f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f4c  test    eax, eax
0x180007f4e  jns     short loc_180007F67
0x180007f50  cmp     eax, 80004002h
0x180007f55  jnz     short loc_180007F63
0x180007f57  lea     rcx, aGetConfig; "get-config"
0x180007f5e  call    ?SetFunctionInvalidArgumentException@AppHostNavigatorException@@SAJPEBG@Z; AppHostNavigatorException::SetFunctionInvalidArgumentException(ushort const *)
0x180007f63  mov     ebx, eax
0x180007f65  jmp     short loc_180007F7A
0x180007f67  mov     rdx, rbx
0x180007f6a  mov     rcx, [rsp+28h+arg_8]
0x180007f6f  call    ?CreateInstance@?$ProjectionIterator@VConfigPathToMergedConfigSelector@@@@SAJPEAUIXPathNodeIterator@@PEAPEAUIUnknown@@@Z; ProjectionIterator<ConfigPathToMergedConfigSelector>::CreateInstance(IXPathNodeIterator *,IUnknown * *)
0x180007f74  test    eax, eax
0x180007f76  js      short loc_180007F63
0x180007f78  xor     ebx, ebx
0x180007f7a  lea     rcx, [rsp+28h+arg_8]
0x180007f7f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007f84  mov     eax, ebx
0x180007f86  add     rsp, 20h
0x180007f8a  pop     rbx
0x180007f8b  retn
```
