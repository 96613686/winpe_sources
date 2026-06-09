# Int_FWOpenGPOPolicyStore

- ea: `0x180055378`
- end: `0x1800554dc`
- name: `Int_FWOpenGPOPolicyStore`
- size: `356`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005748`
- `0x180009210`
- `0x18000d980`
- `0x18000e750`
- `0x18000f0a0`
- `0x1800149f4`
- `0x180028370`
- `0x1800557bc`

## callees

- `0x180005e0c`
- `0x180026c9c`
- `0x180054d58`
- `0x180055378`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x180055434`
- `fwbase!FwHResultToWindowsError` at `0x180055481`
- `fwbase!FwHResultToWindowsError` at `0x180055434`
- `fwbase!FwHResultToWindowsError` at `0x180055481`
- `FWPolicyIOMgr!FWOpenGPOAndGetRegKey` at `0x180055426`
- `FWPolicyIOMgr!FWOpenGPOAndGetRegKey` at `0x180055426`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x180055473`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x180055473`

## pseudocode

```c
__int64 __fastcall Int_FWOpenGPOPolicyStore(__int64 a1)
{
  int v1; // r9d
  unsigned int v2; // edi
  unsigned int v4; // ebp
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  unsigned int v8; // r14d
  unsigned int RegKey; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  FwPolicy2 *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax

  v1 = *(_DWORD *)(a1 + 72);
  v2 = 0;
  v4 = 0;
  v5 = 3;
  if ( *(_DWORD *)(a1 + 20) != 1 )
    v5 = 1;
  LOBYTE(v4) = (*(_DWORD *)(a1 + 72) & 2) != 0;
  v6 = (unsigned int)v5 | 8;
  if ( (v1 & 2) == 0 )
    v6 = (unsigned int)v5;
  if ( (v1 & 4) != 0 )
    v4 = 1;
  v7 = (unsigned int)v6 | 0xC;
  if ( (v1 & 4) == 0 )
    v7 = (unsigned int)v6;
  if ( (v1 & 8) != 0 )
    v4 = 1;
  v8 = v7 | 4;
  if ( (v1 & 8) == 0 )
    v8 = v7;
  if ( *(_DWORD *)(a1 + 4) != 2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v5, v6);
  if ( !*(_QWORD *)(a1 + 40) )
  {
    RegKey = FWOpenGPOAndGetRegKey(*(_QWORD *)(a1 + 8), v8, v4, a1 + 64, a1 + 40, a1 + 48, a1 + 32);
    v2 = FwHResultToWindowsError(RegKey);
    if ( v2 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_25;
      v13 = 374;
LABEL_24:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v2);
LABEL_25:
      Int_FWCleanupGPOPolicyStore(a1, v10, v11);
      return v2;
    }
    v14 = FwOpenPolicyStore(*(unsigned int *)(a1 + 16), *(unsigned int *)(a1 + 20), *(_QWORD *)(a1 + 48), a1 + 56);
    v2 = FwHResultToWindowsError(v14);
    if ( v2 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_25;
      v13 = 375;
      goto LABEL_24;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180055378  push    rbx
0x18005537a  push    rbp
0x18005537b  push    rsi
0x18005537c  push    rdi
0x18005537d  push    r14
0x18005537f  push    r15
0x180055381  sub     rsp, 48h
0x180055385  mov     r9d, [rcx+48h]
0x180055389  xor     edi, edi
0x18005538b  mov     rbx, rcx
0x18005538e  mov     ebp, edi
0x180055390  lea     r15d, [rdi+1]
0x180055394  cmp     [rcx+14h], r15d
0x180055398  lea     edx, [rdi+3]
0x18005539b  cmovnz  edx, r15d
0x18005539f  bt      r9d, 1
0x1800553a4  mov     r8d, edx
0x1800553a7  setb    bpl
0x1800553ab  or      r8d, 8
0x1800553af  bt      r9d, 1
0x1800553b4  cmovnb  r8d, edx
0x1800553b8  bt      r9d, 2
0x1800553bd  mov     ecx, r8d
0x1800553c0  cmovb   ebp, r15d
0x1800553c4  or      ecx, 0Ch
0x1800553c7  bt      r9d, 2
0x1800553cc  cmovnb  ecx, r8d
0x1800553d0  bt      r9d, 3
0x1800553d5  mov     r14d, ecx
0x1800553d8  cmovb   ebp, r15d
0x1800553dc  or      r14d, 4
0x1800553e0  bt      r9d, 3
0x1800553e5  cmovnb  r14d, ecx
0x1800553e9  cmp     dword ptr [rbx+4], 2
0x1800553ed  jz      short loc_1800553F4
0x1800553ef  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "phClient->HandleType == FWINT_CLIENT_HANDLE_GPO")
0x1800553f4  lea     rcx, [rbx+28h]
0x1800553f8  cmp     [rcx], rdi
0x1800553fb  jnz     loc_1800554CC
0x180055401  lea     rax, [rbx+20h]
0x180055405  mov     r8d, ebp
0x180055408  mov     [rsp+78h+var_48], rax
0x18005540d  lea     rsi, [rbx+30h]
0x180055411  mov     [rsp+78h+var_50], rsi
0x180055416  lea     r9, [rbx+40h]
0x18005541a  mov     [rsp+78h+var_58], rcx
0x18005541f  mov     edx, r14d
0x180055422  mov     rcx, [rbx+8]
0x180055426  call    cs:__imp_FWOpenGPOAndGetRegKey
0x18005542d  nop     dword ptr [rax+rax+00h]
0x180055432  mov     ecx, eax
0x180055434  call    cs:__imp_FwHResultToWindowsError
0x18005543b  nop     dword ptr [rax+rax+00h]
0x180055440  mov     edi, eax
0x180055442  test    eax, eax
0x180055444  jz      short loc_180055466
0x180055446  mov     rcx, cs:WPP_GLOBAL_Control
0x18005544d  lea     rax, WPP_GLOBAL_Control
0x180055454  cmp     rcx, rax
0x180055457  jz      short loc_1800554C4
0x180055459  test    [rcx+1Ch], r15b
0x18005545d  jz      short loc_1800554C4
0x18005545f  mov     edx, 176h
0x180055464  jmp     short loc_1800554B1
0x180055466  mov     r8, [rsi]
0x180055469  lea     r9, [rbx+38h]
0x18005546d  mov     edx, [rbx+14h]
0x180055470  mov     ecx, [rbx+10h]
0x180055473  call    cs:__imp_FwOpenPolicyStore
0x18005547a  nop     dword ptr [rax+rax+00h]
0x18005547f  mov     ecx, eax
0x180055481  call    cs:__imp_FwHResultToWindowsError
0x180055488  nop     dword ptr [rax+rax+00h]
0x18005548d  mov     edi, eax
0x18005548f  test    eax, eax
0x180055491  jz      short loc_1800554CC
0x180055493  mov     rcx, cs:WPP_GLOBAL_Control
0x18005549a  lea     rax, WPP_GLOBAL_Control
0x1800554a1  cmp     rcx, rax
0x1800554a4  jz      short loc_1800554C4
0x1800554a6  test    [rcx+1Ch], r15b
0x1800554aa  jz      short loc_1800554C4
0x1800554ac  mov     edx, 177h
0x1800554b1  mov     rcx, [rcx+10h]
0x1800554b5  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800554bc  mov     r9d, edi
0x1800554bf  call    WPP_SF_d
0x1800554c4  mov     rcx, rbx
0x1800554c7  call    Int_FWCleanupGPOPolicyStore
0x1800554cc  mov     eax, edi
0x1800554ce  add     rsp, 48h
0x1800554d2  pop     r15
0x1800554d4  pop     r14
0x1800554d6  pop     rdi
0x1800554d7  pop     rsi
0x1800554d8  pop     rbp
0x1800554d9  pop     rbx
0x1800554da  retn
```
