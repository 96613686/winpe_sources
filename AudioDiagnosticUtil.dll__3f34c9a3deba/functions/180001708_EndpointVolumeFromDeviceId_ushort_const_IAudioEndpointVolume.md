# EndpointVolumeFromDeviceId(ushort const *,IAudioEndpointVolume * *)

- ea: `0x180001708`
- end: `0x1800017e0`
- name: `?EndpointVolumeFromDeviceId@@YAJPEBGPEAPEAUIAudioEndpointVolume@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IAudioEndpointVolume **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c70`
- `0x180001cf0`
- `0x180002070`

## callees

- `0x180001708`
- `0x180003010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000174a`
- `ole32!CoCreateInstance` at `0x18000174a`

## pseudocode

```c
__int64 __fastcall EndpointVolumeFromDeviceId(const unsigned __int16 *a1, struct IAudioEndpointVolume **a2)
{
  HRESULT v3; // ebx
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF
  LPVOID v6; // [rsp+58h] [rbp+20h] BYREF

  v6 = 0;
  v5 = 0;
  v3 = CoCreateInstance(
         &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
         0,
         0x17u,
         &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
         &v6);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64 *))(*(_QWORD *)v6 + 40LL))(v6, a1, &v5);
    if ( v3 >= 0 )
      v3 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v5 + 24LL))(
             v5,
             &GUID_5cdf2c82_841e_4546_9722_0cf74078229a,
             23);
  }
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180001708  mov     r11, rsp
0x18000170b  mov     [r11+8], rbx
0x18000170f  mov     [r11+10h], rsi
0x180001713  push    rdi
0x180001714  sub     rsp, 30h
0x180001718  mov     rsi, rdx
0x18000171b  mov     qword ptr [r11+20h], 0
0x180001723  xor     edx, edx; pUnkOuter
0x180001725  mov     qword ptr [r11+18h], 0
0x18000172d  mov     rdi, rcx
0x180001730  lea     rax, [r11+20h]
0x180001734  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x18000173b  mov     [r11-18h], rax
0x18000173f  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x180001746  lea     r8d, [rdx+17h]; dwClsContext
0x18000174a  call    cs:__imp_CoCreateInstance
0x180001751  nop     dword ptr [rax+rax+00h]
0x180001756  mov     ebx, eax
0x180001758  test    eax, eax
0x18000175a  js      short loc_1800017A1
0x18000175c  mov     rcx, [rsp+38h+arg_18]
0x180001761  lea     r8, [rsp+38h+arg_10]
0x180001766  mov     rdx, rdi
0x180001769  mov     rax, [rcx]
0x18000176c  mov     rax, [rax+28h]
0x180001770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001775  mov     ebx, eax
0x180001777  test    eax, eax
0x180001779  js      short loc_1800017A1
0x18000177b  mov     rcx, [rsp+38h+arg_10]
0x180001780  lea     rdx, _GUID_5cdf2c82_841e_4546_9722_0cf74078229a
0x180001787  xor     r9d, r9d
0x18000178a  mov     [rsp+38h+var_18], rsi
0x18000178f  mov     rax, [rcx]
0x180001792  lea     r8d, [r9+17h]
0x180001796  mov     rax, [rax+18h]
0x18000179a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000179f  mov     ebx, eax
0x1800017a1  mov     rcx, [rsp+38h+arg_10]
0x1800017a6  test    rcx, rcx
0x1800017a9  jz      short loc_1800017B7
0x1800017ab  mov     rax, [rcx]
0x1800017ae  mov     rax, [rax+10h]
0x1800017b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017b7  mov     rcx, [rsp+38h+arg_18]
0x1800017bc  test    rcx, rcx
0x1800017bf  jz      short loc_1800017CD
0x1800017c1  mov     rax, [rcx]
0x1800017c4  mov     rax, [rax+10h]
0x1800017c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017cd  mov     rsi, [rsp+38h+arg_8]
0x1800017d2  mov     eax, ebx
0x1800017d4  mov     rbx, [rsp+38h+arg_0]
0x1800017d9  add     rsp, 30h
0x1800017dd  pop     rdi
0x1800017de  retn
```
