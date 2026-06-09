# CLocalNotificationSink::Notify(ulong,ushort const *,ushort const *,void *,uchar *,ulong,int *)

- ea: `0x14005d9b0`
- end: `0x14005dbcd`
- name: `?Notify@CLocalNotificationSink@@UEAAJKPEBG0PEAXPEAEKPEAH@Z`
- size: `541`
- prototype: `int(CLocalNotificationSink *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *, void *, unsigned __int8 *, unsigned int, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001bac`
- `0x1400023ec`
- `0x140004c78`
- `0x140004ca8`
- `0x14005d568`
- `0x14005d9b0`
- `0x14006998c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005dac1`
- `KERNEL32!GetLastError` at `0x14005db17`
- `KERNEL32!GetLastError` at `0x14005dba3`
- `KERNEL32!GetLastError` at `0x14005dac1`
- `KERNEL32!GetLastError` at `0x14005db17`
- `KERNEL32!GetLastError` at `0x14005dba3`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14005db03`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14005db03`
- `KERNEL32!lstrcmpW` at `0x14005da14`
- `KERNEL32!lstrcmpW` at `0x14005da14`

## pseudocode

```c
__int64 __fastcall CLocalNotificationSink::Notify(
        CLocalNotificationSink *this,
        __int64 a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        void *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        int *a8)
{
  void *v11; // rax
  CExtNotifyCallbackPacket *v13; // rax
  struct _OVERLAPPED *v14; // rdi
  DWORD v15; // ebx
  CMapDeviceId *v16; // rcx
  __int64 v17; // rdx
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids);
  }
  *a8 = 0;
  if ( lstrcmpW(&Class, a4) || (v11 = (void *)*((_QWORD *)this + 4), a5 != v11) )
  {
    v13 = (CExtNotifyCallbackPacket *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v14 = (struct _OVERLAPPED *)v13;
    if ( !v13 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids);
      }
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return v15;
    }
    *((_QWORD *)v13 + 1) = 0;
    *((_QWORD *)v13 + 2) = 0;
    if ( CExtNotifyCallbackPacket::Init(
           v13,
           *((int (**)(unsigned int, const unsigned __int16 *, unsigned __int8 *, unsigned int))this + 2),
           *((_DWORD *)this + 6),
           a3,
           a6,
           a7) )
    {
      v15 = 0;
      if ( PostQueuedCompletionStatus(*((HANDLE *)g_pNotificationMap + 1), 0, 0, v14) )
        return v15;
      v15 = GetLastError();
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_24:
        if ( (int)v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        pMemFree((LPVOID)v14->InternalHigh);
        pMemFree(v14->Pointer);
        operator delete(v14);
        return v15;
      }
      v17 = 17;
    }
    else
    {
      v15 = GetLastError();
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      v17 = 16;
    }
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids, v15);
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids,
      (unsigned int)v11);
  }
  return 0;
}

```

## disassembly

```asm
0x14005d9b0  push    rbx
0x14005d9b2  push    rsi
0x14005d9b3  push    rdi
0x14005d9b4  push    r12
0x14005d9b6  push    r15
0x14005d9b8  sub     rsp, 30h
0x14005d9bc  mov     rdi, r9
0x14005d9bf  mov     rsi, r8
0x14005d9c2  mov     rbx, rcx
0x14005d9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d9cc  lea     r15, WPP_GLOBAL_Control
0x14005d9d3  lea     r12, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005d9da  cmp     rcx, r15
0x14005d9dd  jz      short loc_14005D9FC
0x14005d9df  test    byte ptr [rcx+1Ch], 4
0x14005d9e3  jz      short loc_14005D9FC
0x14005d9e5  cmp     byte ptr [rcx+19h], 5
0x14005d9e9  jb      short loc_14005D9FC
0x14005d9eb  mov     rcx, [rcx+10h]
0x14005d9ef  mov     edx, 0Dh
0x14005d9f4  mov     r8, r12
0x14005d9f7  call    WPP_SF_
0x14005d9fc  mov     rax, [rsp+58h+arg_38]
0x14005da04  lea     rcx, Class; lpString1
0x14005da0b  mov     rdx, rdi; lpString2
0x14005da0e  mov     dword ptr [rax], 0
0x14005da14  call    cs:__imp_lstrcmpW
0x14005da1b  nop     dword ptr [rax+rax+00h]
0x14005da20  test    eax, eax
0x14005da22  jnz     short loc_14005DA65
0x14005da24  mov     rax, [rbx+20h]
0x14005da28  cmp     [rsp+58h+arg_20], rax
0x14005da30  jnz     short loc_14005DA65
0x14005da32  mov     rcx, cs:WPP_GLOBAL_Control
0x14005da39  cmp     rcx, r15
0x14005da3c  jz      short loc_14005DA5E
0x14005da3e  test    byte ptr [rcx+1Ch], 4
0x14005da42  jz      short loc_14005DA5E
0x14005da44  cmp     byte ptr [rcx+19h], 5
0x14005da48  jb      short loc_14005DA5E
0x14005da4a  mov     rcx, [rcx+10h]
0x14005da4e  mov     edx, 0Eh
0x14005da53  mov     r9d, eax
0x14005da56  mov     r8, r12
0x14005da59  call    WPP_SF_d
0x14005da5e  xor     eax, eax
0x14005da60  jmp     loc_14005DBC0
0x14005da65  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14005da6c  mov     ecx, 28h ; '('; unsigned __int64
0x14005da71  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14005da76  mov     rdi, rax
0x14005da79  test    rax, rax
0x14005da7c  jz      loc_14005DB7A
0x14005da82  mov     ecx, [rsp+58h+arg_30]
0x14005da89  mov     r9, rsi; unsigned __int16 *
0x14005da8c  mov     [rsp+58h+var_30], ecx; unsigned int
0x14005da90  mov     rcx, [rsp+58h+arg_28]
0x14005da98  mov     qword ptr [rax+8], 0
0x14005daa0  mov     qword ptr [rax+10h], 0
0x14005daa8  mov     r8d, [rbx+18h]; unsigned int
0x14005daac  mov     rdx, [rbx+10h]; int (*)(unsigned int, const unsigned __int16 *, unsigned __int8 *, unsigned int)
0x14005dab0  mov     [rsp+58h+var_38], rcx; unsigned __int8 *
0x14005dab5  mov     rcx, rax; this
0x14005dab8  call    ?Init@CExtNotifyCallbackPacket@@QEAAHP6AJKPEBGPEAEK@ZK01K@Z; CExtNotifyCallbackPacket::Init(long (*)(ulong,ushort const *,uchar *,ulong),ulong,ushort const *,uchar *,ulong)
0x14005dabd  test    eax, eax
0x14005dabf  jnz     short loc_14005DAEE
0x14005dac1  call    cs:__imp_GetLastError
0x14005dac8  nop     dword ptr [rax+rax+00h]
0x14005dacd  mov     ebx, eax
0x14005dacf  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dad6  cmp     rcx, r15
0x14005dad9  jz      short loc_14005DB51
0x14005dadb  test    byte ptr [rcx+1Ch], 4
0x14005dadf  jz      short loc_14005DB51
0x14005dae1  cmp     byte ptr [rcx+19h], 2
0x14005dae5  jb      short loc_14005DB51
0x14005dae7  mov     edx, 10h
0x14005daec  jmp     short loc_14005DB42
0x14005daee  mov     rcx, cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA; CNotificationMap * g_pNotificationMap
0x14005daf5  mov     r9, rdi; lpOverlapped
0x14005daf8  xor     r8d, r8d; dwCompletionKey
0x14005dafb  xor     edx, edx; dwNumberOfBytesTransferred
0x14005dafd  xor     ebx, ebx
0x14005daff  mov     rcx, [rcx+8]; CompletionPort
0x14005db03  call    cs:__imp_PostQueuedCompletionStatus
0x14005db0a  nop     dword ptr [rax+rax+00h]
0x14005db0f  test    eax, eax
0x14005db11  jnz     loc_14005DBBE
0x14005db17  call    cs:__imp_GetLastError
0x14005db1e  nop     dword ptr [rax+rax+00h]
0x14005db23  mov     ebx, eax
0x14005db25  mov     rcx, cs:WPP_GLOBAL_Control
0x14005db2c  cmp     rcx, r15
0x14005db2f  jz      short loc_14005DB51
0x14005db31  test    byte ptr [rcx+1Ch], 4
0x14005db35  jz      short loc_14005DB51
0x14005db37  cmp     byte ptr [rcx+19h], 2
0x14005db3b  jb      short loc_14005DB51
0x14005db3d  mov     edx, 11h
0x14005db42  mov     rcx, [rcx+10h]
0x14005db46  mov     r9d, ebx
0x14005db49  mov     r8, r12
0x14005db4c  call    WPP_SF_d
0x14005db51  test    ebx, ebx
0x14005db53  jle     short loc_14005DB5E
0x14005db55  movzx   ebx, bx
0x14005db58  or      ebx, 80070000h
0x14005db5e  mov     rcx, [rdi+8]; lpMem
0x14005db62  call    pMemFree
0x14005db67  mov     rcx, [rdi+10h]; lpMem
0x14005db6b  call    pMemFree
0x14005db70  mov     rcx, rdi; Block
0x14005db73  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005db78  jmp     short loc_14005DBBE
0x14005db7a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005db81  cmp     rcx, r15
0x14005db84  jz      short loc_14005DBA3
0x14005db86  test    byte ptr [rcx+1Ch], 4
0x14005db8a  jz      short loc_14005DBA3
0x14005db8c  cmp     byte ptr [rcx+19h], 2
0x14005db90  jb      short loc_14005DBA3
0x14005db92  mov     rcx, [rcx+10h]
0x14005db96  mov     edx, 0Fh
0x14005db9b  mov     r8, r12
0x14005db9e  call    WPP_SF_
0x14005dba3  call    cs:__imp_GetLastError
0x14005dbaa  nop     dword ptr [rax+rax+00h]
0x14005dbaf  mov     ebx, eax
0x14005dbb1  test    eax, eax
0x14005dbb3  jle     short loc_14005DBBE
0x14005dbb5  movzx   ebx, ax
0x14005dbb8  or      ebx, 80070000h
0x14005dbbe  mov     eax, ebx
0x14005dbc0  add     rsp, 30h
0x14005dbc4  pop     r15
0x14005dbc6  pop     r12
0x14005dbc8  pop     rdi
0x14005dbc9  pop     rsi
0x14005dbca  pop     rbx
0x14005dbcb  retn
```
