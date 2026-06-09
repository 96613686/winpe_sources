# IsHardwareVoiceActivationSupported(void)

- ea: `0x14000c470`
- end: `0x14000c553`
- name: `?IsHardwareVoiceActivationSupported@@YAJXZ`
- size: `227`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000c55c`

## callees

- `0x14000c32c`
- `0x14000c37c`
- `0x14000c470`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000c4b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000c4b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 IsHardwareVoiceActivationSupported(void)
{
  HRESULT v0; // ebx
  LPVOID v1; // rdi
  __int64 (__fastcall *v2)(LPVOID, __int64, __int64, struct IMMDeviceCollection **); // rbx
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int v6; // [rsp+50h] [rbp+20h] BYREF
  struct IMMDeviceCollection *v7; // [rsp+58h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+30h] BYREF

  ppv = 0;
  v7 = 0;
  v6 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  v0 = CoCreateInstance(
         &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
         0,
         0x17u,
         &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
         &ppv);
  if ( v0 >= 0 )
  {
    v1 = ppv;
    v2 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64, struct IMMDeviceCollection **))(*(_QWORD *)ppv + 24LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v7);
    v3 = v2(v1, 1, 1, &v7);
    if ( v3 < 0
      || (v3 = ((__int64 (__fastcall *)(struct IMMDeviceCollection *, unsigned int *))v7->lpVtbl->GetCount)(v7, &v6),
          v3 < 0) )
    {
      v0 = v3;
    }
    else
    {
      v4 = 0;
      if ( v6 )
      {
        while ( (int)IsHardwareVoiceActivationSupported(v7, v4) < 0 )
        {
          if ( ++v4 >= v6 )
            goto LABEL_8;
        }
        v0 = 0;
      }
      else
      {
LABEL_8:
        v0 = -2147023728;
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v7);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000c470  push    rbp
0x14000c472  push    rbx
0x14000c473  push    rdi
0x14000c474  mov     rbp, rsp
0x14000c477  sub     rsp, 30h
0x14000c47b  mov     [rbp+arg_10], 0
0x14000c483  mov     [rbp+arg_8], 0
0x14000c48b  mov     [rbp+arg_0], 0
0x14000c492  lea     rcx, [rbp+arg_10]
0x14000c496  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000c49b  lea     rax, [rbp+arg_10]
0x14000c49f  mov     [rsp+30h+ppv], rax; ppv
0x14000c4a4  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x14000c4ab  xor     edx, edx; pUnkOuter
0x14000c4ad  lea     r8d, [rdx+17h]; dwClsContext
0x14000c4b1  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x14000c4b8  call    cs:__imp_CoCreateInstance
0x14000c4be  mov     ebx, eax
0x14000c4c0  test    eax, eax
0x14000c4c2  js      short loc_14000C531
0x14000c4c4  mov     rdi, [rbp+arg_10]
0x14000c4c8  mov     rax, [rdi]
0x14000c4cb  mov     rbx, [rax+18h]
0x14000c4cf  lea     rcx, [rbp+arg_8]
0x14000c4d3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000c4d8  lea     r9, [rbp+arg_8]
0x14000c4dc  mov     edx, 1
0x14000c4e1  mov     r8d, edx
0x14000c4e4  mov     rcx, rdi
0x14000c4e7  mov     rax, rbx
0x14000c4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c4ef  test    eax, eax
0x14000c4f1  jns     short loc_14000C4F7
0x14000c4f3  mov     ebx, eax
0x14000c4f5  jmp     short loc_14000C531
0x14000c4f7  mov     rcx, [rbp+arg_8]
0x14000c4fb  mov     rax, [rcx]
0x14000c4fe  lea     rdx, [rbp+arg_0]
0x14000c502  mov     rax, [rax+18h]
0x14000c506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c50b  test    eax, eax
0x14000c50d  js      short loc_14000C4F3
0x14000c50f  xor     ebx, ebx
0x14000c511  cmp     [rbp+arg_0], ebx
0x14000c514  jbe     short loc_14000C52C
0x14000c516  mov     edx, ebx; unsigned int
0x14000c518  mov     rcx, [rbp+arg_8]; struct IMMDeviceCollection *
0x14000c51c  call    ?IsHardwareVoiceActivationSupported@@YAJPEAUIMMDeviceCollection@@I@Z; IsHardwareVoiceActivationSupported(IMMDeviceCollection *,uint)
0x14000c521  test    eax, eax
0x14000c523  jns     short loc_14000C54E
0x14000c525  inc     ebx
0x14000c527  cmp     ebx, [rbp+arg_0]
0x14000c52a  jb      short loc_14000C516
0x14000c52c  mov     ebx, 80070490h
0x14000c531  lea     rcx, [rbp+arg_8]
0x14000c535  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000c53a  nop
0x14000c53b  lea     rcx, [rbp+arg_10]
0x14000c53f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000c544  mov     eax, ebx
0x14000c546  add     rsp, 30h
0x14000c54a  pop     rdi
0x14000c54b  pop     rbx
0x14000c54c  pop     rbp
0x14000c54d  retn
0x14000c54e  xor     ebx, ebx
0x14000c550  jmp     short loc_14000C531
```
