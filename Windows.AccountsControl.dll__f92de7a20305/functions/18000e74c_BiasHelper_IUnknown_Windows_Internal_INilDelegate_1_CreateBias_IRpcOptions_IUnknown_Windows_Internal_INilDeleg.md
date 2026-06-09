# BiasHelper<IUnknown,Windows::Internal::INilDelegate,1>::CreateBias(IRpcOptions *,IUnknown *,Windows::Internal::INilDelegate *)

- ea: `0x18000e74c`
- end: `0x18000e7d1`
- name: `?CreateBias@?$BiasHelper@UIUnknown@@UINilDelegate@Internal@Windows@@$00@@SA?AV?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@PEAUIRpcOptions@@PEAUIUnknown@@PEAUINilDelegate@Internal@Windows@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f2dc`
- `0x180027560`

## callees

- `0x18000e74c`
- `0x180011ffc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000e7b1`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000e7b1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000e783`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000e783`

## pseudocode

```c
LPSTREAM *__fastcall BiasHelper<IUnknown,Windows::Internal::INilDelegate,1>::CreateBias(
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
0x18000e74c  mov     [rsp+arg_0], rbx
0x18000e751  push    rdi
0x18000e752  sub     rsp, 30h
0x18000e756  mov     qword ptr [rcx], 0
0x18000e75d  mov     rdi, r8
0x18000e760  mov     dword ptr [rcx+8], 0
0x18000e767  mov     rbx, rcx
0x18000e76a  test    rdx, rdx
0x18000e76d  jz      short loc_18000E7BC
0x18000e76f  test    r9, r9
0x18000e772  jz      short loc_18000E7BC
0x18000e774  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000e779  mov     r8, rbx; ppstm
0x18000e77c  mov     edx, 1; fDeleteOnRelease
0x18000e781  xor     ecx, ecx; hGlobal
0x18000e783  call    cs:__imp_CreateStreamOnHGlobal
0x18000e789  mov     [rbx+8], eax
0x18000e78c  test    eax, eax
0x18000e78e  js      short loc_18000E7C3
0x18000e790  mov     rcx, [rbx]; pStm
0x18000e793  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000e79a  mov     [rsp+38h+mshlflags], 1; mshlflags
0x18000e7a2  xor     r9d, r9d; dwDestContext
0x18000e7a5  mov     r8, rdi; pUnk
0x18000e7a8  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x18000e7b1  call    cs:__imp_CoMarshalInterface
0x18000e7b7  mov     [rbx+8], eax
0x18000e7ba  jmp     short loc_18000E7C3
0x18000e7bc  mov     dword ptr [rcx+8], 80004002h
0x18000e7c3  mov     rax, rbx
0x18000e7c6  mov     rbx, [rsp+38h+arg_0]
0x18000e7cb  add     rsp, 30h
0x18000e7cf  pop     rdi
0x18000e7d0  retn
```
