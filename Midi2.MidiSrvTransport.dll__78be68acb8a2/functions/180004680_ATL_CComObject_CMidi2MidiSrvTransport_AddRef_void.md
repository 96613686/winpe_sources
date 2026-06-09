# ATL::CComObject<CMidi2MidiSrvTransport>::AddRef(void)

- ea: `0x180004680`
- end: `0x1800046a9`
- name: `?AddRef@?$CComObject@VCMidi2MidiSrvTransport@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004680`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMidi2MidiSrvTransport>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180004680  mov     r9d, 7FFFFFFFh
0x180004686  jmp     short loc_180004696
0x180004688  lea     edx, [r8+1]
0x18000468c  mov     eax, r8d
0x18000468f  lock cmpxchg [rcx+8], edx
0x180004694  jz      short loc_1800046A1
0x180004696  mov     r8d, [rcx+8]
0x18000469a  cmp     r8d, r9d
0x18000469d  jnz     short loc_180004688
0x18000469f  jmp     short loc_1800046A5
0x1800046a1  lea     r9d, [r8+1]
0x1800046a5  mov     eax, r9d
0x1800046a8  retn
```
