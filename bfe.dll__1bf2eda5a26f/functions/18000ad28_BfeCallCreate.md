# BfeCallCreate

- ea: `0x18000ad28`
- end: `0x18000aeec`
- name: `BfeCallCreate`
- size: `452`
- prototype: `__int64 __fastcall(__int64, __int64, int, char, _QWORD *lpTlsValue)`
- caller_count: `121`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000857c`
- `0x1800086e0`
- `0x180008a90`
- `0x180008cb0`
- `0x180009030`
- `0x180009200`
- `0x180009650`
- `0x180009700`
- `0x180009c30`
- `0x18000a140`
- `0x18000a730`
- `0x18000bf10`
- `0x18001c950`
- `0x18001d7a0`
- `0x18001df90`
- `0x180020338`
- `0x18002040c`
- `0x180021bd0`
- `0x180025460`
- `0x180025d30`
- `0x180027990`
- `0x18003cdb0`
- `0x1800402f0`
- `0x180042410`
- `0x18004259c`
- `0x180043320`
- `0x180043a30`
- `0x180043ff4`
- `0x180044898`
- `0x180045130`
- `0x1800451d0`
- `0x180045470`
- `0x180045e30`
- `0x1800468a0`
- `0x180046ff0`
- `0x180047080`
- `0x180047350`
- `0x180048dd0`
- `0x180048e60`
- `0x180048ef0`
- `0x1800497e0`
- `0x18004a0a0`
- `0x180057200`
- `0x1800582c0`
- `0x1800602c0`
- `0x180060380`
- `0x180060430`
- `0x180060510`
- `0x180060620`
- `0x1800606b0`

## callees

- `0x18000ad28`
- `0x18001236c`
- `0x180018b74`
- `0x180037bcc`
- `0x1800398f8`
- `0x18005529c`
- `0x1800557a4`
- `0x1800575c4`
- `0x1800652c0`
- `0x1800652f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ad5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ad5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000adcb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000aec6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000adcb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000aec6`

## string_xrefs

- `0x18000ae99`: `bfe.dll`
- `0x18000ad80`: `BfeCallCreate`

## pseudocode

```c
__int64 __fastcall BfeCallCreate(__int64 a1, __int64 a2, int a3, char a4, _QWORD *lpTlsValue)
{
  __int64 v6; // r14
  int IsEnabledDeviceUsageNoInline; // eax
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rax
  int v14; // eax

  v6 = a3;
  if ( (qword_1800F2668[372] & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = qword_1800F2668[372] & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline && TlsGetValue(gBfeContextComponent) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (qword_1800F2668[371] & 0x10) != 0 )
    v9 = qword_1800F2668[371] & 1;
  else
    v9 = Feature_Netsec_BugFix_Bfe33010__private_IsEnabledDeviceUsageNoInline();
  if ( v9 && ((unsigned int)v6 > 6 || *(_DWORD *)(a2 + 36) > 2u) )
  {
    MicrosoftTelemetryAssertTriggeredArgs("bfe.dll", (unsigned int)v6, *(unsigned int *)(a2 + 36));
    v11 = 2150760501LL;
    goto LABEL_37;
  }
  lpTlsValue[1] = 0;
  lpTlsValue[2] = 0;
  lpTlsValue[3] = 0;
  *lpTlsValue = a2;
  TlsSetValue(gBfeContextComponent, lpTlsValue);
  if ( (a4 & 1) == 0 && (*(_BYTE *)(*(_QWORD *)(a2 + 16) + 32LL) & 1) != 0 )
  {
    v11 = 2150760459LL;
LABEL_37:
    v12 = WfpReportSysErrorAsWinError(v10, "BfeCallCreate", v11);
LABEL_38:
    if ( !v12 )
      return v12;
    goto LABEL_39;
  }
  if ( (a4 & 2) != 0 && !*(_DWORD *)(*(_QWORD *)(a2 + 16) + 64LL) )
  {
    v11 = 2150760469LL;
    goto LABEL_37;
  }
  v11 = *((unsigned int *)qword_1800C6AB0 + 3 * v6 + *(int *)(a2 + 36));
  if ( !(_DWORD)v11 )
  {
    v13 = BfeSessionResume(a2);
    goto LABEL_27;
  }
  if ( (_DWORD)v11 == 1 || (v10 = (unsigned int)(v11 - 2), (_DWORD)v11 == 2) )
  {
    v13 = BfeTxnBegin(*(_DWORD *)(*(_QWORD *)(a2 + 16) + 36LL));
LABEL_27:
    v12 = v13;
    if ( v13 )
    {
LABEL_39:
      TlsSetValue(gBfeContextComponent, 0);
      if ( v12 )
        WfpReportError(v12, "BfeCallCreate");
      return v12;
    }
    lpTlsValue[1] = a2 + 32;
    goto LABEL_29;
  }
  if ( (_DWORD)v11 != 3 )
    goto LABEL_37;
  v12 = 0;
LABEL_29:
  if ( (qword_1800F2668[372] & 0x10) != 0 )
    v14 = qword_1800F2668[372] & 1;
  else
    v14 = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageNoInline();
  if ( v14 && !*(_DWORD *)(a2 + 36) && (unsigned int)v6 <= 1 )
  {
    BfeTxnSetLockTimeout(0);
    goto LABEL_38;
  }
  return v12;
}

```

## disassembly

```asm
0x18000ad28  push    rbx
0x18000ad2a  push    rbp
0x18000ad2b  push    rsi
0x18000ad2c  push    rdi
0x18000ad2d  push    r12
0x18000ad2f  push    r14
0x18000ad31  sub     rsp, 28h
0x18000ad35  mov     ebx, r9d
0x18000ad38  movsxd  r14, r8d
0x18000ad3b  mov     rdi, rdx
0x18000ad3e  mov     eax, dword ptr cs:qword_1800F2668+0BA0h
0x18000ad44  test    al, 10h
0x18000ad46  jz      short loc_18000AD4D
0x18000ad48  and     eax, 1
0x18000ad4b  jmp     short loc_18000AD52
0x18000ad4d  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageNoInline
0x18000ad52  test    eax, eax
0x18000ad54  jz      short loc_18000AD6C
0x18000ad56  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000ad5c  call    cs:__imp_TlsGetValue
0x18000ad62  test    rax, rax
0x18000ad65  jz      short loc_18000AD6C
0x18000ad67  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ad6c  mov     eax, dword ptr cs:qword_1800F2668+0B98h
0x18000ad72  test    al, 10h
0x18000ad74  jz      short loc_18000AD7B
0x18000ad76  and     eax, 1
0x18000ad79  jmp     short loc_18000AD80
0x18000ad7b  call    Feature_Netsec_BugFix_Bfe33010__private_IsEnabledDeviceUsageNoInline
0x18000ad80  lea     r12, aBfecallcreate; "BfeCallCreate"
0x18000ad87  test    eax, eax
0x18000ad89  jz      short loc_18000AD9F
0x18000ad8b  cmp     r14d, 6
0x18000ad8f  ja      loc_18000AE95
0x18000ad95  cmp     dword ptr [rdi+24h], 2
0x18000ad99  ja      loc_18000AE95
0x18000ad9f  mov     rsi, [rsp+58h+lpTlsValue]
0x18000ada7  mov     rdx, rsi; lpTlsValue
0x18000adaa  mov     qword ptr [rsi+8], 0
0x18000adb2  mov     qword ptr [rsi+10h], 0
0x18000adba  mov     qword ptr [rsi+18h], 0
0x18000adc2  mov     [rsi], rdi
0x18000adc5  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000adcb  call    cs:__imp_TlsSetValue
0x18000add1  test    bl, 1
0x18000add4  jnz     short loc_18000ADEB
0x18000add6  mov     rax, [rdi+10h]
0x18000adda  test    byte ptr [rax+20h], 1
0x18000adde  jz      short loc_18000ADEB
0x18000ade0  mov     r8d, 8032000Bh
0x18000ade6  jmp     loc_18000AEAE
0x18000adeb  test    bl, 2
0x18000adee  jz      short loc_18000AE05
0x18000adf0  mov     rax, [rdi+10h]
0x18000adf4  cmp     dword ptr [rax+40h], 0
0x18000adf8  jnz     short loc_18000AE05
0x18000adfa  mov     r8d, 80320015h
0x18000ae00  jmp     loc_18000AEAE
0x18000ae05  movsxd  rax, dword ptr [rdi+24h]
0x18000ae09  lea     rcx, [r14+r14*2]
0x18000ae0d  add     rcx, rax
0x18000ae10  lea     r8, qword_1800C6AB0
0x18000ae17  lea     rbp, [rdi+20h]
0x18000ae1b  mov     r8d, [r8+rcx*4]
0x18000ae1f  mov     ecx, r8d
0x18000ae22  test    r8d, r8d
0x18000ae25  jz      short loc_18000AE54
0x18000ae27  sub     ecx, 1
0x18000ae2a  jz      short loc_18000AE4D
0x18000ae2c  sub     ecx, 1
0x18000ae2f  jz      short loc_18000AE3A
0x18000ae31  cmp     ecx, 1
0x18000ae34  jnz     short loc_18000AEAE
0x18000ae36  xor     ebx, ebx
0x18000ae38  jmp     short loc_18000AE68
0x18000ae3a  xor     edx, edx
0x18000ae3c  mov     rcx, [rdi+10h]
0x18000ae40  mov     r8, rbp
0x18000ae43  mov     ecx, [rcx+24h]; dwMilliseconds
0x18000ae46  call    BfeTxnBegin
0x18000ae4b  jmp     short loc_18000AE5C
0x18000ae4d  mov     edx, 1
0x18000ae52  jmp     short loc_18000AE3C
0x18000ae54  mov     rcx, rdi
0x18000ae57  call    BfeSessionResume
0x18000ae5c  mov     rbx, rax
0x18000ae5f  test    rax, rax
0x18000ae62  jnz     short loc_18000AEBE
0x18000ae64  mov     [rsi+8], rbp
0x18000ae68  mov     eax, dword ptr cs:qword_1800F2668+0BA0h
0x18000ae6e  test    al, 10h
0x18000ae70  jz      short loc_18000AE77
0x18000ae72  and     eax, 1
0x18000ae75  jmp     short loc_18000AE7C
0x18000ae77  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageNoInline
0x18000ae7c  test    eax, eax
0x18000ae7e  jz      short loc_18000AEDC
0x18000ae80  cmp     dword ptr [rdi+24h], 0
0x18000ae84  jnz     short loc_18000AEDC
0x18000ae86  cmp     r14d, 1
0x18000ae8a  ja      short loc_18000AEDC
0x18000ae8c  xor     ecx, ecx
0x18000ae8e  call    BfeTxnSetLockTimeout
0x18000ae93  jmp     short loc_18000AEB9
0x18000ae95  mov     r8d, [rdi+24h]
0x18000ae99  lea     rcx, aBfeDll_0; "bfe.dll"
0x18000aea0  mov     edx, r14d
0x18000aea3  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000aea8  mov     r8d, 80320035h
0x18000aeae  mov     rdx, r12
0x18000aeb1  call    WfpReportSysErrorAsWinError
0x18000aeb6  mov     rbx, rax
0x18000aeb9  test    rbx, rbx
0x18000aebc  jz      short loc_18000AEDC
0x18000aebe  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000aec4  xor     edx, edx; lpTlsValue
0x18000aec6  call    cs:__imp_TlsSetValue
0x18000aecc  test    rbx, rbx
0x18000aecf  jz      short loc_18000AEDC
0x18000aed1  mov     rdx, r12
0x18000aed4  mov     rcx, rbx
0x18000aed7  call    WfpReportError
0x18000aedc  mov     rax, rbx
0x18000aedf  add     rsp, 28h
0x18000aee3  pop     r14
0x18000aee5  pop     r12
0x18000aee7  pop     rdi
0x18000aee8  pop     rsi
0x18000aee9  pop     rbp
0x18000aeea  pop     rbx
0x18000aeeb  retn
```
