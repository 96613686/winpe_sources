# BIHelper::Cleanup(void)

- ea: `0x180028208`
- end: `0x180028248`
- name: `?Cleanup@BIHelper@@AEAAXXZ`
- size: `64`
- prototype: `void __fastcall(BIHelper *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c194`
- `0x180026a08`

## callees

- `0x18000a0a0`
- `0x180028208`

## import_xrefs

- `BrokerLib!BrDeleteBrokerInstance` at `0x180028219`
- `BrokerLib!BrDeleteBrokerInstance` at `0x180028219`

## string_xrefs

- `0x18002822f`: `BIHelper::Cleanup: BrDeleteBrokerInstance failed with`

## pseudocode

```c
void __fastcall BIHelper::Cleanup(BIHelper *this)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx

  if ( *(_QWORD *)this )
  {
    v2 = BrDeleteBrokerInstance();
    if ( v2 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v4, v3, L"BIHelper::Cleanup: BrDeleteBrokerInstance failed with", v2);
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180028208  push    rbx
0x18002820a  sub     rsp, 20h
0x18002820e  mov     rbx, rcx
0x180028211  mov     rcx, [rcx]
0x180028214  test    rcx, rcx
0x180028217  jz      short loc_180028242
0x180028219  call    cs:__imp_BrDeleteBrokerInstance
0x18002821f  test    eax, eax
0x180028221  jz      short loc_18002823B
0x180028223  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002822a  jz      short loc_18002823B
0x18002822c  mov     r9d, eax
0x18002822f  lea     r8, aBihelperCleanu; "BIHelper::Cleanup: BrDeleteBrokerInstan"...
0x180028236  call    McTemplateU0zq_EventWriteTransfer
0x18002823b  mov     qword ptr [rbx], 0
0x180028242  add     rsp, 20h
0x180028246  pop     rbx
0x180028247  retn
```
