# CMetadataXMPReaderWriter::AddRef(void)

- ea: `0x18000fa90`
- end: `0x18000faba`
- name: `?AddRef@CMetadataXMPReaderWriter@@UEAAKXZ`
- size: `42`
- prototype: `unsigned int __fastcall(CMetadataXMPReaderWriter *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800229c0`
- `0x1800229d0`
- `0x1800229e0`

## callees

- `0x18000fa90`
- `0x18002292c`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::AddRef(
        CMetadataXMPReaderWriter *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  if ( *((int *)this + 8) < 0 )
  {
    PrintAssertionMessageW((const unsigned __int16 *)this, a2, a3, a4);
    __int2c();
  }
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 8);
}

```

## disassembly

```asm
0x18000fa90  push    rbx
0x18000fa92  sub     rsp, 30h
0x18000fa96  cmp     dword ptr [rcx+20h], 0
0x18000fa9a  mov     rbx, rcx
0x18000fa9d  jl      short loc_18000FAB1
0x18000fa9f  mov     eax, 1
0x18000faa4  lock xadd [rbx+20h], eax
0x18000faa9  inc     eax
0x18000faab  add     rsp, 30h
0x18000faaf  pop     rbx
0x18000fab0  retn
0x18000fab1  call    ?PrintAssertionMessageW@@YAXPEBG000K@Z; PrintAssertionMessageW(ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x18000fab6  int     2Ch; Windows NT - assertion failure
0x18000fab8  jmp     short loc_18000FA9F
```
