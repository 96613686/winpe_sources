# DllGetActivationFactory

- ea: `0x180006b50`
- end: `0x180006b7d`
- name: `DllGetActivationFactory`
- size: `45`
- prototype: `__int64 __fastcall(HSTRING, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002f58`
- `0x180004620`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING a1, _QWORD *a2)
{
  __int64 *v4; // rax
  __int64 v5; // rdx

  v4 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  return Microsoft::WRL::Details::GetActivationFactory<1>((Microsoft::WRL::Details *)v4, v5, a1, a2);
}

```

## disassembly

```asm
0x180006b50  mov     [rsp+arg_0], rbx
0x180006b55  push    rdi
0x180006b56  sub     rsp, 20h
0x180006b5a  mov     rbx, rdx
0x180006b5d  mov     rdi, rcx
0x180006b60  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180006b65  mov     r9, rbx
0x180006b68  mov     r8, rdi
0x180006b6b  mov     rcx, rax; this
0x180006b6e  mov     rbx, [rsp+28h+arg_0]
0x180006b73  add     rsp, 20h
0x180006b77  pop     rdi
0x180006b78  jmp     ??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)
```
