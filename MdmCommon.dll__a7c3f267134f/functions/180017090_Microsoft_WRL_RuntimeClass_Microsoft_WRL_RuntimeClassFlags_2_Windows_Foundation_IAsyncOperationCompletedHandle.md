# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::`scalar deleting destructor'(uint)

- ea: `0x180017090`
- end: `0x1800170b9`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001544`
- `0x180017090`

## pseudocode

```c
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
0x180017090  push    rbx
0x180017092  sub     rsp, 20h
0x180017096  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18001709d  mov     rbx, rcx
0x1800170a0  test    dl, 1
0x1800170a3  jz      short loc_1800170AF
0x1800170a5  mov     edx, 10h; unsigned __int64
0x1800170aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800170af  mov     rax, rbx
0x1800170b2  add     rsp, 20h
0x1800170b6  pop     rbx
0x1800170b7  retn
```
