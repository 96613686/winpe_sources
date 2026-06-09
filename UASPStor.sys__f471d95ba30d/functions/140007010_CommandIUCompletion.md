# CommandIUCompletion

- ea: `0x140007010`
- end: `0x1400072ac`
- name: `CommandIUCompletion`
- size: `668`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002964`
- `0x140005744`
- `0x140007010`
- `0x1400081dc`
- `0x140009098`
- `0x1400091b0`
- `0x1400098a0`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000709c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400070f5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007181`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400071e3`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000725d`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000709c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400070f5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007181`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400071e3`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000725d`

## pseudocode

```c
__int64 __fastcall CommandIUCompletion(__int64 *a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v4; // rdi
  int v7; // r15d
  int v8; // eax
  int v9; // edx
  char v10; // r13
  int v11; // eax
  int v12; // edx
  int v13; // eax
  int v14; // edx
  __int64 v15; // rcx
  void *v16; // rdx
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // rbx
  int v20; // eax
  int v21; // edx
  int Default; // eax
  int v23; // edx
  __int64 v24; // rax

  v4 = a4;
  v7 = *(_DWORD *)(a1[10] + 4);
  *((_DWORD *)a1 + 2) = 3;
  if ( a3 == -1073741536 || v7 == -1073676288 )
  {
    v10 = 2;
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v23) = 3;
      WPP_RECORDER_SF_Di(Default, v23, 2, 15);
    }
    goto LABEL_28;
  }
  if ( !v7 && a3 >= 0 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v9) = 3;
      WPP_RECORDER_SF_Di(v8, v9, 3, 19);
    }
    return QueueUpdateCompletion(a1);
  }
  v10 = 4;
  if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v11 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    LOBYTE(v12) = 3;
    WPP_RECORDER_SF_DiD(v11, v12, 1, 16);
    v4 = a4;
  }
  if ( (unsigned int)(v7 + 1073741807) <= 1 || v7 == -1073741820 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = a1[4];
      v20 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v21) = 3;
      WPP_RECORDER_SF_i(v20, v21, 2, 17, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v19);
    }
    v15 = *a1;
    v16 = &ResetPipeWorkItem;
    v17 = v4;
    v18 = 0;
    goto LABEL_24;
  }
  if ( v7 == -1073713152 || a3 == -1073741667 || a3 == -1073741810 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v14) = 3;
      WPP_RECORDER_SF_(v13, v14, 2, 18, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
    }
    v15 = *a1;
    v16 = &BulkResetDeviceWorkItem;
    v17 = 0;
    v18 = *(_QWORD *)(*a1 + 160);
LABEL_24:
    UaspQueueWorkItem(v15, v16, v18, v17);
  }
LABEL_28:
  v24 = a1[4];
  if ( *(_BYTE *)(v24 + 3) <= 1u )
    *(_BYTE *)(v24 + 3) = v10;
  return QueueUpdateCompletion(a1);
}

```

## disassembly

```asm
0x140007010  mov     [rsp+arg_18], r9
0x140007015  push    rbx
0x140007016  push    rbp
0x140007017  push    rsi
0x140007018  push    rdi
0x140007019  push    r12
0x14000701b  push    r13
0x14000701d  push    r14
0x14000701f  push    r15
0x140007021  sub     rsp, 48h
0x140007025  mov     rax, [rcx+50h]
0x140007029  mov     r13d, 3
0x14000702f  mov     rdi, r9
0x140007032  mov     r12d, r8d
0x140007035  mov     r14, rcx
0x140007038  mov     r15d, [rax+4]
0x14000703c  mov     [rcx+8], r13d
0x140007040  cmp     r8d, 0C0000120h
0x140007047  jz      loc_140007229
0x14000704d  cmp     r15d, 0C0010000h
0x140007054  jz      loc_140007229
0x14000705a  xor     esi, esi
0x14000705c  test    r15d, r15d
0x14000705f  jnz     short loc_1400070C8
0x140007061  test    r8d, r8d
0x140007064  js      short loc_1400070C8
0x140007066  cmp     cs:gTracingEnabled, sil
0x14000706d  jz      loc_140007292
0x140007073  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000707a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140007081  jz      loc_140007292
0x140007087  movzx   ebx, word ptr [rcx+28h]
0x14000708b  lea     esi, [r13+10h]
0x14000708f  mov     rdi, [rcx+20h]
0x140007093  dec     ebx
0x140007095  mov     rcx, cs:WPP_GLOBAL_Control
0x14000709c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400070a3  nop     dword ptr [rax+rax+00h]
0x1400070a8  mov     [rsp+88h+var_58], rdi
0x1400070ad  movzx   r9d, si
0x1400070b1  mov     rcx, rax
0x1400070b4  mov     dword ptr [rsp+88h+var_60], ebx
0x1400070b8  mov     r8d, r13d
0x1400070bb  mov     dl, r13b
0x1400070be  call    WPP_RECORDER_SF_Di
0x1400070c3  jmp     loc_140007292
0x1400070c8  cmp     cs:gTracingEnabled, sil
0x1400070cf  lea     rbp, WPP_RECORDER_INITIALIZED
0x1400070d6  mov     r13b, 4
0x1400070d9  jz      short loc_14000712B
0x1400070db  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400070e2  jz      short loc_14000712B
0x1400070e4  movzx   ebx, word ptr [rcx+28h]
0x1400070e8  mov     rdi, [rcx+20h]
0x1400070ec  dec     ebx
0x1400070ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400070f5  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400070fc  nop     dword ptr [rax+rax+00h]
0x140007101  mov     r9d, 10h
0x140007107  mov     [rsp+88h+var_50], r15d
0x14000710c  mov     rcx, rax
0x14000710f  mov     [rsp+88h+var_58], rdi
0x140007114  mov     dl, 3
0x140007116  mov     dword ptr [rsp+88h+var_60], ebx
0x14000711a  lea     r8d, [r9-0Fh]
0x14000711e  call    WPP_RECORDER_SF_DiD
0x140007123  mov     rdi, [rsp+88h+arg_18]
0x14000712b  lea     eax, [r15+3FFFFFEFh]
0x140007132  cmp     eax, 1
0x140007135  jbe     loc_1400071C1
0x14000713b  cmp     r15d, 0C0000004h
0x140007142  jz      short loc_1400071C1
0x140007144  cmp     r15d, 0C0007000h
0x14000714b  jz      short loc_140007163
0x14000714d  cmp     r12d, 0C000009Dh
0x140007154  jz      short loc_140007163
0x140007156  cmp     r12d, 0C000000Eh
0x14000715d  jnz     loc_140007284
0x140007163  cmp     cs:gTracingEnabled, sil
0x14000716a  jz      short loc_1400071AB
0x14000716c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140007173  jz      short loc_1400071AB
0x140007175  mov     rcx, cs:WPP_GLOBAL_Control
0x14000717c  mov     ebx, 12h
0x140007181  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007188  nop     dword ptr [rax+rax+00h]
0x14000718d  movzx   r9d, bx
0x140007191  lea     r8d, [rbx-10h]
0x140007195  mov     rcx, rax
0x140007198  mov     dl, 3
0x14000719a  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x1400071a1  mov     [rsp+88h+var_68], rax
0x1400071a6  call    WPP_RECORDER_SF_
0x1400071ab  mov     rcx, [r14]
0x1400071ae  lea     rdx, BulkResetDeviceWorkItem
0x1400071b5  xor     r9d, r9d
0x1400071b8  mov     r8, [rcx+0A0h]
0x1400071bf  jmp     short loc_140007222
0x1400071c1  cmp     cs:gTracingEnabled, sil
0x1400071c8  jz      short loc_140007212
0x1400071ca  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400071d1  jz      short loc_140007212
0x1400071d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400071da  mov     esi, 11h
0x1400071df  mov     rbx, [r14+20h]
0x1400071e3  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400071ea  nop     dword ptr [rax+rax+00h]
0x1400071ef  mov     [rsp+88h+var_60], rbx
0x1400071f4  lea     r8d, [rsi-0Fh]
0x1400071f8  mov     rcx, rax
0x1400071fb  movzx   r9d, si
0x1400071ff  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140007206  mov     dl, 3
0x140007208  mov     [rsp+88h+var_68], rax
0x14000720d  call    WPP_RECORDER_SF_i
0x140007212  mov     rcx, [r14]
0x140007215  lea     rdx, ResetPipeWorkItem
0x14000721c  mov     r9, rdi
0x14000721f  xor     r8d, r8d
0x140007222  call    UaspQueueWorkItem
0x140007227  jmp     short loc_140007284
0x140007229  xor     esi, esi
0x14000722b  mov     r13b, 2
0x14000722e  cmp     cs:gTracingEnabled, sil
0x140007235  jz      short loc_140007284
0x140007237  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000723e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140007245  jz      short loc_140007284
0x140007247  movzx   ebx, word ptr [rcx+28h]
0x14000724b  mov     esi, 0Fh
0x140007250  mov     rdi, [rcx+20h]
0x140007254  dec     ebx
0x140007256  mov     rcx, cs:WPP_GLOBAL_Control
0x14000725d  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007264  nop     dword ptr [rax+rax+00h]
0x140007269  mov     [rsp+88h+var_58], rdi
0x14000726e  lea     r8d, [rsi-0Dh]
0x140007272  mov     rcx, rax
0x140007275  mov     dword ptr [rsp+88h+var_60], ebx
0x140007279  movzx   r9d, si
0x14000727d  mov     dl, 3
0x14000727f  call    WPP_RECORDER_SF_Di
0x140007284  mov     rax, [r14+20h]
0x140007288  cmp     byte ptr [rax+3], 1
0x14000728c  ja      short loc_140007292
0x14000728e  mov     [rax+3], r13b
0x140007292  mov     rcx, r14
0x140007295  call    QueueUpdateCompletion
0x14000729a  add     rsp, 48h
0x14000729e  pop     r15
0x1400072a0  pop     r14
0x1400072a2  pop     r13
0x1400072a4  pop     r12
0x1400072a6  pop     rdi
0x1400072a7  pop     rsi
0x1400072a8  pop     rbp
0x1400072a9  pop     rbx
0x1400072aa  retn
```
