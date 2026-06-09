# EndpointVolumeFromFlow(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,IAudioEndpointVolume * *)

- ea: `0x1800017e8`
- end: `0x1800018c1`
- name: `?EndpointVolumeFromFlow@@YAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@PEAPEAUIAudioEndpointVolume@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001, struct IAudioEndpointVolume **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001d70`
- `0x180001e10`
- `0x1800020e0`

## callees

- `0x1800017e8`
- `0x180003010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180001829`
- `ole32!CoCreateInstance` at `0x180001829`

## pseudocode

```c
__int64 __fastcall EndpointVolumeFromFlow(unsigned int a1, struct IAudioEndpointVolume **a2)
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
    v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v6 + 32LL))(v6, a1, 0, &v5);
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
0x1800017e8  mov     r11, rsp
0x1800017eb  mov     [r11+8], rbx
0x1800017ef  mov     [r11+10h], rsi
0x1800017f3  push    rdi
0x1800017f4  sub     rsp, 30h
0x1800017f8  mov     rsi, rdx
0x1800017fb  mov     qword ptr [r11+20h], 0
0x180001803  xor     edx, edx; pUnkOuter
0x180001805  mov     qword ptr [r11+18h], 0
0x18000180d  mov     edi, ecx
0x18000180f  lea     rax, [r11+20h]
0x180001813  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x18000181a  mov     [r11-18h], rax
0x18000181e  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x180001825  lea     r8d, [rdx+17h]; dwClsContext
0x180001829  call    cs:__imp_CoCreateInstance
0x180001830  nop     dword ptr [rax+rax+00h]
0x180001835  mov     ebx, eax
0x180001837  test    eax, eax
0x180001839  js      short loc_180001882
0x18000183b  mov     rcx, [rsp+38h+arg_18]
0x180001840  lea     r9, [rsp+38h+arg_10]
0x180001845  xor     r8d, r8d
0x180001848  mov     edx, edi
0x18000184a  mov     rax, [rcx]
0x18000184d  mov     rax, [rax+20h]
0x180001851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001856  mov     ebx, eax
0x180001858  test    eax, eax
0x18000185a  js      short loc_180001882
0x18000185c  mov     rcx, [rsp+38h+arg_10]
0x180001861  lea     rdx, _GUID_5cdf2c82_841e_4546_9722_0cf74078229a
0x180001868  xor     r9d, r9d
0x18000186b  mov     [rsp+38h+var_18], rsi
0x180001870  mov     rax, [rcx]
0x180001873  lea     r8d, [r9+17h]
0x180001877  mov     rax, [rax+18h]
0x18000187b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001880  mov     ebx, eax
0x180001882  mov     rcx, [rsp+38h+arg_10]
0x180001887  test    rcx, rcx
0x18000188a  jz      short loc_180001898
0x18000188c  mov     rax, [rcx]
0x18000188f  mov     rax, [rax+10h]
0x180001893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001898  mov     rcx, [rsp+38h+arg_18]
0x18000189d  test    rcx, rcx
0x1800018a0  jz      short loc_1800018AE
0x1800018a2  mov     rax, [rcx]
0x1800018a5  mov     rax, [rax+10h]
0x1800018a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018ae  mov     rsi, [rsp+38h+arg_8]
0x1800018b3  mov     eax, ebx
0x1800018b5  mov     rbx, [rsp+38h+arg_0]
0x1800018ba  add     rsp, 30h
0x1800018be  pop     rdi
0x1800018bf  retn
```
