# KapiDeliverKaUpdate

- ea: `0x180009388`
- end: `0x180009641`
- name: `KapiDeliverKaUpdate`
- size: `697`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008140`
- `0x18000f150`
- `0x180016a68`

## callees

- `0x180003ed0`
- `0x1800050d0`
- `0x180009388`
- `0x18001c4e0`
- `0x18001c500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000941e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009469`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000941e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009469`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009445`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009445`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094d5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009610`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009636`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009610`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009636`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180009489`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180009489`

## pseudocode

```c
void KapiDeliverKaUpdate()
{
  int v0; // esi
  int v1; // eax
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  _QWORD *v4; // rdi
  int v5; // eax
  _QWORD *v6; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
  }
  v0 = 1;
  do
  {
    v1 = g_KapiClientCallbackRefObject;
    if ( (g_KapiClientCallbackRefObject & 1) != 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        return;
      }
      v3 = 82;
      goto LABEL_28;
    }
  }
  while ( v1 != _InterlockedCompareExchange(
                  &g_KapiClientCallbackRefObject,
                  g_KapiClientCallbackRefObject + 2,
                  g_KapiClientCallbackRefObject) );
  v4 = (_QWORD *)MALLOC(0x28u);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
    }
    goto LABEL_22;
  }
  EnterCriticalSection(&g_KapiProviderSetLock);
  if ( g_KapiKaSampleSet )
    v5 = *(_DWORD *)(*((_QWORD *)g_KapiKaSampleSet + 2) + 20LL);
  else
    v5 = 60;
  *((_DWORD *)v4 + 8) = v5;
  LeaveCriticalSection(&g_KapiProviderSetLock);
  if ( !(unsigned __int8)RoReferenceEx(&dword_18004DE68) )
  {
LABEL_32:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
    }
    VpnFree(v4);
LABEL_22:
    if ( _InterlockedExchangeAdd(&g_KapiClientCallbackRefObject, 0xFFFFFFFE) == 3 )
      SetEvent(g_KapiClientCallbackRefEvent);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
      return;
    }
    v3 = 86;
LABEL_28:
    WPP_SF_(v2[2], v3, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
    return;
  }
  EnterCriticalSection(&g_KapiNcbWorkQueue);
  if ( dword_18004DE78
    || (dword_18004DE78 = TrySubmitThreadpoolCallback(WorkQueueCallback, &g_KapiNcbWorkQueue, pcbe),
        (v0 = dword_18004DE78) != 0) )
  {
    v4[2] = &g_KapiNcbWorkQueue;
    v4[3] = KapiDeliverKaUpdateWorkItem;
    v6 = (_QWORD *)qword_18004DE88;
    if ( *(__int64 **)qword_18004DE88 != &qword_18004DE80 )
      __fastfail(3u);
    *v4 = &qword_18004DE80;
    v4[1] = v6;
    *v6 = v4;
    qword_18004DE88 = (__int64)v4;
  }
  LeaveCriticalSection(&g_KapiNcbWorkQueue);
  if ( !v0 )
  {
    if ( _InterlockedExchangeAdd(&dword_18004DE68, 0xFFFFFFFE) == 3 )
      SetEvent(hEvent);
    goto LABEL_32;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v3 = 85;
    goto LABEL_28;
  }
}

```

## disassembly

```asm
0x180009388  push    rbx
0x18000938a  push    rsi
0x18000938b  push    rdi
0x18000938c  push    r13
0x18000938e  push    r14
0x180009390  push    r15
0x180009392  sub     rsp, 28h
0x180009396  mov     rcx, cs:WPP_GLOBAL_Control
0x18000939d  lea     r14, WPP_GLOBAL_Control
0x1800093a4  lea     r15, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x1800093ab  cmp     rcx, r14
0x1800093ae  jz      short loc_1800093BA
0x1800093b0  test    byte ptr [rcx+1Ch], 2
0x1800093b4  jnz     loc_1800095A2
0x1800093ba  mov     esi, 1
0x1800093bf  mov     eax, cs:g_KapiClientCallbackRefObject
0x1800093c5  test    sil, al
0x1800093c8  jz      loc_1800095C2
0x1800093ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093d5  cmp     rcx, r14
0x1800093d8  jz      loc_1800094F5
0x1800093de  test    byte ptr [rcx+1Ch], 2
0x1800093e2  jz      loc_1800094F5
0x1800093e8  cmp     byte ptr [rcx+19h], 6
0x1800093ec  jb      loc_1800094F5
0x1800093f2  mov     edx, 52h ; 'R'
0x1800093f7  jmp     loc_180009541
0x1800093fc  mov     ecx, 28h ; '('; dwBytes
0x180009401  call    MALLOC
0x180009406  mov     rdi, rax
0x180009409  mov     ebx, 0FFFFFFFEh
0x18000940e  test    rax, rax
0x180009411  jz      loc_180009503
0x180009417  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18000941e  call    cs:__imp_EnterCriticalSection
0x180009424  mov     rax, cs:g_KapiKaSampleSet
0x18000942b  test    rax, rax
0x18000942e  jz      loc_18000954F
0x180009434  mov     rax, [rax+10h]
0x180009438  mov     eax, [rax+14h]
0x18000943b  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x180009442  mov     [rdi+20h], eax
0x180009445  call    cs:__imp_LeaveCriticalSection
0x18000944b  lea     rcx, dword_18004DE68
0x180009452  call    RoReferenceEx
0x180009457  test    al, al
0x180009459  jz      loc_18000956C
0x18000945f  lea     r13, g_KapiNcbWorkQueue
0x180009466  mov     rcx, r13; lpCriticalSection
0x180009469  call    cs:__imp_EnterCriticalSection
0x18000946f  cmp     cs:dword_18004DE78, 0
0x180009476  jnz     short loc_18000949B
0x180009478  mov     r8, cs:pcbe; pcbe
0x18000947f  lea     rcx, WorkQueueCallback; pfns
0x180009486  mov     rdx, r13; pv
0x180009489  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000948f  mov     cs:dword_18004DE78, eax
0x180009495  mov     esi, eax
0x180009497  test    eax, eax
0x180009499  jz      short loc_1800094D2
0x18000949b  lea     rax, KapiDeliverKaUpdateWorkItem
0x1800094a2  mov     [rdi+10h], r13
0x1800094a6  mov     [rdi+18h], rax
0x1800094aa  lea     rcx, qword_18004DE80
0x1800094b1  mov     rax, cs:qword_18004DE88
0x1800094b8  cmp     [rax], rcx
0x1800094bb  jnz     loc_180009602
0x1800094c1  mov     [rdi], rcx
0x1800094c4  mov     [rdi+8], rax
0x1800094c8  mov     [rax], rdi
0x1800094cb  mov     cs:qword_18004DE88, rdi
0x1800094d2  mov     rcx, r13; lpCriticalSection
0x1800094d5  call    cs:__imp_LeaveCriticalSection
0x1800094db  test    esi, esi
0x1800094dd  jz      short loc_180009559
0x1800094df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094e6  cmp     rcx, r14
0x1800094e9  jz      short loc_1800094F5
0x1800094eb  test    byte ptr [rcx+1Ch], 2
0x1800094ef  jnz     loc_18000961B
0x1800094f5  add     rsp, 28h
0x1800094f9  pop     r15
0x1800094fb  pop     r14
0x1800094fd  pop     r13
0x1800094ff  pop     rdi
0x180009500  pop     rsi
0x180009501  pop     rbx
0x180009502  retn
0x180009503  mov     rcx, cs:WPP_GLOBAL_Control
0x18000950a  cmp     rcx, r14
0x18000950d  jnz     loc_1800095D8
0x180009513  lock xadd cs:g_KapiClientCallbackRefObject, ebx
0x18000951b  cmp     ebx, 3
0x18000951e  jz      loc_18000962F
0x180009524  mov     rcx, cs:WPP_GLOBAL_Control
0x18000952b  cmp     rcx, r14
0x18000952e  jz      short loc_1800094F5
0x180009530  test    byte ptr [rcx+1Ch], 2
0x180009534  jz      short loc_1800094F5
0x180009536  cmp     byte ptr [rcx+19h], 6
0x18000953a  jb      short loc_1800094F5
0x18000953c  mov     edx, 56h ; 'V'
0x180009541  mov     rcx, [rcx+10h]
0x180009545  mov     r8, r15
0x180009548  call    WPP_SF_
0x18000954d  jmp     short loc_1800094F5
0x18000954f  mov     eax, 3Ch ; '<'
0x180009554  jmp     loc_18000943B
0x180009559  mov     eax, ebx
0x18000955b  lock xadd cs:dword_18004DE68, eax
0x180009563  cmp     eax, 3
0x180009566  jz      loc_180009609
0x18000956c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009573  cmp     rcx, r14
0x180009576  jz      short loc_180009595
0x180009578  test    byte ptr [rcx+1Ch], 2
0x18000957c  jz      short loc_180009595
0x18000957e  cmp     byte ptr [rcx+19h], 2
0x180009582  jb      short loc_180009595
0x180009584  mov     rcx, [rcx+10h]
0x180009588  mov     edx, 54h ; 'T'
0x18000958d  mov     r8, r15
0x180009590  call    WPP_SF_
0x180009595  mov     rcx, rdi; lpMem
0x180009598  call    VpnFree
0x18000959d  jmp     loc_180009513
0x1800095a2  cmp     byte ptr [rcx+19h], 6
0x1800095a6  jb      loc_1800093BA
0x1800095ac  mov     rcx, [rcx+10h]
0x1800095b0  mov     edx, 51h ; 'Q'
0x1800095b5  mov     r8, r15
0x1800095b8  call    WPP_SF_
0x1800095bd  jmp     loc_1800093BA
0x1800095c2  lea     ecx, [rax+2]
0x1800095c5  lock cmpxchg cs:g_KapiClientCallbackRefObject, ecx
0x1800095cd  jnz     loc_1800093BF
0x1800095d3  jmp     loc_1800093FC
0x1800095d8  test    byte ptr [rcx+1Ch], 2
0x1800095dc  jz      loc_180009513
0x1800095e2  cmp     byte ptr [rcx+19h], 2
0x1800095e6  jb      loc_180009513
0x1800095ec  mov     rcx, [rcx+10h]
0x1800095f0  mov     edx, 53h ; 'S'
0x1800095f5  mov     r8, r15
0x1800095f8  call    WPP_SF_
0x1800095fd  jmp     loc_180009513
0x180009602  mov     ecx, 3
0x180009607  int     29h; Win8: RtlFailFast(ecx)
0x180009609  mov     rcx, cs:hEvent; hEvent
0x180009610  call    cs:__imp_SetEvent
0x180009616  jmp     loc_18000956C
0x18000961b  cmp     byte ptr [rcx+19h], 6
0x18000961f  jb      loc_1800094F5
0x180009625  mov     edx, 55h ; 'U'
0x18000962a  jmp     loc_180009541
0x18000962f  mov     rcx, cs:g_KapiClientCallbackRefEvent; hEvent
0x180009636  call    cs:__imp_SetEvent
0x18000963c  jmp     loc_180009524
```
