# BfeCallCreate

- ea: `0x18000b3d4`
- end: `0x18000b5ab`
- name: `BfeCallCreate`
- size: `471`
- prototype: `__int64 __fastcall(int, int, int, int, LPVOID lpTlsValue)`
- caller_count: `121`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008b80`
- `0x180008d00`
- `0x1800090f0`
- `0x180009220`
- `0x1800095a0`
- `0x180009780`
- `0x180009bf0`
- `0x180009cb0`
- `0x18000a220`
- `0x18000a770`
- `0x18000ada0`
- `0x18000c640`
- `0x18001ec20`
- `0x18001f780`
- `0x18001fa70`
- `0x180022a4c`
- `0x1800242c0`
- `0x180026204`
- `0x18003e800`
- `0x180041610`
- `0x1800435e0`
- `0x180043810`
- `0x180043a30`
- `0x180044c50`
- `0x180044f80`
- `0x180045430`
- `0x1800459a0`
- `0x180045ee4`
- `0x180046838`
- `0x180046f60`
- `0x18004712c`
- `0x180047310`
- `0x180047cb0`
- `0x1800488b0`
- `0x180048ff0`
- `0x1800490c0`
- `0x1800492b0`
- `0x18004ae20`
- `0x18004aeb0`
- `0x18004af40`
- `0x18004b770`
- `0x18004bee0`
- `0x180059400`
- `0x18005a1f0`
- `0x1800625e0`
- `0x1800626a0`
- `0x180062750`
- `0x180062830`
- `0x180062940`
- `0x1800629d0`

## callees

- `0x18000b3d4`
- `0x180012d8c`
- `0x1800197d0`
- `0x180036970`
- `0x18003844c`
- `0x18005715c`
- `0x1800575a0`
- `0x1800592f4`
- `0x180067704`
- `0x180067738`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b408`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b408`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b47d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b57e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b47d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b57e`

## string_xrefs

- `0x18000b551`: `bfe.dll`
- `0x18000b432`: `BfeCallCreate`

## pseudocode

```c
__int64 __fastcall BfeCallCreate(__int64 a1, __int64 a2, int a3, char a4, _QWORD *lpTlsValue)
{
  __int64 v6; // r14
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rbx
  __int64 v14; // rax
  int v15; // eax

  v6 = a3;
  if ( (Feature_BugFix_FwBfeSessions__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BugFix_FwBfeSessions__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline && TlsGetValue(gBfeContextComponent) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
  if ( (Feature_Netsec_BugFix_Bfe33010__private_featureState & 0x10) != 0 )
    v10 = Feature_Netsec_BugFix_Bfe33010__private_featureState & 1;
  else
    v10 = Feature_Netsec_BugFix_Bfe33010__private_IsEnabledDeviceUsageNoInline();
  if ( v10 && ((unsigned int)v6 > 6 || *(_DWORD *)(a2 + 36) > 2u) )
  {
    MicrosoftTelemetryAssertTriggeredArgs("bfe.dll", (unsigned int)v6, *(unsigned int *)(a2 + 36));
    v12 = 2150760501LL;
    goto LABEL_37;
  }
  lpTlsValue[1] = 0;
  lpTlsValue[2] = 0;
  lpTlsValue[3] = 0;
  *lpTlsValue = a2;
  TlsSetValue(gBfeContextComponent, lpTlsValue);
  if ( (a4 & 1) == 0 && (*(_BYTE *)(*(_QWORD *)(a2 + 16) + 32LL) & 1) != 0 )
  {
    v12 = 2150760459LL;
LABEL_37:
    v13 = WfpReportSysErrorAsWinError(v11, "BfeCallCreate", v12);
LABEL_38:
    if ( !v13 )
      return v13;
    goto LABEL_39;
  }
  if ( (a4 & 2) != 0 && !*(_DWORD *)(*(_QWORD *)(a2 + 16) + 64LL) )
  {
    v12 = 2150760469LL;
    goto LABEL_37;
  }
  v12 = *((unsigned int *)qword_1800C9A80 + 3 * v6 + *(int *)(a2 + 36));
  if ( !(_DWORD)v12 )
  {
    v14 = BfeSessionResume(a2);
    goto LABEL_27;
  }
  if ( (_DWORD)v12 == 1 || (v11 = (unsigned int)(v12 - 2), (_DWORD)v12 == 2) )
  {
    v14 = BfeTxnBegin(*(_DWORD *)(*(_QWORD *)(a2 + 16) + 36LL));
LABEL_27:
    v13 = v14;
    if ( v14 )
    {
LABEL_39:
      TlsSetValue(gBfeContextComponent, 0);
      if ( v13 )
        WfpReportError(v13, "BfeCallCreate");
      return v13;
    }
    lpTlsValue[1] = a2 + 32;
    goto LABEL_29;
  }
  if ( (_DWORD)v12 != 3 )
    goto LABEL_37;
  v13 = 0;
LABEL_29:
  if ( (Feature_BugFix_FwBfeSessions__private_featureState & 0x10) != 0 )
    v15 = Feature_BugFix_FwBfeSessions__private_featureState & 1;
  else
    v15 = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageNoInline();
  if ( v15 && !*(_DWORD *)(a2 + 36) && (unsigned int)v6 <= 1 )
  {
    BfeTxnSetLockTimeout(0);
    goto LABEL_38;
  }
  return v13;
}

```

## disassembly

```asm
0x18000b3d4  push    rbx
0x18000b3d6  push    rbp
0x18000b3d7  push    rsi
0x18000b3d8  push    rdi
0x18000b3d9  push    r12
0x18000b3db  push    r14
0x18000b3dd  sub     rsp, 28h
0x18000b3e1  mov     ebx, r9d
0x18000b3e4  movsxd  r14, r8d
0x18000b3e7  mov     rdi, rdx
0x18000b3ea  mov     eax, cs:Feature_BugFix_FwBfeSessions__private_featureState
0x18000b3f0  test    al, 10h
0x18000b3f2  jz      short loc_18000B3F9
0x18000b3f4  and     eax, 1
0x18000b3f7  jmp     short loc_18000B3FE
0x18000b3f9  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageNoInline
0x18000b3fe  test    eax, eax
0x18000b400  jz      short loc_18000B41E
0x18000b402  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000b408  call    cs:__imp_TlsGetValue
0x18000b40f  nop     dword ptr [rax+rax+00h]
0x18000b414  test    rax, rax
0x18000b417  jz      short loc_18000B41E
0x18000b419  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeCallGet() == NULL", "BfeCallCreate: BfeCallGet() returned a valid open Call")
0x18000b41e  mov     eax, cs:Feature_Netsec_BugFix_Bfe33010__private_featureState
0x18000b424  test    al, 10h
0x18000b426  jz      short loc_18000B42D
0x18000b428  and     eax, 1
0x18000b42b  jmp     short loc_18000B432
0x18000b42d  call    Feature_Netsec_BugFix_Bfe33010__private_IsEnabledDeviceUsageNoInline
0x18000b432  lea     r12, aBfecallcreate; "BfeCallCreate"
0x18000b439  test    eax, eax
0x18000b43b  jz      short loc_18000B451
0x18000b43d  cmp     r14d, 6
0x18000b441  ja      loc_18000B54D
0x18000b447  cmp     dword ptr [rdi+24h], 2
0x18000b44b  ja      loc_18000B54D
0x18000b451  mov     rsi, [rsp+58h+lpTlsValue]
0x18000b459  mov     rdx, rsi; lpTlsValue
0x18000b45c  mov     qword ptr [rsi+8], 0
0x18000b464  mov     qword ptr [rsi+10h], 0
0x18000b46c  mov     qword ptr [rsi+18h], 0
0x18000b474  mov     [rsi], rdi
0x18000b477  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000b47d  call    cs:__imp_TlsSetValue
0x18000b484  nop     dword ptr [rax+rax+00h]
0x18000b489  test    bl, 1
0x18000b48c  jnz     short loc_18000B4A3
0x18000b48e  mov     rax, [rdi+10h]
0x18000b492  test    byte ptr [rax+20h], 1
0x18000b496  jz      short loc_18000B4A3
0x18000b498  mov     r8d, 8032000Bh
0x18000b49e  jmp     loc_18000B566
0x18000b4a3  test    bl, 2
0x18000b4a6  jz      short loc_18000B4BD
0x18000b4a8  mov     rax, [rdi+10h]
0x18000b4ac  cmp     dword ptr [rax+40h], 0
0x18000b4b0  jnz     short loc_18000B4BD
0x18000b4b2  mov     r8d, 80320015h
0x18000b4b8  jmp     loc_18000B566
0x18000b4bd  movsxd  rax, dword ptr [rdi+24h]
0x18000b4c1  lea     rcx, [r14+r14*2]
0x18000b4c5  add     rcx, rax
0x18000b4c8  lea     r8, qword_1800C9A80
0x18000b4cf  lea     rbp, [rdi+20h]
0x18000b4d3  mov     r8d, [r8+rcx*4]
0x18000b4d7  mov     ecx, r8d
0x18000b4da  test    r8d, r8d
0x18000b4dd  jz      short loc_18000B50C
0x18000b4df  sub     ecx, 1
0x18000b4e2  jz      short loc_18000B505
0x18000b4e4  sub     ecx, 1
0x18000b4e7  jz      short loc_18000B4F2
0x18000b4e9  cmp     ecx, 1
0x18000b4ec  jnz     short loc_18000B566
0x18000b4ee  xor     ebx, ebx
0x18000b4f0  jmp     short loc_18000B520
0x18000b4f2  xor     edx, edx
0x18000b4f4  mov     rcx, [rdi+10h]
0x18000b4f8  mov     r8, rbp
0x18000b4fb  mov     ecx, [rcx+24h]; dwMilliseconds
0x18000b4fe  call    BfeTxnBegin
0x18000b503  jmp     short loc_18000B514
0x18000b505  mov     edx, 1
0x18000b50a  jmp     short loc_18000B4F4
0x18000b50c  mov     rcx, rdi
0x18000b50f  call    BfeSessionResume
0x18000b514  mov     rbx, rax
0x18000b517  test    rax, rax
0x18000b51a  jnz     short loc_18000B576
0x18000b51c  mov     [rsi+8], rbp
0x18000b520  mov     eax, cs:Feature_BugFix_FwBfeSessions__private_featureState
0x18000b526  test    al, 10h
0x18000b528  jz      short loc_18000B52F
0x18000b52a  and     eax, 1
0x18000b52d  jmp     short loc_18000B534
0x18000b52f  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageNoInline
0x18000b534  test    eax, eax
0x18000b536  jz      short loc_18000B59A
0x18000b538  cmp     dword ptr [rdi+24h], 0
0x18000b53c  jnz     short loc_18000B59A
0x18000b53e  cmp     r14d, 1
0x18000b542  ja      short loc_18000B59A
0x18000b544  xor     ecx, ecx
0x18000b546  call    BfeTxnSetLockTimeout
0x18000b54b  jmp     short loc_18000B571
0x18000b54d  mov     r8d, [rdi+24h]; __annotation("Debug", "TelemetryAssert", "FALSE", "BfeCallCreate: Bad fsm indices")
0x18000b551  lea     rcx, aBfeDll_0; "bfe.dll"
0x18000b558  mov     edx, r14d
0x18000b55b  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000b560  mov     r8d, 80320035h
0x18000b566  mov     rdx, r12
0x18000b569  call    WfpReportSysErrorAsWinError
0x18000b56e  mov     rbx, rax
0x18000b571  test    rbx, rbx
0x18000b574  jz      short loc_18000B59A
0x18000b576  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000b57c  xor     edx, edx; lpTlsValue
0x18000b57e  call    cs:__imp_TlsSetValue
0x18000b585  nop     dword ptr [rax+rax+00h]
0x18000b58a  test    rbx, rbx
0x18000b58d  jz      short loc_18000B59A
0x18000b58f  mov     rdx, r12
0x18000b592  mov     rcx, rbx
0x18000b595  call    WfpReportError
0x18000b59a  mov     rax, rbx
0x18000b59d  add     rsp, 28h
0x18000b5a1  pop     r14
0x18000b5a3  pop     r12
0x18000b5a5  pop     rdi
0x18000b5a6  pop     rsi
0x18000b5a7  pop     rbp
0x18000b5a8  pop     rbx
0x18000b5a9  retn
```
