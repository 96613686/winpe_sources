# MediaFrameHelpers::ConvertMFMediaBuffer(_GUID const &,Microsoft::WRL::ComPtr<IMFMediaBuffer> const &,_GUID const &,int,int,tagRECT const &)

- ea: `0x180005d10`
- end: `0x180005f73`
- name: `?ConvertMFMediaBuffer@MediaFrameHelpers@@SA?AV?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@AEBU_GUID@@AEBV234@0HHAEBUtagRECT@@@Z`
- size: `611`
- prototype: `__int64 __usercall@<rax>(IMFMediaBuffer **ppBuffer@<rcx>, DWORD, DWORD, struct tagRECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002940`

## callees

- `0x1800019c0`
- `0x180004300`
- `0x180005cd0`
- `0x180005d10`
- `0x1800348dc`
- `0x18003492c`
- `0x180052010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180005d80`
- `MFPlat!MFCreateMediaType` at `0x180005d80`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
IMFMediaBuffer **__fastcall MediaFrameHelpers::ConvertMFMediaBuffer(
        IMFMediaBuffer **ppBuffer,
        _QWORD *a2,
        struct IMFMediaBuffer **a3,
        __int64 a4,
        DWORD dwWidth,
        DWORD dwHeight,
        struct tagRECT *a7)
{
  IMFMediaBuffer **v10; // rsi
  unsigned int v11; // eax
  int v12; // edx
  unsigned int v13; // eax
  int v14; // edx
  unsigned int v15; // eax
  int v16; // edx
  unsigned int v17; // eax
  int v18; // edx
  IMFMediaType *v19; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  IMFMediaType *ppMFType[8]; // [rsp+48h] [rbp-40h] BYREF

  v10 = ppBuffer;
  if ( (dwWidth & 1) != 0 )
  {
    v21 = *(_QWORD *)a4 - *(_QWORD *)&MFVideoFormat_NV12.Data1;
    if ( *(_QWORD *)a4 == *(_QWORD *)&MFVideoFormat_NV12.Data1 )
      v21 = *(_QWORD *)(a4 + 8) - *(_QWORD *)MFVideoFormat_NV12.Data4;
    if ( !v21 )
      goto LABEL_6;
    v22 = *(_QWORD *)a4 - *(_QWORD *)&MFVideoFormat_P010.Data1;
    if ( *(_QWORD *)a4 == *(_QWORD *)&MFVideoFormat_P010.Data1 )
      v22 = *(_QWORD *)(a4 + 8) - *(_QWORD *)MFVideoFormat_P010.Data4;
    if ( !v22 )
      goto LABEL_6;
    ppBuffer = *(IMFMediaBuffer ***)MFVideoFormat_YUY2.Data4;
    v23 = *(_QWORD *)a4 - *(_QWORD *)&MFVideoFormat_YUY2.Data1;
    if ( *(_QWORD *)a4 == *(_QWORD *)&MFVideoFormat_YUY2.Data1 )
      v23 = *(_QWORD *)(a4 + 8) - *(_QWORD *)MFVideoFormat_YUY2.Data4;
    if ( !v23 )
      goto LABEL_6;
    v24 = *a2 - *(_QWORD *)&MFVideoFormat_NV12.Data1;
    if ( *a2 == *(_QWORD *)&MFVideoFormat_NV12.Data1 )
      v24 = a2[1] - *(_QWORD *)MFVideoFormat_NV12.Data4;
    if ( !v24 )
      goto LABEL_6;
    v25 = *a2 - *(_QWORD *)&MFVideoFormat_P010.Data1;
    if ( *a2 == *(_QWORD *)&MFVideoFormat_P010.Data1 )
      v25 = a2[1] - *(_QWORD *)MFVideoFormat_P010.Data4;
    if ( !v25 )
      goto LABEL_6;
    v26 = *a2 - *(_QWORD *)&MFVideoFormat_YUY2.Data1;
    if ( *a2 == *(_QWORD *)&MFVideoFormat_YUY2.Data1 )
      v26 = a2[1] - *(_QWORD *)MFVideoFormat_YUY2.Data4;
    if ( !v26 )
LABEL_6:
      MF::ThrowOriginateError<19>(ppBuffer, L"Width must be even");
  }
  if ( (dwHeight & 1) != 0 )
  {
    v27 = *(_QWORD *)a4 - *(_QWORD *)&MFVideoFormat_NV12.Data1;
    if ( *(_QWORD *)a4 == *(_QWORD *)&MFVideoFormat_NV12.Data1 )
      v27 = *(_QWORD *)(a4 + 8) - *(_QWORD *)MFVideoFormat_NV12.Data4;
    if ( !v27 )
      goto LABEL_7;
    v28 = *(_QWORD *)a4 - *(_QWORD *)&MFVideoFormat_P010.Data1;
    if ( *(_QWORD *)a4 == *(_QWORD *)&MFVideoFormat_P010.Data1 )
      v28 = *(_QWORD *)(a4 + 8) - *(_QWORD *)MFVideoFormat_P010.Data4;
    if ( !v28 )
      goto LABEL_7;
    v29 = *a2 - *(_QWORD *)&MFVideoFormat_NV12.Data1;
    if ( *a2 == *(_QWORD *)&MFVideoFormat_NV12.Data1 )
      v29 = a2[1] - *(_QWORD *)MFVideoFormat_NV12.Data4;
    if ( !v29 )
      goto LABEL_7;
    v30 = *a2 - *(_QWORD *)&MFVideoFormat_P010.Data1;
    if ( *a2 == *(_QWORD *)&MFVideoFormat_P010.Data1 )
      v30 = a2[1] - *(_QWORD *)MFVideoFormat_P010.Data4;
    if ( !v30 )
LABEL_7:
      MF::ThrowOriginateError<20>(ppBuffer, L"Height must be even");
  }
  ppMFType[0] = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(ppMFType);
  v11 = MFCreateMediaType(ppMFType);
  MF::ThrowIfFailed((MF *)v11, v12);
  v13 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType[0]->lpVtbl->SetGUID)(
          ppMFType[0],
          &MF_MT_MAJOR_TYPE,
          &MFMediaType_Video);
  MF::ThrowIfFailed((MF *)v13, v14);
  v15 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD *))ppMFType[0]->lpVtbl->SetGUID)(
          ppMFType[0],
          &MF_MT_SUBTYPE,
          a2);
  MF::ThrowIfFailed((MF *)v15, v16);
  v17 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, unsigned __int64))ppMFType[0]->lpVtbl->SetUINT64)(
          ppMFType[0],
          &MF_MT_FRAME_SIZE,
          dwHeight | ((unsigned __int64)dwWidth << 32));
  MF::ThrowIfFailed((MF *)v17, v18);
  MediaFrameHelpers::ConvertMFMediaBuffer(v10, ppMFType, a3, (DWORD *)a4, dwWidth, dwHeight, a7);
  v19 = ppMFType[0];
  if ( ppMFType[0] )
  {
    ppMFType[0] = 0;
    ((void (__fastcall *)(IMFMediaType *))v19->lpVtbl->Release)(v19);
  }
  return v10;
}

```

## disassembly

```asm
0x180005d10  push    rbx
0x180005d12  push    rbp
0x180005d13  push    rsi
0x180005d14  push    rdi
0x180005d15  push    r14
0x180005d17  push    r15
0x180005d19  sub     rsp, 58h
0x180005d1d  mov     rbx, r9
0x180005d20  mov     r15, r8
0x180005d23  mov     rdi, rdx
0x180005d26  mov     rsi, rcx
0x180005d29  mov     r14d, [rsp+88h+arg_20]
0x180005d31  mov     r9, qword ptr cs:MFVideoFormat_NV12.Data4
0x180005d38  mov     rdx, qword ptr cs:MFVideoFormat_NV12.Data1
0x180005d3f  mov     r11, qword ptr cs:MFVideoFormat_P010.Data4
0x180005d46  mov     r10, qword ptr cs:MFVideoFormat_P010.Data1
0x180005d4d  test    r14b, 1
0x180005d51  jnz     loc_180005E7B
0x180005d57  mov     ebp, [rsp+88h+arg_28]
0x180005d5e  test    bpl, 1
0x180005d62  jnz     loc_180005F0E
0x180005d68  mov     [rsp+88h+ppMFType], 0
0x180005d71  lea     rcx, [rsp+88h+ppMFType]
0x180005d76  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180005d7b  lea     rcx, [rsp+88h+ppMFType]; ppMFType
0x180005d80  call    cs:__imp_MFCreateMediaType
0x180005d86  mov     ecx, eax; this
0x180005d88  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005d8d  mov     rcx, [rsp+88h+ppMFType]
0x180005d92  mov     rax, [rcx]
0x180005d95  lea     r8, MFMediaType_Video
0x180005d9c  lea     rdx, MF_MT_MAJOR_TYPE
0x180005da3  mov     rax, [rax+0C0h]
0x180005daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005daf  mov     ecx, eax; this
0x180005db1  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005db6  mov     rcx, [rsp+88h+ppMFType]
0x180005dbb  mov     rax, [rcx]
0x180005dbe  mov     r8, rdi
0x180005dc1  lea     rdx, MF_MT_SUBTYPE
0x180005dc8  mov     rax, [rax+0C0h]
0x180005dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd4  mov     ecx, eax; this
0x180005dd6  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005ddb  mov     rcx, [rsp+88h+ppMFType]
0x180005de0  mov     r9, [rcx]
0x180005de3  mov     r8, r14
0x180005de6  shl     r8, 20h
0x180005dea  or      r8, rbp
0x180005ded  lea     rdx, MF_MT_FRAME_SIZE
0x180005df4  mov     rax, [r9+0B0h]
0x180005dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e00  mov     ecx, eax; this
0x180005e02  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005e07  mov     rax, [rsp+88h+arg_30]
0x180005e0f  mov     [rsp+88h+var_58], rax; struct tagRECT *
0x180005e14  mov     [rsp+88h+dwHeight], ebp; dwHeight
0x180005e18  mov     [rsp+88h+dwWidth], r14d; dwWidth
0x180005e1d  mov     r9, rbx
0x180005e20  mov     r8, r15
0x180005e23  lea     rdx, [rsp+88h+ppMFType]
0x180005e28  mov     rcx, rsi; ppBuffer
0x180005e2b  call    ?ConvertMFMediaBuffer@MediaFrameHelpers@@SA?AV?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@AEBV?$ComPtr@UIMFMediaType@@@34@AEBV234@AEBU_GUID@@HHAEBUtagRECT@@@Z; MediaFrameHelpers::ConvertMFMediaBuffer(Microsoft::WRL::ComPtr<IMFMediaType> const &,Microsoft::WRL::ComPtr<IMFMediaBuffer> const &,_GUID const &,int,int,tagRECT const &)
0x180005e30  nop
0x180005e31  mov     rcx, [rsp+88h+ppMFType]
0x180005e36  test    rcx, rcx
0x180005e39  jz      short loc_180005E51
0x180005e3b  mov     [rsp+88h+ppMFType], 0
0x180005e44  mov     rax, [rcx]
0x180005e47  mov     rax, [rax+10h]
0x180005e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e50  nop
0x180005e51  mov     rax, rsi
0x180005e54  add     rsp, 58h
0x180005e58  pop     r15
0x180005e5a  pop     r14
0x180005e5c  pop     rdi
0x180005e5d  pop     rsi
0x180005e5e  pop     rbp
0x180005e5f  pop     rbx
0x180005e60  retn
0x180005e61  lea     rdx, aWidthMustBeEve; "Width must be even"
0x180005e68  call    ??$ThrowOriginateError@$0BD@@MF@@YAXJAEAY0BD@$$CBG@Z; MF::ThrowOriginateError<19>(long,ushort const (&)[19])
0x180005e6e  lea     rdx, aHeightMustBeEv; "Height must be even"
0x180005e75  call    ??$ThrowOriginateError@$0BE@@MF@@YAXJAEAY0BE@$$CBG@Z; MF::ThrowOriginateError<20>(long,ushort const (&)[20])
0x180005e7b  mov     rax, [rbx]
0x180005e7e  sub     rax, rdx
0x180005e81  jnz     short loc_180005E8A
0x180005e83  mov     rax, [rbx+8]
0x180005e87  sub     rax, r9
0x180005e8a  test    rax, rax
0x180005e8d  jz      short loc_180005E61
0x180005e8f  mov     rax, [rbx]
0x180005e92  sub     rax, r10
0x180005e95  jnz     short loc_180005E9E
0x180005e97  mov     rax, [rbx+8]
0x180005e9b  sub     rax, r11
0x180005e9e  test    rax, rax
0x180005ea1  jz      short loc_180005E61
0x180005ea3  mov     rax, [rbx]
0x180005ea6  mov     r8, qword ptr cs:MFVideoFormat_YUY2.Data1
0x180005ead  mov     rcx, qword ptr cs:MFVideoFormat_YUY2.Data4
0x180005eb4  sub     rax, r8
0x180005eb7  jnz     short loc_180005EC0
0x180005eb9  mov     rax, [rbx+8]
0x180005ebd  sub     rax, rcx
0x180005ec0  test    rax, rax
0x180005ec3  jz      short loc_180005E61
0x180005ec5  mov     rax, [rdi]
0x180005ec8  sub     rax, rdx
0x180005ecb  jnz     short loc_180005ED4
0x180005ecd  mov     rax, [rdi+8]
0x180005ed1  sub     rax, r9
0x180005ed4  test    rax, rax
0x180005ed7  jz      short loc_180005E61
0x180005ed9  mov     rax, [rdi]
0x180005edc  sub     rax, r10
0x180005edf  jnz     short loc_180005EE8
0x180005ee1  mov     rax, [rdi+8]
0x180005ee5  sub     rax, r11
0x180005ee8  test    rax, rax
0x180005eeb  jz      loc_180005E61
0x180005ef1  mov     rax, [rdi]
0x180005ef4  sub     rax, r8
0x180005ef7  jnz     short loc_180005F00
0x180005ef9  mov     rax, [rdi+8]
0x180005efd  sub     rax, rcx
0x180005f00  test    rax, rax
0x180005f03  jnz     loc_180005D57
0x180005f09  jmp     loc_180005E61
0x180005f0e  mov     rax, [rbx]
0x180005f11  sub     rax, rdx
0x180005f14  jnz     short loc_180005F1D
0x180005f16  mov     rax, [rbx+8]
0x180005f1a  sub     rax, r9
0x180005f1d  test    rax, rax
0x180005f20  jz      loc_180005E6E
0x180005f26  mov     rax, [rbx]
0x180005f29  sub     rax, r10
0x180005f2c  jnz     short loc_180005F35
0x180005f2e  mov     rax, [rbx+8]
0x180005f32  sub     rax, r11
0x180005f35  test    rax, rax
0x180005f38  jz      loc_180005E6E
0x180005f3e  mov     rax, [rdi]
0x180005f41  sub     rax, rdx
0x180005f44  jnz     short loc_180005F4D
0x180005f46  mov     rax, [rdi+8]
0x180005f4a  sub     rax, r9
0x180005f4d  test    rax, rax
0x180005f50  jz      loc_180005E6E
0x180005f56  mov     rax, [rdi]
0x180005f59  sub     rax, r10
0x180005f5c  jnz     short loc_180005F65
0x180005f5e  mov     rax, [rdi+8]
0x180005f62  sub     rax, r11
0x180005f65  test    rax, rax
0x180005f68  jnz     loc_180005D68
0x180005f6e  jmp     loc_180005E6E
```
