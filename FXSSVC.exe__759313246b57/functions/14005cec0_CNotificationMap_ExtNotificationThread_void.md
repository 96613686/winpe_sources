# CNotificationMap::ExtNotificationThread(void *)

- ea: `0x14005cec0`
- end: `0x14005d0ee`
- name: `?ExtNotificationThread@CNotificationMap@@CAKPEAX@Z`
- size: `558`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140001bac`
- `0x140004c78`
- `0x140004ca8`
- `0x140052184`
- `0x14005cec0`
- `0x14005eac0`
- `0x14006998c`
- `0x14008b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005cf4c`
- `KERNEL32!GetLastError` at `0x14005d05a`
- `KERNEL32!GetLastError` at `0x14005d0b7`
- `KERNEL32!GetLastError` at `0x14005cf4c`
- `KERNEL32!GetLastError` at `0x14005d05a`
- `KERNEL32!GetLastError` at `0x14005d0b7`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14005d04a`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14005d04a`
- `KERNEL32!GetQueuedCompletionStatus` at `0x14005cf3c`
- `KERNEL32!GetQueuedCompletionStatus` at `0x14005cf3c`

## pseudocode

```c
__int64 __fastcall CNotificationMap::ExtNotificationThread(void *a1)
{
  int v1; // edx
  int v2; // r8d
  DWORD LastError; // eax
  LPVOID *v4; // rbx
  DWORD v5; // eax
  DWORD v6; // eax
  DWORD NumberOfBytesTransferred; // [rsp+68h] [rbp+10h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int64 CompletionKey; // [rsp+78h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids);
  }
  while ( 1 )
  {
    while ( 1 )
    {
      NumberOfBytesTransferred = 0;
      CompletionKey = 0;
      Overlapped = 0;
      if ( GetQueuedCompletionStatus(
             *((HANDLE *)g_pNotificationMap + 1),
             &NumberOfBytesTransferred,
             &CompletionKey,
             &Overlapped,
             0xFFFFFFFF) )
      {
        break;
      }
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids, LastError);
      }
      v4 = (LPVOID *)Overlapped;
      if ( Overlapped )
        goto LABEL_18;
    }
    if ( CompletionKey == 0xFFFFFFFF )
      break;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_qlSql(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v1,
        v2,
        Overlapped[1].Internal,
        Overlapped->Internal,
        Overlapped->InternalHigh,
        (char)Overlapped->Pointer,
        (char)Overlapped->hEvent);
    }
    ((void (__fastcall *)(_QWORD, ULONG_PTR, PVOID, _QWORD))Overlapped[1].Internal)(
      LODWORD(Overlapped->Internal),
      Overlapped->InternalHigh,
      Overlapped->Pointer,
      LODWORD(Overlapped->hEvent));
    v4 = (LPVOID *)Overlapped;
LABEL_18:
    if ( v4 )
    {
      pMemFree(v4[1]);
      pMemFree(v4[2]);
      operator delete(v4);
    }
  }
  if ( !PostQueuedCompletionStatus(*((HANDLE *)g_pNotificationMap + 1), 0, 0xFFFFFFFF, 0) )
  {
    v5 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids, v5);
    }
  }
  if ( !(unsigned int)DecreaseServiceThreadsCount()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids, v6);
  }
  return 0;
}

```

## disassembly

```asm
0x14005cec0  push    rbx
0x14005cec2  push    rbp
0x14005cec3  push    r12
0x14005cec5  sub     rsp, 40h
0x14005cec9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ced0  lea     rbp, WPP_GLOBAL_Control
0x14005ced7  cmp     rcx, rbp
0x14005ceda  jz      short loc_14005CEFD
0x14005cedc  test    byte ptr [rcx+1Ch], 4
0x14005cee0  jz      short loc_14005CEFD
0x14005cee2  cmp     byte ptr [rcx+19h], 5
0x14005cee6  jb      short loc_14005CEFD
0x14005cee8  mov     rcx, [rcx+10h]
0x14005ceec  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005cef3  mov     edx, 22h ; '"'
0x14005cef8  call    WPP_SF_
0x14005cefd  mov     r12d, 0FFFFFFFFh
0x14005cf03  mov     rcx, cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA; CNotificationMap * g_pNotificationMap
0x14005cf0a  lea     r9, [rsp+58h+Overlapped]; lpOverlapped
0x14005cf0f  mov     [rsp+58h+NumberOfBytesTransferred], 0
0x14005cf17  lea     r8, [rsp+58h+CompletionKey]; lpCompletionKey
0x14005cf1c  mov     [rsp+58h+CompletionKey], 0
0x14005cf25  lea     rdx, [rsp+58h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x14005cf2a  mov     [rsp+58h+Overlapped], 0
0x14005cf33  mov     rcx, [rcx+8]; CompletionPort
0x14005cf37  mov     [rsp+58h+dwMilliseconds], r12d; dwMilliseconds
0x14005cf3c  call    cs:__imp_GetQueuedCompletionStatus
0x14005cf43  nop     dword ptr [rax+rax+00h]
0x14005cf48  test    eax, eax
0x14005cf4a  jnz     short loc_14005CF98
0x14005cf4c  call    cs:__imp_GetLastError
0x14005cf53  nop     dword ptr [rax+rax+00h]
0x14005cf58  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cf5f  cmp     rcx, rbp
0x14005cf62  jz      short loc_14005CF88
0x14005cf64  test    byte ptr [rcx+1Ch], 4
0x14005cf68  jz      short loc_14005CF88
0x14005cf6a  cmp     byte ptr [rcx+19h], 2
0x14005cf6e  jb      short loc_14005CF88
0x14005cf70  mov     rcx, [rcx+10h]
0x14005cf74  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005cf7b  mov     edx, 23h ; '#'
0x14005cf80  mov     r9d, eax
0x14005cf83  call    WPP_SF_d
0x14005cf88  mov     rbx, [rsp+58h+Overlapped]
0x14005cf8d  test    rbx, rbx
0x14005cf90  jz      loc_14005CF03
0x14005cf96  jmp     short loc_14005D00F
0x14005cf98  cmp     [rsp+58h+CompletionKey], r12
0x14005cf9d  jz      loc_14005D037
0x14005cfa3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cfaa  cmp     rcx, rbp
0x14005cfad  jz      short loc_14005CFEE
0x14005cfaf  test    byte ptr [rcx+1Ch], 4
0x14005cfb3  jz      short loc_14005CFEE
0x14005cfb5  cmp     byte ptr [rcx+19h], 5
0x14005cfb9  jb      short loc_14005CFEE
0x14005cfbb  mov     r9, [rsp+58h+Overlapped]
0x14005cfc0  mov     rcx, [rcx+10h]
0x14005cfc4  mov     eax, [r9+18h]
0x14005cfc8  mov     [rsp+58h+var_20], eax
0x14005cfcc  mov     rax, [r9+10h]
0x14005cfd0  mov     [rsp+58h+var_28], rax
0x14005cfd5  mov     rax, [r9+8]
0x14005cfd9  mov     [rsp+58h+var_30], rax
0x14005cfde  mov     eax, [r9]
0x14005cfe1  mov     r9, [r9+20h]
0x14005cfe5  mov     [rsp+58h+dwMilliseconds], eax
0x14005cfe9  call    WPP_SF_qlSql
0x14005cfee  mov     rcx, [rsp+58h+Overlapped]
0x14005cff3  mov     rax, [rcx+20h]
0x14005cff7  mov     r9d, [rcx+18h]
0x14005cffb  mov     r8, [rcx+10h]
0x14005cfff  mov     rdx, [rcx+8]
0x14005d003  mov     ecx, [rcx]
0x14005d005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005d00a  mov     rbx, [rsp+58h+Overlapped]
0x14005d00f  test    rbx, rbx
0x14005d012  jz      loc_14005CF03
0x14005d018  mov     rcx, [rbx+8]; lpMem
0x14005d01c  call    pMemFree
0x14005d021  mov     rcx, [rbx+10h]; lpMem
0x14005d025  call    pMemFree
0x14005d02a  mov     rcx, rbx; Block
0x14005d02d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005d032  jmp     loc_14005CF03
0x14005d037  mov     rcx, cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA; CNotificationMap * g_pNotificationMap
0x14005d03e  xor     r9d, r9d; lpOverlapped
0x14005d041  mov     r8, r12; dwCompletionKey
0x14005d044  xor     edx, edx; dwNumberOfBytesTransferred
0x14005d046  mov     rcx, [rcx+8]; CompletionPort
0x14005d04a  call    cs:__imp_PostQueuedCompletionStatus
0x14005d051  nop     dword ptr [rax+rax+00h]
0x14005d056  test    eax, eax
0x14005d058  jnz     short loc_14005D096
0x14005d05a  call    cs:__imp_GetLastError
0x14005d061  nop     dword ptr [rax+rax+00h]
0x14005d066  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d06d  cmp     rcx, rbp
0x14005d070  jz      short loc_14005D096
0x14005d072  test    byte ptr [rcx+1Ch], 4
0x14005d076  jz      short loc_14005D096
0x14005d078  cmp     byte ptr [rcx+19h], 2
0x14005d07c  jb      short loc_14005D096
0x14005d07e  mov     rcx, [rcx+10h]
0x14005d082  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005d089  mov     edx, 24h ; '$'
0x14005d08e  mov     r9d, eax
0x14005d091  call    WPP_SF_d
0x14005d096  call    ?DecreaseServiceThreadsCount@@YAHXZ; DecreaseServiceThreadsCount(void)
0x14005d09b  test    eax, eax
0x14005d09d  jnz     short loc_14005D0E2
0x14005d09f  mov     rax, cs:WPP_GLOBAL_Control
0x14005d0a6  cmp     rax, rbp
0x14005d0a9  jz      short loc_14005D0E2
0x14005d0ab  test    byte ptr [rax+1Ch], 4
0x14005d0af  jz      short loc_14005D0E2
0x14005d0b1  cmp     byte ptr [rax+19h], 2
0x14005d0b5  jb      short loc_14005D0E2
0x14005d0b7  call    cs:__imp_GetLastError
0x14005d0be  nop     dword ptr [rax+rax+00h]
0x14005d0c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d0ca  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005d0d1  mov     edx, 25h ; '%'
0x14005d0d6  mov     r9d, eax
0x14005d0d9  mov     rcx, [rcx+10h]
0x14005d0dd  call    WPP_SF_d
0x14005d0e2  xor     eax, eax
0x14005d0e4  add     rsp, 40h
0x14005d0e8  pop     r12
0x14005d0ea  pop     rbp
0x14005d0eb  pop     rbx
0x14005d0ec  retn
```
