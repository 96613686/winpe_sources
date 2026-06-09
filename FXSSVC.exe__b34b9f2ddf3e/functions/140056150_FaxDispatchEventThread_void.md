# FaxDispatchEventThread(void *)

- ea: `0x140056150`
- end: `0x1400562e3`
- name: `?FaxDispatchEventThread@@YAKPEAX@Z`
- size: `403`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14004eedc`
- `0x140054f24`
- `0x140056150`
- `0x140085010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400561e7`
- `KERNEL32!GetLastError` at `0x1400562b3`
- `KERNEL32!GetLastError` at `0x1400561e7`
- `KERNEL32!GetLastError` at `0x1400562b3`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1400561c5`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1400561c5`

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
0x140056150  push    rbp
0x140056152  push    rsi
0x140056153  push    r13
0x140056155  mov     rbp, rsp
0x140056158  sub     rsp, 30h
0x14005615c  mov     [rbp+NumberOfBytesTransferred], 0
0x140056163  mov     [rbp+CompletionKey], 0
0x14005616b  mov     [rbp+Overlapped], 0
0x140056173  mov     rcx, cs:WPP_GLOBAL_Control
0x14005617a  lea     rsi, WPP_GLOBAL_Control
0x140056181  cmp     rcx, rsi
0x140056184  jz      short loc_1400561A7
0x140056186  test    byte ptr [rcx+1Ch], 4
0x14005618a  jz      short loc_1400561A7
0x14005618c  cmp     byte ptr [rcx+19h], 5
0x140056190  jb      short loc_1400561A7
0x140056192  mov     rcx, [rcx+10h]
0x140056196  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x14005619d  mov     edx, 54h ; 'T'
0x1400561a2  call    WPP_SF_
0x1400561a7  mov     r13d, 0FFFFFFFFh
0x1400561ad  mov     rcx, cs:?g_hDispatchEventsCompPort@@3PEAXEA; CompletionPort
0x1400561b4  lea     r9, [rbp+Overlapped]; lpOverlapped
0x1400561b8  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x1400561bc  mov     [rsp+30h+dwMilliseconds], r13d; dwMilliseconds
0x1400561c1  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1400561c5  call    cs:__imp_GetQueuedCompletionStatus
0x1400561cb  test    eax, eax
0x1400561cd  jnz     short loc_140056217
0x1400561cf  mov     rax, cs:WPP_GLOBAL_Control
0x1400561d6  cmp     rax, rsi
0x1400561d9  jz      short loc_14005620C
0x1400561db  test    byte ptr [rax+1Ch], 4
0x1400561df  jz      short loc_14005620C
0x1400561e1  cmp     byte ptr [rax+19h], 2
0x1400561e5  jb      short loc_14005620C
0x1400561e7  call    cs:__imp_GetLastError
0x1400561ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400561f4  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x1400561fb  mov     edx, 55h ; 'U'
0x140056200  mov     r9d, eax
0x140056203  mov     rcx, [rcx+10h]
0x140056207  call    WPP_SF_d
0x14005620c  mov     rcx, [rbp+Overlapped]
0x140056210  test    rcx, rcx
0x140056213  jz      short loc_1400561AD
0x140056215  jmp     short loc_140056275
0x140056217  cmp     [rbp+CompletionKey], 1
0x14005621c  jnz     short loc_140056266
0x14005621e  cmp     cs:?g_bServiceIsDown@@3HA, 0; int g_bServiceIsDown
0x140056225  jnz     short loc_14005626C
0x140056227  mov     rdx, [rbp+Overlapped]; struct CFaxEvent *
0x14005622b  call    ?AddEvent@CClientsMap@@QEAAKPEAVCFaxEvent@@@Z; CClientsMap::AddEvent(CFaxEvent *)
0x140056230  test    eax, eax
0x140056232  jz      short loc_14005626C
0x140056234  mov     rcx, cs:WPP_GLOBAL_Control
0x14005623b  cmp     rcx, rsi
0x14005623e  jz      short loc_14005626C
0x140056240  test    byte ptr [rcx+1Ch], 4
0x140056244  jz      short loc_14005626C
0x140056246  cmp     byte ptr [rcx+19h], 2
0x14005624a  jb      short loc_14005626C
0x14005624c  mov     rcx, [rcx+10h]
0x140056250  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140056257  mov     edx, 56h ; 'V'
0x14005625c  mov     r9d, eax
0x14005625f  call    WPP_SF_d
0x140056264  jmp     short loc_14005626C
0x140056266  cmp     [rbp+CompletionKey], r13
0x14005626a  jz      short loc_140056292
0x14005626c  mov     rcx, [rbp+Overlapped]
0x140056270  test    rcx, rcx
0x140056273  jz      short loc_140056285
0x140056275  mov     rax, [rcx]
0x140056278  mov     edx, 1
0x14005627d  mov     rax, [rax]
0x140056280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056285  mov     [rbp+Overlapped], 0
0x14005628d  jmp     loc_1400561AD
0x140056292  call    ?DecreaseServiceThreadsCount@@YAHXZ; DecreaseServiceThreadsCount(void)
0x140056297  test    eax, eax
0x140056299  jnz     short loc_1400562D8
0x14005629b  mov     rax, cs:WPP_GLOBAL_Control
0x1400562a2  cmp     rax, rsi
0x1400562a5  jz      short loc_1400562D8
0x1400562a7  test    byte ptr [rax+1Ch], 4
0x1400562ab  jz      short loc_1400562D8
0x1400562ad  cmp     byte ptr [rax+19h], 2
0x1400562b1  jb      short loc_1400562D8
0x1400562b3  call    cs:__imp_GetLastError
0x1400562b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400562c0  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x1400562c7  mov     edx, 57h ; 'W'
0x1400562cc  mov     r9d, eax
0x1400562cf  mov     rcx, [rcx+10h]
0x1400562d3  call    WPP_SF_d
0x1400562d8  xor     eax, eax
0x1400562da  add     rsp, 30h
0x1400562de  pop     r13
0x1400562e0  pop     rsi
0x1400562e1  pop     rbp
0x1400562e2  retn
```
