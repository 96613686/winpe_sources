# BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Graphics::Imaging::SoftwareBitmap *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Imaging::SoftwareBitmap *>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<Windows::Graphics::Imaging::SoftwareBitmap *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Imaging::SoftwareBitmap *> *)

- ea: `0x180017de0`
- end: `0x180017e65`
- name: `?CreateBias@?$BiasHelper@U?$IAsyncOperation@PEAVSoftwareBitmap@Imaging@Graphics@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSoftwareBitmap@Imaging@Graphics@Windows@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@PEAVSoftwareBitmap@Imaging@Graphics@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSoftwareBitmap@Imaging@Graphics@Windows@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@PEAVSoftwareBitmap@Imaging@Graphics@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAVSoftwareBitmap@Imaging@Graphics@Windows@@@56@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017900`
- `0x180017a40`
- `0x18001cfc0`

## callees

- `0x1800019c0`
- `0x180017de0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180017e45`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180017e45`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180017e17`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180017e17`

## pseudocode

```c
LPSTREAM *__fastcall BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Graphics::Imaging::SoftwareBitmap *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Imaging::SoftwareBitmap *>,1>::CreateBias(
        LPSTREAM *ppstm,
        __int64 a2,
        IUnknown *a3,
        __int64 a4)
{
  HRESULT StreamOnHGlobal; // eax

  *ppstm = 0;
  *((_DWORD *)ppstm + 2) = 0;
  if ( a2 && a4 )
  {
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(ppstm);
    StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, ppstm);
    *((_DWORD *)ppstm + 2) = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
      *((_DWORD *)ppstm + 2) = CoMarshalInterface(*ppstm, &GUID_00000000_0000_0000_c000_000000000046, a3, 0, 0, 1u);
  }
  else
  {
    *((_DWORD *)ppstm + 2) = -2147467262;
  }
  return ppstm;
}

```

## disassembly

```asm
0x180017de0  mov     [rsp+arg_0], rbx
0x180017de5  push    rdi
0x180017de6  sub     rsp, 30h
0x180017dea  mov     qword ptr [rcx], 0
0x180017df1  mov     rdi, r8
0x180017df4  mov     dword ptr [rcx+8], 0
0x180017dfb  mov     rbx, rcx
0x180017dfe  test    rdx, rdx
0x180017e01  jz      short loc_180017E50
0x180017e03  test    r9, r9
0x180017e06  jz      short loc_180017E50
0x180017e08  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180017e0d  mov     r8, rbx; ppstm
0x180017e10  mov     edx, 1; fDeleteOnRelease
0x180017e15  xor     ecx, ecx; hGlobal
0x180017e17  call    cs:__imp_CreateStreamOnHGlobal
0x180017e1d  mov     [rbx+8], eax
0x180017e20  test    eax, eax
0x180017e22  js      short loc_180017E57
0x180017e24  mov     rcx, [rbx]; pStm
0x180017e27  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180017e2e  mov     [rsp+38h+mshlflags], 1; mshlflags
0x180017e36  xor     r9d, r9d; dwDestContext
0x180017e39  mov     r8, rdi; pUnk
0x180017e3c  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x180017e45  call    cs:__imp_CoMarshalInterface
0x180017e4b  mov     [rbx+8], eax
0x180017e4e  jmp     short loc_180017E57
0x180017e50  mov     dword ptr [rcx+8], 80004002h
0x180017e57  mov     rax, rbx
0x180017e5a  mov     rbx, [rsp+38h+arg_0]
0x180017e5f  add     rsp, 30h
0x180017e63  pop     rdi
0x180017e64  retn
```
