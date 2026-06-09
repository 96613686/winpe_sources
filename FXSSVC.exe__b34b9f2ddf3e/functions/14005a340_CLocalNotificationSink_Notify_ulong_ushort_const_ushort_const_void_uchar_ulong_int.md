# CLocalNotificationSink::Notify(ulong,ushort const *,ushort const *,void *,uchar *,ulong,int *)

- ea: `0x14005a340`
- end: `0x14005a53e`
- name: `?Notify@CLocalNotificationSink@@UEAAJKPEBG0PEAXPEAEKPEAH@Z`
- size: `510`
- prototype: `__int64 __fastcall(CLocalNotificationSink *this, __int64, const unsigned __int16 *, const unsigned __int16 *, void *, unsigned __int8 *, unsigned int, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001b8c`
- `0x1400023cc`
- `0x140004b30`
- `0x140004b58`
- `0x140059f40`
- `0x14005a340`
- `0x140065dbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005a44b`
- `KERNEL32!GetLastError` at `0x14005a495`
- `KERNEL32!GetLastError` at `0x14005a51b`
- `KERNEL32!GetLastError` at `0x14005a44b`
- `KERNEL32!GetLastError` at `0x14005a495`
- `KERNEL32!GetLastError` at `0x14005a51b`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14005a487`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14005a487`
- `KERNEL32!lstrcmpW` at `0x14005a3a4`
- `KERNEL32!lstrcmpW` at `0x14005a3a4`

## pseudocode

```c
__int64 __fastcall CLocalNotificationSink::Notify(
        CLocalNotificationSink *this,
        __int64 a2,
        const unsigned __int16 *a3,
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
0x14005a340  push    rbx
0x14005a342  push    rsi
0x14005a343  push    rdi
0x14005a344  push    r12
0x14005a346  push    r15
0x14005a348  sub     rsp, 30h
0x14005a34c  mov     rdi, r9
0x14005a34f  mov     rsi, r8
0x14005a352  mov     rbx, rcx
0x14005a355  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a35c  lea     r15, WPP_GLOBAL_Control
0x14005a363  lea     r12, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005a36a  cmp     rcx, r15
0x14005a36d  jz      short loc_14005A38C
0x14005a36f  test    byte ptr [rcx+1Ch], 4
0x14005a373  jz      short loc_14005A38C
0x14005a375  cmp     byte ptr [rcx+19h], 5
0x14005a379  jb      short loc_14005A38C
0x14005a37b  mov     rcx, [rcx+10h]
0x14005a37f  mov     edx, 0Dh
0x14005a384  mov     r8, r12
0x14005a387  call    WPP_SF_
0x14005a38c  mov     rax, [rsp+58h+arg_38]
0x14005a394  lea     rcx, Class; lpString1
0x14005a39b  mov     rdx, rdi; lpString2
0x14005a39e  mov     dword ptr [rax], 0
0x14005a3a4  call    cs:__imp_lstrcmpW
0x14005a3aa  test    eax, eax
0x14005a3ac  jnz     short loc_14005A3EF
0x14005a3ae  mov     rax, [rbx+20h]
0x14005a3b2  cmp     [rsp+58h+arg_20], rax
0x14005a3ba  jnz     short loc_14005A3EF
0x14005a3bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a3c3  cmp     rcx, r15
0x14005a3c6  jz      short loc_14005A3E8
0x14005a3c8  test    byte ptr [rcx+1Ch], 4
0x14005a3cc  jz      short loc_14005A3E8
0x14005a3ce  cmp     byte ptr [rcx+19h], 5
0x14005a3d2  jb      short loc_14005A3E8
0x14005a3d4  mov     rcx, [rcx+10h]
0x14005a3d8  mov     edx, 0Eh
0x14005a3dd  mov     r9d, eax
0x14005a3e0  mov     r8, r12
0x14005a3e3  call    WPP_SF_d
0x14005a3e8  xor     eax, eax
0x14005a3ea  jmp     loc_14005A532
0x14005a3ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14005a3f6  mov     ecx, 28h ; '('; unsigned __int64
0x14005a3fb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14005a400  mov     rdi, rax
0x14005a403  test    rax, rax
0x14005a406  jz      loc_14005A4F2
0x14005a40c  mov     ecx, [rsp+58h+arg_30]
0x14005a413  mov     r9, rsi; unsigned __int16 *
0x14005a416  mov     [rsp+58h+var_30], ecx; unsigned int
0x14005a41a  mov     rcx, [rsp+58h+arg_28]
0x14005a422  mov     qword ptr [rax+8], 0
0x14005a42a  mov     qword ptr [rax+10h], 0
0x14005a432  mov     r8d, [rbx+18h]; unsigned int
0x14005a436  mov     rdx, [rbx+10h]; int (*)(unsigned int, const unsigned __int16 *, unsigned __int8 *, unsigned int)
0x14005a43a  mov     [rsp+58h+var_38], rcx; unsigned __int8 *
0x14005a43f  mov     rcx, rax; this
0x14005a442  call    ?Init@CExtNotifyCallbackPacket@@QEAAHP6AJKPEBGPEAEK@ZK01K@Z; CExtNotifyCallbackPacket::Init(long (*)(ulong,ushort const *,uchar *,ulong),ulong,ushort const *,uchar *,ulong)
0x14005a447  test    eax, eax
0x14005a449  jnz     short loc_14005A472
0x14005a44b  call    cs:__imp_GetLastError
0x14005a451  mov     ebx, eax
0x14005a453  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a45a  cmp     rcx, r15
0x14005a45d  jz      short loc_14005A4C9
0x14005a45f  test    byte ptr [rcx+1Ch], 4
0x14005a463  jz      short loc_14005A4C9
0x14005a465  cmp     byte ptr [rcx+19h], 2
0x14005a469  jb      short loc_14005A4C9
0x14005a46b  mov     edx, 10h
0x14005a470  jmp     short loc_14005A4BA
0x14005a472  mov     rcx, cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA; CNotificationMap * g_pNotificationMap
0x14005a479  mov     r9, rdi; lpOverlapped
0x14005a47c  xor     r8d, r8d; dwCompletionKey
0x14005a47f  xor     edx, edx; dwNumberOfBytesTransferred
0x14005a481  xor     ebx, ebx
0x14005a483  mov     rcx, [rcx+8]; CompletionPort
0x14005a487  call    cs:__imp_PostQueuedCompletionStatus
0x14005a48d  test    eax, eax
0x14005a48f  jnz     loc_14005A530
0x14005a495  call    cs:__imp_GetLastError
0x14005a49b  mov     ebx, eax
0x14005a49d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a4a4  cmp     rcx, r15
0x14005a4a7  jz      short loc_14005A4C9
0x14005a4a9  test    byte ptr [rcx+1Ch], 4
0x14005a4ad  jz      short loc_14005A4C9
0x14005a4af  cmp     byte ptr [rcx+19h], 2
0x14005a4b3  jb      short loc_14005A4C9
0x14005a4b5  mov     edx, 11h
0x14005a4ba  mov     rcx, [rcx+10h]
0x14005a4be  mov     r9d, ebx
0x14005a4c1  mov     r8, r12
0x14005a4c4  call    WPP_SF_d
0x14005a4c9  test    ebx, ebx
0x14005a4cb  jle     short loc_14005A4D6
0x14005a4cd  movzx   ebx, bx
0x14005a4d0  or      ebx, 80070000h
0x14005a4d6  mov     rcx, [rdi+8]; lpMem
0x14005a4da  call    pMemFree
0x14005a4df  mov     rcx, [rdi+10h]; lpMem
0x14005a4e3  call    pMemFree
0x14005a4e8  mov     rcx, rdi; Block
0x14005a4eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005a4f0  jmp     short loc_14005A530
0x14005a4f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a4f9  cmp     rcx, r15
0x14005a4fc  jz      short loc_14005A51B
0x14005a4fe  test    byte ptr [rcx+1Ch], 4
0x14005a502  jz      short loc_14005A51B
0x14005a504  cmp     byte ptr [rcx+19h], 2
0x14005a508  jb      short loc_14005A51B
0x14005a50a  mov     rcx, [rcx+10h]
0x14005a50e  mov     edx, 0Fh
0x14005a513  mov     r8, r12
0x14005a516  call    WPP_SF_
0x14005a51b  call    cs:__imp_GetLastError
0x14005a521  mov     ebx, eax
0x14005a523  test    eax, eax
0x14005a525  jle     short loc_14005A530
0x14005a527  movzx   ebx, ax
0x14005a52a  or      ebx, 80070000h
0x14005a530  mov     eax, ebx
0x14005a532  add     rsp, 30h
0x14005a536  pop     r15
0x14005a538  pop     r12
0x14005a53a  pop     rdi
0x14005a53b  pop     rsi
0x14005a53c  pop     rbx
0x14005a53d  retn
```
