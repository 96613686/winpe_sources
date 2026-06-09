# AfdTLBindComplete2

- ea: `0x14001a8a0`
- end: `0x14001aab4`
- name: `AfdTLBindComplete2`
- size: `532`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140019690`
- `0x14001a710`
- `0x14001a7b0`

## callees

- `0x140002440`
- `0x14000dc90`
- `0x14000fcd0`
- `0x14001a8a0`
- `0x1400250a0`
- `0x140039198`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14001a9b6`
- `ntoskrnl!IoFreeMdl` at `0x14001a9b6`
- `ntoskrnl!MmUnlockPages` at `0x14001a9a6`
- `ntoskrnl!MmUnlockPages` at `0x14001a9a6`
- `ntoskrnl!IofCompleteRequest` at `0x14001a9f4`
- `ntoskrnl!IofCompleteRequest` at `0x14001a9f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a983`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a983`

## pseudocode

```c
void __fastcall AfdTLBindComplete2(PIRP Irp, __int64 a2, NTSTATUS a3, char a4)
{
  void *v8; // rdx
  int v9; // eax
  int v10; // eax
  void *v11; // rcx
  PMDL MdlAddress; // rcx
  CCHAR v13; // dl
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rdx
  struct _KPROCESS *v17; // [rsp+30h] [rbp-39h]
  __int64 v18; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v19[14]; // [rsp+50h] [rbp-19h] BYREF

  memset(v19, 0, 0x50u);
  if ( a4 )
    AfdDerefTLBaseEndpoint(a2);
  if ( a3 < 0 )
    goto LABEL_8;
  if ( (*(_BYTE *)(a2 + 5) & 0x10) == 0 || (*(_BYTE *)(a2 + 6) & 1) == 0 )
  {
    *(_BYTE *)(a2 + 2) = 3;
    goto LABEL_22;
  }
  v8 = *(void **)(a2 + 272);
  v17 = *(struct _KPROCESS **)(a2 + 48);
  v9 = (*(_DWORD *)(a2 + 8) >> 7) & 1;
  v18 = 0;
  v10 = AfdCreateConnection(a2, v8, (void *)0xFFFFFFFFFFFFFFFFLL, 0, 1u, v9, v17, &v18);
  if ( v10 >= 0 )
  {
    if ( _InterlockedIncrement64((volatile signed __int64 *)(a2 + 64)) <= 1 )
      __fastfail(0xEu);
    v14 = v18;
    *(_QWORD *)(v18 + 8) = a2;
    *(_QWORD *)(a2 + 192) = v14;
    *(_WORD *)a2 = -20526;
    if ( (int)AfdAddConnectedReference(v14) < 0 )
      goto LABEL_8;
    *(_BYTE *)(a2 + 2) = 4;
    *(_WORD *)(v14 + 2) = 3;
LABEL_22:
    v15 = *(_QWORD *)(a2 + 24);
    v16 = *(_QWORD *)(a2 + 16);
    v19[0] = AfdTLBindGetAddrComplete;
    v19[6] = *(_QWORD *)(a2 + 240);
    v19[7] = *(unsigned int *)(a2 + 236);
    v19[1] = Irp;
    v19[2] = 0xFFFD00000000LL;
    LODWORD(v19[3]) = 16;
    AfdTLIoControl(*(_QWORD *)(v15 + 8), v16, v19, a2);
    return;
  }
  a3 = v10;
LABEL_8:
  AFDETW_TRACEBIND(1, 7025, a2, a3, *(_QWORD *)(a2 + 240));
  v11 = *(void **)(a2 + 240);
  *(_QWORD *)(a2 + 240) = 0;
  *(_DWORD *)(a2 + 236) = 0;
  ExFreePoolWithTag(v11, 0x6C646641u);
  _InterlockedExchange((volatile __int32 *)(a2 + 368), 0);
  MdlAddress = Irp->MdlAddress;
  if ( MdlAddress )
  {
    if ( (MdlAddress->MdlFlags & 2) != 0 )
      MmUnlockPages(MdlAddress);
    IoFreeMdl(Irp->MdlAddress);
    Irp->MdlAddress = 0;
  }
  if ( (a3 == -1073741757 || a3 == -1073741302)
    && LODWORD(Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink) == 1 )
  {
    a3 = -1073741790;
  }
  v13 = AfdPriorityBoost;
  Irp->IoStatus.Status = a3;
  IofCompleteRequest(Irp, v13);
}

```

## disassembly

```asm
0x14001a8a0  push    rbp
0x14001a8a2  push    rbx
0x14001a8a3  push    rsi
0x14001a8a4  push    rdi
0x14001a8a5  push    r14
0x14001a8a7  lea     rbp, [rsp-37h]
0x14001a8ac  sub     rsp, 0A0h
0x14001a8b3  mov     rdi, rdx
0x14001a8b6  mov     esi, r8d
0x14001a8b9  xor     edx, edx; Val
0x14001a8bb  mov     r14, rcx
0x14001a8be  lea     rcx, [rbp+57h+var_70]; void *
0x14001a8c2  mov     bl, r9b
0x14001a8c5  lea     r8d, [rdx+50h]; Size
0x14001a8c9  call    memset
0x14001a8ce  test    bl, bl
0x14001a8d0  jz      short loc_14001A8DA
0x14001a8d2  mov     rcx, rdi
0x14001a8d5  call    AfdDerefTLBaseEndpoint
0x14001a8da  test    esi, esi
0x14001a8dc  js      short loc_14001A941
0x14001a8de  test    byte ptr [rdi+5], 10h
0x14001a8e2  jz      loc_14001AA5A
0x14001a8e8  test    byte ptr [rdi+6], 1
0x14001a8ec  jz      loc_14001AA5A
0x14001a8f2  mov     eax, [rdi+8]
0x14001a8f5  lea     rcx, [rbp+57h+var_80]
0x14001a8f9  mov     rdx, [rdi+110h]
0x14001a900  xor     r9d, r9d
0x14001a903  mov     [rsp+0C0h+var_88], rcx
0x14001a908  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001a90c  mov     rcx, [rdi+30h]
0x14001a910  mov     [rsp+0C0h+var_90], rcx
0x14001a915  mov     rcx, rdi
0x14001a918  shr     eax, 7
0x14001a91b  and     eax, 1
0x14001a91e  mov     [rbp+57h+var_80], 0
0x14001a926  mov     [rsp+0C0h+var_98], eax
0x14001a92a  mov     dword ptr [rsp+0C0h+var_A0], 1
0x14001a932  call    AfdCreateConnection
0x14001a937  test    eax, eax
0x14001a939  jns     loc_14001AA0F
0x14001a93f  mov     esi, eax
0x14001a941  mov     rax, [rdi+0F0h]
0x14001a948  mov     r9d, esi
0x14001a94b  mov     r8, rdi
0x14001a94e  mov     [rsp+0C0h+var_A0], rax
0x14001a953  mov     edx, 1B71h
0x14001a958  mov     ecx, 1
0x14001a95d  call    AFDETW_TRACEBIND
0x14001a962  mov     rcx, [rdi+0F0h]; P
0x14001a969  mov     edx, 6C646641h; Tag
0x14001a96e  mov     qword ptr [rdi+0F0h], 0
0x14001a979  mov     dword ptr [rdi+0ECh], 0
0x14001a983  call    cs:__imp_ExFreePoolWithTag
0x14001a98a  nop     dword ptr [rax+rax+00h]
0x14001a98f  xor     eax, eax
0x14001a991  xchg    eax, [rdi+170h]
0x14001a997  mov     rcx, [r14+8]; MemoryDescriptorList
0x14001a99b  test    rcx, rcx
0x14001a99e  jz      short loc_14001A9CA
0x14001a9a0  test    byte ptr [rcx+0Ah], 2
0x14001a9a4  jz      short loc_14001A9B2
0x14001a9a6  call    cs:__imp_MmUnlockPages
0x14001a9ad  nop     dword ptr [rax+rax+00h]
0x14001a9b2  mov     rcx, [r14+8]; Mdl
0x14001a9b6  call    cs:__imp_IoFreeMdl
0x14001a9bd  nop     dword ptr [rax+rax+00h]
0x14001a9c2  mov     qword ptr [r14+8], 0
0x14001a9ca  cmp     esi, 0C0000043h
0x14001a9d0  jz      short loc_14001A9DA
0x14001a9d2  cmp     esi, 0C000020Ah
0x14001a9d8  jnz     short loc_14001A9E7
0x14001a9da  cmp     dword ptr [r14+78h], 1
0x14001a9df  mov     eax, 0C0000022h
0x14001a9e4  cmovz   esi, eax
0x14001a9e7  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14001a9ed  mov     rcx, r14; Irp
0x14001a9f0  mov     [r14+30h], esi
0x14001a9f4  call    cs:__imp_IofCompleteRequest
0x14001a9fb  nop     dword ptr [rax+rax+00h]
0x14001aa00  add     rsp, 0A0h
0x14001aa07  pop     r14
0x14001aa09  pop     rdi
0x14001aa0a  pop     rsi
0x14001aa0b  pop     rbx
0x14001aa0c  pop     rbp
0x14001aa0d  retn
0x14001aa0f  mov     eax, 1
0x14001aa14  lock xadd [rdi+40h], rax
0x14001aa1a  inc     rax
0x14001aa1d  cmp     rax, 1
0x14001aa21  jg      short loc_14001AA2A
0x14001aa23  mov     ecx, 0Eh
0x14001aa28  int     29h; Win8: RtlFailFast(ecx)
0x14001aa2a  mov     rbx, [rbp+57h+var_80]
0x14001aa2e  mov     [rbx+8], rdi
0x14001aa32  mov     [rdi+0C0h], rbx
0x14001aa39  mov     word ptr [rdi], 0AFD2h
0x14001aa3e  mov     rcx, rbx
0x14001aa41  call    AfdAddConnectedReference
0x14001aa46  test    eax, eax
0x14001aa48  js      loc_14001A941
0x14001aa4e  mov     byte ptr [rdi+2], 4
0x14001aa52  mov     word ptr [rbx+2], 3
0x14001aa58  jmp     short loc_14001AA5E
0x14001aa5a  mov     byte ptr [rdi+2], 3
0x14001aa5e  mov     rcx, [rdi+18h]
0x14001aa62  lea     rax, AfdTLBindGetAddrComplete
0x14001aa69  mov     rdx, [rdi+10h]
0x14001aa6d  lea     r8, [rbp+57h+var_70]
0x14001aa71  mov     [rbp+57h+var_70], rax
0x14001aa75  mov     r9, rdi
0x14001aa78  mov     rax, [rdi+0F0h]
0x14001aa7f  mov     [rbp+57h+var_40], rax
0x14001aa83  mov     eax, [rdi+0ECh]
0x14001aa89  mov     [rbp+57h+var_38], rax
0x14001aa8d  mov     [rbp+57h+var_68], r14
0x14001aa91  mov     [rbp+57h+var_60], 0
0x14001aa98  mov     [rbp+57h+var_5C], 0FFFDh
0x14001aa9f  mov     [rbp+57h+var_58], 10h
0x14001aaa6  mov     rcx, [rcx+8]
0x14001aaaa  call    AfdTLIoControl
0x14001aaaf  jmp     loc_14001AA00
```
