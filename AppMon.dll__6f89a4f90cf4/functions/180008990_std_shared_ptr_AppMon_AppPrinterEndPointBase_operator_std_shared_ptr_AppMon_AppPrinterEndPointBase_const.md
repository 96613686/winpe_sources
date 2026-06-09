# std::shared_ptr<AppMon::AppPrinterEndPointBase>::operator=(std::shared_ptr<AppMon::AppPrinterEndPointBase> const &)

- ea: `0x180008990`
- end: `0x1800089d7`
- name: `??4?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@QEAAAEAV01@AEBV01@@Z`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1800066cc`
- `0x180008a94`
- `0x180008d9c`
- `0x18000a59c`
- `0x18000a698`
- `0x18000a758`
- `0x18000b6a8`
- `0x18000bafc`
- `0x18000c808`

## callees

- `0x180006344`
- `0x18000798c`
- `0x180008990`

## pseudocode

```c
__int64 *__fastcall std::shared_ptr<AppMon::AppPrinterEndPointBase>::operator=(__int64 *a1, __int64 a2)
{
  __int64 *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r8
  std::_Ref_count_base *v6; // rcx
  _BYTE v8[8]; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v9; // [rsp+28h] [rbp-10h]

  v3 = (__int64 *)std::shared_ptr<AppMon::AppPrinterEndPointBase>::shared_ptr<AppMon::AppPrinterEndPointBase>(v8, a2);
  v4 = *v3;
  *v3 = *a1;
  *a1 = v4;
  v5 = v3[1];
  v3[1] = a1[1];
  v6 = v9;
  a1[1] = v5;
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  return a1;
}

```

## disassembly

```asm
0x180008990  push    rbx
0x180008992  sub     rsp, 30h
0x180008996  mov     rbx, rcx
0x180008999  lea     rcx, [rsp+38h+var_18]
0x18000899e  call    ??0?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<AppMon::AppPrinterEndPointBase>::shared_ptr<AppMon::AppPrinterEndPointBase>(std::shared_ptr<AppMon::AppPrinterEndPointBase> const &)
0x1800089a3  mov     rdx, [rbx]
0x1800089a6  mov     r8, [rax]
0x1800089a9  mov     [rax], rdx
0x1800089ac  mov     [rbx], r8
0x1800089af  mov     rdx, [rbx+8]
0x1800089b3  mov     r8, [rax+8]
0x1800089b7  mov     [rax+8], rdx
0x1800089bb  mov     rcx, [rsp+38h+var_10]; this
0x1800089c0  mov     [rbx+8], r8
0x1800089c4  test    rcx, rcx
0x1800089c7  jz      short loc_1800089CE
0x1800089c9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800089ce  mov     rax, rbx
0x1800089d1  add     rsp, 30h
0x1800089d5  pop     rbx
0x1800089d6  retn
```
