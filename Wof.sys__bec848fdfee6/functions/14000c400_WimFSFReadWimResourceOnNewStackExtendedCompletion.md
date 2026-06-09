# WimFSFReadWimResourceOnNewStackExtendedCompletion

- ea: `0x14000c400`
- end: `0x14000c6b2`
- name: `WimFSFReadWimResourceOnNewStackExtendedCompletion`
- size: `690`
- prototype: `__int64 __fastcall(char *Entry)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140008fd0`
- `0x140009000`
- `0x1400094f0`
- `0x14000a9f0`
- `0x14000c400`
- `0x14000d3b8`
- `0x14000fb60`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000c62e`
- `ntoskrnl!KeSetEvent` at `0x14000c62e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c64f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c64f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000c4cf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000c4cf`
- `ntoskrnl!KeInitializeEvent` at `0x14000c4af`
- `ntoskrnl!KeInitializeEvent` at `0x14000c4af`

## pseudocode

```c
__int64 __fastcall WimFSFReadWimResourceOnNewStackExtendedCompletion(char *Entry)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  __int64 v4; // r15
  __int64 v5; // rbx
  unsigned int v6; // r13d
  unsigned int v7; // r12d
  _QWORD *v8; // rax
  _QWORD *v9; // r14
  __int64 v10; // xmm1_8
  __int64 v11; // r10
  unsigned int v12; // r8d
  __int64 v13; // rdx
  unsigned int v14; // ecx
  unsigned int v15; // r15d
  int v16; // edi
  __int64 v17; // rax
  unsigned int v18; // edx
  unsigned int v19; // ebx
  __int64 result; // rax
  __int64 v21; // [rsp+30h] [rbp-48h]
  __int64 v22; // [rsp+38h] [rbp-40h]
  _QWORD Event[4]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v24; // [rsp+60h] [rbp-18h]
  unsigned int v25; // [rsp+C0h] [rbp+48h]
  __int64 v26; // [rsp+C8h] [rbp+50h]
  __int64 v27; // [rsp+D0h] [rbp+58h]
  __int64 v28; // [rsp+D8h] [rbp+60h]

  v2 = *((_QWORD *)Entry + 31);
  LODWORD(v24) = 0;
  memset(Event, 0, sizeof(Event));
  v3 = *((_QWORD *)Entry + 6);
  v4 = *((_QWORD *)Entry + 15);
  v5 = *((_QWORD *)Entry + 11);
  v6 = *((_DWORD *)Entry + 28);
  v27 = *((_QWORD *)Entry + 32);
  v25 = *((_DWORD *)Entry + 66);
  v21 = *((_QWORD *)Entry + 12);
  v26 = v2;
  v22 = v3;
  v28 = v4;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
  if ( *((int *)Entry + 2) < 0 )
  {
    v19 = 0;
    v18 = 0;
  }
  else
  {
    LODWORD(Event[0]) = 1;
    v7 = 0;
    KeInitializeEvent((PRKEVENT)&Event[1], SynchronizationEvent, 0);
    v24 = 0;
    while ( v7 < v6 )
    {
      v8 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 640));
      v9 = v8;
      if ( !v8 )
      {
        LODWORD(v24) = -1073741670;
        break;
      }
      _InterlockedIncrement((volatile signed __int32 *)Event);
      v8[1] = 0;
      v8[2] = WimFSFDecompressWimResources;
      v8[3] = v8;
      *v8 = 0;
      v8[4] = v3;
      v8[5] = v26;
      *((_OWORD *)v8 + 3) = *(_OWORD *)(Entry + 56);
      v10 = *((_QWORD *)Entry + 9);
      v11 = v7 + v5;
      v8[9] = v21;
      v8[10] = v7 + v4;
      v8[8] = v10;
      v8[12] = v11;
      v12 = *(_DWORD *)(v3 + 108);
      *((_DWORD *)v8 + 26) = v12;
      v13 = v11 % *(unsigned int *)(v3 + 104);
      if ( v13 <= 0 )
      {
        v14 = v12;
      }
      else
      {
        v14 = *(_DWORD *)(v3 + 104) - v13;
        *((_DWORD *)v8 + 26) = v14;
        v12 = v14;
      }
      v15 = v6 - v7;
      if ( v14 <= v6 - v7 )
        v15 = v12;
      else
        *((_DWORD *)v8 + 26) = v15;
      *(_QWORD *)((char *)v8 + 108) = 0;
      v8[15] = Event;
      if ( v26 )
      {
        v16 = WimFSFGetChunkOffset(v26, v11 / *(unsigned int *)(v3 + 104));
        v17 = v27 + v16 - (unsigned int)WimFSFGetChunkOffset(v26, v25);
        v3 = v22;
      }
      else
      {
        v17 = v27;
      }
      v9[11] = v17;
      v7 += v15;
      _InterlockedIncrement(&WimPostedReads);
      if ( v7 < v6 )
      {
        v4 = v28;
        if ( (unsigned __int8)WofTryQueueWorkItem(v9, (unsigned int)(*((_DWORD *)Entry + 33) + 32)) )
          continue;
      }
      _InterlockedDecrement(&WimPostedReads);
      _InterlockedIncrement(&WimInlineReads);
      WimFSFDecompressWimResources(v9);
      v4 = v28;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Event, 0xFFFFFFFF) == 1 )
      KeSetEvent((PRKEVENT)&Event[1], 0, 0);
    KeWaitForSingleObject(&Event[1], Executive, 0, 0, 0);
    v18 = HIDWORD(v24);
    v19 = v24;
  }
  WimFSFCompleteRead(Entry, v18, v19);
  result = HIDWORD(WPP_GLOBAL_Control->Timer);
  if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    return WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, v19);
  return result;
}

```

## disassembly

```asm
0x14000c400  push    rbp
0x14000c402  push    rbx
0x14000c403  push    rsi
0x14000c404  push    rdi
0x14000c405  push    r12
0x14000c407  push    r13
0x14000c409  push    r14
0x14000c40b  push    r15
0x14000c40d  mov     rbp, rsp
0x14000c410  sub     rsp, 78h
0x14000c414  mov     rsi, rcx
0x14000c417  xor     eax, eax
0x14000c419  mov     rcx, [rcx+0F8h]
0x14000c420  xorps   xmm0, xmm0
0x14000c423  mov     dword ptr [rbp+var_18], eax
0x14000c426  movups  xmmword ptr [rbp+Event], xmm0
0x14000c42a  mov     rax, [rsi+100h]
0x14000c431  mov     rdi, [rsi+30h]
0x14000c435  mov     r15, [rsi+78h]
0x14000c439  mov     rbx, [rsi+58h]
0x14000c43d  mov     r13d, [rsi+70h]
0x14000c441  mov     [rbp+arg_10], rax
0x14000c445  mov     eax, [rsi+108h]
0x14000c44b  mov     [rbp+arg_0], eax
0x14000c44e  mov     rax, [rsi+60h]
0x14000c452  mov     [rbp+var_48], rax
0x14000c456  movups  xmmword ptr [rbp+Event+10h], xmm0
0x14000c45a  mov     [rbp+arg_8], rcx
0x14000c45e  mov     [rbp+var_40], rdi
0x14000c462  mov     [rbp+arg_18], r15
0x14000c466  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c46d  mov     eax, [rcx+2Ch]
0x14000c470  test    al, 20h
0x14000c472  jz      short loc_14000C48F
0x14000c474  cmp     byte ptr [rcx+29h], 4
0x14000c478  jb      short loc_14000C48F
0x14000c47a  mov     rcx, [rcx+18h]
0x14000c47e  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000c485  mov     edx, 18h
0x14000c48a  call    WPP_SF_
0x14000c48f  xor     r14d, r14d
0x14000c492  cmp     [rsi+8], r14d
0x14000c496  jl      loc_14000C663
0x14000c49c  lea     eax, [r14+1]
0x14000c4a0  xor     r8d, r8d; State
0x14000c4a3  mov     edx, eax; Type
0x14000c4a5  mov     dword ptr [rbp+Event], eax
0x14000c4a8  lea     rcx, [rbp+Event+8]; Event
0x14000c4ac  mov     r12d, r14d
0x14000c4af  call    cs:__imp_KeInitializeEvent
0x14000c4b6  nop     dword ptr [rax+rax+00h]
0x14000c4bb  mov     [rbp+var_18], r14
0x14000c4bf  cmp     r12d, r13d
0x14000c4c2  jnb     loc_14000C618
0x14000c4c8  lea     rcx, [rdi+280h]; Lookaside
0x14000c4cf  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000c4d6  nop     dword ptr [rax+rax+00h]
0x14000c4db  xor     r11d, r11d
0x14000c4de  mov     r14, rax
0x14000c4e1  test    rax, rax
0x14000c4e4  jz      loc_14000C611
0x14000c4ea  lock inc dword ptr [rbp+Event]
0x14000c4ee  mov     r9, [rbp+arg_8]
0x14000c4f2  mov     [rax+8], r11
0x14000c4f6  lea     rax, WimFSFDecompressWimResources
0x14000c4fd  mov     [r14+10h], rax
0x14000c501  mov     rax, [rbp+var_48]
0x14000c505  mov     [r14+18h], r14
0x14000c509  mov     [r14], r11
0x14000c50c  mov     [r14+20h], rdi
0x14000c510  mov     [r14+28h], r9
0x14000c514  movups  xmm0, xmmword ptr [rsi+38h]
0x14000c518  mov     ecx, r12d
0x14000c51b  movups  xmmword ptr [r14+30h], xmm0
0x14000c520  movsd   xmm1, qword ptr [rsi+48h]
0x14000c525  lea     r10, [rcx+rbx]
0x14000c529  mov     [r14+48h], rax
0x14000c52d  lea     rax, [rcx+r15]
0x14000c531  mov     [r14+50h], rax
0x14000c535  mov     rax, r10
0x14000c538  movsd   qword ptr [r14+40h], xmm1
0x14000c53e  cqo
0x14000c540  mov     [r14+60h], r10
0x14000c544  mov     r8d, [rdi+6Ch]
0x14000c548  mov     [r14+68h], r8d
0x14000c54c  mov     ecx, [rdi+68h]
0x14000c54f  idiv    rcx
0x14000c552  test    rdx, rdx
0x14000c555  jle     short loc_14000C562
0x14000c557  sub     ecx, edx
0x14000c559  mov     [r14+68h], ecx
0x14000c55d  mov     r8d, ecx
0x14000c560  jmp     short loc_14000C565
0x14000c562  mov     ecx, r8d
0x14000c565  mov     r15d, r13d
0x14000c568  sub     r15d, r12d
0x14000c56b  cmp     ecx, r15d
0x14000c56e  jbe     short loc_14000C576
0x14000c570  mov     [r14+68h], r15d
0x14000c574  jmp     short loc_14000C579
0x14000c576  mov     r15d, r8d
0x14000c579  mov     [r14+6Ch], r11
0x14000c57d  lea     rax, [rbp+Event]
0x14000c581  mov     [r14+78h], rax
0x14000c585  test    r9, r9
0x14000c588  jz      short loc_14000C5BE
0x14000c58a  mov     ecx, [rdi+68h]
0x14000c58d  mov     rax, r10
0x14000c590  cqo
0x14000c592  idiv    rcx
0x14000c595  mov     rcx, r9
0x14000c598  mov     rdx, rax
0x14000c59b  call    WimFSFGetChunkOffset
0x14000c5a0  mov     edx, [rbp+arg_0]
0x14000c5a3  mov     rdi, rax
0x14000c5a6  mov     rcx, [rbp+arg_8]
0x14000c5aa  call    WimFSFGetChunkOffset
0x14000c5af  sub     rdi, rax
0x14000c5b2  mov     eax, edi
0x14000c5b4  add     rax, [rbp+arg_10]
0x14000c5b8  mov     rdi, [rbp+var_40]
0x14000c5bc  jmp     short loc_14000C5C2
0x14000c5be  mov     rax, [rbp+arg_10]
0x14000c5c2  mov     [r14+58h], rax
0x14000c5c6  add     r12d, r15d
0x14000c5c9  lock inc cs:WimPostedReads
0x14000c5d0  cmp     r12d, r13d
0x14000c5d3  jnb     short loc_14000C5F2
0x14000c5d5  mov     edx, [rsi+84h]
0x14000c5db  mov     rcx, r14
0x14000c5de  add     edx, 20h ; ' '
0x14000c5e1  call    WofTryQueueWorkItem
0x14000c5e6  mov     r15, [rbp+arg_18]
0x14000c5ea  test    al, al
0x14000c5ec  jnz     loc_14000C4BF
0x14000c5f2  lock dec cs:WimPostedReads
0x14000c5f9  lock inc cs:WimInlineReads
0x14000c600  mov     rcx, r14; Entry
0x14000c603  call    WimFSFDecompressWimResources
0x14000c608  mov     r15, [rbp+arg_18]
0x14000c60c  jmp     loc_14000C4BF
0x14000c611  mov     dword ptr [rbp+var_18], 0C000009Ah
0x14000c618  or      eax, 0FFFFFFFFh
0x14000c61b  lock xadd dword ptr [rbp+Event], eax
0x14000c620  cmp     eax, 1
0x14000c623  jnz     short loc_14000C63A
0x14000c625  xor     r8d, r8d; Wait
0x14000c628  lea     rcx, [rbp+Event+8]; Event
0x14000c62c  xor     edx, edx; Increment
0x14000c62e  call    cs:__imp_KeSetEvent
0x14000c635  nop     dword ptr [rax+rax+00h]
0x14000c63a  xor     r9d, r9d; Alertable
0x14000c63d  mov     [rsp+78h+Timeout], 0; Timeout
0x14000c646  xor     r8d, r8d; WaitMode
0x14000c649  lea     rcx, [rbp+Event+8]; Object
0x14000c64d  xor     edx, edx; WaitReason
0x14000c64f  call    cs:__imp_KeWaitForSingleObject
0x14000c656  nop     dword ptr [rax+rax+00h]
0x14000c65b  mov     edx, dword ptr [rbp+var_18+4]
0x14000c65e  mov     ebx, dword ptr [rbp+var_18]
0x14000c661  jmp     short loc_14000C669
0x14000c663  mov     ebx, r14d
0x14000c666  mov     edx, r14d
0x14000c669  mov     r8d, ebx
0x14000c66c  mov     rcx, rsi; Entry
0x14000c66f  call    WimFSFCompleteRead
0x14000c674  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c67b  mov     eax, [rcx+2Ch]
0x14000c67e  test    al, 20h
0x14000c680  jz      short loc_14000C6A0
0x14000c682  cmp     byte ptr [rcx+29h], 4
0x14000c686  jb      short loc_14000C6A0
0x14000c688  mov     rcx, [rcx+18h]
0x14000c68c  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000c693  mov     edx, 19h
0x14000c698  mov     r9d, ebx
0x14000c69b  call    WPP_SF_d
0x14000c6a0  add     rsp, 78h
0x14000c6a4  pop     r15
0x14000c6a6  pop     r14
0x14000c6a8  pop     r13
0x14000c6aa  pop     r12
0x14000c6ac  pop     rdi
0x14000c6ad  pop     rsi
0x14000c6ae  pop     rbx
0x14000c6af  pop     rbp
0x14000c6b0  retn
```
