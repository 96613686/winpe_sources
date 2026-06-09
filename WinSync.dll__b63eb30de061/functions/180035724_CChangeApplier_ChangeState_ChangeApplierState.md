# CChangeApplier::ChangeState(ChangeApplierState)

- ea: `0x180035724`
- end: `0x180035a74`
- name: `?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z`
- size: `848`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `25`
- callee_count: `4`
- tags: ``

## callers

- `0x180022b44`
- `0x180031c9c`
- `0x1800347e0`
- `0x180034e84`
- `0x180034f40`
- `0x180035600`
- `0x180038250`
- `0x1800383f4`
- `0x180039f60`
- `0x18003a64c`
- `0x18003c750`
- `0x18003cb34`
- `0x18003e1e8`
- `0x18003ea50`
- `0x180041238`
- `0x180041f28`
- `0x1800428f0`
- `0x180042df4`
- `0x180043374`
- `0x180043ac0`
- `0x180044c80`
- `0x180045260`
- `0x180045580`
- `0x180045df0`
- `0x180046160`

## callees

- `0x18001ae20`
- `0x18003187c`
- `0x180035724`
- `0x180040a00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800359c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800359c1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035975`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035a1c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035975`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035a1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035794`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800359ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035a0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035794`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800359ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035a0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800359fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035a25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800359fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035a25`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800359f3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800359f3`

## pseudocode

```c
__int64 __fastcall CChangeApplier::ChangeState(__int64 a1, int a2)
{
  int v5; // r14d
  __int64 v6; // rcx
  signed int v7; // ebx
  int v8; // edx
  unsigned int v9; // ecx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // eax
  bool v15; // zf
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  bool v20; // zf
  int v21; // edx
  int v22; // edx
  int v23; // edx
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      87,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      *(unsigned int *)(a1 + 336),
      a2);
  }
  if ( *(_DWORD *)(a1 + 336) == 23 )
    return 2147500036LL;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  v5 = 0;
  if ( (unsigned int)CChangeApplier::IsOutboundCallState(*(unsigned int *)(a1 + 336), *(unsigned int *)(a1 + 336)) )
    --*(_DWORD *)(a1 + 360);
  if ( (unsigned int)(v6 - 20) <= 1 && a2 != 20 )
  {
LABEL_11:
    v7 = -2147467260;
    goto LABEL_84;
  }
  if ( (unsigned int)CChangeApplier::IsOutboundCallState(v6, (unsigned int)a2) && a2 != 20 && a2 != 23 )
    ++*(_DWORD *)(a1 + 360);
  v7 = -2147217379;
  if ( a2 > 14 )
  {
    if ( a2 > 20 )
    {
      v25 = v8 - 22;
      if ( !v25 )
      {
        v7 = *(_DWORD *)(a1 + 280);
        *(_DWORD *)(a1 + 336) = 22;
LABEL_74:
        if ( v7 < 0 )
          goto LABEL_84;
LABEL_75:
        *(_DWORD *)(a1 + 336) = a2;
        if ( a2 == 20 || a2 == 23 )
        {
          v5 = 1;
          goto LABEL_84;
        }
        goto LABEL_77;
      }
      v26 = v25 - 1;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( !v27 )
        {
LABEL_38:
          v9 -= 8;
          goto LABEL_30;
        }
        if ( v27 != 1 )
          goto LABEL_84;
        v20 = v9 == 24;
        goto LABEL_68;
      }
    }
    else if ( a2 != 20 )
    {
      v21 = v8 - 15;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( !v22 )
        {
          v9 -= 15;
          goto LABEL_30;
        }
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            if ( v24 != 1 )
              goto LABEL_84;
            v9 -= 18;
            goto LABEL_30;
          }
          if ( v9 > 0x19 )
            goto LABEL_84;
          v14 = 33706305;
        }
        else
        {
          if ( v9 > 0x19 )
            goto LABEL_84;
          v14 = 33640800;
        }
      }
      else
      {
        if ( v9 > 0x19 )
          goto LABEL_84;
        v14 = 50362816;
      }
      goto LABEL_61;
    }
    v7 = 0;
    SetEvent(*(HANDLE *)(a1 + 344));
    goto LABEL_75;
  }
  if ( a2 == 14 )
  {
    v9 -= 13;
    goto LABEL_30;
  }
  if ( a2 > 6 )
  {
    v16 = v8 - 7;
    if ( !v16 )
    {
      if ( v9 > 0x19 )
        goto LABEL_84;
      v14 = 34230593;
      goto LABEL_61;
    }
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 3;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          if ( v19 != 1 )
            goto LABEL_84;
          goto LABEL_38;
        }
        v15 = ((v9 - 11) & 0xFFFFFFF7) == 0;
LABEL_70:
        if ( !v15 )
          goto LABEL_84;
        goto LABEL_71;
      }
      if ( v9 > 0x19 )
        goto LABEL_84;
      v14 = 33571072;
LABEL_61:
      if ( !_bittest(&v14, v9) )
        goto LABEL_84;
      goto LABEL_71;
    }
    v20 = v9 == 7;
LABEL_68:
    if ( v20 )
    {
LABEL_71:
      v7 = 0;
      *(_DWORD *)(a1 + 336) = a2;
LABEL_77:
      if ( !*(_DWORD *)(a1 + 680) )
        goto LABEL_84;
      goto LABEL_11;
    }
    v15 = v9 == 19;
    goto LABEL_70;
  }
  if ( a2 == 6 )
  {
    if ( v9 > 0x19 )
      goto LABEL_84;
    v14 = 34099552;
    goto LABEL_61;
  }
  v10 = v8 - 1;
  if ( !v10 )
  {
LABEL_30:
    v7 = v9 != 0 ? 0x8004101D : 0;
    goto LABEL_74;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    --v9;
    goto LABEL_30;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v15 = ((v9 - 2) & 0xFFFFFFFD) == 0;
    goto LABEL_70;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v9 -= 3;
    goto LABEL_30;
  }
  if ( v13 == 1 && v9 <= 0x13 )
  {
    v14 = 655669;
    goto LABEL_61;
  }
LABEL_84:
  while ( 1 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    if ( !v5 )
      break;
    if ( WaitForSingleObject(*(HANDLE *)(a1 + 344), 0xFFFFFFFF) )
    {
      v7 = -2147217379;
      break;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    if ( *(int *)(a1 + 360) <= 0 )
    {
      v5 = 0;
      *(_DWORD *)(a1 + 336) = 21;
      v7 = 0;
    }
    ResetEvent(*(HANDLE *)(a1 + 344));
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  SetEvent(*(HANDLE *)(a1 + 344));
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::ChangeState",
      v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180035724  push    rbx
0x180035726  push    rbp
0x180035727  push    rsi
0x180035728  push    rdi
0x180035729  push    r12
0x18003572b  push    r13
0x18003572d  push    r14
0x18003572f  sub     rsp, 30h
0x180035733  mov     edi, edx
0x180035735  mov     rsi, rcx
0x180035738  mov     rcx, cs:WPP_GLOBAL_Control
0x18003573f  lea     r13, WPP_GLOBAL_Control
0x180035746  cmp     rcx, r13
0x180035749  jz      short loc_180035777
0x18003574b  test    byte ptr [rcx+1Ch], 8
0x18003574f  jz      short loc_180035777
0x180035751  cmp     byte ptr [rcx+19h], 5
0x180035755  jb      short loc_180035777
0x180035757  mov     r9d, [rsi+150h]
0x18003575e  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180035765  mov     rcx, [rcx+10h]
0x180035769  mov     edx, 57h ; 'W'
0x18003576e  mov     [rsp+68h+var_48], edi
0x180035772  call    WPP_SF_dd
0x180035777  cmp     dword ptr [rsi+150h], 17h
0x18003577e  jnz     short loc_18003578A
0x180035780  mov     eax, 80004004h
0x180035785  jmp     loc_180035A65
0x18003578a  lea     rbp, [rsi+120h]
0x180035791  mov     rcx, rbp; lpCriticalSection
0x180035794  call    cs:__imp_EnterCriticalSection
0x18003579a  mov     ecx, [rsi+150h]
0x1800357a0  xor     r14d, r14d
0x1800357a3  mov     edx, ecx
0x1800357a5  call    ?IsOutboundCallState@CChangeApplier@@AEAAHW4ChangeApplierState@@@Z; CChangeApplier::IsOutboundCallState(ChangeApplierState)
0x1800357aa  test    eax, eax
0x1800357ac  jz      short loc_1800357B4
0x1800357ae  dec     dword ptr [rsi+168h]
0x1800357b4  lea     eax, [rcx-14h]
0x1800357b7  mov     r12d, 8004101Dh
0x1800357bd  cmp     eax, 1
0x1800357c0  ja      short loc_1800357D1
0x1800357c2  cmp     edi, 14h
0x1800357c5  jz      short loc_1800357D1
0x1800357c7  mov     ebx, 80004004h
0x1800357cc  jmp     loc_1800359F9
0x1800357d1  mov     edx, edi
0x1800357d3  call    ?IsOutboundCallState@CChangeApplier@@AEAAHW4ChangeApplierState@@@Z; CChangeApplier::IsOutboundCallState(ChangeApplierState)
0x1800357d8  test    eax, eax
0x1800357da  jz      short loc_1800357EC
0x1800357dc  cmp     edi, 14h
0x1800357df  jz      short loc_1800357EC
0x1800357e1  cmp     edi, 17h
0x1800357e4  jz      short loc_1800357EC
0x1800357e6  inc     dword ptr [rsi+168h]
0x1800357ec  mov     ebx, r12d
0x1800357ef  cmp     edi, 0Eh
0x1800357f2  jg      loc_1800358C7
0x1800357f8  jz      loc_1800358C2
0x1800357fe  cmp     edi, 6
0x180035801  jg      short loc_180035868
0x180035803  jz      short loc_180035855
0x180035805  sub     edx, 1
0x180035808  jz      short loc_180035849
0x18003580a  sub     edx, 1
0x18003580d  jz      short loc_180035847
0x18003580f  sub     edx, 1
0x180035812  jz      short loc_18003583A
0x180035814  sub     edx, 1
0x180035817  jz      short loc_180035835
0x180035819  cmp     edx, 1
0x18003581c  jnz     loc_1800359F9
0x180035822  cmp     ecx, 13h
0x180035825  ja      loc_1800359F9
0x18003582b  mov     eax, 0A0135h
0x180035830  jmp     loc_18003592D
0x180035835  sub     ecx, 3
0x180035838  jmp     short loc_180035849
0x18003583a  lea     eax, [rcx-2]
0x18003583d  test    eax, 0FFFFFFFDh
0x180035842  jmp     loc_18003595C
0x180035847  dec     ecx
0x180035849  neg     ecx
0x18003584b  sbb     ebx, ebx
0x18003584d  and     ebx, r12d
0x180035850  jmp     loc_18003598D
0x180035855  cmp     ecx, 19h
0x180035858  ja      loc_1800359F9
0x18003585e  mov     eax, 2085160h
0x180035863  jmp     loc_18003592D
0x180035868  sub     edx, 7
0x18003586b  jz      short loc_1800358B2
0x18003586d  sub     edx, 1
0x180035870  jz      short loc_1800358AA
0x180035872  sub     edx, 3
0x180035875  jz      short loc_180035897
0x180035877  sub     edx, 1
0x18003587a  jz      short loc_18003588A
0x18003587c  cmp     edx, 1
0x18003587f  jnz     loc_1800359F9
0x180035885  sub     ecx, 8
0x180035888  jmp     short loc_180035849
0x18003588a  lea     eax, [rcx-0Bh]
0x18003588d  test    eax, 0FFFFFFF7h
0x180035892  jmp     loc_18003595C
0x180035897  cmp     ecx, 19h
0x18003589a  ja      loc_1800359F9
0x1800358a0  mov     eax, 2004100h
0x1800358a5  jmp     loc_18003592D
0x1800358aa  cmp     ecx, 7
0x1800358ad  jmp     loc_180035957
0x1800358b2  cmp     ecx, 19h
0x1800358b5  ja      loc_1800359F9
0x1800358bb  mov     eax, 20A5141h
0x1800358c0  jmp     short loc_18003592D
0x1800358c2  sub     ecx, 0Dh
0x1800358c5  jmp     short loc_180035849
0x1800358c7  cmp     edi, 14h
0x1800358ca  jg      short loc_180035938
0x1800358cc  jz      loc_18003596C
0x1800358d2  sub     edx, 0Fh
0x1800358d5  jz      short loc_18003591F
0x1800358d7  sub     edx, 1
0x1800358da  jz      short loc_180035917
0x1800358dc  sub     edx, 1
0x1800358df  jz      short loc_180035907
0x1800358e1  sub     edx, 1
0x1800358e4  jz      short loc_1800358F7
0x1800358e6  cmp     edx, 1
0x1800358e9  jnz     loc_1800359F9
0x1800358ef  sub     ecx, 12h
0x1800358f2  jmp     loc_180035849
0x1800358f7  cmp     ecx, 19h
0x1800358fa  ja      loc_1800359F9
0x180035900  mov     eax, 2025141h
0x180035905  jmp     short loc_18003592D
0x180035907  cmp     ecx, 19h
0x18003590a  ja      loc_1800359F9
0x180035910  mov     eax, 2015160h
0x180035915  jmp     short loc_18003592D
0x180035917  sub     ecx, 0Fh
0x18003591a  jmp     loc_180035849
0x18003591f  cmp     ecx, 19h
0x180035922  ja      loc_1800359F9
0x180035928  mov     eax, 30079C0h
0x18003592d  bt      eax, ecx
0x180035930  jnb     loc_1800359F9
0x180035936  jmp     short loc_180035962
0x180035938  sub     edx, 16h
0x18003593b  jz      short loc_18003597D
0x18003593d  sub     edx, 1
0x180035940  jz      short loc_18003596C
0x180035942  sub     edx, 1
0x180035945  jz      loc_180035885
0x18003594b  cmp     edx, 1
0x18003594e  jnz     loc_1800359F9
0x180035954  cmp     ecx, 18h
0x180035957  jz      short loc_180035962
0x180035959  cmp     ecx, 13h
0x18003595c  jnz     loc_1800359F9
0x180035962  xor     ebx, ebx
0x180035964  mov     [rsi+150h], edi
0x18003596a  jmp     short loc_1800359A1
0x18003596c  mov     rcx, [rsi+158h]; hEvent
0x180035973  xor     ebx, ebx
0x180035975  call    cs:__imp_SetEvent
0x18003597b  jmp     short loc_180035991
0x18003597d  mov     ebx, [rsi+118h]
0x180035983  mov     dword ptr [rsi+150h], 16h
0x18003598d  test    ebx, ebx
0x18003598f  js      short loc_1800359F9
0x180035991  mov     [rsi+150h], edi
0x180035997  cmp     edi, 14h
0x18003599a  jz      short loc_1800359AF
0x18003599c  cmp     edi, 17h
0x18003599f  jz      short loc_1800359AF
0x1800359a1  cmp     [rsi+2A8h], r14d
0x1800359a8  jz      short loc_1800359F9
0x1800359aa  jmp     loc_1800357C7
0x1800359af  mov     r14d, 1
0x1800359b5  jmp     short loc_1800359F9
0x1800359b7  mov     rcx, [rsi+158h]; hHandle
0x1800359be  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800359c1  call    cs:__imp_WaitForSingleObject
0x1800359c7  test    eax, eax
0x1800359c9  jnz     short loc_180035A09
0x1800359cb  mov     rcx, rbp; lpCriticalSection
0x1800359ce  call    cs:__imp_EnterCriticalSection
0x1800359d4  cmp     dword ptr [rsi+168h], 0
0x1800359db  jg      short loc_1800359EC
0x1800359dd  xor     r14d, r14d
0x1800359e0  mov     dword ptr [rsi+150h], 15h
0x1800359ea  xor     ebx, ebx
0x1800359ec  mov     rcx, [rsi+158h]; hEvent
0x1800359f3  call    cs:__imp_ResetEvent
0x1800359f9  mov     rcx, rbp; lpCriticalSection
0x1800359fc  call    cs:__imp_LeaveCriticalSection
0x180035a02  test    r14d, r14d
0x180035a05  jnz     short loc_1800359B7
0x180035a07  jmp     short loc_180035A0C
0x180035a09  mov     ebx, r12d
0x180035a0c  mov     rcx, rbp; lpCriticalSection
0x180035a0f  call    cs:__imp_EnterCriticalSection
0x180035a15  mov     rcx, [rsi+158h]; hEvent
0x180035a1c  call    cs:__imp_SetEvent
0x180035a22  mov     rcx, rbp; lpCriticalSection
0x180035a25  call    cs:__imp_LeaveCriticalSection
0x180035a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035a32  cmp     rcx, r13
0x180035a35  jz      short loc_180035A63
0x180035a37  test    byte ptr [rcx+1Ch], 8
0x180035a3b  jz      short loc_180035A63
0x180035a3d  cmp     byte ptr [rcx+19h], 5
0x180035a41  jb      short loc_180035A63
0x180035a43  mov     rcx, [rcx+10h]
0x180035a47  lea     r9, aCchangeapplier_70; "CChangeApplier::ChangeState"
0x180035a4e  mov     edx, 58h ; 'X'
0x180035a53  mov     [rsp+68h+var_48], ebx
0x180035a57  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180035a5e  call    WPP_SF_sD
0x180035a63  mov     eax, ebx
0x180035a65  add     rsp, 30h
0x180035a69  pop     r14
0x180035a6b  pop     r13
0x180035a6d  pop     r12
0x180035a6f  pop     rdi
0x180035a70  pop     rsi
0x180035a71  pop     rbp
0x180035a72  pop     rbx
0x180035a73  retn
```
