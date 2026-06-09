# Srv2ProcCompleteRequest

- ea: `0x140008410`
- end: `0x140008934`
- name: `Srv2ProcCompleteRequest`
- size: `1316`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140008200`
- `0x140062f00`

## callees

- `0x140004960`
- `0x140005070`
- `0x1400051dc`
- `0x140006218`
- `0x140006ad0`
- `0x140008410`
- `0x140008940`
- `0x140009190`
- `0x14000a560`
- `0x140022690`
- `0x1400229ac`
- `0x1400384d0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140008843`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140008843`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400088d2`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400088d2`
- `ntoskrnl!RtlInitAnsiString` at `0x140008765`
- `ntoskrnl!RtlInitAnsiString` at `0x140008765`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000885f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000885f`
- `HAL!KeQueryPerformanceCounter` at `0x14000870b`
- `HAL!KeQueryPerformanceCounter` at `0x14000870b`
- `srvnet!SrvNetSendData` at `0x14000863c`
- `srvnet!SrvNetSendData` at `0x14000863c`

## string_xrefs

- `0x14000874b`: `Srv2ProcCompleteRequest`
- `0x14000881c`: `Srv2PostToThreadPool`

## pseudocode

```c
void __fastcall Srv2ProcCompleteRequest(__int64 a1, unsigned int a2, unsigned __int8 a3)
{
  int v3; // edi
  __int64 v5; // r8
  char v6; // al
  __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned int *v9; // rdi
  __int64 v10; // r8
  __int16 v11; // ax
  __int16 v12; // dx
  __int16 v13; // ax
  void (__fastcall *v14)(__int64); // rax
  __int64 v15; // rsi
  __int64 v16; // rax
  char v17; // cl
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rbp
  __int64 v21; // r9
  __int64 v22; // rax
  __int64 v23; // rdx
  char v24; // si
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // edx
  int v29; // ecx
  int v30; // eax
  bool v31; // zf
  __int64 v32; // rdi
  __int64 v33; // rdi
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rcx
  int v37; // [rsp+20h] [rbp-38h]
  struct _STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  v3 = a3;
  v5 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 29, &WPP_1f56813514af312e5a39176f5ad11993_Traceguids, a1, a2, v3);
  }
  if ( *(_BYTE *)(a1 + 472) || *(_BYTE *)(a1 + 474) )
  {
    v6 = *(_BYTE *)(a1 + 474);
    if ( v6 )
      LOBYTE(v3) = 0;
    v7 = *(_QWORD *)(a1 + 416);
    if ( v7 )
    {
      v24 = *(_BYTE *)(a1 + 475);
      if ( v6 )
        *(_BYTE *)(v7 + 474) = v6;
      if ( !(unsigned __int8)Srv2ProcPartialCompleteCompoundedRequest(a1, (unsigned __int8)v3, v5) && v24 )
      {
        if ( *(_BYTE *)(a1 + 474) )
          Srv2ProcPartialCompleteCompoundedReceive(*(_QWORD *)(a1 + 416));
        else
          Srv2ContinueCompoundedReceive(a1);
      }
    }
    else if ( (_BYTE)v3 && *(_QWORD *)(a1 + 96) )
    {
      v8 = *(_QWORD *)(a1 + 312);
      *(_QWORD *)(a1 + 144) = Srv2ProcSendComplete;
      v9 = (unsigned int *)(a1 + 128);
      *(_QWORD *)(a1 + 160) = Srv2DereferenceWorkItem;
      *(_QWORD *)(a1 + 168) = *(_QWORD *)(a1 + 120);
      *(_QWORD *)(a1 + 152) = a1;
      *(_DWORD *)(a1 + 132) = 0;
      *(_DWORD *)(a1 + 128) = *(_DWORD *)(v8 + 36);
      if ( (*(_DWORD *)(a1 + 484) & 4) != 0 )
      {
        *(_QWORD *)(a1 + 136) = *(_QWORD *)(v8 + 80);
        v10 = *(_QWORD *)(v8 + 80);
        v11 = *(_WORD *)(v10 + 10);
        v12 = v11 & 0xEFFF;
        v13 = v11 | 0x1000;
        if ( *(_QWORD *)(v10 + 24) == *(_QWORD *)(v8 + 24) )
          v12 = v13;
        *(_WORD *)(v10 + 10) = v12;
      }
      else
      {
        *(_QWORD *)(a1 + 136) = *(_QWORD *)(v8 + 56);
      }
      v14 = *(void (__fastcall **)(__int64))(a1 + 536);
      if ( v14 )
        v14(a1);
      if ( *(_BYTE *)(a1 + 556) )
      {
        v30 = *(_DWORD *)(a1 + 552);
        *(_DWORD *)(a1 + 132) |= 1u;
        *(_DWORD *)(a1 + 224) = v30;
      }
      v15 = a1 + 584;
      DestinationString = 0;
      v16 = MEMORY[0xFFFFF78000000014];
      v17 = *(_BYTE *)(a1 + 714);
      if ( v17 == 5 || v17 == 4 )
      {
        v23 = *(_QWORD *)(a1 + 744);
        if ( v23 <= MEMORY[0xFFFFF78000000014] - v23 )
          v23 = MEMORY[0xFFFFF78000000014] - v23;
        *(_QWORD *)(a1 + 704) = v23;
      }
      *(_BYTE *)(a1 + 714) = 5;
      *(_QWORD *)(a1 + 744) = v16;
      if ( *(_BYTE *)(a1 + 600) )
      {
        PerformanceCounter = KeQueryPerformanceCounter(0);
        v26 = *(unsigned __int8 *)(a1 + 712);
        if ( (_BYTE)v26 != 0xFF && (_BYTE)v26 != 5 )
        {
          v27 = *(_QWORD *)(a1 + 720);
          if ( PerformanceCounter.QuadPart > v27 )
            *(_QWORD *)(v15 + 8 * v26 + 40) += PerformanceCounter.QuadPart - v27;
          ++*(_WORD *)(v15 + 2 * v26 + 18);
        }
        *(_BYTE *)(a1 + 712) = 5;
        *(LARGE_INTEGER *)(a1 + 720) = PerformanceCounter;
        RtlInitAnsiString(&DestinationString, "Srv2ProcCompleteRequest");
        if ( (Microsoft_Windows_SMBServerEnableBits & 4) != 0 )
          McTemplateK0qqhsr2_EtwWriteTransfer(
            v29,
            v28,
            a1 + 584,
            5,
            3,
            DestinationString.Length,
            (__int64)DestinationString.Buffer);
      }
      v18 = *(_QWORD *)(a1 + 96);
      v19 = *(_QWORD *)(a1 + 560);
      v20 = *(_QWORD *)(v18 + 480);
      v21 = *(_QWORD *)(v18 + 496);
      if ( byte_140058150 )
      {
        v22 = *(_QWORD *)(v19 + 56);
        if ( v22 )
        {
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v22 + 104) + 320LL), *v9);
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v19 + 56) + 104LL) + 328LL), *v9);
        }
        if ( *(_QWORD *)(v19 + 32) )
        {
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v19 + 40) + 168LL), *v9);
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v19 + 40) + 176LL), *v9);
        }
      }
      if ( (*(_DWORD *)(a1 + 484) & 0x2040) != 0 && !Smb2CompressionDisabled )
      {
        *(_DWORD *)(a1 + 216) = *(_DWORD *)(v21 + 144);
        *(_DWORD *)(a1 + 220) = *(_DWORD *)(v21 + 152);
        v35 = *(_QWORD *)(v19 + 56);
        if ( v35 )
        {
          *(_QWORD *)(a1 + 232) = *(_QWORD *)(v35 + 104) + 624LL;
          *(_QWORD *)(a1 + 240) = *(_QWORD *)(*(_QWORD *)(v19 + 56) + 104LL) + 640LL;
          v36 = *(_QWORD *)(*(_QWORD *)(v19 + 56) + 104LL) + 648LL;
        }
        else
        {
          *(_QWORD *)(a1 + 232) = 0;
          v36 = 0;
          *(_QWORD *)(a1 + 240) = 0;
        }
        *(_QWORD *)(a1 + 248) = v36;
        if ( (*(_BYTE *)(v21 + 49) & 0x20) != 0 )
          *(_DWORD *)(a1 + 132) |= 2u;
      }
      if ( *(_BYTE *)(v19 + 7) )
      {
        *(_DWORD *)(a1 + 180) = _InterlockedExchangeAdd((volatile signed __int32 *)(v21 + 196), 0xFFFFFFFF);
        *(_BYTE *)(v19 + 7) = 0;
      }
      else
      {
        *(_DWORD *)(a1 + 180) = -1;
      }
      if ( *(_DWORD *)(a1 + 216) && KeGetCurrentIrql() )
      {
        v31 = *(_DWORD *)(a1 + 8) == 5;
        *(_QWORD *)(a1 + 48) = Smb2SendDataAtPassive;
        *(_DWORD *)(a1 + 72) = 0;
        if ( v31 )
        {
          LOBYTE(v37) = 1;
          LOBYTE(v34) = 1;
          SRV2_PERF_ENTER_EX(a1 + 584, v34, 391, "Srv2PostToThreadPool", v37);
        }
        v32 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
        v33 = *(_QWORD *)(v32 + 8LL * KeGetCurrentNodeNumber() + 8);
        if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v33 + 16), (PSLIST_ENTRY)(a1 + 32)) )
        {
          if ( *(_WORD *)(v33 + 66) )
            RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v33);
        }
      }
      else
      {
        SrvNetSendData(v20, a1 + 128);
      }
    }
    else
    {
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            30,
            &WPP_1f56813514af312e5a39176f5ad11993_Traceguids,
            *(_QWORD *)(a1 + 96),
            a1);
        }
        Srv2CloseConnection(*(PVOID *)(a1 + 96));
      }
      Srv2DereferenceWorkItem(a1);
    }
  }
  else
  {
    *(_BYTE *)(a1 + 473) = v3;
  }
}

```

## disassembly

```asm
0x140008410  mov     [rsp+arg_10], rbx
0x140008415  mov     [rsp+arg_18], rsi
0x14000841a  push    rdi
0x14000841b  sub     rsp, 50h
0x14000841f  movzx   edi, r8b
0x140008423  mov     rbx, rcx
0x140008426  mov     r8d, edx
0x140008429  mov     rcx, cs:WPP_GLOBAL_Control
0x140008430  lea     rsi, WPP_GLOBAL_Control
0x140008437  cmp     rcx, rsi
0x14000843a  jz      short loc_140008447
0x14000843c  mov     eax, [rcx+2Ch]
0x14000843f  test    al, 20h
0x140008441  jnz     loc_14000888F
0x140008447  cmp     byte ptr [rbx+1D8h], 0
0x14000844e  jz      loc_1400087C5
0x140008454  movzx   eax, byte ptr [rbx+1DAh]
0x14000845b  test    al, al
0x14000845d  jnz     loc_1400088BF
0x140008463  mov     rcx, [rbx+1A0h]
0x14000846a  test    rcx, rcx
0x14000846d  jnz     loc_140008690
0x140008473  test    dil, dil
0x140008476  jz      loc_1400086E8
0x14000847c  cmp     [rbx+60h], rcx
0x140008480  jz      loc_1400086E8
0x140008486  mov     rcx, [rbx+138h]
0x14000848d  lea     rax, Srv2ProcSendComplete
0x140008494  mov     [rbx+90h], rax
0x14000849b  lea     rdi, [rbx+80h]
0x1400084a2  lea     rax, Srv2DereferenceWorkItem
0x1400084a9  mov     [rsp+58h+arg_0], rbp
0x1400084ae  mov     [rbx+0A0h], rax
0x1400084b5  mov     rax, [rbx+78h]
0x1400084b9  mov     [rbx+0A8h], rax
0x1400084c0  mov     [rsp+58h+arg_8], r14
0x1400084c5  xor     r14d, r14d
0x1400084c8  mov     [rbx+98h], rbx
0x1400084cf  mov     [rbx+84h], r14d
0x1400084d6  mov     eax, [rcx+24h]
0x1400084d9  mov     [rdi], eax
0x1400084db  mov     eax, [rbx+1E4h]
0x1400084e1  test    al, 4
0x1400084e3  jz      loc_140008663
0x1400084e9  mov     rax, [rcx+50h]
0x1400084ed  mov     r9d, 0FFFFEFFFh
0x1400084f3  mov     [rbx+88h], rax
0x1400084fa  mov     r8, [rcx+50h]
0x1400084fe  mov     rcx, [rcx+18h]
0x140008502  movzx   edx, word ptr [r8+0Ah]
0x140008507  movzx   eax, dx
0x14000850a  and     dx, r9w
0x14000850e  or      ax, 1000h
0x140008512  cmp     [r8+18h], rcx
0x140008516  cmovz   dx, ax
0x14000851a  mov     [r8+0Ah], dx
0x14000851f  mov     rax, [rbx+218h]
0x140008526  test    rax, rax
0x140008529  jz      short loc_140008533
0x14000852b  mov     rcx, rbx
0x14000852e  call    _guard_dispatch_icall
0x140008533  cmp     [rbx+22Ch], r14b
0x14000853a  jnz     loc_1400087AD
0x140008540  mov     rax, 0FFFFF78000000014h
0x14000854a  lea     rsi, [rbx+248h]
0x140008551  xorps   xmm0, xmm0
0x140008554  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140008559  mov     rax, [rax]
0x14000855c  movzx   ecx, byte ptr [rsi+82h]
0x140008563  cmp     cl, 5
0x140008566  jz      loc_140008673
0x14000856c  cmp     cl, 4
0x14000856f  jz      loc_140008673
0x140008575  mov     byte ptr [rsi+82h], 5
0x14000857c  mov     [rsi+0A0h], rax
0x140008583  cmp     [rsi+10h], r14b
0x140008587  jnz     loc_140008709
0x14000858d  cmp     cs:byte_140058150, r14b
0x140008594  mov     rax, [rbx+60h]
0x140008598  mov     r8, [rbx+230h]
0x14000859f  mov     rbp, [rax+1E0h]
0x1400085a6  mov     r9, [rax+1F0h]
0x1400085ad  jz      short loc_1400085FA
0x1400085af  mov     rax, [r8+38h]
0x1400085b3  test    rax, rax
0x1400085b6  jz      short loc_1400085D8
0x1400085b8  mov     ecx, [rdi]
0x1400085ba  mov     rax, [rax+68h]
0x1400085be  lock add [rax+140h], rcx
0x1400085c6  mov     rax, [r8+38h]
0x1400085ca  mov     edx, [rdi]
0x1400085cc  mov     rcx, [rax+68h]
0x1400085d0  lock add [rcx+148h], rdx
0x1400085d8  cmp     [r8+20h], r14
0x1400085dc  jz      short loc_1400085FA
0x1400085de  mov     ecx, [rdi]
0x1400085e0  mov     rax, [r8+28h]
0x1400085e4  lock add [rax+0A8h], rcx
0x1400085ec  mov     ecx, [rdi]
0x1400085ee  mov     rax, [r8+28h]
0x1400085f2  lock add [rax+0B0h], rcx
0x1400085fa  test    dword ptr [rbx+1E4h], 2040h
0x140008604  jnz     loc_14003AA20
0x14000860a  cmp     [r8+7], r14b
0x14000860e  jz      loc_1400086D9
0x140008614  mov     eax, 0FFFFFFFFh
0x140008619  lock xadd [r9+0C4h], eax
0x140008622  mov     [rbx+0B4h], eax
0x140008628  mov     [r8+7], r14b
0x14000862c  cmp     [rdi+58h], r14d
0x140008630  jnz     loc_1400088D2
0x140008636  mov     rdx, rdi
0x140008639  mov     rcx, rbp
0x14000863c  call    cs:__imp_SrvNetSendData
0x140008643  nop     dword ptr [rax+rax+00h]
0x140008648  mov     rbp, [rsp+58h+arg_0]
0x14000864d  mov     r14, [rsp+58h+arg_8]
0x140008652  mov     rbx, [rsp+58h+arg_10]
0x140008657  mov     rsi, [rsp+58h+arg_18]
0x14000865c  add     rsp, 50h
0x140008660  pop     rdi
0x140008661  retn
0x140008663  mov     rax, [rcx+38h]
0x140008667  mov     [rbx+88h], rax
0x14000866e  jmp     loc_14000851F
0x140008673  mov     rdx, [rsi+0A0h]
0x14000867a  mov     rcx, rax
0x14000867d  sub     rcx, rdx
0x140008680  cmp     rdx, rcx
0x140008683  cmovle  rdx, rcx
0x140008687  mov     [rsi+78h], rdx
0x14000868b  jmp     loc_140008575
0x140008690  movzx   esi, byte ptr [rbx+1DBh]
0x140008697  test    al, al
0x140008699  jnz     loc_1400088C7
0x14000869f  movzx   edx, dil
0x1400086a3  mov     rcx, rbx
0x1400086a6  call    Srv2ProcPartialCompleteCompoundedRequest
0x1400086ab  test    al, al
0x1400086ad  jnz     short loc_140008652
0x1400086af  test    sil, sil
0x1400086b2  jz      short loc_140008652
0x1400086b4  cmp     [rbx+1DAh], al
0x1400086ba  jnz     loc_1400087EA
0x1400086c0  mov     rcx, rbx
0x1400086c3  call    Srv2ContinueCompoundedReceive
0x1400086c8  mov     rbx, [rsp+58h+arg_10]
0x1400086cd  mov     rsi, [rsp+58h+arg_18]
0x1400086d2  add     rsp, 50h
0x1400086d6  pop     rdi
0x1400086d7  retn
0x1400086d9  mov     dword ptr [rbx+0B4h], 0FFFFFFFFh
0x1400086e3  jmp     loc_14000862C
0x1400086e8  test    al, al
0x1400086ea  jnz     loc_1400088EB
0x1400086f0  mov     rcx, rbx
0x1400086f3  call    Srv2DereferenceWorkItem
0x1400086f8  mov     rbx, [rsp+58h+arg_10]
0x1400086fd  mov     rsi, [rsp+58h+arg_18]
0x140008702  add     rsp, 50h
0x140008706  pop     rdi
0x140008707  retn
0x140008709  xor     ecx, ecx; PerformanceFrequency
0x14000870b  call    cs:__imp_KeQueryPerformanceCounter
0x140008712  nop     dword ptr [rax+rax+00h]
0x140008717  movzx   r8d, byte ptr [rsi+80h]
0x14000871f  cmp     r8b, 0FFh
0x140008723  jz      short loc_14000874B
0x140008725  cmp     r8b, 5
0x140008729  jz      short loc_14000874B
0x14000872b  mov     r9, [rsi+88h]
0x140008732  cmp     rax, r9
0x140008735  jle     short loc_140008745
0x140008737  mov     rcx, rax
0x14000873a  lea     rdx, [rsi+r8*8]
0x14000873e  sub     rcx, r9
0x140008741  add     [rdx+28h], rcx
0x140008745  inc     word ptr [rsi+r8*2+12h]
0x14000874b  lea     rdx, aSrv2proccomple; "Srv2ProcCompleteRequest"
0x140008752  mov     byte ptr [rsi+80h], 5
0x140008759  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14000875e  mov     [rsi+88h], rax
0x140008765  call    cs:__imp_RtlInitAnsiString
0x14000876c  nop     dword ptr [rax+rax+00h]
0x140008771  test    cs:Microsoft_Windows_SMBServerEnableBits, 4
0x140008778  jz      loc_14000858D
0x14000877e  mov     rax, [rsp+58h+DestinationString.Buffer]
0x140008783  mov     r9d, 5
0x140008789  mov     [rsp+58h+var_28], rax
0x14000878e  mov     r8, rsi
0x140008791  movzx   eax, [rsp+58h+DestinationString.Length]
0x140008796  mov     word ptr [rsp+58h+var_30], ax
0x14000879b  mov     dword ptr [rsp+58h+var_38], 603h
0x1400087a3  call    McTemplateK0qqhsr2_EtwWriteTransfer
0x1400087a8  jmp     loc_14000858D
0x1400087ad  mov     eax, [rbx+228h]
0x1400087b3  or      dword ptr [rbx+84h], 1
0x1400087ba  mov     [rbx+0E0h], eax
0x1400087c0  jmp     loc_140008540
0x1400087c5  cmp     byte ptr [rbx+1DAh], 0
0x1400087cc  jnz     loc_140008454
0x1400087d2  mov     [rbx+1D9h], dil
0x1400087d9  mov     rbx, [rsp+58h+arg_10]
0x1400087de  mov     rsi, [rsp+58h+arg_18]
0x1400087e3  add     rsp, 50h
0x1400087e7  pop     rdi
0x1400087e8  retn
0x1400087ea  mov     rcx, [rbx+1A0h]
0x1400087f1  call    Srv2ProcPartialCompleteCompoundedReceive
0x1400087f6  mov     rbx, [rsp+58h+arg_10]
0x1400087fb  mov     rsi, [rsp+58h+arg_18]
0x140008800  add     rsp, 50h
0x140008804  pop     rdi
0x140008805  retn
0x140008807  cmp     dword ptr [rbx+8], 5
0x14000880b  lea     rax, Smb2SendDataAtPassive
0x140008812  mov     [rbx+30h], rax
0x140008816  mov     [rbx+48h], r14d
0x14000881a  jnz     short loc_140008838
0x14000881c  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140008823  mov     byte ptr [rsp+58h+var_38], 1
0x140008828  mov     r8d, 187h
0x14000882e  mov     dl, 1
0x140008830  mov     rcx, rsi
0x140008833  call    SRV2_PERF_ENTER_EX
0x140008838  mov     rax, [rbx+40h]
0x14000883c  mov     rdi, [rax+88h]
0x140008843  call    cs:__imp_KeGetCurrentNodeNumber
0x14000884a  nop     dword ptr [rax+rax+00h]
0x14000884f  movzx   eax, ax
0x140008852  lea     rdx, [rbx+20h]; ListEntry
0x140008856  mov     rdi, [rdi+rax*8+8]
0x14000885b  lea     rcx, [rdi+10h]; ListHead
0x14000885f  call    cs:__imp_ExpInterlockedPushEntrySList
0x140008866  nop     dword ptr [rax+rax+00h]
0x14000886b  test    rax, rax
0x14000886e  jnz     loc_140008648
0x140008874  movzx   edx, word ptr [rdi+42h]
0x140008878  cmp     r14w, dx
0x14000887c  jz      loc_140008648
0x140008882  mov     rcx, rdi
0x140008885  call    RfspThreadPoolNodeWakeIdleWorker
0x14000888a  jmp     loc_140008648
0x14000888f  cmp     byte ptr [rcx+29h], 2
0x140008893  jb      loc_140008447
0x140008899  mov     rcx, [rcx+18h]
0x14000889d  mov     edx, 1Dh
0x1400088a2  mov     [rsp+58h+var_30], edi
0x1400088a6  mov     r9, rbx
0x1400088a9  mov     dword ptr [rsp+58h+var_38], r8d
0x1400088ae  lea     r8, WPP_1f56813514af312e5a39176f5ad11993_Traceguids
0x1400088b5  call    WPP_SF_qDD
0x1400088ba  jmp     loc_140008447
0x1400088bf  xor     dil, dil
0x1400088c2  jmp     loc_140008463
0x1400088c7  mov     [rcx+1DAh], al
0x1400088cd  jmp     loc_14000869F
0x1400088d2  call    cs:__imp_KeGetCurrentIrql
0x1400088d9  nop     dword ptr [rax+rax+00h]
0x1400088de  test    al, al
0x1400088e0  jz      loc_140008636
0x1400088e6  jmp     loc_140008807
0x1400088eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088f2  cmp     rcx, rsi
0x1400088f5  jz      loc_14003AAAE
0x1400088fb  mov     eax, [rcx+2Ch]
0x1400088fe  test    al, 1
0x140008900  jz      loc_14003AAAE
0x140008906  cmp     byte ptr [rcx+29h], 2
0x14000890a  jb      loc_14003AAAE
0x140008910  mov     r9, [rbx+60h]
0x140008914  lea     r8, WPP_1f56813514af312e5a39176f5ad11993_Traceguids
0x14000891b  mov     rcx, [rcx+18h]
0x14000891f  mov     edx, 1Eh
0x140008924  mov     [rsp+58h+var_38], rbx
0x140008929  call    WPP_SF_qq
0x14000892e  nop
0x14000892f  jmp     loc_14003AAAE
0x14003aa20  cmp     cs:Smb2CompressionDisabled, r14b
0x14003aa27  jnz     loc_14000860A
0x14003aa2d  mov     eax, [r9+90h]
0x14003aa34  mov     [rdi+58h], eax
0x14003aa37  mov     eax, [r9+98h]
0x14003aa3e  mov     [rdi+5Ch], eax
0x14003aa41  mov     rax, [r8+38h]
0x14003aa45  test    rax, rax
0x14003aa48  jz      short loc_14003AA82
0x14003aa4a  mov     rax, [rax+68h]
0x14003aa4e  add     rax, 270h
0x14003aa54  mov     [rbx+0E8h], rax
0x14003aa5b  mov     rax, [r8+38h]
0x14003aa5f  mov     rcx, [rax+68h]
0x14003aa63  add     rcx, 280h
0x14003aa6a  mov     [rbx+0F0h], rcx
0x14003aa71  mov     rax, [r8+38h]
0x14003aa75  mov     rcx, [rax+68h]
0x14003aa79  add     rcx, 288h
0x14003aa80  jmp     short loc_14003AA93
0x14003aa82  mov     [rbx+0E8h], r14
0x14003aa89  mov     rcx, r14
  ... truncated ...
```
