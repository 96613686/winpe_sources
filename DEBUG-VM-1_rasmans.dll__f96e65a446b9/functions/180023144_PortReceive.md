# PortReceive

- ea: `0x180023144`
- end: `0x18002371b`
- name: `PortReceive`
- size: `1495`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023730`
- `0x1800279a0`

## callees

- `0x180005c6c`
- `0x180005d18`
- `0x180005e0c`
- `0x180005e34`
- `0x180005f1c`
- `0x18000bfb0`
- `0x1800146e8`
- `0x180023144`
- `0x18002a0a0`
- `0x18003705c`
- `0x180047668`
- `0x180047714`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023218`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800233ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023218`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800233ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023245`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800235b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800235b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023230`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023230`

## pseudocode

```c
double __fastcall PortReceive(__int64 a1, _DWORD *a2, DWORD *a3, int a4)
{
  DWORD *v5; // r14
  struct _LIST_ENTRY *v8; // rcx
  double result; // xmm0_8
  DWORD v10; // esi
  DWORD LastError; // edi
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  char *v15; // rax
  char *v16; // rbp
  unsigned __int16 v17; // r12
  DWORD v18; // eax
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  struct _LIST_ENTRY *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r9
  char *v25; // rsi
  int v26; // ecx
  struct _LIST_ENTRY *v27; // rcx
  __int64 v28; // r8

  v5 = a3;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 398, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a2 && *a2 )
    v10 = a2[2];
  else
    v10 = v5[4];
  if ( !a1 )
  {
    if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v8[1].Blink) & 0x2000) != 0
      && BYTE1(v8[1].Blink) >= 2u )
    {
      result = WPP_SF_(v8[1].Flink, 400, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      goto LABEL_95;
    }
LABEL_96:
    LastError = 618;
    if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v8[1].Blink) & 0x2000) != 0
      && BYTE1(v8[1].Blink) >= 2u )
    {
      result = WPP_SF_(v8[1].Flink, 401, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    }
    goto LABEL_100;
  }
  if ( *(_DWORD *)(a1 + 24) == 2 )
  {
    if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v8[1].Blink) & 0x2000) != 0
      && BYTE1(v8[1].Blink) >= 2u )
    {
      WPP_SF_q(v8[1].Flink, 399, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *(_QWORD *)a1);
LABEL_95:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_96;
    }
    goto LABEL_96;
  }
  if ( *(_DWORD *)(a1 + 24) )
  {
    LastError = 618;
    goto LABEL_100;
  }
  if ( *(_DWORD *)(a1 + 472) && *(_DWORD *)(a1 + 28) != 2
    || (v12 = *(_DWORD *)(a1 + 1224), (v12 & 2) != 0)
    || !a4 && (v12 & 4) != 0 )
  {
    if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v8[1].Blink) & 0x2000) != 0
      && BYTE1(v8[1].Blink) >= 4u )
    {
      WPP_SF_s(v8[1].Flink, 402, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a1 + 8);
    }
    LastError = 616;
  }
  else
  {
    if ( v10 == GetCurrentProcessId() || a4 )
    {
      v16 = (char *)*((_QWORD *)v5 + 3);
      if ( !a4 )
        *(_DWORD *)(a1 + 1224) = 0;
    }
    else
    {
      v15 = (char *)LocalAlloc(0x40u, 0x608u);
      *(_QWORD *)(a1 + 528) = v15;
      v16 = v15;
      if ( !v15 )
      {
        LastError = GetLastError();
        goto LABEL_100;
      }
      *(_DWORD *)(a1 + 1224) = 1;
    }
    if ( *(_DWORD *)(a1 + 28) == 2 )
    {
      v17 = 26;
      v18 = CompleteReceiveIfPending(a1, v16, 7);
    }
    else
    {
      if ( *(_DWORD *)(a1 + 28) == 4 )
      {
        SetPortConnState(v14, v13, a1, 0);
        LastError = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 48) + 136LL))(*(_QWORD *)(a1 + 216));
        if ( LastError )
          goto LABEL_100;
      }
      if ( v5[1] != -1 )
      {
        v19 = 1000LL * v5[1];
        if ( v19 > 0xFFFFFFFF )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            result = WPP_SF_d(
                       WPP_GLOBAL_Control[1].Flink,
                       403,
                       WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                       2147942934LL);
          }
          goto LABEL_56;
        }
        v5[1] = v19;
      }
      v20 = *(_QWORD *)(a1 + 48);
      v21 = *(_QWORD *)(a1 + 216);
      v17 = 7;
      *(_DWORD *)(a1 + 536) = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, _QWORD))(v20 + 128))(v21, v16 + 32, *v5, v5[1]);
    }
    LastError = v18;
    if ( v18 == 997 )
      LastError = 600;
    *(_DWORD *)(a1 + 264) = LastError;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      result = WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 404, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, LastError);
      v22 = WPP_GLOBAL_Control;
    }
    if ( LastError )
    {
      if ( LastError != 600 )
        goto LABEL_100;
      if ( v22 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v22[1].Blink) & 0x2000) != 0
        && BYTE1(v22[1].Blink) >= 5u )
      {
        result = WPP_SF_(v22[1].Flink, 405, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
      v23 = ValidateHandleForRasman(*((HANDLE *)v5 + 1), v10);
      *(_QWORD *)(a1 + 464) = v23;
      if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        SetPortAsyncReqType("onecoreuap\\net\\rras\\ras\\rasman\\rasman\\request.c", 6237, a1, v17);
        if ( !a4 && v10 == GetCurrentProcessId() )
          *(_QWORD *)(a1 + 528) = v16;
        if ( v17 == 26 )
        {
          v24 = v5[1];
          if ( (unsigned int)(v24 - 1) <= 0xFFFFFFFD )
            *(_QWORD *)(a1 + 480) = AddTimeoutElement(HubReceiveTimeout, a1, 0, v24);
        }
        goto LABEL_100;
      }
LABEL_56:
      LastError = -2147024809;
      goto LABEL_100;
    }
    if ( v22 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v22[1].Blink) & 0x2000) != 0
      && BYTE1(v22[1].Blink) >= 5u )
    {
      result = WPP_SF_(v22[1].Flink, 406, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    }
    if ( v17 == 7 )
      *(_DWORD *)(a1 + 536) = 0;
    v25 = (char *)ValidateHandleForRasman(*((HANDLE *)v5 + 1), v10);
    if ( (unsigned __int64)(v25 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_56;
    v26 = *(_DWORD *)(a1 + 1224);
    if ( (v26 & 1) != 0 )
    {
      *(_DWORD *)(a1 + 1224) = v26 | 2;
      *(_QWORD *)(a1 + 480) = AddTimeoutElement(OutOfProcessReceiveTimeout, a1, 0, 15000);
    }
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 407, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a1 + 8);
      v27 = WPP_GLOBAL_Control;
    }
    if ( (*(_BYTE *)(a1 + 1224) & 4) != 0 )
    {
      while ( 1 )
      {
        if ( v27 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v27[1].Blink) & 0x2000) != 0
          && BYTE1(v27[1].Blink) >= 4u )
        {
          WPP_SF_s(v27[1].Flink, 408, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a1 + 8);
        }
        SendReceivedPacketToProtocolEngine(a1, v16 + 8);
        LastError = CompleteReceiveIfPending(a1, v16, v28);
        if ( LastError )
          break;
        v27 = WPP_GLOBAL_Control;
      }
      v5 = a3;
    }
    SetEvent(v25);
    if ( !a4 )
    {
      if ( (*(_DWORD *)(a1 + 1224) & 1) != 0 )
      {
        SetPortAsyncReqType("onecoreuap\\net\\rras\\ras\\rasman\\rasman\\request.c", 6315, a1, v17);
        *(_QWORD *)(a1 + 464) = v25;
      }
      else
      {
        FreeNotifierHandle(v25);
      }
    }
  }
LABEL_100:
  *v5 = LastError;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    return WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 409, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, LastError);
  }
  return result;
}

```

## disassembly

```asm
0x180023144  mov     [rsp+arg_10], r8
0x180023149  push    rbx
0x18002314a  push    rbp
0x18002314b  push    rsi
0x18002314c  push    rdi
0x18002314d  push    r12
0x18002314f  push    r13
0x180023151  push    r14
0x180023153  push    r15
0x180023155  sub     rsp, 38h
0x180023159  mov     r13d, r9d
0x18002315c  mov     r14, r8
0x18002315f  mov     rdi, rdx
0x180023162  mov     rbx, rcx
0x180023165  mov     rcx, cs:WPP_GLOBAL_Control
0x18002316c  lea     rdx, WPP_GLOBAL_Control
0x180023173  cmp     rcx, rdx
0x180023176  jz      short loc_1800231AA
0x180023178  test    dword ptr [rcx+1Ch], 2000h
0x18002317f  jz      short loc_1800231AA
0x180023181  cmp     byte ptr [rcx+19h], 6
0x180023185  jb      short loc_1800231AA
0x180023187  mov     rcx, [rcx+10h]
0x18002318b  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180023192  mov     edx, 18Eh
0x180023197  call    WPP_SF_
0x18002319c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231a3  lea     rdx, WPP_GLOBAL_Control
0x1800231aa  xor     r15d, r15d
0x1800231ad  test    rdi, rdi
0x1800231b0  jz      short loc_1800231BC
0x1800231b2  cmp     [rdi], r15d
0x1800231b5  jz      short loc_1800231BC
0x1800231b7  mov     esi, [rdi+8]
0x1800231ba  jmp     short loc_1800231C0
0x1800231bc  mov     esi, [r14+10h]
0x1800231c0  mov     r12d, 2
0x1800231c6  test    rbx, rbx
0x1800231c9  jz      loc_180023668
0x1800231cf  cmp     [rbx+18h], r12d
0x1800231d3  jz      loc_18002363A
0x1800231d9  cmp     [rbx+18h], r15d
0x1800231dd  jz      short loc_1800231E9
0x1800231df  mov     edi, 26Ah
0x1800231e4  jmp     loc_1800236CD
0x1800231e9  cmp     [rbx+1D8h], r15d
0x1800231f0  jz      short loc_1800231FC
0x1800231f2  cmp     [rbx+1Ch], r12d
0x1800231f6  jnz     loc_180023603
0x1800231fc  mov     eax, [rbx+4C8h]
0x180023202  test    r12b, al
0x180023205  jnz     loc_180023603
0x18002320b  test    r13d, r13d
0x18002320e  jnz     short loc_180023218
0x180023210  test    al, 4
0x180023212  jnz     loc_180023603
0x180023218  call    cs:__imp_GetCurrentProcessId
0x18002321e  cmp     esi, eax
0x180023220  jz      short loc_18002325E
0x180023222  test    r13d, r13d
0x180023225  jnz     short loc_18002325E
0x180023227  mov     edx, 608h; uBytes
0x18002322c  lea     ecx, [r13+40h]; uFlags
0x180023230  call    cs:__imp_LocalAlloc
0x180023236  mov     [rbx+210h], rax
0x18002323d  mov     rbp, rax
0x180023240  test    rax, rax
0x180023243  jnz     short loc_180023252
0x180023245  call    cs:__imp_GetLastError
0x18002324b  mov     edi, eax
0x18002324d  jmp     loc_1800236CD
0x180023252  mov     dword ptr [rbx+4C8h], 1
0x18002325c  jmp     short loc_18002326E
0x18002325e  mov     rbp, [r14+18h]
0x180023262  test    r13d, r13d
0x180023265  jnz     short loc_18002326E
0x180023267  mov     [rbx+4C8h], r15d
0x18002326e  mov     eax, 1Ah
0x180023273  lea     r8d, [rax-13h]
0x180023277  cmp     [rbx+1Ch], r12d
0x18002327b  jnz     short loc_180023291
0x18002327d  mov     rdx, rbp
0x180023280  mov     rcx, rbx
0x180023283  movzx   r12d, ax
0x180023287  call    CompleteReceiveIfPending
0x18002328c  jmp     loc_180023316
0x180023291  cmp     dword ptr [rbx+1Ch], 4
0x180023295  jnz     short loc_1800232C7
0x180023297  xor     r9d, r9d
0x18002329a  mov     r8, rbx
0x18002329d  call    SetPortConnState
0x1800232a2  mov     rax, [rbx+30h]
0x1800232a6  mov     rcx, [rbx+0D8h]
0x1800232ad  mov     rax, [rax+88h]
0x1800232b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232b9  mov     edi, eax
0x1800232bb  test    eax, eax
0x1800232bd  jnz     loc_1800236CD
0x1800232c3  lea     r8d, [rax+7]
0x1800232c7  mov     edx, 0FFFFFFFFh
0x1800232cc  cmp     [r14+4], edx
0x1800232d0  jz      short loc_1800232EA
0x1800232d2  mov     eax, [r14+4]
0x1800232d6  imul    rcx, rax, 3E8h
0x1800232dd  cmp     rcx, rdx
0x1800232e0  ja      loc_18002343C
0x1800232e6  mov     [r14+4], ecx
0x1800232ea  mov     rax, [rbx+30h]
0x1800232ee  lea     rdx, [rbp+20h]
0x1800232f2  mov     rcx, [rbx+0D8h]
0x1800232f9  mov     r12d, r8d
0x1800232fc  mov     [rbx+218h], r15d
0x180023303  mov     r9d, [r14+4]
0x180023307  mov     rax, [rax+80h]
0x18002330e  mov     r8d, [r14]
0x180023311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023316  cmp     eax, 3E5h
0x18002331b  mov     edi, eax
0x18002331d  mov     edx, 258h
0x180023322  cmovz   edi, edx
0x180023325  mov     [rbx+108h], edi
0x18002332b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023332  lea     rax, WPP_GLOBAL_Control
0x180023339  cmp     rcx, rax
0x18002333c  jz      short loc_180023378
0x18002333e  test    dword ptr [rcx+1Ch], 2000h
0x180023345  jz      short loc_180023378
0x180023347  cmp     byte ptr [rcx+19h], 5
0x18002334b  jb      short loc_180023378
0x18002334d  mov     rcx, [rcx+10h]
0x180023351  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180023358  mov     edx, 194h
0x18002335d  mov     r9d, edi
0x180023360  call    WPP_SF_d
0x180023365  mov     rcx, cs:WPP_GLOBAL_Control
0x18002336c  lea     rax, WPP_GLOBAL_Control
0x180023373  mov     edx, 258h
0x180023378  test    edi, edi
0x18002337a  jz      loc_180023483
0x180023380  cmp     edi, edx
0x180023382  jnz     loc_1800236CD
0x180023388  cmp     rcx, rax
0x18002338b  jz      short loc_1800233B1
0x18002338d  test    dword ptr [rcx+1Ch], 2000h
0x180023394  jz      short loc_1800233B1
0x180023396  cmp     byte ptr [rcx+19h], 5
0x18002339a  jb      short loc_1800233B1
0x18002339c  mov     rcx, [rcx+10h]
0x1800233a0  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800233a7  mov     edx, 195h
0x1800233ac  call    WPP_SF_
0x1800233b1  mov     rcx, [r14+8]; hSourceHandle
0x1800233b5  mov     edx, esi; dwProcessId
0x1800233b7  call    ValidateHandleForRasman
0x1800233bc  mov     [rbx+1D0h], rax
0x1800233c3  dec     rax
0x1800233c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800233ca  ja      loc_180023479
0x1800233d0  movzx   r9d, r12w
0x1800233d4  lea     rcx, aOnecoreuapNetR_2; "onecoreuap\\net\\rras\\ras\\rasman\\ras"...
0x1800233db  mov     r8, rbx
0x1800233de  mov     edx, 185Dh
0x1800233e3  call    SetPortAsyncReqType
0x1800233e8  test    r13d, r13d
0x1800233eb  jnz     short loc_1800233FE
0x1800233ed  call    cs:__imp_GetCurrentProcessId
0x1800233f3  cmp     esi, eax
0x1800233f5  jnz     short loc_1800233FE
0x1800233f7  mov     [rbx+210h], rbp
0x1800233fe  mov     eax, 1Ah
0x180023403  cmp     r12w, ax
0x180023407  jnz     loc_1800236CD
0x18002340d  mov     r9d, [r14+4]
0x180023411  lea     eax, [r9-1]
0x180023415  cmp     eax, 0FFFFFFFDh
0x180023418  ja      loc_1800236CD
0x18002341e  xor     r8d, r8d
0x180023421  lea     rcx, HubReceiveTimeout
0x180023428  mov     rdx, rbx
0x18002342b  call    AddTimeoutElement
0x180023430  mov     [rbx+1E0h], rax
0x180023437  jmp     loc_1800236CD
0x18002343c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023443  lea     rax, WPP_GLOBAL_Control
0x18002344a  cmp     rcx, rax
0x18002344d  jz      short loc_180023479
0x18002344f  test    dword ptr [rcx+1Ch], 2000h
0x180023456  jz      short loc_180023479
0x180023458  cmp     [rcx+19h], r12b
0x18002345c  jb      short loc_180023479
0x18002345e  mov     rcx, [rcx+10h]
0x180023462  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180023469  mov     edx, 193h
0x18002346e  mov     r9d, 80070216h
0x180023474  call    WPP_SF_d
0x180023479  mov     edi, 80070057h
0x18002347e  jmp     loc_1800236CD
0x180023483  cmp     rcx, rax
0x180023486  jz      short loc_1800234AC
0x180023488  test    dword ptr [rcx+1Ch], 2000h
0x18002348f  jz      short loc_1800234AC
0x180023491  cmp     byte ptr [rcx+19h], 5
0x180023495  jb      short loc_1800234AC
0x180023497  mov     rcx, [rcx+10h]
0x18002349b  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800234a2  mov     edx, 196h
0x1800234a7  call    WPP_SF_
0x1800234ac  mov     eax, 7
0x1800234b1  cmp     r12w, ax
0x1800234b5  jnz     short loc_1800234BE
0x1800234b7  mov     [rbx+218h], r15d
0x1800234be  mov     rcx, [r14+8]; hSourceHandle
0x1800234c2  mov     edx, esi; dwProcessId
0x1800234c4  call    ValidateHandleForRasman
0x1800234c9  mov     rsi, rax
0x1800234cc  lea     rcx, [rax-1]
0x1800234d0  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800234d4  ja      short loc_180023479
0x1800234d6  mov     ecx, [rbx+4C8h]
0x1800234dc  test    cl, 1
0x1800234df  jz      short loc_180023509
0x1800234e1  or      ecx, 2
0x1800234e4  mov     r9d, 3A98h
0x1800234ea  mov     [rbx+4C8h], ecx
0x1800234f0  xor     r8d, r8d
0x1800234f3  lea     rcx, OutOfProcessReceiveTimeout
0x1800234fa  mov     rdx, rbx
0x1800234fd  call    AddTimeoutElement
0x180023502  mov     [rbx+1E0h], rax
0x180023509  mov     rcx, cs:WPP_GLOBAL_Control
0x180023510  lea     rax, WPP_GLOBAL_Control
0x180023517  cmp     rcx, rax
0x18002351a  jz      short loc_18002354B
0x18002351c  test    dword ptr [rcx+1Ch], 2000h
0x180023523  jz      short loc_18002354B
0x180023525  cmp     byte ptr [rcx+19h], 4
0x180023529  jb      short loc_18002354B
0x18002352b  mov     rcx, [rcx+10h]
0x18002352f  lea     r9, [rbx+8]
0x180023533  mov     edx, 197h
0x180023538  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002353f  call    WPP_SF_s
0x180023544  mov     rcx, cs:WPP_GLOBAL_Control
0x18002354b  test    byte ptr [rbx+4C8h], 4
0x180023552  jz      short loc_1800235B6
0x180023554  lea     r14, WPP_GLOBAL_Control
0x18002355b  cmp     rcx, r14
0x18002355e  jz      short loc_180023588
0x180023560  test    dword ptr [rcx+1Ch], 2000h
0x180023567  jz      short loc_180023588
0x180023569  cmp     byte ptr [rcx+19h], 4
0x18002356d  jb      short loc_180023588
0x18002356f  mov     rcx, [rcx+10h]
0x180023573  lea     r9, [rbx+8]
0x180023577  mov     edx, 198h
0x18002357c  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180023583  call    WPP_SF_s
0x180023588  lea     rdx, [rbp+8]
0x18002358c  mov     rcx, rbx
0x18002358f  call    SendReceivedPacketToProtocolEngine
0x180023594  mov     rdx, rbp
0x180023597  mov     rcx, rbx
0x18002359a  call    CompleteReceiveIfPending
0x18002359f  mov     edi, eax
0x1800235a1  test    eax, eax
0x1800235a3  jnz     short loc_1800235AE
0x1800235a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235ac  jmp     short loc_18002355B
0x1800235ae  mov     r14, [rsp+78h+arg_10]
0x1800235b6  mov     rcx, rsi; hEvent
0x1800235b9  call    cs:__imp_SetEvent
0x1800235bf  test    r13d, r13d
0x1800235c2  jnz     loc_1800236CD
0x1800235c8  mov     eax, [rbx+4C8h]
0x1800235ce  test    al, 1
0x1800235d0  jnz     short loc_1800235DF
0x1800235d2  mov     rcx, rsi; hObject
0x1800235d5  call    FreeNotifierHandle
0x1800235da  jmp     loc_1800236CD
0x1800235df  movzx   r9d, r12w
0x1800235e3  lea     rcx, aOnecoreuapNetR_2; "onecoreuap\\net\\rras\\ras\\rasman\\ras"...
0x1800235ea  mov     r8, rbx
0x1800235ed  mov     edx, 18ABh
0x1800235f2  call    SetPortAsyncReqType
0x1800235f7  mov     [rbx+1D0h], rsi
0x1800235fe  jmp     loc_1800236CD
0x180023603  cmp     rcx, rdx
0x180023606  jz      short loc_180023630
0x180023608  test    dword ptr [rcx+1Ch], 2000h
0x18002360f  jz      short loc_180023630
0x180023611  cmp     byte ptr [rcx+19h], 4
0x180023615  jb      short loc_180023630
0x180023617  mov     rcx, [rcx+10h]
0x18002361b  lea     r9, [rbx+8]
0x18002361f  mov     edx, 192h
0x180023624  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002362b  call    WPP_SF_s
0x180023630  mov     edi, 268h
0x180023635  jmp     loc_1800236CD
0x18002363a  cmp     rcx, rdx
  ... truncated ...
```
