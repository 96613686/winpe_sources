# _CMyAtlServiceModuleT_CTieringEngineService_102_::ServiceMain_::_1_::fin$0

- ea: `0x14003fe6f`
- end: `0x14003fecf`
- name: `_CMyAtlServiceModuleT_CTieringEngineService_102_::ServiceMain_::_1_::fin$0`
- size: `96`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400045d0`
- `0x14003fe6f`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003fea5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003fea5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003fec0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003fec0`

## pseudocode

```c
void __fastcall CMyAtlServiceModuleT_CTieringEngineService_102_::ServiceMain_::_1_::fin_0(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx

  v3 = *(_QWORD *)(a2 + 80);
  if ( *(_QWORD *)(v3 + 616) )
  {
    CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(v3, 1);
    *(_QWORD *)(v3 + 616) = 0;
  }
  if ( *(_BYTE *)(a2 + 32) )
  {
    CoUninitialize();
    *(_BYTE *)(v3 + 98) = 0;
  }
  if ( *(_QWORD *)(v3 + 656) )
    SetEvent(*(HANDLE *)(v3 + 656));
}

```

## disassembly

```asm
0x14003fe6f  push    rbx
0x14003fe71  push    rbp
0x14003fe72  sub     rsp, 28h
0x14003fe76  mov     rbp, rdx
0x14003fe79  mov     rbx, [rbp+50h]
0x14003fe7d  cmp     qword ptr [rbx+268h], 0
0x14003fe85  jz      short loc_14003FE9F
0x14003fe87  mov     edx, 1
0x14003fe8c  mov     rcx, rbx
0x14003fe8f  call    ?SetServiceStatus@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXK@Z; CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(ulong)
0x14003fe94  mov     qword ptr [rbx+268h], 0
0x14003fe9f  cmp     byte ptr [rbp+20h], 0
0x14003fea3  jz      short loc_14003FEAF
0x14003fea5  call    cs:__imp_CoUninitialize
0x14003feab  mov     byte ptr [rbx+62h], 0
0x14003feaf  cmp     qword ptr [rbx+290h], 0
0x14003feb7  jz      short loc_14003FEC7
0x14003feb9  mov     rcx, [rbx+290h]; hEvent
0x14003fec0  call    cs:__imp_SetEvent
0x14003fec6  nop
0x14003fec7  add     rsp, 28h
0x14003fecb  pop     rbp
0x14003fecc  pop     rbx
0x14003fecd  retn
```
