# GetDeviceMute

- ea: `0x180001cf0`
- end: `0x180001d63`
- name: `GetDeviceMute`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001708`
- `0x180001cf0`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall GetDeviceMute(const unsigned __int16 *a1, _DWORD *a2)
{
  int v3; // ebx
  int v5; // [rsp+40h] [rbp+18h] BYREF
  struct IAudioEndpointVolume *v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  v5 = 0;
  v3 = EndpointVolumeFromDeviceId(a1, &v6);
  if ( v3 >= 0 )
  {
    v3 = ((__int64 (__fastcall *)(struct IAudioEndpointVolume *, int *))v6->lpVtbl->GetMute)(v6, &v5);
    if ( v3 >= 0 )
      *a2 = v5;
  }
  if ( v6 )
    ((void (__fastcall *)(struct IAudioEndpointVolume *))v6->lpVtbl->Release)(v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180001cf0  mov     rax, rsp
0x180001cf3  mov     [rax+8], rbx
0x180001cf7  push    rdi
0x180001cf8  sub     rsp, 20h
0x180001cfc  mov     rdi, rdx
0x180001cff  mov     qword ptr [rax+20h], 0
0x180001d07  lea     rdx, [rax+20h]; struct IAudioEndpointVolume **
0x180001d0b  mov     dword ptr [rax+18h], 0
0x180001d12  call    ?EndpointVolumeFromDeviceId@@YAJPEBGPEAPEAUIAudioEndpointVolume@@@Z; EndpointVolumeFromDeviceId(ushort const *,IAudioEndpointVolume * *)
0x180001d17  mov     ebx, eax
0x180001d19  test    eax, eax
0x180001d1b  js      short loc_180001D3F
0x180001d1d  mov     rcx, [rsp+28h+arg_18]
0x180001d22  lea     rdx, [rsp+28h+arg_10]
0x180001d27  mov     rax, [rcx]
0x180001d2a  mov     rax, [rax+78h]
0x180001d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d33  mov     ebx, eax
0x180001d35  test    eax, eax
0x180001d37  js      short loc_180001D3F
0x180001d39  mov     eax, [rsp+28h+arg_10]
0x180001d3d  mov     [rdi], eax
0x180001d3f  mov     rcx, [rsp+28h+arg_18]
0x180001d44  test    rcx, rcx
0x180001d47  jz      short loc_180001D55
0x180001d49  mov     rax, [rcx]
0x180001d4c  mov     rax, [rax+10h]
0x180001d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d55  mov     eax, ebx
0x180001d57  mov     rbx, [rsp+28h+arg_0]
0x180001d5c  add     rsp, 20h
0x180001d60  pop     rdi
0x180001d61  retn
```
