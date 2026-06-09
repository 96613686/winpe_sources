# Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>::SimpleClassFactory<CreateSystemObjectTask,0>(void)

- ea: `0x140007208`
- end: `0x140007223`
- name: `??0?$SimpleClassFactory@VCreateSystemObjectTask@@$0A@@WRL@Microsoft@@QEAA@XZ`
- size: `27`
- prototype: `_QWORD *()`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400065e8`

## callees

- `0x1400071a8`

## pseudocode

```c
_QWORD *Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>::SimpleClassFactory<CreateSystemObjectTask,0>()
{
  _QWORD *v0; // rcx
  _QWORD *result; // rax

  Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>();
  result = v0;
  *v0 = &Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>::`vftable';
  return result;
}

```

## disassembly

```asm
0x140007208  sub     rsp, 28h
0x14000720c  call    ??0?$ClassFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>(void)
0x140007211  lea     r9, ??_7?$SimpleClassFactory@VCreateSystemObjectTask@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>::`vftable'
0x140007218  mov     rax, rcx
0x14000721b  mov     [rcx], r9
0x14000721e  add     rsp, 28h
0x140007222  retn
```
