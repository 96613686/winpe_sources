# GetMasterVolumeLevel

- ea: `0x180001d70`
- end: `0x180001e02`
- name: `GetMasterVolumeLevel`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800017e8`
- `0x180001d70`
- `0x180003010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001d95`
- `msvcrt!_wcsicmp` at `0x180001d95`

## pseudocode

```c
__int64 __fastcall GetMasterVolumeLevel(const wchar_t *a1, int *a2)
{
  int v3; // eax
  int v4; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF
  struct IAudioEndpointVolume *v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 1065353216;
  v3 = _wcsicmp(a1, L"Render");
  v4 = EndpointVolumeFromFlow(v3 != 0, &v7);
  if ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(struct IAudioEndpointVolume *, int *))v7->lpVtbl->GetMasterVolumeLevelScalar)(v7, &v6);
    if ( v4 >= 0 )
      *a2 = v6;
  }
  if ( v7 )
    ((void (__fastcall *)(struct IAudioEndpointVolume *))v7->lpVtbl->Release)(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001d70  mov     [rsp+arg_0], rbx
0x180001d75  push    rdi
0x180001d76  sub     rsp, 20h
0x180001d7a  mov     rdi, rdx
0x180001d7d  mov     [rsp+28h+arg_18], 0
0x180001d86  lea     rdx, aRender; "Render"
0x180001d8d  mov     [rsp+28h+arg_10], 3F800000h
0x180001d95  call    cs:__imp__wcsicmp
0x180001d9c  nop     dword ptr [rax+rax+00h]
0x180001da1  xor     ecx, ecx
0x180001da3  lea     rdx, [rsp+28h+arg_18]; struct IAudioEndpointVolume **
0x180001da8  test    eax, eax
0x180001daa  setnz   cl; enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001
0x180001dad  call    ?EndpointVolumeFromFlow@@YAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@PEAPEAUIAudioEndpointVolume@@@Z; EndpointVolumeFromFlow(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,IAudioEndpointVolume * *)
0x180001db2  mov     ebx, eax
0x180001db4  test    eax, eax
0x180001db6  js      short loc_180001DDE
0x180001db8  mov     rcx, [rsp+28h+arg_18]
0x180001dbd  lea     rdx, [rsp+28h+arg_10]
0x180001dc2  mov     rax, [rcx]
0x180001dc5  mov     rax, [rax+48h]
0x180001dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dce  mov     ebx, eax
0x180001dd0  test    eax, eax
0x180001dd2  js      short loc_180001DDE
0x180001dd4  movss   xmm0, [rsp+28h+arg_10]
0x180001dda  movss   dword ptr [rdi], xmm0
0x180001dde  mov     rcx, [rsp+28h+arg_18]
0x180001de3  test    rcx, rcx
0x180001de6  jz      short loc_180001DF4
0x180001de8  mov     rax, [rcx]
0x180001deb  mov     rax, [rax+10h]
0x180001def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001df4  mov     eax, ebx
0x180001df6  mov     rbx, [rsp+28h+arg_0]
0x180001dfb  add     rsp, 20h
0x180001dff  pop     rdi
0x180001e00  retn
```
