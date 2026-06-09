# Endpoint_Enable

- ea: `0x140027270`
- end: `0x1400277b0`
- name: `Endpoint_Enable`
- size: `1344`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140025720`
- `0x140025954`

## callees

- `0x140002758`
- `0x1400038c0`
- `0x14002338c`
- `0x1400233d0`
- `0x140027270`
- `0x1400283c8`
- `0x140029048`
- `0x1400290e0`
- `0x14002989c`
- `0x1400369ac`
- `0x14003c5d4`
- `0x140042b38`
- `0x14004560c`
- `0x140059970`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140027626`
- `ntoskrnl!ExAllocatePool2` at `0x140027626`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x1400273cc`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x1400273cc`

## pseudocode

```c
__int64 __fastcall Endpoint_Enable(__int64 *a1)
{
  __int64 *v2; // r14
  __int64 *v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r12
  __int64 v7; // rdx
  int StreamContextArray; // edi
  __int64 v9; // rax
  __int64 v10; // r9
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r15
  unsigned int i; // esi
  __int64 DequeuePointer; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rsi
  __int64 Pool2; // rax
  int v23; // r9d
  __int64 v24; // rcx
  int v25; // edx
  char v26; // [rsp+28h] [rbp-31h]
  int v27; // [rsp+30h] [rbp-29h]
  char v28; // [rsp+38h] [rbp-21h]
  __int128 v29; // [rsp+50h] [rbp-9h] BYREF
  __int128 v30; // [rsp+60h] [rbp+7h]
  char pszDest[16]; // [rsp+70h] [rbp+17h] BYREF
  __int64 v32; // [rsp+80h] [rbp+27h]

  v29 = 0;
  v32 = 0;
  v30 = 0;
  *(_OWORD *)pszDest = 0;
  v2 = a1 + 2;
  v3 = WPP_efed3b2fad403e600dcc20c948898b03_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = 4;
    WPP_RECORDER_SF_ddq(
      *(_QWORD *)(*a1 + 72),
      (_DWORD)v3,
      13,
      24,
      (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
      *(_BYTE *)(*v2 + 143),
      *((_DWORD *)a1 + 38),
      a1[3]);
  }
  if ( (*(_DWORD *)(*a1 + 744) & 0x10000) != 0 )
  {
    v12 = *v2;
    if ( *(_DWORD *)(*v2 + 36) == 1 && ((*((_DWORD *)a1 + 32) - 3) & 0xFFFFFFFB) == 0 )
    {
      v13 = 120LL * (unsigned int)(*(_DWORD *)(v12 + 44) - 1);
      v14 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 8) + 152LL) + 48LL);
      if ( *(_BYTE *)(v13 + v14 + 13) == 3 )
        _InterlockedAdd((volatile signed __int32 *)(v13 + v14 + 108), 1u);
    }
  }
  v4 = *a1;
  if ( (*(_DWORD *)(*a1 + 744) & 0x100000) != 0
    && *(_DWORD *)(*v2 + 36) > 1u
    && *(_DWORD *)(*v2 + 20) <= 1u
    && ((*((_DWORD *)a1 + 32) - 3) & 0xFFFFFFFB) == 0
    && !*((_BYTE *)a1 + 38) )
  {
    *((_BYTE *)a1 + 38) = 1;
    if ( _InterlockedIncrement((volatile signed __int32 *)(v4 + 1104)) == 1 )
      Controller_SetHSIIWorkaround();
  }
  v5 = ((__int64 (__fastcall *)(__int64, __int64, __int64 (__fastcall *)()))qword_14006CD18)(
         UcxDriverGlobals,
         a1[3],
         Endpoint_Enable);
  v6 = v5;
  if ( *((_BYTE *)a1 + 37) )
  {
    if ( v5 )
    {
      v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
              WdfDriverGlobals,
              v5,
              off_14006C220);
      a1[18] = v15;
      v16 = v15;
      if ( *(_QWORD *)(v15 + 32)
        || (StreamContextArray = XilEndpoint_AllocateStreamContextArray(v15), StreamContextArray >= 0) )
      {
        for ( i = 1; ; ++i )
        {
          if ( i > *(_DWORD *)(v16 + 8) )
          {
            v20 = v16;
            goto LABEL_27;
          }
          StreamContextArray = TR_Enable_Internal(*(_QWORD *)(104LL * (i - 1) + a1[18] + 48));
          if ( StreamContextArray < 0 )
            break;
          DequeuePointer = Endpoint_GetDequeuePointer(a1, i);
          v19 = 2LL * i;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1[18] + 32) + 16LL) + 8 * v19) = DequeuePointer;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v25 = *(unsigned __int8 *)(*v2 + 143);
          LOBYTE(v25) = 2;
          WPP_RECORDER_SF_dddd(
            *(_QWORD *)(*a1 + 72),
            v25,
            13,
            26,
            (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
            *(_BYTE *)(*v2 + 143),
            *((_DWORD *)a1 + 38),
            i + 1,
            StreamContextArray);
        }
      }
      goto LABEL_15;
    }
    v21 = a1[17];
    if ( !v21 )
    {
      Pool2 = ExAllocatePool2(64, 152, 1229146200);
      a1[17] = Pool2;
      v21 = Pool2;
      if ( !Pool2 )
      {
        StreamContextArray = -1073741670;
        goto LABEL_15;
      }
      a1[18] = Pool2;
      *(_QWORD *)Pool2 = a1;
      *(_DWORD *)(Pool2 + 8) = 1;
      *(_DWORD *)(Pool2 + 12) = 1;
      *(_QWORD *)(a1[18] + 48) = a1[11];
      StreamContextArray = XilEndpoint_AllocateStreamContextArray(Pool2);
      if ( StreamContextArray < 0 )
        goto LABEL_15;
    }
    StreamContextArray = TR_Enable_Internal(a1[11]);
    if ( StreamContextArray >= 0 )
    {
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1[18] + 32) + 16LL) + 16LL) = TR_GetDequeuePointer(a1[11]);
      v20 = v21;
LABEL_27:
      StreamContextArray = XilEndpoint_CommitStreamContextArrayUpdates(v20);
      if ( StreamContextArray >= 0 )
        goto LABEL_7;
LABEL_15:
      LOBYTE(v7) = 1;
      Endpoint_Disable_Internal(a1, v7);
      goto LABEL_10;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_15;
    v23 = 25;
    v28 = StreamContextArray;
    v27 = *((_DWORD *)a1 + 38);
    v26 = *(_BYTE *)(*v2 + 143);
    v24 = *(_QWORD *)(*a1 + 72);
LABEL_49:
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_ddd(v24, v7, 13, v23, (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids, v26, v27, v28);
    goto LABEL_15;
  }
  StreamContextArray = TR_Enable_Internal(a1[11]);
  if ( StreamContextArray < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_15;
    v23 = 27;
    v28 = StreamContextArray;
    v24 = *(_QWORD *)(*a1 + 72);
    v27 = *((_DWORD *)a1 + 38);
    v26 = *(_BYTE *)(*v2 + 143);
    goto LABEL_49;
  }
LABEL_7:
  v9 = *v2;
  v10 = *a1;
  *(_QWORD *)&v29 = 56;
  pszDest[0] = 0;
  HIDWORD(v30) = 16;
  *(_QWORD *)&v30 = 0;
  BYTE8(v30) = 0;
  v32 = 0x200000002LL;
  *((_QWORD *)&v29 + 1) = 0xC800000400LL;
  if ( RtlStringCchPrintfA(
         pszDest,
         0x10u,
         "%02d SLT%02d DCI%02d",
         *(_DWORD *)(v10 + 176),
         *(unsigned __int8 *)(v9 + 143),
         *((_DWORD *)a1 + 38)) < 0
    || (int)imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v29, a1 + 10) < 0 )
  {
    a1[10] = *(_QWORD *)(*a1 + 72);
  }
  ESM_AddEvent(a1 + 39);
  StreamContextArray = 0;
LABEL_10:
  if ( v6 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(), __int64, const char *))(WdfFunctions_01033 + 1648))(
      WdfDriverGlobals,
      v6,
      Endpoint_Enable,
      1321,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\endpoint.c");
  return (unsigned int)StreamContextArray;
}

```

## disassembly

```asm
0x140027270  mov     [rsp-8+arg_8], rbx
0x140027275  mov     [rsp-8+arg_10], rsi
0x14002727a  push    rbp
0x14002727b  push    rdi
0x14002727c  push    r12
0x14002727e  push    r14
0x140027280  push    r15
0x140027282  lea     rbp, [rsp-37h]
0x140027287  sub     rsp, 90h
0x14002728e  mov     rax, cs:__security_cookie
0x140027295  xor     rax, rsp
0x140027298  mov     [rbp+57h+var_28], rax
0x14002729c  xorps   xmm0, xmm0
0x14002729f  xor     eax, eax
0x1400272a1  movups  [rbp+57h+var_60], xmm0
0x1400272a5  mov     [rbp+57h+var_30], rax
0x1400272a9  mov     rbx, rcx
0x1400272ac  movups  [rbp+57h+var_50], xmm0
0x1400272b0  movups  xmmword ptr [rbp+57h+pszDest], xmm0
0x1400272b4  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400272bb  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400272c2  lea     r14, [rcx+10h]
0x1400272c6  lea     rdx, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x1400272cd  lea     esi, [rax+0Dh]
0x1400272d0  jnz     loc_140027465
0x1400272d6  mov     rax, [rbx]
0x1400272d9  mov     edi, 1
0x1400272de  mov     r8d, 0FFFFFFFBh
0x1400272e4  mov     ecx, [rax+2E8h]
0x1400272ea  bt      rcx, 10h
0x1400272ef  jb      loc_1400274C3
0x1400272f5  mov     rcx, [rbx]
0x1400272f8  mov     eax, [rcx+2E8h]
0x1400272fe  bt      rax, 14h
0x140027303  jb      loc_1400275E3
0x140027309  mov     rax, cs:qword_14006CD18
0x140027310  lea     r8, Endpoint_Enable
0x140027317  mov     rdx, [rbx+18h]
0x14002731b  mov     rcx, cs:UcxDriverGlobals
0x140027322  call    _guard_dispatch_icall
0x140027327  cmp     byte ptr [rbx+25h], 0
0x14002732b  mov     r12, rax
0x14002732e  jnz     loc_14002750E
0x140027334  mov     rcx, [rbx+58h]
0x140027338  call    TR_Enable_Internal
0x14002733d  mov     edi, eax
0x14002733f  test    eax, eax
0x140027341  js      loc_1400274A7
0x140027347  mov     rax, [r14]
0x14002734a  lea     r8, pszFormat; "%02d SLT%02d DCI%02d"
0x140027351  mov     r9, [rbx]
0x140027354  mov     edx, 10h; cchDest
0x140027359  mov     qword ptr [rbp+57h+var_60], 38h ; '8'
0x140027361  mov     [rbp+57h+pszDest], 0
0x140027365  mov     dword ptr [rbp+57h+var_50+0Ch], edx
0x140027368  mov     qword ptr [rbp+57h+var_50], 0
0x140027370  mov     byte ptr [rbp+57h+var_50+8], 0
0x140027374  mov     dword ptr [rbp+57h+var_30], 2
0x14002737b  mov     dword ptr [rbp+57h+var_30+4], 2
0x140027382  mov     dword ptr [rbp+57h+var_60+8], 400h
0x140027389  mov     dword ptr [rbp+57h+var_60+0Ch], 0C8h
0x140027390  movzx   ecx, byte ptr [rax+8Fh]
0x140027397  mov     eax, [rbx+98h]
0x14002739d  mov     r9d, [r9+0B0h]
0x1400273a4  mov     dword ptr [rsp+0B0h+var_88], eax
0x1400273a8  mov     dword ptr [rsp+0B0h+var_90], ecx
0x1400273ac  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1400273b0  call    RtlStringCchPrintfA
0x1400273b5  test    eax, eax
0x1400273b7  js      loc_140027455
0x1400273bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400273c4  lea     r8, [rbx+50h]
0x1400273c8  lea     rdx, [rbp+57h+var_60]
0x1400273cc  call    cs:__imp_imp_WppRecorderLogCreate
0x1400273d3  nop     dword ptr [rax+rax+00h]
0x1400273d8  test    eax, eax
0x1400273da  js      short loc_140027455
0x1400273dc  lea     rcx, [rbx+138h]; Context
0x1400273e3  mov     edx, 6Fh ; 'o'
0x1400273e8  call    ESM_AddEvent
0x1400273ed  xor     edi, edi
0x1400273ef  test    r12, r12
0x1400273f2  jz      short loc_14002742A
0x1400273f4  mov     rax, cs:WdfFunctions_01033
0x1400273fb  lea     rcx, aOnecoreDrivers_11; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140027402  mov     [rsp+0B0h+var_90], rcx
0x140027407  lea     r8, Endpoint_Enable
0x14002740e  mov     rcx, cs:WdfDriverGlobals
0x140027415  mov     r9d, 529h
0x14002741b  mov     rdx, r12
0x14002741e  mov     rax, [rax+670h]
0x140027425  call    _guard_dispatch_icall
0x14002742a  mov     eax, edi
0x14002742c  mov     rcx, [rbp+57h+var_28]
0x140027430  xor     rcx, rsp; StackCookie
0x140027433  call    __security_check_cookie
0x140027438  lea     r11, [rsp+0B0h+var_20]
0x140027440  mov     rbx, [r11+38h]
0x140027444  mov     rsi, [r11+40h]
0x140027448  mov     rsp, r11
0x14002744b  pop     r15
0x14002744d  pop     r14
0x14002744f  pop     r12
0x140027451  pop     rdi
0x140027452  pop     rbp
0x140027453  retn
0x140027455  mov     rax, [rbx]
0x140027458  mov     rcx, [rax+48h]
0x14002745c  mov     [rbx+50h], rcx
0x140027460  jmp     loc_1400273DC
0x140027465  mov     rax, [r14]
0x140027468  mov     r9d, 18h
0x14002746e  mov     r10, [rbx]
0x140027471  mov     r8d, esi
0x140027474  movzx   ecx, byte ptr [rax+8Fh]
0x14002747b  mov     rax, [rbx+18h]
0x14002747f  mov     [rsp+0B0h+var_78], rax
0x140027484  mov     eax, [rbx+98h]
0x14002748a  mov     [rsp+0B0h+var_80], eax
0x14002748e  mov     dword ptr [rsp+0B0h+var_88], ecx
0x140027492  mov     rcx, [r10+48h]
0x140027496  mov     [rsp+0B0h+var_90], rdx
0x14002749b  mov     dl, 4
0x14002749d  call    WPP_RECORDER_SF_ddq
0x1400274a2  jmp     loc_1400272D6
0x1400274a7  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400274ae  jnz     loc_14002776A
0x1400274b4  mov     dl, 1
0x1400274b6  mov     rcx, rbx
0x1400274b9  call    Endpoint_Disable_Internal
0x1400274be  jmp     loc_1400273EF
0x1400274c3  mov     rcx, [r14]
0x1400274c6  cmp     [rcx+24h], edi
0x1400274c9  jnz     loc_1400272F5
0x1400274cf  mov     eax, [rbx+80h]
0x1400274d5  sub     eax, 3
0x1400274d8  test    r8d, eax
0x1400274db  jnz     loc_1400272F5
0x1400274e1  mov     eax, [rcx+2Ch]
0x1400274e4  sub     eax, edi
0x1400274e6  imul    rdx, rax, 78h ; 'x'
0x1400274ea  mov     rax, [rcx+8]
0x1400274ee  mov     rcx, [rax+98h]
0x1400274f5  mov     rax, [rcx+30h]
0x1400274f9  cmp     byte ptr [rdx+rax+0Dh], 3
0x1400274fe  jnz     loc_1400272F5
0x140027504  lock add [rdx+rax+6Ch], edi
0x140027509  jmp     loc_1400272F5
0x14002750e  test    r12, r12
0x140027511  jz      loc_14002760C
0x140027517  mov     rax, cs:WdfFunctions_01033
0x14002751e  mov     rdx, r12
0x140027521  mov     r8, cs:off_14006C220
0x140027528  mov     rcx, cs:WdfDriverGlobals
0x14002752f  mov     rax, [rax+650h]
0x140027536  call    _guard_dispatch_icall
0x14002753b  mov     [rbx+90h], rax
0x140027542  mov     r15, rax
0x140027545  cmp     qword ptr [rax+20h], 0
0x14002754a  jz      loc_1400276EE
0x140027550  mov     esi, edi
0x140027552  cmp     esi, [r15+8]
0x140027556  ja      short loc_1400275A0
0x140027558  lea     ecx, [rsi-1]
0x14002755b  imul    rax, rcx, 68h ; 'h'
0x14002755f  mov     rcx, [rbx+90h]
0x140027566  mov     rcx, [rax+rcx+30h]
0x14002756b  call    TR_Enable_Internal
0x140027570  mov     edi, eax
0x140027572  test    eax, eax
0x140027574  js      loc_14002770A
0x14002757a  mov     edx, esi
0x14002757c  mov     rcx, rbx
0x14002757f  call    Endpoint_GetDequeuePointer
0x140027584  mov     rcx, [rbx+90h]
0x14002758b  mov     edx, esi
0x14002758d  add     rdx, rdx
0x140027590  inc     esi
0x140027592  mov     rcx, [rcx+20h]
0x140027596  mov     rcx, [rcx+10h]
0x14002759a  mov     [rcx+rdx*8], rax
0x14002759e  jmp     short loc_140027552
0x1400275a0  mov     rcx, r15
0x1400275a3  call    XilEndpoint_CommitStreamContextArrayUpdates
0x1400275a8  mov     edi, eax
0x1400275aa  test    eax, eax
0x1400275ac  js      loc_1400274B4
0x1400275b2  jmp     loc_140027347
0x1400275b7  cmp     byte ptr [rbx+26h], 0
0x1400275bb  jnz     loc_140027309
0x1400275c1  mov     [rbx+26h], dil
0x1400275c5  mov     eax, edi
0x1400275c7  lock xadd [rcx+450h], eax
0x1400275cf  add     eax, edi
0x1400275d1  cmp     eax, edi
0x1400275d3  jnz     loc_140027309
0x1400275d9  call    Controller_SetHSIIWorkaround
0x1400275de  jmp     loc_140027309
0x1400275e3  mov     rax, [r14]
0x1400275e6  cmp     [rax+24h], edi
0x1400275e9  jbe     loc_140027309
0x1400275ef  cmp     [rax+14h], edi
0x1400275f2  ja      loc_140027309
0x1400275f8  mov     eax, [rbx+80h]
0x1400275fe  sub     eax, 3
0x140027601  test    r8d, eax
0x140027604  jnz     loc_140027309
0x14002760a  jmp     short loc_1400275B7
0x14002760c  mov     rsi, [rbx+88h]
0x140027613  test    rsi, rsi
0x140027616  jnz     short loc_14002767C
0x140027618  mov     edx, 98h
0x14002761d  lea     ecx, [rsi+40h]
0x140027620  mov     r8d, 49434858h
0x140027626  call    cs:__imp_ExAllocatePool2
0x14002762d  nop     dword ptr [rax+rax+00h]
0x140027632  mov     [rbx+88h], rax
0x140027639  mov     rsi, rax
0x14002763c  test    rax, rax
0x14002763f  jnz     short loc_14002764B
0x140027641  mov     edi, 0C000009Ah
0x140027646  jmp     loc_1400274B4
0x14002764b  mov     [rbx+90h], rsi
0x140027652  mov     [rax], rbx
0x140027655  mov     [rax+8], edi
0x140027658  mov     [rax+0Ch], edi
0x14002765b  mov     rcx, [rbx+90h]
0x140027662  mov     rax, [rbx+58h]
0x140027666  mov     [rcx+30h], rax
0x14002766a  mov     rcx, rsi
0x14002766d  call    XilEndpoint_AllocateStreamContextArray
0x140027672  mov     edi, eax
0x140027674  test    eax, eax
0x140027676  js      loc_1400274B4
0x14002767c  mov     rcx, [rbx+58h]
0x140027680  call    TR_Enable_Internal
0x140027685  mov     edi, eax
0x140027687  test    eax, eax
0x140027689  jns     short loc_1400276CA
0x14002768b  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140027692  jz      loc_1400274B4
0x140027698  mov     rax, [r14]
0x14002769b  mov     r9d, 19h
0x1400276a1  mov     r10, [rbx]
0x1400276a4  mov     dword ptr [rsp+0B0h+var_78], edi
0x1400276a8  movzx   ecx, byte ptr [rax+8Fh]
0x1400276af  lea     r8d, [r9-0Ch]
0x1400276b3  mov     eax, [rbx+98h]
0x1400276b9  mov     [rsp+0B0h+var_80], eax
0x1400276bd  mov     dword ptr [rsp+0B0h+var_88], ecx
0x1400276c1  mov     rcx, [r10+48h]
0x1400276c5  jmp     loc_140027798
0x1400276ca  mov     rcx, [rbx+58h]
0x1400276ce  call    TR_GetDequeuePointer
0x1400276d3  mov     rcx, [rbx+90h]
0x1400276da  mov     rdx, [rcx+20h]
0x1400276de  mov     rcx, [rdx+10h]
0x1400276e2  mov     [rcx+10h], rax
0x1400276e6  mov     rcx, rsi
0x1400276e9  jmp     loc_1400275A3
0x1400276ee  mov     rcx, r15
0x1400276f1  call    XilEndpoint_AllocateStreamContextArray
0x1400276f6  mov     edi, eax
0x1400276f8  test    eax, eax
0x1400276fa  js      loc_1400274B4
0x140027700  mov     edi, 1
0x140027705  jmp     loc_140027550
0x14002770a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140027711  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027718  jz      loc_1400274B4
0x14002771e  mov     rax, [r14]
0x140027721  lea     ecx, [rsi+1]
0x140027724  mov     r10, [rbx]
0x140027727  mov     r9d, 1Ah
0x14002772d  mov     [rsp+0B0h+var_70], edi
0x140027731  mov     dword ptr [rsp+0B0h+var_78], ecx
0x140027735  movzx   edx, byte ptr [rax+8Fh]
0x14002773c  mov     eax, [rbx+98h]
0x140027742  lea     r8d, [r9-0Dh]
0x140027746  mov     rcx, [r10+48h]
0x14002774a  mov     [rsp+0B0h+var_80], eax
0x14002774e  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140027755  mov     dword ptr [rsp+0B0h+var_88], edx
0x140027759  mov     dl, 2
0x14002775b  mov     [rsp+0B0h+var_90], rax
0x140027760  call    WPP_RECORDER_SF_dddd
0x140027765  jmp     loc_1400274B4
0x14002776a  mov     rax, [r14]
0x14002776d  mov     r9d, 1Bh
0x140027773  mov     rcx, [rbx]
0x140027776  mov     dword ptr [rsp+0B0h+var_78], edi
0x14002777a  movzx   r8d, byte ptr [rax+8Fh]
0x140027782  mov     eax, [rbx+98h]
0x140027788  mov     rcx, [rcx+48h]
0x14002778c  mov     [rsp+0B0h+var_80], eax
0x140027790  mov     dword ptr [rsp+0B0h+var_88], r8d
0x140027795  mov     r8d, esi
0x140027798  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x14002779f  mov     dl, 2
0x1400277a1  mov     [rsp+0B0h+var_90], rax
  ... truncated ...
```
