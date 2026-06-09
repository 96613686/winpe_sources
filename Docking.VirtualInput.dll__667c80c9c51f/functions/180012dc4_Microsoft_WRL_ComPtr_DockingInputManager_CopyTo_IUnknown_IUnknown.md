# Microsoft::WRL::ComPtr<DockingInputManager>::CopyTo<IUnknown>(IUnknown * *)

- ea: `0x180012dc4`
- end: `0x180012dfa`
- name: `??$CopyTo@UIUnknown@@@?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEBAJPEAPEAUIUnknown@@@Z`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800130c8`

## callees

- `0x180013ec0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<DockingInputManager>::CopyTo<IUnknown>(_QWORD *a1, __int64 a2)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDockingInputManager,Microsoft::WRL::FtmBase>::QueryInterface(
           *a1,
           &GUID_00000000_0000_0000_c000_000000000046,
           a2);
}

```

## disassembly

```asm
0x180012dc4  mov     [rsp+arg_8], rdx
0x180012dc9  mov     [rsp+arg_0], rcx
0x180012dce  sub     rsp, 38h
0x180012dd2  mov     rax, [rsp+38h+arg_0]
0x180012dd7  mov     rax, [rax]
0x180012dda  mov     [rsp+38h+var_18], rax
0x180012ddf  mov     r8, [rsp+38h+arg_8]
0x180012de4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180012deb  mov     rcx, [rsp+38h+var_18]
0x180012df0  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDockingInputManager@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDockingInputManager,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)
0x180012df5  add     rsp, 38h
0x180012df9  retn
```
