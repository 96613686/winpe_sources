# BiasHelper<IUnknown,Windows::Internal::INilDelegate,1>::CreateBias(IRpcOptions *,IUnknown *,Windows::Internal::INilDelegate *)

- ea: `0x1800158cc`
- end: `0x180015951`
- name: `?CreateBias@?$BiasHelper@UIUnknown@@UINilDelegate@Internal@Windows@@$00@@SA?AV?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@PEAUIRpcOptions@@PEAUIUnknown@@PEAUINilDelegate@Internal@Windows@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800162bc`

## callees

- `0x18000c6c8`
- `0x1800158cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180015903`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180015903`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180015931`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180015931`

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
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(ppstm);
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
0x1800158cc  mov     [rsp+arg_0], rbx
0x1800158d1  push    rdi
0x1800158d2  sub     rsp, 30h
0x1800158d6  mov     qword ptr [rcx], 0
0x1800158dd  mov     rdi, r8
0x1800158e0  mov     dword ptr [rcx+8], 0
0x1800158e7  mov     rbx, rcx
0x1800158ea  test    rdx, rdx
0x1800158ed  jz      short loc_18001593C
0x1800158ef  test    r9, r9
0x1800158f2  jz      short loc_18001593C
0x1800158f4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800158f9  mov     r8, rbx; ppstm
0x1800158fc  mov     edx, 1; fDeleteOnRelease
0x180015901  xor     ecx, ecx; hGlobal
0x180015903  call    cs:__imp_CreateStreamOnHGlobal
0x180015909  mov     [rbx+8], eax
0x18001590c  test    eax, eax
0x18001590e  js      short loc_180015943
0x180015910  mov     rcx, [rbx]; pStm
0x180015913  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001591a  mov     [rsp+38h+mshlflags], 1; mshlflags
0x180015922  xor     r9d, r9d; dwDestContext
0x180015925  mov     r8, rdi; pUnk
0x180015928  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x180015931  call    cs:__imp_CoMarshalInterface
0x180015937  mov     [rbx+8], eax
0x18001593a  jmp     short loc_180015943
0x18001593c  mov     dword ptr [rcx+8], 80004002h
0x180015943  mov     rax, rbx
0x180015946  mov     rbx, [rsp+38h+arg_0]
0x18001594b  add     rsp, 30h
0x18001594f  pop     rdi
0x180015950  retn
```
