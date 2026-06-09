# UlpAuthenticateRequestCompletion

- ea: `0x1400eaff0`
- end: `0x1400eb349`
- name: `UlpAuthenticateRequestCompletion`
- size: `857`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x14000f480`
- `0x140013430`
- `0x14002dd70`
- `0x14008b7c0`
- `0x1400eaaec`
- `0x1400eaff0`
- `0x1400eba60`
- `0x1400ecea4`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4a18`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400eb2ad`
- `ntoskrnl!IofCompleteRequest` at `0x1400eb2ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400eb0a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400eb23a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400eb0a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400eb23a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400eb09d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400eb22e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400eb09d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400eb22e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400eb066`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400eb066`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400eb04e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400eb04e`

## pseudocode

```c
void __fastcall UlpAuthenticateRequestCompletion(__int64 a1, int a2, __int64 a3)
{
  __int64 v5; // rbx
  __int64 v6; // r8
  __int64 v7; // r9
  ULONG_PTR v8; // rdx
  int v9; // eax
  int Request; // esi
  bool v11; // si
  bool v12; // cl
  char IsRequestFromProxy; // al
  _QWORD *v14; // rcx
  __int64 v15; // rax
  _QWORD v16[2]; // [rsp+30h] [rbp-10h] BYREF

  v16[0] = v16;
  v16[1] = v16;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qdP(1032, 162, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1, a2, a3);
  v5 = *(_QWORD *)(a1 + 24);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v5 + 576, 0);
  *(_BYTE *)(a1 + 2440) = 0;
  if ( (*(_DWORD *)(v5 + 632) & 2) != 0 )
  {
    UlCleanupSecurityContext(*(_QWORD *)(v5 + 1096), 0, v5 + 792);
    ExReleasePushLockExclusiveEx(v5 + 576, 0);
    KeLeaveCriticalRegion();
    v8 = a1 + 48;
    v9 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 48));
    if ( UxDebugCheckRefcount && v9 <= -1 )
      UlBugCheckEx(3u, v8, 0x20u, v9);
    goto LABEL_43;
  }
  Request = 0;
  if ( a2 < 0 )
  {
LABEL_15:
    if ( !*(_DWORD *)(a1 + 1868) )
      UlSetErrorCode(a1, 20, *(_QWORD *)(a1 + 1344));
    UlSendErrorResponse(v5);
LABEL_18:
    v12 = 0;
    if ( Request < 0 )
      goto LABEL_31;
    goto LABEL_19;
  }
  if ( a2 != 259 )
  {
    ++*(_DWORD *)(a1 + 2756);
    Request = UlpDeliverHttpRequest(v5, v16);
    if ( Request >= 0 )
    {
      Request = UlpParseNextRequest(v5, 0, (__int64)v16);
      if ( Request >= 0 )
        goto LABEL_18;
    }
    goto LABEL_15;
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 253, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, v5, *(_QWORD *)(v5 + 48));
  UlpSendErrorResponse(v5, 9);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_(1032, 254, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids);
    v11 = 1;
LABEL_20:
    if ( *(_BYTE *)(v5 + 821) && !*(_BYTE *)(a1 + 1466) || *(_BYTE *)(v5 + 822) && (*(_BYTE *)(a1 + 1467) & 1) != 0 )
    {
      IsRequestFromProxy = UlpIsRequestFromProxy(a1);
      v12 = v11;
      if ( !IsRequestFromProxy )
        v12 = 1;
    }
    else
    {
      v12 = v11;
    }
    if ( *(_BYTE *)(v5 + 823) )
      v12 = 1;
    goto LABEL_31;
  }
LABEL_19:
  v11 = a2 == 259;
  if ( a2 >= 0 )
    goto LABEL_20;
  v12 = a2 == 259;
LABEL_31:
  UlCleanupSecurityContext(*(_QWORD *)(v5 + 1096), v12, v5 + 792);
  ExReleasePushLockExclusiveEx(v5 + 576, 0);
  KeLeaveCriticalRegion();
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 289, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, v16);
  while ( 1 )
  {
    v14 = (_QWORD *)v16[0];
    if ( (_QWORD *)v16[0] == v16 )
      break;
    if ( *(_QWORD **)(v16[0] + 8LL) != v16 || (v15 = *(_QWORD *)v16[0], *(_QWORD *)(*(_QWORD *)v16[0] + 8LL) != v16[0]) )
      __fastfail(3u);
    v16[0] = *(_QWORD *)v16[0];
    *(_QWORD *)(v15 + 8) = v16;
    *v14 = 0;
    v14[1] = 0;
    IofCompleteRequest((PIRP)(v14 - 21), 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 290, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids);
  v8 = a1 + 48;
  v9 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 48));
  if ( UxDebugCheckRefcount && v9 <= -1 )
    UlBugCheckEx(3u, v8, 0x20u, v9);
LABEL_43:
  if ( !v9 )
    UlpQueueFreeHttpRequest(a1, v8, v6, v7);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 163, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids);
}

```

## disassembly

```asm
0x1400eaff0  push    rbp
0x1400eaff2  push    rbx
0x1400eaff3  push    rsi
0x1400eaff4  push    rdi
0x1400eaff5  push    r13
0x1400eaff7  push    r14
0x1400eaff9  push    r15
0x1400eaffb  mov     rbp, rsp
0x1400eaffe  sub     rsp, 40h
0x1400eb002  lea     rax, [rbp+var_10]
0x1400eb006  mov     r14d, edx
0x1400eb009  mov     [rbp+var_10], rax
0x1400eb00d  mov     rdi, rcx
0x1400eb010  lea     rax, [rbp+var_10]
0x1400eb014  mov     [rbp+var_8], rax
0x1400eb018  mov     r13d, 1
0x1400eb01e  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eb025  jz      short loc_1400EB04A
0x1400eb027  mov     [rsp+40h+var_18], r8
0x1400eb02c  mov     edx, 0A2h
0x1400eb031  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x1400eb038  mov     dword ptr [rsp+40h+var_20], r14d
0x1400eb03d  mov     ecx, 408h
0x1400eb042  mov     r9, rdi
0x1400eb045  call    WPP_SF_qdP
0x1400eb04a  mov     rbx, [rdi+18h]
0x1400eb04e  call    cs:__imp_KeEnterCriticalRegion
0x1400eb055  nop     dword ptr [rax+rax+00h]
0x1400eb05a  lea     r15, [rbx+240h]
0x1400eb061  xor     edx, edx
0x1400eb063  mov     rcx, r15
0x1400eb066  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400eb06d  nop     dword ptr [rax+rax+00h]
0x1400eb072  mov     byte ptr [rdi+988h], 0
0x1400eb079  mov     eax, [rbx+278h]
0x1400eb07f  test    al, 2
0x1400eb081  jz      short loc_1400EB0EA
0x1400eb083  mov     rcx, [rbx+448h]
0x1400eb08a  lea     r8, [rbx+318h]
0x1400eb091  xor     edx, edx
0x1400eb093  call    UlCleanupSecurityContext
0x1400eb098  xor     edx, edx
0x1400eb09a  mov     rcx, r15
0x1400eb09d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400eb0a4  nop     dword ptr [rax+rax+00h]
0x1400eb0a9  call    cs:__imp_KeLeaveCriticalRegion
0x1400eb0b0  nop     dword ptr [rax+rax+00h]
0x1400eb0b5  lea     rdx, [rdi+30h]; BugCheckParameter2
0x1400eb0b9  or      eax, 0FFFFFFFFh
0x1400eb0bc  lock xadd [rdx], eax
0x1400eb0c0  dec     eax
0x1400eb0c2  cmp     cs:UxDebugCheckRefcount, 0
0x1400eb0c9  jz      loc_1400EB30E
0x1400eb0cf  cmp     eax, 0FFFFFFFFh
0x1400eb0d2  jg      loc_1400EB30E
0x1400eb0d8  mov     ecx, 3; BugCheckParameter1
0x1400eb0dd  movsxd  r9, eax; BugCheckParameter4
0x1400eb0e0  lea     r8d, [rcx+1Dh]; BugCheckParameter3
0x1400eb0e4  call    UlBugCheckEx
0x1400eb0ea  xor     esi, esi
0x1400eb0ec  test    r14d, r14d
0x1400eb0ef  js      loc_1400EB188
0x1400eb0f5  cmp     r14d, 103h
0x1400eb0fc  jnz     short loc_1400EB15B
0x1400eb0fe  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eb105  jz      short loc_1400EB128
0x1400eb107  mov     rax, [rbx+30h]
0x1400eb10b  lea     edx, [r14-6]
0x1400eb10f  mov     ecx, 408h
0x1400eb114  mov     [rsp+40h+var_20], rax
0x1400eb119  mov     r9, rbx
0x1400eb11c  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x1400eb123  call    WPP_SF_qq
0x1400eb128  xor     r8d, r8d
0x1400eb12b  mov     rcx, rbx
0x1400eb12e  lea     edx, [r8+9]
0x1400eb132  call    UlpSendErrorResponse
0x1400eb137  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eb13e  jz      short loc_1400EB1B3
0x1400eb140  mov     edx, 0FEh
0x1400eb145  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x1400eb14c  mov     ecx, 408h
0x1400eb151  call    WPP_SF_
0x1400eb156  mov     sil, r13b
0x1400eb159  jmp     short loc_1400EB1C3
0x1400eb15b  add     [rdi+0AC4h], r13d
0x1400eb162  lea     rdx, [rbp+var_10]
0x1400eb166  mov     rcx, rbx
0x1400eb169  call    UlpDeliverHttpRequest
0x1400eb16e  mov     esi, eax
0x1400eb170  test    eax, eax
0x1400eb172  js      short loc_1400EB188
0x1400eb174  lea     r8, [rbp+var_10]
0x1400eb178  xor     edx, edx
0x1400eb17a  mov     rcx, rbx
0x1400eb17d  call    UlpParseNextRequest
0x1400eb182  mov     esi, eax
0x1400eb184  test    eax, eax
0x1400eb186  jns     short loc_1400EB1AD
0x1400eb188  cmp     dword ptr [rdi+74Ch], 0
0x1400eb18f  jnz     short loc_1400EB1A5
0x1400eb191  mov     r8, [rdi+540h]
0x1400eb198  mov     edx, 14h
0x1400eb19d  mov     rcx, rdi
0x1400eb1a0  call    UlSetErrorCode
0x1400eb1a5  mov     rcx, rbx
0x1400eb1a8  call    UlSendErrorResponse
0x1400eb1ad  xor     cl, cl
0x1400eb1af  test    esi, esi
0x1400eb1b1  js      short loc_1400EB20F
0x1400eb1b3  cmp     r14d, 103h
0x1400eb1ba  setz    sil
0x1400eb1be  test    r14d, r14d
0x1400eb1c1  js      short loc_1400EB20C
0x1400eb1c3  cmp     byte ptr [rbx+335h], 0
0x1400eb1ca  jz      short loc_1400EB1D5
0x1400eb1cc  cmp     byte ptr [rdi+5BAh], 0
0x1400eb1d3  jz      short loc_1400EB1E7
0x1400eb1d5  cmp     byte ptr [rbx+336h], 0
0x1400eb1dc  jz      short loc_1400EB1FB
0x1400eb1de  test    [rdi+5BBh], r13b
0x1400eb1e5  jz      short loc_1400EB1FB
0x1400eb1e7  mov     rcx, rdi
0x1400eb1ea  call    UlpIsRequestFromProxy
0x1400eb1ef  test    al, al
0x1400eb1f1  movzx   ecx, sil
0x1400eb1f5  cmovz   ecx, r13d
0x1400eb1f9  jmp     short loc_1400EB1FE
0x1400eb1fb  mov     cl, sil
0x1400eb1fe  cmp     byte ptr [rbx+337h], 0
0x1400eb205  jz      short loc_1400EB20F
0x1400eb207  mov     cl, r13b
0x1400eb20a  jmp     short loc_1400EB20F
0x1400eb20c  mov     cl, sil
0x1400eb20f  xor     edx, edx
0x1400eb211  lea     r8, [rbx+318h]
0x1400eb218  test    cl, cl
0x1400eb21a  mov     rcx, [rbx+448h]
0x1400eb221  setnz   dl
0x1400eb224  call    UlCleanupSecurityContext
0x1400eb229  xor     edx, edx
0x1400eb22b  mov     rcx, r15
0x1400eb22e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400eb235  nop     dword ptr [rax+rax+00h]
0x1400eb23a  call    cs:__imp_KeLeaveCriticalRegion
0x1400eb241  nop     dword ptr [rax+rax+00h]
0x1400eb246  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eb24d  jz      short loc_1400EB269
0x1400eb24f  mov     edx, 121h
0x1400eb254  lea     r9, [rbp+var_10]
0x1400eb258  mov     ecx, 408h
0x1400eb25d  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x1400eb264  call    WPP_SF_q
0x1400eb269  mov     rcx, [rbp+var_10]
0x1400eb26d  lea     rax, [rbp+var_10]
0x1400eb271  cmp     rcx, rax
0x1400eb274  jz      short loc_1400EB2C2
0x1400eb276  lea     rax, [rbp+var_10]
0x1400eb27a  cmp     [rcx+8], rax
0x1400eb27e  jnz     short loc_1400EB2BB
0x1400eb280  mov     rax, [rcx]
0x1400eb283  cmp     [rax+8], rcx
0x1400eb287  jnz     short loc_1400EB2BB
0x1400eb289  mov     [rbp+var_10], rax
0x1400eb28d  lea     rdx, [rbp+var_10]
0x1400eb291  mov     [rax+8], rdx
0x1400eb295  xor     edx, edx; PriorityBoost
0x1400eb297  mov     qword ptr [rcx], 0
0x1400eb29e  mov     qword ptr [rcx+8], 0
0x1400eb2a6  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1400eb2ad  call    cs:__imp_IofCompleteRequest
0x1400eb2b4  nop     dword ptr [rax+rax+00h]
0x1400eb2b9  jmp     short loc_1400EB269
0x1400eb2bb  mov     ecx, 3
0x1400eb2c0  int     29h; Win8: RtlFailFast(ecx)
0x1400eb2c2  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eb2c9  jz      short loc_1400EB2E1
0x1400eb2cb  mov     edx, 122h
0x1400eb2d0  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x1400eb2d7  mov     ecx, 408h
0x1400eb2dc  call    WPP_SF_
0x1400eb2e1  lea     rdx, [rdi+30h]; BugCheckParameter2
0x1400eb2e5  or      eax, 0FFFFFFFFh
0x1400eb2e8  lock xadd [rdx], eax
0x1400eb2ec  dec     eax
0x1400eb2ee  cmp     cs:UxDebugCheckRefcount, 0
0x1400eb2f5  jz      short loc_1400EB30E
0x1400eb2f7  cmp     eax, 0FFFFFFFFh
0x1400eb2fa  jg      short loc_1400EB30E
0x1400eb2fc  mov     ecx, 3; BugCheckParameter1
0x1400eb301  movsxd  r9, eax; BugCheckParameter4
0x1400eb304  lea     r8d, [rcx+1Dh]; BugCheckParameter3
0x1400eb308  call    UlBugCheckEx
0x1400eb30e  test    eax, eax
0x1400eb310  jnz     short loc_1400EB31A
0x1400eb312  mov     rcx, rdi
0x1400eb315  call    UlpQueueFreeHttpRequest
0x1400eb31a  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eb321  jz      short loc_1400EB339
0x1400eb323  mov     edx, 0A3h
0x1400eb328  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x1400eb32f  mov     ecx, 408h
0x1400eb334  call    WPP_SF_
0x1400eb339  add     rsp, 40h
0x1400eb33d  pop     r15
0x1400eb33f  pop     r14
0x1400eb341  pop     r13
0x1400eb343  pop     rdi
0x1400eb344  pop     rsi
0x1400eb345  pop     rbx
0x1400eb346  pop     rbp
0x1400eb347  retn
```
