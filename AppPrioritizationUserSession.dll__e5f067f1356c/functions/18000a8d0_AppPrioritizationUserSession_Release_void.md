# AppPrioritizationUserSession::Release(void)

- ea: `0x18000a8d0`
- end: `0x18000a8d5`
- name: `?Release@AppPrioritizationUserSession@@UEAAKXZ`
- size: `5`
- prototype: `unsigned int __fastcall(AppPrioritizationUserSession *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a8e0`
- `0x18000a8f0`
- `0x18000a900`
- `0x18000a910`

## callees

- `0x18000a7f0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall AppPrioritizationUserSession::Release(volatile signed __int64 *this)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::Release(this);
}

```

## disassembly

```asm
0x18000a8d0  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAppPrioritizationUserSessionInternal@@UIAppPrioritizationUserSession@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::Release(void)
```
