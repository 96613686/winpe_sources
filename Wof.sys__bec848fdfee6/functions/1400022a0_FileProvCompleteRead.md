# FileProvCompleteRead

- ea: `0x1400022a0`
- end: `0x140002636`
- name: `FileProvCompleteRead`
- size: `918`
- prototype: `__int64 __fastcall(char *Entry, unsigned int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001570`
- `0x1400016f0`
- `0x140001890`

## callees

- `0x1400022a0`
- `0x14000d3b8`
- `0x14000d440`
- `0x14000fb60`
- `0x140010654`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000241e`
- `ntoskrnl!KeSetEvent` at `0x14000241e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400023f6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400023f6`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140002492`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140002492`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000239e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000239e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024c9`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400024aa`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400024aa`
- `FLTMGR!FltFreeCallbackData` at `0x140002327`
- `FLTMGR!FltFreeCallbackData` at `0x140002327`

## string_xrefs

- `0x1400025da`: `(StreamContext != NULL) || (Context->ReadCompressedResource.ChunkTable == NULL)`

## pseudocode

```c
__int64 __fastcall FileProvCompleteRead(char *Entry, unsigned int a2, int a3)
{
  __int64 v5; // rdi
  struct _KEVENT *v6; // rsi
  void *v7; // rdi
  void *v8; // r12
  __int64 v9; // r15
  __int64 result; // rax
  __int64 v11; // rcx
  struct _EX_RUNDOWN_REF *v12; // rcx

  v5 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
  if ( Entry[137] )
  {
    *((_DWORD *)Entry + 2) = a3;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
    v6 = (struct _KEVENT *)(Entry + 144);
    if ( a3 < 0 )
      LODWORD(v5) = 0;
    *((_DWORD *)Entry + 19) = v5;
  }
  else
  {
    v6 = 0;
    *(_DWORD *)(*((_QWORD *)Entry + 3) + 24LL) = a3;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
    v11 = *((_QWORD *)Entry + 3);
    if ( a3 < 0 )
    {
      *(_QWORD *)(v11 + 32) = 0;
    }
    else
    {
      *(_QWORD *)(v11 + 32) = v5;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_3b099794e4b93327e327da255c047df6_Traceguids,
          *(unsigned int *)(*((_QWORD *)Entry + 3) + 32LL));
    }
    v12 = (struct _EX_RUNDOWN_REF *)*((_QWORD *)Entry + 4);
    if ( v12 )
      ExReleaseRundownProtection(v12);
    FltCompletePendedPreOperation(*((PFLT_CALLBACK_DATA *)Entry + 3), FLT_PREOP_COMPLETE, 0);
  }
  if ( Entry[136] )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
    FltFreeCallbackData(*(PFLT_CALLBACK_DATA *)Entry);
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_eaaba969f297373d9ffb29335f34480c_Traceguids,
      *((unsigned int *)Entry + 4),
      Entry);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 4, 0xFFFFFFFF) == 1 )
  {
    v7 = (void *)*((_QWORD *)Entry + 26);
    v8 = (void *)*((_QWORD *)Entry + 27);
    v9 = *((_QWORD *)Entry + 7);
    if ( !v9 && *((_QWORD *)Entry + 23) )
      MicrosoftTelemetryAssertTriggeredMsgKM("(StreamContext != NULL) || (Context->ReadCompressedResource.ChunkTable == NULL)");
    if ( v7 )
    {
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)&qword_140019400[104 * *(unsigned int *)(v9 + 4)], v7);
      *((_QWORD *)Entry + 26) = 0;
    }
    else
    {
      if ( !v8 )
      {
LABEL_16:
        if ( (*((_DWORD *)Entry + 3) & 1) != 0 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids);
          ExFreeToNPagedLookasideList(
            (PNPAGED_LOOKASIDE_LIST)&qword_140019500[104 * *(unsigned int *)(*((_QWORD *)Entry + 7) + 4LL)],
            Entry);
        }
        goto LABEL_19;
      }
      ExFreePoolWithTag(v8, 0);
    }
    *((_QWORD *)Entry + 27) = 0;
    goto LABEL_16;
  }
LABEL_19:
  if ( v6 )
    KeSetEvent(v6, 0, 0);
  result = HIDWORD(WPP_GLOBAL_Control->Timer);
  if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    return WPP_SF_d(
             WPP_GLOBAL_Control->AttachedDevice,
             19,
             WPP_3b099794e4b93327e327da255c047df6_Traceguids,
             (unsigned int)a3);
  return result;
}

```

## disassembly

```asm
0x1400022a0  push    rbp
0x1400022a2  sub     rsp, 50h
0x1400022a6  mov     [rsp+58h+arg_8], rbx
0x1400022ab  mov     ebp, r8d
0x1400022ae  mov     [rsp+58h+arg_10], rsi
0x1400022b3  mov     rbx, rcx
0x1400022b6  mov     [rsp+58h+var_10], rdi
0x1400022bb  mov     edi, edx
0x1400022bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022c4  mov     eax, [rcx+2Ch]
0x1400022c7  test    al, 20h
0x1400022c9  jnz     loc_1400024DA
0x1400022cf  cmp     byte ptr [rbx+89h], 0
0x1400022d6  mov     [rsp+58h+var_20], r14
0x1400022db  jz      loc_140002448
0x1400022e1  mov     [rbx+8], ebp
0x1400022e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022eb  mov     eax, [rcx+2Ch]
0x1400022ee  test    al, 20h
0x1400022f0  jnz     loc_1400024FE
0x1400022f6  xor     r14d, r14d
0x1400022f9  lea     rsi, [rbx+90h]
0x140002300  test    ebp, ebp
0x140002302  cmovs   edi, r14d
0x140002306  mov     [rbx+4Ch], edi
0x140002309  cmp     byte ptr [rbx+88h], 0
0x140002310  jz      short loc_140002333
0x140002312  mov     rcx, cs:WPP_GLOBAL_Control
0x140002319  mov     eax, [rcx+2Ch]
0x14000231c  test    al, 20h
0x14000231e  jnz     loc_14000257B
0x140002324  mov     rcx, [rbx]; CallbackData
0x140002327  call    cs:__imp_FltFreeCallbackData
0x14000232e  nop     dword ptr [rax+rax+00h]
0x140002333  mov     rcx, cs:WPP_GLOBAL_Control
0x14000233a  mov     eax, [rcx+2Ch]
0x14000233d  test    al, 20h
0x14000233f  jnz     loc_14000259F
0x140002345  mov     eax, 0FFFFFFFFh
0x14000234a  lock xadd [rbx+10h], eax
0x14000234f  cmp     eax, 1
0x140002352  jnz     loc_140002402
0x140002358  mov     rdi, [rbx+0D0h]
0x14000235f  mov     [rsp+58h+var_18], r12
0x140002364  mov     r12, [rbx+0D8h]
0x14000236b  mov     [rsp+58h+var_28], r15
0x140002370  mov     r15, [rbx+38h]
0x140002374  test    r15, r15
0x140002377  jz      loc_1400025CC
0x14000237d  test    rdi, rdi
0x140002380  jz      loc_1400024BB
0x140002386  mov     eax, [r15+4]
0x14000238a  mov     rdx, rdi; Entry
0x14000238d  imul    rcx, rax, 340h
0x140002394  lea     rax, qword_140019400
0x14000239b  add     rcx, rax; Lookaside
0x14000239e  call    cs:__imp_ExFreeToPagedLookasideList
0x1400023a5  nop     dword ptr [rax+rax+00h]
0x1400023aa  mov     [rbx+0D0h], r14
0x1400023b1  mov     [rbx+0D8h], r14
0x1400023b8  mov     eax, [rbx+0Ch]
0x1400023bb  mov     r15, [rsp+58h+var_28]
0x1400023c0  mov     r12, [rsp+58h+var_18]
0x1400023c5  test    al, 1
0x1400023c7  jz      short loc_140002402
0x1400023c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023d0  mov     eax, [rcx+2Ch]
0x1400023d3  test    al, 20h
0x1400023d5  jnz     loc_1400025EB
0x1400023db  mov     rax, [rbx+38h]
0x1400023df  mov     rdx, rbx; Entry
0x1400023e2  mov     ecx, [rax+4]
0x1400023e5  lea     rax, qword_140019500
0x1400023ec  imul    rcx, 340h
0x1400023f3  add     rcx, rax; Lookaside
0x1400023f6  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400023fd  nop     dword ptr [rax+rax+00h]
0x140002402  mov     r14, [rsp+58h+var_20]
0x140002407  mov     rdi, [rsp+58h+var_10]
0x14000240c  mov     rbx, [rsp+58h+arg_8]
0x140002411  test    rsi, rsi
0x140002414  jz      short loc_14000242A
0x140002416  xor     r8d, r8d; Wait
0x140002419  xor     edx, edx; Increment
0x14000241b  mov     rcx, rsi; Event
0x14000241e  call    cs:__imp_KeSetEvent
0x140002425  nop     dword ptr [rax+rax+00h]
0x14000242a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002431  mov     rsi, [rsp+58h+arg_10]
0x140002436  mov     eax, [rcx+2Ch]
0x140002439  test    al, 20h
0x14000243b  jnz     loc_14000260F
0x140002441  add     rsp, 50h
0x140002445  pop     rbp
0x140002446  retn
0x140002448  mov     rax, [rbx+18h]
0x14000244c  xor     r14d, r14d
0x14000244f  mov     esi, r14d
0x140002452  mov     [rax+18h], ebp
0x140002455  mov     rcx, cs:WPP_GLOBAL_Control
0x14000245c  mov     eax, [rcx+2Ch]
0x14000245f  test    al, 20h
0x140002461  jnz     loc_140002522
0x140002467  mov     rcx, [rbx+18h]
0x14000246b  test    ebp, ebp
0x14000246d  js      loc_140002546
0x140002473  mov     [rcx+20h], rdi
0x140002477  mov     rcx, cs:WPP_GLOBAL_Control
0x14000247e  mov     eax, [rcx+2Ch]
0x140002481  test    al, 4
0x140002483  jnz     loc_14000254F
0x140002489  mov     rcx, [rbx+20h]; RunRef
0x14000248d  test    rcx, rcx
0x140002490  jz      short loc_14000249E
0x140002492  call    cs:__imp_ExReleaseRundownProtection
0x140002499  nop     dword ptr [rax+rax+00h]
0x14000249e  mov     rcx, [rbx+18h]; CallbackData
0x1400024a2  xor     r8d, r8d; Context
0x1400024a5  mov     edx, 4; CallbackStatus
0x1400024aa  call    cs:__imp_FltCompletePendedPreOperation
0x1400024b1  nop     dword ptr [rax+rax+00h]
0x1400024b6  jmp     loc_140002309
0x1400024bb  test    r12, r12
0x1400024be  jz      loc_1400023B8
0x1400024c4  xor     edx, edx; Tag
0x1400024c6  mov     rcx, r12; P
0x1400024c9  call    cs:__imp_ExFreePoolWithTag
0x1400024d0  nop     dword ptr [rax+rax+00h]
0x1400024d5  jmp     loc_1400023B1
0x1400024da  cmp     byte ptr [rcx+29h], 4
0x1400024de  jb      loc_1400022CF
0x1400024e4  mov     rcx, [rcx+18h]
0x1400024e8  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400024ef  mov     edx, 0Eh
0x1400024f4  call    WPP_SF_
0x1400024f9  jmp     loc_1400022CF
0x1400024fe  cmp     byte ptr [rcx+29h], 4
0x140002502  jb      loc_1400022F6
0x140002508  mov     rcx, [rcx+18h]
0x14000250c  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140002513  mov     edx, 0Fh
0x140002518  call    WPP_SF_
0x14000251d  jmp     loc_1400022F6
0x140002522  cmp     byte ptr [rcx+29h], 4
0x140002526  jb      loc_140002467
0x14000252c  mov     rcx, [rcx+18h]
0x140002530  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140002537  mov     edx, 10h
0x14000253c  call    WPP_SF_
0x140002541  jmp     loc_140002467
0x140002546  mov     [rcx+20h], r14
0x14000254a  jmp     loc_140002489
0x14000254f  cmp     byte ptr [rcx+29h], 5
0x140002553  jb      loc_140002489
0x140002559  mov     r9, [rbx+18h]
0x14000255d  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140002564  mov     rcx, [rcx+18h]
0x140002568  mov     edx, 11h
0x14000256d  mov     r9d, [r9+20h]
0x140002571  call    WPP_SF_d
0x140002576  jmp     loc_140002489
0x14000257b  cmp     byte ptr [rcx+29h], 4
0x14000257f  jb      loc_140002324
0x140002585  mov     rcx, [rcx+18h]
0x140002589  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140002590  mov     edx, 12h
0x140002595  call    WPP_SF_
0x14000259a  jmp     loc_140002324
0x14000259f  cmp     byte ptr [rcx+29h], 5
0x1400025a3  jb      loc_140002345
0x1400025a9  mov     rcx, [rcx+18h]
0x1400025ad  lea     r8, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids
0x1400025b4  mov     r9d, [rbx+10h]
0x1400025b8  mov     edx, 0Dh
0x1400025bd  mov     [rsp+58h+var_38], rbx
0x1400025c2  call    WPP_SF_dq
0x1400025c7  jmp     loc_140002345
0x1400025cc  cmp     qword ptr [rbx+0B8h], 0
0x1400025d4  jz      loc_14000237D
0x1400025da  lea     rcx, aStreamcontextN; "(StreamContext != NULL) || (Context->Re"...
0x1400025e1  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400025e6  jmp     loc_14000237D
0x1400025eb  cmp     byte ptr [rcx+29h], 5
0x1400025ef  jb      loc_1400023DB
0x1400025f5  mov     rcx, [rcx+18h]
0x1400025f9  lea     r8, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids
0x140002600  mov     edx, 0Eh
0x140002605  call    WPP_SF_
0x14000260a  jmp     loc_1400023DB
0x14000260f  cmp     byte ptr [rcx+29h], 4
0x140002613  jb      loc_140002441
0x140002619  mov     rcx, [rcx+18h]
0x14000261d  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140002624  mov     edx, 13h
0x140002629  mov     r9d, ebp
0x14000262c  call    WPP_SF_d
0x140002631  jmp     loc_140002441
```
