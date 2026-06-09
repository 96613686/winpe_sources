# BiasHelper<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<HSTRING__ *> *,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *> *)

- ea: `0x1800759a4`
- end: `0x180075a29`
- name: `?CreateBias@?$BiasHelper@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@56@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800157e0`
- `0x18007604c`
- `0x18007d9e0`
- `0x1800859ac`
- `0x1800a1340`
- `0x1800ca770`

## callees

- `0x18000fa5c`
- `0x1800759a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800759db`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800759db`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180075a09`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180075a09`

## pseudocode

```c
LPSTREAM *__fastcall BiasHelper<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1>::CreateBias(
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
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppstm);
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
0x1800759a4  mov     [rsp+arg_0], rbx
0x1800759a9  push    rdi
0x1800759aa  sub     rsp, 30h
0x1800759ae  mov     qword ptr [rcx], 0
0x1800759b5  mov     rdi, r8
0x1800759b8  mov     dword ptr [rcx+8], 0
0x1800759bf  mov     rbx, rcx
0x1800759c2  test    rdx, rdx
0x1800759c5  jz      short loc_180075A14
0x1800759c7  test    r9, r9
0x1800759ca  jz      short loc_180075A14
0x1800759cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800759d1  mov     r8, rbx; ppstm
0x1800759d4  mov     edx, 1; fDeleteOnRelease
0x1800759d9  xor     ecx, ecx; hGlobal
0x1800759db  call    cs:__imp_CreateStreamOnHGlobal
0x1800759e1  mov     [rbx+8], eax
0x1800759e4  test    eax, eax
0x1800759e6  js      short loc_180075A1B
0x1800759e8  mov     rcx, [rbx]; pStm
0x1800759eb  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800759f2  mov     [rsp+38h+mshlflags], 1; mshlflags
0x1800759fa  xor     r9d, r9d; dwDestContext
0x1800759fd  mov     r8, rdi; pUnk
0x180075a00  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x180075a09  call    cs:__imp_CoMarshalInterface
0x180075a0f  mov     [rbx+8], eax
0x180075a12  jmp     short loc_180075A1B
0x180075a14  mov     dword ptr [rcx+8], 80004002h
0x180075a1b  mov     rax, rbx
0x180075a1e  mov     rbx, [rsp+38h+arg_0]
0x180075a23  add     rsp, 30h
0x180075a27  pop     rdi
0x180075a28  retn
```
