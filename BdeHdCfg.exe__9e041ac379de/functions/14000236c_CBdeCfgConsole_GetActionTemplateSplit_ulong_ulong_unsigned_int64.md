# CBdeCfgConsole::GetActionTemplateSplit(ulong,ulong *,unsigned __int64 *)

- ea: `0x14000236c`
- end: `0x140002417`
- name: `?GetActionTemplateSplit@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z`
- size: `171`
- prototype: `__int64 __fastcall(CBdeCfgConsole *this, __int64, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002014`

## callees

- `0x14000236c`

## import_xrefs

- `BDEHDCFGLIB!?GetTargetDriveLetter@CDriveConfiguration@@QEAAGXZ` at `0x140002398`
- `BDEHDCFGLIB!?GetTargetDriveLetter@CDriveConfiguration@@QEAAGXZ` at `0x140002398`
- `BDEHDCFGLIB!?GetTargetDiskNumber@CDriveConfiguration@@QEAAKXZ` at `0x1400023a5`
- `BDEHDCFGLIB!?GetTargetDiskNumber@CDriveConfiguration@@QEAAKXZ` at `0x1400023a5`
- `BDEHDCFGLIB!?GetTargetPartitionNumber@CDriveConfiguration@@QEAAKXZ` at `0x1400023b1`
- `BDEHDCFGLIB!?GetTargetPartitionNumber@CDriveConfiguration@@QEAAKXZ` at `0x1400023b1`
- `BDEHDCFGLIB!?GetShrinkSize@CDriveConfiguration@@QEAA_KXZ` at `0x1400023bd`
- `BDEHDCFGLIB!?GetShrinkSize@CDriveConfiguration@@QEAA_KXZ` at `0x1400023bd`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::GetActionTemplateSplit(
        CBdeCfgConsole *this,
        __int64 a2,
        unsigned int *a3,
        unsigned __int64 *a4)
{
  unsigned int v6; // r14d
  CDriveConfiguration *v7; // rbx
  unsigned int TargetDriveLetter; // r15d
  unsigned __int64 TargetDiskNumber; // r12
  unsigned __int64 TargetPartitionNumber; // r13
  unsigned __int64 v11; // rcx

  v6 = 0;
  if ( a3 && a4 )
  {
    v7 = (CBdeCfgConsole *)((char *)this + 72);
    TargetDriveLetter = CDriveConfiguration::GetTargetDriveLetter((CBdeCfgConsole *)((char *)this + 72));
    TargetDiskNumber = CDriveConfiguration::GetTargetDiskNumber(v7);
    TargetPartitionNumber = CDriveConfiguration::GetTargetPartitionNumber(v7);
    v11 = (unsigned int)((CDriveConfiguration::GetShrinkSize(v7) + 0xFFFFF) >> 20);
    if ( (_WORD)TargetDriveLetter )
    {
      *a4 = TargetDriveLetter;
      a4[1] = v11;
      *a3 = 205;
    }
    else
    {
      *a4 = TargetDiskNumber;
      a4[1] = TargetPartitionNumber;
      a4[2] = v11;
      *a3 = 204;
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
0x14000236c  push    rbx
0x14000236e  push    rsi
0x14000236f  push    rdi
0x140002370  push    r12
0x140002372  push    r13
0x140002374  push    r14
0x140002376  push    r15
0x140002378  sub     rsp, 20h
0x14000237c  mov     rdi, r9
0x14000237f  mov     rsi, r8
0x140002382  xor     eax, eax
0x140002384  mov     r14d, eax
0x140002387  test    r8, r8
0x14000238a  jz      short loc_1400023FE
0x14000238c  test    r9, r9
0x14000238f  jz      short loc_1400023FE
0x140002391  lea     rbx, [rcx+48h]
0x140002395  mov     rcx, rbx
0x140002398  call    cs:__imp_?GetTargetDriveLetter@CDriveConfiguration@@QEAAGXZ; CDriveConfiguration::GetTargetDriveLetter(void)
0x14000239e  movzx   r15d, ax
0x1400023a2  mov     rcx, rbx
0x1400023a5  call    cs:__imp_?GetTargetDiskNumber@CDriveConfiguration@@QEAAKXZ; CDriveConfiguration::GetTargetDiskNumber(void)
0x1400023ab  mov     r12d, eax
0x1400023ae  mov     rcx, rbx
0x1400023b1  call    cs:__imp_?GetTargetPartitionNumber@CDriveConfiguration@@QEAAKXZ; CDriveConfiguration::GetTargetPartitionNumber(void)
0x1400023b7  mov     r13d, eax
0x1400023ba  mov     rcx, rbx
0x1400023bd  call    cs:__imp_?GetShrinkSize@CDriveConfiguration@@QEAA_KXZ; CDriveConfiguration::GetShrinkSize(void)
0x1400023c3  lea     rcx, [rax+0FFFFFh]
0x1400023ca  shr     rcx, 14h
0x1400023ce  mov     ecx, ecx
0x1400023d0  test    r15w, r15w
0x1400023d4  jz      short loc_1400023E8
0x1400023d6  mov     eax, r15d
0x1400023d9  mov     [rdi], rax
0x1400023dc  mov     [rdi+8], rcx
0x1400023e0  mov     dword ptr [rsi], 0CDh
0x1400023e6  jmp     short loc_140002404
0x1400023e8  mov     [rdi], r12
0x1400023eb  mov     rax, r13
0x1400023ee  mov     [rdi+8], rax
0x1400023f2  mov     [rdi+10h], rcx
0x1400023f6  mov     dword ptr [rsi], 0CCh
0x1400023fc  jmp     short loc_140002404
0x1400023fe  mov     r14d, 80004003h
0x140002404  mov     eax, r14d
0x140002407  add     rsp, 20h
0x14000240b  pop     r15
0x14000240d  pop     r14
0x14000240f  pop     r13
0x140002411  pop     r12
0x140002413  pop     rdi
0x140002414  pop     rsi
0x140002415  pop     rbx
0x140002416  retn
0x140004604  push    rbp
0x140004606  sub     rsp, 20h
0x14000460a  mov     rbp, rdx
0x14000460d  add     rsp, 20h
0x140004611  pop     rbp
0x140004612  retn
```
