# MediaFrameHelpers::CreateMFMediaType(Windows::Graphics::Imaging::BitmapPixelFormat,uint,uint,Windows::Graphics::Imaging::BitmapAlphaMode)

- ea: `0x18000f678`
- end: `0x18000f776`
- name: `?CreateMFMediaType@MediaFrameHelpers@@SA?AV?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@W4BitmapPixelFormat@Imaging@Graphics@Windows@@IIW4BitmapAlphaMode@678@@Z`
- size: `254`
- prototype: `__int64 __usercall@<rax>(IMFMediaType **ppMFType@<rcx>, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000eef4`
- `0x180022c1c`
- `0x1800231cc`

## callees

- `0x1800019c0`
- `0x180003fcc`
- `0x180005cd0`
- `0x180026920`
- `0x180052010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18000f6da`
- `MFPlat!MFCreateMediaType` at `0x18000f6da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
IMFMediaType **__fastcall MediaFrameHelpers::CreateMFMediaType(
        IMFMediaType **ppMFType,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v5; // rdi
  unsigned int v8; // eax
  int v9; // edx
  unsigned int v10; // eax
  int v11; // edx
  unsigned int v12; // eax
  int v13; // edx
  unsigned int v14; // eax
  int v15; // edx
  _BYTE v17[16]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v18; // [rsp+40h] [rbp-38h] BYREF

  v5 = a4;
  *ppMFType = 0;
  v18 = *(_OWORD *)MediaFrameHelpers::GetMFVideoFormat(v17, a2, a5);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(ppMFType);
  v8 = MFCreateMediaType(ppMFType);
  MF::ThrowIfFailed((MF *)v8, v9);
  v10 = ((__int64 (__fastcall *)(_QWORD, const GUID *, const GUID *))(*ppMFType)->lpVtbl->SetGUID)(
          *ppMFType,
          &MF_MT_MAJOR_TYPE,
          &MFMediaType_Video);
  MF::ThrowIfFailed((MF *)v10, v11);
  v12 = ((__int64 (__fastcall *)(_QWORD, const GUID *, __int128 *))(*ppMFType)->lpVtbl->SetGUID)(
          *ppMFType,
          &MF_MT_SUBTYPE,
          &v18);
  MF::ThrowIfFailed((MF *)v12, v13);
  v14 = ((__int64 (__fastcall *)(_QWORD, const GUID *, unsigned __int64))(*ppMFType)->lpVtbl->SetUINT64)(
          *ppMFType,
          &MF_MT_FRAME_SIZE,
          v5 | ((unsigned __int64)a3 << 32));
  MF::ThrowIfFailed((MF *)v14, v15);
  return ppMFType;
}

```

## disassembly

```asm
0x18000f678  push    rbx
0x18000f67a  push    rsi
0x18000f67b  push    rdi
0x18000f67c  sub     rsp, 60h
0x18000f680  mov     rax, cs:__security_cookie
0x18000f687  xor     rax, rsp
0x18000f68a  mov     [rsp+78h+var_28], rax
0x18000f68f  mov     edi, r9d
0x18000f692  mov     ebx, r8d
0x18000f695  mov     rsi, rcx
0x18000f698  mov     [rsp+78h+var_50], rcx
0x18000f69d  mov     r8d, [rsp+78h+arg_20]
0x18000f6a5  mov     [rsp+78h+var_58], 0
0x18000f6ad  mov     qword ptr [rcx], 0
0x18000f6b4  mov     [rsp+78h+var_58], 1
0x18000f6bc  lea     rcx, [rsp+78h+var_48]
0x18000f6c1  call    ?GetMFVideoFormat@MediaFrameHelpers@@SA?AU_GUID@@W4BitmapPixelFormat@Imaging@Graphics@Windows@@W4BitmapAlphaMode@456@@Z; MediaFrameHelpers::GetMFVideoFormat(Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Graphics::Imaging::BitmapAlphaMode)
0x18000f6c6  movups  xmm0, xmmword ptr [rax]
0x18000f6c9  movdqu  [rsp+78h+var_38], xmm0
0x18000f6cf  mov     rcx, rsi
0x18000f6d2  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000f6d7  mov     rcx, rsi; ppMFType
0x18000f6da  call    cs:__imp_MFCreateMediaType
0x18000f6e0  mov     ecx, eax; this
0x18000f6e2  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000f6e7  mov     rcx, [rsi]
0x18000f6ea  mov     rax, [rcx]
0x18000f6ed  lea     r8, MFMediaType_Video
0x18000f6f4  lea     rdx, MF_MT_MAJOR_TYPE
0x18000f6fb  mov     rax, [rax+0C0h]
0x18000f702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f707  mov     ecx, eax; this
0x18000f709  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000f70e  mov     rcx, [rsi]
0x18000f711  mov     rax, [rcx]
0x18000f714  lea     r8, [rsp+78h+var_38]
0x18000f719  lea     rdx, MF_MT_SUBTYPE
0x18000f720  mov     rax, [rax+0C0h]
0x18000f727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f72c  mov     ecx, eax; this
0x18000f72e  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000f733  mov     rcx, [rsi]
0x18000f736  mov     rax, [rcx]
0x18000f739  mov     r8d, ebx
0x18000f73c  shl     r8, 20h
0x18000f740  or      r8, rdi
0x18000f743  lea     rdx, MF_MT_FRAME_SIZE
0x18000f74a  mov     rax, [rax+0B0h]
0x18000f751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f756  mov     ecx, eax; this
0x18000f758  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000f75d  mov     rax, rsi
0x18000f760  mov     rcx, [rsp+78h+var_28]
0x18000f765  xor     rcx, rsp; StackCookie
0x18000f768  call    __security_check_cookie
0x18000f76d  add     rsp, 60h
0x18000f771  pop     rdi
0x18000f772  pop     rsi
0x18000f773  pop     rbx
0x18000f774  retn
```
