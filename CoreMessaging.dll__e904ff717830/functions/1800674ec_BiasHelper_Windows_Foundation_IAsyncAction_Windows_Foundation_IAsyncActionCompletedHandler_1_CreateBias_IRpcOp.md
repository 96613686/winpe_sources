# BiasHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncAction *,Windows::Foundation::IAsyncActionCompletedHandler *)

- ea: `0x1800674ec`
- end: `0x180067571`
- name: `?CreateBias@?$BiasHelper@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$00@@SA?AV?$AutoStubBias@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@@@PEAUIRpcOptions@@PEAUIAsyncAction@Foundation@Windows@@PEAUIAsyncActionCompletedHandler@56@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180067fe0`

## callees

- `0x18001df58`
- `0x1800674ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180067566`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180067566`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180067538`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180067538`

## pseudocode

```c
LPSTREAM *__fastcall BiasHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,1>::CreateBias(
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
0x1800674ec  mov     [rsp+arg_0], rbx
0x1800674f1  push    rdi
0x1800674f2  sub     rsp, 30h
0x1800674f6  mov     qword ptr [rcx], 0
0x1800674fd  mov     rdi, r8
0x180067500  mov     dword ptr [rcx+8], 0
0x180067507  mov     rbx, rcx
0x18006750a  test    rdx, rdx
0x18006750d  jnz     short loc_180067524
0x18006750f  mov     dword ptr [rcx+8], 80004002h
0x180067516  mov     rax, rbx
0x180067519  mov     rbx, [rsp+38h+arg_0]
0x18006751e  add     rsp, 30h
0x180067522  pop     rdi
0x180067523  retn
0x180067524  test    r9, r9
0x180067527  jz      short loc_18006750F
0x180067529  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006752e  mov     r8, rbx; ppstm
0x180067531  mov     edx, 1; fDeleteOnRelease
0x180067536  xor     ecx, ecx; hGlobal
0x180067538  call    cs:__imp_CreateStreamOnHGlobal
0x18006753e  mov     [rbx+8], eax
0x180067541  test    eax, eax
0x180067543  js      short loc_180067516
0x180067545  mov     rcx, [rbx]; pStm
0x180067548  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18006754f  mov     [rsp+38h+mshlflags], 1; mshlflags
0x180067557  xor     r9d, r9d; dwDestContext
0x18006755a  mov     r8, rdi; pUnk
0x18006755d  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x180067566  call    cs:__imp_CoMarshalInterface
0x18006756c  mov     [rbx+8], eax
0x18006756f  jmp     short loc_180067516
```
