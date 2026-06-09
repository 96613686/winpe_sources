# BiasHelper<IUnknown,Windows::Internal::INilDelegate,1>::CreateBias(IRpcOptions *,IUnknown *,Windows::Internal::INilDelegate *)

- ea: `0x18001de48`
- end: `0x18001decd`
- name: `?CreateBias@?$BiasHelper@UIUnknown@@UINilDelegate@Internal@Windows@@$00@@SA?AV?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@PEAUIRpcOptions@@PEAUIUnknown@@PEAUINilDelegate@Internal@Windows@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e1c0`
- `0x18001e380`
- `0x1800240a0`

## callees

- `0x180002a3c`
- `0x18001de48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001dead`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001dead`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001de7f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001de7f`

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
0x18001de48  mov     [rsp+arg_0], rbx
0x18001de4d  push    rdi
0x18001de4e  sub     rsp, 30h
0x18001de52  mov     qword ptr [rcx], 0
0x18001de59  mov     rdi, r8
0x18001de5c  mov     dword ptr [rcx+8], 0
0x18001de63  mov     rbx, rcx
0x18001de66  test    rdx, rdx
0x18001de69  jz      short loc_18001DEB8
0x18001de6b  test    r9, r9
0x18001de6e  jz      short loc_18001DEB8
0x18001de70  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001de75  mov     r8, rbx; ppstm
0x18001de78  mov     edx, 1; fDeleteOnRelease
0x18001de7d  xor     ecx, ecx; hGlobal
0x18001de7f  call    cs:__imp_CreateStreamOnHGlobal
0x18001de85  mov     [rbx+8], eax
0x18001de88  test    eax, eax
0x18001de8a  js      short loc_18001DEBF
0x18001de8c  mov     rcx, [rbx]; pStm
0x18001de8f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001de96  mov     [rsp+38h+mshlflags], 1; mshlflags
0x18001de9e  xor     r9d, r9d; dwDestContext
0x18001dea1  mov     r8, rdi; pUnk
0x18001dea4  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x18001dead  call    cs:__imp_CoMarshalInterface
0x18001deb3  mov     [rbx+8], eax
0x18001deb6  jmp     short loc_18001DEBF
0x18001deb8  mov     dword ptr [rcx+8], 80004002h
0x18001debf  mov     rax, rbx
0x18001dec2  mov     rbx, [rsp+38h+arg_0]
0x18001dec7  add     rsp, 30h
0x18001decb  pop     rdi
0x18001decc  retn
```
