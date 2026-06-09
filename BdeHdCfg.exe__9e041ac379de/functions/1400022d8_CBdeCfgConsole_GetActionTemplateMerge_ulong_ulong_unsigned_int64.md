# CBdeCfgConsole::GetActionTemplateMerge(ulong,ulong *,unsigned __int64 *)

- ea: `0x1400022d8`
- end: `0x140002365`
- name: `?GetActionTemplateMerge@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z`
- size: `141`
- prototype: `__int64 __fastcall(CBdeCfgConsole *this, __int64, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002014`

## callees

- `0x1400022d8`

## import_xrefs

- `BDEHDCFGLIB!?GetTargetDriveLetter@CDriveConfiguration@@QEAAGXZ` at `0x140002305`
- `BDEHDCFGLIB!?GetTargetDriveLetter@CDriveConfiguration@@QEAAGXZ` at `0x140002305`
- `BDEHDCFGLIB!?GetTargetDiskNumber@CDriveConfiguration@@QEAAKXZ` at `0x140002312`
- `BDEHDCFGLIB!?GetTargetDiskNumber@CDriveConfiguration@@QEAAKXZ` at `0x140002312`
- `BDEHDCFGLIB!?GetTargetPartitionNumber@CDriveConfiguration@@QEAAKXZ` at `0x14000231e`
- `BDEHDCFGLIB!?GetTargetPartitionNumber@CDriveConfiguration@@QEAAKXZ` at `0x14000231e`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::GetActionTemplateMerge(
        CBdeCfgConsole *this,
        __int64 a2,
        unsigned int *a3,
        unsigned __int64 *a4)
{
  unsigned int v6; // r14d
  CDriveConfiguration *v7; // rbx
  unsigned int TargetDriveLetter; // r15d
  unsigned __int64 TargetDiskNumber; // r12
  unsigned int TargetPartitionNumber; // eax

  v6 = 0;
  if ( a3 && a4 )
  {
    v7 = (CBdeCfgConsole *)((char *)this + 72);
    TargetDriveLetter = CDriveConfiguration::GetTargetDriveLetter((CBdeCfgConsole *)((char *)this + 72));
    TargetDiskNumber = CDriveConfiguration::GetTargetDiskNumber(v7);
    TargetPartitionNumber = CDriveConfiguration::GetTargetPartitionNumber(v7);
    if ( (_WORD)TargetDriveLetter )
    {
      *a4 = TargetDriveLetter;
      *a3 = 202;
    }
    else
    {
      *a4 = TargetDiskNumber;
      a4[1] = TargetPartitionNumber;
      *a3 = 201;
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
0x1400022d8  push    rbx
0x1400022da  push    rsi
0x1400022db  push    rdi
0x1400022dc  push    r12
0x1400022de  push    r13
0x1400022e0  push    r14
0x1400022e2  push    r15
0x1400022e4  sub     rsp, 20h
0x1400022e8  mov     rdi, r9
0x1400022eb  mov     rsi, r8
0x1400022ee  xor     r13d, r13d
0x1400022f1  mov     r14d, r13d
0x1400022f4  test    r8, r8
0x1400022f7  jz      short loc_14000234C
0x1400022f9  test    r9, r9
0x1400022fc  jz      short loc_14000234C
0x1400022fe  lea     rbx, [rcx+48h]
0x140002302  mov     rcx, rbx
0x140002305  call    cs:__imp_?GetTargetDriveLetter@CDriveConfiguration@@QEAAGXZ; CDriveConfiguration::GetTargetDriveLetter(void)
0x14000230b  movzx   r15d, ax
0x14000230f  mov     rcx, rbx
0x140002312  call    cs:__imp_?GetTargetDiskNumber@CDriveConfiguration@@QEAAKXZ; CDriveConfiguration::GetTargetDiskNumber(void)
0x140002318  mov     r12d, eax
0x14000231b  mov     rcx, rbx
0x14000231e  call    cs:__imp_?GetTargetPartitionNumber@CDriveConfiguration@@QEAAKXZ; CDriveConfiguration::GetTargetPartitionNumber(void)
0x140002324  mov     ecx, eax
0x140002326  test    r15w, r15w
0x14000232a  jz      short loc_14000233A
0x14000232c  mov     eax, r15d
0x14000232f  mov     [rdi], rax
0x140002332  mov     dword ptr [rsi], 0CAh
0x140002338  jmp     short loc_140002352
0x14000233a  mov     [rdi], r12
0x14000233d  mov     rax, rcx
0x140002340  mov     [rdi+8], rcx
0x140002344  mov     dword ptr [rsi], 0C9h
0x14000234a  jmp     short loc_140002352
0x14000234c  mov     r14d, 80004003h
0x140002352  mov     eax, r14d
0x140002355  add     rsp, 20h
0x140002359  pop     r15
0x14000235b  pop     r14
0x14000235d  pop     r13
0x14000235f  pop     r12
0x140002361  pop     rdi
0x140002362  pop     rsi
0x140002363  pop     rbx
0x140002364  retn
0x140004604  push    rbp
0x140004606  sub     rsp, 20h
0x14000460a  mov     rbp, rdx
0x14000460d  add     rsp, 20h
0x140004611  pop     rbp
0x140004612  retn
```
