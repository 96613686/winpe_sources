# ResponseIUCompletion

- ea: `0x140008430`
- end: `0x140008714`
- name: `ResponseIUCompletion`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14000a7bc`

## callees

- `0x140002964`
- `0x140005744`
- `0x140008348`
- `0x140008430`
- `0x140009098`
- `0x1400091b0`
- `0x1400098a0`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400084d5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000856a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400085f1`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000865b`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400086d4`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400084d5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000856a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400085f1`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000865b`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400086d4`

## pseudocode

```c
__int64 __fastcall ResponseIUCompletion(__int64 *a1, __int64 a2, int a3, __int64 a4)
{
  int v7; // ebp
  __int64 v8; // rax
  bool v9; // zf
  int v10; // eax
  int v11; // edx
  unsigned __int16 v12; // si
  int v13; // eax
  int v14; // edx
  int v15; // eax
  int v16; // edx
  __int64 v17; // rcx
  void *v18; // rdx
  __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // rbx
  int v22; // eax
  int v23; // edx
  int Default; // eax
  int v25; // edx

  v7 = *(_DWORD *)(a1[12] + 4);
  *((_DWORD *)a1 + 4) = 3;
  *((_BYTE *)a1 + 202) = 0;
  if ( a3 == -1073741536 || v7 == -1073676288 )
  {
    v9 = gTracingEnabled == 0;
    *(_BYTE *)(a1[4] + 3) = 2;
    if ( v9 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return QueueUpdateTaskCompletion(a1);
    v12 = 47;
LABEL_32:
    Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    LOBYTE(v25) = 4;
    WPP_RECORDER_SF_Di(Default, v25, 3, v12);
    return QueueUpdateTaskCompletion(a1);
  }
  if ( v7 || a3 < 0 )
  {
    v9 = gTracingEnabled == 0;
    *(_BYTE *)(a1[4] + 3) = 4;
    if ( !v9 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_DiD(v13, v14, 1, 48);
    }
    if ( (unsigned int)(v7 + 1073741807) <= 1 || v7 == -1073741820 )
    {
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v21 = a1[4];
        v22 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v23) = 3;
        WPP_RECORDER_SF_i(v22, v23, 2, 49, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v21);
      }
      v17 = *a1;
      v18 = &ResetPipeWorkItem;
      v19 = a4;
      v20 = 0;
    }
    else
    {
      if ( v7 != -1073713152 && a3 != -1073741667 && a3 != -1073741810 )
        return QueueUpdateTaskCompletion(a1);
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v15 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v16) = 3;
        WPP_RECORDER_SF_(v15, v16, 2, 50, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
      }
      v17 = *a1;
      v18 = &BulkResetDeviceWorkItem;
      v19 = 0;
      v20 = *(_QWORD *)(*a1 + 160);
    }
    UaspQueueWorkItem(v17, v18, v20, v19);
    return QueueUpdateTaskCompletion(a1);
  }
  v8 = a1[4];
  if ( (*(_BYTE *)(a2 + 7) & 0xF7) == 0 )
  {
    v9 = gTracingEnabled == 0;
    *(_BYTE *)(v8 + 3) = 1;
    if ( v9 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return QueueUpdateTaskCompletion(a1);
    v12 = 51;
    goto LABEL_32;
  }
  v9 = gTracingEnabled == 0;
  *(_BYTE *)(v8 + 3) = 4;
  if ( !v9 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_DiD(v10, v11, 3, 52);
  }
  return QueueUpdateTaskCompletion(a1);
}

```

## disassembly

```asm
0x140008430  push    rbx
0x140008432  push    rbp
0x140008433  push    rsi
0x140008434  push    rdi
0x140008435  push    r12
0x140008437  push    r13
0x140008439  push    r14
0x14000843b  push    r15
0x14000843d  sub     rsp, 48h
0x140008441  mov     rax, [rcx+60h]
0x140008445  mov     r14, rcx
0x140008448  mov     r13d, 3
0x14000844e  mov     r12, r9
0x140008451  mov     r15d, r8d
0x140008454  mov     ebp, [rax+4]
0x140008457  mov     [rcx+10h], r13d
0x14000845b  xor     ecx, ecx
0x14000845d  mov     [r14+0CAh], cl
0x140008464  cmp     r8d, 0C0000120h
0x14000846b  jz      loc_14000869D
0x140008471  cmp     ebp, 0C0010000h
0x140008477  jz      loc_14000869D
0x14000847d  test    ebp, ebp
0x14000847f  jnz     loc_140008532
0x140008485  test    r8d, r8d
0x140008488  js      loc_140008532
0x14000848e  test    byte ptr [rdx+7], 0F7h
0x140008492  mov     rax, [r14+20h]
0x140008496  jz      short loc_140008504
0x140008498  cmp     cs:gTracingEnabled, cl
0x14000849e  mov     byte ptr [rax+3], 4
0x1400084a2  jz      loc_1400086FA
0x1400084a8  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400084af  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400084b6  jz      loc_1400086FA
0x1400084bc  movzx   ebx, word ptr [r14+28h]
0x1400084c1  lea     ebp, [rcx+34h]
0x1400084c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400084cb  dec     ebx
0x1400084cd  movzx   edi, byte ptr [rdx+7]
0x1400084d1  mov     rsi, [r14+20h]
0x1400084d5  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400084dc  nop     dword ptr [rax+rax+00h]
0x1400084e1  mov     [rsp+88h+var_50], edi
0x1400084e5  movzx   r9d, bp
0x1400084e9  mov     rcx, rax
0x1400084ec  mov     [rsp+88h+var_58], rsi
0x1400084f1  mov     r8d, r13d
0x1400084f4  mov     dword ptr [rsp+88h+var_60], ebx
0x1400084f8  mov     dl, 4
0x1400084fa  call    WPP_RECORDER_SF_DiD
0x1400084ff  jmp     loc_1400086FA
0x140008504  cmp     cs:gTracingEnabled, cl
0x14000850a  mov     byte ptr [rax+3], 1
0x14000850e  jz      loc_1400086FA
0x140008514  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000851b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140008522  jz      loc_1400086FA
0x140008528  mov     esi, 33h ; '3'
0x14000852d  jmp     loc_1400086C2
0x140008532  cmp     cs:gTracingEnabled, cl
0x140008538  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000853f  mov     rax, [r14+20h]
0x140008543  mov     byte ptr [rax+3], 4
0x140008547  jz      short loc_14000859B
0x140008549  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140008550  jz      short loc_14000859B
0x140008552  movzx   ebx, word ptr [r14+28h]
0x140008557  mov     r13d, 30h ; '0'
0x14000855d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008564  dec     ebx
0x140008566  mov     rdi, [r14+20h]
0x14000856a  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140008571  nop     dword ptr [rax+rax+00h]
0x140008576  mov     [rsp+88h+var_50], ebp
0x14000857a  lea     r8d, [r13-2Fh]
0x14000857e  mov     rcx, rax
0x140008581  mov     [rsp+88h+var_58], rdi
0x140008586  movzx   r9d, r13w
0x14000858a  mov     dword ptr [rsp+88h+var_60], ebx
0x14000858e  mov     dl, 2
0x140008590  call    WPP_RECORDER_SF_DiD
0x140008595  xor     ecx, ecx
0x140008597  lea     r13d, [rcx+3]
0x14000859b  lea     eax, [rbp+3FFFFFEFh]
0x1400085a1  cmp     eax, 1
0x1400085a4  jbe     loc_14000863A
0x1400085aa  cmp     ebp, 0C0000004h
0x1400085b0  jz      loc_14000863A
0x1400085b6  cmp     ebp, 0C0007000h
0x1400085bc  jz      short loc_1400085D4
0x1400085be  cmp     r15d, 0C000009Dh
0x1400085c5  jz      short loc_1400085D4
0x1400085c7  cmp     r15d, 0C000000Eh
0x1400085ce  jnz     loc_1400086FA
0x1400085d4  cmp     cs:gTracingEnabled, cl
0x1400085da  jz      short loc_14000861C
0x1400085dc  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400085e3  jz      short loc_14000861C
0x1400085e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400085ec  mov     ebx, 32h ; '2'
0x1400085f1  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400085f8  nop     dword ptr [rax+rax+00h]
0x1400085fd  movzx   r9d, bx
0x140008601  lea     r8d, [rbx-30h]
0x140008605  mov     rcx, rax
0x140008608  mov     dl, r13b
0x14000860b  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140008612  mov     [rsp+88h+var_68], rax
0x140008617  call    WPP_RECORDER_SF_
0x14000861c  mov     rcx, [r14]
0x14000861f  lea     rdx, BulkResetDeviceWorkItem
0x140008626  xor     r9d, r9d
0x140008629  mov     r8, [rcx+0A0h]
0x140008630  call    UaspQueueWorkItem
0x140008635  jmp     loc_1400086FA
0x14000863a  cmp     cs:gTracingEnabled, cl
0x140008640  jz      short loc_14000868B
0x140008642  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140008649  jz      short loc_14000868B
0x14000864b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008652  mov     edi, 31h ; '1'
0x140008657  mov     rbx, [r14+20h]
0x14000865b  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140008662  nop     dword ptr [rax+rax+00h]
0x140008667  mov     [rsp+88h+var_60], rbx
0x14000866c  lea     r8d, [rdi-2Fh]
0x140008670  mov     rcx, rax
0x140008673  movzx   r9d, di
0x140008677  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x14000867e  mov     dl, r13b
0x140008681  mov     [rsp+88h+var_68], rax
0x140008686  call    WPP_RECORDER_SF_i
0x14000868b  mov     rcx, [r14]
0x14000868e  lea     rdx, ResetPipeWorkItem
0x140008695  mov     r9, r12
0x140008698  xor     r8d, r8d
0x14000869b  jmp     short loc_140008630
0x14000869d  cmp     cs:gTracingEnabled, cl
0x1400086a3  mov     rax, [r14+20h]
0x1400086a7  mov     byte ptr [rax+3], 2
0x1400086ab  jz      short loc_1400086FA
0x1400086ad  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400086b4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400086bb  jz      short loc_1400086FA
0x1400086bd  mov     esi, 2Fh ; '/'
0x1400086c2  movzx   ebx, word ptr [r14+28h]
0x1400086c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086ce  dec     ebx
0x1400086d0  mov     rdi, [r14+20h]
0x1400086d4  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400086db  nop     dword ptr [rax+rax+00h]
0x1400086e0  mov     [rsp+88h+var_58], rdi
0x1400086e5  movzx   r9d, si
0x1400086e9  mov     rcx, rax
0x1400086ec  mov     dword ptr [rsp+88h+var_60], ebx
0x1400086f0  mov     r8d, r13d
0x1400086f3  mov     dl, 4
0x1400086f5  call    WPP_RECORDER_SF_Di
0x1400086fa  mov     rcx, r14
0x1400086fd  call    QueueUpdateTaskCompletion
0x140008702  add     rsp, 48h
0x140008706  pop     r15
0x140008708  pop     r14
0x14000870a  pop     r13
0x14000870c  pop     r12
0x14000870e  pop     rdi
0x14000870f  pop     rsi
0x140008710  pop     rbp
0x140008711  pop     rbx
0x140008712  retn
```
