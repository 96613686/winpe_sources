# CBdeCfgConsole::Reboot(void)

- ea: `0x140003804`
- end: `0x14000387e`
- name: `?Reboot@CBdeCfgConsole@@AEAAJXZ`
- size: `122`
- prototype: `__int64 __fastcall(CBdeCfgConsole *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140001dbc`

## callees

- `0x140001008`
- `0x1400032b0`
- `0x1400035bc`
- `0x140003804`

## import_xrefs

- `BDEHDCFGLIB!BdeCfgRestart` at `0x14000381c`
- `BDEHDCFGLIB!BdeCfgRestart` at `0x14000385f`
- `BDEHDCFGLIB!BdeCfgRestart` at `0x14000381c`
- `BDEHDCFGLIB!BdeCfgRestart` at `0x14000385f`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003835`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003835`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::Reboot(CBdeCfgConsole *this)
{
  int ResourceString; // ebx
  void *Block; // [rsp+38h] [rbp+10h] BYREF

  Block = 0;
  ResourceString = BdeCfgRestart(0);
  if ( ResourceString == -2147023705 )
  {
    ResourceString = BdeCfgLoadResourceString(0xCEu, (unsigned __int16 **)&Block);
    if ( ResourceString >= 0 )
    {
      CBdeCfgConsole::PrintConsoleMessage(this, (const unsigned __int16 *)Block);
      ResourceString = CBdeCfgConsole::PromptForContinue(this);
      if ( !ResourceString )
        ResourceString = BdeCfgRestart(1);
    }
  }
  operator delete(Block);
  return (unsigned int)ResourceString;
}

```

## disassembly

```asm
0x140003804  mov     [rsp+arg_0], rbx
0x140003809  push    rdi
0x14000380a  sub     rsp, 20h
0x14000380e  mov     rdi, rcx
0x140003811  mov     [rsp+28h+Block], 0
0x14000381a  xor     ecx, ecx
0x14000381c  call    cs:__imp_?BdeCfgRestart@@YAJH@Z; BdeCfgRestart(int)
0x140003822  mov     ebx, eax
0x140003824  cmp     eax, 800704A7h
0x140003829  jnz     short loc_140003867
0x14000382b  lea     rdx, [rsp+28h+Block]
0x140003830  mov     ecx, 0CEh
0x140003835  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x14000383b  mov     ebx, eax
0x14000383d  test    eax, eax
0x14000383f  js      short loc_140003867
0x140003841  mov     rdx, [rsp+28h+Block]; unsigned __int16 *
0x140003846  mov     rcx, rdi; this
0x140003849  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJPEBGZZ; CBdeCfgConsole::PrintConsoleMessage(ushort const *,...)
0x14000384e  mov     rcx, rdi; this
0x140003851  call    ?PromptForContinue@CBdeCfgConsole@@AEAAJXZ; CBdeCfgConsole::PromptForContinue(void)
0x140003856  mov     ebx, eax
0x140003858  test    eax, eax
0x14000385a  jnz     short loc_140003867
0x14000385c  lea     ecx, [rax+1]
0x14000385f  call    cs:__imp_?BdeCfgRestart@@YAJH@Z; BdeCfgRestart(int)
0x140003865  mov     ebx, eax
0x140003867  mov     rcx, [rsp+28h+Block]; Block
0x14000386c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003871  mov     eax, ebx
0x140003873  mov     rbx, [rsp+28h+arg_0]
0x140003878  add     rsp, 20h
0x14000387c  pop     rdi
0x14000387d  retn
0x1400047cd  push    rbp
0x1400047cf  sub     rsp, 20h
0x1400047d3  mov     rbp, rdx
0x1400047d6  mov     rcx, [rbp+38h]; Block
0x1400047da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400047df  nop
0x1400047e0  add     rsp, 20h
0x1400047e4  pop     rbp
0x1400047e5  retn
```
