# Microsoft::Bluetooth::Foundation::SentRequestCollection::Remove(WDFREQUEST__ *)

- ea: `0x140016214`
- end: `0x14001628b`
- name: `?Remove@SentRequestCollection@Foundation@Bluetooth@Microsoft@@QEAAXPEAUWDFREQUEST__@@@Z`
- size: `119`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::SentRequestCollection *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140016320`
- `0x140016520`
- `0x140016680`
- `0x14002de78`

## callees

- `0x14001ae00`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::SentRequestCollection::Remove(
        Microsoft::Bluetooth::Foundation::SentRequestCollection *this,
        struct WDFREQUEST__ *a2)
{
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2528))(WdfDriverGlobals, *(_QWORD *)this);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, struct WDFREQUEST__ *))(WdfFunctions_01015 + 128))(
    WdfDriverGlobals,
    *((_QWORD *)this + 1),
    a2);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2536))(WdfDriverGlobals, *(_QWORD *)this);
}

```

## disassembly

```asm
0x140016214  mov     [rsp+arg_0], rbx
0x140016219  push    rdi
0x14001621a  sub     rsp, 20h
0x14001621e  mov     rax, cs:WdfFunctions_01015
0x140016225  mov     rbx, rdx
0x140016228  mov     rdx, [rcx]
0x14001622b  mov     rdi, rcx
0x14001622e  mov     rcx, cs:WdfDriverGlobals
0x140016235  mov     rax, [rax+9E0h]
0x14001623c  call    _guard_dispatch_icall
0x140016241  mov     rax, cs:WdfFunctions_01015
0x140016248  mov     r8, rbx
0x14001624b  mov     rdx, [rdi+8]
0x14001624f  mov     rcx, cs:WdfDriverGlobals
0x140016256  mov     rax, [rax+80h]
0x14001625d  call    _guard_dispatch_icall
0x140016262  mov     rax, cs:WdfFunctions_01015
0x140016269  mov     rdx, [rdi]
0x14001626c  mov     rcx, cs:WdfDriverGlobals
0x140016273  mov     rax, [rax+9E8h]
0x14001627a  call    _guard_dispatch_icall
0x14001627f  mov     rbx, [rsp+28h+arg_0]
0x140016284  add     rsp, 20h
0x140016288  pop     rdi
0x140016289  retn
```
