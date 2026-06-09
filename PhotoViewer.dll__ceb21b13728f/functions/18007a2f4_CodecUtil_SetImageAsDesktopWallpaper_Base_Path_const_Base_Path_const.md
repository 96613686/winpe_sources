# CodecUtil::SetImageAsDesktopWallpaper(Base::Path const &,Base::Path const &)

- ea: `0x18007a2f4`
- end: `0x18007a3b5`
- name: `?SetImageAsDesktopWallpaper@CodecUtil@@YAXAEBVPath@Base@@0@Z`
- size: `193`
- prototype: `void(CodecUtil *__hidden this, const struct Path *, const struct Path *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006f5f4`

## callees

- `0x18000cb74`
- `0x18007a2f4`
- `0x18007a3bc`
- `0x180080010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18007a32a`
- `ole32!CoCreateInstance` at `0x18007a32a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a336`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a37b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a336`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a37b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CodecUtil::SetImageAsDesktopWallpaper(
        CodecUtil *this,
        struct IWICBitmapDecoder *a2,
        const struct Path *a3)
{
  HRESULT Instance; // eax
  int v6; // edx
  int v7; // eax
  int v8; // edx
  const struct Path *v9; // r9
  CodecUtil *v10; // [rsp+60h] [rbp+18h] BYREF
  struct IWICImagingFactory *v11; // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&v10);
  if ( Instance < 0 )
  {
    Base::Throw((Base *)(unsigned int)Instance, v6);
    __debugbreak();
  }
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(CodecUtil *, _QWORD, _QWORD, __int64, _DWORD, struct IWICImagingFactory **))(*(_QWORD *)v10 + 24LL))(
         v10,
         *(_QWORD *)this,
         0,
         0x80000000LL,
         0,
         &v11);
  if ( v7 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v7, v8);
    __debugbreak();
  }
  CodecUtil::SetImageAsDesktopWallpaper(v10, v11, a2, v9);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v11);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v10);
}

```

## disassembly

```asm
0x18007a2f4  mov     r11, rsp
0x18007a2f7  mov     [r11+8], rbx
0x18007a2fb  push    rdi
0x18007a2fc  sub     rsp, 40h
0x18007a300  mov     rbx, rdx
0x18007a303  mov     rdi, rcx
0x18007a306  mov     qword ptr [r11+18h], 0
0x18007a30e  lea     rax, [r11+18h]
0x18007a312  mov     [r11-28h], rax
0x18007a316  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18007a31d  xor     edx, edx; pUnkOuter
0x18007a31f  lea     r8d, [rdx+1]; dwClsContext
0x18007a323  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18007a32a  call    cs:__imp_CoCreateInstance
0x18007a330  test    eax, eax
0x18007a332  jns     short loc_18007A33D
0x18007a334  mov     ecx, eax
0x18007a336  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18007a33c  int     3; Trap to Debugger
0x18007a33d  mov     [rsp+48h+arg_18], 0
0x18007a346  mov     rcx, [rsp+48h+arg_10]
0x18007a34b  mov     rax, [rcx]
0x18007a34e  lea     rdx, [rsp+48h+arg_18]
0x18007a353  mov     [rsp+48h+var_20], rdx
0x18007a358  mov     [rsp+48h+var_28], 0
0x18007a360  mov     r9d, 80000000h
0x18007a366  xor     r8d, r8d
0x18007a369  mov     rdx, [rdi]
0x18007a36c  mov     rax, [rax+18h]
0x18007a370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a375  test    eax, eax
0x18007a377  jns     short loc_18007A382
0x18007a379  mov     ecx, eax
0x18007a37b  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18007a381  int     3; Trap to Debugger
0x18007a382  mov     r8, rbx; struct IWICBitmapDecoder *
0x18007a385  mov     rdx, [rsp+48h+arg_18]; struct IWICImagingFactory *
0x18007a38a  mov     rcx, [rsp+48h+arg_10]; this
0x18007a38f  call    ?SetImageAsDesktopWallpaper@CodecUtil@@YAXPEAUIWICImagingFactory@@PEAUIWICBitmapDecoder@@AEBVPath@Base@@@Z; CodecUtil::SetImageAsDesktopWallpaper(IWICImagingFactory *,IWICBitmapDecoder *,Base::Path const &)
0x18007a394  nop
0x18007a395  lea     rcx, [rsp+48h+arg_18]
0x18007a39a  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18007a39f  nop
0x18007a3a0  lea     rcx, [rsp+48h+arg_10]
0x18007a3a5  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18007a3aa  mov     rbx, [rsp+48h+arg_0]
0x18007a3af  add     rsp, 40h
0x18007a3b3  pop     rdi
0x18007a3b4  retn
```
