# CAACDec::GetNumberOfChannelsFromChannelConfig(int)

- ea: `0x18004a850`
- end: `0x18004a8b4`
- name: `?GetNumberOfChannelsFromChannelConfig@CAACDec@@AEAAHH@Z`
- size: `100`
- prototype: `__int64 __fastcall(CAACDec *this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180041e50`

## callees

- `0x1800018d0`
- `0x180003af0`
- `0x18004a850`

## string_xrefs

- `0x18004a888`: `CAACDec::GetNumberOfChannelsFromChannelConfig() unsupported channel config: %d`
- `0x18004a894`: `CAACDec::GetNumberOfChannelsFromChannelConfig`

## pseudocode

```c
__int64 __fastcall CAACDec::GetNumberOfChannelsFromChannelConfig(CAACDec *this, int a2)
{
  int v2; // edx
  __int64 v3; // r8

  if ( IsChannelConfigSupported(a2) )
    return (unsigned int)dword_1800B5F20[2 * dword_1800B5E64[2 * v2]];
  TraceLoggingHelperBase::TraceVA(
    (TraceLoggingHelperBase *)(v3 + 246488),
    2u,
    "CAACDec::GetNumberOfChannelsFromChannelConfig",
    0x146u,
    "CAACDec::GetNumberOfChannelsFromChannelConfig() unsupported channel config: %d",
    v2);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18004a850  sub     rsp, 38h
0x18004a854  mov     r8, rcx
0x18004a857  mov     ecx, edx; int
0x18004a859  call    ?IsChannelConfigSupported@@YA_NH@Z; IsChannelConfigSupported(int)
0x18004a85e  test    al, al
0x18004a860  jz      short loc_18004A87D
0x18004a862  lea     rcx, __ImageBase
0x18004a869  movsxd  rax, edx
0x18004a86c  movsxd  rax, ds:rva dword_1800B5E64[rcx+rax*8]
0x18004a874  mov     eax, ds:rva dword_1800B5F20[rcx+rax*8]
0x18004a87b  jmp     short loc_18004A8AE
0x18004a87d  mov     [rsp+38h+var_10], edx
0x18004a881  lea     rcx, [r8+3C2D8h]; this
0x18004a888  lea     rax, aCaacdecGetnumb_0; "CAACDec::GetNumberOfChannelsFromChannel"...
0x18004a88f  mov     edx, 2; unsigned __int8
0x18004a894  lea     r8, aCaacdecGetnumb; "CAACDec::GetNumberOfChannelsFromChannel"...
0x18004a89b  mov     [rsp+38h+Format], rax; Format
0x18004a8a0  mov     r9d, 146h; unsigned int
0x18004a8a6  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18004a8ab  or      eax, 0FFFFFFFFh
0x18004a8ae  add     rsp, 38h
0x18004a8b2  retn
```
