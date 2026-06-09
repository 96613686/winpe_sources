# AppPrioritizationUserSession::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a2d0`
- end: `0x18000a2d5`
- name: `?QueryInterface@AppPrioritizationUserSession@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(AppPrioritizationUserSession *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a2e0`
- `0x18000a2f0`
- `0x18000a300`
- `0x18000a310`

## callees

- `0x18000a1f0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall AppPrioritizationUserSession::QueryInterface(__int64 this, _DWORD *a2, _QWORD *a3)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::QueryInterface(
           this,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000a2d0  jmp     ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAppPrioritizationUserSessionInternal@@UIAppPrioritizationUserSession@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::QueryInterface(_GUID const &,void * *)
```
