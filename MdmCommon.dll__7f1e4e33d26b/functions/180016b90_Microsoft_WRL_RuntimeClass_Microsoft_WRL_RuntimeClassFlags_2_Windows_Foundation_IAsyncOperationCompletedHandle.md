# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::`scalar deleting destructor'(uint)

- ea: `0x180016b90`
- end: `0x180016bb8`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001544`
- `0x180016b90`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[3] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180016b90  push    rbx
0x180016b92  sub     rsp, 20h
0x180016b96  mov     dword ptr [rcx+0Ch], 0C0000001h
0x180016b9d  mov     rbx, rcx
0x180016ba0  test    dl, 1
0x180016ba3  jz      short loc_180016BAF
0x180016ba5  mov     edx, 10h; unsigned __int64
0x180016baa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016baf  mov     rax, rbx
0x180016bb2  add     rsp, 20h
0x180016bb6  pop     rbx
0x180016bb7  retn
```
