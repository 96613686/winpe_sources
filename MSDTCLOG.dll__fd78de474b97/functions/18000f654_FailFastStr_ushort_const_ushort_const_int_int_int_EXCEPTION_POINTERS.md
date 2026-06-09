# FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)

- ea: `0x18000f654`
- end: `0x18000f6dd`
- name: `?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z`
- size: `137`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, int, int, struct _EXCEPTION_POINTERS *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e6fc`
- `0x18000fca8`

## callees

- `0x18000ed38`
- `0x18000f654`
- `0x18000fc84`
- `0x180010070`
- `0x180010364`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000f6af`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000f6af`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f67e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f67e`

## string_xrefs

- `0x18000f691`: `COM+ Failfast:  Unable to allocate memory for stack trace!`

## pseudocode

```c
void __fastcall FailFastStr(const unsigned __int16 *a1, const unsigned __int16 *a2, __int64 a3, int a4, int a5)
{
  _BYTE v6[8]; // [rsp+20h] [rbp-48h] BYREF
  const wchar_t *v7; // [rsp+28h] [rbp-40h]

  if ( !DebugFlags::sm_registryInitialized )
    DebugFlags::InitRegistry();
  if ( DebugFlags::sm_fDebugBreakOnFailFast )
  {
    if ( a5 )
    {
      if ( IsDebuggerPresent()
        || MEMORY[0x7FFE02D4]
        || (v7 = L"COM+ Failfast:  Unable to allocate memory for stack trace!",
            CStackDlg::DoModal((CStackDlg *)v6) == 603) )
      {
        DebugBreak();
      }
    }
  }
  if ( a4 )
    FF_DumpProcess();
  if ( !g_fKeepRunningAfterFailfast )
  {
    TerminateThisProcess();
    JUMPOUT(0x18000F6DCLL);
  }
  g_fKeepRunningAfterFailfast = 0;
}

```

## disassembly

```asm
0x18000f654  push    rbx
0x18000f656  sub     rsp, 60h
0x18000f65a  cmp     cs:?sm_registryInitialized@DebugFlags@@0HA, 0; int DebugFlags::sm_registryInitialized
0x18000f661  mov     ebx, r9d
0x18000f664  jnz     short loc_18000F66B
0x18000f666  call    ?InitRegistry@DebugFlags@@CAXXZ; DebugFlags::InitRegistry(void)
0x18000f66b  cmp     cs:?sm_fDebugBreakOnFailFast@DebugFlags@@0HA, 0; int DebugFlags::sm_fDebugBreakOnFailFast
0x18000f672  jz      short loc_18000F6B5
0x18000f674  cmp     [rsp+68h+arg_20], 0
0x18000f67c  jz      short loc_18000F6B5
0x18000f67e  call    cs:__imp_IsDebuggerPresent
0x18000f684  test    eax, eax
0x18000f686  jnz     short loc_18000F6AF
0x18000f688  cmp     ds:7FFE02D4h, al
0x18000f68f  jnz     short loc_18000F6AF
0x18000f691  lea     rax, aComFailfastUna; "COM+ Failfast:  Unable to allocate memo"...
0x18000f698  lea     rcx, [rsp+68h+var_48]; this
0x18000f69d  mov     [rsp+68h+var_40], rax
0x18000f6a2  call    ?DoModal@CStackDlg@@QEAA_JXZ; CStackDlg::DoModal(void)
0x18000f6a7  cmp     rax, 25Bh
0x18000f6ad  jnz     short loc_18000F6B5
0x18000f6af  call    cs:__imp_DebugBreak
0x18000f6b5  test    ebx, ebx
0x18000f6b7  jz      short loc_18000F6BE
0x18000f6b9  call    ?FF_DumpProcess@@YAXXZ; FF_DumpProcess(void)
0x18000f6be  cmp     cs:?g_fKeepRunningAfterFailfast@@3HA, 0; int g_fKeepRunningAfterFailfast
0x18000f6c5  jz      short loc_18000F6D7
0x18000f6c7  mov     cs:?g_fKeepRunningAfterFailfast@@3HA, 0; int g_fKeepRunningAfterFailfast
0x18000f6d1  add     rsp, 60h
0x18000f6d5  pop     rbx
0x18000f6d6  retn
0x18000f6d7  call    ?TerminateThisProcess@@YAXXZ; TerminateThisProcess(void)
```
