# std::_Destroy_range<std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(std::shared_ptr<AppMon::AppPrinterEndPointBase> *,std::shared_ptr<AppMon::AppPrinterEndPointBase> * const,std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>> &)

- ea: `0x1800062c8`
- end: `0x1800062ff`
- name: `??$_Destroy_range@V?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@0@@Z`
- size: `55`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180006468`
- `0x180006bb0`
- `0x18000a698`
- `0x18000aefc`
- `0x18000af40`
- `0x18000b4f4`
- `0x18000c0cc`
- `0x18000d5c4`
- `0x18000d628`

## callees

- `0x1800062c8`
- `0x18000798c`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  std::_Ref_count_base *v4; // rcx

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      v4 = *(std::_Ref_count_base **)(v3 + 8);
      if ( v4 )
        std::_Ref_count_base::_Decref(v4);
      v3 += 16;
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x1800062c8  cmp     rcx, rdx
0x1800062cb  jz      short locret_1800062FE
0x1800062cd  mov     [rsp+arg_0], rbx
0x1800062d2  push    rdi
0x1800062d3  sub     rsp, 20h
0x1800062d7  mov     rdi, rdx
0x1800062da  mov     rbx, rcx
0x1800062dd  mov     rcx, [rbx+8]; this
0x1800062e1  test    rcx, rcx
0x1800062e4  jz      short loc_1800062EB
0x1800062e6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800062eb  add     rbx, 10h
0x1800062ef  cmp     rbx, rdi
0x1800062f2  jnz     short loc_1800062DD
0x1800062f4  mov     rbx, [rsp+28h+arg_0]
0x1800062f9  add     rsp, 20h
0x1800062fd  pop     rdi
0x1800062fe  retn
```
