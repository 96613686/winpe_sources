# PrjfExpandAndWait

- ea: `0x140029214`
- end: `0x140029647`
- name: `PrjfExpandAndWait`
- size: `1075`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, int, int, int, char)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140023d68`
- `0x14002aecc`
- `0x14002b640`
- `0x14002d988`
- `0x14003df88`

## callees

- `0x14000d754`
- `0x140029214`
- `0x14002aa24`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400294be`
- `ntoskrnl!KeSetEvent` at `0x1400294be`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002925d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029319`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029584`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002925d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029319`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029584`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002923c`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400294d4`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002923c`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400294d4`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140029283`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140029382`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x1400295b7`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140029283`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140029382`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x1400295b7`

## pseudocode

```c
__int64 __fastcall PrjfExpandAndWait(
        PFLT_CALLBACK_DATA CallbackData,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        __int64 a4,
        int a5,
        int a6,
        unsigned int a7,
        char a8)
{
  struct _FAST_MUTEX *v8; // r14
  NTSTATUS v13; // r9d
  int v15; // ebx
  signed __int32 v16; // r12d
  _DWORD *v17; // rax
  NTSTATUS v18; // eax
  __int64 v19; // [rsp+48h] [rbp-60h]
  __int64 v20; // [rsp+50h] [rbp-58h]

  v8 = (struct _FAST_MUTEX *)(a4 + 8);
  ExAcquireFastMutex((PFAST_MUTEX)(a4 + 8));
  if ( *(_DWORD *)(a4 + 64) < a5 )
  {
    ExReleaseFastMutex(v8);
    v15 = PrjfLaunchExpansion(a2, a3, a4, a5, 0, a6, a7);
    if ( v15 >= 0 )
    {
      v15 = FltCancellableWaitForSingleObject((PVOID)(*(_QWORD *)(a4 + 88) + 16LL), 0, CallbackData);
      v16 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a4 + 88) + 68LL));
      if ( v15 == -1073741536 || v15 == -1073741749 )
      {
        if ( (BYTE9(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_sDdZ(
            778,
            BYTE9(xmmword_14001A3D0) & 4,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            3u,
            0xAu,
            0x1Fu,
            (ULONGLONG)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
            "onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
            2092,
            v15,
            &a3->FileName);
        if ( !v16 )
          KeSetEvent((PRKEVENT)(*(_QWORD *)(a4 + 88) + 40LL), 0, 0);
      }
      else if ( v15 < 0
             && ((BYTE9(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          778,
          BYTE9(xmmword_14001A3D0) & 4,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3u,
          0xAu,
          0x20u,
          (ULONGLONG)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
          "onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
          2110,
          v15,
          &a3->FileName);
      }
    }
    ExAcquireFastMutex(v8);
    if ( *(_DWORD *)(a4 + 64) < a5 )
    {
      v17 = *(_DWORD **)(a4 + 88);
      if ( v17 )
      {
        if ( v15 >= 0 )
        {
          v15 = v17[2];
          if ( v15 >= 0 )
            v15 = -1073741595;
        }
        *v17 = 0;
        *(_DWORD *)(*(_QWORD *)(a4 + 88) + 4LL) = *(_DWORD *)(a4 + 64);
      }
      if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v20) = v15;
        LODWORD(v19) = 2157;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          522,
          BYTE1(xmmword_14001A3D0) & 4,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2u,
          0xAu,
          0x21u,
          (ULONGLONG)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
          "onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
          v19,
          v20,
          &a3->FileName);
      }
    }
    else
    {
      v15 = 0;
    }
    ExReleaseFastMutex(v8);
    if ( v15 >= 0 )
    {
      if ( a8 )
      {
        v18 = FltCancellableWaitForSingleObject((PVOID)(a4 + 344), 0, CallbackData);
        v15 = v18;
        if ( v18 < 0
          && ((BYTE9(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
        {
          LODWORD(v20) = v18;
          LODWORD(v19) = 2183;
          WPP_RECORDER_AND_TRACE_SF_sDdZ(
            778,
            BYTE9(xmmword_14001A3D0) & 4,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            3u,
            0xAu,
            0x22u,
            (ULONGLONG)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
            "onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
            v19,
            v20,
            &a3->FileName);
        }
      }
    }
    return (unsigned int)v15;
  }
  else
  {
    ExReleaseFastMutex(v8);
    if ( a8 )
    {
      v13 = FltCancellableWaitForSingleObject((PVOID)(a4 + 344), 0, CallbackData);
      if ( v13 < 0
        && ((BYTE9(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          778,
          BYTE9(xmmword_14001A3D0) & 4,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3u,
          0xAu,
          0x1Eu,
          (ULONGLONG)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
          "onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
          2061,
          v13,
          &a3->FileName);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140029214  mov     [rsp+CallbackData], rcx
0x140029219  push    rbx
0x14002921a  push    rbp
0x14002921b  push    rsi
0x14002921c  push    rdi
0x14002921d  push    r12
0x14002921f  push    r13
0x140029221  push    r14
0x140029223  push    r15
0x140029225  sub     rsp, 68h
0x140029229  lea     r14, [r9+8]
0x14002922d  mov     rsi, rcx
0x140029230  mov     rcx, r14; FastMutex
0x140029233  mov     rdi, r9
0x140029236  mov     r13, r8
0x140029239  mov     rbx, rdx
0x14002923c  call    cs:__imp_ExAcquireFastMutex
0x140029243  nop     dword ptr [rax+rax+00h]
0x140029248  mov     r15d, [rsp+0A8h+arg_20]
0x140029250  mov     rcx, r14; FastMutex
0x140029253  cmp     [rdi+40h], r15d
0x140029257  jl      loc_140029319
0x14002925d  call    cs:__imp_ExReleaseFastMutex
0x140029264  nop     dword ptr [rax+rax+00h]
0x140029269  cmp     [rsp+0A8h+arg_38], 0
0x140029271  jz      loc_140029312
0x140029277  lea     rcx, [rdi+158h]; Object
0x14002927e  mov     r8, rsi; CallbackData
0x140029281  xor     edx, edx; Timeout
0x140029283  call    cs:__imp_FltCancellableWaitForSingleObject
0x14002928a  nop     dword ptr [rax+rax+00h]
0x14002928f  mov     r9d, eax
0x140029292  test    eax, eax
0x140029294  jns     short loc_140029312
0x140029296  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x14002929c  lea     rbp, WPP_RECORDER_INITIALIZED
0x1400292a3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400292aa  mov     sil, 4
0x1400292ad  setnz   r8b
0x1400292b1  and     dl, sil
0x1400292b4  jnz     short loc_1400292BB
0x1400292b6  test    r8b, r8b
0x1400292b9  jz      short loc_140029312
0x1400292bb  lea     rax, [r13+58h]
0x1400292bf  mov     ecx, 30Ah
0x1400292c4  mov     [rsp+0A8h+var_50], rax
0x1400292c9  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400292d0  mov     dword ptr [rsp+0A8h+var_58], r9d
0x1400292d5  mov     r9, cs:WPP_GLOBAL_Control
0x1400292dc  mov     dword ptr [rsp+0A8h+var_60], 80Dh
0x1400292e4  mov     [rsp+0A8h+var_68], rax
0x1400292e9  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x1400292f0  mov     [rsp+0A8h+var_70], rax
0x1400292f5  mov     r9, [r9+40h]
0x1400292f9  mov     word ptr [rsp+0A8h+var_78], 1Eh
0x140029300  mov     [rsp+0A8h+var_80], 0Ah
0x140029308  mov     byte ptr [rsp+0A8h+var_88], 3
0x14002930d  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140029312  xor     eax, eax
0x140029314  jmp     loc_140029635
0x140029319  call    cs:__imp_ExReleaseFastMutex
0x140029320  nop     dword ptr [rax+rax+00h]
0x140029325  mov     eax, [rsp+0A8h+arg_30]
0x14002932c  mov     r9d, r15d
0x14002932f  mov     [rsp+0A8h+var_78], eax; int
0x140029333  mov     r8, rdi; Context
0x140029336  mov     eax, [rsp+0A8h+arg_28]
0x14002933d  mov     rdx, r13; FileObject
0x140029340  mov     [rsp+0A8h+var_80], eax; int
0x140029344  mov     rcx, rbx; Instance
0x140029347  mov     [rsp+0A8h+var_88], 0; CallbackData
0x140029350  call    PrjfLaunchExpansion
0x140029355  lea     rbp, WPP_RECORDER_INITIALIZED
0x14002935c  mov     ebx, eax
0x14002935e  lea     r12, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140029365  mov     sil, 4
0x140029368  test    eax, eax
0x14002936a  js      loc_1400294D1
0x140029370  mov     rcx, [rdi+58h]
0x140029374  xor     edx, edx; Timeout
0x140029376  mov     r8, [rsp+0A8h+CallbackData]; CallbackData
0x14002937e  add     rcx, 10h; Object
0x140029382  call    cs:__imp_FltCancellableWaitForSingleObject
0x140029389  nop     dword ptr [rax+rax+00h]
0x14002938e  mov     ebx, eax
0x140029390  or      r12d, 0FFFFFFFFh
0x140029394  mov     rax, [rdi+58h]
0x140029398  lock xadd [rax+44h], r12d
0x14002939e  dec     r12d
0x1400293a1  cmp     ebx, 0C0000120h
0x1400293a7  jz      loc_14002943B
0x1400293ad  cmp     ebx, 0C000004Bh
0x1400293b3  jz      loc_14002943B
0x1400293b9  test    ebx, ebx
0x1400293bb  jns     loc_1400294CA
0x1400293c1  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400293c8  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x1400293ce  setnz   r8b
0x1400293d2  and     dl, sil
0x1400293d5  jnz     short loc_1400293E0
0x1400293d7  test    r8b, r8b
0x1400293da  jz      loc_1400294CA
0x1400293e0  mov     r9, cs:WPP_GLOBAL_Control
0x1400293e7  lea     rax, [r13+58h]
0x1400293eb  mov     [rsp+0A8h+var_50], rax
0x1400293f0  lea     r12, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400293f7  mov     dword ptr [rsp+0A8h+var_58], ebx
0x1400293fb  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x140029402  mov     dword ptr [rsp+0A8h+var_60], 83Eh
0x14002940a  mov     ecx, 30Ah
0x14002940f  mov     r9, [r9+40h]
0x140029413  mov     [rsp+0A8h+var_68], r12
0x140029418  mov     [rsp+0A8h+var_70], rax
0x14002941d  mov     word ptr [rsp+0A8h+var_78], 20h ; ' '
0x140029424  mov     [rsp+0A8h+var_80], 0Ah
0x14002942c  mov     byte ptr [rsp+0A8h+var_88], 3
0x140029431  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140029436  jmp     loc_1400294D1
0x14002943b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140029442  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x140029448  setnz   r8b
0x14002944c  and     dl, sil
0x14002944f  jnz     short loc_140029456
0x140029451  test    r8b, r8b
0x140029454  jz      short loc_1400294AC
0x140029456  mov     r9, cs:WPP_GLOBAL_Control
0x14002945d  lea     rax, [r13+58h]
0x140029461  mov     [rsp+0A8h+var_50], rax
0x140029466  mov     ecx, 30Ah
0x14002946b  mov     dword ptr [rsp+0A8h+var_58], ebx
0x14002946f  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140029476  mov     dword ptr [rsp+0A8h+var_60], 82Ch
0x14002947e  mov     r9, [r9+40h]
0x140029482  mov     [rsp+0A8h+var_68], rax
0x140029487  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002948e  mov     [rsp+0A8h+var_70], rax
0x140029493  mov     word ptr [rsp+0A8h+var_78], 1Fh
0x14002949a  mov     [rsp+0A8h+var_80], 0Ah
0x1400294a2  mov     byte ptr [rsp+0A8h+var_88], 3
0x1400294a7  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x1400294ac  test    r12d, r12d
0x1400294af  jnz     short loc_1400294CA
0x1400294b1  mov     rcx, [rdi+58h]
0x1400294b5  xor     r8d, r8d; Wait
0x1400294b8  add     rcx, 28h ; '('; Event
0x1400294bc  xor     edx, edx; Increment
0x1400294be  call    cs:__imp_KeSetEvent
0x1400294c5  nop     dword ptr [rax+rax+00h]
0x1400294ca  lea     r12, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400294d1  mov     rcx, r14; FastMutex
0x1400294d4  call    cs:__imp_ExAcquireFastMutex
0x1400294db  nop     dword ptr [rax+rax+00h]
0x1400294e0  cmp     [rdi+40h], r15d
0x1400294e4  jl      short loc_1400294ED
0x1400294e6  xor     ebx, ebx
0x1400294e8  jmp     loc_140029581
0x1400294ed  mov     rax, [rdi+58h]
0x1400294f1  test    rax, rax
0x1400294f4  jz      short loc_140029517
0x1400294f6  test    ebx, ebx
0x1400294f8  js      short loc_140029507
0x1400294fa  mov     ebx, [rax+8]
0x1400294fd  mov     ecx, 0C00000E5h
0x140029502  test    ebx, ebx
0x140029504  cmovns  ebx, ecx
0x140029507  mov     dword ptr [rax], 0
0x14002950d  mov     rcx, [rdi+58h]
0x140029511  mov     eax, [rdi+40h]
0x140029514  mov     [rcx+4], eax
0x140029517  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14002951e  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140029524  setnz   r8b
0x140029528  and     dl, sil
0x14002952b  jnz     short loc_140029532
0x14002952d  test    r8b, r8b
0x140029530  jz      short loc_140029581
0x140029532  mov     r9, cs:WPP_GLOBAL_Control
0x140029539  lea     rax, [r13+58h]
0x14002953d  mov     [rsp+0A8h+var_50], rax
0x140029542  mov     ecx, 20Ah
0x140029547  mov     dword ptr [rsp+0A8h+var_58], ebx
0x14002954b  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x140029552  mov     dword ptr [rsp+0A8h+var_60], 86Dh
0x14002955a  mov     r9, [r9+40h]
0x14002955e  mov     [rsp+0A8h+var_68], r12
0x140029563  mov     [rsp+0A8h+var_70], rax
0x140029568  mov     word ptr [rsp+0A8h+var_78], 21h ; '!'
0x14002956f  mov     [rsp+0A8h+var_80], 0Ah
0x140029577  mov     byte ptr [rsp+0A8h+var_88], 2
0x14002957c  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140029581  mov     rcx, r14; FastMutex
0x140029584  call    cs:__imp_ExReleaseFastMutex
0x14002958b  nop     dword ptr [rax+rax+00h]
0x140029590  test    ebx, ebx
0x140029592  js      loc_140029633
0x140029598  cmp     [rsp+0A8h+arg_38], 0
0x1400295a0  jz      loc_140029633
0x1400295a6  mov     r8, [rsp+0A8h+CallbackData]; CallbackData
0x1400295ae  lea     rcx, [rdi+158h]; Object
0x1400295b5  xor     edx, edx; Timeout
0x1400295b7  call    cs:__imp_FltCancellableWaitForSingleObject
0x1400295be  nop     dword ptr [rax+rax+00h]
0x1400295c3  mov     ebx, eax
0x1400295c5  test    eax, eax
0x1400295c7  jns     short loc_140029633
0x1400295c9  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400295d0  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x1400295d6  setnz   r8b
0x1400295da  and     dl, sil
0x1400295dd  jnz     short loc_1400295E4
0x1400295df  test    r8b, r8b
0x1400295e2  jz      short loc_140029633
0x1400295e4  mov     r9, cs:WPP_GLOBAL_Control
0x1400295eb  lea     rax, [r13+58h]
0x1400295ef  mov     [rsp+0A8h+var_50], rax
0x1400295f4  mov     ecx, 30Ah
0x1400295f9  mov     dword ptr [rsp+0A8h+var_58], ebx
0x1400295fd  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x140029604  mov     dword ptr [rsp+0A8h+var_60], 887h
0x14002960c  mov     r9, [r9+40h]
0x140029610  mov     [rsp+0A8h+var_68], r12
0x140029615  mov     [rsp+0A8h+var_70], rax
0x14002961a  mov     word ptr [rsp+0A8h+var_78], 22h ; '"'
0x140029621  mov     [rsp+0A8h+var_80], 0Ah
0x140029629  mov     byte ptr [rsp+0A8h+var_88], 3
0x14002962e  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140029633  mov     eax, ebx
0x140029635  add     rsp, 68h
0x140029639  pop     r15
0x14002963b  pop     r14
0x14002963d  pop     r13
0x14002963f  pop     r12
0x140029641  pop     rdi
0x140029642  pop     rsi
0x140029643  pop     rbp
0x140029644  pop     rbx
0x140029645  retn
```
