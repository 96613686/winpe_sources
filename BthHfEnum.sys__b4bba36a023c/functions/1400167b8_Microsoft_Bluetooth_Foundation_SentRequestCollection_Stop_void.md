# Microsoft::Bluetooth::Foundation::SentRequestCollection::Stop(void)

- ea: `0x1400167b8`
- end: `0x1400168d6`
- name: `?Stop@SentRequestCollection@Foundation@Bluetooth@Microsoft@@QEAAXXZ`
- size: `286`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::SentRequestCollection *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140015c9c`
- `0x14002e6e0`
- `0x14002e700`

## callees

- `0x1400167b8`
- `0x14001ae00`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::SentRequestCollection::Stop(
        Microsoft::Bluetooth::Foundation::SentRequestCollection *this)
{
  unsigned int i; // esi
  __int64 v3; // rbx
  __int64 v4; // rdx

  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2528))(WdfDriverGlobals, *(_QWORD *)this);
  for ( i = 0;
        i < (*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 112))(
              WdfDriverGlobals,
              *((_QWORD *)this + 1));
        ++i )
  {
    v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 144))(
           WdfDriverGlobals,
           *((_QWORD *)this + 1),
           i);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1640))(
      WdfDriverGlobals,
      v3,
      0,
      114,
      "onecore\\drivers\\bluetooth\\foundation\\lib\\SentRequestCollection.h");
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2064))(WdfDriverGlobals, v3);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
      WdfDriverGlobals,
      v3,
      0,
      116,
      "onecore\\drivers\\bluetooth\\foundation\\lib\\SentRequestCollection.h");
  }
  v4 = *(_QWORD *)this;
  *((_BYTE *)this + 16) = 1;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2536))(WdfDriverGlobals, v4);
}

```

## disassembly

```asm
0x1400167b8  push    rbx
0x1400167ba  push    rbp
0x1400167bb  push    rsi
0x1400167bc  push    rdi
0x1400167bd  sub     rsp, 38h
0x1400167c1  mov     rax, cs:WdfFunctions_01015
0x1400167c8  mov     rdi, rcx
0x1400167cb  mov     rdx, [rcx]
0x1400167ce  mov     rcx, cs:WdfDriverGlobals
0x1400167d5  mov     rax, [rax+9E0h]
0x1400167dc  call    _guard_dispatch_icall
0x1400167e1  xor     esi, esi
0x1400167e3  lea     rbp, aOnecoreDrivers; "onecore\\drivers\\bluetooth\\foundation"...
0x1400167ea  mov     rax, cs:WdfFunctions_01015
0x1400167f1  mov     rdx, [rdi+8]
0x1400167f5  mov     rcx, cs:WdfDriverGlobals
0x1400167fc  mov     rax, [rax+70h]
0x140016800  call    _guard_dispatch_icall
0x140016805  cmp     esi, eax
0x140016807  jnb     loc_1400168AB
0x14001680d  mov     rax, cs:WdfFunctions_01015
0x140016814  mov     r8d, esi
0x140016817  mov     rdx, [rdi+8]
0x14001681b  mov     rcx, cs:WdfDriverGlobals
0x140016822  mov     rax, [rax+90h]
0x140016829  call    _guard_dispatch_icall
0x14001682e  mov     rcx, cs:WdfFunctions_01015
0x140016835  mov     rbx, rax
0x140016838  mov     r9d, 72h ; 'r'
0x14001683e  mov     [rsp+58h+var_38], rbp
0x140016843  xor     r8d, r8d
0x140016846  mov     rdx, rbx
0x140016849  mov     rax, [rcx+668h]
0x140016850  mov     rcx, cs:WdfDriverGlobals
0x140016857  call    _guard_dispatch_icall
0x14001685c  mov     rcx, cs:WdfFunctions_01015
0x140016863  mov     rdx, rbx
0x140016866  mov     rax, [rcx+810h]
0x14001686d  mov     rcx, cs:WdfDriverGlobals
0x140016874  call    _guard_dispatch_icall
0x140016879  mov     rax, cs:WdfFunctions_01015
0x140016880  mov     r9d, 74h ; 't'
0x140016886  mov     rcx, cs:WdfDriverGlobals
0x14001688d  xor     r8d, r8d
0x140016890  mov     rdx, rbx
0x140016893  mov     [rsp+58h+var_38], rbp
0x140016898  mov     rax, [rax+670h]
0x14001689f  call    _guard_dispatch_icall
0x1400168a4  inc     esi
0x1400168a6  jmp     loc_1400167EA
0x1400168ab  mov     rdx, [rdi]
0x1400168ae  mov     byte ptr [rdi+10h], 1
0x1400168b2  mov     rax, cs:WdfFunctions_01015
0x1400168b9  mov     rcx, cs:WdfDriverGlobals
0x1400168c0  mov     rax, [rax+9E8h]
0x1400168c7  call    _guard_dispatch_icall
0x1400168cc  add     rsp, 38h
0x1400168d0  pop     rdi
0x1400168d1  pop     rsi
0x1400168d2  pop     rbp
0x1400168d3  pop     rbx
0x1400168d4  retn
```
