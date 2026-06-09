# Command_HandleCommandRingStoppedEvent

- ea: `0x14002390c`
- end: `0x140023be0`
- name: `Command_HandleCommandRingStoppedEvent`
- size: `724`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140021f3c`

## callees

- `0x14000c264`
- `0x140010d40`
- `0x1400110e0`
- `0x14001ac48`
- `0x1400218a0`
- `0x1400219b0`
- `0x140021a74`
- `0x14002390c`
- `0x14002b2c0`
- `0x140031568`
- `0x140032a2c`
- `0x14003d3b4`
- `0x14003e7f4`
- `0x14003f514`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140023932`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023932`

## string_xrefs

- `0x140023a31`: `After command abort completion, software and hardware dequeue pointers do not match`

## pseudocode

```c
__int64 __fastcall Command_HandleCommandRingStoppedEvent(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdi
  char v5; // r13
  __int64 v6; // rcx
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // r14
  _DWORD *v12; // rsi
  __int64 v13; // r15
  unsigned int *v14; // r15
  __int64 *v15; // rax
  int v16; // ecx
  __int64 v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 result; // rax
  __int64 v23; // rcx
  __int128 v24; // [rsp+40h] [rbp-18h] BYREF

  v24 = 0;
  v4 = 0;
  v5 = 0;
  if ( KeGetCurrentIrql() == 2 )
  {
    v6 = *(_QWORD *)(a1 + 8);
    if ( *(_BYTE *)(v6 + 1041) )
    {
      Controller_LowerAndTrackIrql(v6);
      v5 = 1;
    }
  }
  DynamicLock_Acquire(*(_QWORD *)(a1 + 112));
  *(_BYTE *)(a1 + 121) = 0;
  if ( *(_BYTE *)(a1 + 136) )
    v10 = *(_QWORD *)(a1 + 176);
  else
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 184) + 24LL);
  v11 = *a2;
  v12 = (_DWORD *)(a1 + 44);
  v13 = v10 + 16LL * *(unsigned int *)(a1 + 44);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_ii(*(_QWORD *)(a1 + 16), v7, v8, v9);
  if ( v11 == v13
    || (v14 = (unsigned int *)(a1 + 44), v11 == *(_QWORD *)(a1 + 56)) && (v14 = (unsigned int *)(a1 + 44), !*v12) )
  {
    v15 = *(__int64 **)(a1 + 80);
    if ( v15 != (__int64 *)(a1 + 80) )
    {
      v16 = *((_DWORD *)v15 + 14);
      v4 = *(_QWORD *)(a1 + 80);
      if ( v16 )
      {
        if ( v16 == 5 || v16 == 10 )
          v4 = 0;
      }
      else
      {
        v17 = *v15;
        if ( *(__int64 **)(*v15 + 8) != v15 || (v18 = (_QWORD *)v15[1], *v18 != v4) )
LABEL_36:
          __fastfail(3u);
        *v18 = v17;
        *(_QWORD *)(v17 + 8) = v18;
        v19 = (unsigned int)++*v12;
        if ( (_DWORD)v19 == *(_DWORD *)(a1 + 48) )
        {
          *v12 = 0;
          v19 = 0;
        }
        XilCommand_AdvanceCommandRingControlDequeuePointer(a1, v19);
      }
    }
    if ( *(_QWORD *)(a1 + 80) != a1 + 80 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 4;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 16), v7, 7, 42, (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids);
      }
      XilCommand_WriteDoorbell(a1);
    }
    v20 = *(_QWORD *)(a1 + 96);
    if ( v20 == a1 + 96 )
    {
      *((_QWORD *)&v24 + 1) = &v24;
      *(_QWORD *)&v24 = &v24;
    }
    else
    {
      *((_QWORD *)&v24 + 1) = *(_QWORD *)(a1 + 104);
      *(_QWORD *)&v24 = v20;
      *(_QWORD *)(v20 + 8) = &v24;
      **((_QWORD **)&v24 + 1) = &v24;
      *(_QWORD *)(a1 + 104) = a1 + 96;
      *(_QWORD *)(a1 + 96) = a1 + 96;
    }
    while ( (__int128 *)v24 != &v24 )
    {
      if ( *(__int128 **)(v24 + 8) != &v24 )
        goto LABEL_36;
      v21 = *(_QWORD *)v24;
      if ( *(_QWORD *)(*(_QWORD *)v24 + 8LL) != (_QWORD)v24 )
        goto LABEL_36;
      *(_QWORD *)&v24 = *(_QWORD *)v24;
      *(_QWORD *)(v21 + 8) = &v24;
      Command_InternalSendCommand(a1);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 4;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 16), v7, 7, 43, (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids);
    }
    Controller_HwVerifierBreakIfEnabled(
      *(_QWORD *)(a1 + 8),
      0,
      0,
      0x8000,
      (__int64)"After command abort completion, software and hardware dequeue pointers do not match",
      *(_QWORD *)(a1 + 72) + 16LL * *v14,
      (__int64)a2);
    Controller_ReportFatalError(*(_QWORD *)(a1 + 8), 2, 4115, 0, 0, 0, 0);
    *(_DWORD *)(a1 + 36) = 2;
  }
  result = DynamicLock_Release(*(_QWORD *)(a1 + 112));
  if ( v5 )
    result = Controller_RaiseAndTrackIrql(*(_QWORD *)(a1 + 8));
  if ( v4 )
  {
    *(_BYTE *)(v4 + 60) = 25;
    Etw_CommandCompleteError(v23, a1, v4, 2);
    return Command_ProcessCrbCompletion(v4, 2);
  }
  return result;
}

```

## disassembly

```asm
0x14002390c  push    rbp
0x14002390e  push    rbx
0x14002390f  push    rsi
0x140023910  push    rdi
0x140023911  push    r12
0x140023913  push    r13
0x140023915  push    r14
0x140023917  push    r15
0x140023919  mov     rbp, rsp
0x14002391c  sub     rsp, 58h
0x140023920  xorps   xmm0, xmm0
0x140023923  mov     r12, rdx
0x140023926  movups  [rbp+var_18], xmm0
0x14002392a  mov     rbx, rcx
0x14002392d  xor     edi, edi
0x14002392f  xor     r13b, r13b
0x140023932  call    cs:__imp_KeGetCurrentIrql
0x140023939  nop     dword ptr [rax+rax+00h]
0x14002393e  cmp     al, 2
0x140023940  jnz     short loc_140023957
0x140023942  mov     rcx, [rbx+8]
0x140023946  cmp     [rcx+411h], dil
0x14002394d  jz      short loc_140023957
0x14002394f  call    Controller_LowerAndTrackIrql
0x140023954  mov     r13b, 1
0x140023957  mov     rcx, [rbx+70h]
0x14002395b  call    DynamicLock_Acquire
0x140023960  mov     [rbx+79h], dil
0x140023964  cmp     [rbx+88h], dil
0x14002396b  jz      short loc_140023976
0x14002396d  mov     rcx, [rbx+0B0h]
0x140023974  jmp     short loc_140023981
0x140023976  mov     rax, [rbx+0B8h]
0x14002397d  mov     rcx, [rax+18h]
0x140023981  mov     r14, [r12]
0x140023985  lea     rsi, [rbx+2Ch]
0x140023989  mov     r15d, [rsi]
0x14002398c  shl     r15, 4
0x140023990  add     r15, rcx
0x140023993  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002399a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400239a1  jz      short loc_1400239C3
0x1400239a3  mov     rcx, [rbx+10h]
0x1400239a7  mov     [rsp+58h+var_28], r14
0x1400239ac  mov     [rsp+58h+var_30], r15
0x1400239b1  call    WPP_RECORDER_SF_ii
0x1400239b6  lea     rax, [rbx+2Ch]
0x1400239ba  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400239c1  jmp     short loc_1400239C6
0x1400239c3  mov     rax, rsi
0x1400239c6  cmp     r14, r15
0x1400239c9  jz      loc_140023A71
0x1400239cf  mov     r15, rsi
0x1400239d2  cmp     r14, [rbx+38h]
0x1400239d6  jnz     short loc_1400239E3
0x1400239d8  mov     r15, rax
0x1400239db  cmp     [rsi], edi
0x1400239dd  jz      loc_140023A71
0x1400239e3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x1400239ea  jz      short loc_140023A0D
0x1400239ec  mov     rcx, [rbx+10h]
0x1400239f0  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x1400239f7  mov     r9d, 2Bh ; '+'
0x1400239fd  mov     [rsp+58h+var_38], rax
0x140023a02  mov     dl, 4
0x140023a04  lea     r8d, [r9-24h]
0x140023a08  call    WPP_RECORDER_SF_
0x140023a0d  mov     eax, [r15]
0x140023a10  mov     r9d, 8000h
0x140023a16  mov     rcx, [rbx+8]
0x140023a1a  xor     r8d, r8d
0x140023a1d  shl     rax, 4
0x140023a21  xor     edx, edx
0x140023a23  add     rax, [rbx+48h]
0x140023a27  mov     [rsp+58h+var_28], r12
0x140023a2c  mov     [rsp+58h+var_30], rax
0x140023a31  lea     rax, aAfterCommandAb; "After command abort completion, softwar"...
0x140023a38  mov     [rsp+58h+var_38], rax
0x140023a3d  call    Controller_HwVerifierBreakIfEnabled
0x140023a42  mov     rcx, [rbx+8]
0x140023a46  xor     r9d, r9d
0x140023a49  mov     [rsp+58h+var_28], rdi
0x140023a4e  mov     r8d, 1013h
0x140023a54  mov     [rsp+58h+var_30], rdi
0x140023a59  mov     [rsp+58h+var_38], rdi
0x140023a5e  lea     esi, [r9+2]
0x140023a62  mov     edx, esi
0x140023a64  call    Controller_ReportFatalError
0x140023a69  mov     [rbx+24h], esi
0x140023a6c  jmp     loc_140023B93
0x140023a71  lea     r14, [rbx+50h]
0x140023a75  mov     rax, [r14]
0x140023a78  cmp     rax, r14
0x140023a7b  jz      short loc_140023ACF
0x140023a7d  mov     ecx, [rax+38h]
0x140023a80  mov     rdi, rax
0x140023a83  test    ecx, ecx
0x140023a85  jz      short loc_140023A95
0x140023a87  cmp     ecx, 5
0x140023a8a  jz      short loc_140023A91
0x140023a8c  cmp     ecx, 0Ah
0x140023a8f  jnz     short loc_140023ACF
0x140023a91  xor     edi, edi
0x140023a93  jmp     short loc_140023ACF
0x140023a95  mov     rcx, [rax]
0x140023a98  cmp     [rcx+8], rdi
0x140023a9c  jnz     loc_140023B87
0x140023aa2  mov     rax, [rax+8]
0x140023aa6  cmp     [rax], rdi
0x140023aa9  jnz     loc_140023B87
0x140023aaf  mov     [rax], rcx
0x140023ab2  mov     [rcx+8], rax
0x140023ab6  inc     dword ptr [rsi]
0x140023ab8  mov     edx, [rsi]
0x140023aba  cmp     edx, [rbx+30h]
0x140023abd  jnz     short loc_140023AC7
0x140023abf  mov     dword ptr [rsi], 0
0x140023ac5  xor     edx, edx
0x140023ac7  mov     rcx, rbx
0x140023aca  call    XilCommand_AdvanceCommandRingControlDequeuePointer
0x140023acf  cmp     [r14], r14
0x140023ad2  jz      short loc_140023B0D
0x140023ad4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140023adb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023ae2  jz      short loc_140023B05
0x140023ae4  mov     rcx, [rbx+10h]
0x140023ae8  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x140023aef  mov     r9d, 2Ah ; '*'
0x140023af5  mov     [rsp+58h+var_38], rax
0x140023afa  mov     dl, 4
0x140023afc  lea     r8d, [r9-23h]
0x140023b00  call    WPP_RECORDER_SF_
0x140023b05  mov     rcx, rbx
0x140023b08  call    XilCommand_WriteDoorbell
0x140023b0d  lea     rcx, [rbx+60h]
0x140023b11  mov     rdx, [rcx]
0x140023b14  cmp     rdx, rcx
0x140023b17  jnz     short loc_140023B2B
0x140023b19  lea     rax, [rbp+var_18]
0x140023b1d  mov     qword ptr [rbp+var_18+8], rax
0x140023b21  lea     rax, [rbp+var_18]
0x140023b25  mov     qword ptr [rbp+var_18], rax
0x140023b29  jmp     short loc_140023B51
0x140023b2b  mov     rax, [rcx+8]
0x140023b2f  mov     qword ptr [rbp+var_18+8], rax
0x140023b33  lea     rax, [rbp+var_18]
0x140023b37  mov     qword ptr [rbp+var_18], rdx
0x140023b3b  mov     [rdx+8], rax
0x140023b3f  lea     rdx, [rbp+var_18]
0x140023b43  mov     rax, qword ptr [rbp+var_18+8]
0x140023b47  mov     [rax], rdx
0x140023b4a  mov     [rcx+8], rcx
0x140023b4e  mov     [rcx], rcx
0x140023b51  mov     rdx, qword ptr [rbp+var_18]
0x140023b55  lea     rax, [rbp+var_18]
0x140023b59  cmp     rdx, rax
0x140023b5c  jz      short loc_140023B8E
0x140023b5e  lea     rax, [rbp+var_18]
0x140023b62  cmp     [rdx+8], rax
0x140023b66  jnz     short loc_140023B87
0x140023b68  mov     rax, [rdx]
0x140023b6b  cmp     [rax+8], rdx
0x140023b6f  jnz     short loc_140023B87
0x140023b71  lea     rcx, [rbp+var_18]
0x140023b75  mov     qword ptr [rbp+var_18], rax
0x140023b79  mov     [rax+8], rcx
0x140023b7d  mov     rcx, rbx
0x140023b80  call    Command_InternalSendCommand
0x140023b85  jmp     short loc_140023B51
0x140023b87  mov     ecx, 3
0x140023b8c  int     29h; Win8: RtlFailFast(ecx)
0x140023b8e  mov     esi, 2
0x140023b93  mov     rcx, [rbx+70h]
0x140023b97  call    DynamicLock_Release
0x140023b9c  test    r13b, r13b
0x140023b9f  jz      short loc_140023BAA
0x140023ba1  mov     rcx, [rbx+8]
0x140023ba5  call    Controller_RaiseAndTrackIrql
0x140023baa  test    rdi, rdi
0x140023bad  jz      short loc_140023BCE
0x140023baf  mov     r9d, esi
0x140023bb2  mov     byte ptr [rdi+3Ch], 19h
0x140023bb6  mov     r8, rdi
0x140023bb9  mov     rdx, rbx
0x140023bbc  call    Etw_CommandCompleteError
0x140023bc1  xor     r8d, r8d
0x140023bc4  mov     edx, esi
0x140023bc6  mov     rcx, rdi
0x140023bc9  call    Command_ProcessCrbCompletion
0x140023bce  add     rsp, 58h
0x140023bd2  pop     r15
0x140023bd4  pop     r14
0x140023bd6  pop     r13
0x140023bd8  pop     r12
0x140023bda  pop     rdi
0x140023bdb  pop     rsi
0x140023bdc  pop     rbx
0x140023bdd  pop     rbp
0x140023bde  retn
```
