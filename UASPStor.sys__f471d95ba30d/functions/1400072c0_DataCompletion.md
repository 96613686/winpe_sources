# DataCompletion

- ea: `0x1400072c0`
- end: `0x140007625`
- name: `DataCompletion`
- size: `869`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002964`
- `0x140005744`
- `0x1400072c0`
- `0x1400081dc`
- `0x140009098`
- `0x1400091b0`
- `0x1400098a0`
- `0x140009b78`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x140007558`
- `ntoskrnl!IoCancelIrp` at `0x140007558`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000734c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400073a5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000742c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400074ca`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007530`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000758c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400075f9`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000734c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400073a5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000742c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400074ca`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007530`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000758c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400075f9`

## pseudocode

```c
__int64 __fastcall DataCompletion(_QWORD *a1, __int64 a2, int a3, __int64 a4)
{
  int v6; // r15d
  int v7; // eax
  int v8; // edx
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edx
  char v13; // r15
  __int64 v14; // rax
  __int64 v16; // rbx
  int v17; // eax
  int v18; // edx
  int v19; // eax
  int v20; // edx
  int v21; // eax
  int v22; // edx
  int Default; // eax
  int v24; // edx

  v6 = *(_DWORD *)(a1[11] + 4LL);
  *((_DWORD *)a1 + 3) = 3;
  if ( a3 == -1073741536 || v6 == -1073676288 )
  {
    v13 = 2;
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v24) = 3;
      WPP_RECORDER_SF_Di(Default, v24, 2, 33);
    }
  }
  else
  {
    if ( !v6 && a3 >= 0 )
    {
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v7 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v8) = 4;
        WPP_RECORDER_SF_Di(v7, v8, 3, 39);
      }
      return QueueUpdateCompletion(a1);
    }
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v10) = 3;
      WPP_RECORDER_SF_DiD(v9, v10, 2, 34);
    }
    if ( (unsigned int)(v6 + 1073741807) <= 1 || v6 == -1073741820 )
    {
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = a1[4];
        v17 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v18) = 3;
        WPP_RECORDER_SF_i(v17, v18, 2, 35, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v16);
      }
      UaspQueueWorkItem(*a1, &ResetPipeWorkItem, 0, a4);
      if ( *((_DWORD *)a1 + 2) == 2 )
      {
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v19 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v20) = 4;
          WPP_RECORDER_SF_(v19, v20, 3, 36, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
        }
        IoCancelIrp((PIRP)a1[14]);
      }
      if ( *((_DWORD *)a1 + 4) == 2 )
      {
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v21 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v22) = 4;
          WPP_RECORDER_SF_(v21, v22, 3, 37, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
        }
        CancelStatusIrp(a1);
      }
    }
    else if ( v6 == -1073713152 || a3 == -1073741667 || a3 == -1073741810 )
    {
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v11 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v12) = 3;
        WPP_RECORDER_SF_(v11, v12, 2, 38, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
      }
      UaspQueueWorkItem(*a1, &BulkResetDeviceWorkItem, *(_QWORD *)(*a1 + 160LL), 0);
    }
    v13 = 4;
  }
  v14 = a1[4];
  if ( *(_BYTE *)(v14 + 3) <= 1u )
    *(_BYTE *)(v14 + 3) = v13;
  return QueueUpdateCompletion(a1);
}

```

## disassembly

```asm
0x1400072c0  mov     [rsp+arg_0], rbx
0x1400072c5  mov     [rsp+arg_8], rbp
0x1400072ca  mov     [rsp+arg_18], r9
0x1400072cf  push    rsi
0x1400072d0  push    rdi
0x1400072d1  push    r13
0x1400072d3  push    r14
0x1400072d5  push    r15
0x1400072d7  sub     rsp, 40h
0x1400072db  mov     rax, [rcx+58h]
0x1400072df  mov     r13d, r8d
0x1400072e2  mov     rsi, rcx
0x1400072e5  mov     r15d, [rax+4]
0x1400072e9  mov     dword ptr [rcx+0Ch], 3
0x1400072f0  cmp     r8d, 0C0000120h
0x1400072f7  jz      loc_1400075BD
0x1400072fd  cmp     r15d, 0C0010000h
0x140007304  jz      loc_1400075BD
0x14000730a  xor     ebp, ebp
0x14000730c  test    r15d, r15d
0x14000730f  jnz     short loc_140007378
0x140007311  test    r8d, r8d
0x140007314  js      short loc_140007378
0x140007316  cmp     cs:gTracingEnabled, bpl
0x14000731d  jz      loc_140007480
0x140007323  lea     r14, WPP_RECORDER_INITIALIZED
0x14000732a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007331  jz      loc_140007480
0x140007337  movzx   ebx, word ptr [rcx+28h]
0x14000733b  lea     ebp, [r15+27h]
0x14000733f  mov     rdi, [rcx+20h]
0x140007343  dec     ebx
0x140007345  mov     rcx, cs:WPP_GLOBAL_Control
0x14000734c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007353  nop     dword ptr [rax+rax+00h]
0x140007358  mov     [rsp+68h+var_38], rdi
0x14000735d  lea     r8d, [r15+3]
0x140007361  mov     rcx, rax
0x140007364  mov     dword ptr [rsp+68h+var_40], ebx
0x140007368  movzx   r9d, bp
0x14000736c  mov     dl, 4
0x14000736e  call    WPP_RECORDER_SF_Di
0x140007373  jmp     loc_140007480
0x140007378  cmp     cs:gTracingEnabled, bpl
0x14000737f  lea     r14, WPP_RECORDER_INITIALIZED
0x140007386  mov     dil, 4
0x140007389  jz      short loc_1400073D6
0x14000738b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007392  jz      short loc_1400073D6
0x140007394  movzx   ebx, word ptr [rcx+28h]
0x140007398  mov     rdi, [rcx+20h]
0x14000739c  dec     ebx
0x14000739e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073a5  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400073ac  nop     dword ptr [rax+rax+00h]
0x1400073b1  mov     r9d, 22h ; '"'
0x1400073b7  mov     [rsp+68h+var_30], r15d
0x1400073bc  mov     rcx, rax
0x1400073bf  mov     [rsp+68h+var_38], rdi
0x1400073c4  mov     dl, 3
0x1400073c6  mov     dword ptr [rsp+68h+var_40], ebx
0x1400073ca  lea     r8d, [r9-20h]
0x1400073ce  call    WPP_RECORDER_SF_DiD
0x1400073d3  mov     dil, 4
0x1400073d6  lea     eax, [r15+3FFFFFEFh]
0x1400073dd  cmp     eax, 1
0x1400073e0  jbe     loc_1400074A0
0x1400073e6  cmp     r15d, 0C0000004h
0x1400073ed  jz      loc_1400074A0
0x1400073f3  cmp     r15d, 0C0007000h
0x1400073fa  jz      short loc_14000740E
0x1400073fc  cmp     r13d, 0C000009Dh
0x140007403  jz      short loc_14000740E
0x140007405  cmp     r13d, 0C000000Eh
0x14000740c  jnz     short loc_14000746F
0x14000740e  cmp     cs:gTracingEnabled, bpl
0x140007415  jz      short loc_140007456
0x140007417  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000741e  jz      short loc_140007456
0x140007420  mov     rcx, cs:WPP_GLOBAL_Control
0x140007427  mov     ebx, 26h ; '&'
0x14000742c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007433  nop     dword ptr [rax+rax+00h]
0x140007438  lea     r15, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x14000743f  movzx   r9d, bx
0x140007443  mov     rcx, rax
0x140007446  mov     [rsp+68h+var_48], r15
0x14000744b  lea     r8d, [rbx-24h]
0x14000744f  mov     dl, 3
0x140007451  call    WPP_RECORDER_SF_
0x140007456  mov     rcx, [rsi]
0x140007459  lea     rdx, BulkResetDeviceWorkItem
0x140007460  xor     r9d, r9d
0x140007463  mov     r8, [rcx+0A0h]
0x14000746a  call    UaspQueueWorkItem
0x14000746f  mov     r15b, 4
0x140007472  mov     rax, [rsi+20h]
0x140007476  cmp     byte ptr [rax+3], 1
0x14000747a  ja      short loc_140007480
0x14000747c  mov     [rax+3], r15b
0x140007480  mov     rcx, rsi
0x140007483  call    QueueUpdateCompletion
0x140007488  mov     rbx, [rsp+68h+arg_0]
0x14000748d  mov     rbp, [rsp+68h+arg_8]
0x140007492  add     rsp, 40h
0x140007496  pop     r15
0x140007498  pop     r14
0x14000749a  pop     r13
0x14000749c  pop     rdi
0x14000749d  pop     rsi
0x14000749e  retn
0x1400074a0  cmp     cs:gTracingEnabled, bpl
0x1400074a7  lea     r15, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x1400074ae  jz      short loc_1400074F2
0x1400074b0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400074b7  jz      short loc_1400074F2
0x1400074b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400074c0  mov     r13d, 23h ; '#'
0x1400074c6  mov     rbx, [rsi+20h]
0x1400074ca  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400074d1  nop     dword ptr [rax+rax+00h]
0x1400074d6  mov     [rsp+68h+var_40], rbx
0x1400074db  lea     r8d, [r13-21h]
0x1400074df  mov     rcx, rax
0x1400074e2  mov     [rsp+68h+var_48], r15
0x1400074e7  movzx   r9d, r13w
0x1400074eb  mov     dl, 3
0x1400074ed  call    WPP_RECORDER_SF_i
0x1400074f2  mov     r9, [rsp+68h+arg_18]
0x1400074fa  lea     rdx, ResetPipeWorkItem
0x140007501  mov     rcx, [rsi]
0x140007504  xor     r8d, r8d
0x140007507  call    UaspQueueWorkItem
0x14000750c  cmp     dword ptr [rsi+8], 2
0x140007510  jnz     short loc_140007564
0x140007512  cmp     cs:gTracingEnabled, bpl
0x140007519  jz      short loc_140007554
0x14000751b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007522  jz      short loc_140007554
0x140007524  mov     rcx, cs:WPP_GLOBAL_Control
0x14000752b  mov     ebx, 24h ; '$'
0x140007530  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007537  nop     dword ptr [rax+rax+00h]
0x14000753c  movzx   r9d, bx
0x140007540  mov     [rsp+68h+var_48], r15
0x140007545  mov     rcx, rax
0x140007548  lea     r8d, [rbx-21h]
0x14000754c  mov     dl, dil
0x14000754f  call    WPP_RECORDER_SF_
0x140007554  mov     rcx, [rsi+70h]; Irp
0x140007558  call    cs:__imp_IoCancelIrp
0x14000755f  nop     dword ptr [rax+rax+00h]
0x140007564  cmp     dword ptr [rsi+10h], 2
0x140007568  jnz     loc_14000746F
0x14000756e  cmp     cs:gTracingEnabled, bpl
0x140007575  jz      short loc_1400075B0
0x140007577  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000757e  jz      short loc_1400075B0
0x140007580  mov     rcx, cs:WPP_GLOBAL_Control
0x140007587  mov     ebx, 25h ; '%'
0x14000758c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007593  nop     dword ptr [rax+rax+00h]
0x140007598  movzx   r9d, bx
0x14000759c  mov     [rsp+68h+var_48], r15
0x1400075a1  mov     rcx, rax
0x1400075a4  lea     r8d, [rbx-22h]
0x1400075a8  mov     dl, dil
0x1400075ab  call    WPP_RECORDER_SF_
0x1400075b0  mov     rcx, rsi
0x1400075b3  call    CancelStatusIrp
0x1400075b8  jmp     loc_14000746F
0x1400075bd  xor     ebp, ebp
0x1400075bf  mov     r15b, 2
0x1400075c2  cmp     cs:gTracingEnabled, bpl
0x1400075c9  jz      loc_140007472
0x1400075cf  lea     r14, WPP_RECORDER_INITIALIZED
0x1400075d6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400075dd  jz      loc_140007472
0x1400075e3  movzx   ebx, word ptr [rcx+28h]
0x1400075e7  mov     ebp, 21h ; '!'
0x1400075ec  mov     rdi, [rcx+20h]
0x1400075f0  dec     ebx
0x1400075f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400075f9  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007600  nop     dword ptr [rax+rax+00h]
0x140007605  mov     [rsp+68h+var_38], rdi
0x14000760a  lea     r8d, [rbp-1Fh]
0x14000760e  mov     rcx, rax
0x140007611  mov     dword ptr [rsp+68h+var_40], ebx
0x140007615  movzx   r9d, bp
0x140007619  mov     dl, 3
0x14000761b  call    WPP_RECORDER_SF_Di
0x140007620  jmp     loc_140007472
```
