# CBdeCfgConsole::GetActionTemplateUnallocatedSpace(ulong,ulong *,unsigned __int64 *)

- ea: `0x140002420`
- end: `0x140002479`
- name: `?GetActionTemplateUnallocatedSpace@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z`
- size: `89`
- prototype: `__int64 __fastcall(CBdeCfgConsole *this, __int64, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002014`

## callees

- `0x140002420`

## import_xrefs

- `BDEHDCFGLIB!?GetTargetPartitionSize@CDriveConfiguration@@QEAA_KXZ` at `0x140002445`
- `BDEHDCFGLIB!?GetTargetPartitionSize@CDriveConfiguration@@QEAA_KXZ` at `0x140002445`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::GetActionTemplateUnallocatedSpace(
        CBdeCfgConsole *this,
        __int64 a2,
        unsigned int *a3,
        unsigned __int64 *a4)
{
  unsigned int v5; // ebx

  v5 = 0;
  if ( a3 && a4 )
  {
    *a4 = (unsigned int)((CDriveConfiguration::GetTargetPartitionSize((CBdeCfgConsole *)((char *)this + 72)) + 0xFFFFF) >> 20);
    *a3 = 203;
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
0x140002420  mov     [rsp+arg_0], rbx
0x140002425  mov     [rsp+arg_8], rsi
0x14000242a  push    rdi
0x14000242b  sub     rsp, 20h
0x14000242f  mov     rdi, r9
0x140002432  mov     rsi, r8
0x140002435  xor     ebx, ebx
0x140002437  test    r8, r8
0x14000243a  jz      short loc_140002462
0x14000243c  test    r9, r9
0x14000243f  jz      short loc_140002462
0x140002441  add     rcx, 48h ; 'H'
0x140002445  call    cs:__imp_?GetTargetPartitionSize@CDriveConfiguration@@QEAA_KXZ; CDriveConfiguration::GetTargetPartitionSize(void)
0x14000244b  add     rax, 0FFFFFh
0x140002451  shr     rax, 14h
0x140002455  mov     eax, eax
0x140002457  mov     [rdi], rax
0x14000245a  mov     dword ptr [rsi], 0CBh
0x140002460  jmp     short loc_140002467
0x140002462  mov     ebx, 80004003h
0x140002467  mov     eax, ebx
0x140002469  mov     rbx, [rsp+28h+arg_0]
0x14000246e  mov     rsi, [rsp+28h+arg_8]
0x140002473  add     rsp, 20h
0x140002477  pop     rdi
0x140002478  retn
0x140004604  push    rbp
0x140004606  sub     rsp, 20h
0x14000460a  mov     rbp, rdx
0x14000460d  add     rsp, 20h
0x140004611  pop     rbp
0x140004612  retn
```
