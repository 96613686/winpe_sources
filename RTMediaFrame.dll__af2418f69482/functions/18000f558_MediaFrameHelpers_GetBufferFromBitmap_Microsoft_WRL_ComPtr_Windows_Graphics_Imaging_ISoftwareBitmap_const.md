# MediaFrameHelpers::GetBufferFromBitmap(Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> const &)

- ea: `0x18000f558`
- end: `0x18000f671`
- name: `?GetBufferFromBitmap@MediaFrameHelpers@@SA?AV?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@AEBV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@34@@Z`
- size: `281`
- prototype: `IMFMediaBuffer **__fastcall(IMFMediaBuffer **ppBuffer)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001ddc`
- `0x18000eef4`
- `0x180022c1c`
- `0x1800230d0`
- `0x1800231cc`

## callees

- `0x1800019c0`
- `0x180005cd0`
- `0x18000f558`
- `0x180021ea0`
- `0x180052010`

## import_xrefs

- `MFPlat!MFCreateWICBitmapBuffer` at `0x18000f60c`
- `MFPlat!MFCreateWICBitmapBuffer` at `0x18000f60c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
IMFMediaBuffer **__fastcall MediaFrameHelpers::GetBufferFromBitmap(IMFMediaBuffer **ppBuffer)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, GUID *, IMFMediaBuffer **); // rbx
  unsigned int v4; // eax
  int v5; // edx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, GUID *, IUnknown **); // rbx
  unsigned int v8; // eax
  int v9; // edx
  unsigned int v10; // eax
  int v11; // edx
  IUnknown *v12; // rcx
  __int64 v13; // rcx
  IUnknown *punkSurface; // [rsp+60h] [rbp+30h] BYREF
  __int64 v16; // [rsp+68h] [rbp+38h] BYREF

  *ppBuffer = 0;
  MF::As<ISoftwareBitmapNative,Windows::Graphics::Imaging::ISoftwareBitmap>(&v16);
  v2 = v16;
  v3 = *(__int64 (__fastcall **)(__int64, GUID *, IMFMediaBuffer **))(*(_QWORD *)v16 + 48LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(ppBuffer);
  v4 = v3(v2, &GUID_045fa593_8799_42b8_bc8d_8968c6453507, ppBuffer);
  if ( v4 == -2147467262 )
  {
    punkSurface = 0;
    v6 = v16;
    v7 = *(__int64 (__fastcall **)(__int64, GUID *, IUnknown **))(*(_QWORD *)v16 + 48LL);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&punkSurface);
    v8 = v7(v6, &GUID_00000121_a8f2_4877_ba0a_fd2b6645fb94, &punkSurface);
    MF::ThrowIfFailed((MF *)v8, v9);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(ppBuffer);
    v10 = MFCreateWICBitmapBuffer(&GUID_00000121_a8f2_4877_ba0a_fd2b6645fb94, punkSurface, ppBuffer);
    MF::ThrowIfFailed((MF *)v10, v11);
    v12 = punkSurface;
    if ( punkSurface )
    {
      punkSurface = 0;
      ((void (__fastcall *)(IUnknown *))v12->lpVtbl->Release)(v12);
    }
  }
  else
  {
    MF::ThrowIfFailed((MF *)v4, v5);
  }
  v13 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return ppBuffer;
}

```

## disassembly

```asm
0x18000f558  mov     [rsp-18h+arg_8], rbx
0x18000f55d  mov     [rsp-18h+arg_0], rcx
0x18000f562  push    rbp
0x18000f563  push    rsi
0x18000f564  push    rdi
0x18000f565  mov     rbp, rsp
0x18000f568  sub     rsp, 30h
0x18000f56c  mov     rsi, rcx
0x18000f56f  mov     [rbp+var_10], 0
0x18000f576  mov     qword ptr [rcx], 0
0x18000f57d  mov     [rbp+var_10], 1
0x18000f584  lea     rcx, [rbp+arg_18]
0x18000f588  call    ??$As@UISoftwareBitmapNative@@UISoftwareBitmap@Imaging@Graphics@Windows@@@MF@@YA?AV?$ComPtr@UISoftwareBitmapNative@@@WRL@Microsoft@@AEBV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@23@@Z; MF::As<ISoftwareBitmapNative,Windows::Graphics::Imaging::ISoftwareBitmap>(Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> const &)
0x18000f58d  nop
0x18000f58e  mov     rdi, [rbp+arg_18]
0x18000f592  mov     rax, [rdi]
0x18000f595  mov     rbx, [rax+30h]
0x18000f599  mov     rcx, rsi
0x18000f59c  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000f5a1  mov     r8, rsi
0x18000f5a4  lea     rdx, _GUID_045fa593_8799_42b8_bc8d_8968c6453507
0x18000f5ab  mov     rcx, rdi
0x18000f5ae  mov     rax, rbx
0x18000f5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5b6  cmp     eax, 80004002h
0x18000f5bb  jnz     short loc_18000F63A
0x18000f5bd  mov     [rbp+punkSurface], 0
0x18000f5c5  mov     rdi, [rbp+arg_18]
0x18000f5c9  mov     rax, [rdi]
0x18000f5cc  mov     rbx, [rax+30h]
0x18000f5d0  lea     rcx, [rbp+punkSurface]
0x18000f5d4  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000f5d9  lea     r8, [rbp+punkSurface]
0x18000f5dd  lea     rdx, _GUID_00000121_a8f2_4877_ba0a_fd2b6645fb94
0x18000f5e4  mov     rcx, rdi
0x18000f5e7  mov     rax, rbx
0x18000f5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5ef  mov     ecx, eax; this
0x18000f5f1  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000f5f6  mov     rcx, rsi
0x18000f5f9  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000f5fe  mov     r8, rsi; ppBuffer
0x18000f601  mov     rdx, [rbp+punkSurface]; punkSurface
0x18000f605  lea     rcx, _GUID_00000121_a8f2_4877_ba0a_fd2b6645fb94; riid
0x18000f60c  call    cs:__imp_MFCreateWICBitmapBuffer
0x18000f612  mov     ecx, eax; this
0x18000f614  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000f619  nop
0x18000f61a  mov     rcx, [rbp+punkSurface]
0x18000f61e  test    rcx, rcx
0x18000f621  jz      short loc_18000F638
0x18000f623  mov     [rbp+punkSurface], 0
0x18000f62b  mov     rax, [rcx]
0x18000f62e  mov     rax, [rax+10h]
0x18000f632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f637  nop
0x18000f638  jmp     short loc_18000F642
0x18000f63a  mov     ecx, eax; this
0x18000f63c  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000f641  nop
0x18000f642  mov     rcx, [rbp+arg_18]
0x18000f646  test    rcx, rcx
0x18000f649  jz      short loc_18000F660
0x18000f64b  mov     [rbp+arg_18], 0
0x18000f653  mov     rax, [rcx]
0x18000f656  mov     rax, [rax+10h]
0x18000f65a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f65f  nop
0x18000f660  mov     rax, rsi
0x18000f663  mov     rbx, [rsp+30h+arg_8]
0x18000f668  add     rsp, 30h
0x18000f66c  pop     rdi
0x18000f66d  pop     rsi
0x18000f66e  pop     rbp
0x18000f66f  retn
```
