# detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)

- ea: `0x18000e4c4`
- end: `0x18000e500`
- name: `??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ`
- size: `60`
- prototype: ``
- caller_count: `111`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fd0c`
- `0x1800109e0`
- `0x1800169f4`
- `0x180016b74`
- `0x1800185f0`
- `0x180018df4`
- `0x180018f78`
- `0x180019680`
- `0x180019c1c`
- `0x18001ec70`
- `0x1800211f4`
- `0x1800255bc`
- `0x1800266dc`
- `0x180027a3c`
- `0x180028098`
- `0x180028810`
- `0x180028acc`
- `0x180029010`
- `0x18002919c`
- `0x180029538`
- `0x18002990c`
- `0x18002a294`
- `0x18002a684`
- `0x18002ab88`
- `0x18002b2fc`
- `0x18002b6f4`
- `0x18002bcf0`
- `0x18002ca54`
- `0x18002e684`
- `0x18002f6e8`
- `0x180030284`
- `0x180032a94`
- `0x1800336ec`
- `0x180033a70`
- `0x180033c88`
- `0x180033d5c`
- `0x1800345fc`
- `0x1800348a0`
- `0x180034a44`
- `0x18003540c`
- `0x180035864`
- `0x180035e20`
- `0x180035fa4`
- `0x180036674`
- `0x1800368f0`
- `0x180037c20`
- `0x180038078`
- `0x1800393b4`
- `0x180039984`
- `0x180039cd4`

## callees

- `0x18000de7c`
- `0x18000e4c4`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(_QWORD *a1)
{
  int *v1; // rax
  __int64 result; // rax

  if ( *a1 )
  {
    v1 = (int *)a1[1];
    if ( *v1 >= 0 )
    {
      try
      {
        result = std::shared_ptr<ID2D1DeviceContext>::reset<ID2D1DeviceContext,void (*)(IUnknown *),0>();
      }
      catch ( ... )
      {
        result = (__int64)a1;
        *(_DWORD *)a1[1] = -2147024882;
      }
    }
    else
    {
      return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e4c4  mov     [rsp+arg_0], rcx
0x18000e4c9  sub     rsp, 28h
0x18000e4cd  mov     rdx, [rcx]
0x18000e4d0  test    rdx, rdx
0x18000e4d3  jz      short loc_18000E4FB
0x18000e4d5  mov     rax, [rcx+8]
0x18000e4d9  cmp     dword ptr [rax], 0
0x18000e4dc  jge     short loc_18000E4EF
0x18000e4de  mov     rax, [rdx]
0x18000e4e1  mov     rcx, rdx
0x18000e4e4  mov     rax, [rax+10h]
0x18000e4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4ed  jmp     short loc_18000E4FB
0x18000e4ef  mov     rcx, [rcx+10h]
0x18000e4f3  call    ??$reset@UID2D1DeviceContext@@P6AXPEAUIUnknown@@@Z$0A@@?$shared_ptr@UID2D1DeviceContext@@@std@@QEAAXPEAUID2D1DeviceContext@@P6AXPEAUIUnknown@@@Z@Z; std::shared_ptr<ID2D1DeviceContext>::reset<ID2D1DeviceContext,void (*)(IUnknown *),0>(ID2D1DeviceContext *,void (*)(IUnknown *))
0x18000e4f8  nop
0x18000e4f9  jmp     short $+2
0x18000e4fb  add     rsp, 28h
0x18000e4ff  retn
```
