# SetStartedEventWhenSCardSubsytemIsStarted(_REDIRECTION_CONTEXT *)

- ea: `0x180006400`
- end: `0x180006885`
- name: `?SetStartedEventWhenSCardSubsytemIsStarted@@YAHPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `1157`
- prototype: `__int64 __fastcall(struct _REDIRECTION_CONTEXT *)`
- caller_count: `6`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x1800046a0`
- `0x180005de0`
- `0x180007940`
- `0x180007f40`
- `0x180021150`
- `0x180021960`

## callees

- `0x18000605c`
- `0x180006400`
- `0x180006890`
- `0x180006c80`
- `0x180007bc0`
- `0x180008d20`
- `0x1800093e4`
- `0x180010898`
- `0x180014d40`
- `0x1800150c0`
- `0x180016cd0`
- `0x18001991c`
- `0x1800239b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006418`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006432`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000648f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006418`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006432`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000648f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006452`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000661f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006628`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006452`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000661f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006628`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800064c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800064c7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800065a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800065a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800064d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800064d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180006616`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800066a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180006616`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800066a2`
- `ntdll!RtlDllShutdownInProgress` at `0x1800065ff`
- `ntdll!RtlDllShutdownInProgress` at `0x1800065ff`

## pseudocode

```c
__int64 __fastcall SetStartedEventWhenSCardSubsytemIsStarted(struct _REDIRECTION_CONTEXT *a1)
{
  int v1; // ebp
  unsigned int v3; // r15d
  char v4; // si
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  LPCRITICAL_SECTION v6; // rcx
  char v7; // di
  __int64 v8; // rcx
  int v9; // esi
  HANDLE v10; // rdi
  int v11; // r14d
  DWORD CurrentThreadId; // eax
  unsigned __int64 v13; // rdx
  char *v14; // rcx
  int v15; // r10d
  DWORD v16; // r9d
  int v17; // r8d
  unsigned int i; // eax
  bool v19; // zf
  int v20; // r9d
  HANDLE v21; // rdi
  int v23; // r9d
  __int64 v24; // rcx
  __int64 v25; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp+8h] BYREF

  v1 = 1;
  v3 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  v4 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)a1;
  v5 = (struct _RTL_CRITICAL_SECTION *)a1;
  if ( !a1 )
  {
    if ( (unsigned int)RedirectionContextLookup(&lpCriticalSection) )
    {
LABEL_48:
      WppTraceIndent(v8, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
          v23,
          *((_DWORD *)a1 + 18));
      }
      goto LABEL_41;
    }
    v5 = lpCriticalSection;
    v4 = 1;
  }
  EnterCriticalSection(v5);
  v6 = lpCriticalSection;
  if ( !lpCriticalSection[3].DebugInfo )
  {
    UpdateConnectionStateForContext(lpCriticalSection);
    v6 = lpCriticalSection;
  }
  v7 = BYTE2(v6[1].DebugInfo);
  LeaveCriticalSection(v6);
  if ( v4 )
    RedirectionContextRelease((struct _REDIRECTION_CONTEXT *)lpCriticalSection);
  if ( !v7 )
    goto LABEL_48;
  if ( !RedirectionContextIsLocal((LPCRITICAL_SECTION)a1) )
  {
    if ( RedirectDisabled() )
    {
      WppTraceIndent(v24, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
      }
      goto LABEL_41;
    }
    v9 = 0;
    v11 = 0;
    v10 = RedirectedSCardAccessStartedEvent(a1);
    if ( v10 )
      goto LABEL_13;
    WppTraceIndent(v25, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
    }
LABEL_63:
    v3 = 0;
    goto LABEL_41;
  }
  v9 = 0;
  if ( dword_180045A28 )
  {
    EnterCriticalSection(&stru_1800455F0);
    if ( !hObject )
      hObject = CreateSCEvent(0x19u);
    LeaveCriticalSection(&stru_1800455F0);
    v10 = hObject;
  }
  else
  {
    v10 = 0;
  }
  v11 = 1;
  if ( !v10 )
    goto LABEL_63;
LABEL_13:
  if ( !WaitForSingleObject(v10, 0) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v15 = `WppTraceIndent'::`2'::idxCurrentThread;
    v16 = CurrentThreadId;
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
    {
      v15 = 0;
      `WppTraceIndent'::`2'::idxCurrentThread = 0;
      LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
      dword_180045874 = 0;
    }
    else
    {
      if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
        || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
      {
        v17 = -1;
        for ( i = 0; ; ++i )
        {
          v19 = i == 32;
          if ( i >= 0x20 )
            break;
          v14 = (char *)(int)i;
          v13 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
          if ( (_DWORD)v13 == v16 )
          {
            v15 = i;
            `WppTraceIndent'::`2'::idxCurrentThread = i;
            v19 = i == 32;
            break;
          }
          if ( v17 == -1 && !(_DWORD)v13 )
            v17 = i;
        }
        if ( v19 )
        {
          if ( v17 == -1 )
          {
            `WppTraceIndent'::`2'::idxCurrentThread = -2;
LABEL_29:
            `WppTraceIndent'::`2'::szIndentPrefix = 0;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v9 >= 1 )
            {
              do
              {
                if ( (unsigned int)StringCbCatA(v14, v13, "..") )
                  break;
                ++v1;
              }
              while ( v1 <= v9 );
            }
            StringCbCatA(v14, v13, " ");
            WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                51,
                (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
                v20,
                *((_DWORD *)a1 + 18));
            }
            SetEvent(*((HANDLE *)a1 + 16));
            if ( v11 && dword_180045A10 )
            {
              EnterCriticalSection(&CriticalSection);
              if ( !h )
                h = CreateSCEvent(0x3Du);
              LeaveCriticalSection(&CriticalSection);
              v21 = h;
              if ( h )
              {
                EnterCriticalSection((LPCRITICAL_SECTION)a1);
                if ( !*((_BYTE *)a1 + 40) && !RtlDllShutdownInProgress() )
                  SetThreadpoolWait(*((PTP_WAIT *)a1 + 19), v21, 0);
                LeaveCriticalSection((LPCRITICAL_SECTION)a1);
              }
            }
            goto LABEL_41;
          }
          v15 = v17;
          `WppTraceIndent'::`2'::idxCurrentThread = v17;
          *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v17) = v16;
          *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v17 + 1) = 0;
        }
      }
      if ( v15 < 0 )
        goto LABEL_29;
    }
    v9 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v15 + 1);
    goto LABEL_29;
  }
  v3 = 0;
  if ( RedirectionContextThreadpoolIsSafeForUse(a1) )
  {
    SetThreadpoolWait(*((PTP_WAIT *)a1 + 20), v10, 0);
    v3 = 1;
  }
LABEL_41:
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  return v3;
}

```

## disassembly

```asm
0x180006400  push    rbx
0x180006402  push    rbp
0x180006403  push    rsi
0x180006404  push    rdi
0x180006405  push    r14
0x180006407  push    r15
0x180006409  sub     rsp, 38h
0x18000640d  mov     ebp, 1
0x180006412  mov     rbx, rcx
0x180006415  mov     r15d, ebp
0x180006418  call    cs:__imp_EnterCriticalSection
0x18000641e  xor     sil, sil
0x180006421  mov     [rsp+68h+lpCriticalSection], rbx
0x180006426  mov     rcx, rbx; lpCriticalSection
0x180006429  test    rbx, rbx
0x18000642c  jz      loc_1800067E4
0x180006432  call    cs:__imp_EnterCriticalSection
0x180006438  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18000643d  cmp     qword ptr [rcx+78h], 0
0x180006442  jnz     short loc_18000644E
0x180006444  call    ?UpdateConnectionStateForContext@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; UpdateConnectionStateForContext(_REDIRECTION_CONTEXT *)
0x180006449  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18000644e  movzx   edi, byte ptr [rcx+2Ah]
0x180006452  call    cs:__imp_LeaveCriticalSection
0x180006458  test    sil, sil
0x18000645b  jnz     loc_180006804
0x180006461  test    dil, dil
0x180006464  jz      loc_1800066B0
0x18000646a  mov     rcx, rbx; lpCriticalSection
0x18000646d  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x180006472  test    al, al
0x180006474  jz      loc_180006708
0x18000647a  xor     esi, esi
0x18000647c  cmp     cs:dword_180045A28, esi
0x180006482  jz      loc_180006659
0x180006488  lea     rcx, stru_1800455F0; lpCriticalSection
0x18000648f  call    cs:__imp_EnterCriticalSection
0x180006495  cmp     cs:hObject, rsi
0x18000649c  jz      loc_1800067CE
0x1800064a2  lea     rcx, stru_1800455F0; lpCriticalSection
0x1800064a9  call    cs:__imp_LeaveCriticalSection
0x1800064af  mov     rdi, cs:hObject
0x1800064b6  mov     r14d, ebp
0x1800064b9  test    rdi, rdi
0x1800064bc  jz      loc_1800067C6
0x1800064c2  xor     edx, edx; dwMilliseconds
0x1800064c4  mov     rcx, rdi; hHandle
0x1800064c7  call    cs:__imp_WaitForSingleObject
0x1800064cd  test    eax, eax
0x1800064cf  jnz     loc_180006686
0x1800064d5  call    cs:__imp_GetCurrentThreadId
0x1800064db  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800064e2  lea     r11, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x1800064e9  mov     r9d, eax
0x1800064ec  cmp     r10d, 0FFFFFFFFh
0x1800064f0  jz      loc_18000663E
0x1800064f6  cmp     r10d, 0FFFFFFFEh
0x1800064fa  jz      short loc_180006502
0x1800064fc  cmp     [r11+r10*8], eax
0x180006500  jz      short loc_180006545
0x180006502  mov     r8d, 0FFFFFFFFh
0x180006508  mov     eax, esi
0x18000650a  nop     word ptr [rax+rax+00h]
0x180006510  cmp     eax, 20h ; ' '
0x180006513  jnb     short loc_18000653F
0x180006515  movsxd  rcx, eax; char *
0x180006518  mov     edx, [r11+rcx*8]; unsigned __int64
0x18000651c  cmp     edx, r9d
0x18000651f  jz      short loc_180006533
0x180006521  cmp     r8d, 0FFFFFFFFh
0x180006525  jz      short loc_18000652B
0x180006527  inc     eax
0x180006529  jmp     short loc_180006510
0x18000652b  test    edx, edx
0x18000652d  cmovz   r8d, eax
0x180006531  jmp     short loc_180006527
0x180006533  mov     r10d, eax
0x180006536  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, eax; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000653c  cmp     eax, 20h ; ' '
0x18000653f  jz      loc_180006661
0x180006545  test    r10d, r10d
0x180006548  js      short loc_180006552
0x18000654a  movsxd  rax, r10d
0x18000654d  mov     esi, [r11+rax*8+4]
0x180006552  mov     rax, cs:WPP_GLOBAL_Control
0x180006559  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180006560  test    byte ptr [rax+1Ch], 2
0x180006564  jnz     loc_180006813
0x18000656a  lea     r8, asc_1800382C8; " "
0x180006571  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180006576  lea     r10, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000657d  mov     cs:?WPP_pszIndent@@3PEADEA, r10; char * WPP_pszIndent
0x180006584  mov     rcx, cs:WPP_GLOBAL_Control
0x18000658b  lea     rax, WPP_GLOBAL_Control
0x180006592  cmp     rcx, rax
0x180006595  jz      short loc_1800065A1
0x180006597  test    [rcx+1Ch], r15b
0x18000659b  jnz     loc_180006844
0x1800065a1  mov     rcx, [rbx+80h]; hEvent
0x1800065a8  call    cs:__imp_SetEvent
0x1800065ae  test    r14d, r14d
0x1800065b1  jz      short loc_180006625
0x1800065b3  cmp     cs:dword_180045A10, 0
0x1800065ba  jz      short loc_180006625
0x1800065bc  lea     rcx, CriticalSection; lpCriticalSection
0x1800065c3  call    cs:__imp_EnterCriticalSection
0x1800065c9  cmp     cs:h, 0
0x1800065d1  jz      loc_18000686F
0x1800065d7  lea     rcx, CriticalSection; lpCriticalSection
0x1800065de  call    cs:__imp_LeaveCriticalSection
0x1800065e4  mov     rdi, cs:h
0x1800065eb  test    rdi, rdi
0x1800065ee  jz      short loc_180006625
0x1800065f0  mov     rcx, rbx; lpCriticalSection
0x1800065f3  call    cs:__imp_EnterCriticalSection
0x1800065f9  cmp     byte ptr [rbx+28h], 0
0x1800065fd  jnz     short loc_18000661C
0x1800065ff  call    cs:__imp_RtlDllShutdownInProgress
0x180006605  test    al, al
0x180006607  jnz     short loc_18000661C
0x180006609  mov     rcx, [rbx+98h]; pwa
0x180006610  xor     r8d, r8d; pftTimeout
0x180006613  mov     rdx, rdi; h
0x180006616  call    cs:__imp_SetThreadpoolWait
0x18000661c  mov     rcx, rbx; lpCriticalSection
0x18000661f  call    cs:__imp_LeaveCriticalSection
0x180006625  mov     rcx, rbx; lpCriticalSection
0x180006628  call    cs:__imp_LeaveCriticalSection
0x18000662e  mov     eax, r15d
0x180006631  add     rsp, 38h
0x180006635  pop     r15
0x180006637  pop     r14
0x180006639  pop     rdi
0x18000663a  pop     rsi
0x18000663b  pop     rbp
0x18000663c  pop     rbx
0x18000663d  retn
0x18000663e  mov     r10d, esi
0x180006641  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, esi; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006647  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r9d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000664e  mov     cs:dword_180045874, esi
0x180006654  jmp     loc_18000654A
0x180006659  mov     rdi, rsi
0x18000665c  jmp     loc_1800064B6
0x180006661  cmp     r8d, 0FFFFFFFFh
0x180006665  jz      loc_180006760
0x18000666b  movsxd  rax, r8d
0x18000666e  mov     r10d, r8d
0x180006671  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r8d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006678  mov     [r11+rax*8], r9d
0x18000667c  mov     [r11+rax*8+4], esi
0x180006681  jmp     loc_180006545
0x180006686  mov     rcx, rbx; struct _REDIRECTION_CONTEXT *
0x180006689  mov     r15d, esi
0x18000668c  call    ?RedirectionContextThreadpoolIsSafeForUse@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextThreadpoolIsSafeForUse(_REDIRECTION_CONTEXT *)
0x180006691  test    al, al
0x180006693  jz      short loc_180006625
0x180006695  mov     rcx, [rbx+0A0h]; pwa
0x18000669c  xor     r8d, r8d; pftTimeout
0x18000669f  mov     rdx, rdi; h
0x1800066a2  call    cs:__imp_SetThreadpoolWait
0x1800066a8  mov     r15d, ebp
0x1800066ab  jmp     loc_180006625
0x1800066b0  mov     edx, 2
0x1800066b5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800066ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066c1  lea     rax, WPP_GLOBAL_Control
0x1800066c8  cmp     rcx, rax
0x1800066cb  jz      loc_180006625
0x1800066d1  test    [rcx+1Ch], bpl
0x1800066d5  jz      loc_180006625
0x1800066db  cmp     byte ptr [rcx+19h], 4
0x1800066df  jb      loc_180006625
0x1800066e5  mov     r8d, [rbx+48h]
0x1800066e9  mov     edx, 32h ; '2'
0x1800066ee  mov     rcx, [rcx+10h]
0x1800066f2  mov     [rsp+68h+var_48], r8d
0x1800066f7  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x1800066fe  call    WPP_SF_sd
0x180006703  jmp     loc_180006625
0x180006708  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x18000670d  test    al, al
0x18000670f  jz      short loc_18000676F
0x180006711  mov     edx, 2
0x180006716  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000671b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006722  lea     rax, WPP_GLOBAL_Control
0x180006729  cmp     rcx, rax
0x18000672c  jz      loc_180006625
0x180006732  test    [rcx+1Ch], bpl
0x180006736  jz      loc_180006625
0x18000673c  cmp     byte ptr [rcx+19h], 4
0x180006740  jb      loc_180006625
0x180006746  mov     rcx, [rcx+10h]
0x18000674a  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180006751  mov     edx, 30h ; '0'
0x180006756  call    WPP_SF_s
0x18000675b  jmp     loc_180006625
0x180006760  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, 0FFFFFFFEh; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000676a  jmp     loc_180006552
0x18000676f  xor     esi, esi
0x180006771  mov     rcx, rbx; struct _REDIRECTION_CONTEXT *
0x180006774  mov     r14d, esi
0x180006777  call    ?RedirectedSCardAccessStartedEvent@@YAPEAXPEAU_REDIRECTION_CONTEXT@@@Z; RedirectedSCardAccessStartedEvent(_REDIRECTION_CONTEXT *)
0x18000677c  mov     rdi, rax
0x18000677f  test    rax, rax
0x180006782  jnz     loc_1800064C2
0x180006788  mov     edx, 2
0x18000678d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180006792  mov     rcx, cs:WPP_GLOBAL_Control
0x180006799  lea     rax, WPP_GLOBAL_Control
0x1800067a0  cmp     rcx, rax
0x1800067a3  jz      short loc_1800067C6
0x1800067a5  test    [rcx+1Ch], bpl
0x1800067a9  jz      short loc_1800067C6
0x1800067ab  cmp     byte ptr [rcx+19h], 2
0x1800067af  jb      short loc_1800067C6
0x1800067b1  mov     rcx, [rcx+10h]
0x1800067b5  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x1800067bc  mov     edx, 31h ; '1'
0x1800067c1  call    WPP_SF_s
0x1800067c6  mov     r15d, esi
0x1800067c9  jmp     loc_180006625
0x1800067ce  mov     ecx, 19h; unsigned int
0x1800067d3  call    ?CreateSCEvent@@YAPEAXK@Z; CreateSCEvent(ulong)
0x1800067d8  mov     cs:hObject, rax
0x1800067df  jmp     loc_1800064A2
0x1800067e4  lea     rcx, [rsp+68h+lpCriticalSection]; struct _REDIRECTION_CONTEXT **
0x1800067e9  call    ?RedirectionContextLookup@@YAKPEAPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextLookup(_REDIRECTION_CONTEXT * *)
0x1800067ee  test    eax, eax
0x1800067f0  jnz     loc_1800066B0
0x1800067f6  mov     rcx, [rsp+68h+lpCriticalSection]
0x1800067fb  movzx   esi, bpl
0x1800067ff  jmp     loc_180006432
0x180006804  mov     rcx, [rsp+68h+lpCriticalSection]; struct _REDIRECTION_CONTEXT *
0x180006809  call    ?RedirectionContextRelease@@YAKPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextRelease(_REDIRECTION_CONTEXT *)
0x18000680e  jmp     loc_180006461
0x180006813  cmp     byte ptr [rax+19h], 5
0x180006817  jb      loc_18000656A
0x18000681d  cmp     esi, ebp
0x18000681f  jl      loc_18000656A
0x180006825  lea     r8, asc_18003926C; ".."
0x18000682c  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180006831  test    eax, eax
0x180006833  jnz     loc_18000656A
0x180006839  inc     ebp
0x18000683b  cmp     ebp, esi
0x18000683d  jle     short loc_180006825
0x18000683f  jmp     loc_18000656A
0x180006844  cmp     byte ptr [rcx+19h], 4
0x180006848  jb      loc_1800065A1
0x18000684e  mov     eax, [rbx+48h]
0x180006851  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180006858  mov     rcx, [rcx+10h]
0x18000685c  mov     edx, 33h ; '3'
0x180006861  mov     [rsp+68h+var_48], eax
0x180006865  call    WPP_SF_sd
0x18000686a  jmp     loc_1800065A1
0x18000686f  mov     ecx, 3Dh ; '='; unsigned int
0x180006874  call    ?CreateSCEvent@@YAPEAXK@Z; CreateSCEvent(ulong)
0x180006879  mov     cs:h, rax
0x180006880  jmp     loc_1800065D7
```
