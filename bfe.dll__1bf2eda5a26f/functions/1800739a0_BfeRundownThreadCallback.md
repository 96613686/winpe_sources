# BfeRundownThreadCallback

- ea: `0x1800739a0`
- end: `0x180073a09`
- name: `BfeRundownThreadCallback`
- size: `105`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x1800738a0`
- `0x1800739a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800739cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800739cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800739e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800739e9`

## string_xrefs

- `0x1800739b5`: `BfeRundownThreadCallback`
- `0x1800739f4`: `BfeRundownThreadCallback`
- `0x1800739d3`: `%ProgramData%\Microsoft\Windows\wfp\currentState.xml`

## pseudocode

```c
void __fastcall BfeRundownThreadCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  __int64 v3; // rbx

  if ( BYTE1(qword_1800F2668[28]) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)&qword_1800F2668[19]);
    v3 = BfeRundownStateToXml(L"%ProgramData%\\Microsoft\\Windows\\wfp\\currentState.xml");
    LeaveCriticalSection((LPCRITICAL_SECTION)&qword_1800F2668[19]);
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
0x1800739a0  push    rbx
0x1800739a2  sub     rsp, 20h
0x1800739a6  cmp     byte ptr cs:qword_1800F2668+0E1h, 0
0x1800739ad  jnz     short loc_1800739C6
0x1800739af  mov     r8d, 15h
0x1800739b5  lea     rdx, aBferundownthre; "BfeRundownThreadCallback"
0x1800739bc  call    WfpReportSysErrorAsWinError
0x1800739c1  mov     rbx, rax
0x1800739c4  jmp     short loc_1800739EF
0x1800739c6  lea     rcx, qword_1800F2668+98h; lpCriticalSection
0x1800739cd  call    cs:__imp_EnterCriticalSection
0x1800739d3  lea     rcx, aProgramdataMic_1; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x1800739da  call    BfeRundownStateToXml
0x1800739df  mov     rbx, rax
0x1800739e2  lea     rcx, qword_1800F2668+98h; lpCriticalSection
0x1800739e9  call    cs:__imp_LeaveCriticalSection
0x1800739ef  test    rbx, rbx
0x1800739f2  jz      short loc_180073A03
0x1800739f4  lea     rdx, aBferundownthre; "BfeRundownThreadCallback"
0x1800739fb  mov     rcx, rbx
0x1800739fe  call    WfpReportError
0x180073a03  add     rsp, 20h
0x180073a07  pop     rbx
0x180073a08  retn
```
