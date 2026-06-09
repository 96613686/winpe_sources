# xpsthumbnail::TXpsOMThumbnailGenerator::TXpsOMThumbnailGenerator(void)

- ea: `0x18011a638`
- end: `0x18011a767`
- name: `??0TXpsOMThumbnailGenerator@xpsthumbnail@@QEAA@XZ`
- size: `303`
- prototype: `__int64 __fastcall(xpsthumbnail::TXpsOMThumbnailGenerator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801aab24`

## callees

- `0x18001844c`
- `0x18010a8c4`
- `0x18011a638`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011a6e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011a735`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011a6e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011a735`
- `XpsRasterService!__imp_CreateXpsRasterizationFactory` at `0x18011a694`
- `XpsRasterService!__imp_CreateXpsRasterizationFactory` at `0x18011a694`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
xpsthumbnail::TXpsOMThumbnailGenerator *__fastcall xpsthumbnail::TXpsOMThumbnailGenerator::TXpsOMThumbnailGenerator(
        xpsthumbnail::TXpsOMThumbnailGenerator *this)
{
  LPVOID *v2; // rdi
  LPVOID *v3; // rsi
  int v4; // eax
  int v5; // edx
  const char *v6; // r8
  unsigned int v7; // r9d
  HRESULT v8; // eax
  int v9; // edx
  const char *v10; // r8
  unsigned int v11; // r9d
  HRESULT v12; // eax
  int v13; // edx
  const char *v14; // r8
  unsigned int v15; // r9d
  LPVOID ppv; // [rsp+30h] [rbp-18h] BYREF
  LPVOID *v18; // [rsp+38h] [rbp-10h]

  *(_QWORD *)this = &xpsthumbnail::TXpsOMThumbnailGenerator::`vftable';
  *((_QWORD *)this + 1) = 0;
  v2 = (LPVOID *)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  v3 = (LPVOID *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  ppv = 0;
  v18 = (LPVOID *)((char *)this + 8);
  v4 = CreateXpsRasterizationFactory(&CLSID_XPSRAS_FACTORY, &GUID_e094808a_24c6_482b_a3a7_c21ac9b55f17, &ppv);
  if ( v4 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v4, v5, v6, v7);
  xpsutil::HolderCOM<IWICBitmapScaler>::reset(v18);
  *v18 = ppv;
  ppv = 0;
  v18 = v2;
  v8 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
  if ( v8 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v8, v9, v10, v11);
  xpsutil::HolderCOM<IWICBitmapScaler>::reset(v18);
  *v18 = ppv;
  ppv = 0;
  v18 = v3;
  v12 = CoCreateInstance(
          &GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585,
          0,
          1u,
          &GUID_f9b2a685_a50d_4fc2_b764_b56e093ea0ca,
          &ppv);
  if ( v12 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v12, v13, v14, v15);
  xpsutil::HolderCOM<IWICBitmapScaler>::reset(v18);
  *v18 = ppv;
  return this;
}

```

## disassembly

```asm
0x18011a638  mov     [rsp-20h+arg_0], rcx
0x18011a63d  push    rbp
0x18011a63e  push    rbx
0x18011a63f  push    rsi
0x18011a640  push    rdi
0x18011a641  mov     rbp, rsp
0x18011a644  sub     rsp, 48h
0x18011a648  mov     rbx, rcx
0x18011a64b  lea     rax, ??_7TXpsOMThumbnailGenerator@xpsthumbnail@@6B@; const xpsthumbnail::TXpsOMThumbnailGenerator::`vftable'
0x18011a652  mov     [rcx], rax
0x18011a655  lea     rax, [rcx+8]
0x18011a659  mov     qword ptr [rax], 0
0x18011a660  lea     rdi, [rcx+10h]
0x18011a664  mov     qword ptr [rdi], 0
0x18011a66b  lea     rsi, [rcx+18h]
0x18011a66f  mov     qword ptr [rsi], 0
0x18011a676  mov     [rbp+var_18], 0
0x18011a67e  mov     [rbp+var_10], rax
0x18011a682  lea     r8, [rbp+var_18]
0x18011a686  lea     rdx, _GUID_e094808a_24c6_482b_a3a7_c21ac9b55f17
0x18011a68d  lea     rcx, CLSID_XPSRAS_FACTORY
0x18011a694  call    cs:__imp_CreateXpsRasterizationFactory
0x18011a69a  test    eax, eax
0x18011a69c  jns     short loc_18011A6A6
0x18011a69e  mov     ecx, eax; this
0x18011a6a0  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x18011a6a6  mov     rcx, [rbp+var_10]
0x18011a6aa  call    ?reset@?$HolderCOM@UIWICBitmapScaler@@@xpsutil@@QEAAXXZ; xpsutil::HolderCOM<IWICBitmapScaler>::reset(void)
0x18011a6af  mov     rcx, [rbp+var_10]
0x18011a6b3  mov     rax, [rbp+var_18]
0x18011a6b7  mov     [rcx], rax
0x18011a6ba  mov     [rbp+var_18], 0
0x18011a6c2  mov     [rbp+var_10], rdi
0x18011a6c6  lea     rax, [rbp+var_18]
0x18011a6ca  mov     [rsp+48h+ppv], rax; ppv
0x18011a6cf  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18011a6d6  mov     edi, 1
0x18011a6db  mov     r8d, edi; dwClsContext
0x18011a6de  xor     edx, edx; pUnkOuter
0x18011a6e0  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18011a6e7  call    cs:__imp_CoCreateInstance
0x18011a6ed  test    eax, eax
0x18011a6ef  jns     short loc_18011A6F9
0x18011a6f1  mov     ecx, eax; this
0x18011a6f3  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x18011a6f9  mov     rcx, [rbp+var_10]
0x18011a6fd  call    ?reset@?$HolderCOM@UIWICBitmapScaler@@@xpsutil@@QEAAXXZ; xpsutil::HolderCOM<IWICBitmapScaler>::reset(void)
0x18011a702  mov     rcx, [rbp+var_18]
0x18011a706  mov     rax, [rbp+var_10]
0x18011a70a  mov     [rax], rcx
0x18011a70d  mov     [rbp+var_18], 0
0x18011a715  mov     [rbp+var_10], rsi
0x18011a719  lea     rax, [rbp+var_18]
0x18011a71d  mov     [rsp+48h+ppv], rax; ppv
0x18011a722  lea     r9, _GUID_f9b2a685_a50d_4fc2_b764_b56e093ea0ca; riid
0x18011a729  mov     r8d, edi; dwClsContext
0x18011a72c  xor     edx, edx; pUnkOuter
0x18011a72e  lea     rcx, _GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585; rclsid
0x18011a735  call    cs:__imp_CoCreateInstance
0x18011a73b  test    eax, eax
0x18011a73d  jns     short loc_18011A747
0x18011a73f  mov     ecx, eax; this
0x18011a741  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x18011a747  mov     rcx, [rbp+var_10]
0x18011a74b  call    ?reset@?$HolderCOM@UIWICBitmapScaler@@@xpsutil@@QEAAXXZ; xpsutil::HolderCOM<IWICBitmapScaler>::reset(void)
0x18011a750  mov     rcx, [rbp+var_18]
0x18011a754  mov     rax, [rbp+var_10]
0x18011a758  mov     [rax], rcx
0x18011a75b  mov     rax, rbx
0x18011a75e  add     rsp, 48h
0x18011a762  pop     rdi
0x18011a763  pop     rsi
0x18011a764  pop     rbx
0x18011a765  pop     rbp
0x18011a766  retn
```
