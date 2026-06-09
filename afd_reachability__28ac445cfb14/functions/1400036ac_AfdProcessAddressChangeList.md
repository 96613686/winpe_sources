# AfdProcessAddressChangeList

- ea: `0x1400036ac`
- end: `0x140003a34`
- name: `AfdProcessAddressChangeList`
- size: `904`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140003164`
- `0x140003338`
- `0x140051834`

## callees

- `0x1400036ac`
- `0x14000f450`
- `0x1400137a0`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140003715`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140003715`
- `ntoskrnl!IofCompleteRequest` at `0x140003a03`
- `ntoskrnl!IofCompleteRequest` at `0x140003a03`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003859`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003859`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000399e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000399e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003905`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000392a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003905`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000392a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003745`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003875`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003745`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003875`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000397f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400039c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000397f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400039c4`

## pseudocode

```c
PVOID *__fastcall AfdProcessAddressChangeList(__int64 a1, __int16 a2, const UNICODE_STRING *a3)
{
  __int16 v4; // r15
  __int64 i; // rdi
  PVOID *result; // rax
  __int64 *v8; // rbx
  __int64 v9; // rcx
  char v10; // si
  __int64 *v11; // r14
  int v12; // eax
  __int64 v13; // r12
  __int64 v14; // r8
  __int64 v15; // r14
  __int16 v16; // dx
  __int64 *v17; // r13
  __int64 **v18; // rax
  bool v19; // zf
  KIRQL v20; // r15
  __int64 v21; // rax
  __int64 **v22; // rcx
  __int64 **v23; // rax
  char *v24; // rcx
  __int64 v25; // rax
  IRP *v26; // rbx
  PVOID P[2]; // [rsp+20h] [rbp-40h] BYREF
  struct _KLOCK_QUEUE_HANDLE v28; // [rsp+30h] [rbp-30h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-18h] BYREF
  __int64 *v31; // [rsp+B8h] [rbp+58h]

  v4 = a2;
  i = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  *(_OWORD *)P = 0;
  if ( a2 != 17 || !a3 )
  {
LABEL_7:
    P[1] = P;
    P[0] = P;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 216), &LockHandle);
    v8 = *(__int64 **)(a1 + 200);
    v31 = (__int64 *)(a1 + 200);
    if ( v8 == (__int64 *)(a1 + 200) )
    {
LABEL_38:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      while ( 1 )
      {
        v24 = (char *)P[0];
        result = P;
        if ( P[0] == P )
          return result;
        if ( *((PVOID **)P[0] + 1) != P )
          goto LABEL_51;
        v25 = *(_QWORD *)P[0];
        if ( *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0] )
          goto LABEL_51;
        P[0] = *(PVOID *)P[0];
        *(_QWORD *)(v25 + 8) = P;
        if ( (v24[38] & 1) != 0 )
        {
          ExFreePoolWithTag(v24 - 32, 0x68646641u);
        }
        else
        {
          v26 = (IRP *)*((_QWORD *)v24 + 2);
          ExFreePoolWithTag(v24, 0x68646641u);
          v26->IoStatus.Status = 0;
          v26->IoStatus.Information = 0;
          if ( (BYTE2(xmmword_1400875E0) & 2) != 0 )
            WPP_SF_q(1041, 38, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids, v26);
          IofCompleteRequest(v26, AfdPriorityBoost);
        }
      }
    }
    while ( 1 )
    {
      v9 = v8[2];
      v10 = *((_BYTE *)v8 + 38) & 2;
      if ( (*((_BYTE *)v8 + 38) & 1) != 0 )
      {
        v11 = v8 - 4;
        v12 = *(_DWORD *)(v9 + 8) >> 20;
        v13 = 0;
        v14 = 0;
      }
      else
      {
        v15 = *(_QWORD *)(v9 + 184);
        v14 = v8[2];
        if ( v10 )
        {
          v13 = v8[3];
          v9 = 0;
          v12 = *(_DWORD *)(v13 + 4) >> 15;
        }
        else
        {
          v13 = 0;
          v9 = *(_QWORD *)(*(_QWORD *)(v15 + 48) + 24LL);
          v12 = *(_DWORD *)(v9 + 8) >> 20;
        }
        v11 = (__int64 *)(v15 + 8);
      }
      v16 = *((_WORD *)v8 + 18);
      v17 = (__int64 *)*v8;
      if ( (v16 == v4 || !v4 || v16 == 23 && v4 == 2 && (v12 & 1) != 0) && (!i || v10 || i == *(_QWORD *)(v9 + 272)) )
      {
        memset(&v28, 0, sizeof(v28));
        if ( (__int64 *)v17[1] != v8 || (v18 = (__int64 **)v8[1], *v18 != v8) )
LABEL_51:
          __fastfail(3u);
        *v18 = v17;
        v17[1] = (__int64)v18;
        v19 = (*((_BYTE *)v8 + 38) & 1) == 0;
        *v8 = 0;
        if ( !v19 || _InterlockedExchange64((volatile __int64 *)(v14 + 104), 0) )
          break;
      }
LABEL_37:
      v8 = v17;
      if ( v17 == v31 )
        goto LABEL_38;
    }
    if ( v10 )
    {
      v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 16));
    }
    else
    {
      v20 = 0;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v9 + 56), &v28);
    }
    v21 = *v11;
    if ( *v11 )
    {
      if ( *(__int64 **)(v21 + 8) != v11 )
        goto LABEL_51;
      v22 = (__int64 **)v11[1];
      if ( *v22 != v11 )
        goto LABEL_51;
      *v22 = (__int64 *)v21;
      *(_QWORD *)(v21 + 8) = v22;
      v23 = (__int64 **)P[1];
      if ( *(PVOID **)P[1] != P )
        goto LABEL_51;
      v8[1] = (__int64)P[1];
      *v8 = (__int64)P;
      *v23 = v8;
      P[1] = v8;
      if ( (*((_BYTE *)v8 + 38) & 1) != 0 )
      {
        AfdIndicateEventSelectEvent(v8[2], 4096, 0);
        if ( (unsigned __int8)AfdIndicatePollEvent(v8[2], 4096, 0, &v28) )
        {
LABEL_36:
          v4 = a2;
          goto LABEL_37;
        }
LABEL_35:
        KeReleaseInStackQueuedSpinLock(&v28);
        goto LABEL_36;
      }
    }
    else if ( v11[1] )
    {
      v11[1] = 0;
    }
    if ( v10 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 16), v20);
      goto LABEL_36;
    }
    goto LABEL_35;
  }
  for ( i = AfdTransportInfoListHead; ; i = *(_QWORD *)i )
  {
    result = (PVOID *)&AfdTransportInfoListHead;
    if ( (__int64 *)i == &AfdTransportInfoListHead )
      break;
    if ( RtlEqualUnicodeString(a3, (PCUNICODE_STRING)(i + 32), 1u) )
      goto LABEL_7;
  }
  return result;
}

```

## disassembly

```asm
0x1400036ac  mov     [rsp-38h+arg_0], rbx
0x1400036b1  mov     [rsp-38h+arg_8], dx
0x1400036b6  push    rbp
0x1400036b7  push    rsi
0x1400036b8  push    rdi
0x1400036b9  push    r12
0x1400036bb  push    r13
0x1400036bd  push    r14
0x1400036bf  push    r15
0x1400036c1  mov     rbp, rsp
0x1400036c4  sub     rsp, 60h
0x1400036c8  xor     eax, eax
0x1400036ca  xor     r14d, r14d
0x1400036cd  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400036d1  xorps   xmm0, xmm0
0x1400036d4  mov     rbx, r8
0x1400036d7  movzx   r15d, dx
0x1400036db  mov     rsi, rcx
0x1400036de  mov     edi, r14d
0x1400036e1  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400036e5  movups  xmmword ptr [rbp+P], xmm0
0x1400036e9  cmp     dx, 11h
0x1400036ed  jnz     short loc_14000372A
0x1400036ef  test    rbx, rbx
0x1400036f2  jz      short loc_14000372A
0x1400036f4  mov     rdi, cs:AfdTransportInfoListHead
0x1400036fb  lea     rax, AfdTransportInfoListHead
0x140003702  cmp     rdi, rax
0x140003705  jz      loc_140003A1B
0x14000370b  lea     rdx, [rdi+20h]; String2
0x14000370f  mov     r8b, 1; CaseInSensitive
0x140003712  mov     rcx, rbx; String1
0x140003715  call    cs:__imp_RtlEqualUnicodeString
0x14000371c  nop     dword ptr [rax+rax+00h]
0x140003721  test    al, al
0x140003723  jnz     short loc_14000372A
0x140003725  mov     rdi, [rdi]
0x140003728  jmp     short loc_1400036FB
0x14000372a  lea     rax, [rbp+P]
0x14000372e  mov     [rbp+P+8], rax
0x140003732  lea     rcx, [rsi+0D8h]; SpinLock
0x140003739  lea     rax, [rbp+P]
0x14000373d  lea     rdx, [rbp+LockHandle]; LockHandle
0x140003741  mov     [rbp+P], rax
0x140003745  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000374c  nop     dword ptr [rax+rax+00h]
0x140003751  lea     rax, [rsi+0C8h]
0x140003758  mov     rbx, [rax]
0x14000375b  mov     [rbp+arg_18], rax
0x14000375f  cmp     rbx, rax
0x140003762  jz      loc_140003926
0x140003768  mov     al, [rbx+26h]
0x14000376b  xor     r9d, r9d
0x14000376e  mov     rcx, [rbx+10h]
0x140003772  mov     sil, al
0x140003775  and     sil, 2
0x140003779  test    al, 1
0x14000377b  jz      short loc_14000378F
0x14000377d  mov     eax, [rcx+8]
0x140003780  lea     r14, [rbx-20h]
0x140003784  shr     eax, 14h
0x140003787  mov     r12d, r9d
0x14000378a  mov     r8d, r9d
0x14000378d  jmp     short loc_1400037C4
0x14000378f  mov     r14, [rcx+0B8h]
0x140003796  mov     r8, rcx
0x140003799  test    sil, sil
0x14000379c  jz      short loc_1400037AF
0x14000379e  mov     r12, [rbx+18h]
0x1400037a2  mov     rcx, r9
0x1400037a5  mov     eax, [r12+4]
0x1400037aa  shr     eax, 0Fh
0x1400037ad  jmp     short loc_1400037C0
0x1400037af  mov     rax, [r14+30h]
0x1400037b3  mov     r12, r9
0x1400037b6  mov     rcx, [rax+18h]
0x1400037ba  mov     eax, [rcx+8]
0x1400037bd  shr     eax, 14h
0x1400037c0  add     r14, 8
0x1400037c4  movzx   edx, word ptr [rbx+24h]
0x1400037c8  mov     r13, [rbx]
0x1400037cb  cmp     dx, r15w
0x1400037cf  jz      short loc_1400037F4
0x1400037d1  test    r15w, r15w
0x1400037d5  jz      short loc_1400037F4
0x1400037d7  cmp     dx, 17h
0x1400037db  jnz     loc_140003916
0x1400037e1  cmp     r15w, 2
0x1400037e6  jnz     loc_140003916
0x1400037ec  test    al, 1
0x1400037ee  jz      loc_140003916
0x1400037f4  test    rdi, rdi
0x1400037f7  jz      short loc_14000380B
0x1400037f9  test    sil, sil
0x1400037fc  jnz     short loc_14000380B
0x1400037fe  cmp     rdi, [rcx+110h]
0x140003805  jnz     loc_140003916
0x14000380b  xor     eax, eax
0x14000380d  xorps   xmm0, xmm0
0x140003810  movups  xmmword ptr [rbp+var_30.LockQueue.Next], xmm0
0x140003814  mov     qword ptr [rbp+var_30.OldIrql], rax
0x140003818  cmp     [r13+8], rbx
0x14000381c  jnz     loc_140003A14
0x140003822  mov     rax, [rbx+8]
0x140003826  cmp     [rax], rbx
0x140003829  jnz     loc_140003A14
0x14000382f  mov     [rax], r13
0x140003832  mov     [r13+8], rax
0x140003836  test    byte ptr [rbx+26h], 1
0x14000383a  mov     [rbx], r9
0x14000383d  jnz     short loc_14000384F
0x14000383f  mov     rax, r9
0x140003842  xchg    rax, [r8+68h]
0x140003846  test    rax, rax
0x140003849  jz      loc_140003916
0x14000384f  test    sil, sil
0x140003852  jz      short loc_14000386A
0x140003854  lea     rcx, [r12+10h]; SpinLock
0x140003859  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003860  nop     dword ptr [rax+rax+00h]
0x140003865  mov     r15b, al
0x140003868  jmp     short loc_140003881
0x14000386a  add     rcx, 38h ; '8'; SpinLock
0x14000386e  lea     rdx, [rbp+var_30]; LockHandle
0x140003872  mov     r15b, r9b
0x140003875  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000387c  nop     dword ptr [rax+rax+00h]
0x140003881  mov     rax, [r14]
0x140003884  test    rax, rax
0x140003887  jz      loc_1400039AF
0x14000388d  cmp     [rax+8], r14
0x140003891  jnz     loc_140003A14
0x140003897  mov     rcx, [r14+8]
0x14000389b  cmp     [rcx], r14
0x14000389e  jnz     loc_140003A14
0x1400038a4  mov     [rcx], rax
0x1400038a7  mov     [rax+8], rcx
0x1400038ab  lea     rcx, [rbp+P]
0x1400038af  mov     rax, [rbp+P+8]
0x1400038b3  cmp     [rax], rcx
0x1400038b6  jnz     loc_140003A14
0x1400038bc  mov     [rbx+8], rax
0x1400038c0  lea     rcx, [rbp+P]
0x1400038c4  mov     [rbx], rcx
0x1400038c7  mov     [rax], rbx
0x1400038ca  mov     [rbp+P+8], rbx
0x1400038ce  test    byte ptr [rbx+26h], 1
0x1400038d2  jz      loc_14000398D
0x1400038d8  mov     rcx, [rbx+10h]
0x1400038dc  mov     esi, 1000h
0x1400038e1  mov     edx, esi
0x1400038e3  xor     r8d, r8d
0x1400038e6  call    AfdIndicateEventSelectEvent
0x1400038eb  mov     rcx, [rbx+10h]
0x1400038ef  lea     r9, [rbp+var_30]
0x1400038f3  xor     r8d, r8d
0x1400038f6  mov     edx, esi
0x1400038f8  call    AfdIndicatePollEvent
0x1400038fd  test    al, al
0x1400038ff  jnz     short loc_140003911
0x140003901  lea     rcx, [rbp+var_30]; LockHandle
0x140003905  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000390c  nop     dword ptr [rax+rax+00h]
0x140003911  movzx   r15d, [rbp+arg_8]
0x140003916  mov     rbx, r13
0x140003919  cmp     r13, [rbp+arg_18]
0x14000391d  jnz     loc_140003768
0x140003923  xor     r14d, r14d
0x140003926  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000392a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003931  nop     dword ptr [rax+rax+00h]
0x140003936  mov     edi, 68646641h
0x14000393b  mov     rcx, [rbp+P]; P
0x14000393f  lea     rax, [rbp+P]
0x140003943  cmp     rcx, rax
0x140003946  jz      loc_140003A1B
0x14000394c  lea     rax, [rbp+P]
0x140003950  cmp     [rcx+8], rax
0x140003954  jnz     loc_140003A14
0x14000395a  mov     rax, [rcx]
0x14000395d  cmp     [rax+8], rcx
0x140003961  jnz     loc_140003A14
0x140003967  lea     rdx, [rbp+P]
0x14000396b  mov     [rbp+P], rax
0x14000396f  mov     [rax+8], rdx
0x140003973  mov     edx, edi; Tag
0x140003975  test    byte ptr [rcx+26h], 1
0x140003979  jz      short loc_1400039C0
0x14000397b  add     rcx, 0FFFFFFFFFFFFFFE0h; P
0x14000397f  call    cs:__imp_ExFreePoolWithTag
0x140003986  nop     dword ptr [rax+rax+00h]
0x14000398b  jmp     short loc_14000393B
0x14000398d  test    sil, sil
0x140003990  jz      loc_140003901
0x140003996  mov     dl, r15b; NewIrql
0x140003999  lea     rcx, [r12+10h]; SpinLock
0x14000399e  call    cs:__imp_KeReleaseSpinLock
0x1400039a5  nop     dword ptr [rax+rax+00h]
0x1400039aa  jmp     loc_140003911
0x1400039af  cmp     qword ptr [r14+8], 0
0x1400039b4  jz      short loc_14000398D
0x1400039b6  mov     qword ptr [r14+8], 0
0x1400039be  jmp     short loc_14000398D
0x1400039c0  mov     rbx, [rcx+10h]
0x1400039c4  call    cs:__imp_ExFreePoolWithTag
0x1400039cb  nop     dword ptr [rax+rax+00h]
0x1400039d0  mov     [rbx+30h], r14d
0x1400039d4  mov     [rbx+38h], r14
0x1400039d8  test    byte ptr cs:xmmword_1400875E0+2, 2
0x1400039df  jz      short loc_1400039FA
0x1400039e1  mov     edx, 26h ; '&'
0x1400039e6  lea     r8, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids
0x1400039ed  mov     ecx, 411h
0x1400039f2  mov     r9, rbx
0x1400039f5  call    WPP_SF_q
0x1400039fa  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140003a00  mov     rcx, rbx; Irp
0x140003a03  call    cs:__imp_IofCompleteRequest
0x140003a0a  nop     dword ptr [rax+rax+00h]
0x140003a0f  jmp     loc_14000393B
0x140003a14  mov     ecx, 3
0x140003a19  int     29h; Win8: RtlFailFast(ecx)
0x140003a1b  mov     rbx, [rsp+60h+arg_0]
0x140003a23  add     rsp, 60h
0x140003a27  pop     r15
0x140003a29  pop     r14
0x140003a2b  pop     r13
0x140003a2d  pop     r12
0x140003a2f  pop     rdi
0x140003a30  pop     rsi
0x140003a31  pop     rbp
0x140003a32  retn
```
