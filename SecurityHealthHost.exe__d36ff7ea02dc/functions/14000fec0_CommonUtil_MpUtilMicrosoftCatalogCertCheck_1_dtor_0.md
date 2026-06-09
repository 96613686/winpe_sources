# _CommonUtil::MpUtilMicrosoftCatalogCertCheck_::_1_::dtor$0

- ea: `0x14000fec0`
- end: `0x14000fecc`
- name: `_CommonUtil::MpUtilMicrosoftCatalogCertCheck_::_1_::dtor$0`
- size: `12`
- prototype: `BOOL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000ed68`

## pseudocode

```c
BOOL __fastcall CommonUtil::MpUtilMicrosoftCatalogCertCheck_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CommonUtil::CAutoUniqueWinHandle<CommonUtil::CAutoWinFileTag,-1>::~CAutoUniqueWinHandle<CommonUtil::CAutoWinFileTag,-1>((HANDLE *)(a2 + 80));
}

```

## disassembly

```asm
0x14000fec0  lea     rcx, [rdx+50h]
0x14000fec7  jmp     ??1?$CAutoUniqueWinHandle@UCAutoWinFileTag@CommonUtil@@$0?0@CommonUtil@@QEAA@XZ; CommonUtil::CAutoUniqueWinHandle<CommonUtil::CAutoWinFileTag,-1>::~CAutoUniqueWinHandle<CommonUtil::CAutoWinFileTag,-1>(void)
```
