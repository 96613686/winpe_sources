# CBdeCfgConsole::DoConsoleMode(void)

- ea: `0x140001fac`
- end: `0x14000200b`
- name: `?DoConsoleMode@CBdeCfgConsole@@QEAAJXZ`
- size: `95`
- prototype: `int __fastcall(CBdeCfgConsole *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001bf4`

## callees

- `0x140001dbc`
- `0x140001fac`
- `0x140002bc4`
- `0x1400031c4`
- `0x140003884`

## import_xrefs

- `BDEHDCFGLIB!BdeCfgCalculateSizeRequirements` at `0x140001fc1`
- `BDEHDCFGLIB!BdeCfgCalculateSizeRequirements` at `0x140001fc1`

## pseudocode

```c
int __fastcall CBdeCfgConsole::DoConsoleMode(CBdeCfgConsole *this)
{
  int result; // eax

  result = BdeCfgCalculateSizeRequirements(1, (CBdeCfgConsole *)((char *)this + 1392));
  if ( result >= 0 )
  {
    result = CBdeCfgConsole::ParseCommandLine(this);
    if ( result >= 0 )
    {
      if ( *((_BYTE *)this + 1361) )
      {
        return CBdeCfgConsole::ShowDriveInfo(this);
      }
      else if ( *((_BYTE *)this + 1360) )
      {
        return CBdeCfgConsole::PrintConsoleMessage(this, 1084227638);
      }
      else
      {
        return CBdeCfgConsole::ConfigureDrive(this);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140001fac  push    rbx
0x140001fae  sub     rsp, 20h
0x140001fb2  mov     rbx, rcx
0x140001fb5  lea     rdx, [rcx+570h]
0x140001fbc  mov     ecx, 1
0x140001fc1  call    cs:__imp_?BdeCfgCalculateSizeRequirements@@YAJHPEAU_BDECFG_SIZE_REQUIREMENTS@@@Z; BdeCfgCalculateSizeRequirements(int,_BDECFG_SIZE_REQUIREMENTS *)
0x140001fc7  test    eax, eax
0x140001fc9  js      short loc_140002005
0x140001fcb  mov     rcx, rbx; this
0x140001fce  call    ?ParseCommandLine@CBdeCfgConsole@@AEAAJXZ; CBdeCfgConsole::ParseCommandLine(void)
0x140001fd3  test    eax, eax
0x140001fd5  js      short loc_140002005
0x140001fd7  mov     rcx, rbx; this
0x140001fda  cmp     byte ptr [rbx+551h], 0
0x140001fe1  jz      short loc_140001FEA
0x140001fe3  call    ?ShowDriveInfo@CBdeCfgConsole@@AEAAJXZ; CBdeCfgConsole::ShowDriveInfo(void)
0x140001fe8  jmp     short loc_140002005
0x140001fea  cmp     byte ptr [rbx+550h], 0
0x140001ff1  jz      short loc_140001FFF
0x140001ff3  mov     edx, 40A00036h; int
0x140001ff8  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJJZZ; CBdeCfgConsole::PrintConsoleMessage(long,...)
0x140001ffd  jmp     short loc_140002005
0x140001fff  call    ?ConfigureDrive@CBdeCfgConsole@@AEAAJXZ; CBdeCfgConsole::ConfigureDrive(void)
0x140002004  nop
0x140002005  add     rsp, 20h
0x140002009  pop     rbx
0x14000200a  retn
0x140004604  push    rbp
0x140004606  sub     rsp, 20h
0x14000460a  mov     rbp, rdx
0x14000460d  add     rsp, 20h
0x140004611  pop     rbp
0x140004612  retn
```
