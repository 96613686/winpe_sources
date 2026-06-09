# SetDeviceMute

- ea: `0x180002070`
- end: `0x1800020d1`
- name: `SetDeviceMute`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001708`
- `0x180002070`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall SetDeviceMute(const unsigned __int16 *a1, unsigned int a2)
{
  int v3; // ebx
  struct IAudioEndpointVolume *v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  v3 = EndpointVolumeFromDeviceId(a1, &v5);
  if ( v3 >= 0 )
    v3 = ((__int64 (__fastcall *)(struct IAudioEndpointVolume *, _QWORD, _QWORD))v5->lpVtbl->SetMute)(v5, a2, 0);
  if ( v5 )
    ((void (__fastcall *)(struct IAudioEndpointVolume *))v5->lpVtbl->Release)(v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002070  mov     [rsp+arg_0], rbx
0x180002075  push    rdi
0x180002076  sub     rsp, 20h
0x18000207a  mov     edi, edx
0x18000207c  mov     [rsp+28h+arg_10], 0
0x180002085  lea     rdx, [rsp+28h+arg_10]; struct IAudioEndpointVolume **
0x18000208a  call    ?EndpointVolumeFromDeviceId@@YAJPEBGPEAPEAUIAudioEndpointVolume@@@Z; EndpointVolumeFromDeviceId(ushort const *,IAudioEndpointVolume * *)
0x18000208f  mov     ebx, eax
0x180002091  test    eax, eax
0x180002093  js      short loc_1800020AD
0x180002095  mov     rcx, [rsp+28h+arg_10]
0x18000209a  xor     r8d, r8d
0x18000209d  mov     edx, edi
0x18000209f  mov     rax, [rcx]
0x1800020a2  mov     rax, [rax+70h]
0x1800020a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ab  mov     ebx, eax
0x1800020ad  mov     rcx, [rsp+28h+arg_10]
0x1800020b2  test    rcx, rcx
0x1800020b5  jz      short loc_1800020C3
0x1800020b7  mov     rax, [rcx]
0x1800020ba  mov     rax, [rax+10h]
0x1800020be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c3  mov     eax, ebx
0x1800020c5  mov     rbx, [rsp+28h+arg_0]
0x1800020ca  add     rsp, 20h
0x1800020ce  pop     rdi
0x1800020cf  retn
```
