# Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreDispatcher>::As<Windows::UI::Core::ICoreAcceleratorKeys>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreAcceleratorKeys>>)

- ea: `0x140006c44`
- end: `0x140006c8d`
- name: `??$As@UICoreAcceleratorKeys@Core@UI@Windows@@@?$ComPtr@UICoreDispatcher@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoreAcceleratorKeys@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007080`
- `0x1400082a8`

## callees

- `0x140003a8c`
- `0x140014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreDispatcher>::As<Windows::UI::Core::ICoreAcceleratorKeys>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        __int64 *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  return v4(v3, &GUID_9ffdf7f5_b8c9_4ef0_b7d2_1de626561fc8, a2);
}

```

## disassembly

```asm
0x140006c44  mov     [rsp+arg_0], rbx
0x140006c49  mov     [rsp+arg_8], rsi
0x140006c4e  push    rdi
0x140006c4f  sub     rsp, 20h
0x140006c53  mov     rbx, rdx
0x140006c56  mov     rsi, [rcx]
0x140006c59  mov     rax, [rsi]
0x140006c5c  mov     rdi, [rax]
0x140006c5f  mov     rcx, rdx
0x140006c62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140006c67  mov     r8, rbx
0x140006c6a  lea     rdx, _GUID_9ffdf7f5_b8c9_4ef0_b7d2_1de626561fc8
0x140006c71  mov     rcx, rsi
0x140006c74  mov     rax, rdi
0x140006c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c7c  nop
0x140006c7d  mov     rbx, [rsp+28h+arg_0]
0x140006c82  mov     rsi, [rsp+28h+arg_8]
0x140006c87  add     rsp, 20h
0x140006c8b  pop     rdi
0x140006c8c  retn
```
