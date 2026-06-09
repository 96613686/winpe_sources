# CBdeCfgConsole::GetStepTemplateMigrating(ulong,ulong *,unsigned __int64 *)

- ea: `0x1400027a4`
- end: `0x1400027e7`
- name: `?GetStepTemplateMigrating@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z`
- size: `67`
- prototype: `__int64 __fastcall(CBdeCfgConsole *this, __int64, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002480`

## callees

- `0x1400027a4`

## import_xrefs

- `BDEHDCFGLIB!?ActionRequiresMerge@CDriveConfiguration@@QEAA_NXZ` at `0x1400027c3`
- `BDEHDCFGLIB!?ActionRequiresMerge@CDriveConfiguration@@QEAA_NXZ` at `0x1400027c3`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::GetStepTemplateMigrating(
        CBdeCfgConsole *this,
        __int64 a2,
        unsigned int *a3,
        unsigned __int64 *a4)
{
  unsigned int v5; // ebx

  v5 = 0;
  if ( a3 )
  {
    if ( CDriveConfiguration::ActionRequiresMerge((CBdeCfgConsole *)((char *)this + 72)) )
      *a3 = 304;
    else
      return (unsigned int)-1063256037;
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v5;
}

```

## disassembly

```asm
0x1400027a4  mov     [rsp+arg_0], rbx
0x1400027a9  push    rdi
0x1400027aa  sub     rsp, 20h
0x1400027ae  mov     rdi, r8
0x1400027b1  xor     ebx, ebx
0x1400027b3  test    r8, r8
0x1400027b6  jnz     short loc_1400027BF
0x1400027b8  mov     ebx, 80004003h
0x1400027bd  jmp     short loc_1400027DA
0x1400027bf  add     rcx, 48h ; 'H'
0x1400027c3  call    cs:__imp_?ActionRequiresMerge@CDriveConfiguration@@QEAA_NXZ; CDriveConfiguration::ActionRequiresMerge(void)
0x1400027c9  test    al, al
0x1400027cb  jnz     short loc_1400027D4
0x1400027cd  mov     ebx, 0C0A0001Bh
0x1400027d2  jmp     short loc_1400027DA
0x1400027d4  mov     dword ptr [rdi], 130h
0x1400027da  mov     eax, ebx
0x1400027dc  mov     rbx, [rsp+28h+arg_0]
0x1400027e1  add     rsp, 20h
0x1400027e5  pop     rdi
0x1400027e6  retn
0x140004604  push    rbp
0x140004606  sub     rsp, 20h
0x14000460a  mov     rbp, rdx
0x14000460d  add     rsp, 20h
0x140004611  pop     rbp
0x140004612  retn
```
