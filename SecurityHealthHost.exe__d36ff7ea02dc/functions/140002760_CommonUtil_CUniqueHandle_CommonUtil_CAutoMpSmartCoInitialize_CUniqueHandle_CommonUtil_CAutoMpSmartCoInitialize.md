# CommonUtil::CUniqueHandle<CommonUtil::CAutoMpSmartCoInitialize>::~CUniqueHandle<CommonUtil::CAutoMpSmartCoInitialize>(void)

- ea: `0x140002760`
- end: `0x140002775`
- name: `??1?$CUniqueHandle@UCAutoMpSmartCoInitialize@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000fbb4`

## callees

- `0x140002760`

## import_xrefs

- `ole32!CoUninitialize` at `0x14000276a`
- `ole32!CoUninitialize` at `0x14000276a`

## pseudocode

```c
void __fastcall CommonUtil::CUniqueHandle<CommonUtil::CAutoMpSmartCoInitialize>::~CUniqueHandle<CommonUtil::CAutoMpSmartCoInitialize>(
        _QWORD *a1)
{
  if ( *a1 )
    CoUninitialize();
}

```

## disassembly

```asm
0x140002760  sub     rsp, 28h
0x140002764  cmp     qword ptr [rcx], 0
0x140002768  jz      short loc_140002770
0x14000276a  call    cs:__imp_CoUninitialize
0x140002770  add     rsp, 28h
0x140002774  retn
```
