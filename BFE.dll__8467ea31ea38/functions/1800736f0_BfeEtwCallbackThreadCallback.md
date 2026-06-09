# BfeEtwCallbackThreadCallback

- ea: `0x1800736f0`
- end: `0x18007378e`
- name: `BfeEtwCallbackThreadCallback`
- size: `158`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x1800736f0`
- `0x1800738a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073721`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073721`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073769`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073769`

## string_xrefs

- `0x180073706`: `BfeEtwCallbackThreadCallback`
- `0x180073774`: `BfeEtwCallbackThreadCallback`
- `0x180073735`: `%ProgramData%\Microsoft\Windows\wfp\wfpStateOne.xml`
- `0x18007372e`: `%ProgramData%\Microsoft\Windows\wfp\wfpStateTwo.xml`

## pseudocode

```c
void __fastcall BfeEtwCallbackThreadCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  char v3; // di
  __int64 v4; // rax
  const WCHAR *v5; // rcx
  __int64 v6; // rbx

  if ( byte_1800F2749 )
  {
    EnterCriticalSection(&gBfeRundownComponent);
    v5 = L"%ProgramData%\\Microsoft\\Windows\\wfp\\wfpStateOne.xml";
    v3 = 1;
    if ( !byte_1800F2748 )
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
    byte_1800F2748 = byte_1800F2748 == 0;
  if ( v3 )
    LeaveCriticalSection(&gBfeRundownComponent);
  if ( v6 )
    WfpReportError(v6, "BfeEtwCallbackThreadCallback");
}

```

## disassembly

```asm
0x1800736f0  mov     [rsp+arg_0], rbx
0x1800736f5  push    rdi
0x1800736f6  sub     rsp, 20h
0x1800736fa  cmp     cs:byte_1800F2749, 0
0x180073701  jnz     short loc_18007371A
0x180073703  xor     dil, dil
0x180073706  lea     rdx, aBfeetwcallback; "BfeEtwCallbackThreadCallback"
0x18007370d  mov     r8d, 15h
0x180073713  call    WfpReportSysErrorAsWinError
0x180073718  jmp     short loc_180073748
0x18007371a  lea     rcx, gBfeRundownComponent; lpCriticalSection
0x180073721  call    cs:__imp_EnterCriticalSection
0x180073727  cmp     cs:byte_1800F2748, 0
0x18007372e  lea     rax, aProgramdataMic; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x180073735  lea     rcx, aProgramdataMic_0; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x18007373c  mov     dil, 1
0x18007373f  cmovz   rcx, rax
0x180073743  call    BfeRundownStateToXml
0x180073748  mov     rbx, rax
0x18007374b  test    rax, rax
0x18007374e  jnz     short loc_18007375D
0x180073750  cmp     cs:byte_1800F2748, al
0x180073756  setz    cs:byte_1800F2748
0x18007375d  test    dil, dil
0x180073760  jz      short loc_18007376F
0x180073762  lea     rcx, gBfeRundownComponent; lpCriticalSection
0x180073769  call    cs:__imp_LeaveCriticalSection
0x18007376f  test    rbx, rbx
0x180073772  jz      short loc_180073783
0x180073774  lea     rdx, aBfeetwcallback; "BfeEtwCallbackThreadCallback"
0x18007377b  mov     rcx, rbx
0x18007377e  call    WfpReportError
0x180073783  mov     rbx, [rsp+28h+arg_0]
0x180073788  add     rsp, 20h
0x18007378c  pop     rdi
0x18007378d  retn
```
