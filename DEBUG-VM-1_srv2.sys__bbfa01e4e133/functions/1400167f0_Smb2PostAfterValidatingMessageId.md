# Smb2PostAfterValidatingMessageId

- ea: `0x1400167f0`
- end: `0x140016c8f`
- name: `Smb2PostAfterValidatingMessageId`
- size: `1183`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004020`
- `0x140004960`
- `0x140005070`
- `0x1400051dc`
- `0x1400167f0`
- `0x1400222ec`
- `0x140062f00`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140016a02`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140016bd3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140016a02`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140016bd3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003cc4c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003cc4c`
- `ntoskrnl!KeSetEvent` at `0x140016c7e`
- `ntoskrnl!KeSetEvent` at `0x140016c7e`
- `ntoskrnl!KeReadStateEvent` at `0x140016a3c`
- `ntoskrnl!KeReadStateEvent` at `0x140016a3c`
- `ntoskrnl!RtlInitAnsiString` at `0x140016b4b`
- `ntoskrnl!RtlInitAnsiString` at `0x140016b4b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140016a1e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140016bee`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140016a1e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140016bee`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14001690f`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14001690f`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140016999`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140016aa3`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140016999`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140016aa3`
- `HAL!KeQueryPerformanceCounter` at `0x140016b12`
- `HAL!KeQueryPerformanceCounter` at `0x140016b12`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x140016afa`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x140016afa`

## string_xrefs

- `0x140016b31`: `Srv2PostToThreadPool`
- `0x140016bb4`: `Srv2PostToThreadPool`

## pseudocode

```c
int __fastcall Smb2PostAfterValidatingMessageId(int a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v5; // r12
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 *v8; // rdi
  __int64 v9; // r8
  __int64 v10; // r14
  unsigned __int16 v11; // ax
  __int16 v12; // ax
  unsigned int v13; // esi
  __int64 v14; // rdi
  unsigned __int64 v15; // r15
  KIRQL v16; // al
  unsigned __int64 v17; // rdx
  KIRQL v18; // r10
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  __int64 v21; // r8
  char v22; // r15
  int v23; // edx
  signed __int16 v24; // ax
  int v25; // eax
  bool v26; // zf
  __int64 v27; // rdi
  __int64 v28; // rdi
  PSLIST_ENTRY v29; // rax
  unsigned int v30; // eax
  unsigned __int64 v31; // rax
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v33; // rax
  int v34; // edx
  int v35; // ecx
  __int64 v36; // rdi
  __int64 v37; // rdi
  __int64 v38; // rdx
  struct _STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF

  v4 = *(_QWORD *)(a3 + 24);
  if ( (int)(a1 + 0x80000000) >= 0 && a1 != -2147483643 )
  {
LABEL_65:
    if ( KeGetCurrentIrql() >= 2u )
    {
      v26 = *(_DWORD *)(v4 + 8) == 5;
      *(_QWORD *)(v4 + 48) = Smb2DisconnectConnectionAndCompleteWorkItem;
      *(_DWORD *)(v4 + 72) = 0;
      if ( v26 )
      {
        LOBYTE(v38) = 1;
        SRV2_PERF_ENTER_EX(v4 + 584, v38, 391, "Srv2PostToThreadPool", 1);
      }
      v36 = *(_QWORD *)(*(_QWORD *)(v4 + 64) + 136LL);
      v37 = *(_QWORD *)(v36 + 8LL * KeGetCurrentNodeNumber() + 8);
      v29 = ExpInterlockedPushEntrySList((PSLIST_HEADER)v37, (PSLIST_ENTRY)(v4 + 32));
      if ( !v29 )
      {
        LODWORD(v29) = *(unsigned __int16 *)(v37 + 66);
        if ( (_WORD)v29 )
          LODWORD(v29) = RfspThreadPoolNodeWakeIdleWorker(v37);
      }
    }
    else
    {
      LODWORD(v29) = Smb2DisconnectConnectionAndCompleteWorkItem(v4);
    }
    return (int)v29;
  }
  *(_DWORD *)(v4 + 404) += a2;
  v5 = *(_QWORD *)(v4 + 96);
  *(_DWORD *)(*(_QWORD *)(v4 + 304) + 36LL) = *(_DWORD *)(v4 + 404);
  if ( *(_DWORD *)(v4 + 404) == *(_DWORD *)(v4 + 400) )
    *(_BYTE *)(v4 + 472) = 1;
  v6 = *(_QWORD *)(v4 + 304);
  v7 = *(_QWORD *)(v6 + 24);
  v8 = *(__int64 **)(*(_QWORD *)(v4 + 96) + 496LL);
  v9 = *(unsigned int *)(v6 + 36);
  *(_QWORD *)(v4 + 528) = Smb2CleanupWorkItem;
  *(_WORD *)(v4 + 488) = 1;
  *(_WORD *)(v4 + 490) = *(_WORD *)(v7 + 14);
  if ( (unsigned int)v9 <= 4 )
  {
LABEL_42:
    v25 = -1073741616;
LABEL_43:
    *(_DWORD *)(v4 + 488) = 0;
    goto LABEL_28;
  }
  if ( *(_DWORD *)v7 != 1112364031 )
  {
    if ( (unsigned int)v9 >= 0x40 )
    {
      v10 = *(_QWORD *)(v4 + 560);
      if ( *(_BYTE *)v10 )
        goto LABEL_29;
      v11 = *(_WORD *)(v7 + 12);
      if ( v11 < 0x14u )
      {
        *(_WORD *)(v10 + 14) = v11;
        *(_QWORD *)(v10 + 176) = *(_QWORD *)(v7 + 24);
        if ( *(_WORD *)(v7 + 12) == 12 )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v4 + 96) + 510LL) || (unsigned __int8)SrvAdminAllowAnonymousAccess(v6, v7, v9, a4) )
            goto LABEL_29;
        }
        else
        {
          if ( (*((_BYTE *)v8 + 49) & 2) != 0 )
          {
            v12 = *(_WORD *)(v7 + 6);
            if ( v12 )
              *(_WORD *)(v4 + 488) = v12;
          }
          v13 = *(unsigned __int16 *)(v4 + 488);
          if ( *(_WORD *)(v4 + 488) )
          {
            v14 = *v8;
            v15 = *(_QWORD *)(v7 + 24);
            v16 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)v14);
            v17 = *(_QWORD *)(v14 + 8);
            v18 = v16;
            if ( v15 >= v17 && v15 <= *(_QWORD *)(v14 + 16) )
            {
              v19 = *(unsigned int *)(v14 + 24) - v17 + v15;
              v20 = *(unsigned int *)(v14 + 32);
              v21 = (unsigned int)(v19 - v20);
              if ( v19 < v20 )
                v21 = (unsigned int)v19;
              if ( (_DWORD)v21 != -1 )
              {
                if ( v13 <= 1 || (v31 = v15 + v13 - 1, v31 >= v15) && v31 <= *(_QWORD *)(v14 + 16) )
                {
                  v22 = 0;
                  v23 = 0;
                  while ( 1 )
                  {
                    v24 = _InterlockedCompareExchange16(
                            (volatile signed __int16 *)(2 * v21 + *(_QWORD *)(v14 + 40)),
                            2,
                            0);
                    if ( v24 )
                    {
                      if ( v24 == 2
                        || v23
                        || _InterlockedCompareExchange16(
                             (volatile signed __int16 *)(2 * v21 + *(_QWORD *)(v14 + 40)),
                             2,
                             1) != 1 )
                      {
                        goto LABEL_41;
                      }
                      v22 = 1;
                    }
                    if ( ++v23 == v13 )
                      break;
                    v30 = v21 + 1;
                    v21 = 0;
                    if ( v30 != *(_DWORD *)(v14 + 32) )
                      v21 = v30;
                  }
                  ExReleaseSpinLockShared((PEX_SPIN_LOCK)v14, v18);
                  *(_BYTE *)v10 = 1;
                  if ( v22 )
                    *(_DWORD *)(v4 + 480) = 1;
                  goto LABEL_29;
                }
              }
            }
LABEL_41:
            ExReleaseSpinLockShared((PEX_SPIN_LOCK)v14, v18);
          }
        }
      }
    }
    goto LABEL_42;
  }
  v25 = 0;
  if ( *((_WORD *)v8 + 22) != 0xFFFF )
    v25 = -1073741616;
  if ( v25 == -1073741616 )
    goto LABEL_43;
LABEL_28:
  if ( v25 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, &WPP_989bf530af953911b31e85319f536320_Traceguids, v5);
    }
    goto LABEL_65;
  }
LABEL_29:
  v26 = *(_DWORD *)(v4 + 8) == 5;
  *(_DWORD *)(v4 + 72) = 0;
  if ( v26 )
  {
    DestinationString = 0;
    if ( *(_BYTE *)(v4 + 600) )
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      v33 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SRV2_PERF_UPDATE_PERF_COUNTER)(
              v4 + 584,
              1,
              (LARGE_INTEGER)PerformanceCounter.QuadPart);
      *(_BYTE *)(v4 + 712) = 1;
      *(_QWORD *)(v4 + 720) = v33;
      RtlInitAnsiString(&DestinationString, "Srv2PostToThreadPool");
      if ( (Microsoft_Windows_SMBServerEnableBits & 4) != 0 )
        McTemplateK0qqhsr2_EtwWriteTransfer(
          v35,
          v34,
          v4 + 584,
          1,
          135,
          DestinationString.Length,
          (__int64)DestinationString.Buffer);
    }
  }
  v27 = *(_QWORD *)(*(_QWORD *)(v4 + 64) + 136LL);
  v28 = *(_QWORD *)(v27 + 8LL * KeGetCurrentNodeNumber() + 8);
  v29 = ExpInterlockedPushEntrySList((PSLIST_HEADER)(v28 + 16), (PSLIST_ENTRY)(v4 + 32));
  if ( !v29 )
  {
    LODWORD(v29) = *(unsigned __int16 *)(v28 + 66);
    if ( (_WORD)v29 )
    {
      LODWORD(v29) = KeReadStateEvent((PRKEVENT)(v28 + 72));
      if ( !(_DWORD)v29 )
        LODWORD(v29) = KeSetEvent((PRKEVENT)(v28 + 72), 0, 0);
    }
  }
  return (int)v29;
}

```

## disassembly

```asm
0x1400167f0  push    rbx
0x1400167f2  push    rbp
0x1400167f3  push    rsi
0x1400167f4  push    rdi
0x1400167f5  push    r12
0x1400167f7  push    r13
0x1400167f9  push    r14
0x1400167fb  push    r15
0x1400167fd  sub     rsp, 58h
0x140016801  mov     rbx, [r8+18h]
0x140016805  mov     r8d, 80000000h
0x14001680b  lea     eax, [rcx+r8]
0x14001680f  test    r8d, eax
0x140016812  jz      loc_140016A62
0x140016818  add     [rbx+194h], edx
0x14001681e  mov     rax, [rbx+130h]
0x140016825  mov     r12, [rbx+60h]
0x140016829  mov     ecx, [rbx+194h]
0x14001682f  mov     [rax+24h], ecx
0x140016832  mov     eax, [rbx+190h]
0x140016838  cmp     [rbx+194h], eax
0x14001683e  jz      loc_140016C1D
0x140016844  mov     rcx, [rbx+130h]
0x14001684b  mov     r13d, 1
0x140016851  mov     rax, [rbx+60h]
0x140016855  xor     ebp, ebp
0x140016857  mov     rdx, [rcx+18h]
0x14001685b  mov     rdi, [rax+1F0h]
0x140016862  lea     rax, Smb2CleanupWorkItem
0x140016869  mov     r8d, [rcx+24h]
0x14001686d  mov     [rbx+210h], rax
0x140016874  mov     [rbx+1E8h], r13w
0x14001687c  movzx   eax, word ptr [rdx+0Eh]
0x140016880  mov     [rbx+1EAh], ax
0x140016887  cmp     r8d, 4
0x14001688b  jbe     loc_140016AAF
0x140016891  cmp     dword ptr [rdx], 424D53FFh
0x140016897  jz      loc_1400169B6
0x14001689d  cmp     r8d, 40h ; '@'
0x1400168a1  jb      loc_140016AAF
0x1400168a7  mov     r14, [rbx+230h]
0x1400168ae  cmp     [r14], bpl
0x1400168b1  jnz     loc_1400169D9
0x1400168b7  movzx   eax, word ptr [rdx+0Ch]
0x1400168bb  cmp     ax, 14h
0x1400168bf  jnb     loc_140016AAF
0x1400168c5  mov     [r14+0Eh], ax
0x1400168ca  mov     rax, [rdx+18h]
0x1400168ce  mov     [r14+0B0h], rax
0x1400168d5  cmp     word ptr [rdx+0Ch], 0Ch
0x1400168da  jz      loc_140016AE9
0x1400168e0  test    byte ptr [rdi+31h], 2
0x1400168e4  jz      short loc_1400168F6
0x1400168e6  movzx   eax, word ptr [rdx+6]
0x1400168ea  test    ax, ax
0x1400168ed  jz      short loc_1400168F6
0x1400168ef  mov     [rbx+1E8h], ax
0x1400168f6  movzx   esi, word ptr [rbx+1E8h]
0x1400168fd  test    esi, esi
0x1400168ff  jz      loc_140016AAF
0x140016905  mov     rdi, [rdi]
0x140016908  mov     r15, [rdx+18h]
0x14001690c  mov     rcx, rdi; SpinLock
0x14001690f  call    cs:__imp_ExAcquireSpinLockShared
0x140016916  nop     dword ptr [rax+rax+00h]
0x14001691b  mov     rdx, [rdi+8]
0x14001691f  movzx   r10d, al
0x140016923  cmp     r15, rdx
0x140016926  jb      loc_140016A9C
0x14001692c  cmp     r15, [rdi+10h]
0x140016930  ja      loc_140016A9C
0x140016936  mov     ecx, [rdi+18h]
0x140016939  sub     rcx, rdx
0x14001693c  lea     rdx, [rcx+r15]
0x140016940  mov     ecx, [rdi+20h]
0x140016943  mov     r8d, edx
0x140016946  sub     r8d, ecx
0x140016949  cmp     rdx, rcx
0x14001694c  cmovb   r8d, edx
0x140016950  cmp     r8d, 0FFFFFFFFh
0x140016954  jz      loc_140016A9C
0x14001695a  cmp     esi, r13d
0x14001695d  ja      loc_140016AD2
0x140016963  xor     r15b, r15b
0x140016966  mov     edx, ebp
0x140016968  mov     r11d, 2
0x14001696e  mov     rcx, [rdi+28h]
0x140016972  lea     r9, [r8+r8]
0x140016976  xor     eax, eax
0x140016978  lock cmpxchg [r9+rcx], r11w
0x14001697f  test    ax, ax
0x140016982  jnz     loc_140016A75
0x140016988  inc     edx
0x14001698a  cmp     edx, esi
0x14001698c  jnz     loc_140016ABF
0x140016992  movzx   edx, r10b; OldIrql
0x140016996  mov     rcx, rdi; SpinLock
0x140016999  call    cs:__imp_ExReleaseSpinLockShared
0x1400169a0  nop     dword ptr [rax+rax+00h]
0x1400169a5  mov     [r14], r13b
0x1400169a8  test    r15b, r15b
0x1400169ab  jz      short loc_1400169D9
0x1400169ad  mov     [rbx+1E0h], r13d
0x1400169b4  jmp     short loc_1400169D9
0x1400169b6  mov     edx, 0FFFFh
0x1400169bb  mov     eax, ebp
0x1400169bd  cmp     [rdi+2Ch], dx
0x1400169c1  mov     ecx, 0C00000D0h
0x1400169c6  cmovnz  eax, ecx
0x1400169c9  cmp     eax, ecx
0x1400169cb  jz      loc_140016AB4
0x1400169d1  test    eax, eax
0x1400169d3  js      loc_140016C29
0x1400169d9  cmp     dword ptr [rbx+8], 5
0x1400169dd  mov     [rbx+48h], ebp
0x1400169e0  jnz     short loc_1400169F7
0x1400169e2  xorps   xmm0, xmm0
0x1400169e5  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x1400169ea  cmp     [rbx+258h], bpl
0x1400169f1  jnz     loc_140016B10
0x1400169f7  mov     rax, [rbx+40h]
0x1400169fb  mov     rdi, [rax+88h]
0x140016a02  call    cs:__imp_KeGetCurrentNodeNumber
0x140016a09  nop     dword ptr [rax+rax+00h]
0x140016a0e  movzx   eax, ax
0x140016a11  lea     rdx, [rbx+20h]; ListEntry
0x140016a15  mov     rdi, [rdi+rax*8+8]
0x140016a1a  lea     rcx, [rdi+10h]; ListHead
0x140016a1e  call    cs:__imp_ExpInterlockedPushEntrySList
0x140016a25  nop     dword ptr [rax+rax+00h]
0x140016a2a  test    rax, rax
0x140016a2d  jnz     short loc_140016A50
0x140016a2f  movzx   eax, word ptr [rdi+42h]
0x140016a33  cmp     bp, ax
0x140016a36  jz      short loc_140016A50
0x140016a38  lea     rcx, [rdi+48h]; Event
0x140016a3c  call    cs:__imp_KeReadStateEvent
0x140016a43  nop     dword ptr [rax+rax+00h]
0x140016a48  test    eax, eax
0x140016a4a  jz      loc_140016C75
0x140016a50  add     rsp, 58h
0x140016a54  pop     r15
0x140016a56  pop     r14
0x140016a58  pop     r13
0x140016a5a  pop     r12
0x140016a5c  pop     rdi
0x140016a5d  pop     rsi
0x140016a5e  pop     rbp
0x140016a5f  pop     rbx
0x140016a60  retn
0x140016a62  cmp     ecx, 80000005h
0x140016a68  jz      loc_140016818
0x140016a6e  xor     ebp, ebp
0x140016a70  jmp     loc_14003CC4C
0x140016a75  cmp     ax, r11w
0x140016a79  jz      short loc_140016A9C
0x140016a7b  test    edx, edx
0x140016a7d  jnz     short loc_140016A9C
0x140016a7f  mov     rcx, [rdi+28h]
0x140016a83  mov     eax, r13d
0x140016a86  lock cmpxchg [r9+rcx], r11w
0x140016a8d  cmp     ax, r13w
0x140016a91  jnz     short loc_140016A9C
0x140016a93  movzx   r15d, r13b
0x140016a97  jmp     loc_140016988
0x140016a9c  movzx   edx, r10b; OldIrql
0x140016aa0  mov     rcx, rdi; SpinLock
0x140016aa3  call    cs:__imp_ExReleaseSpinLockShared
0x140016aaa  nop     dword ptr [rax+rax+00h]
0x140016aaf  mov     eax, 0C00000D0h
0x140016ab4  mov     [rbx+1E8h], ebp
0x140016aba  jmp     loc_1400169D1
0x140016abf  lea     eax, [r8+1]
0x140016ac3  mov     r8d, ebp
0x140016ac6  cmp     eax, [rdi+20h]
0x140016ac9  cmovnz  r8d, eax
0x140016acd  jmp     loc_14001696E
0x140016ad2  lea     eax, [rsi-1]
0x140016ad5  add     rax, r15
0x140016ad8  cmp     rax, r15
0x140016adb  jb      short loc_140016A9C
0x140016add  cmp     rax, [rdi+10h]
0x140016ae1  jbe     loc_140016963
0x140016ae7  jmp     short loc_140016A9C
0x140016ae9  mov     rax, [rbx+60h]
0x140016aed  cmp     [rax+1FEh], bpl
0x140016af4  jnz     loc_1400169D9
0x140016afa  call    cs:__imp_SrvAdminAllowAnonymousAccess
0x140016b01  nop     dword ptr [rax+rax+00h]
0x140016b06  test    al, al
0x140016b08  jnz     loc_1400169D9
0x140016b0e  jmp     short loc_140016AAF
0x140016b10  xor     ecx, ecx; PerformanceFrequency
0x140016b12  call    cs:__imp_KeQueryPerformanceCounter
0x140016b19  nop     dword ptr [rax+rax+00h]
0x140016b1e  movzx   edx, r13b
0x140016b22  lea     rcx, [rbx+248h]
0x140016b29  mov     r8, rax
0x140016b2c  call    SRV2_PERF_UPDATE_PERF_COUNTER
0x140016b31  lea     rdx, SourceString; "Srv2PostToThreadPool"
0x140016b38  mov     [rbx+2C8h], r13b
0x140016b3f  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x140016b44  mov     [rbx+2D0h], rax
0x140016b4b  call    cs:__imp_RtlInitAnsiString
0x140016b52  nop     dword ptr [rax+rax+00h]
0x140016b57  test    cs:Microsoft_Windows_SMBServerEnableBits, 4
0x140016b5e  jz      loc_1400169F7
0x140016b64  mov     rax, [rsp+98h+DestinationString.Buffer]
0x140016b69  lea     r8, [rbx+248h]
0x140016b70  mov     [rsp+98h+var_68], rax
0x140016b75  mov     r9d, r13d
0x140016b78  movzx   eax, [rsp+98h+DestinationString.Length]
0x140016b7d  mov     [rsp+98h+var_70], ax
0x140016b82  mov     [rsp+98h+var_78], 187h
0x140016b8a  call    McTemplateK0qqhsr2_EtwWriteTransfer
0x140016b8f  jmp     loc_1400169F7
0x140016b94  cmp     dword ptr [rbx+8], 5
0x140016b98  lea     rax, Smb2DisconnectConnectionAndCompleteWorkItem
0x140016b9f  mov     [rbx+30h], rax
0x140016ba3  mov     [rbx+48h], ebp
0x140016ba6  jnz     short loc_140016BC8
0x140016ba8  lea     rcx, [rbx+248h]
0x140016baf  mov     byte ptr [rsp+98h+var_78], 1
0x140016bb4  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140016bbb  mov     r8d, 187h
0x140016bc1  mov     dl, 1
0x140016bc3  call    SRV2_PERF_ENTER_EX
0x140016bc8  mov     rax, [rbx+40h]
0x140016bcc  mov     rdi, [rax+88h]
0x140016bd3  call    cs:__imp_KeGetCurrentNodeNumber
0x140016bda  nop     dword ptr [rax+rax+00h]
0x140016bdf  movzx   eax, ax
0x140016be2  lea     rdx, [rbx+20h]; ListEntry
0x140016be6  mov     rdi, [rdi+rax*8+8]
0x140016beb  mov     rcx, rdi; ListHead
0x140016bee  call    cs:__imp_ExpInterlockedPushEntrySList
0x140016bf5  nop     dword ptr [rax+rax+00h]
0x140016bfa  test    rax, rax
0x140016bfd  jnz     loc_140016A50
0x140016c03  movzx   eax, word ptr [rdi+42h]
0x140016c07  cmp     bp, ax
0x140016c0a  jz      loc_140016A50
0x140016c10  mov     rcx, rdi
0x140016c13  call    RfspThreadPoolNodeWakeIdleWorker
0x140016c18  jmp     loc_140016A50
0x140016c1d  mov     byte ptr [rbx+1D8h], 1
0x140016c24  jmp     loc_140016844
0x140016c29  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c30  lea     rax, WPP_GLOBAL_Control
0x140016c37  cmp     rcx, rax
0x140016c3a  jz      loc_14003CC4C
0x140016c40  test    dword ptr [rcx+2Ch], 200h
0x140016c47  jz      loc_14003CC4C
0x140016c4d  cmp     [rcx+29h], r13b
0x140016c51  jb      loc_14003CC4C
0x140016c57  mov     rcx, [rcx+18h]
0x140016c5b  lea     r8, WPP_989bf530af953911b31e85319f536320_Traceguids
0x140016c62  mov     edx, 0Fh
0x140016c67  mov     r9, r12
0x140016c6a  call    WPP_SF_q
0x140016c6f  nop
0x140016c70  jmp     loc_14003CC4C
0x140016c75  xor     r8d, r8d; Wait
0x140016c78  lea     rcx, [rdi+48h]; Event
0x140016c7c  xor     edx, edx; Increment
0x140016c7e  call    cs:__imp_KeSetEvent
0x140016c85  nop     dword ptr [rax+rax+00h]
0x140016c8a  jmp     loc_140016A50
0x14003cc4c  call    cs:__imp_KeGetCurrentIrql
0x14003cc53  nop     dword ptr [rax+rax+00h]
0x14003cc58  cmp     al, 2
0x14003cc5a  jnb     loc_140016B94
0x14003cc60  mov     rcx, rbx
0x14003cc63  call    Smb2DisconnectConnectionAndCompleteWorkItem
0x14003cc68  nop
0x14003cc69  jmp     loc_140016A50
```
