# FaxDispatchEventThread(void *)

- ea: `0x1400596c0`
- end: `0x140059866`
- name: `?FaxDispatchEventThread@@YAKPEAX@Z`
- size: `422`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140052184`
- `0x140058410`
- `0x1400596c0`
- `0x14008b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005975d`
- `KERNEL32!GetLastError` at `0x14005982f`
- `KERNEL32!GetLastError` at `0x14005975d`
- `KERNEL32!GetLastError` at `0x14005982f`
- `KERNEL32!GetQueuedCompletionStatus` at `0x140059735`
- `KERNEL32!GetQueuedCompletionStatus` at `0x140059735`

## pseudocode

```c
__int64 __fastcall FaxDispatchEventThread(void *a1)
{
  CClientsMap *v1; // rcx
  DWORD LastError; // eax
  LPOVERLAPPED v3; // rcx
  unsigned int v4; // eax
  DWORD v5; // eax
  DWORD NumberOfBytesTransferred; // [rsp+58h] [rbp+28h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int64 CompletionKey; // [rsp+68h] [rbp+38h] BYREF

  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  Overlapped = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
  }
  while ( !GetQueuedCompletionStatus(
             g_hDispatchEventsCompPort,
             &NumberOfBytesTransferred,
             &CompletionKey,
             &Overlapped,
             0xFFFFFFFF) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, LastError);
    }
    v3 = Overlapped;
    if ( Overlapped )
    {
LABEL_21:
      (*(void (__fastcall **)(LPOVERLAPPED, __int64))v3->Internal)(v3, 1);
LABEL_22:
      Overlapped = 0;
    }
  }
  if ( CompletionKey == 1 )
  {
    if ( !g_bServiceIsDown )
    {
      v4 = CClientsMap::AddEvent(v1, (struct CFaxEvent *)Overlapped);
      if ( v4 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v4);
        }
      }
    }
LABEL_20:
    v3 = Overlapped;
    if ( !Overlapped )
      goto LABEL_22;
    goto LABEL_21;
  }
  if ( CompletionKey != 0xFFFFFFFF )
    goto LABEL_20;
  if ( !(unsigned int)DecreaseServiceThreadsCount()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v5);
  }
  return 0;
}

```

## disassembly

```asm
0x1400596c0  push    rbp
0x1400596c2  push    rsi
0x1400596c3  push    r13
0x1400596c5  mov     rbp, rsp
0x1400596c8  sub     rsp, 30h
0x1400596cc  mov     [rbp+NumberOfBytesTransferred], 0
0x1400596d3  mov     [rbp+CompletionKey], 0
0x1400596db  mov     [rbp+Overlapped], 0
0x1400596e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400596ea  lea     rsi, WPP_GLOBAL_Control
0x1400596f1  cmp     rcx, rsi
0x1400596f4  jz      short loc_140059717
0x1400596f6  test    byte ptr [rcx+1Ch], 4
0x1400596fa  jz      short loc_140059717
0x1400596fc  cmp     byte ptr [rcx+19h], 5
0x140059700  jb      short loc_140059717
0x140059702  mov     rcx, [rcx+10h]
0x140059706  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005970d  mov     edx, 54h ; 'T'
0x140059712  call    WPP_SF_
0x140059717  mov     r13d, 0FFFFFFFFh
0x14005971d  mov     rcx, cs:?g_hDispatchEventsCompPort@@3PEAXEA; CompletionPort
0x140059724  lea     r9, [rbp+Overlapped]; lpOverlapped
0x140059728  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x14005972c  mov     [rsp+30h+dwMilliseconds], r13d; dwMilliseconds
0x140059731  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140059735  call    cs:__imp_GetQueuedCompletionStatus
0x14005973c  nop     dword ptr [rax+rax+00h]
0x140059741  test    eax, eax
0x140059743  jnz     short loc_140059793
0x140059745  mov     rax, cs:WPP_GLOBAL_Control
0x14005974c  cmp     rax, rsi
0x14005974f  jz      short loc_140059788
0x140059751  test    byte ptr [rax+1Ch], 4
0x140059755  jz      short loc_140059788
0x140059757  cmp     byte ptr [rax+19h], 2
0x14005975b  jb      short loc_140059788
0x14005975d  call    cs:__imp_GetLastError
0x140059764  nop     dword ptr [rax+rax+00h]
0x140059769  mov     rcx, cs:WPP_GLOBAL_Control
0x140059770  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140059777  mov     edx, 55h ; 'U'
0x14005977c  mov     r9d, eax
0x14005977f  mov     rcx, [rcx+10h]
0x140059783  call    WPP_SF_d
0x140059788  mov     rcx, [rbp+Overlapped]
0x14005978c  test    rcx, rcx
0x14005978f  jz      short loc_14005971D
0x140059791  jmp     short loc_1400597F1
0x140059793  cmp     [rbp+CompletionKey], 1
0x140059798  jnz     short loc_1400597E2
0x14005979a  cmp     cs:?g_bServiceIsDown@@3HA, 0; int g_bServiceIsDown
0x1400597a1  jnz     short loc_1400597E8
0x1400597a3  mov     rdx, [rbp+Overlapped]; struct CFaxEvent *
0x1400597a7  call    ?AddEvent@CClientsMap@@QEAAKPEAVCFaxEvent@@@Z; CClientsMap::AddEvent(CFaxEvent *)
0x1400597ac  test    eax, eax
0x1400597ae  jz      short loc_1400597E8
0x1400597b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400597b7  cmp     rcx, rsi
0x1400597ba  jz      short loc_1400597E8
0x1400597bc  test    byte ptr [rcx+1Ch], 4
0x1400597c0  jz      short loc_1400597E8
0x1400597c2  cmp     byte ptr [rcx+19h], 2
0x1400597c6  jb      short loc_1400597E8
0x1400597c8  mov     rcx, [rcx+10h]
0x1400597cc  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x1400597d3  mov     edx, 56h ; 'V'
0x1400597d8  mov     r9d, eax
0x1400597db  call    WPP_SF_d
0x1400597e0  jmp     short loc_1400597E8
0x1400597e2  cmp     [rbp+CompletionKey], r13
0x1400597e6  jz      short loc_14005980E
0x1400597e8  mov     rcx, [rbp+Overlapped]
0x1400597ec  test    rcx, rcx
0x1400597ef  jz      short loc_140059801
0x1400597f1  mov     rax, [rcx]
0x1400597f4  mov     edx, 1
0x1400597f9  mov     rax, [rax]
0x1400597fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059801  mov     [rbp+Overlapped], 0
0x140059809  jmp     loc_14005971D
0x14005980e  call    ?DecreaseServiceThreadsCount@@YAHXZ; DecreaseServiceThreadsCount(void)
0x140059813  test    eax, eax
0x140059815  jnz     short loc_14005985A
0x140059817  mov     rax, cs:WPP_GLOBAL_Control
0x14005981e  cmp     rax, rsi
0x140059821  jz      short loc_14005985A
0x140059823  test    byte ptr [rax+1Ch], 4
0x140059827  jz      short loc_14005985A
0x140059829  cmp     byte ptr [rax+19h], 2
0x14005982d  jb      short loc_14005985A
0x14005982f  call    cs:__imp_GetLastError
0x140059836  nop     dword ptr [rax+rax+00h]
0x14005983b  mov     rcx, cs:WPP_GLOBAL_Control
0x140059842  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140059849  mov     edx, 57h ; 'W'
0x14005984e  mov     r9d, eax
0x140059851  mov     rcx, [rcx+10h]
0x140059855  call    WPP_SF_d
0x14005985a  xor     eax, eax
0x14005985c  add     rsp, 30h
0x140059860  pop     r13
0x140059862  pop     rsi
0x140059863  pop     rbp
0x140059864  retn
```
