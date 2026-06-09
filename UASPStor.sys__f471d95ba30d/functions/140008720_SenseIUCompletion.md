# SenseIUCompletion

- ea: `0x140008720`
- end: `0x140008dec`
- name: `SenseIUCompletion`
- size: `1740`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000a7bc`

## callees

- `0x140002964`
- `0x140004adc`
- `0x140005744`
- `0x1400081dc`
- `0x140008720`
- `0x140009098`
- `0x1400091b0`
- `0x140009760`
- `0x1400098a0`
- `0x14000998c`
- `0x140009a88`
- `0x14000d900`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x140008d11`
- `ntoskrnl!IoCancelIrp` at `0x140008d71`
- `ntoskrnl!IoCancelIrp` at `0x140008d11`
- `ntoskrnl!IoCancelIrp` at `0x140008d71`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400087ed`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008837`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400088af`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000893e`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400089c0`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008acb`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008b23`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008bb5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008c17`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008c8b`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008ce2`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008d42`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008d9d`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400087ed`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008837`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400088af`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000893e`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400089c0`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008acb`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008b23`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008bb5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008c17`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008c8b`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008ce2`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008d42`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008d9d`

## pseudocode

```c
__int64 __fastcall SenseIUCompletion(__int64 *a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v5; // rcx
  char v8; // r12
  int v9; // esi
  int v10; // eax
  int v11; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  char v15; // bl
  __int64 v16; // rdi
  int v17; // eax
  int v18; // edx
  char v19; // di
  int v20; // eax
  int v21; // edx
  int v22; // ecx
  int v23; // r13d
  int v24; // r10d
  unsigned __int8 v25; // al
  unsigned __int8 v26; // r8
  __int64 v27; // rbx
  int v28; // eax
  int v29; // edx
  __int64 v30; // rax
  int v31; // eax
  int v32; // edx
  __int64 v33; // r9
  __int64 v34; // rcx
  int v35; // eax
  const void *v36; // rdx
  __int64 v37; // rcx
  unsigned __int8 v38; // bl
  unsigned __int8 v39; // al
  void *v40; // rcx
  int v41; // eax
  int v42; // edx
  int v43; // r8d
  int v44; // r9d
  int v45; // eax
  int v46; // edx
  int v47; // eax
  int v48; // edx
  __int64 v49; // rcx
  void *v50; // rdx
  __int64 v51; // r9
  __int64 v52; // r8
  __int64 v53; // rbx
  int v54; // eax
  int v55; // edx
  int Default; // eax
  int v57; // edx
  int v58; // eax
  int v59; // edx
  int v60; // eax
  int v61; // edx
  int v62; // eax
  int v63; // edx

  v5 = a1[12];
  v8 = 4;
  v9 = *(_DWORD *)(v5 + 4);
  *((_DWORD *)a1 + 4) = 3;
  *((_BYTE *)a1 + 202) = 0;
  if ( a3 == -1073741536 || v9 == -1073676288 )
  {
    v8 = 2;
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v57) = 3;
      WPP_RECORDER_SF_Di(Default, v57, 2, 20);
    }
  }
  else
  {
    if ( v9 || a3 < 0 )
    {
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v45 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v46) = 3;
        WPP_RECORDER_SF_DiD(v45, v46, 2, 21);
      }
      if ( (unsigned int)(v9 + 1073741807) <= 1 || v9 == -1073741820 )
      {
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v53 = a1[4];
          v54 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v55) = 3;
          WPP_RECORDER_SF_i(v54, v55, 2, 22, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v53);
        }
        v49 = *a1;
        v50 = &ResetPipeWorkItem;
        v51 = a4;
        v52 = 0;
      }
      else
      {
        if ( v9 != -1073713152 && a3 != -1073741667 && a3 != -1073741810 )
          goto LABEL_30;
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v47 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v48) = 3;
          WPP_RECORDER_SF_(v47, v48, 2, 23, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
        }
        v49 = *a1;
        v50 = &BulkResetDeviceWorkItem;
        v51 = 0;
        v52 = *(_QWORD *)(*a1 + 160);
      }
      UaspQueueWorkItem(v49, v50, v52, v51);
      goto LABEL_30;
    }
    if ( *(_BYTE *)a2 == 4 )
    {
      v10 = *(unsigned __int8 *)(a2 + 7);
      if ( (v10 & 0xF7) != 0 )
      {
        if ( v10 == 2 || v10 == 4 || v10 == 5 )
        {
          v8 = 6;
        }
        else if ( v10 == 9 )
        {
          v8 = 32;
        }
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v11 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          WPP_RECORDER_SF_iDD(v11, v12, v13, v14);
        }
      }
      else
      {
        v8 = 1;
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v15 = *(_BYTE *)(a2 + 7);
          v16 = a1[4];
          v17 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v18) = 3;
          WPP_RECORDER_SF_iD(v17, v18, 2, 24, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v16, v15);
        }
      }
      goto LABEL_30;
    }
    v19 = *(_BYTE *)(a2 + 4);
    if ( !v19 && !*(_BYTE *)(a2 + 6) )
    {
      v8 = 1;
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v20 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v21) = 4;
        WPP_RECORDER_SF_Di(v20, v21, 3, 26);
      }
      goto LABEL_30;
    }
    v22 = *(_DWORD *)(v5 + 36);
    v23 = (unsigned __int8)__ROR2__(*(_WORD *)(a2 + 6), 8);
    v24 = v22 - 8;
    v25 = __ROR2__(*(_WORD *)(a2 + 14), 8);
    if ( v23 == v22 - 8 )
    {
      v26 = v23;
    }
    else
    {
      v26 = v25;
      if ( v25 != v22 - 16 )
      {
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v27 = a1[4];
          v28 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v29) = 2;
          WPP_RECORDER_SF_i(v28, v29, 1, 28, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v27);
        }
        goto LABEL_30;
      }
      v19 = *(_BYTE *)(a2 + 6);
    }
    v33 = *a1;
    v34 = 8;
    if ( v23 != v24 )
      v34 = 16;
    if ( !*(_DWORD *)(v33 + 1380) )
    {
      v35 = 2;
      if ( v23 != v24 )
        v35 = 4;
      *(_DWORD *)(v33 + 1380) = v35;
    }
    *(_BYTE *)(a1[4] + 4) = v19;
    if ( v19 == 2 )
    {
      if ( v26 > 2u )
      {
        v36 = (const void *)(v34 + a2);
        if ( v36 )
        {
          v37 = a1[4];
          v8 = -124;
          v38 = v26;
          v39 = *(_BYTE *)(v37 + 11);
          v40 = *(void **)(v37 + 32);
          if ( v39 < v26 )
            v38 = v39;
          memmove(v40, v36, v38);
          *(_BYTE *)(a1[4] + 11) = v38;
        }
      }
    }
    else
    {
      v8 = 5 - (((v19 - 8) & 0xDF) != 0);
    }
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v41 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      WPP_RECORDER_SF_diDDD(v41, v42, v43, v44);
    }
  }
LABEL_30:
  v30 = a1[4];
  if ( *(_BYTE *)(v30 + 3) != 4 )
    *(_BYTE *)(v30 + 3) = v8;
  if ( *(_BYTE *)(a1[4] + 3) != 1 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v31 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v32) = 4;
      WPP_RECORDER_SF_Di(v31, v32, 3, 29);
    }
    if ( *((_DWORD *)a1 + 3) == 2 )
    {
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v58 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v59) = 4;
        WPP_RECORDER_SF_(v58, v59, 3, 30, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
      }
      IoCancelIrp((PIRP)a1[15]);
    }
    if ( *((_DWORD *)a1 + 2) == 2 )
    {
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v60 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v61) = 4;
        WPP_RECORDER_SF_(v60, v61, 3, 31, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
      }
      IoCancelIrp((PIRP)a1[14]);
    }
    if ( *((_DWORD *)a1 + 5) == 2 )
    {
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v62 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v63) = 4;
        WPP_RECORDER_SF_(v62, v63, 3, 32, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
      }
      CancelReadyIrp(a1);
    }
  }
  return QueueUpdateCompletion(a1);
}

```

## disassembly

```asm
0x140008720  push    rbx
0x140008722  push    rbp
0x140008723  push    rsi
0x140008724  push    rdi
0x140008725  push    r12
0x140008727  push    r13
0x140008729  push    r14
0x14000872b  push    r15
0x14000872d  sub     rsp, 58h
0x140008731  xor     r11d, r11d
0x140008734  lea     rbx, WPP_RECORDER_INITIALIZED
0x14000873b  lea     rdi, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140008742  mov     r15, rcx
0x140008745  mov     rcx, [rcx+60h]
0x140008749  mov     r14, r9
0x14000874c  mov     ebp, r8d
0x14000874f  lea     r13d, [r11+2]
0x140008753  lea     r12d, [r11+4]
0x140008757  mov     esi, [rcx+4]
0x14000875a  mov     dword ptr [r15+10h], 3
0x140008762  mov     [r15+0CAh], r11b
0x140008769  cmp     r8d, 0C0000120h
0x140008770  jz      loc_140008C57
0x140008776  cmp     esi, 0C0010000h
0x14000877c  jz      loc_140008C57
0x140008782  test    esi, esi
0x140008784  jnz     loc_140008AF9
0x14000878a  test    r8d, r8d
0x14000878d  js      loc_140008AF9
0x140008793  cmp     [rdx], r12b
0x140008796  jnz     loc_140008874
0x14000879c  movzx   eax, byte ptr [rdx+7]
0x1400087a0  test    al, 0F7h
0x1400087a2  jz      short loc_140008810
0x1400087a4  mov     ecx, eax
0x1400087a6  mov     esi, eax
0x1400087a8  sub     ecx, r13d
0x1400087ab  jz      short loc_1400087C1
0x1400087ad  sub     ecx, r13d
0x1400087b0  jz      short loc_1400087C1
0x1400087b2  sub     ecx, 1
0x1400087b5  jz      short loc_1400087C1
0x1400087b7  cmp     ecx, r12d
0x1400087ba  jnz     short loc_1400087C4
0x1400087bc  mov     r12b, 20h ; ' '
0x1400087bf  jmp     short loc_1400087C4
0x1400087c1  mov     r12b, 6
0x1400087c4  cmp     cs:gTracingEnabled, r11b
0x1400087cb  jz      loc_140008869
0x1400087d1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400087d8  jz      loc_140008869
0x1400087de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087e5  mov     rdi, [r15+20h]
0x1400087e9  movzx   ebx, r12b
0x1400087ed  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400087f4  nop     dword ptr [rax+rax+00h]
0x1400087f9  mov     [rsp+98h+var_60], ebx
0x1400087fd  mov     rcx, rax
0x140008800  mov     dword ptr [rsp+98h+var_68], esi
0x140008804  mov     [rsp+98h+var_70], rdi
0x140008809  call    WPP_RECORDER_SF_iDD
0x14000880e  jmp     short loc_140008869
0x140008810  cmp     cs:gTracingEnabled, r11b
0x140008817  mov     r12b, 1
0x14000881a  jz      short loc_140008869
0x14000881c  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140008823  jz      short loc_140008869
0x140008825  mov     rcx, cs:WPP_GLOBAL_Control
0x14000882c  mov     ebx, eax
0x14000882e  mov     rdi, [r15+20h]
0x140008832  mov     esi, 18h
0x140008837  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000883e  nop     dword ptr [rax+rax+00h]
0x140008843  mov     dword ptr [rsp+98h+var_68], ebx
0x140008847  movzx   r9d, si
0x14000884b  mov     rcx, rax
0x14000884e  mov     [rsp+98h+var_70], rdi
0x140008853  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x14000885a  mov     r8d, r13d
0x14000885d  mov     dl, 3
0x14000885f  mov     [rsp+98h+var_78], rax
0x140008864  call    WPP_RECORDER_SF_iD
0x140008869  mov     r13d, 4
0x14000886f  jmp     loc_140008970
0x140008874  mov     dil, [rdx+4]
0x140008878  test    dil, dil
0x14000887b  jnz     short loc_1400088E0
0x14000887d  cmp     [rdx+6], r11b
0x140008881  jnz     short loc_1400088E0
0x140008883  cmp     cs:gTracingEnabled, r11b
0x14000888a  mov     r12b, 1
0x14000888d  jz      short loc_140008869
0x14000888f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140008896  jz      short loc_140008869
0x140008898  movzx   ebx, word ptr [r15+28h]
0x14000889d  mov     esi, 1Ah
0x1400088a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088a9  dec     ebx
0x1400088ab  mov     rdi, [r15+20h]
0x1400088af  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400088b6  nop     dword ptr [rax+rax+00h]
0x1400088bb  lea     r13d, [rsi-16h]
0x1400088bf  mov     [rsp+98h+var_68], rdi
0x1400088c4  mov     rcx, rax
0x1400088c7  mov     dword ptr [rsp+98h+var_70], ebx
0x1400088cb  mov     dl, r13b
0x1400088ce  lea     r8d, [rsi-17h]
0x1400088d2  movzx   r9d, si
0x1400088d6  call    WPP_RECORDER_SF_Di
0x1400088db  jmp     loc_140008970
0x1400088e0  movzx   eax, word ptr [rdx+6]
0x1400088e4  mov     ecx, [rcx+24h]
0x1400088e7  ror     ax, 8
0x1400088eb  movzx   r13d, al
0x1400088ef  movzx   eax, word ptr [rdx+0Eh]
0x1400088f3  lea     r10d, [rcx-8]
0x1400088f7  ror     ax, 8
0x1400088fb  mov     [rsp+98h+arg_10], r10d
0x140008903  cmp     r13d, r10d
0x140008906  jz      loc_1400089F3
0x14000890c  movzx   r8d, al
0x140008910  lea     eax, [rcx-10h]
0x140008913  cmp     r8d, eax
0x140008916  jz      loc_1400089ED
0x14000891c  cmp     cs:gTracingEnabled, r11b
0x140008923  jz      short loc_14000896D
0x140008925  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000892c  jz      short loc_14000896D
0x14000892e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008935  mov     edi, 1Ch
0x14000893a  mov     rbx, [r15+20h]
0x14000893e  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140008945  nop     dword ptr [rax+rax+00h]
0x14000894a  mov     [rsp+98h+var_70], rbx
0x14000894f  lea     r8d, [rdi-1Bh]
0x140008953  mov     rcx, rax
0x140008956  movzx   r9d, di
0x14000895a  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140008961  mov     dl, 2
0x140008963  mov     [rsp+98h+var_78], rax
0x140008968  call    WPP_RECORDER_SF_i
0x14000896d  mov     r13d, r12d
0x140008970  mov     rax, [r15+20h]
0x140008974  cmp     [rax+3], r13b
0x140008978  jz      short loc_14000897E
0x14000897a  mov     [rax+3], r12b
0x14000897e  mov     rdi, [r15+20h]
0x140008982  cmp     byte ptr [rdi+3], 1
0x140008986  jz      loc_140008DD2
0x14000898c  xor     ebp, ebp
0x14000898e  cmp     cs:gTracingEnabled, bpl
0x140008995  jz      loc_140008CB6
0x14000899b  lea     r14, WPP_RECORDER_INITIALIZED
0x1400089a2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400089a9  jz      loc_140008CBD
0x1400089af  movzx   ebx, word ptr [r15+28h]
0x1400089b4  lea     esi, [rbp+1Dh]
0x1400089b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400089be  dec     ebx
0x1400089c0  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400089c7  nop     dword ptr [rax+rax+00h]
0x1400089cc  mov     [rsp+98h+var_68], rdi
0x1400089d1  lea     r8d, [rbp+3]
0x1400089d5  mov     rcx, rax
0x1400089d8  mov     dword ptr [rsp+98h+var_70], ebx
0x1400089dc  movzx   r9d, si
0x1400089e0  mov     dl, r13b
0x1400089e3  call    WPP_RECORDER_SF_Di
0x1400089e8  jmp     loc_140008CBD
0x1400089ed  mov     dil, [rdx+6]
0x1400089f1  jmp     short loc_1400089F6
0x1400089f3  mov     r8b, r13b
0x1400089f6  mov     r9, [r15]
0x1400089f9  mov     ecx, 8
0x1400089fe  cmp     r13d, r10d
0x140008a01  lea     eax, [rcx+8]
0x140008a04  cmovnz  ecx, eax
0x140008a07  cmp     [r9+564h], r11d
0x140008a0e  jnz     short loc_140008A23
0x140008a10  cmp     r13d, r10d
0x140008a13  mov     eax, 2
0x140008a18  cmovnz  eax, r12d
0x140008a1c  mov     [r9+564h], eax
0x140008a23  mov     rax, [r15+20h]
0x140008a27  mov     [rax+4], dil
0x140008a2b  cmp     dil, 2
0x140008a2f  jz      short loc_140008A41
0x140008a31  lea     eax, [rdi-8]
0x140008a34  and     al, 0DFh
0x140008a36  neg     al
0x140008a38  sbb     r12b, r12b
0x140008a3b  add     r12b, 5
0x140008a3f  jmp     short loc_140008A87
0x140008a41  cmp     r8b, 2
0x140008a45  jbe     short loc_140008A87
0x140008a47  add     rdx, rcx; Src
0x140008a4a  jz      short loc_140008A87
0x140008a4c  mov     rcx, [r15+20h]
0x140008a50  mov     r12b, 84h
0x140008a53  movzx   ebx, r8b
0x140008a57  movzx   eax, byte ptr [rcx+0Bh]
0x140008a5b  mov     rcx, [rcx+20h]; void *
0x140008a5f  cmp     al, r8b
0x140008a62  cmovb   ebx, eax
0x140008a65  movzx   r8d, bl; Size
0x140008a69  call    memmove
0x140008a6e  mov     rax, [r15+20h]
0x140008a72  xor     r11d, r11d
0x140008a75  mov     r10d, [rsp+98h+arg_10]
0x140008a7d  mov     [rax+0Bh], bl
0x140008a80  lea     rbx, WPP_RECORDER_INITIALIZED
0x140008a87  cmp     cs:gTracingEnabled, r11b
0x140008a8e  jz      loc_140008869
0x140008a94  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140008a9b  jz      loc_140008869
0x140008aa1  movzx   ebp, word ptr [r15+28h]
0x140008aa6  mov     esi, 2
0x140008aab  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ab2  dec     ebp
0x140008ab4  mov     r14, [r15+20h]
0x140008ab8  cmp     r13d, r10d
0x140008abb  movzx   ebx, r12b
0x140008abf  lea     r13d, [rsi+2]
0x140008ac3  movzx   edi, dil
0x140008ac7  cmovnz  esi, r13d
0x140008acb  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140008ad2  nop     dword ptr [rax+rax+00h]
0x140008ad7  mov     [rsp+98h+var_50], ebx
0x140008adb  mov     rcx, rax
0x140008ade  mov     [rsp+98h+var_58], edi
0x140008ae2  mov     [rsp+98h+var_60], ebp
0x140008ae6  mov     [rsp+98h+var_68], r14
0x140008aeb  mov     dword ptr [rsp+98h+var_70], esi
0x140008aef  call    WPP_RECORDER_SF_diDDD
0x140008af4  jmp     loc_140008970
0x140008af9  cmp     cs:gTracingEnabled, r11b
0x140008b00  jz      short loc_140008B64
0x140008b02  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140008b09  jz      short loc_140008B64
0x140008b0b  movzx   ebx, word ptr [r15+28h]
0x140008b10  mov     r13d, 15h
0x140008b16  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b1d  dec     ebx
0x140008b1f  mov     rdi, [r15+20h]
0x140008b23  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140008b2a  nop     dword ptr [rax+rax+00h]
0x140008b2f  movzx   r9d, r13w
0x140008b33  mov     [rsp+98h+var_60], esi
0x140008b37  mov     r13d, 2
0x140008b3d  mov     [rsp+98h+var_68], rdi
0x140008b42  mov     r8d, r13d
0x140008b45  mov     dword ptr [rsp+98h+var_70], ebx
0x140008b49  mov     rcx, rax
0x140008b4c  mov     dl, 3
0x140008b4e  call    WPP_RECORDER_SF_DiD
0x140008b53  xor     r11d, r11d
0x140008b56  lea     rbx, WPP_RECORDER_INITIALIZED
0x140008b5d  lea     rdi, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140008b64  lea     eax, [rsi+3FFFFFEFh]
0x140008b6a  cmp     eax, 1
0x140008b6d  jbe     loc_140008BF5
0x140008b73  cmp     esi, 0C0000004h
0x140008b79  jz      short loc_140008BF5
0x140008b7b  cmp     esi, 0C0007000h
0x140008b81  jz      short loc_140008B97
0x140008b83  cmp     ebp, 0C000009Dh
0x140008b89  jz      short loc_140008B97
0x140008b8b  cmp     ebp, 0C000000Eh
0x140008b91  jnz     loc_14000896D
0x140008b97  cmp     cs:gTracingEnabled, r11b
0x140008b9e  jz      short loc_140008BD7
0x140008ba0  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140008ba7  jz      short loc_140008BD7
0x140008ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x140008bb0  mov     ebx, 17h
0x140008bb5  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140008bbc  nop     dword ptr [rax+rax+00h]
0x140008bc1  movzx   r9d, bx
0x140008bc5  mov     [rsp+98h+var_78], rdi
0x140008bca  mov     rcx, rax
0x140008bcd  mov     r8d, r13d
0x140008bd0  mov     dl, 3
0x140008bd2  call    WPP_RECORDER_SF_
0x140008bd7  mov     rcx, [r15]
0x140008bda  lea     rdx, BulkResetDeviceWorkItem
0x140008be1  xor     r9d, r9d
0x140008be4  mov     r8, [rcx+0A0h]
0x140008beb  call    UaspQueueWorkItem
0x140008bf0  jmp     loc_14000896D
0x140008bf5  cmp     cs:gTracingEnabled, r11b
0x140008bfc  jz      short loc_140008C45
0x140008bfe  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140008c05  jz      short loc_140008C45
0x140008c07  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c0e  mov     edi, 16h
0x140008c13  mov     rbx, [r15+20h]
0x140008c17  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140008c1e  nop     dword ptr [rax+rax+00h]
0x140008c23  mov     [rsp+98h+var_70], rbx
0x140008c28  movzx   r9d, di
  ... truncated ...
```
