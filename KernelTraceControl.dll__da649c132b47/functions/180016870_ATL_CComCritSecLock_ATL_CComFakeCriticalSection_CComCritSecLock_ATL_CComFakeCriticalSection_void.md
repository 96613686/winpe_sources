# ATL::CComCritSecLock<ATL::CComFakeCriticalSection>::~CComCritSecLock<ATL::CComFakeCriticalSection>(void)

- ea: `0x180016870`
- end: `0x18001687b`
- name: `??1?$CComCritSecLock@VCComFakeCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180028bcb`

## callees

- `0x180016870`

## pseudocode

```c
void __fastcall ATL::CComCritSecLock<ATL::CComFakeCriticalSection>::~CComCritSecLock<ATL::CComFakeCriticalSection>(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
    *(_BYTE *)(a1 + 8) = 0;
}

```

## disassembly

```asm
0x180016870  cmp     byte ptr [rcx+8], 0
0x180016874  jz      short locret_18001687A
0x180016876  mov     byte ptr [rcx+8], 0
0x18001687a  retn
```
