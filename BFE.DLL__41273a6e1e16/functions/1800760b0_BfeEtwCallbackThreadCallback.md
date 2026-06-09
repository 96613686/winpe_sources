# BfeEtwCallbackThreadCallback

- ea: `0x1800760b0`
- end: `0x18007615b`
- name: `BfeEtwCallbackThreadCallback`
- size: `171`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x1800760b0`
- `0x180076284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800760e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800760e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007612f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007612f`

## string_xrefs

- `0x1800760c6`: `BfeEtwCallbackThreadCallback`
- `0x180076140`: `BfeEtwCallbackThreadCallback`
- `0x1800760fb`: `%ProgramData%\Microsoft\Windows\wfp\wfpStateOne.xml`
- `0x1800760f4`: `%ProgramData%\Microsoft\Windows\wfp\wfpStateTwo.xml`

## pseudocode

```c
void __fastcall BfeEtwCallbackThreadCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  char v3; // di
  __int64 v4; // rax
  const wchar_t *v5; // rcx
  __int64 v6; // rbx

  if ( byte_1800F5769 )
  {
    EnterCriticalSection(&gBfeRundownComponent);
    v5 = L"%ProgramData%\\Microsoft\\Windows\\wfp\\wfpStateOne.xml";
    v3 = 1;
    if ( !byte_1800F5768 )
      v5 = L"%ProgramData%\\Microsoft\\Windows\\wfp\\wfpStateTwo.xml";
    v4 = BfeRundownStateToXml(v5);
  }
  else
  {
    v3 = 0;
    v4 = WfpReportSysErrorAsWinError(Instance, "BfeEtwCallbackThreadCallback", 21);
  }
  v6 = v4;
  if ( !v4 )
    byte_1800F5768 = byte_1800F5768 == 0;
  if ( v3 )
    LeaveCriticalSection(&gBfeRundownComponent);
  if ( v6 )
    WfpReportError(v6, "BfeEtwCallbackThreadCallback");
}

```

## disassembly

```asm
0x1800760b0  mov     [rsp+arg_0], rbx
0x1800760b5  push    rdi
0x1800760b6  sub     rsp, 20h
0x1800760ba  cmp     cs:byte_1800F5769, 0
0x1800760c1  jnz     short loc_1800760DA
0x1800760c3  xor     dil, dil
0x1800760c6  lea     rdx, aBfeetwcallback; "BfeEtwCallbackThreadCallback"
0x1800760cd  mov     r8d, 15h
0x1800760d3  call    WfpReportSysErrorAsWinError
0x1800760d8  jmp     short loc_18007610E
0x1800760da  lea     rcx, gBfeRundownComponent; lpCriticalSection
0x1800760e1  call    cs:__imp_EnterCriticalSection
0x1800760e8  nop     dword ptr [rax+rax+00h]
0x1800760ed  cmp     cs:byte_1800F5768, 0
0x1800760f4  lea     rax, aProgramdataMic; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x1800760fb  lea     rcx, aProgramdataMic_0; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x180076102  mov     dil, 1
0x180076105  cmovz   rcx, rax
0x180076109  call    BfeRundownStateToXml
0x18007610e  mov     rbx, rax
0x180076111  test    rax, rax
0x180076114  jnz     short loc_180076123
0x180076116  cmp     cs:byte_1800F5768, al
0x18007611c  setz    cs:byte_1800F5768
0x180076123  test    dil, dil
0x180076126  jz      short loc_18007613B
0x180076128  lea     rcx, gBfeRundownComponent; lpCriticalSection
0x18007612f  call    cs:__imp_LeaveCriticalSection
0x180076136  nop     dword ptr [rax+rax+00h]
0x18007613b  test    rbx, rbx
0x18007613e  jz      short loc_18007614F
0x180076140  lea     rdx, aBfeetwcallback; "BfeEtwCallbackThreadCallback"
0x180076147  mov     rcx, rbx
0x18007614a  call    WfpReportError
0x18007614f  mov     rbx, [rsp+28h+arg_0]
0x180076154  add     rsp, 20h
0x180076158  pop     rdi
0x180076159  retn
```
