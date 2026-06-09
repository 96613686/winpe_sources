# BiasHelper<IUnknown,Windows::Internal::INilDelegate,1>::CreateBias(IRpcOptions *,IUnknown *,Windows::Internal::INilDelegate *)

- ea: `0x18000f6e8`
- end: `0x18000f76d`
- name: `?CreateBias@?$BiasHelper@UIUnknown@@UINilDelegate@Internal@Windows@@$00@@SA?AV?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@PEAUIRpcOptions@@PEAUIUnknown@@PEAUINilDelegate@Internal@Windows@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001024c`

## callees

- `0x180007630`
- `0x18000f6e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000f74d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000f74d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000f71f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000f71f`

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
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppstm);
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
0x18000f6e8  mov     [rsp+arg_0], rbx
0x18000f6ed  push    rdi
0x18000f6ee  sub     rsp, 30h
0x18000f6f2  mov     qword ptr [rcx], 0
0x18000f6f9  mov     rdi, r8
0x18000f6fc  mov     dword ptr [rcx+8], 0
0x18000f703  mov     rbx, rcx
0x18000f706  test    rdx, rdx
0x18000f709  jz      short loc_18000F758
0x18000f70b  test    r9, r9
0x18000f70e  jz      short loc_18000F758
0x18000f710  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f715  mov     r8, rbx; ppstm
0x18000f718  mov     edx, 1; fDeleteOnRelease
0x18000f71d  xor     ecx, ecx; hGlobal
0x18000f71f  call    cs:__imp_CreateStreamOnHGlobal
0x18000f725  mov     [rbx+8], eax
0x18000f728  test    eax, eax
0x18000f72a  js      short loc_18000F75F
0x18000f72c  mov     rcx, [rbx]; pStm
0x18000f72f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000f736  mov     [rsp+38h+mshlflags], 1; mshlflags
0x18000f73e  xor     r9d, r9d; dwDestContext
0x18000f741  mov     r8, rdi; pUnk
0x18000f744  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x18000f74d  call    cs:__imp_CoMarshalInterface
0x18000f753  mov     [rbx+8], eax
0x18000f756  jmp     short loc_18000F75F
0x18000f758  mov     dword ptr [rcx+8], 80004002h
0x18000f75f  mov     rax, rbx
0x18000f762  mov     rbx, [rsp+38h+arg_0]
0x18000f767  add     rsp, 30h
0x18000f76b  pop     rdi
0x18000f76c  retn
```
