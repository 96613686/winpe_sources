# ATL::CComCritSecLock<ATL::CComFakeCriticalSection>::~CComCritSecLock<ATL::CComFakeCriticalSection>(void)

- ea: `0x180015fe0`
- end: `0x180015feb`
- name: `??1?$CComCritSecLock@VCComFakeCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002880f`

## callees

- `0x180015fe0`

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
0x180015fe0  cmp     byte ptr [rcx+8], 0
0x180015fe4  jz      short locret_180015FEA
0x180015fe6  mov     byte ptr [rcx+8], 0
0x180015fea  retn
```
