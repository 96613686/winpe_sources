# CBdeCfgConsole::GetStepTemplateShrinking(ulong,ulong *,unsigned __int64 *)

- ea: `0x1400027f0`
- end: `0x14000288f`
- name: `?GetStepTemplateShrinking@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z`
- size: `159`
- prototype: `__int64 __fastcall(CBdeCfgConsole *this, __int64, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002480`

## callees

- `0x1400027f0`

## import_xrefs

- `BDEHDCFGLIB!?GetTargetDriveLetter@CDriveConfiguration@@QEAAGXZ` at `0x140002831`
- `BDEHDCFGLIB!?GetTargetDriveLetter@CDriveConfiguration@@QEAAGXZ` at `0x140002831`
- `BDEHDCFGLIB!?GetTargetDiskNumber@CDriveConfiguration@@QEAAKXZ` at `0x14000283e`
- `BDEHDCFGLIB!?GetTargetDiskNumber@CDriveConfiguration@@QEAAKXZ` at `0x14000283e`
- `BDEHDCFGLIB!?GetTargetPartitionNumber@CDriveConfiguration@@QEAAKXZ` at `0x14000284a`
- `BDEHDCFGLIB!?GetTargetPartitionNumber@CDriveConfiguration@@QEAAKXZ` at `0x14000284a`
- `BDEHDCFGLIB!?ActionRequiresShrink@CDriveConfiguration@@QEAA_NXZ` at `0x14000281d`
- `BDEHDCFGLIB!?ActionRequiresShrink@CDriveConfiguration@@QEAA_NXZ` at `0x14000281d`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::GetStepTemplateShrinking(
        CBdeCfgConsole *this,
        __int64 a2,
        unsigned int *a3,
        unsigned __int64 *a4)
{
  unsigned int v6; // ebx
  CDriveConfiguration *v7; // r14
  unsigned int TargetDriveLetter; // r15d
  unsigned __int64 TargetDiskNumber; // r12
  unsigned int TargetPartitionNumber; // eax

  v6 = 0;
  if ( a3 && a4 )
  {
    v7 = (CBdeCfgConsole *)((char *)this + 72);
    if ( CDriveConfiguration::ActionRequiresShrink((CBdeCfgConsole *)((char *)this + 72)) )
    {
      TargetDriveLetter = CDriveConfiguration::GetTargetDriveLetter(v7);
      TargetDiskNumber = CDriveConfiguration::GetTargetDiskNumber(v7);
      TargetPartitionNumber = CDriveConfiguration::GetTargetPartitionNumber(v7);
      if ( (_WORD)TargetDriveLetter )
      {
        *a4 = TargetDriveLetter;
        *a3 = 300;
      }
      else
      {
        *a4 = TargetDiskNumber;
        a4[1] = TargetPartitionNumber;
        *a3 = 301;
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
0x1400027f0  push    rbx
0x1400027f2  push    rsi
0x1400027f3  push    rdi
0x1400027f4  push    r12
0x1400027f6  push    r13
0x1400027f8  push    r14
0x1400027fa  push    r15
0x1400027fc  sub     rsp, 20h
0x140002800  mov     rdi, r9
0x140002803  mov     rsi, r8
0x140002806  xor     r13d, r13d
0x140002809  mov     ebx, r13d
0x14000280c  test    r8, r8
0x14000280f  jz      short loc_140002878
0x140002811  test    r9, r9
0x140002814  jz      short loc_140002878
0x140002816  lea     r14, [rcx+48h]
0x14000281a  mov     rcx, r14
0x14000281d  call    cs:__imp_?ActionRequiresShrink@CDriveConfiguration@@QEAA_NXZ; CDriveConfiguration::ActionRequiresShrink(void)
0x140002823  test    al, al
0x140002825  jnz     short loc_14000282E
0x140002827  mov     ebx, 0C0A0001Bh
0x14000282c  jmp     short loc_14000287D
0x14000282e  mov     rcx, r14
0x140002831  call    cs:__imp_?GetTargetDriveLetter@CDriveConfiguration@@QEAAGXZ; CDriveConfiguration::GetTargetDriveLetter(void)
0x140002837  movzx   r15d, ax
0x14000283b  mov     rcx, r14
0x14000283e  call    cs:__imp_?GetTargetDiskNumber@CDriveConfiguration@@QEAAKXZ; CDriveConfiguration::GetTargetDiskNumber(void)
0x140002844  mov     r12d, eax
0x140002847  mov     rcx, r14
0x14000284a  call    cs:__imp_?GetTargetPartitionNumber@CDriveConfiguration@@QEAAKXZ; CDriveConfiguration::GetTargetPartitionNumber(void)
0x140002850  mov     ecx, eax
0x140002852  test    r15w, r15w
0x140002856  jz      short loc_140002866
0x140002858  mov     eax, r15d
0x14000285b  mov     [rdi], rax
0x14000285e  mov     dword ptr [rsi], 12Ch
0x140002864  jmp     short loc_14000287D
0x140002866  mov     [rdi], r12
0x140002869  mov     rax, rcx
0x14000286c  mov     [rdi+8], rcx
0x140002870  mov     dword ptr [rsi], 12Dh
0x140002876  jmp     short loc_14000287D
0x140002878  mov     ebx, 80004003h
0x14000287d  mov     eax, ebx
0x14000287f  add     rsp, 20h
0x140002883  pop     r15
0x140002885  pop     r14
0x140002887  pop     r13
0x140002889  pop     r12
0x14000288b  pop     rdi
0x14000288c  pop     rsi
0x14000288d  pop     rbx
0x14000288e  retn
0x140004604  push    rbp
0x140004606  sub     rsp, 20h
0x14000460a  mov     rbp, rdx
0x14000460d  add     rsp, 20h
0x140004611  pop     rbp
0x140004612  retn
```
