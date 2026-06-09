# BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<Windows::Internal::AI::Agents::Mcp::McpAccessStatus> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::AI::Agents::Mcp::McpAccessStatus> *)

- ea: `0x18009b928`
- end: `0x18009b9ad`
- name: `?CreateBias@?$BiasHelper@U?$IAsyncOperation@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@56@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009bb30`
- `0x18009bdcc`

## callees

- `0x18001f5f4`
- `0x18009b928`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18009b95f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18009b95f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18009b98d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18009b98d`

## pseudocode

```c
LPSTREAM *__fastcall BiasHelper<Windows::Foundation::IAsyncOperation<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,1>::CreateBias(
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
0x18009b928  mov     [rsp+arg_0], rbx
0x18009b92d  push    rdi
0x18009b92e  sub     rsp, 30h
0x18009b932  mov     qword ptr [rcx], 0
0x18009b939  mov     rdi, r8
0x18009b93c  mov     dword ptr [rcx+8], 0
0x18009b943  mov     rbx, rcx
0x18009b946  test    rdx, rdx
0x18009b949  jz      short loc_18009B998
0x18009b94b  test    r9, r9
0x18009b94e  jz      short loc_18009B998
0x18009b950  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009b955  mov     r8, rbx; ppstm
0x18009b958  mov     edx, 1; fDeleteOnRelease
0x18009b95d  xor     ecx, ecx; hGlobal
0x18009b95f  call    cs:__imp_CreateStreamOnHGlobal
0x18009b965  mov     [rbx+8], eax
0x18009b968  test    eax, eax
0x18009b96a  js      short loc_18009B99F
0x18009b96c  mov     rcx, [rbx]; pStm
0x18009b96f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18009b976  mov     [rsp+38h+mshlflags], 1; mshlflags
0x18009b97e  xor     r9d, r9d; dwDestContext
0x18009b981  mov     r8, rdi; pUnk
0x18009b984  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x18009b98d  call    cs:__imp_CoMarshalInterface
0x18009b993  mov     [rbx+8], eax
0x18009b996  jmp     short loc_18009B99F
0x18009b998  mov     dword ptr [rcx+8], 80004002h
0x18009b99f  mov     rax, rbx
0x18009b9a2  mov     rbx, [rsp+38h+arg_0]
0x18009b9a7  add     rsp, 30h
0x18009b9ab  pop     rdi
0x18009b9ac  retn
```
