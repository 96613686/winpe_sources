# AfdHandleIcmpError

- ea: `0x140019364`
- end: `0x14001967e`
- name: `AfdHandleIcmpError`
- size: `794`
- prototype: `void __fastcall(__int64, __int64, NTSTATUS)`
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400192c0`
- `0x14004e1e0`
- `0x14004e280`

## callees

- `0x140005b60`
- `0x140007120`
- `0x140008fb0`
- `0x14000f450`
- `0x1400137a0`
- `0x140019364`
- `0x14001b0d0`
- `0x14001b800`
- `0x1400504cc`
- `0x140072840`
- `0x140072980`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001964a`
- `ntoskrnl!IofCompleteRequest` at `0x14001964a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400194c9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400195fb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400194c9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400195fb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140019477`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140019477`

## pseudocode

```c
void __fastcall AfdHandleIcmpError(__int64 a1, __int64 a2, NTSTATUS a3)
{
  _OWORD *Src; // rdi
  int v6; // esi
  __int64 v7; // xmm1_8
  _QWORD **v8; // rdx
  _QWORD *v9; // rcx
  _QWORD *v10; // rax
  IRP *v11; // r14
  _QWORD **v12; // rdx
  _QWORD *v13; // rcx
  _QWORD *v14; // rax
  unsigned __int64 v15; // rdx
  unsigned int v16; // eax
  signed __int16 *BufferTag; // rax
  signed __int16 *v18; // r15
  void *v19; // rcx
  signed __int16 **v20; // rcx
  __int64 v21; // rcx
  char v22; // al
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+58h] [rbp-21h] BYREF
  _OWORD v25[2]; // [rsp+70h] [rbp-9h] BYREF
  __int16 v26; // [rsp+90h] [rbp+17h]

  Src = (_OWORD *)a2;
  if ( *(_WORD *)a1 == 0xAFD1 )
  {
    if ( a3 == -1073741249 )
    {
      if ( _bittest((const signed __int32 *)(a1 + 192), 8u) )
        return;
    }
    else if ( a3 != -1073700846 || (*(_DWORD *)(a1 + 192) & 0x200) != 0 )
    {
      return;
    }
    v26 = 0;
    memset(&LockHandle, 0, sizeof(LockHandle));
    memset(v25, 0, sizeof(v25));
    if ( a2 )
    {
      if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
      {
        v6 = SOCKADDR_SIZE(*(_WORD *)a2);
      }
      else
      {
        v6 = *(unsigned __int16 *)(a2 + 4) + 8;
        if ( ((*(_DWORD *)(a1 + 8) & 0x400000) != 0 || (*(_DWORD *)(a1 + 8) & 0x200000) != 0)
          && *(_WORD *)(a2 + 4) == 14
          && *(_WORD *)(a2 + 6) == 2 )
        {
          v7 = *(_QWORD *)(a2 + 14);
          v25[0] = *(_OWORD *)a2;
          *(_QWORD *)((char *)v25 + 14) = v7;
          if ( (unsigned __int8)AfdTdi_TA4toTA6_InPlace(v25) )
          {
            v6 = 34;
            Src = v25;
          }
        }
      }
    }
    else
    {
      v6 = 0;
    }
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
    v8 = (_QWORD **)(a1 + 96);
    while ( 1 )
    {
      v9 = *v8;
      if ( *v8 == v8 )
        break;
      if ( (_QWORD **)v9[1] != v8 )
        goto LABEL_36;
      v10 = (_QWORD *)*v9;
      if ( *(_QWORD **)(*v9 + 8LL) != v9 )
        goto LABEL_36;
      *v8 = v10;
      v11 = (IRP *)(v9 - 21);
      v10[1] = v8;
      if ( _InterlockedExchange64(v9 - 8, 0) )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_42:
        v11->IoStatus.Status = a3;
        v11->IoStatus.Information = 0;
        AfdSetupReceiveDatagramIrp(v11, 0, 0, 0, Src, v6, 0, 0, 0);
        IofCompleteRequest(v11, AfdPriorityBoost);
        return;
      }
      *v9 = 0;
    }
    v12 = (_QWORD **)(a1 + 112);
    while ( 1 )
    {
      v13 = *v12;
      if ( *v12 == v12 )
        break;
      if ( (_QWORD **)v13[1] != v12 )
        goto LABEL_36;
      v14 = (_QWORD *)*v13;
      if ( *(_QWORD **)(*v13 + 8LL) != v13 )
        goto LABEL_36;
      *v12 = v14;
      v11 = (IRP *)(v13 - 21);
      v14[1] = v12;
      if ( _InterlockedExchange64(v13 - 8, 0) )
        goto LABEL_31;
      *v13 = 0;
    }
    v11 = 0;
LABEL_31:
    v15 = *(unsigned int *)(a1 + 152);
    v16 = *(_DWORD *)(a1 + 144);
    if ( v16 < (unsigned int)v15
      && (v16 || 104 * (unsigned __int64)*(unsigned int *)(a1 + 148) < v15)
      && (BufferTag = AfdGetBufferTag(v6, *(struct _KPROCESS **)(a1 + 48), 0), (v18 = BufferTag) != 0) )
    {
      v19 = (void *)*((_QWORD *)BufferTag + 5);
      *((_DWORD *)BufferTag + 12) = a3;
      *((_DWORD *)BufferTag + 16) = 0;
      *((_DWORD *)BufferTag + 4) = 0;
      memmove(v19, Src, v6);
      *((_DWORD *)v18 + 8) = v6;
      v20 = *(signed __int16 ***)(a1 + 136);
      if ( *v20 != (signed __int16 *)(a1 + 128) )
LABEL_36:
        __fastfail(3u);
      *((_QWORD *)v18 + 1) = v20;
      *(_QWORD *)v18 = a1 + 128;
      *v20 = v18;
      *(_QWORD *)(a1 + 136) = v18;
      ++*(_DWORD *)(a1 + 148);
      AfdNotifySockEventsChangedUnderLock(a1, 1, 0);
      AfdIndicateEventSelectEvent(v21, 1, 0);
      v22 = AfdIndicatePollEvent(a1, 1, 0, &LockHandle);
      p_LockHandle = &LockHandle;
      if ( v22 )
        p_LockHandle = 0;
      AfdNotifySockIndicateEventsUnlock(a1, p_LockHandle, 0);
    }
    else
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    if ( v11 )
      goto LABEL_42;
  }
}

```

## disassembly

```asm
0x140019364  mov     [rsp-8+arg_10], rbx
0x140019369  push    rbp
0x14001936a  push    rsi
0x14001936b  push    rdi
0x14001936c  push    r12
0x14001936e  push    r13
0x140019370  push    r14
0x140019372  push    r15
0x140019374  lea     rbp, [rsp-27h]
0x140019379  sub     rsp, 0A0h
0x140019380  mov     rax, cs:__security_cookie
0x140019387  xor     rax, rsp
0x14001938a  mov     [rbp+57h+var_38], rax
0x14001938e  mov     eax, 0AFD1h
0x140019393  mov     r12d, r8d
0x140019396  mov     rdi, rdx
0x140019399  mov     rbx, rcx
0x14001939c  cmp     [rcx], ax
0x14001939f  jnz     loc_140019656
0x1400193a5  cmp     r8d, 0C000023Fh
0x1400193ac  jnz     short loc_1400193BE
0x1400193ae  bt      dword ptr [rcx+0C0h], 8
0x1400193b6  jb      loc_140019656
0x1400193bc  jmp     short loc_1400193DB
0x1400193be  cmp     r12d, 0C000A012h
0x1400193c5  jnz     loc_140019656
0x1400193cb  test    dword ptr [rcx+0C0h], 200h
0x1400193d5  jnz     loc_140019656
0x1400193db  xor     eax, eax
0x1400193dd  xorps   xmm1, xmm1
0x1400193e0  xor     r13d, r13d
0x1400193e3  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x1400193e7  mov     [rbp+57h+var_40], ax
0x1400193eb  xorps   xmm0, xmm0
0x1400193ee  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x1400193f2  movups  [rbp+57h+var_60], xmm1
0x1400193f6  movups  [rbp+57h+var_50], xmm1
0x1400193fa  test    rdx, rdx
0x1400193fd  jz      short loc_14001946C
0x1400193ff  mov     eax, [rcx+8]
0x140019402  bt      eax, 8
0x140019406  jb      short loc_14001945F
0x140019408  movzx   esi, word ptr [rdx+4]
0x14001940c  mov     eax, [rcx+8]
0x14001940f  add     esi, 8
0x140019412  bt      eax, 16h
0x140019416  jb      short loc_140019421
0x140019418  mov     eax, [rcx+8]
0x14001941b  bt      eax, 15h
0x14001941f  jnb     short loc_14001946F
0x140019421  cmp     esi, 16h
0x140019424  jnz     short loc_14001946F
0x140019426  cmp     word ptr [rdx+6], 2
0x14001942b  jnz     short loc_14001946F
0x14001942d  movups  xmm0, xmmword ptr [rdx]
0x140019430  lea     rcx, [rbp+57h+var_60]; void *
0x140019434  mov     [rbp+57h+var_80], 22h ; '"'
0x14001943b  movsd   xmm1, qword ptr [rdx+0Eh]
0x140019440  lea     rdx, [rbp+57h+var_80]
0x140019444  movups  [rbp+57h+var_60], xmm0
0x140019448  movsd   qword ptr [rbp+57h+var_60+0Eh], xmm1
0x14001944d  call    AfdTdi_TA4toTA6_InPlace
0x140019452  test    al, al
0x140019454  jz      short loc_14001946F
0x140019456  mov     esi, [rbp+57h+var_80]
0x140019459  lea     rdi, [rbp+57h+var_60]
0x14001945d  jmp     short loc_14001946F
0x14001945f  movzx   ecx, word ptr [rdx]; af
0x140019462  call    SOCKADDR_SIZE
0x140019467  movzx   esi, al
0x14001946a  jmp     short loc_14001946F
0x14001946c  mov     esi, r13d
0x14001946f  lea     rcx, [rbx+38h]; SpinLock
0x140019473  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140019477  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001947e  nop     dword ptr [rax+rax+00h]
0x140019483  lea     rdx, [rbx+60h]
0x140019487  mov     rcx, [rdx]
0x14001948a  cmp     rcx, rdx
0x14001948d  jz      short loc_1400194DA
0x14001948f  cmp     [rcx+8], rdx
0x140019493  jnz     loc_140019593
0x140019499  mov     rax, [rcx]
0x14001949c  cmp     [rax+8], rcx
0x1400194a0  jnz     loc_140019593
0x1400194a6  mov     [rdx], rax
0x1400194a9  lea     r14, [rcx-0A8h]
0x1400194b0  mov     [rax+8], rdx
0x1400194b4  mov     rax, r13
0x1400194b7  xchg    rax, [r14+68h]
0x1400194bb  test    rax, rax
0x1400194be  jnz     short loc_1400194C5
0x1400194c0  mov     [rcx], r13
0x1400194c3  jmp     short loc_140019487
0x1400194c5  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1400194c9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400194d0  nop     dword ptr [rax+rax+00h]
0x1400194d5  jmp     loc_14001960C
0x1400194da  lea     rdx, [rbx+70h]
0x1400194de  mov     rcx, [rdx]
0x1400194e1  cmp     rcx, rdx
0x1400194e4  jz      short loc_14001951C
0x1400194e6  cmp     [rcx+8], rdx
0x1400194ea  jnz     loc_140019593
0x1400194f0  mov     rax, [rcx]
0x1400194f3  cmp     [rax+8], rcx
0x1400194f7  jnz     loc_140019593
0x1400194fd  mov     [rdx], rax
0x140019500  lea     r14, [rcx-0A8h]
0x140019507  mov     [rax+8], rdx
0x14001950b  mov     rax, r13
0x14001950e  xchg    rax, [r14+68h]
0x140019512  test    rax, rax
0x140019515  jnz     short loc_14001951F
0x140019517  mov     [rcx], r13
0x14001951a  jmp     short loc_1400194DE
0x14001951c  mov     r14, r13
0x14001951f  mov     edx, [rbx+98h]
0x140019525  mov     eax, [rbx+90h]
0x14001952b  cmp     eax, edx
0x14001952d  jnb     loc_1400195F7
0x140019533  test    eax, eax
0x140019535  jnz     short loc_14001954A
0x140019537  mov     eax, [rbx+94h]
0x14001953d  imul    rcx, rax, 68h ; 'h'
0x140019541  cmp     rcx, rdx
0x140019544  jnb     loc_1400195F7
0x14001954a  mov     rdx, [rbx+30h]
0x14001954e  xor     r8d, r8d
0x140019551  mov     ecx, esi
0x140019553  call    AfdGetBufferTag
0x140019558  mov     r15, rax
0x14001955b  test    rax, rax
0x14001955e  jz      loc_1400195F7
0x140019564  mov     rcx, [rax+28h]; void *
0x140019568  mov     rdx, rdi; Src
0x14001956b  movsxd  r8, esi; Size
0x14001956e  mov     [rax+30h], r12d
0x140019572  mov     [rax+40h], r13d
0x140019576  mov     [rax+10h], r13d
0x14001957a  call    memmove
0x14001957f  lea     rax, [rbx+80h]
0x140019586  mov     [r15+20h], esi
0x14001958a  mov     rcx, [rax+8]
0x14001958e  cmp     [rcx], rax
0x140019591  jz      short loc_14001959A
0x140019593  mov     ecx, 3
0x140019598  int     29h; Win8: RtlFailFast(ecx)
0x14001959a  mov     [r15+8], rcx
0x14001959e  xor     r8d, r8d
0x1400195a1  mov     [r15], rax
0x1400195a4  mov     [rcx], r15
0x1400195a7  mov     rcx, rbx
0x1400195aa  mov     [rax+8], r15
0x1400195ae  mov     r15d, 1
0x1400195b4  add     [rbx+94h], r15d
0x1400195bb  mov     edx, r15d
0x1400195be  call    AfdNotifySockEventsChangedUnderLock
0x1400195c3  xor     r8d, r8d
0x1400195c6  mov     edx, r15d
0x1400195c9  call    AfdIndicateEventSelectEvent
0x1400195ce  lea     r9, [rbp+57h+LockHandle]
0x1400195d2  xor     r8d, r8d
0x1400195d5  mov     edx, r15d
0x1400195d8  mov     rcx, rbx
0x1400195db  call    AfdIndicatePollEvent
0x1400195e0  test    al, al
0x1400195e2  lea     rdx, [rbp+57h+LockHandle]
0x1400195e6  mov     rcx, rbx
0x1400195e9  cmovnz  rdx, r13
0x1400195ed  xor     r8d, r8d
0x1400195f0  call    AfdNotifySockIndicateEventsUnlock
0x1400195f5  jmp     short loc_140019607
0x1400195f7  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1400195fb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140019602  nop     dword ptr [rax+rax+00h]
0x140019607  test    r14, r14
0x14001960a  jz      short loc_140019656
0x14001960c  mov     [rsp+0D0h+var_88], r13d; int
0x140019611  xor     r9d, r9d
0x140019614  mov     [rsp+0D0h+var_90], r13b; char
0x140019619  xor     r8d, r8d; SourceBytesToCopy
0x14001961c  mov     [rsp+0D0h+var_98], r13d; int
0x140019621  xor     edx, edx; SourceBuffer
0x140019623  mov     [rsp+0D0h+var_A0], esi; int
0x140019627  mov     rcx, r14; Irp
0x14001962a  mov     [r14+30h], r12d
0x14001962e  mov     [rsp+0D0h+Src], rdi; Src
0x140019633  mov     [rsp+0D0h+var_B0], r13d; int
0x140019638  mov     [r14+38h], r13
0x14001963c  call    AfdSetupReceiveDatagramIrp
0x140019641  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140019647  mov     rcx, r14; Irp
0x14001964a  call    cs:__imp_IofCompleteRequest
0x140019651  nop     dword ptr [rax+rax+00h]
0x140019656  mov     rcx, [rbp+57h+var_38]
0x14001965a  xor     rcx, rsp; StackCookie
0x14001965d  call    __security_check_cookie
0x140019662  mov     rbx, [rsp+0D0h+arg_10]
0x14001966a  add     rsp, 0A0h
0x140019671  pop     r15
0x140019673  pop     r14
0x140019675  pop     r13
0x140019677  pop     r12
0x140019679  pop     rdi
0x14001967a  pop     rsi
0x14001967b  pop     rbp
0x14001967c  retn
```
