# GetDeviceMasterVolumeLevel

- ea: `0x180001c70`
- end: `0x180001ce7`
- name: `GetDeviceMasterVolumeLevel`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001708`
- `0x180001c70`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall GetDeviceMasterVolumeLevel(const unsigned __int16 *a1, int *a2)
{
  int v3; // ebx
  int v5; // [rsp+40h] [rbp+18h] BYREF
  struct IAudioEndpointVolume *v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  v5 = 1065353216;
  v3 = EndpointVolumeFromDeviceId(a1, &v6);
  if ( v3 >= 0 )
  {
    v3 = ((__int64 (__fastcall *)(struct IAudioEndpointVolume *, int *))v6->lpVtbl->GetMasterVolumeLevelScalar)(v6, &v5);
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
0x180001c70  mov     rax, rsp
0x180001c73  mov     [rax+8], rbx
0x180001c77  push    rdi
0x180001c78  sub     rsp, 20h
0x180001c7c  mov     rdi, rdx
0x180001c7f  mov     qword ptr [rax+20h], 0
0x180001c87  lea     rdx, [rax+20h]; struct IAudioEndpointVolume **
0x180001c8b  mov     dword ptr [rax+18h], 3F800000h
0x180001c92  call    ?EndpointVolumeFromDeviceId@@YAJPEBGPEAPEAUIAudioEndpointVolume@@@Z; EndpointVolumeFromDeviceId(ushort const *,IAudioEndpointVolume * *)
0x180001c97  mov     ebx, eax
0x180001c99  test    eax, eax
0x180001c9b  js      short loc_180001CC3
0x180001c9d  mov     rcx, [rsp+28h+arg_18]
0x180001ca2  lea     rdx, [rsp+28h+arg_10]
0x180001ca7  mov     rax, [rcx]
0x180001caa  mov     rax, [rax+48h]
0x180001cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cb3  mov     ebx, eax
0x180001cb5  test    eax, eax
0x180001cb7  js      short loc_180001CC3
0x180001cb9  movss   xmm0, [rsp+28h+arg_10]
0x180001cbf  movss   dword ptr [rdi], xmm0
0x180001cc3  mov     rcx, [rsp+28h+arg_18]
0x180001cc8  test    rcx, rcx
0x180001ccb  jz      short loc_180001CD9
0x180001ccd  mov     rax, [rcx]
0x180001cd0  mov     rax, [rax+10h]
0x180001cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cd9  mov     eax, ebx
0x180001cdb  mov     rbx, [rsp+28h+arg_0]
0x180001ce0  add     rsp, 20h
0x180001ce4  pop     rdi
0x180001ce5  retn
```
