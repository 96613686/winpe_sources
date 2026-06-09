# CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::RemoveAll(void)

- ea: `0x180066d74`
- end: `0x180066dda`
- name: `?RemoveAll@?$CTSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@QEAAXXZ`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180062af4`
- `0x180068ef4`

## callees

- `0x180004c98`
- `0x180066d74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066dae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066dae`

## pseudocode

```c
void __fastcall CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::RemoveAll(
        __int64 a1)
{
  unsigned __int64 *v1; // rdi
  unsigned __int64 i; // rsi

  v1 = (unsigned __int64 *)(a1 + 8);
  if ( *(_QWORD *)a1 )
  {
    for ( i = 0; i < *v1; ++i )
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(*(_QWORD *)a1 + 8 * i);
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 24) = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x180066d74  mov     [rsp+arg_0], rbx
0x180066d79  mov     [rsp+arg_8], rsi
0x180066d7e  push    rdi
0x180066d7f  sub     rsp, 20h
0x180066d83  cmp     qword ptr [rcx], 0
0x180066d87  lea     rdi, [rcx+8]
0x180066d8b  mov     rbx, rcx
0x180066d8e  jz      short loc_180066DBB
0x180066d90  xor     esi, esi
0x180066d92  cmp     [rdi], rsi
0x180066d95  jbe     short loc_180066DAB
0x180066d97  mov     rax, [rbx]
0x180066d9a  lea     rcx, [rax+rsi*8]
0x180066d9e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180066da3  inc     rsi
0x180066da6  cmp     rsi, [rdi]
0x180066da9  jb      short loc_180066D97
0x180066dab  mov     rcx, [rbx]; pv
0x180066dae  call    cs:__imp_CoTaskMemFree
0x180066db4  mov     qword ptr [rbx], 0
0x180066dbb  mov     rsi, [rsp+28h+arg_8]
0x180066dc0  mov     qword ptr [rbx+18h], 0
0x180066dc8  mov     rbx, [rsp+28h+arg_0]
0x180066dcd  mov     qword ptr [rdi], 0
0x180066dd4  add     rsp, 20h
0x180066dd8  pop     rdi
0x180066dd9  retn
```
