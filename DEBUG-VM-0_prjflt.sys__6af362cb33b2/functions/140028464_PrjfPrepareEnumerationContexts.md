# PrjfPrepareEnumerationContexts

- ea: `0x140028464`
- end: `0x14002875a`
- name: `PrjfPrepareEnumerationContexts`
- size: `758`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140024b24`

## callees

- `0x14000b1a0`
- `0x14000b1d0`
- `0x14000be80`
- `0x14000d128`
- `0x1400249dc`
- `0x140028464`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140028544`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140028574`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400285a4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140028544`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140028574`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400285a4`
- `ntoskrnl!ExAllocatePool2` at `0x1400285ef`
- `ntoskrnl!ExAllocatePool2` at `0x1400285ef`

## pseudocode

```c
__int64 __fastcall PrjfPrepareEnumerationContexts(
        _QWORD *a1,
        int a2,
        int a3,
        unsigned int a4,
        int a5,
        char a6,
        int a7,
        __int64 a8)
{
  int v8; // ebp
  __int64 v10; // r15
  int v13; // r9d
  _QWORD *v14; // rbx
  char v15; // r14
  PVOID Pool2; // rdi
  int v17; // edx
  int v18; // r8d
  size_t v19; // r8
  bool v20; // zf

  v8 = 0;
  v10 = a4;
  if ( a8 && (a6 & 4) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1);
  if ( (_QWORD *)*a1 != a1
    || (v8 = PrjfAddSubContext((_DWORD)a1, a2, a3, a4, 0), v8 >= 0)
    && (!a8 || (v8 = PrjfAddSubContext((_DWORD)a1, a2, a3, v13, a8), v8 >= 0)) )
  {
    v14 = (_QWORD *)*a1;
    if ( (_QWORD *)*a1 != a1 )
    {
      v15 = a6 & 1;
      while ( 1 )
      {
        if ( *((_DWORD *)v14 + 13) && !v14[9] )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(a1);
        if ( !v15 && *((_DWORD *)v14 + 13) )
          goto LABEL_37;
        Pool2 = (PVOID)v14[8];
        if ( !Pool2 )
          break;
LABEL_33:
        memset(Pool2, 0, *((unsigned int *)v14 + 14));
        v20 = v14[9] == 0;
        *((_DWORD *)v14 + 11) = a5;
        v14[6] = 0;
        *((_DWORD *)v14 + 5) = 0;
        *((_BYTE *)v14 + 40) = a6;
        if ( v20 && !v15 && a7 )
          *((_BYTE *)v14 + 40) = a6 | 4;
LABEL_37:
        v14 = (_QWORD *)*v14;
        if ( v14 == a1 )
          return (unsigned int)v8;
      }
      if ( (_DWORD)v10 )
      {
        if ( (unsigned int)v10 > 0x27C )
        {
          if ( (unsigned int)v10 > 0x1014 )
          {
            if ( (unsigned int)v10 > 0x10014 )
            {
              MicrosoftTelemetryAssertTriggeredMsgKM("Unexpectedly large enumeration result buffer size");
              Pool2 = (PVOID)ExAllocatePool2(256, v10, 1852131920);
              if ( (BYTE2(xmmword_14001A3D0) & 4) != 0
                || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v17) = BYTE2(xmmword_14001A3D0) & 4;
                LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_sDL(
                  530,
                  v17,
                  v18,
                  *((_QWORD *)WPP_GLOBAL_Control + 8),
                  2,
                  18,
                  83,
                  (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
                  (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
                  122,
                  v10);
              }
            }
            else
            {
              Pool2 = ExAllocateFromPagedLookasideList(&stru_14001AA40);
              if ( Pool2 )
              {
                v19 = 65556;
                goto LABEL_27;
              }
            }
          }
          else
          {
            Pool2 = ExAllocateFromPagedLookasideList(&stru_14001A9C0);
            if ( Pool2 )
            {
              v19 = 4116;
              goto LABEL_27;
            }
          }
LABEL_31:
          v14[8] = Pool2;
          if ( !Pool2 )
          {
            v8 = -1073741670;
            if ( (BYTE2(xmmword_14001A3D0) & 4) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v17) = BYTE2(xmmword_14001A3D0) & 4;
              LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDL(
                530,
                v17,
                v18,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                18,
                22,
                (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
                19,
                154);
            }
            return (unsigned int)v8;
          }
          goto LABEL_32;
        }
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgsKM(a1);
      }
      Pool2 = ExAllocateFromPagedLookasideList(&stru_14001A940);
      if ( Pool2 )
      {
        v19 = 636;
LABEL_27:
        memset(Pool2, 0, v19);
        v14[8] = Pool2;
LABEL_32:
        *((_DWORD *)v14 + 14) = v10;
        goto LABEL_33;
      }
      goto LABEL_31;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140028464  push    rbx
0x140028466  push    rbp
0x140028467  push    rsi
0x140028468  push    rdi
0x140028469  push    r12
0x14002846b  push    r13
0x14002846d  push    r14
0x14002846f  push    r15
0x140028471  sub     rsp, 68h
0x140028475  mov     rbx, [rsp+0A8h+arg_38]
0x14002847d  xor     ebp, ebp
0x14002847f  mov     r12b, [rsp+0A8h+arg_28]
0x140028487  mov     rdi, r8
0x14002848a  mov     r15d, r9d
0x14002848d  mov     r14, rdx
0x140028490  mov     rsi, rcx
0x140028493  test    rbx, rbx
0x140028496  jz      short loc_1400284A3
0x140028498  test    r12b, 4
0x14002849c  jz      short loc_1400284A3
0x14002849e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400284a3  cmp     [rsi], rsi
0x1400284a6  jnz     short loc_1400284E7
0x1400284a8  mov     r8, rdi
0x1400284ab  mov     [rsp+0A8h+var_88], rbp
0x1400284b0  mov     rdx, r14
0x1400284b3  mov     rcx, rsi
0x1400284b6  call    PrjfAddSubContext
0x1400284bb  mov     ebp, eax
0x1400284bd  test    eax, eax
0x1400284bf  js      loc_140028746
0x1400284c5  test    rbx, rbx
0x1400284c8  jz      short loc_1400284E7
0x1400284ca  mov     r8, rdi
0x1400284cd  mov     [rsp+0A8h+var_88], rbx
0x1400284d2  mov     rdx, r14
0x1400284d5  mov     rcx, rsi
0x1400284d8  call    PrjfAddSubContext
0x1400284dd  mov     ebp, eax
0x1400284df  test    eax, eax
0x1400284e1  js      loc_140028746
0x1400284e7  mov     rbx, [rsi]
0x1400284ea  cmp     rbx, rsi
0x1400284ed  jz      loc_140028746
0x1400284f3  mov     r14b, r12b
0x1400284f6  and     r14b, 1
0x1400284fa  cmp     dword ptr [rbx+34h], 0
0x1400284fe  jz      short loc_14002850C
0x140028500  cmp     qword ptr [rbx+48h], 0
0x140028505  jnz     short loc_14002850C
0x140028507  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002850c  test    r14b, r14b
0x14002850f  jnz     short loc_14002851B
0x140028511  cmp     dword ptr [rbx+34h], 0
0x140028515  jnz     loc_1400286C4
0x14002851b  mov     rdi, [rbx+40h]
0x14002851f  test    rdi, rdi
0x140028522  jnz     loc_14002867B
0x140028528  test    r15d, r15d
0x14002852b  jnz     short loc_140028534
0x14002852d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140028532  jmp     short loc_14002853D
0x140028534  cmp     r15d, 27Ch
0x14002853b  ja      short loc_140028564
0x14002853d  lea     rcx, stru_14001A940; Lookaside
0x140028544  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14002854b  nop     dword ptr [rax+rax+00h]
0x140028550  mov     rdi, rax
0x140028553  test    rax, rax
0x140028556  jz      loc_14002866E
0x14002855c  mov     r8d, 27Ch
0x140028562  jmp     short loc_1400285C2
0x140028564  cmp     r15d, 1014h
0x14002856b  ja      short loc_140028594
0x14002856d  lea     rcx, stru_14001A9C0; Lookaside
0x140028574  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14002857b  nop     dword ptr [rax+rax+00h]
0x140028580  mov     rdi, rax
0x140028583  test    rax, rax
0x140028586  jz      loc_14002866E
0x14002858c  mov     r8d, 1014h
0x140028592  jmp     short loc_1400285C2
0x140028594  cmp     r15d, 10014h
0x14002859b  ja      short loc_1400285D5
0x14002859d  lea     rcx, stru_14001AA40; Lookaside
0x1400285a4  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400285ab  nop     dword ptr [rax+rax+00h]
0x1400285b0  mov     rdi, rax
0x1400285b3  test    rax, rax
0x1400285b6  jz      loc_14002866E
0x1400285bc  mov     r8d, 10014h; Size
0x1400285c2  xor     edx, edx; Val
0x1400285c4  mov     rcx, rdi; void *
0x1400285c7  call    memset
0x1400285cc  mov     [rbx+40h], rdi
0x1400285d0  jmp     loc_140028677
0x1400285d5  lea     rcx, aUnexpectedlyLa; "Unexpectedly large enumeration result b"...
0x1400285dc  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400285e1  mov     rdx, r15
0x1400285e4  mov     ecx, 100h
0x1400285e9  mov     r8d, 6E654A50h
0x1400285ef  call    cs:__imp_ExAllocatePool2
0x1400285f6  nop     dword ptr [rax+rax+00h]
0x1400285fb  mov     rdi, rax
0x1400285fe  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140028604  lea     rax, WPP_RECORDER_INITIALIZED
0x14002860b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140028612  setnz   r8b
0x140028616  and     dl, 4
0x140028619  jnz     short loc_140028620
0x14002861b  test    r8b, r8b
0x14002861e  jz      short loc_14002866E
0x140028620  mov     r9, cs:WPP_GLOBAL_Control
0x140028627  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002862e  mov     [rsp+0A8h+var_58], r15d
0x140028633  mov     ecx, 212h
0x140028638  mov     [rsp+0A8h+var_60], 0F7Ah
0x140028640  mov     [rsp+0A8h+var_68], rax
0x140028645  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14002864c  mov     r9, [r9+40h]
0x140028650  mov     [rsp+0A8h+var_70], rax
0x140028655  mov     [rsp+0A8h+var_78], 53h ; 'S'
0x14002865c  mov     [rsp+0A8h+var_80], 12h
0x140028664  mov     byte ptr [rsp+0A8h+var_88], 2
0x140028669  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002866e  mov     [rbx+40h], rdi
0x140028672  test    rdi, rdi
0x140028675  jz      short loc_1400286D2
0x140028677  mov     [rbx+38h], r15d
0x14002867b  mov     r8d, [rbx+38h]; Size
0x14002867f  xor     edx, edx; Val
0x140028681  mov     rcx, rdi; void *
0x140028684  call    memset
0x140028689  cmp     qword ptr [rbx+48h], 0
0x14002868e  mov     eax, [rsp+0A8h+arg_20]
0x140028695  mov     [rbx+2Ch], eax
0x140028698  mov     qword ptr [rbx+30h], 0
0x1400286a0  mov     dword ptr [rbx+14h], 0
0x1400286a7  mov     [rbx+28h], r12b
0x1400286ab  jnz     short loc_1400286C4
0x1400286ad  test    r14b, r14b
0x1400286b0  jnz     short loc_1400286C4
0x1400286b2  cmp     [rsp+0A8h+arg_30], 0
0x1400286ba  jz      short loc_1400286C4
0x1400286bc  mov     al, r12b
0x1400286bf  or      al, 4
0x1400286c1  mov     [rbx+28h], al
0x1400286c4  mov     rbx, [rbx]
0x1400286c7  cmp     rbx, rsi
0x1400286ca  jnz     loc_1400284FA
0x1400286d0  jmp     short loc_140028746
0x1400286d2  mov     ebp, 0C000009Ah
0x1400286d7  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x1400286dd  lea     rax, WPP_RECORDER_INITIALIZED
0x1400286e4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400286eb  setnz   r8b
0x1400286ef  and     dl, 4
0x1400286f2  jnz     short loc_1400286F9
0x1400286f4  test    r8b, r8b
0x1400286f7  jz      short loc_140028746
0x1400286f9  mov     r9, cs:WPP_GLOBAL_Control
0x140028700  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140028707  mov     [rsp+0A8h+var_58], ebp
0x14002870b  mov     ecx, 212h
0x140028710  mov     [rsp+0A8h+var_60], 713h
0x140028718  mov     [rsp+0A8h+var_68], rax
0x14002871d  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x140028724  mov     r9, [r9+40h]
0x140028728  mov     [rsp+0A8h+var_70], rax
0x14002872d  mov     [rsp+0A8h+var_78], 16h
0x140028734  mov     [rsp+0A8h+var_80], 12h
0x14002873c  mov     byte ptr [rsp+0A8h+var_88], 2
0x140028741  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140028746  mov     eax, ebp
0x140028748  add     rsp, 68h
0x14002874c  pop     r15
0x14002874e  pop     r14
0x140028750  pop     r13
0x140028752  pop     r12
0x140028754  pop     rdi
0x140028755  pop     rsi
0x140028756  pop     rbp
0x140028757  pop     rbx
0x140028758  retn
```
