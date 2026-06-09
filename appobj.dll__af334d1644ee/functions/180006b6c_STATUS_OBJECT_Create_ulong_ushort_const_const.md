# STATUS_OBJECT::Create(ulong,ushort const * * const)

- ea: `0x180006b6c`
- end: `0x180006bd0`
- name: `?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z`
- size: `100`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, DWORD dwMessageId, va_list *Arguments)`
- caller_count: `19`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007040`
- `0x18000cd60`
- `0x1800113c8`
- `0x180017a24`
- `0x1800194e4`
- `0x180019948`
- `0x180019d30`
- `0x18001a850`
- `0x18001b188`
- `0x18001bd50`
- `0x18001ca1c`
- `0x18001d8c0`
- `0x18001e0f8`
- `0x180021658`
- `0x180023ba8`
- `0x180025170`
- `0x180025748`
- `0x180028f50`
- `0x18002a6cc`

## callees

- `0x180002e90`
- `0x180005ba8`
- `0x180006b6c`
- `0x1800131d8`

## pseudocode

```c
__int64 __fastcall STATUS_OBJECT::Create(const unsigned __int16 **this, DWORD dwMessageId, va_list *Arguments)
{
  int v4; // edx

  v4 = FormatCommandMessage(dwMessageId, Arguments, (struct STRU *)(this + 27));
  if ( v4 >= 0 )
  {
    v4 = COMMAND_OBJECT::AddAttribute((COMMAND_OBJECT *)this, L"message", this[31]);
    if ( v4 >= 0 )
    {
      v4 = STRU::Copy((STRU *)(this + 2), (const unsigned __int8 *)&Str);
      if ( v4 >= 0 )
        return 0;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006b6c  push    rbx
0x180006b6e  sub     rsp, 20h
0x180006b72  mov     rax, r8
0x180006b75  mov     r9d, edx
0x180006b78  lea     r8, [rcx+0D8h]; this
0x180006b7f  mov     rbx, rcx
0x180006b82  mov     rdx, rax; Arguments
0x180006b85  mov     ecx, r9d; dwMessageId
0x180006b88  call    ?FormatCommandMessage@@YAJKQEAPEBGPEAVSTRU@@@Z; FormatCommandMessage(ulong,ushort const * * const,STRU *)
0x180006b8d  mov     edx, eax
0x180006b8f  test    eax, eax
0x180006b91  js      short loc_180006BC8
0x180006b93  mov     r8, [rbx+0F8h]; unsigned __int16 *
0x180006b9a  lea     rdx, aMessage; "message"
0x180006ba1  mov     rcx, rbx; this
0x180006ba4  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180006ba9  mov     edx, eax
0x180006bab  test    eax, eax
0x180006bad  js      short loc_180006BC8
0x180006baf  lea     rcx, [rbx+10h]; this
0x180006bb3  lea     rdx, Str; unsigned __int16 *
0x180006bba  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006bbf  mov     edx, eax
0x180006bc1  xor     eax, eax
0x180006bc3  test    edx, edx
0x180006bc5  cmovns  edx, eax
0x180006bc8  mov     eax, edx
0x180006bca  add     rsp, 20h
0x180006bce  pop     rbx
0x180006bcf  retn
```
