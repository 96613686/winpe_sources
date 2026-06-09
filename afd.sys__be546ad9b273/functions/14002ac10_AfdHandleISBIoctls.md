# AfdHandleISBIoctls

- ea: `0x14002ac10`
- end: `0x14002aff0`
- name: `AfdHandleISBIoctls`
- size: `992`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002a1e0`

## callees

- `0x14001c708`
- `0x14001e7e0`
- `0x14001ebf4`
- `0x14002ac10`
- `0x14002fd7c`
- `0x140066bc0`
- `0x140092254`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002afd4`
- `ntoskrnl!IofCompleteRequest` at `0x14002afd4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002adf9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002af28`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002af4b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002adf9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002af28`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002af4b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002adc8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002ae72`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002adc8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002ae72`
- `ntoskrnl!IoIs32bitProcess` at `0x14002aca7`
- `ntoskrnl!IoIs32bitProcess` at `0x14002aca7`
- `ntoskrnl!ProbeForWrite` at `0x14002acbf`
- `ntoskrnl!ProbeForWrite` at `0x14002acbf`

## pseudocode

```c
__int64 __fastcall AfdHandleISBIoctls(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 ConnectionReferenceFromEndpoint; // r14
  __int64 v5; // r12
  int v6; // ebx
  __int64 *v7; // r15
  unsigned int v8; // eax
  signed __int32 v9; // edx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  __int64 *i; // rcx
  __int64 **v15; // rcx
  __int64 v16; // rax
  __int64 **v17; // rcx
  signed __int64 v18; // rax
  bool v19; // cc
  signed __int64 v20; // rax
  unsigned int *v22; // [rsp+28h] [rbp-60h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-48h] BYREF
  char v24; // [rsp+A0h] [rbp+18h]
  unsigned int v25; // [rsp+A8h] [rbp+20h] BYREF

  ConnectionReferenceFromEndpoint = 0;
  v22 = 0;
  v24 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v5 = *(_QWORD *)(*(_QWORD *)(a3 + 48) + 24LL);
  *(_QWORD *)(a2 + 56) = 0;
  if ( *(_QWORD *)(a1 + 24) )
  {
    v6 = -1073741811;
    goto LABEL_48;
  }
  v7 = (__int64 *)(a3 + 8);
  v8 = *(_DWORD *)(a3 + 8);
  if ( *(_DWORD *)(a1 + 8) == 1074033787 )
  {
    if ( v8 < 4 )
    {
      v6 = -1073741811;
      goto LABEL_48;
    }
    if ( *(_BYTE *)(a2 + 64) )
    {
      IoIs32bitProcess((PIRP)a2);
      ProbeForWrite(*(volatile void **)(a2 + 112), 4u, 4u);
    }
    v22 = *(unsigned int **)(a2 + 112);
    do
    {
LABEL_11:
      v9 = *(_DWORD *)(v5 + 368);
      if ( v9 > 0 )
      {
        v6 = -1073741436;
        goto LABEL_48;
      }
    }
    while ( v9 != _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 368), v9 - 1, v9) );
    v24 = 1;
    if ( *(_WORD *)v5 == 0xAFD1 )
    {
      v6 = -1073741637;
      goto LABEL_48;
    }
    if ( (*(_WORD *)v5 & 0xAFD2) == 0xAFD2 && *(_BYTE *)(v5 + 2) == 4 )
      ConnectionReferenceFromEndpoint = AfdGetConnectionReferenceFromEndpoint(v5);
    if ( !ConnectionReferenceFromEndpoint )
    {
      v6 = -1073741504;
      goto LABEL_48;
    }
    v6 = AfdCheckISBEvents(ConnectionReferenceFromEndpoint, (unsigned int)AfdTLSockOptEnable);
    if ( v6 >= 0 )
    {
      if ( v22 )
      {
        v25 = 0;
        v10 = *(_DWORD *)(v5 + 8);
        if ( (v10 & 0x800) == 0 && (*(_BYTE *)(ConnectionReferenceFromEndpoint + 4) & 0x10) == 0 && (v10 & 0x10000) == 0 )
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
          v11 = *(_DWORD *)(ConnectionReferenceFromEndpoint + 4);
          if ( (v11 & 0x200000) == 0 )
          {
            *(_DWORD *)(ConnectionReferenceFromEndpoint + 4) = v11 | 0x200000;
            *(_DWORD *)(ConnectionReferenceFromEndpoint + 148) = AfdSendWindowSize;
          }
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          v6 = AfdQueryISB(ConnectionReferenceFromEndpoint, &v25);
          if ( v6 >= 0 )
          {
            if ( *(_BYTE *)(a2 + 64) )
              RtlWriteULongToUser(v22, v25);
            else
              *v22 = v25;
            *(_QWORD *)(a2 + 56) = 4;
          }
          goto LABEL_48;
        }
      }
      else
      {
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
        *(_DWORD *)(*(_QWORD *)(v5 + 192) + 4LL) |= 0x4000000u;
        v12 = *(_DWORD *)(v5 + 8);
        if ( (v12 & 0x800) == 0 && (*(_BYTE *)(ConnectionReferenceFromEndpoint + 4) & 0x10) == 0 && (v12 & 0x10000) == 0 )
        {
          v13 = v5 + 296;
          for ( i = *(__int64 **)(v5 + 296); i != (__int64 *)v13; i = (__int64 *)*i )
          {
            if ( (char (__fastcall *)(__int64, __int64))i[2] == AfdCleanupISBChange )
              goto LABEL_43;
          }
          v7[2] = (__int64)AfdCleanupISBChange;
          v7[3] = a2;
          v15 = *(__int64 ***)(v5 + 304);
          if ( *v15 != (__int64 *)v13 )
            goto LABEL_46;
          *v7 = v13;
          v7[1] = (__int64)v15;
          *v15 = v7;
          *(_QWORD *)(v5 + 304) = v7;
          _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)AfdCancelISBChange);
          if ( !*(_BYTE *)(a2 + 68) || !_InterlockedExchange64((volatile __int64 *)(a2 + 104), 0) )
          {
            *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            v6 = 259;
            goto LABEL_48;
          }
          v16 = *v7;
          if ( *(__int64 **)(*v7 + 8) != v7 || (v17 = (__int64 **)v7[1], *v17 != v7) )
LABEL_46:
            __fastfail(3u);
          *v17 = (__int64 *)v16;
          *(_QWORD *)(v16 + 8) = v17;
        }
LABEL_43:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      v6 = -1073741536;
    }
  }
  else
  {
    if ( !v8 )
      goto LABEL_11;
    v6 = -1073741811;
  }
LABEL_48:
  if ( v24 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 368));
  if ( ConnectionReferenceFromEndpoint )
  {
    v18 = _InterlockedExchangeAdd64(
            (volatile signed __int64 *)(ConnectionReferenceFromEndpoint + 48),
            0xFFFFFFFFFFFFFFFFuLL);
    v19 = v18 <= 1;
    v20 = v18 - 1;
    if ( v19 )
    {
      if ( v20 )
        __fastfail(0xEu);
      AfdCloseConnection(ConnectionReferenceFromEndpoint);
    }
  }
  if ( v6 != 259 )
  {
    *(_DWORD *)(a2 + 48) = v6;
    IofCompleteRequest((PIRP)a2, AfdPriorityBoost);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002ac10  mov     [rsp+arg_8], rdx
0x14002ac15  push    rbx
0x14002ac16  push    rsi
0x14002ac17  push    r12
0x14002ac19  push    r14
0x14002ac1b  push    r15
0x14002ac1d  sub     rsp, 60h
0x14002ac21  mov     rsi, rdx
0x14002ac24  xor     r14d, r14d
0x14002ac27  mov     [rsp+88h+var_58], r14
0x14002ac2c  mov     [rsp+88h+var_60], r14
0x14002ac31  mov     [rsp+88h+arg_10], r14b
0x14002ac39  xorps   xmm0, xmm0
0x14002ac3c  xor     eax, eax
0x14002ac3e  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14002ac43  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14002ac48  mov     [rsp+88h+var_68], 0C0000030h
0x14002ac50  mov     rax, [r8+30h]
0x14002ac54  mov     r12, [rax+18h]
0x14002ac58  mov     [rsp+88h+var_50], r12
0x14002ac5d  mov     [rdx+38h], r14
0x14002ac61  cmp     [rcx+18h], r14
0x14002ac65  jz      short loc_14002AC78
0x14002ac67  mov     [rsp+88h+var_68], 0C000000Dh
0x14002ac6f  mov     ebx, [rsp+88h+var_68]
0x14002ac73  jmp     loc_14002AF82
0x14002ac78  lea     r15, [r8+8]
0x14002ac7c  mov     eax, [r15]
0x14002ac7f  cmp     dword ptr [rcx+8], 4004747Bh
0x14002ac86  jnz     short loc_14002ACD6
0x14002ac88  cmp     eax, 4
0x14002ac8b  jnb     short loc_14002AC9E
0x14002ac8d  mov     [rsp+88h+var_68], 0C000000Dh
0x14002ac95  mov     ebx, [rsp+88h+var_68]
0x14002ac99  jmp     loc_14002AF82
0x14002ac9e  cmp     byte ptr [rdx+40h], 0
0x14002aca2  jz      short loc_14002ACCB
0x14002aca4  mov     rcx, rsi; Irp
0x14002aca7  call    cs:__imp_IoIs32bitProcess
0x14002acae  nop     dword ptr [rax+rax+00h]
0x14002acb3  mov     edx, 4; Length
0x14002acb8  mov     r8d, edx; Alignment
0x14002acbb  mov     rcx, [rsi+70h]; Address
0x14002acbf  call    cs:__imp_ProbeForWrite
0x14002acc6  nop     dword ptr [rax+rax+00h]
0x14002accb  mov     rax, [rsi+70h]
0x14002accf  mov     [rsp+88h+var_60], rax
0x14002acd4  jmp     short loc_14002ACEB
0x14002acd6  test    eax, eax
0x14002acd8  jz      short loc_14002ACEB
0x14002acda  mov     [rsp+88h+var_68], 0C000000Dh
0x14002ace2  mov     ebx, [rsp+88h+var_68]
0x14002ace6  jmp     loc_14002AF82
0x14002aceb  mov     edx, [r12+170h]
0x14002acf3  test    edx, edx
0x14002acf5  jg      loc_14002AF65
0x14002acfb  lea     ecx, [rdx-1]
0x14002acfe  mov     eax, edx
0x14002ad00  lock cmpxchg [r12+170h], ecx
0x14002ad0a  jnz     short loc_14002ACEB
0x14002ad0c  test    edx, edx
0x14002ad0e  jg      loc_14002AF65
0x14002ad14  mov     [rsp+88h+arg_10], 1
0x14002ad1c  movzx   eax, word ptr [r12]
0x14002ad21  mov     ecx, 0AFD1h
0x14002ad26  cmp     ax, cx
0x14002ad29  jnz     short loc_14002AD35
0x14002ad2b  mov     ebx, 0C00000BBh
0x14002ad30  jmp     loc_14002AF82
0x14002ad35  mov     ecx, 0AFD2h
0x14002ad3a  and     ax, cx
0x14002ad3d  cmp     ax, cx
0x14002ad40  jnz     short loc_14002AD5A
0x14002ad42  cmp     byte ptr [r12+2], 4
0x14002ad48  jnz     short loc_14002AD5A
0x14002ad4a  mov     rcx, r12
0x14002ad4d  call    AfdGetConnectionReferenceFromEndpoint
0x14002ad52  mov     r14, rax
0x14002ad55  mov     [rsp+88h+var_58], rax
0x14002ad5a  test    r14, r14
0x14002ad5d  jnz     short loc_14002AD69
0x14002ad5f  mov     ebx, 0C0000140h
0x14002ad64  jmp     loc_14002AF82
0x14002ad69  mov     edx, cs:AfdTLSockOptEnable
0x14002ad6f  mov     rcx, r14
0x14002ad72  call    AfdCheckISBEvents
0x14002ad77  mov     ebx, eax
0x14002ad79  test    eax, eax
0x14002ad7b  js      loc_14002AF82
0x14002ad81  cmp     [rsp+88h+var_60], 0
0x14002ad87  jz      loc_14002AE68
0x14002ad8d  mov     [rsp+88h+arg_18], 0
0x14002ad98  mov     eax, [r12+8]
0x14002ad9d  bt      eax, 0Bh
0x14002ada1  jb      loc_14002AF34
0x14002ada7  test    byte ptr [r14+4], 10h
0x14002adac  setz    cl
0x14002adaf  bt      eax, 10h
0x14002adb3  setnb   al
0x14002adb6  test    al, cl
0x14002adb8  jz      loc_14002AF34
0x14002adbe  lea     rcx, [r12+38h]; SpinLock
0x14002adc3  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14002adc8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002adcf  nop     dword ptr [rax+rax+00h]
0x14002add4  mov     eax, [r14+4]
0x14002add8  mov     ecx, 200000h
0x14002addd  test    ecx, eax
0x14002addf  jnz     short loc_14002ADF4
0x14002ade1  or      eax, ecx
0x14002ade3  mov     [r14+4], eax
0x14002ade7  mov     eax, cs:AfdSendWindowSize
0x14002aded  mov     [r14+94h], eax
0x14002adf4  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14002adf9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002ae00  nop     dword ptr [rax+rax+00h]
0x14002ae05  lea     rdx, [rsp+88h+arg_18]
0x14002ae0d  mov     rcx, r14
0x14002ae10  call    AfdQueryISB
0x14002ae15  mov     ebx, eax
0x14002ae17  mov     [rsp+88h+var_68], eax
0x14002ae1b  test    eax, eax
0x14002ae1d  js      loc_14002AF82
0x14002ae23  mov     eax, [rsp+88h+arg_18]
0x14002ae2a  mov     rcx, [rsp+88h+var_60]
0x14002ae2f  cmp     byte ptr [rsi+40h], 0
0x14002ae33  jz      short loc_14002AE3E
0x14002ae35  mov     edx, eax
0x14002ae37  call    RtlWriteULongToUser
0x14002ae3c  jmp     short loc_14002AE40
0x14002ae3e  mov     [rcx], eax
0x14002ae40  mov     qword ptr [rsi+38h], 4
0x14002ae48  jmp     loc_14002AF82
0x14002ae4d  mov     rsi, [rsp+88h+arg_8]
0x14002ae55  mov     r12, [rsp+88h+var_50]
0x14002ae5a  mov     r14, [rsp+88h+var_58]
0x14002ae5f  mov     ebx, [rsp+88h+var_68]
0x14002ae63  jmp     loc_14002AF82
0x14002ae68  lea     rcx, [r12+38h]; SpinLock
0x14002ae6d  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14002ae72  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002ae79  nop     dword ptr [rax+rax+00h]
0x14002ae7e  mov     rax, [r12+0C0h]
0x14002ae86  bts     dword ptr [rax+4], 1Ah
0x14002ae8b  mov     eax, [r12+8]
0x14002ae90  bt      eax, 0Bh
0x14002ae94  jb      loc_14002AF23
0x14002ae9a  test    byte ptr [r14+4], 10h
0x14002ae9f  setz    cl
0x14002aea2  bt      eax, 10h
0x14002aea6  setnb   al
0x14002aea9  test    al, cl
0x14002aeab  jz      short loc_14002AF23
0x14002aead  lea     rax, [r12+128h]
0x14002aeb5  mov     rcx, [rax]
0x14002aeb8  lea     rdx, AfdCleanupISBChange
0x14002aebf  cmp     rcx, rax
0x14002aec2  jz      short loc_14002AECF
0x14002aec4  cmp     [rcx+10h], rdx
0x14002aec8  jz      short loc_14002AF23
0x14002aeca  mov     rcx, [rcx]
0x14002aecd  jmp     short loc_14002AEBF
0x14002aecf  mov     [r15+10h], rdx
0x14002aed3  mov     [r15+18h], rsi
0x14002aed7  mov     rcx, [rax+8]
0x14002aedb  cmp     [rcx], rax
0x14002aede  jnz     short loc_14002AF5E
0x14002aee0  mov     [r15], rax
0x14002aee3  mov     [r15+8], rcx
0x14002aee7  mov     [rcx], r15
0x14002aeea  mov     [rax+8], r15
0x14002aeee  lea     rax, AfdCancelISBChange
0x14002aef5  xchg    rax, [rsi+68h]
0x14002aef9  cmp     byte ptr [rsi+44h], 0
0x14002aefd  jz      short loc_14002AF3B
0x14002aeff  xor     eax, eax
0x14002af01  xchg    rax, [rsi+68h]
0x14002af05  test    rax, rax
0x14002af08  jz      short loc_14002AF3B
0x14002af0a  mov     rax, [r15]
0x14002af0d  cmp     [rax+8], r15
0x14002af11  jnz     short loc_14002AF5E
0x14002af13  mov     rcx, [r15+8]
0x14002af17  cmp     [rcx], r15
0x14002af1a  jnz     short loc_14002AF5E
0x14002af1c  mov     [rcx], rax
0x14002af1f  mov     [rax+8], rcx
0x14002af23  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14002af28  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002af2f  nop     dword ptr [rax+rax+00h]
0x14002af34  mov     ebx, 0C0000120h
0x14002af39  jmp     short loc_14002AF82
0x14002af3b  mov     rax, [rsi+0B8h]
0x14002af42  or      byte ptr [rax+3], 1
0x14002af46  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14002af4b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002af52  nop     dword ptr [rax+rax+00h]
0x14002af57  mov     ebx, 103h
0x14002af5c  jmp     short loc_14002AF82
0x14002af5e  mov     ecx, 3
0x14002af63  int     29h; Win8: RtlFailFast(ecx)
0x14002af65  mov     ebx, 0C0000184h
0x14002af6a  jmp     short loc_14002AF82
0x14002af6c  mov     rsi, [rsp+88h+arg_8]
0x14002af74  mov     r12, [rsp+88h+var_50]
0x14002af79  mov     r14, [rsp+88h+var_58]
0x14002af7e  mov     ebx, [rsp+88h+var_68]
0x14002af82  cmp     [rsp+88h+arg_10], 0
0x14002af8a  jz      short loc_14002AF95
0x14002af8c  lock inc dword ptr [r12+170h]
0x14002af95  test    r14, r14
0x14002af98  jz      short loc_14002AFC0
0x14002af9a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002af9e  lock xadd [r14+30h], rax
0x14002afa4  sub     rax, 1
0x14002afa8  jg      short loc_14002AFC0
0x14002afaa  test    rax, rax
0x14002afad  jnz     short loc_14002AFB9
0x14002afaf  mov     rcx, r14
0x14002afb2  call    AfdCloseConnection
0x14002afb7  jmp     short loc_14002AFC0
0x14002afb9  mov     ecx, 0Eh
0x14002afbe  int     29h; Win8: RtlFailFast(ecx)
0x14002afc0  cmp     ebx, 103h
0x14002afc6  jz      short loc_14002AFE0
0x14002afc8  mov     [rsi+30h], ebx
0x14002afcb  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14002afd1  mov     rcx, rsi; Irp
0x14002afd4  call    cs:__imp_IofCompleteRequest
0x14002afdb  nop     dword ptr [rax+rax+00h]
0x14002afe0  mov     eax, ebx
0x14002afe2  add     rsp, 60h
0x14002afe6  pop     r15
0x14002afe8  pop     r14
0x14002afea  pop     r12
0x14002afec  pop     rsi
0x14002afed  pop     rbx
0x14002afee  retn
0x1400738b7  push    rbp
0x1400738b9  sub     rsp, 20h
0x1400738bd  mov     rbp, rdx
0x1400738c0  mov     r8, rcx
0x1400738c3  lea     r9, [rbp+20h]
0x1400738c7  mov     edx, 0B1Ch
0x1400738cc  lea     rcx, aMinioSocketsWi_10; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x1400738d3  call    AfdExceptionFilter
0x1400738d8  nop
0x1400738d9  add     rsp, 20h
0x1400738dd  pop     rbp
0x1400738de  retn
0x1400738e0  push    rbp
0x1400738e2  sub     rsp, 20h
0x1400738e6  mov     rbp, rdx
0x1400738e9  mov     r8, rcx
0x1400738ec  lea     r9, [rbp+20h]
0x1400738f0  mov     edx, 0B6Dh
0x1400738f5  lea     rcx, aMinioSocketsWi_10; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x1400738fc  call    AfdExceptionFilter
0x140073901  nop
0x140073902  add     rsp, 20h
0x140073906  pop     rbp
0x140073907  retn
```
