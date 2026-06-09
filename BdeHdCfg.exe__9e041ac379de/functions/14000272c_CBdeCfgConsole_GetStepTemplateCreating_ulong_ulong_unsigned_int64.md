# CBdeCfgConsole::GetStepTemplateCreating(ulong,ulong *,unsigned __int64 *)

- ea: `0x14000272c`
- end: `0x14000279d`
- name: `?GetStepTemplateCreating@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z`
- size: `113`
- prototype: `__int64 __fastcall(CBdeCfgConsole *this, __int64, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002480`

## callees

- `0x14000272c`

## import_xrefs

- `BDEHDCFGLIB!?ActionRequiresCreate@CDriveConfiguration@@QEAA_NXZ` at `0x140002755`
- `BDEHDCFGLIB!?ActionRequiresCreate@CDriveConfiguration@@QEAA_NXZ` at `0x140002755`
- `BDEHDCFGLIB!?GetNewDriveLetter@CDriveConfiguration@@QEAAGXZ` at `0x140002769`
- `BDEHDCFGLIB!?GetNewDriveLetter@CDriveConfiguration@@QEAAGXZ` at `0x140002769`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::GetStepTemplateCreating(
        CBdeCfgConsole *this,
        __int64 a2,
        unsigned int *a3,
        unsigned __int64 *a4)
{
  unsigned int v6; // ebx
  CDriveConfiguration *v7; // r14
  unsigned __int16 NewDriveLetter; // ax

  v6 = 0;
  if ( a3 && a4 )
  {
    v7 = (CBdeCfgConsole *)((char *)this + 72);
    if ( CDriveConfiguration::ActionRequiresCreate((CBdeCfgConsole *)((char *)this + 72)) )
    {
      NewDriveLetter = CDriveConfiguration::GetNewDriveLetter(v7);
      if ( NewDriveLetter )
      {
        *a4 = NewDriveLetter;
        *a3 = 302;
      }
      else
      {
        *a3 = 303;
      }
    }
    else
    {
      return (unsigned int)-1063256037;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v6;
}

```

## disassembly

```asm
0x14000272c  push    rbx
0x14000272e  push    rsi
0x14000272f  push    rdi
0x140002730  push    r14
0x140002732  push    r15
0x140002734  sub     rsp, 20h
0x140002738  mov     rsi, r9
0x14000273b  mov     rdi, r8
0x14000273e  xor     r15d, r15d
0x140002741  mov     ebx, r15d
0x140002744  test    r8, r8
0x140002747  jz      short loc_14000278A
0x140002749  test    r9, r9
0x14000274c  jz      short loc_14000278A
0x14000274e  lea     r14, [rcx+48h]
0x140002752  mov     rcx, r14
0x140002755  call    cs:__imp_?ActionRequiresCreate@CDriveConfiguration@@QEAA_NXZ; CDriveConfiguration::ActionRequiresCreate(void)
0x14000275b  test    al, al
0x14000275d  jnz     short loc_140002766
0x14000275f  mov     ebx, 0C0A0001Bh
0x140002764  jmp     short loc_14000278F
0x140002766  mov     rcx, r14
0x140002769  call    cs:__imp_?GetNewDriveLetter@CDriveConfiguration@@QEAAGXZ; CDriveConfiguration::GetNewDriveLetter(void)
0x14000276f  test    ax, ax
0x140002772  jz      short loc_140002782
0x140002774  movzx   eax, ax
0x140002777  mov     [rsi], rax
0x14000277a  mov     dword ptr [rdi], 12Eh
0x140002780  jmp     short loc_14000278F
0x140002782  mov     dword ptr [rdi], 12Fh
0x140002788  jmp     short loc_14000278F
0x14000278a  mov     ebx, 80004003h
0x14000278f  mov     eax, ebx
0x140002791  add     rsp, 20h
0x140002795  pop     r15
0x140002797  pop     r14
0x140002799  pop     rdi
0x14000279a  pop     rsi
0x14000279b  pop     rbx
0x14000279c  retn
0x140004604  push    rbp
0x140004606  sub     rsp, 20h
0x14000460a  mov     rbp, rdx
0x14000460d  add     rsp, 20h
0x140004611  pop     rbp
0x140004612  retn
```
