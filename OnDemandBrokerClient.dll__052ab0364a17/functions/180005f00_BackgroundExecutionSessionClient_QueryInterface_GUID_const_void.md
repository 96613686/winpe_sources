# BackgroundExecutionSessionClient::QueryInterface(_GUID const &,void * *)

- ea: `0x180005f00`
- end: `0x180005f05`
- name: `?QueryInterface@BackgroundExecutionSessionClient@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(__int64 this, const struct _GUID *, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005f10`
- `0x180005f20`
- `0x180005f30`

## callees

- `0x180004eac`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall BackgroundExecutionSessionClient::QueryInterface(__int64 this, const struct _GUID *a2, _QWORD *a3)
{
  return Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable>>(
           this,
           a2,
           a3);
}

```

## disassembly

```asm
0x180005f00  jmp     ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIInspectable@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIInspectable@@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable> *,_GUID const &,void * *)
```
