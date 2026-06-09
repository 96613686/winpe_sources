# Endpoint_SM_IsSetDequePointerReissueCountLimitReached

- ea: `0x1400481ec`
- end: `0x140048328`
- name: `Endpoint_SM_IsSetDequePointerReissueCountLimitReached`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400565a0`

## callees

- `0x140002568`
- `0x14000c264`
- `0x14002b300`
- `0x1400481ec`
- `0x1400492a0`
- `0x140057db0`

## string_xrefs

- `0x14004824f`: `Feature_RetryOnContextStateErrorDuringSetDequeuePointer was NOT effective`
- `0x1400482b0`: `Set Dequeue Pointer command following a Stop Endpoint command failed after retries`

## pseudocode

```c
__int64 __fastcall Endpoint_SM_IsSetDequePointerReissueCountLimitReached(_DWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  int v4; // edx

  if ( !(unsigned int)Feature_ROCSEDSDP__private_IsEnabledDeviceUsageNoInline() || a1[42] < 3u )
    return 21;
  v2 = *(_QWORD *)a1;
  ++*(_DWORD *)(v2 + 932);
  ++*(_DWORD *)(v2 + 996);
  *(_BYTE *)(v2 + 872) = 1;
  if ( *(_DWORD *)(*(_QWORD *)a1 + 644LL) == 1 )
    v3 = *(unsigned __int16 *)(*(_QWORD *)a1 + 652LL) | (*(unsigned __int16 *)(*(_QWORD *)a1 + 648LL) << 16);
  else
    v3 = 0;
  MicrosoftTelemetryAssertTriggeredArgsMsgKM(
    "USBXHCI.SYS",
    v3,
    (unsigned int)a1[42],
    "Feature_RetryOnContextStateErrorDuringSetDequeuePointer was NOT effective");
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_DD(
      *((_QWORD *)a1 + 10),
      v4,
      13,
      124,
      (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
      *(_BYTE *)(*((_QWORD *)a1 + 2) + 143LL),
      a1[38]);
  }
  Controller_HwVerifierBreakIfEnabled(
    *(_QWORD *)a1,
    *((_QWORD *)a1 + 1),
    *((_QWORD *)a1 + 3),
    512,
    (__int64)"Set Dequeue Pointer command following a Stop Endpoint command failed after retries",
    0,
    0);
  Controller_ReportFatalErrorEx(*(_QWORD *)a1, 2, 4106, -1, 0xFFFFFFFFLL, *((_QWORD *)a1 + 2), (__int64)a1, 0);
  return 33;
}

```

## disassembly

```asm
0x1400481ec  push    rbx
0x1400481ee  sub     rsp, 40h
0x1400481f2  mov     rbx, rcx
0x1400481f5  call    Feature_ROCSEDSDP__private_IsEnabledDeviceUsageNoInline
0x1400481fa  test    eax, eax
0x1400481fc  jz      loc_14004831C
0x140048202  cmp     dword ptr [rbx+0A8h], 3
0x140048209  jb      loc_14004831C
0x14004820f  mov     rax, [rbx]
0x140048212  inc     dword ptr [rax+3A4h]
0x140048218  inc     dword ptr [rax+3E4h]
0x14004821e  mov     byte ptr [rax+368h], 1
0x140048225  mov     rax, [rbx]; __annotation("Debug", "TelemetryAssert", "FALSE", "Feature_RetryOnContextStateErrorDuringSetDequeuePointer was NOT effective")
0x140048228  cmp     dword ptr [rax+284h], 1
0x14004822f  jnz     short loc_140048246
0x140048231  movzx   edx, word ptr [rax+288h]
0x140048238  movzx   eax, word ptr [rax+28Ch]
0x14004823f  shl     edx, 10h
0x140048242  or      edx, eax
0x140048244  jmp     short loc_140048248
0x140048246  xor     edx, edx
0x140048248  mov     r8d, [rbx+0A8h]
0x14004824f  lea     r9, aFeatureRetryon; "Feature_RetryOnContextStateErrorDuringS"...
0x140048256  lea     rcx, aUsbxhciSys_0; "USBXHCI.SYS"
0x14004825d  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x140048262  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140048269  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140048270  jz      short loc_1400482AC
0x140048272  mov     rax, [rbx+10h]
0x140048276  mov     r9d, 7Ch ; '|'
0x14004827c  mov     dl, 2
0x14004827e  movzx   ecx, byte ptr [rax+8Fh]
0x140048285  lea     r8d, [r9-6Fh]
0x140048289  mov     eax, [rbx+98h]
0x14004828f  mov     dword ptr [rsp+48h+var_18], eax
0x140048293  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x14004829a  mov     dword ptr [rsp+48h+var_20], ecx
0x14004829e  mov     rcx, [rbx+50h]
0x1400482a2  mov     [rsp+48h+var_28], rax
0x1400482a7  call    WPP_RECORDER_SF_DD
0x1400482ac  mov     r8, [rbx+18h]
0x1400482b0  lea     rax, aSetDequeuePoin_0; "Set Dequeue Pointer command following a"...
0x1400482b7  mov     rdx, [rbx+8]
0x1400482bb  mov     r9d, 200h
0x1400482c1  mov     rcx, [rbx]
0x1400482c4  mov     [rsp+48h+var_18], 0
0x1400482cd  mov     [rsp+48h+var_20], 0
0x1400482d6  mov     [rsp+48h+var_28], rax
0x1400482db  call    Controller_HwVerifierBreakIfEnabled
0x1400482e0  mov     rax, [rbx+10h]
0x1400482e4  mov     r9d, 0FFFFFFFFh
0x1400482ea  mov     rcx, [rbx]
0x1400482ed  mov     edx, 2
0x1400482f2  mov     [rsp+48h+var_10], 0
0x1400482fb  mov     r8d, 100Ah
0x140048301  mov     [rsp+48h+var_18], rbx
0x140048306  mov     [rsp+48h+var_20], rax
0x14004830b  mov     [rsp+48h+var_28], r9
0x140048310  call    Controller_ReportFatalErrorEx
0x140048315  mov     eax, 21h ; '!'
0x14004831a  jmp     short loc_140048321
0x14004831c  mov     eax, 15h
0x140048321  add     rsp, 40h
0x140048325  pop     rbx
0x140048326  retn
```
