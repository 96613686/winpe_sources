# Srv2FreeWorkItem

- ea: `0x140006580`
- end: `0x140006a1f`
- name: `Srv2FreeWorkItem`
- size: `1183`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006bd30`
- `0x14006bdd0`

## callees

- `0x1400014d0`
- `0x140004960`
- `0x140005070`
- `0x140005470`
- `0x140006580`
- `0x140006ad0`
- `0x14000ab3c`
- `0x1400384d0`
- `0x140060320`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000696e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000696e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400066fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000687e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400066fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000687e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400069f7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400069f7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400067ac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400067ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006741`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006741`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068b9`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400069c0`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400069df`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400069c0`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400069df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400067f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400067f2`
- `ntoskrnl!IoFreeIrp` at `0x1400067e1`
- `ntoskrnl!IoFreeIrp` at `0x1400067e1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140006989`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140006989`
- `srvnet!SrvNetFreeBuffer` at `0x140006659`
- `srvnet!SrvNetFreeBuffer` at `0x14000681e`
- `srvnet!SrvNetFreeBuffer` at `0x140006840`
- `srvnet!SrvNetFreeBuffer` at `0x140006659`
- `srvnet!SrvNetFreeBuffer` at `0x14000681e`
- `srvnet!SrvNetFreeBuffer` at `0x140006840`

## string_xrefs

- `0x14000694f`: `Srv2PostToThreadPool`

## pseudocode

```c
void __fastcall Srv2FreeWorkItem(KSPIN_LOCK *Entry)
{
  unsigned int (__fastcall *v2)(KSPIN_LOCK *); // rax
  KSPIN_LOCK *v3; // rcx
  _QWORD *v4; // rdi
  KSPIN_LOCK v5; // rcx
  KSPIN_LOCK v6; // rbp
  char *v7; // rdi
  KIRQL v8; // al
  KSPIN_LOCK v9; // r8
  char **v10; // rdx
  int v11; // edi
  signed __int64 v12; // rsi
  struct _LOOKASIDE_LIST_EX *v13; // rdi
  IRP *v14; // rcx
  KSPIN_LOCK v15; // rcx
  KSPIN_LOCK v16; // rcx
  char *v17; // rdi
  char *v18; // rax
  KIRQL v19; // al
  __int64 v20; // rdx
  char **v21; // rcx
  bool v22; // zf
  __int64 v23; // rdi
  __int64 v24; // rdi
  __int64 v25; // rdx
  __int64 v26; // r8

  if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
    Smb2OutputWorkItemResponseEtw(Entry);
  v2 = (unsigned int (__fastcall *)(KSPIN_LOCK *))Entry[66];
  if ( !v2 || v2(Entry) != 259 )
  {
    _InterlockedAdd64(
      (volatile signed __int64 *)Srv2HotGlobals + 16 * (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) + 4,
      *((unsigned int *)Entry + 100));
    v3 = (KSPIN_LOCK *)Entry[52];
    Entry[25] = 0;
    Entry[26] = 0;
    Entry[27] = 0;
    Entry[29] = 0;
    Entry[30] = 0;
    Entry[31] = 0;
    Entry[32] = -1;
    if ( v3 )
    {
      if ( v3 == Entry )
      {
        v16 = Entry[57];
        if ( v16 )
        {
          SrvNetFreeBuffer(v16);
          Entry[57] = 0;
          *((_DWORD *)Entry + 116) = 0;
        }
        Entry[52] = 0;
      }
      else
      {
        v17 = (char *)(Entry + 54);
        v18 = (char *)Entry[54];
        if ( v18 && v18 != v17 )
        {
          v19 = KeAcquireSpinLockRaiseToDpc(v3 + 10);
          v20 = *(_QWORD *)v17;
          if ( *(char **)(*(_QWORD *)v17 + 8LL) != v17 )
            goto LABEL_52;
          v21 = (char **)Entry[55];
          if ( *v21 != v17 )
            goto LABEL_52;
          *v21 = (char *)v20;
          *(_QWORD *)(v20 + 8) = v21;
          KeReleaseSpinLock((PKSPIN_LOCK)(Entry[52] + 80), v19);
          Entry[55] = (KSPIN_LOCK)(Entry + 54);
          *(_QWORD *)v17 = v17;
        }
        Srv2DereferenceWorkItem(Entry[52]);
        Entry[52] = 0;
      }
    }
    if ( (*((_DWORD *)Entry + 121) & 1) != 0 )
    {
      v15 = Entry[39];
      if ( Entry[38] != v15 )
        SrvNetFreeBuffer(v15);
    }
    if ( (*((_DWORD *)Entry + 121) & 2) != 0 )
      SrvNetFreeBuffer(Entry[38]);
    v4 = (_QWORD *)Entry[37];
    if ( v4 )
    {
      v14 = (IRP *)v4[5];
      if ( v14 )
        IoFreeIrp(v14);
      ExFreePoolWithTag(v4, 0);
      Entry[37] = 0;
    }
    v5 = Entry[106];
    if ( (*(_BYTE *)(v5 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v5 + 24), (PMDL)Entry[106]);
    *(_QWORD *)Entry[106] = 0;
    *((_WORD *)Entry + 395) = 0;
    if ( (*((_BYTE *)Entry + 330) & 0x20) != 0 )
      MmUnmapLockedPages((PVOID)Entry[43], (PMDL)(Entry + 40));
    *((_DWORD *)Entry + 121) &= 0xFFFFFFBC;
    Entry[39] = (KSPIN_LOCK)(Entry + 96);
    Entry[38] = (KSPIN_LOCK)(Entry + 96);
    Entry[40] = 0;
    *((_DWORD *)Entry + 3) = 220;
    Entry[90] = 0;
    if ( *((_BYTE *)Entry + 600) )
    {
      if ( (Microsoft_Windows_SMBServerEnableBits & 8) != 0 )
        McTemplateK0x_EtwWriteTransfer(v5, &SMB2_EVENT_WORKITEM_END, Entry + 73, Entry + 73);
      *((_BYTE *)Entry + 600) = 0;
    }
    v6 = Entry[12];
    if ( !v6 )
      goto LABEL_22;
    v7 = (char *)(Entry + 13);
    v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 184));
    v9 = Entry[13];
    if ( *(char **)(*(_QWORD *)v7 + 8LL) == v7 )
    {
      v10 = (char **)Entry[14];
      if ( *v10 == v7 )
      {
        *v10 = (char *)v9;
        *(_QWORD *)(v9 + 8) = v10;
        v11 = *(_DWORD *)(v6 + 208);
        *(_DWORD *)(v6 + 208) = v11 - 1;
        KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 184), v8);
        if ( v11 == 1 )
        {
          v12 = _InterlockedDecrement64((volatile signed __int64 *)v6);
          if ( v12 == -1 )
          {
            __int2c();
          }
          else if ( !v12 )
          {
            if ( KeGetCurrentIrql() )
            {
              v22 = *(_DWORD *)(v6 + 8) == 5;
              *(_QWORD *)(v6 + 48) = Srv2FreeConnection;
              *(_DWORD *)(v6 + 72) = 0;
              if ( v22 )
              {
                LOBYTE(v25) = 1;
                SRV2_PERF_ENTER_EX(v6 + 584, v25, 391, "Srv2PostToThreadPool", 1);
              }
              v23 = *(_QWORD *)(*(_QWORD *)(v6 + 64) + 136LL);
              v24 = *(_QWORD *)(v23 + 8LL * KeGetCurrentNodeNumber() + 8);
              if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v24, (PSLIST_ENTRY)(v6 + 32)) && *(_WORD *)(v24 + 66) )
                RfspThreadPoolNodeWakeIdleWorker(v24);
            }
            else
            {
              Srv2FreeConnection((char *)v6, v25, v26);
            }
          }
        }
        Entry[12] = 0;
        Entry[8] = 0;
LABEL_22:
        *(_QWORD *)(Entry[15] + 8) = 0;
        v13 = (struct _LOOKASIDE_LIST_EX *)((char *)qword_140058148
                                          + 128 * (unsigned __int64)*((unsigned __int16 *)Entry + 198));
        if ( !LOBYTE(v13[3].L.Depth) )
          PplpLazyInitializeLookasideList(qword_140058148, &v13[2]);
        ExFreeToLookasideListEx(v13 + 2, Entry);
        return;
      }
    }
LABEL_52:
    __fastfail(3u);
  }
}

```

## disassembly

```asm
0x140006580  push    rbx
0x140006582  sub     rsp, 40h
0x140006586  test    cs:Microsoft_Windows_SMBServerEnableBits, 2
0x14000658d  mov     rbx, rcx
0x140006590  jnz     loc_1400068E4
0x140006596  mov     rax, [rbx+210h]
0x14000659d  test    rax, rax
0x1400065a0  jz      short loc_1400065B5
0x1400065a2  mov     rcx, rbx
0x1400065a5  call    _guard_dispatch_icall
0x1400065aa  cmp     eax, 103h
0x1400065af  jz      loc_1400067D1
0x1400065b5  mov     eax, gs:1A4h
0x1400065bd  mov     edx, [rbx+190h]
0x1400065c3  mov     [rsp+48h+arg_0], rbp
0x1400065c8  mov     [rsp+48h+arg_8], rsi
0x1400065cd  mov     [rsp+48h+arg_10], rdi
0x1400065d2  mov     ecx, eax
0x1400065d4  mov     rax, cs:Srv2HotGlobals
0x1400065db  mov     [rsp+48h+var_10], r14
0x1400065e0  mov     [rsp+48h+var_18], r15
0x1400065e5  shl     rcx, 7
0x1400065e9  lock add [rcx+rax+20h], rdx
0x1400065ef  mov     rcx, [rbx+1A0h]
0x1400065f6  xor     r15d, r15d
0x1400065f9  mov     [rbx+0C8h], r15
0x140006600  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140006607  mov     [rbx+0D0h], r15
0x14000660e  mov     [rbx+0D8h], r15
0x140006615  mov     [rbx+0E8h], r15
0x14000661c  mov     [rbx+0F0h], r15
0x140006623  mov     [rbx+0F8h], r15
0x14000662a  mov     [rbx+100h], rsi
0x140006631  test    rcx, rcx
0x140006634  jnz     loc_14000682F
0x14000663a  mov     eax, [rbx+1E4h]
0x140006640  test    al, 1
0x140006642  jnz     loc_14000680A
0x140006648  mov     eax, [rbx+1E4h]
0x14000664e  test    al, 2
0x140006650  jz      short loc_140006665
0x140006652  mov     rcx, [rbx+130h]
0x140006659  call    cs:__imp_SrvNetFreeBuffer
0x140006660  nop     dword ptr [rax+rax+00h]
0x140006665  mov     rdi, [rbx+128h]
0x14000666c  test    rdi, rdi
0x14000666f  jnz     loc_1400067D8
0x140006675  mov     rcx, [rbx+350h]
0x14000667c  test    byte ptr [rcx+0Ah], 20h
0x140006680  jnz     loc_1400069B9
0x140006686  mov     rax, [rbx+350h]
0x14000668d  mov     [rax], r15
0x140006690  mov     [rbx+316h], r15w
0x140006698  test    byte ptr [rbx+14Ah], 20h
0x14000669f  jnz     loc_1400069D1
0x1400066a5  and     dword ptr [rbx+1E4h], 0FFFFFFBCh
0x1400066ac  lea     rax, [rbx+300h]
0x1400066b3  mov     [rbx+138h], rax
0x1400066ba  mov     [rbx+130h], rax
0x1400066c1  mov     [rbx+140h], r15
0x1400066c8  mov     dword ptr [rbx+0Ch], 0DCh
0x1400066cf  mov     [rbx+2D0h], r15
0x1400066d6  cmp     [rbx+258h], r15b
0x1400066dd  jnz     loc_1400068EE
0x1400066e3  mov     rbp, [rbx+60h]
0x1400066e7  test    rbp, rbp
0x1400066ea  jz      loc_140006776
0x1400066f0  lea     rcx, [rbp+0B8h]; SpinLock
0x1400066f7  lea     rdi, [rbx+68h]
0x1400066fb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006702  nop     dword ptr [rax+rax+00h]
0x140006707  mov     r8, [rdi]
0x14000670a  cmp     [r8+8], rdi
0x14000670e  jnz     loc_140006A18
0x140006714  mov     rdx, [rdi+8]
0x140006718  cmp     [rdx], rdi
0x14000671b  jnz     loc_140006A18
0x140006721  mov     [rdx], r8
0x140006724  lea     rcx, [rbp+0B8h]; SpinLock
0x14000672b  mov     [r8+8], rdx
0x14000672f  mov     edi, [rbp+0D0h]
0x140006735  lea     edx, [rdi-1]
0x140006738  mov     [rbp+0D0h], edx
0x14000673e  movzx   edx, al; NewIrql
0x140006741  call    cs:__imp_KeReleaseSpinLock
0x140006748  nop     dword ptr [rax+rax+00h]
0x14000674d  cmp     edi, 1
0x140006750  jnz     short loc_14000676E
0x140006752  lock xadd [rbp+0], rsi
0x140006758  dec     rsi
0x14000675b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000675f  jnb     loc_1400069F0
0x140006765  test    rsi, rsi
0x140006768  jz      loc_1400069F7
0x14000676e  mov     [rbx+60h], r15
0x140006772  mov     [rbx+40h], r15
0x140006776  mov     rax, [rbx+78h]
0x14000677a  mov     [rax+8], r15
0x14000677e  movzx   edi, word ptr [rbx+18Ch]
0x140006785  mov     rcx, cs:qword_140058148
0x14000678c  shl     rdi, 7
0x140006790  add     rdi, rcx
0x140006793  movzx   eax, byte ptr [rdi+130h]
0x14000679a  test    al, al
0x14000679c  jz      loc_14000691D
0x1400067a2  mov     rdx, rbx; Entry
0x1400067a5  lea     rcx, [rdi+0C0h]; Lookaside
0x1400067ac  call    cs:__imp_ExFreeToLookasideListEx
0x1400067b3  nop     dword ptr [rax+rax+00h]
0x1400067b8  mov     r14, [rsp+48h+var_10]
0x1400067bd  mov     rdi, [rsp+48h+arg_10]
0x1400067c2  mov     rsi, [rsp+48h+arg_8]
0x1400067c7  mov     rbp, [rsp+48h+arg_0]
0x1400067cc  mov     r15, [rsp+48h+var_18]
0x1400067d1  add     rsp, 40h
0x1400067d5  pop     rbx
0x1400067d6  retn
0x1400067d8  mov     rcx, [rdi+28h]; Irp
0x1400067dc  test    rcx, rcx
0x1400067df  jz      short loc_1400067ED
0x1400067e1  call    cs:__imp_IoFreeIrp
0x1400067e8  nop     dword ptr [rax+rax+00h]
0x1400067ed  xor     edx, edx; Tag
0x1400067ef  mov     rcx, rdi; P
0x1400067f2  call    cs:__imp_ExFreePoolWithTag
0x1400067f9  nop     dword ptr [rax+rax+00h]
0x1400067fe  mov     [rbx+128h], r15
0x140006805  jmp     loc_140006675
0x14000680a  mov     rcx, [rbx+138h]
0x140006811  cmp     [rbx+130h], rcx
0x140006818  jz      loc_140006648
0x14000681e  call    cs:__imp_SrvNetFreeBuffer
0x140006825  nop     dword ptr [rax+rax+00h]
0x14000682a  jmp     loc_140006648
0x14000682f  cmp     rcx, rbx
0x140006832  jnz     short loc_140006866
0x140006834  mov     rcx, [rbx+1C8h]
0x14000683b  test    rcx, rcx
0x14000683e  jz      short loc_14000685A
0x140006840  call    cs:__imp_SrvNetFreeBuffer
0x140006847  nop     dword ptr [rax+rax+00h]
0x14000684c  mov     [rbx+1C8h], r15
0x140006853  mov     [rbx+1D0h], r15d
0x14000685a  mov     [rbx+1A0h], r15
0x140006861  jmp     loc_14000663A
0x140006866  lea     rdi, [rbx+1B0h]
0x14000686d  mov     rax, [rdi]
0x140006870  test    rax, rax
0x140006873  jz      short loc_1400068CC
0x140006875  cmp     rax, rdi
0x140006878  jz      short loc_1400068CC
0x14000687a  add     rcx, 50h ; 'P'; SpinLock
0x14000687e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006885  nop     dword ptr [rax+rax+00h]
0x14000688a  mov     rdx, [rdi]
0x14000688d  cmp     [rdx+8], rdi
0x140006891  jnz     loc_140006A18
0x140006897  mov     rcx, [rdi+8]
0x14000689b  cmp     [rcx], rdi
0x14000689e  jnz     loc_140006A18
0x1400068a4  mov     [rcx], rdx
0x1400068a7  mov     [rdx+8], rcx
0x1400068ab  movzx   edx, al; NewIrql
0x1400068ae  mov     rcx, [rbx+1A0h]
0x1400068b5  add     rcx, 50h ; 'P'; SpinLock
0x1400068b9  call    cs:__imp_KeReleaseSpinLock
0x1400068c0  nop     dword ptr [rax+rax+00h]
0x1400068c5  mov     [rdi+8], rdi
0x1400068c9  mov     [rdi], rdi
0x1400068cc  mov     rcx, [rbx+1A0h]
0x1400068d3  call    Srv2DereferenceWorkItem
0x1400068d8  mov     [rbx+1A0h], r15
0x1400068df  jmp     loc_14000663A
0x1400068e4  call    Smb2OutputWorkItemResponseEtw
0x1400068e9  jmp     loc_140006596
0x1400068ee  test    cs:Microsoft_Windows_SMBServerEnableBits, 8
0x1400068f5  jz      short loc_140006911
0x1400068f7  lea     r9, [rbx+248h]
0x1400068fe  lea     r8, [rbx+248h]
0x140006905  lea     rdx, SMB2_EVENT_WORKITEM_END
0x14000690c  call    McTemplateK0x_EtwWriteTransfer
0x140006911  mov     [rbx+258h], r15b
0x140006918  jmp     loc_1400066E3
0x14000691d  lea     rdx, [rdi+0C0h]
0x140006924  call    PplpLazyInitializeLookasideList
0x140006929  jmp     loc_1400067A2
0x14000692e  cmp     dword ptr [rbp+8], 5
0x140006932  lea     rax, Srv2FreeConnection
0x140006939  mov     [rbp+30h], rax
0x14000693d  mov     [rbp+48h], r15d
0x140006941  jnz     short loc_140006963
0x140006943  lea     rcx, [rbp+248h]
0x14000694a  mov     [rsp+48h+var_28], 1
0x14000694f  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140006956  mov     r8d, 187h
0x14000695c  mov     dl, 1
0x14000695e  call    SRV2_PERF_ENTER_EX
0x140006963  mov     rax, [rbp+40h]
0x140006967  mov     rdi, [rax+88h]
0x14000696e  call    cs:__imp_KeGetCurrentNodeNumber
0x140006975  nop     dword ptr [rax+rax+00h]
0x14000697a  movzx   eax, ax
0x14000697d  lea     rdx, [rbp+20h]; ListEntry
0x140006981  mov     rdi, [rdi+rax*8+8]
0x140006986  mov     rcx, rdi; ListHead
0x140006989  call    cs:__imp_ExpInterlockedPushEntrySList
0x140006990  nop     dword ptr [rax+rax+00h]
0x140006995  test    rax, rax
0x140006998  jnz     loc_14000676E
0x14000699e  movzx   edx, word ptr [rdi+42h]
0x1400069a2  cmp     r15w, dx
0x1400069a6  jz      loc_14000676E
0x1400069ac  mov     rcx, rdi
0x1400069af  call    RfspThreadPoolNodeWakeIdleWorker
0x1400069b4  jmp     loc_14000676E
0x1400069b9  mov     rdx, rcx; MemoryDescriptorList
0x1400069bc  mov     rcx, [rcx+18h]; BaseAddress
0x1400069c0  call    cs:__imp_MmUnmapLockedPages
0x1400069c7  nop     dword ptr [rax+rax+00h]
0x1400069cc  jmp     loc_140006686
0x1400069d1  mov     rcx, [rbx+158h]; BaseAddress
0x1400069d8  lea     rdx, [rbx+140h]; MemoryDescriptorList
0x1400069df  call    cs:__imp_MmUnmapLockedPages
0x1400069e6  nop     dword ptr [rax+rax+00h]
0x1400069eb  jmp     loc_1400066A5
0x1400069f0  int     2Ch; Windows NT - assertion failure
0x1400069f2  jmp     loc_14000676E
0x1400069f7  call    cs:__imp_KeGetCurrentIrql
0x1400069fe  nop     dword ptr [rax+rax+00h]
0x140006a03  test    al, al
0x140006a05  jnz     loc_14000692E
0x140006a0b  mov     rcx, rbp; P
0x140006a0e  call    Srv2FreeConnection
0x140006a13  jmp     loc_14000676E
0x140006a18  mov     ecx, 3
0x140006a1d  int     29h; Win8: RtlFailFast(ecx)
```
