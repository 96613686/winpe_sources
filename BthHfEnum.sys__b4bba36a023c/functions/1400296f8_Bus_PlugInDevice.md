# Bus_PlugInDevice

- ea: `0x1400296f8`
- end: `0x14002981d`
- name: `Bus_PlugInDevice`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400025d0`

## callees

- `0x14001ae00`
- `0x1400296f8`
- `0x14002a548`

## pseudocode

```c
__int64 __fastcall Bus_PlugInDevice(__int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // rax
  unsigned int Pdo; // ebx

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  v3 = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(v2 + 16),
    0);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1072))(WdfDriverGlobals, a1);
  while ( 1 )
  {
    v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01015 + 1080))(
           WdfDriverGlobals,
           a1,
           v3,
           5);
    v3 = v4;
    if ( !v4 )
      break;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
      WdfDriverGlobals,
      v4,
      off_1400220D8);
  }
  Pdo = Bus_CreatePdo(a1);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1088))(WdfDriverGlobals, a1);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
    WdfDriverGlobals,
    *(_QWORD *)(v2 + 16));
  return Pdo;
}

```

## disassembly

```asm
0x1400296f8  mov     [rsp+arg_0], rbx
0x1400296fd  mov     [rsp+arg_8], rsi
0x140029702  push    rdi
0x140029703  sub     rsp, 30h
0x140029707  mov     rax, cs:WdfFunctions_01015
0x14002970e  mov     rdi, rcx
0x140029711  mov     r8, cs:off_1400220B0
0x140029718  mov     rdx, rcx
0x14002971b  mov     rcx, cs:WdfDriverGlobals
0x140029722  mov     rax, [rax+650h]
0x140029729  call    _guard_dispatch_icall
0x14002972e  mov     rcx, cs:WdfFunctions_01015
0x140029735  mov     rsi, rax
0x140029738  xor     r8d, r8d
0x14002973b  xor     ebx, ebx
0x14002973d  mov     rax, [rcx+9C8h]
0x140029744  mov     rcx, cs:WdfDriverGlobals
0x14002974b  mov     rdx, [rsi+10h]
0x14002974f  call    _guard_dispatch_icall
0x140029754  mov     rcx, cs:WdfFunctions_01015
0x14002975b  mov     rdx, rdi
0x14002975e  mov     rax, [rcx+430h]
0x140029765  mov     rcx, cs:WdfDriverGlobals
0x14002976c  call    _guard_dispatch_icall
0x140029771  mov     rax, cs:WdfFunctions_01015
0x140029778  mov     r9d, 5
0x14002977e  mov     rcx, cs:WdfDriverGlobals
0x140029785  mov     r8, rbx
0x140029788  mov     rdx, rdi
0x14002978b  mov     rax, [rax+438h]
0x140029792  call    _guard_dispatch_icall
0x140029797  mov     rbx, rax
0x14002979a  test    rax, rax
0x14002979d  jz      short loc_1400297C5
0x14002979f  mov     rax, cs:WdfFunctions_01015
0x1400297a6  mov     rdx, rbx
0x1400297a9  mov     r8, cs:off_1400220D8
0x1400297b0  mov     rcx, cs:WdfDriverGlobals
0x1400297b7  mov     rax, [rax+650h]
0x1400297be  call    _guard_dispatch_icall
0x1400297c3  jmp     short loc_140029771
0x1400297c5  mov     rcx, rdi
0x1400297c8  call    Bus_CreatePdo
0x1400297cd  mov     rcx, cs:WdfFunctions_01015
0x1400297d4  mov     ebx, eax
0x1400297d6  mov     rdx, rdi
0x1400297d9  mov     rax, [rcx+440h]
0x1400297e0  mov     rcx, cs:WdfDriverGlobals
0x1400297e7  call    _guard_dispatch_icall
0x1400297ec  mov     rcx, cs:WdfFunctions_01015
0x1400297f3  mov     rdx, [rsi+10h]
0x1400297f7  mov     rax, [rcx+9D0h]
0x1400297fe  mov     rcx, cs:WdfDriverGlobals
0x140029805  call    _guard_dispatch_icall
0x14002980a  mov     rsi, [rsp+38h+arg_8]
0x14002980f  mov     eax, ebx
0x140029811  mov     rbx, [rsp+38h+arg_0]
0x140029816  add     rsp, 30h
0x14002981a  pop     rdi
0x14002981b  retn
```
