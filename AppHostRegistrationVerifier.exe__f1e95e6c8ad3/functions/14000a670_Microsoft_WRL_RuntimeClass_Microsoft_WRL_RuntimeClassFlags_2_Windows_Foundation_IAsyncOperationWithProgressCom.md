# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Microsoft::WRL::FtmBase>::`vector deleting destructor'(uint)

- ea: `0x14000a670`
- end: `0x14000a6af`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `63`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x140002504`
- `0x14000a670`
- `0x14000d49c`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Microsoft::WRL::FtmBase>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[11] = -1073741823;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(a1 + 8);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x14000a670  mov     [rsp+arg_0], rbx
0x14000a675  push    rdi
0x14000a676  sub     rsp, 20h
0x14000a67a  mov     rdi, rcx
0x14000a67d  mov     dword ptr [rcx+2Ch], 0C0000001h
0x14000a684  add     rcx, 20h ; ' '
0x14000a688  mov     ebx, edx
0x14000a68a  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000a68f  test    bl, 1
0x14000a692  jz      short loc_14000A6A1
0x14000a694  mov     edx, 30h ; '0'; unsigned __int64
0x14000a699  mov     rcx, rdi; void *
0x14000a69c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000a6a1  mov     rbx, [rsp+28h+arg_0]
0x14000a6a6  mov     rax, rdi
0x14000a6a9  add     rsp, 20h
0x14000a6ad  pop     rdi
0x14000a6ae  retn
```
