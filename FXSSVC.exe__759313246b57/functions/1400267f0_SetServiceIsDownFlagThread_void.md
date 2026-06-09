# SetServiceIsDownFlagThread(void *)

- ea: `0x1400267f0`
- end: `0x140026a1e`
- name: `?SetServiceIsDownFlagThread@@YAKPEAX@Z`
- size: `558`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400267f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400268e9`
- `KERNEL32!GetLastError` at `0x140026959`
- `KERNEL32!GetLastError` at `0x1400269e4`
- `KERNEL32!GetLastError` at `0x1400268e9`
- `KERNEL32!GetLastError` at `0x140026959`
- `KERNEL32!GetLastError` at `0x1400269e4`
- `KERNEL32!SetEvent` at `0x1400268c1`
- `KERNEL32!SetEvent` at `0x1400268c1`
- `KERNEL32!WaitForSingleObject` at `0x1400269bc`
- `KERNEL32!WaitForSingleObject` at `0x1400269bc`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140026931`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140026931`

## pseudocode

```c
__int64 __fastcall SetServiceIsDownFlagThread(PVOID Parameter)
{
  unsigned int v1; // edi
  CMapDeviceId *v2; // rcx
  DWORD LastError; // eax
  DWORD v4; // eax
  unsigned int i; // ebx
  DWORD v6; // eax

  v1 = 2;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  g_bServiceIsDown = 1;
  if ( !g_hTapiWorkerThread )
  {
    if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)v2 + 2), 69, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    v1 = 1;
  }
  if ( !g_hJobQueueThread )
  {
    if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)v2 + 2), 70, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    --v1;
  }
  if ( g_hJobQueueEvent )
  {
    if ( SetEvent(g_hJobQueueEvent) )
    {
LABEL_23:
      v2 = WPP_GLOBAL_Control;
      goto LABEL_24;
    }
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, LastError);
      goto LABEL_23;
    }
  }
LABEL_24:
  if ( g_TapiCompletionPort )
  {
    if ( PostQueuedCompletionStatus(g_TapiCompletionPort, 0, 0x80000002, 0) )
    {
LABEL_30:
      v2 = WPP_GLOBAL_Control;
      goto LABEL_31;
    }
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
      goto LABEL_35;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v4);
      goto LABEL_30;
    }
  }
LABEL_31:
  if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_d(*((_QWORD *)v2 + 2), 73, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v1);
LABEL_35:
  for ( i = 0; i < v1; ++i )
  {
    if ( WaitForSingleObject(g_hServiceIsDownSemaphore, 0xFFFFFFFF)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400267f0  push    rbx
0x1400267f2  push    rbp
0x1400267f3  push    rdi
0x1400267f4  push    r14
0x1400267f6  sub     rsp, 28h
0x1400267fa  mov     edi, 2
0x1400267ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140026806  lea     rbp, WPP_GLOBAL_Control
0x14002680d  lea     r14, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140026814  cmp     rcx, rbp
0x140026817  jz      short loc_14002683B
0x140026819  test    byte ptr [rcx+1Ch], 4
0x14002681d  jz      short loc_14002683B
0x14002681f  cmp     byte ptr [rcx+19h], 5
0x140026823  jb      short loc_14002683B
0x140026825  mov     rcx, [rcx+10h]
0x140026829  lea     edx, [rdi+42h]
0x14002682c  mov     r8, r14
0x14002682f  call    WPP_SF_
0x140026834  mov     rcx, cs:WPP_GLOBAL_Control
0x14002683b  cmp     cs:?g_hTapiWorkerThread@@3PEAXEA, 0; void * g_hTapiWorkerThread
0x140026843  mov     cs:?g_bServiceIsDown@@3HA, 1; int g_bServiceIsDown
0x14002684d  jnz     short loc_14002687D
0x14002684f  cmp     rcx, rbp
0x140026852  jz      short loc_140026878
0x140026854  test    byte ptr [rcx+1Ch], 4
0x140026858  jz      short loc_140026878
0x14002685a  cmp     byte ptr [rcx+19h], 3
0x14002685e  jb      short loc_140026878
0x140026860  mov     rcx, [rcx+10h]
0x140026864  mov     edx, 45h ; 'E'
0x140026869  mov     r8, r14
0x14002686c  call    WPP_SF_
0x140026871  mov     rcx, cs:WPP_GLOBAL_Control
0x140026878  mov     edi, 1
0x14002687d  cmp     cs:?g_hJobQueueThread@@3PEAXEA, 0; void * g_hJobQueueThread
0x140026885  jnz     short loc_1400268B2
0x140026887  cmp     rcx, rbp
0x14002688a  jz      short loc_1400268B0
0x14002688c  test    byte ptr [rcx+1Ch], 4
0x140026890  jz      short loc_1400268B0
0x140026892  cmp     byte ptr [rcx+19h], 3
0x140026896  jb      short loc_1400268B0
0x140026898  mov     rcx, [rcx+10h]
0x14002689c  mov     edx, 46h ; 'F'
0x1400268a1  mov     r8, r14
0x1400268a4  call    WPP_SF_
0x1400268a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400268b0  dec     edi
0x1400268b2  mov     rax, cs:?g_hJobQueueEvent@@3PEAXEA; void * g_hJobQueueEvent
0x1400268b9  test    rax, rax
0x1400268bc  jz      short loc_140026917
0x1400268be  mov     rcx, rax; hEvent
0x1400268c1  call    cs:__imp_SetEvent
0x1400268c8  nop     dword ptr [rax+rax+00h]
0x1400268cd  test    eax, eax
0x1400268cf  jnz     short loc_140026910
0x1400268d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400268d8  cmp     rcx, rbp
0x1400268db  jz      short loc_140026917
0x1400268dd  test    byte ptr [rcx+1Ch], 4
0x1400268e1  jz      short loc_140026917
0x1400268e3  cmp     byte ptr [rcx+19h], 2
0x1400268e7  jb      short loc_140026917
0x1400268e9  call    cs:__imp_GetLastError
0x1400268f0  nop     dword ptr [rax+rax+00h]
0x1400268f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400268fc  mov     edx, 47h ; 'G'
0x140026901  mov     r9d, eax
0x140026904  mov     r8, r14
0x140026907  mov     rcx, [rcx+10h]
0x14002690b  call    WPP_SF_d
0x140026910  mov     rcx, cs:WPP_GLOBAL_Control
0x140026917  mov     rax, cs:?g_TapiCompletionPort@@3PEAXEA; void * g_TapiCompletionPort
0x14002691e  test    rax, rax
0x140026921  jz      short loc_140026987
0x140026923  xor     r9d, r9d; lpOverlapped
0x140026926  xor     edx, edx; dwNumberOfBytesTransferred
0x140026928  mov     r8d, 80000002h; dwCompletionKey
0x14002692e  mov     rcx, rax; CompletionPort
0x140026931  call    cs:__imp_PostQueuedCompletionStatus
0x140026938  nop     dword ptr [rax+rax+00h]
0x14002693d  test    eax, eax
0x14002693f  jnz     short loc_140026980
0x140026941  mov     rcx, cs:WPP_GLOBAL_Control
0x140026948  cmp     rcx, rbp
0x14002694b  jz      short loc_1400269AC
0x14002694d  test    byte ptr [rcx+1Ch], 4
0x140026951  jz      short loc_140026987
0x140026953  cmp     byte ptr [rcx+19h], 2
0x140026957  jb      short loc_140026987
0x140026959  call    cs:__imp_GetLastError
0x140026960  nop     dword ptr [rax+rax+00h]
0x140026965  mov     rcx, cs:WPP_GLOBAL_Control
0x14002696c  mov     edx, 48h ; 'H'
0x140026971  mov     r9d, eax
0x140026974  mov     r8, r14
0x140026977  mov     rcx, [rcx+10h]
0x14002697b  call    WPP_SF_d
0x140026980  mov     rcx, cs:WPP_GLOBAL_Control
0x140026987  cmp     rcx, rbp
0x14002698a  jz      short loc_1400269AC
0x14002698c  test    byte ptr [rcx+1Ch], 4
0x140026990  jz      short loc_1400269AC
0x140026992  cmp     byte ptr [rcx+19h], 5
0x140026996  jb      short loc_1400269AC
0x140026998  mov     rcx, [rcx+10h]
0x14002699c  mov     edx, 49h ; 'I'
0x1400269a1  mov     r9d, edi
0x1400269a4  mov     r8, r14
0x1400269a7  call    WPP_SF_d
0x1400269ac  xor     ebx, ebx
0x1400269ae  test    edi, edi
0x1400269b0  jz      short loc_140026A11
0x1400269b2  mov     rcx, cs:?g_hServiceIsDownSemaphore@@3PEAXEA; hHandle
0x1400269b9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400269bc  call    cs:__imp_WaitForSingleObject
0x1400269c3  nop     dword ptr [rax+rax+00h]
0x1400269c8  test    eax, eax
0x1400269ca  jz      short loc_140026A0B
0x1400269cc  mov     rax, cs:WPP_GLOBAL_Control
0x1400269d3  cmp     rax, rbp
0x1400269d6  jz      short loc_140026A0B
0x1400269d8  test    byte ptr [rax+1Ch], 4
0x1400269dc  jz      short loc_140026A0B
0x1400269de  cmp     byte ptr [rax+19h], 2
0x1400269e2  jb      short loc_140026A0B
0x1400269e4  call    cs:__imp_GetLastError
0x1400269eb  nop     dword ptr [rax+rax+00h]
0x1400269f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400269f7  mov     edx, 4Ah ; 'J'
0x1400269fc  mov     r9d, eax
0x1400269ff  mov     r8, r14
0x140026a02  mov     rcx, [rcx+10h]
0x140026a06  call    WPP_SF_d
0x140026a0b  inc     ebx
0x140026a0d  cmp     ebx, edi
0x140026a0f  jb      short loc_1400269B2
0x140026a11  xor     eax, eax
0x140026a13  add     rsp, 28h
0x140026a17  pop     r14
0x140026a19  pop     rdi
0x140026a1a  pop     rbp
0x140026a1b  pop     rbx
0x140026a1c  retn
```
