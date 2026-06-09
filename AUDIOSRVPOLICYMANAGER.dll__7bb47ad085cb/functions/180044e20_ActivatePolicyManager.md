# ActivatePolicyManager

- ea: `0x180044e20`
- end: `0x180044ea6`
- name: `ActivatePolicyManager`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a384`
- `0x180043320`
- `0x180044e20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044e54`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044e54`

## pseudocode

```c
__int64 __fastcall ActivatePolicyManager(__int64 a1, struct IVolumeProvider *a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v5; // rcx
  int Instance; // ebx
  __int64 v7; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  g_VolumeProvider = a2;
  Instance = CoCreateInstance(
               &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
               0,
               3u,
               &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
               &g_DeviceEnumerator);
  if ( Instance < 0 )
  {
    v7 = 94;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return (unsigned int)Instance;
  }
  Instance = Microsoft::WRL::Details::MakeAndInitialize<CWindowsPolicyManager,CWindowsPolicyManager,>(v5);
  if ( Instance < 0 )
  {
    v7 = 96;
    goto LABEL_3;
  }
  *a4 = g_PolicyManager;
  return 0;
}

```

## disassembly

```asm
0x180044e20  mov     [rsp+arg_0], rbx
0x180044e25  push    rdi
0x180044e26  sub     rsp, 30h
0x180044e2a  mov     cs:?g_VolumeProvider@@3PEAUIVolumeProvider@@EA, rdx; IVolumeProvider * g_VolumeProvider
0x180044e31  lea     rax, ?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180044e38  xor     edx, edx; pUnkOuter
0x180044e3a  mov     qword ptr [rsp+38h+ppv], rax; int
0x180044e3f  mov     rdi, r9
0x180044e42  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x180044e49  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180044e50  lea     r8d, [rdx+3]; dwClsContext
0x180044e54  call    cs:__imp_CoCreateInstance
0x180044e5a  mov     ebx, eax
0x180044e5c  test    eax, eax
0x180044e5e  jns     short loc_180044E7D
0x180044e60  mov     edx, 5Eh ; '^'; void *
0x180044e65  mov     rcx, [rsp+38h]; this
0x180044e6a  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x180044e71  mov     r9d, ebx; char *
0x180044e74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044e79  mov     eax, ebx
0x180044e7b  jmp     short loc_180044E9B
0x180044e7d  call    ??$MakeAndInitialize@VCWindowsPolicyManager@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCWindowsPolicyManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CWindowsPolicyManager,CWindowsPolicyManager,>(CWindowsPolicyManager * *)
0x180044e82  mov     ebx, eax
0x180044e84  test    eax, eax
0x180044e86  jns     short loc_180044E8F
0x180044e88  mov     edx, 60h ; '`'
0x180044e8d  jmp     short loc_180044E65
0x180044e8f  mov     rax, cs:?g_PolicyManager@@3PEAVCWindowsPolicyManager@@EA; CWindowsPolicyManager * g_PolicyManager
0x180044e96  mov     [rdi], rax
0x180044e99  xor     eax, eax
0x180044e9b  mov     rbx, [rsp+38h+arg_0]
0x180044ea0  add     rsp, 30h
0x180044ea4  pop     rdi
0x180044ea5  retn
```
