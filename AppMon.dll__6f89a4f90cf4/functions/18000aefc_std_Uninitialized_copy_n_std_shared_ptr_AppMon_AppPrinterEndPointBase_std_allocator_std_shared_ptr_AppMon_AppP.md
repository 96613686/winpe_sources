# std::_Uninitialized_copy_n<std::shared_ptr<AppMon::AppPrinterEndPointBase> *,std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(std::shared_ptr<AppMon::AppPrinterEndPointBase> *,unsigned __int64,std::shared_ptr<AppMon::AppPrinterEndPointBase> *,std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>> &)

- ea: `0x18000aefc`
- end: `0x18000af3a`
- name: `??$_Uninitialized_copy_n@PEAV?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@V?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@2@@std@@YAPEAV?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@0@PEAV10@_K0AEAV?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@0@@Z`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a698`

## callees

- `0x1800062c8`
- `0x180006344`
- `0x18000aefc`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_copy_n<std::shared_ptr<AppMon::AppPrinterEndPointBase> *,std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8

  if ( a2 )
  {
    do
    {
      std::shared_ptr<AppMon::AppPrinterEndPointBase>::shared_ptr<AppMon::AppPrinterEndPointBase>(a3, a1);
      a3 += 16;
      a1 = v6 + 16;
    }
    while ( v7 != 1 );
  }
  std::_Destroy_range<std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x18000aefc  push    rbx
0x18000aefe  sub     rsp, 20h
0x18000af02  mov     rbx, r8
0x18000af05  mov     r8, rdx
0x18000af08  mov     rdx, rcx
0x18000af0b  test    r8, r8
0x18000af0e  jz      short loc_18000AF26
0x18000af10  mov     rcx, rbx
0x18000af13  call    ??0?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<AppMon::AppPrinterEndPointBase>::shared_ptr<AppMon::AppPrinterEndPointBase>(std::shared_ptr<AppMon::AppPrinterEndPointBase> const &)
0x18000af18  add     rbx, 10h
0x18000af1c  add     rdx, 10h
0x18000af20  sub     r8, 1
0x18000af24  jnz     short loc_18000AF10
0x18000af26  mov     rdx, rbx
0x18000af29  mov     rcx, rbx
0x18000af2c  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(std::shared_ptr<AppMon::AppPrinterEndPointBase> *,std::shared_ptr<AppMon::AppPrinterEndPointBase> * const,std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>> &)
0x18000af31  mov     rax, rbx
0x18000af34  add     rsp, 20h
0x18000af38  pop     rbx
0x18000af39  retn
```
