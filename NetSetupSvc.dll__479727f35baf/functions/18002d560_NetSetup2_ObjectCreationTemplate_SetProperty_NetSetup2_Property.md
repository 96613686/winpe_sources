# NetSetup2::ObjectCreationTemplate::SetProperty(NetSetup2::Property &&)

- ea: `0x18002d560`
- end: `0x18002d5af`
- name: `?SetProperty@ObjectCreationTemplate@NetSetup2@@QEAAX$$QEAVProperty@2@@Z`
- size: `79`
- prototype: `void __fastcall(NetSetup2::ObjectCreationTemplate *, __int64)`
- caller_count: `10`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001b168`
- `0x18001b1e8`
- `0x18001b2d0`
- `0x18001b35c`
- `0x18001b414`
- `0x18001d9c0`
- `0x18001df88`
- `0x18001e060`
- `0x180024638`
- `0x1800246c4`

## callees

- `0x18002b554`
- `0x18002b9a0`
- `0x18002bc00`
- `0x18002d560`
- `0x18002d90c`

## pseudocode

```c
void __fastcall NetSetup2::ObjectCreationTemplate::SetProperty(NetSetup2::ObjectCreationTemplate *a1, __int64 a2)
{
  __int64 v3; // r11
  __int64 v4; // [rsp+20h] [rbp-18h] BYREF
  char v5; // [rsp+28h] [rbp-10h]

  if ( *(_DWORD *)(a2 + 20) )
  {
    NetSetup2::PropertyArray::TryGetProperty(a1, &v4);
    if ( v5 )
      NetSetup2::Property::operator=(v4, v3);
    else
      std::vector<NetSetup2::Property>::emplace_back<NetSetup2::Property>(a1, v3);
  }
  else
  {
    NetSetup2::ObjectCreationTemplate::DeleteProperty(a1, (const struct _NETSETUPPROPKEY *)a2);
  }
}

```

## disassembly

```asm
0x18002d560  push    rbx
0x18002d562  sub     rsp, 30h
0x18002d566  mov     r11, rdx
0x18002d569  mov     rbx, rcx
0x18002d56c  cmp     dword ptr [rdx+14h], 0
0x18002d570  jnz     short loc_18002D57C
0x18002d572  add     rsp, 30h
0x18002d576  pop     rbx
0x18002d577  jmp     ?DeleteProperty@ObjectCreationTemplate@NetSetup2@@AEAAXAEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ObjectCreationTemplate::DeleteProperty(_NETSETUPPROPKEY const &)
0x18002d57c  mov     r8, r11
0x18002d57f  lea     rdx, [rsp+38h+var_18]
0x18002d584  call    ?TryGetProperty@PropertyArray@NetSetup2@@QEBA?AV?$Optional@AEBVProperty@NetSetup2@@@details@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::PropertyArray::TryGetProperty(_NETSETUPPROPKEY const &)
0x18002d589  nop
0x18002d58a  mov     rdx, r11
0x18002d58d  cmp     [rsp+38h+var_10], 0
0x18002d592  jz      short loc_18002D5A0
0x18002d594  mov     rcx, [rsp+38h+var_18]
0x18002d599  call    ??4Property@NetSetup2@@QEAAAEAV01@$$QEAV01@@Z; NetSetup2::Property::operator=(NetSetup2::Property &&)
0x18002d59e  jmp     short loc_18002D5A9
0x18002d5a0  mov     rcx, rbx
0x18002d5a3  call    ??$emplace_back@VProperty@NetSetup2@@@?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@QEAAAEAVProperty@NetSetup2@@$$QEAV23@@Z; std::vector<NetSetup2::Property>::emplace_back<NetSetup2::Property>(NetSetup2::Property &&)
0x18002d5a8  nop
0x18002d5a9  add     rsp, 30h
0x18002d5ad  pop     rbx
0x18002d5ae  retn
```
