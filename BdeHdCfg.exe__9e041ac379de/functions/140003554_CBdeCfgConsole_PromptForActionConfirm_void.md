# CBdeCfgConsole::PromptForActionConfirm(void)

- ea: `0x140003554`
- end: `0x1400035b3`
- name: `?PromptForActionConfirm@CBdeCfgConsole@@AEAAJXZ`
- size: `95`
- prototype: `__int64 __fastcall(CBdeCfgConsole *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140001dbc`

## callees

- `0x140001008`
- `0x140002014`
- `0x140003554`
- `0x1400035bc`

## import_xrefs

- `msvcrt!wprintf` at `0x14000358c`
- `msvcrt!wprintf` at `0x14000358c`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::PromptForActionConfirm(CBdeCfgConsole *this)
{
  int ActionDescription; // ebx
  void *Block; // [rsp+38h] [rbp+10h] BYREF

  ActionDescription = 0;
  Block = 0;
  if ( !*((_BYTE *)this + 1384) )
  {
    ActionDescription = CBdeCfgConsole::GetActionDescription(this, (unsigned __int16 **)&Block);
    if ( ActionDescription >= 0 )
    {
      wprintf(L"%s", Block);
      ActionDescription = CBdeCfgConsole::PromptForContinue(this);
    }
  }
  operator delete(Block);
  return (unsigned int)ActionDescription;
}

```

## disassembly

```asm
0x140003554  mov     [rsp+arg_0], rbx
0x140003559  push    rdi
0x14000355a  sub     rsp, 20h
0x14000355e  mov     rdi, rcx
0x140003561  xor     ebx, ebx
0x140003563  mov     [rsp+28h+Block], rbx
0x140003568  cmp     [rcx+568h], bl
0x14000356e  jnz     short loc_14000359C
0x140003570  lea     rdx, [rsp+28h+Block]; unsigned __int16 **
0x140003575  call    ?GetActionDescription@CBdeCfgConsole@@AEAAJPEAPEAG@Z; CBdeCfgConsole::GetActionDescription(ushort * *)
0x14000357a  mov     ebx, eax
0x14000357c  test    eax, eax
0x14000357e  js      short loc_14000359C
0x140003580  mov     rdx, [rsp+28h+Block]
0x140003585  lea     rcx, aS; "%s"
0x14000358c  call    cs:__imp_wprintf
0x140003592  mov     rcx, rdi; this
0x140003595  call    ?PromptForContinue@CBdeCfgConsole@@AEAAJXZ; CBdeCfgConsole::PromptForContinue(void)
0x14000359a  mov     ebx, eax
0x14000359c  mov     rcx, [rsp+28h+Block]; Block
0x1400035a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400035a6  mov     eax, ebx
0x1400035a8  mov     rbx, [rsp+28h+arg_0]
0x1400035ad  add     rsp, 20h
0x1400035b1  pop     rdi
0x1400035b2  retn
0x140004755  push    rbp
0x140004757  sub     rsp, 20h
0x14000475b  mov     rbp, rdx
0x14000475e  mov     rcx, [rbp+38h]; Block
0x140004762  add     rsp, 20h
0x140004766  pop     rbp
0x140004767  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
