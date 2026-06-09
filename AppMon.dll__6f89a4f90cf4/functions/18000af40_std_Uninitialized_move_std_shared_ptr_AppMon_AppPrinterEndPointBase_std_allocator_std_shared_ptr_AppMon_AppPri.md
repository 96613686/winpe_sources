# std::_Uninitialized_move<std::shared_ptr<AppMon::AppPrinterEndPointBase> *,std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(std::shared_ptr<AppMon::AppPrinterEndPointBase> * const,std::shared_ptr<AppMon::AppPrinterEndPointBase> * const,std::shared_ptr<AppMon::AppPrinterEndPointBase> *,std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>> &)

- ea: `0x18000af40`
- end: `0x18000af91`
- name: `??$_Uninitialized_move@PEAV?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@V?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@2@@std@@YAPEAV?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@0@@Z`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a7f8`
- `0x18000ab8c`

## callees

- `0x1800062c8`
- `0x18000af40`

## pseudocode

```c
_QWORD *__fastcall std::_Uninitialized_move<std::shared_ptr<AppMon::AppPrinterEndPointBase> *,std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *i; // r8

  for ( i = a1; i != a2; i += 2 )
  {
    *a3 = 0;
    a3[1] = 0;
    *a3 = *i;
    a3[1] = i[1];
    a3 += 2;
    *i = 0;
    i[1] = 0;
  }
  std::_Destroy_range<std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x18000af40  push    rbx
0x18000af42  sub     rsp, 20h
0x18000af46  mov     rbx, r8
0x18000af49  mov     r8, rcx
0x18000af4c  cmp     rcx, rdx
0x18000af4f  jz      short loc_18000AF7D
0x18000af51  xor     r9d, r9d
0x18000af54  mov     [rbx], r9
0x18000af57  mov     [rbx+8], r9
0x18000af5b  mov     rax, [r8]
0x18000af5e  mov     [rbx], rax
0x18000af61  mov     rcx, [r8+8]
0x18000af65  mov     [rbx+8], rcx
0x18000af69  add     rbx, 10h
0x18000af6d  mov     [r8], r9
0x18000af70  mov     [r8+8], r9
0x18000af74  add     r8, 10h
0x18000af78  cmp     r8, rdx
0x18000af7b  jnz     short loc_18000AF54
0x18000af7d  mov     rdx, rbx
0x18000af80  mov     rcx, rbx
0x18000af83  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(std::shared_ptr<AppMon::AppPrinterEndPointBase> *,std::shared_ptr<AppMon::AppPrinterEndPointBase> * const,std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>> &)
0x18000af88  mov     rax, rbx
0x18000af8b  add     rsp, 20h
0x18000af8f  pop     rbx
0x18000af90  retn
```
