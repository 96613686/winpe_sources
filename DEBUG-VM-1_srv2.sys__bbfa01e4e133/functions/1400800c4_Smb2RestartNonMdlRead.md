# Smb2RestartNonMdlRead

- ea: `0x1400800c4`
- end: `0x14008035c`
- name: `Smb2RestartNonMdlRead`
- size: `664`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14007f4c0`
- `0x14007fd00`

## callees

- `0x1400041a0`
- `0x140004560`
- `0x140005070`
- `0x140006ad0`
- `0x140007090`
- `0x140007400`
- `0x140008190`
- `0x1400125d0`
- `0x140015000`
- `0x1400186f0`
- `0x1400222ec`
- `0x140022958`
- `0x1400384d0`
- `0x14007f2f0`
- `0x1400800c4`
- `0x140080364`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140080283`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140080283`
- `ntoskrnl!KeDelayExecutionThread` at `0x14009867d`
- `ntoskrnl!KeDelayExecutionThread` at `0x14009867d`
- `ntoskrnl!IofCallDriver` at `0x140098650`
- `ntoskrnl!IofCallDriver` at `0x140098650`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x1400800e6`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x1400800e6`

## string_xrefs

- `0x140080182`: `Smb2RestartNonMdlRead`
- `0x1400801ef`: `Smb2RestartNonMdlRead`
- `0x140098634`: `Smb2RestartNonMdlRead`
- `0x140080250`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`

## pseudocode

```c
NTSTATUS __fastcall Smb2RestartNonMdlRead(__int64 a1)
{
  __int64 v1; // rdi
  __int64 BufferNoTransportHeader; // rax
  __int64 v4; // rcx
  PVOID v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rbp
  char v9; // al
  __int64 v10; // rcx
  NTSTATUS result; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  char v14; // cl
  __int64 v15; // r8
  __int64 v16; // r9
  char v17; // r14
  int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // ebp
  char v21; // bp
  __int64 v22; // rdx
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-68h]
  ULONG BugCheckOnFailurea; // [rsp+20h] [rbp-68h]
  ULONG BugCheckOnFailureb; // [rsp+20h] [rbp-68h]
  int Priority; // [rsp+28h] [rbp-60h]
  bool v27; // [rsp+60h] [rbp-28h]
  char v28; // [rsp+68h] [rbp-20h]
  union _LARGE_INTEGER Interval; // [rsp+90h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 560);
  BufferNoTransportHeader = SrvNetAllocateBufferNoTransportHeader(*(unsigned int *)(v1 + 236));
  *(_QWORD *)(v1 + 160) = BufferNoTransportHeader;
  if ( !BufferNoTransportHeader )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1);
    }
    Smb2SequentialReadComplete(a1);
    v12 = 1632;
    goto LABEL_14;
  }
  v4 = *(_QWORD *)(BufferNoTransportHeader + 56);
  if ( (*(_BYTE *)(v4 + 10) & 5) != 0 )
    v5 = *(PVOID *)(v4 + 24);
  else
    v5 = MmMapLockedPagesSpecifyCache((PMDL)v4, 0, MmCached, 0, 0, 0x40000010u);
  v6 = *(_QWORD *)(v1 + 160);
  *(_QWORD *)(v1 + 208) = v5;
  v7 = *(_QWORD *)(v6 + 56);
  *(_QWORD *)(v1 + 200) = v7;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1);
    }
    Smb2SequentialReadComplete(a1);
    v12 = 1647;
LABEL_14:
    v13 = 3221225989LL;
LABEL_15:
    Smb2SetError(a1, v13, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c", v12);
    return Srv2CompleteWorkItem(a1, 0);
  }
  LOBYTE(v7) = 2;
  if ( (*(_BYTE *)(v1 + 264) & 2) == 0 )
  {
    v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 96) + 8LL) + 80LL);
    if ( v8 )
    {
      if ( *(_DWORD *)v8 > 0x10u && *(_QWORD *)(v8 + 16) )
      {
        LOBYTE(BugCheckOnFailure) = 1;
        SRV2_PERF_ENTER_EX(a1 + 584, v7, 1660, "Smb2RestartNonMdlRead", BugCheckOnFailure);
        v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, _QWORD, __int64, _QWORD))(v8 + 16))(
               *(_QWORD *)(v1 + 88),
               v1 + 192,
               *(unsigned int *)(v1 + 236),
               0,
               *(_DWORD *)(v1 + 252),
               *(_QWORD *)(*(_QWORD *)(v1 + 200) + 32LL) + *(unsigned int *)(*(_QWORD *)(v1 + 200) + 44LL),
               *(_QWORD *)(a1 + 120) + 48LL,
               *(_QWORD *)(v1 + 96));
        LOBYTE(BugCheckOnFailurea) = 1;
        v10 = a1 + 584;
        if ( v9 )
        {
          SRV2_PERF_ENTER_EX(v10, 0, 1675, "Smb2RestartNonMdlRead", BugCheckOnFailurea);
          return Smb2ContinueUncachedRead(a1);
        }
        SRV2_PERF_ENTER_EX(v10, 0, 1680, "Smb2RestartNonMdlRead", BugCheckOnFailurea);
      }
    }
  }
  v14 = *(_BYTE *)(v1 + 264);
  v15 = *(_QWORD *)(v1 + 200);
  if ( (v14 & 4) != 0 )
  {
    v16 = *(_QWORD *)(v15 + 32) + *(unsigned int *)(v15 + 44);
    v17 = 1;
    LOBYTE(v15) = 3;
    v18 = Smb2BuildPipeReadOrWriteRequest(a1, *(_QWORD *)(v1 + 88), v15, v16, *(_DWORD *)(v1 + 236));
  }
  else
  {
    v17 = 0;
    v28 = 0;
    v27 = (v14 & 0x10) != 0;
    LOBYTE(Priority) = 0;
    LOBYTE(BugCheckOnFailure) = 3;
    v18 = Smb2BuildReadOrWriteRequest(
            a1,
            0,
            *(_QWORD *)(v1 + 88),
            *(_QWORD *)(v1 + 96),
            BugCheckOnFailure,
            Priority,
            *(_QWORD *)(v15 + 32) + *(unsigned int *)(v15 + 44),
            *(_DWORD *)(v1 + 236),
            v15,
            *(_QWORD *)(v1 + 192),
            *(_DWORD *)(v1 + 252),
            Srv2PostOnCompletionAndClearCancel,
            v27,
            v28);
  }
  v20 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 30, &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1, v18);
    }
    Smb2SequentialReadComplete(a1);
    v12 = 1722;
    v13 = v20;
    goto LABEL_15;
  }
  v21 = v17;
  *(_QWORD *)(a1 + 48) = Smb2ContinueUncachedIrpRead;
  if ( (*(_BYTE *)(v1 + 264) & 8) != 0 )
    v21 = 1;
  LOBYTE(v19) = v21;
  if ( (int)Srv2MarkWorkItemCancellable(a1, v19) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1);
    }
    Smb2SequentialReadComplete(a1);
    v12 = 1741;
    v13 = 3221225760LL;
    goto LABEL_15;
  }
  if ( v21 )
    Srv2ReferenceConnection(a1);
  LOBYTE(BugCheckOnFailureb) = 1;
  LOBYTE(v22) = 3;
  SRV2_PERF_ENTER_EX(a1 + 584, v22, 1752, "Smb2RestartNonMdlRead", BugCheckOnFailureb);
  result = IofCallDriver(*(PDEVICE_OBJECT *)(v1 + 96), *(PIRP *)(a1 + 120));
  if ( v21 )
  {
    Interval.QuadPart = -5000;
    KeDelayExecutionThread(0, 0, &Interval);
    if ( (unsigned int)Srv2MarkWorkItemPending(a1) )
      return Srv2DereferenceWorkItem(a1);
    else
      return Smb2GoAsync2(a1);
  }
  return result;
}

```

## disassembly

```asm
0x1400800c4  mov     [rsp+arg_8], rbx
0x1400800c9  mov     [rsp+arg_10], rbp
0x1400800ce  push    rsi
0x1400800cf  push    rdi
0x1400800d0  push    r14
0x1400800d2  sub     rsp, 70h
0x1400800d6  mov     rdi, [rcx+230h]
0x1400800dd  mov     rbx, rcx
0x1400800e0  mov     ecx, [rdi+0ECh]
0x1400800e6  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x1400800ed  nop     dword ptr [rax+rax+00h]
0x1400800f2  mov     [rdi+0A0h], rax
0x1400800f9  test    rax, rax
0x1400800fc  jz      loc_14008022A
0x140080102  mov     rcx, [rax+38h]; MemoryDescriptorList
0x140080106  mov     esi, 1
0x14008010b  test    byte ptr [rcx+0Ah], 5
0x14008010f  jz      loc_14008026B
0x140080115  mov     rax, [rcx+18h]
0x140080119  mov     rcx, [rdi+0A0h]
0x140080120  mov     [rdi+0D0h], rax
0x140080127  mov     rdx, [rcx+38h]
0x14008012b  mov     [rdi+0C8h], rdx
0x140080132  test    rax, rax
0x140080135  jz      loc_1400802C3
0x14008013b  mov     dl, 2
0x14008013d  test    [rdi+108h], dl
0x140080143  jnz     loc_14008031A
0x140080149  mov     rax, [rdi+60h]
0x14008014d  mov     rcx, [rax+8]
0x140080151  mov     rbp, [rcx+50h]
0x140080155  test    rbp, rbp
0x140080158  jz      loc_14008031A
0x14008015e  cmp     dword ptr [rbp+0], 10h
0x140080162  jbe     loc_14008031A
0x140080168  cmp     qword ptr [rbp+10h], 0
0x14008016d  jz      loc_14008031A
0x140080173  lea     r14, [rbx+248h]
0x14008017a  mov     byte ptr [rsp+88h+BugCheckOnFailure], sil
0x14008017f  mov     rcx, r14
0x140080182  lea     r9, aSmb2restartnon; "Smb2RestartNonMdlRead"
0x140080189  mov     r8d, 67Ch
0x14008018f  call    SRV2_PERF_ENTER_EX
0x140080194  mov     rax, [rdi+0C8h]
0x14008019b  lea     rdx, [rdi+0C0h]
0x1400801a2  mov     rcx, [rdi+60h]
0x1400801a6  xor     r9d, r9d
0x1400801a9  mov     r10, [rbx+78h]
0x1400801ad  mov     [rsp+88h+var_50], rcx
0x1400801b2  add     r10, 30h ; '0'
0x1400801b6  mov     r8d, [rax+2Ch]
0x1400801ba  add     r8, [rax+20h]
0x1400801be  mov     rax, [rbp+10h]
0x1400801c2  mov     rcx, [rdi+58h]
0x1400801c6  mov     [rsp+88h+var_58], r10
0x1400801cb  mov     qword ptr [rsp+88h+Priority], r8
0x1400801d0  mov     r8d, [rdi+0FCh]
0x1400801d7  mov     [rsp+88h+BugCheckOnFailure], r8d
0x1400801dc  mov     r8d, [rdi+0ECh]
0x1400801e3  call    _guard_dispatch_icall
0x1400801e8  xor     edx, edx
0x1400801ea  mov     byte ptr [rsp+88h+BugCheckOnFailure], sil
0x1400801ef  lea     r9, aSmb2restartnon; "Smb2RestartNonMdlRead"
0x1400801f6  mov     rcx, r14
0x1400801f9  test    al, al
0x1400801fb  jz      loc_14008030F
0x140080201  mov     r8d, 68Bh
0x140080207  call    SRV2_PERF_ENTER_EX
0x14008020c  mov     rcx, rbx
0x14008020f  call    Smb2ContinueUncachedRead
0x140080214  lea     r11, [rsp+88h+var_18]
0x140080219  mov     rbx, [r11+28h]
0x14008021d  mov     rbp, [r11+30h]
0x140080221  mov     rsp, r11
0x140080224  pop     r14
0x140080226  pop     rdi
0x140080227  pop     rsi
0x140080228  retn
0x14008022a  mov     rcx, cs:WPP_GLOBAL_Control
0x140080231  lea     rax, WPP_GLOBAL_Control
0x140080238  cmp     rcx, rax
0x14008023b  jnz     short loc_140080294
0x14008023d  mov     rcx, rbx
0x140080240  call    Smb2SequentialReadComplete
0x140080245  mov     r9d, 660h
0x14008024b  mov     edx, 0C0000205h
0x140080250  lea     r8, aOnecoreBaseFsR_9; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140080257  mov     rcx, rbx
0x14008025a  call    _Smb2SetError
0x14008025f  xor     edx, edx
0x140080261  mov     rcx, rbx
0x140080264  call    Srv2CompleteWorkItem
0x140080269  jmp     short loc_140080214
0x14008026b  mov     [rsp+88h+Priority], 40000010h; Priority
0x140080273  xor     r9d, r9d; RequestedAddress
0x140080276  mov     r8d, esi; CacheType
0x140080279  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140080281  xor     edx, edx; AccessMode
0x140080283  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14008028a  nop     dword ptr [rax+rax+00h]
0x14008028f  jmp     loc_140080119
0x140080294  test    dword ptr [rcx+2Ch], 800000h
0x14008029b  jz      short loc_14008023D
0x14008029d  mov     esi, 1
0x1400802a2  cmp     [rcx+29h], sil
0x1400802a6  jb      short loc_14008023D
0x1400802a8  mov     rcx, [rcx+18h]
0x1400802ac  lea     edx, [rsi+1Bh]
0x1400802af  mov     r9, rbx
0x1400802b2  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x1400802b9  call    WPP_SF_q
0x1400802be  jmp     loc_14008023D
0x1400802c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400802ca  lea     rax, WPP_GLOBAL_Control
0x1400802d1  cmp     rcx, rax
0x1400802d4  jz      loc_1400984CE
0x1400802da  test    dword ptr [rcx+2Ch], 800000h
0x1400802e1  jz      loc_1400984CE
0x1400802e7  cmp     [rcx+29h], sil
0x1400802eb  jb      loc_1400984CE
0x1400802f1  mov     rcx, [rcx+18h]
0x1400802f5  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x1400802fc  mov     edx, 1Dh
0x140080301  mov     r9, rbx
0x140080304  call    WPP_SF_q
0x140080309  nop
0x14008030a  jmp     loc_1400984CE
0x14008030f  mov     r8d, 690h
0x140080315  call    SRV2_PERF_ENTER_EX
0x14008031a  mov     cl, [rdi+108h]
0x140080320  mov     r8, [rdi+0C8h]
0x140080327  mov     r10d, [rdi+0ECh]
0x14008032e  test    cl, 4
0x140080331  jz      loc_1400984E1
0x140080337  mov     r9d, [r8+2Ch]
0x14008033b  mov     rcx, rbx
0x14008033e  add     r9, [r8+20h]
0x140080342  mov     r14b, sil
0x140080345  mov     rdx, [rdi+58h]
0x140080349  mov     r8b, 3
0x14008034c  mov     [rsp+88h+BugCheckOnFailure], r10d
0x140080351  call    Smb2BuildPipeReadOrWriteRequest
0x140080356  nop
0x140080357  jmp     loc_140098548
0x1400984ce  mov     rcx, rbx
0x1400984d1  call    Smb2SequentialReadComplete
0x1400984d6  mov     r9d, 66Fh
0x1400984dc  jmp     loc_14008024B
0x1400984e1  mov     edx, [r8+2Ch]
0x1400984e5  xor     r14b, r14b
0x1400984e8  add     rdx, [r8+20h]
0x1400984ec  mov     rax, [rdi+0C0h]
0x1400984f3  mov     r9, [rdi+60h]
0x1400984f7  mov     [rsp+88h+var_20], r14b
0x1400984fc  shr     cl, 4
0x1400984ff  and     cl, sil
0x140098502  mov     [rsp+88h+var_28], cl
0x140098506  lea     rcx, Srv2PostOnCompletionAndClearCancel
0x14009850d  mov     [rsp+88h+var_30], rcx
0x140098512  mov     ecx, [rdi+0FCh]
0x140098518  mov     [rsp+88h+var_38], ecx
0x14009851c  mov     rcx, rbx
0x14009851f  mov     [rsp+88h+var_40], rax
0x140098524  mov     [rsp+88h+var_48], r8
0x140098529  mov     r8, [rdi+58h]
0x14009852d  mov     dword ptr [rsp+88h+var_50], r10d
0x140098532  mov     [rsp+88h+var_58], rdx
0x140098537  xor     edx, edx
0x140098539  mov     byte ptr [rsp+88h+Priority], r14b
0x14009853e  mov     byte ptr [rsp+88h+BugCheckOnFailure], 3
0x140098543  call    Smb2BuildReadOrWriteRequest
0x140098548  mov     ebp, eax
0x14009854a  test    eax, eax
0x14009854c  jns     short loc_1400985A1
0x14009854e  mov     rcx, cs:WPP_GLOBAL_Control
0x140098555  lea     rax, WPP_GLOBAL_Control
0x14009855c  cmp     rcx, rax
0x14009855f  jz      short loc_14009858C
0x140098561  test    dword ptr [rcx+2Ch], 800000h
0x140098568  jz      short loc_14009858C
0x14009856a  cmp     [rcx+29h], sil
0x14009856e  jb      short loc_14009858C
0x140098570  mov     rcx, [rcx+18h]
0x140098574  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x14009857b  mov     edx, 1Eh
0x140098580  mov     [rsp+88h+BugCheckOnFailure], ebp
0x140098584  mov     r9, rbx
0x140098587  call    WPP_SF_qD
0x14009858c  mov     rcx, rbx
0x14009858f  call    Smb2SequentialReadComplete
0x140098594  mov     r9d, 6BAh
0x14009859a  mov     edx, ebp
0x14009859c  jmp     loc_140080250
0x1400985a1  lea     rax, Smb2ContinueUncachedIrpRead
0x1400985a8  movzx   ebp, r14b
0x1400985ac  mov     [rbx+30h], rax
0x1400985b0  mov     rcx, rbx
0x1400985b3  test    byte ptr [rdi+108h], 8
0x1400985ba  cmovnz  ebp, esi
0x1400985bd  mov     dl, bpl
0x1400985c0  call    Srv2MarkWorkItemCancellable
0x1400985c5  test    eax, eax
0x1400985c7  jns     short loc_14009861B
0x1400985c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400985d0  lea     rax, WPP_GLOBAL_Control
0x1400985d7  cmp     rcx, rax
0x1400985da  jz      short loc_140098603
0x1400985dc  test    dword ptr [rcx+2Ch], 800000h
0x1400985e3  jz      short loc_140098603
0x1400985e5  cmp     [rcx+29h], sil
0x1400985e9  jb      short loc_140098603
0x1400985eb  mov     rcx, [rcx+18h]
0x1400985ef  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x1400985f6  mov     edx, 1Fh
0x1400985fb  mov     r9, rbx
0x1400985fe  call    WPP_SF_q
0x140098603  mov     rcx, rbx
0x140098606  call    Smb2SequentialReadComplete
0x14009860b  mov     r9d, 6CDh
0x140098611  mov     edx, 0C0000120h
0x140098616  jmp     loc_140080250
0x14009861b  test    bpl, bpl
0x14009861e  jz      short loc_140098628
0x140098620  mov     rcx, rbx
0x140098623  call    Srv2ReferenceConnection
0x140098628  lea     rcx, [rbx+248h]
0x14009862f  mov     byte ptr [rsp+88h+BugCheckOnFailure], sil
0x140098634  lea     r9, aSmb2restartnon; "Smb2RestartNonMdlRead"
0x14009863b  mov     r8d, 6D8h
0x140098641  mov     dl, 3
0x140098643  call    SRV2_PERF_ENTER_EX
0x140098648  mov     rdx, [rbx+78h]; Irp
0x14009864c  mov     rcx, [rdi+60h]; DeviceObject
0x140098650  call    cs:__imp_IofCallDriver
0x140098657  nop     dword ptr [rax+rax+00h]
0x14009865c  test    bpl, bpl
0x14009865f  jz      loc_140080214
0x140098665  lea     r8, [rsp+88h+Interval]; Interval
0x14009866d  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFFFFFEC78h
0x140098679  xor     edx, edx; Alertable
0x14009867b  xor     ecx, ecx; WaitMode
0x14009867d  call    cs:__imp_KeDelayExecutionThread
0x140098684  nop     dword ptr [rax+rax+00h]
0x140098689  mov     rcx, rbx
0x14009868c  call    Srv2MarkWorkItemPending
0x140098691  mov     rcx, rbx
0x140098694  test    eax, eax
0x140098696  jnz     short loc_1400986A3
0x140098698  call    Smb2GoAsync2
0x14009869d  nop
0x14009869e  jmp     loc_140080214
0x1400986a3  call    Srv2DereferenceWorkItem
0x1400986a8  nop
0x1400986a9  jmp     loc_140080214
```
