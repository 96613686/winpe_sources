# FaxSendEventThread(void *)

- ea: `0x140059870`
- end: `0x140059b67`
- name: `?FaxSendEventThread@@YAKPEAX@Z`
- size: `759`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140001bac`
- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140052184`
- `0x140059870`
- `0x14005a3e0`
- `0x14005a86c`
- `0x14005af4c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005991f`
- `KERNEL32!GetLastError` at `0x140059aab`
- `KERNEL32!GetLastError` at `0x140059b2a`
- `KERNEL32!GetLastError` at `0x14005991f`
- `KERNEL32!GetLastError` at `0x140059aab`
- `KERNEL32!GetLastError` at `0x140059b2a`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140059a9b`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140059a9b`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1400598f7`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1400598f7`

## pseudocode

```c
__int64 __fastcall FaxSendEventThread(void *a1)
{
  CClientsMap *v1; // rcx
  DWORD LastError; // eax
  LPOVERLAPPED v3; // rbx
  unsigned int v4; // eax
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  DWORD v8; // eax
  LPOVERLAPPED v9; // rbx
  DWORD v10; // eax
  DWORD NumberOfBytesTransferred; // [rsp+68h] [rbp+38h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int64 CompletionKey; // [rsp+78h] [rbp+48h] BYREF

  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  Overlapped = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
  }
  while ( 1 )
  {
    while ( 1 )
    {
      while ( !GetQueuedCompletionStatus(
                 g_hSendEventsCompPort,
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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, LastError);
        }
        v3 = Overlapped;
        if ( Overlapped )
        {
LABEL_38:
          memset_0(v3, 0, 0x50u);
          operator delete(v3);
LABEL_39:
          Overlapped = 0;
        }
      }
      if ( CompletionKey != 2 )
        break;
      if ( g_bServiceIsDown )
      {
LABEL_36:
        v3 = Overlapped;
        if ( Overlapped )
          goto LABEL_37;
      }
      else if ( Overlapped )
      {
        v4 = CClientsMap::Notify(v1, (const struct CClientID *)Overlapped);
        if ( !v4 )
          goto LABEL_34;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_34;
        }
        v6 = 79;
LABEL_33:
        WPP_SF_d(*((_QWORD *)v5 + 2), v6, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v4);
LABEL_34:
        v3 = Overlapped;
LABEL_37:
        if ( !v3 )
          goto LABEL_39;
        goto LABEL_38;
      }
    }
    if ( CompletionKey != 3 )
      break;
    if ( g_bServiceIsDown )
      goto LABEL_36;
    if ( Overlapped )
    {
      v7 = CClientsMap::OpenClientConnection(v1, (const struct CClientID *)Overlapped);
      if ( !v7 )
        goto LABEL_34;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v7);
      }
      v4 = CClientsMap::ReleaseClient(g_pClientsMap, (const struct CClientID *)Overlapped, 0);
      if ( !v4 )
        goto LABEL_34;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      v6 = 81;
      goto LABEL_33;
    }
  }
  if ( CompletionKey != 0xFFFFFFFF )
    goto LABEL_36;
  if ( !PostQueuedCompletionStatus(g_hSendEventsCompPort, 0, 0xFFFFFFFF, 0) )
  {
    v8 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v8);
    }
  }
  v9 = Overlapped;
  if ( Overlapped )
  {
    memset_0(Overlapped, 0, 0x50u);
    operator delete(v9);
    Overlapped = 0;
  }
  if ( !(unsigned int)DecreaseServiceThreadsCount()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x140059870  mov     [rsp-28h+arg_0], rbx
0x140059875  push    rbp
0x140059876  push    r12
0x140059878  push    r13
0x14005987a  push    r14
0x14005987c  push    r15
0x14005987e  mov     rbp, rsp
0x140059881  sub     rsp, 30h
0x140059885  mov     [rbp+NumberOfBytesTransferred], 0
0x14005988c  mov     [rbp+CompletionKey], 0
0x140059894  mov     [rbp+Overlapped], 0
0x14005989c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400598a3  lea     r14, WPP_GLOBAL_Control
0x1400598aa  lea     r15, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x1400598b1  cmp     rcx, r14
0x1400598b4  jz      short loc_1400598D3
0x1400598b6  test    byte ptr [rcx+1Ch], 4
0x1400598ba  jz      short loc_1400598D3
0x1400598bc  cmp     byte ptr [rcx+19h], 5
0x1400598c0  jb      short loc_1400598D3
0x1400598c2  mov     rcx, [rcx+10h]
0x1400598c6  mov     edx, 4Dh ; 'M'
0x1400598cb  mov     r8, r15
0x1400598ce  call    WPP_SF_
0x1400598d3  mov     r13d, 0FFFFFFFFh
0x1400598d9  mov     r12d, 50h ; 'P'
0x1400598df  mov     rcx, cs:?g_hSendEventsCompPort@@3PEAXEA; CompletionPort
0x1400598e6  lea     r9, [rbp+Overlapped]; lpOverlapped
0x1400598ea  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x1400598ee  mov     [rsp+30h+dwMilliseconds], r13d; dwMilliseconds
0x1400598f3  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1400598f7  call    cs:__imp_GetQueuedCompletionStatus
0x1400598fe  nop     dword ptr [rax+rax+00h]
0x140059903  test    eax, eax
0x140059905  jnz     short loc_140059954
0x140059907  mov     rax, cs:WPP_GLOBAL_Control
0x14005990e  cmp     rax, r14
0x140059911  jz      short loc_140059946
0x140059913  test    byte ptr [rax+1Ch], 4
0x140059917  jz      short loc_140059946
0x140059919  cmp     byte ptr [rax+19h], 2
0x14005991d  jb      short loc_140059946
0x14005991f  call    cs:__imp_GetLastError
0x140059926  nop     dword ptr [rax+rax+00h]
0x14005992b  mov     rcx, cs:WPP_GLOBAL_Control
0x140059932  mov     edx, 4Eh ; 'N'
0x140059937  mov     r9d, eax
0x14005993a  mov     r8, r15
0x14005993d  mov     rcx, [rcx+10h]
0x140059941  call    WPP_SF_d
0x140059946  mov     rbx, [rbp+Overlapped]
0x14005994a  test    rbx, rbx
0x14005994d  jz      short loc_1400598DF
0x14005994f  jmp     loc_140059A6A
0x140059954  mov     rax, [rbp+CompletionKey]
0x140059958  cmp     rax, 2
0x14005995c  jnz     short loc_1400599B3
0x14005995e  cmp     cs:?g_bServiceIsDown@@3HA, 0; int g_bServiceIsDown
0x140059965  jnz     loc_140059A58
0x14005996b  mov     rdx, [rbp+Overlapped]; struct CClientID *
0x14005996f  test    rdx, rdx
0x140059972  jz      loc_1400598DF
0x140059978  call    ?Notify@CClientsMap@@QEAAKAEBVCClientID@@@Z; CClientsMap::Notify(CClientID const &)
0x14005997d  test    eax, eax
0x14005997f  jz      loc_140059A4D
0x140059985  mov     rcx, cs:WPP_GLOBAL_Control
0x14005998c  cmp     rcx, r14
0x14005998f  jz      loc_140059A4D
0x140059995  test    byte ptr [rcx+1Ch], 4
0x140059999  jz      loc_140059A4D
0x14005999f  cmp     byte ptr [rcx+19h], 2
0x1400599a3  jb      loc_140059A4D
0x1400599a9  mov     edx, 4Fh ; 'O'
0x1400599ae  jmp     loc_140059A3E
0x1400599b3  cmp     rax, 3
0x1400599b7  jnz     loc_140059A53
0x1400599bd  cmp     cs:?g_bServiceIsDown@@3HA, 0; int g_bServiceIsDown
0x1400599c4  jnz     loc_140059A58
0x1400599ca  mov     rdx, [rbp+Overlapped]; struct CClientID *
0x1400599ce  test    rdx, rdx
0x1400599d1  jz      loc_1400598DF
0x1400599d7  call    ?OpenClientConnection@CClientsMap@@QEAAKAEBVCClientID@@@Z; CClientsMap::OpenClientConnection(CClientID const &)
0x1400599dc  test    eax, eax
0x1400599de  jz      short loc_140059A4D
0x1400599e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400599e7  cmp     rcx, r14
0x1400599ea  jz      short loc_140059A0A
0x1400599ec  test    byte ptr [rcx+1Ch], 4
0x1400599f0  jz      short loc_140059A0A
0x1400599f2  cmp     byte ptr [rcx+19h], 2
0x1400599f6  jb      short loc_140059A0A
0x1400599f8  mov     rcx, [rcx+10h]
0x1400599fc  mov     edx, r12d
0x1400599ff  mov     r9d, eax
0x140059a02  mov     r8, r15
0x140059a05  call    WPP_SF_d
0x140059a0a  mov     rdx, [rbp+Overlapped]; struct CClientID *
0x140059a0e  xor     r8d, r8d; int
0x140059a11  mov     rcx, cs:?g_pClientsMap@@3PEAVCClientsMap@@EA; this
0x140059a18  call    ?ReleaseClient@CClientsMap@@QEAAKAEBVCClientID@@H@Z; CClientsMap::ReleaseClient(CClientID const &,int)
0x140059a1d  test    eax, eax
0x140059a1f  jz      short loc_140059A4D
0x140059a21  mov     rcx, cs:WPP_GLOBAL_Control
0x140059a28  cmp     rcx, r14
0x140059a2b  jz      short loc_140059A4D
0x140059a2d  test    byte ptr [rcx+1Ch], 4
0x140059a31  jz      short loc_140059A4D
0x140059a33  cmp     byte ptr [rcx+19h], 2
0x140059a37  jb      short loc_140059A4D
0x140059a39  mov     edx, 51h ; 'Q'
0x140059a3e  mov     rcx, [rcx+10h]
0x140059a42  mov     r9d, eax
0x140059a45  mov     r8, r15
0x140059a48  call    WPP_SF_d
0x140059a4d  mov     rbx, [rbp+Overlapped]
0x140059a51  jmp     short loc_140059A65
0x140059a53  cmp     rax, r13
0x140059a56  jz      short loc_140059A8C
0x140059a58  mov     rbx, [rbp+Overlapped]
0x140059a5c  test    rbx, rbx
0x140059a5f  jz      loc_1400598DF
0x140059a65  test    rbx, rbx
0x140059a68  jz      short loc_140059A7F
0x140059a6a  mov     r8, r12; Size
0x140059a6d  xor     edx, edx; Val
0x140059a6f  mov     rcx, rbx; void *
0x140059a72  call    memset_0
0x140059a77  mov     rcx, rbx; Block
0x140059a7a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140059a7f  mov     [rbp+Overlapped], 0
0x140059a87  jmp     loc_1400598DF
0x140059a8c  mov     rcx, cs:?g_hSendEventsCompPort@@3PEAXEA; CompletionPort
0x140059a93  xor     r9d, r9d; lpOverlapped
0x140059a96  mov     r8, r13; dwCompletionKey
0x140059a99  xor     edx, edx; dwNumberOfBytesTransferred
0x140059a9b  call    cs:__imp_PostQueuedCompletionStatus
0x140059aa2  nop     dword ptr [rax+rax+00h]
0x140059aa7  test    eax, eax
0x140059aa9  jnz     short loc_140059AE3
0x140059aab  call    cs:__imp_GetLastError
0x140059ab2  nop     dword ptr [rax+rax+00h]
0x140059ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x140059abe  cmp     rcx, r14
0x140059ac1  jz      short loc_140059AE3
0x140059ac3  test    byte ptr [rcx+1Ch], 4
0x140059ac7  jz      short loc_140059AE3
0x140059ac9  cmp     byte ptr [rcx+19h], 2
0x140059acd  jb      short loc_140059AE3
0x140059acf  mov     rcx, [rcx+10h]
0x140059ad3  mov     edx, 52h ; 'R'
0x140059ad8  mov     r9d, eax
0x140059adb  mov     r8, r15
0x140059ade  call    WPP_SF_d
0x140059ae3  mov     rbx, [rbp+Overlapped]
0x140059ae7  test    rbx, rbx
0x140059aea  jz      short loc_140059B09
0x140059aec  mov     r8, r12; Size
0x140059aef  xor     edx, edx; Val
0x140059af1  mov     rcx, rbx; void *
0x140059af4  call    memset_0
0x140059af9  mov     rcx, rbx; Block
0x140059afc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140059b01  mov     [rbp+Overlapped], 0
0x140059b09  call    ?DecreaseServiceThreadsCount@@YAHXZ; DecreaseServiceThreadsCount(void)
0x140059b0e  test    eax, eax
0x140059b10  jnz     short loc_140059B51
0x140059b12  mov     rax, cs:WPP_GLOBAL_Control
0x140059b19  cmp     rax, r14
0x140059b1c  jz      short loc_140059B51
0x140059b1e  test    byte ptr [rax+1Ch], 4
0x140059b22  jz      short loc_140059B51
0x140059b24  cmp     byte ptr [rax+19h], 2
0x140059b28  jb      short loc_140059B51
0x140059b2a  call    cs:__imp_GetLastError
0x140059b31  nop     dword ptr [rax+rax+00h]
0x140059b36  mov     rcx, cs:WPP_GLOBAL_Control
0x140059b3d  mov     edx, 53h ; 'S'
0x140059b42  mov     r9d, eax
0x140059b45  mov     r8, r15
0x140059b48  mov     rcx, [rcx+10h]
0x140059b4c  call    WPP_SF_d
0x140059b51  mov     rbx, [rsp+30h+arg_0]
0x140059b56  xor     eax, eax
0x140059b58  add     rsp, 30h
0x140059b5c  pop     r15
0x140059b5e  pop     r14
0x140059b60  pop     r13
0x140059b62  pop     r12
0x140059b64  pop     rbp
0x140059b65  retn
```
