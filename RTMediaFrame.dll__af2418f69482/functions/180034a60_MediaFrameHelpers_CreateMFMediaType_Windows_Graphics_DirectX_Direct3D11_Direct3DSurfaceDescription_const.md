# MediaFrameHelpers::CreateMFMediaType(Windows::Graphics::DirectX::Direct3D11::Direct3DSurfaceDescription const &)

- ea: `0x180034a60`
- end: `0x180034b78`
- name: `?CreateMFMediaType@MediaFrameHelpers@@SA?AV?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@AEBUDirect3DSurfaceDescription@Direct3D11@DirectX@Graphics@Windows@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(IMFMediaType **ppMFType)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800227b4`
- `0x180022c1c`
- `0x1800231cc`

## callees

- `0x1800019c0`
- `0x180005cd0`
- `0x180026920`
- `0x1800349d0`
- `0x180034a60`
- `0x18004ca00`
- `0x180052010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180034ad6`
- `MFPlat!MFCreateMediaType` at `0x180034ad6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
IMFMediaType **__fastcall MediaFrameHelpers::CreateMFMediaType(
        IMFMediaType **ppMFType,
        unsigned int *a2,
        struct _GUID *a3)
{
  unsigned int v5; // eax
  int v6; // edx
  unsigned int v7; // eax
  int v8; // edx
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // eax
  int v12; // edx
  DXGI_FORMAT v14[4]; // [rsp+30h] [rbp-28h] BYREF

  *(GUID *)v14 = GUID_00000000_0000_0000_0000_000000000000;
  if ( (int)MFMEDIATYPEUtils::DXGIFormatToSubtype((MFMEDIATYPEUtils *)a2[2], (enum DXGI_FORMAT)v14, a3) < 0 )
    MF::ThrowOriginateError<25>(2147942487LL, L"Unsupported pixel format");
  *ppMFType = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(ppMFType);
  v5 = MFCreateMediaType(ppMFType);
  MF::ThrowIfFailed((MF *)v5, v6);
  v7 = ((__int64 (__fastcall *)(_QWORD, const GUID *, const GUID *))(*ppMFType)->lpVtbl->SetGUID)(
         *ppMFType,
         &MF_MT_MAJOR_TYPE,
         &MFMediaType_Video);
  MF::ThrowIfFailed((MF *)v7, v8);
  v9 = ((__int64 (__fastcall *)(_QWORD, const GUID *, DXGI_FORMAT *))(*ppMFType)->lpVtbl->SetGUID)(
         *ppMFType,
         &MF_MT_SUBTYPE,
         v14);
  MF::ThrowIfFailed((MF *)v9, v10);
  v11 = ((__int64 (__fastcall *)(_QWORD, const GUID *, unsigned __int64))(*ppMFType)->lpVtbl->SetUINT64)(
          *ppMFType,
          &MF_MT_FRAME_SIZE,
          a2[1] | ((unsigned __int64)*a2 << 32));
  MF::ThrowIfFailed((MF *)v11, v12);
  return ppMFType;
}

```

## disassembly

```asm
0x180034a60  mov     [rsp+arg_10], rbx
0x180034a65  push    rdi
0x180034a66  sub     rsp, 50h
0x180034a6a  mov     rax, cs:__security_cookie
0x180034a71  xor     rax, rsp
0x180034a74  mov     [rsp+58h+var_18], rax
0x180034a79  mov     rdi, rdx
0x180034a7c  mov     rbx, rcx
0x180034a7f  mov     [rsp+58h+var_30], rcx
0x180034a84  mov     [rsp+58h+var_38], 0
0x180034a8c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180034a93  movdqu  xmmword ptr [rsp+58h+var_28], xmm0
0x180034a99  lea     rdx, [rsp+58h+var_28]; enum DXGI_FORMAT
0x180034a9e  mov     ecx, [rdi+8]; this
0x180034aa1  call    ?DXGIFormatToSubtype@MFMEDIATYPEUtils@@YAJW4DXGI_FORMAT@@PEAU_GUID@@@Z; MFMEDIATYPEUtils::DXGIFormatToSubtype(DXGI_FORMAT,_GUID *)
0x180034aa6  test    eax, eax
0x180034aa8  jns     short loc_180034ABC
0x180034aaa  lea     rdx, aUnsupportedPix; "Unsupported pixel format"
0x180034ab1  mov     ecx, 80070057h
0x180034ab6  call    ??$ThrowOriginateError@$0BJ@@MF@@YAXJAEAY0BJ@$$CBG@Z; MF::ThrowOriginateError<25>(long,ushort const (&)[25])
0x180034abc  mov     qword ptr [rbx], 0
0x180034ac3  mov     [rsp+58h+var_38], 1
0x180034acb  mov     rcx, rbx
0x180034ace  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180034ad3  mov     rcx, rbx; ppMFType
0x180034ad6  call    cs:__imp_MFCreateMediaType
0x180034adc  mov     ecx, eax; this
0x180034ade  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180034ae3  mov     rcx, [rbx]
0x180034ae6  mov     rax, [rcx]
0x180034ae9  lea     r8, MFMediaType_Video
0x180034af0  lea     rdx, MF_MT_MAJOR_TYPE
0x180034af7  mov     rax, [rax+0C0h]
0x180034afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b03  mov     ecx, eax; this
0x180034b05  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180034b0a  mov     rcx, [rbx]
0x180034b0d  mov     rax, [rcx]
0x180034b10  lea     r8, [rsp+58h+var_28]
0x180034b15  lea     rdx, MF_MT_SUBTYPE
0x180034b1c  mov     rax, [rax+0C0h]
0x180034b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b28  mov     ecx, eax; this
0x180034b2a  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180034b2f  mov     rcx, [rbx]
0x180034b32  mov     rax, [rcx]
0x180034b35  mov     r8d, [rdi]
0x180034b38  shl     r8, 20h
0x180034b3c  mov     edx, [rdi+4]
0x180034b3f  or      r8, rdx
0x180034b42  lea     rdx, MF_MT_FRAME_SIZE
0x180034b49  mov     rax, [rax+0B0h]
0x180034b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b55  mov     ecx, eax; this
0x180034b57  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180034b5c  mov     rax, rbx
0x180034b5f  mov     rcx, [rsp+58h+var_18]
0x180034b64  xor     rcx, rsp; StackCookie
0x180034b67  call    __security_check_cookie
0x180034b6c  mov     rbx, [rsp+58h+arg_10]
0x180034b71  add     rsp, 50h
0x180034b75  pop     rdi
0x180034b76  retn
```
