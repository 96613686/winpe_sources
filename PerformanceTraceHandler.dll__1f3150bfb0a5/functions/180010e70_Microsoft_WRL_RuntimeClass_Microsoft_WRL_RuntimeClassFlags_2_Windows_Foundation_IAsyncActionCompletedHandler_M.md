# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vector deleting destructor'(uint)

- ea: `0x180010e70`
- end: `0x180010eaf`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `63`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002fd0`
- `0x180006324`
- `0x180010e70`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[11] = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 8);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010e70  mov     [rsp+arg_0], rbx
0x180010e75  push    rdi
0x180010e76  sub     rsp, 20h
0x180010e7a  mov     rdi, rcx
0x180010e7d  mov     dword ptr [rcx+2Ch], 0C0000001h
0x180010e84  add     rcx, 20h ; ' '
0x180010e88  mov     ebx, edx
0x180010e8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010e8f  test    bl, 1
0x180010e92  jz      short loc_180010EA1
0x180010e94  mov     edx, 30h ; '0'; unsigned __int64
0x180010e99  mov     rcx, rdi; void *
0x180010e9c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010ea1  mov     rbx, [rsp+28h+arg_0]
0x180010ea6  mov     rax, rdi
0x180010ea9  add     rsp, 20h
0x180010ead  pop     rdi
0x180010eae  retn
```
