# BfeRundownThreadCallback

- ea: `0x180076390`
- end: `0x180076406`
- name: `BfeRundownThreadCallback`
- size: `118`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180076284`
- `0x180076390`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800763bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800763bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800763df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800763df`

## string_xrefs

- `0x1800763a5`: `BfeRundownThreadCallback`
- `0x1800763f0`: `BfeRundownThreadCallback`
- `0x1800763c9`: `%ProgramData%\Microsoft\Windows\wfp\currentState.xml`

## pseudocode

```c
void __fastcall BfeRundownThreadCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  __int64 v3; // rbx

  if ( byte_1800F5769 )
  {
    EnterCriticalSection(&gBfeRundownComponent);
    v3 = BfeRundownStateToXml(L"%ProgramData%\\Microsoft\\Windows\\wfp\\currentState.xml");
    LeaveCriticalSection(&gBfeRundownComponent);
  }
  else
  {
    v3 = WfpReportSysErrorAsWinError(Instance, "BfeRundownThreadCallback", 21);
  }
  if ( v3 )
    WfpReportError(v3, "BfeRundownThreadCallback");
}

```

## disassembly

```asm
0x180076390  push    rbx
0x180076392  sub     rsp, 20h
0x180076396  cmp     cs:byte_1800F5769, 0
0x18007639d  jnz     short loc_1800763B6
0x18007639f  mov     r8d, 15h
0x1800763a5  lea     rdx, aBferundownthre; "BfeRundownThreadCallback"
0x1800763ac  call    WfpReportSysErrorAsWinError
0x1800763b1  mov     rbx, rax
0x1800763b4  jmp     short loc_1800763EB
0x1800763b6  lea     rcx, gBfeRundownComponent; lpCriticalSection
0x1800763bd  call    cs:__imp_EnterCriticalSection
0x1800763c4  nop     dword ptr [rax+rax+00h]
0x1800763c9  lea     rcx, aProgramdataMic_1; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x1800763d0  call    BfeRundownStateToXml
0x1800763d5  mov     rbx, rax
0x1800763d8  lea     rcx, gBfeRundownComponent; lpCriticalSection
0x1800763df  call    cs:__imp_LeaveCriticalSection
0x1800763e6  nop     dword ptr [rax+rax+00h]
0x1800763eb  test    rbx, rbx
0x1800763ee  jz      short loc_1800763FF
0x1800763f0  lea     rdx, aBferundownthre; "BfeRundownThreadCallback"
0x1800763f7  mov     rcx, rbx
0x1800763fa  call    WfpReportError
0x1800763ff  add     rsp, 20h
0x180076403  pop     rbx
0x180076404  retn
```
