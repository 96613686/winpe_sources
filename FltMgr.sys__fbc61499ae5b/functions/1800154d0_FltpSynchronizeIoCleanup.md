# FltpSynchronizeIoCleanup

- ea: `0x1800154d0`
- end: `0x180015838`
- name: `FltpSynchronizeIoCleanup`
- size: `872`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007500`

## callees

- `0x1800154d0`
- `0x18001bc90`
- `0x18001ca30`
- `0x1800248e0`
- `0x180024c40`
- `0x180061e00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800155ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x180015740`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800157fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800155ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x180015740`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800157fb`
- `ntoskrnl!ExQueryDepthSList` at `0x1800155c8`
- `ntoskrnl!ExQueryDepthSList` at `0x1800155c8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1800156b1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1800156b1`
- `ntoskrnl!ObfDereferenceObject` at `0x180015690`
- `ntoskrnl!ObfDereferenceObject` at `0x180015690`
- `ntoskrnl!IofCompleteRequest` at `0x180015618`
- `ntoskrnl!IofCompleteRequest` at `0x180015618`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18001565d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18001565d`
- `ntoskrnl!RtlWalkFrameChain` at `0x1800157c3`
- `ntoskrnl!RtlWalkFrameChain` at `0x1800157c3`

## pseudocode

```c
__int64 __fastcall FltpSynchronizeIoCleanup(ULONG_PTR BugCheckParameter3)
{
  IRP *v1; // rsi
  _DWORD *v3; // rcx
  unsigned int Status; // r14d
  __int64 v5; // r8
  __int64 v6; // rdi
  __int64 v7; // r15
  __int64 v8; // r12
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r15
  USHORT v15; // di
  NTSTATUS v16; // ecx
  void (__fastcall *v18)(_DWORD *, _QWORD); // rax
  __int64 v19; // rsi
  void *v20; // rdi
  int v21; // eax
  _DWORD *v22; // rcx
  void *v23; // rcx
  volatile signed __int32 *v24; // rcx
  unsigned __int64 v25; // rbx

  v1 = *(IRP **)(BugCheckParameter3 + 48);
  v3 = (_DWORD *)(BugCheckParameter3 + 232);
  Status = v1->IoStatus.Status;
  if ( (*v3 & 0x10000) == 0 )
  {
    v5 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 104) + 64LL);
    v6 = *(_QWORD *)(v5 + 16);
    v7 = *(_DWORD *)(BugCheckParameter3 + 8) % (unsigned int)dword_18003ECE0;
    v8 = *(_QWORD *)(v6 + 680);
    if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(BugCheckParameter3 + 12) + 22)) & 2) != 0 )
    {
      v22 = *(_DWORD **)(BugCheckParameter3 + 160);
      if ( v22 )
      {
        FltpFreeNameCacheCreateCtrl(v22, *(_QWORD *)(v5 + 80));
        *(_QWORD *)(BugCheckParameter3 + 160) = 0;
      }
      v23 = *(void **)(BugCheckParameter3 + 184);
      if ( v23 )
        ExFreePoolWithTag(v23, 0x6E744D46u);
    }
    if ( (*(_DWORD *)(BugCheckParameter3 + 4) & 0x2000000) != 0 )
      ExFreePoolWithTag(*(PVOID *)(BugCheckParameter3 + 16), 0x6C694D46u);
    v9 = *(_DWORD *)(BugCheckParameter3 + 4);
    if ( (v9 & 0x4000000) != 0 )
    {
      FltpFreeBackPocketIrpCtrl(BugCheckParameter3);
    }
    else if ( (v9 & 0x88FF0000) != 0 )
    {
      FltpFreeStaticIrpCtrl(BugCheckParameter3, v6);
    }
    else
    {
      if ( (v9 & 0x10000000) != 0 )
      {
        v10 = *(unsigned __int8 *)(v6 + 65);
        v11 = *(unsigned __int16 *)(BugCheckParameter3 + 2);
        if ( (*(_DWORD *)(v6 + 972) & 1) == 0
          || v11 == ((unsigned __int64)*(unsigned __int8 *)(v6 + 64) << 7) + 400
          || v11 == (v10 << 7) + 400 )
        {
          *(_QWORD *)(BugCheckParameter3 + 264) = *(unsigned __int16 *)(BugCheckParameter3 + 2);
          v12 = v11;
          v13 = 0;
          if ( v12 != (v10 << 7) + 400 )
            v13 = 16;
          v14 = *(_QWORD *)((v7 << 6) + v8 + v13);
          _InterlockedIncrement((volatile signed __int32 *)(v14 + 28));
          v15 = *(_WORD *)(v14 + 16);
          if ( ExQueryDepthSList((PSLIST_HEADER)v14) < v15 )
          {
            v21 = *(_DWORD *)(BugCheckParameter3 + 4);
            if ( (v21 & 0x20000000) != 0 )
              *(_DWORD *)(BugCheckParameter3 + 4) = v21 & 0xDFFFFFFF;
            ExpInterlockedPushEntrySList((PSLIST_HEADER)v14, (PSLIST_ENTRY)BugCheckParameter3);
            goto LABEL_14;
          }
          _InterlockedIncrement((volatile signed __int32 *)(v14 + 32));
        }
      }
      ExFreePoolWithTag((PVOID)BugCheckParameter3, 0x63694D46u);
    }
LABEL_14:
    v16 = v1->IoStatus.Status;
    if ( (v16 & 0xC0000000) == 0xC0000000 && (v1->Flags & 0x40) != 0 )
      v1->IoStatus.Information = 0;
    v1->IoStatus.Status = v16;
    IofCompleteRequest(v1, 0);
    return Status;
  }
  v18 = *(void (__fastcall **)(_DWORD *, _QWORD))(BugCheckParameter3 + 56);
  if ( v18 )
  {
    v19 = *(_QWORD *)(BugCheckParameter3 + 72);
    v20 = *(void **)(BugCheckParameter3 + 240);
    v18(v3, *(_QWORD *)(BugCheckParameter3 + 64));
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v19 + 8));
    if ( (FltGlobals[0] & 0x2000) != 0 && (*(_DWORD *)v19 & 0x2000000) != 0
      || (FltGlobals[0] & 0x4000) != 0 && (*(_DWORD *)v19 & 0x4000000) != 0
      || (FltGlobals[0] & 0x8000) != 0 && (*(_DWORD *)v19 & 0x1000000) != 0 )
    {
      v24 = *(volatile signed __int32 **)(v19 + 32);
      if ( v24 )
      {
        v25 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(v24, 1u) + 1) & 0x3FF) << 7;
        *(_DWORD *)(v25 + *(_QWORD *)(v19 + 32) + 8) = -1;
        *(_QWORD *)(v25 + *(_QWORD *)(v19 + 32) + 16) = *(_QWORD *)(v19 + 8);
        memset((void *)(v25 + *(_QWORD *)(v19 + 32) + 24LL), 0, 0x70u);
        RtlWalkFrameChain((PVOID *)(v25 + *(_QWORD *)(v19 + 32) + 24LL), 0xEu, 0);
      }
    }
    ObfDereferenceObject(v20);
  }
  return Status;
}

```

## disassembly

```asm
0x1800154d0  mov     [rsp+arg_8], rbx
0x1800154d5  mov     [rsp+arg_10], rsi
0x1800154da  push    rdi
0x1800154db  push    r14
0x1800154dd  push    r15
0x1800154df  sub     rsp, 20h
0x1800154e3  mov     rsi, [rcx+30h]
0x1800154e7  mov     rbx, rcx
0x1800154ea  add     rcx, 0E8h
0x1800154f1  mov     r14d, [rsi+30h]
0x1800154f5  test    dword ptr [rcx], 10000h
0x1800154fb  jnz     loc_18001563C
0x180015501  mov     rax, [rbx+68h]
0x180015505  xor     edx, edx
0x180015507  mov     [rsp+38h+arg_0], r12
0x18001550c  mov     r8, [rax+40h]
0x180015510  mov     eax, [rbx+8]
0x180015513  div     cs:dword_18003ECE0
0x180015519  movzx   eax, byte ptr [rbx+0Ch]
0x18001551d  mov     rdi, [r8+10h]
0x180015521  add     al, 16h
0x180015523  movzx   ecx, al
0x180015526  lea     rax, FltpOperationFlags
0x18001552d  mov     r15d, edx
0x180015530  mov     r12, [rdi+2A8h]
0x180015537  test    byte ptr [rcx+rax], 2
0x18001553b  jnz     loc_18001570B
0x180015541  test    dword ptr [rbx+4], 2000000h
0x180015548  jnz     loc_1800157F2
0x18001554e  mov     eax, [rbx+4]
0x180015551  bt      eax, 1Ah
0x180015555  jb      loc_18001580C
0x18001555b  test    eax, 88FF0000h
0x180015560  jnz     loc_18001581C
0x180015566  bt      eax, 1Ch
0x18001556a  jnb     short loc_1800155E2
0x18001556c  movzx   r8d, byte ptr [rdi+40h]
0x180015571  movzx   ecx, byte ptr [rdi+41h]
0x180015575  mov     eax, [rdi+3CCh]
0x18001557b  movzx   edx, word ptr [rbx+2]
0x18001557f  test    al, 1
0x180015581  jnz     loc_1800156DA
0x180015587  movzx   eax, word ptr [rbx+2]
0x18001558b  mov     r8d, 10h
0x180015591  mov     [rbx+108h], rax
0x180015598  mov     rax, rdx
0x18001559b  shl     rcx, 7
0x18001559f  xor     edx, edx
0x1800155a1  add     rcx, 190h
0x1800155a8  cmp     rax, rcx
0x1800155ab  cmovnz  edx, r8d
0x1800155af  shl     r15, 6
0x1800155b3  lea     rax, [r12+rdx]
0x1800155b7  mov     r15, [r15+rax]
0x1800155bb  lock inc dword ptr [r15+1Ch]
0x1800155c0  movzx   edi, word ptr [r15+10h]
0x1800155c5  mov     rcx, r15; SListHead
0x1800155c8  call    cs:__imp_ExQueryDepthSList
0x1800155cf  nop     dword ptr [rax+rax+00h]
0x1800155d4  cmp     ax, di
0x1800155d7  jb      loc_18001569E
0x1800155dd  lock inc dword ptr [r15+20h]
0x1800155e2  mov     edx, 63694D46h; Tag
0x1800155e7  mov     rcx, rbx; P
0x1800155ea  call    cs:__imp_ExFreePoolWithTag
0x1800155f1  nop     dword ptr [rax+rax+00h]
0x1800155f6  mov     ecx, [rsi+30h]
0x1800155f9  mov     eax, ecx
0x1800155fb  mov     r12, [rsp+38h+arg_0]
0x180015600  and     eax, 0C0000000h
0x180015605  cmp     eax, 0C0000000h
0x18001560a  jz      loc_1800156C2
0x180015610  mov     [rsi+30h], ecx
0x180015613  xor     edx, edx; PriorityBoost
0x180015615  mov     rcx, rsi; Irp
0x180015618  call    cs:__imp_IofCompleteRequest
0x18001561f  nop     dword ptr [rax+rax+00h]
0x180015624  mov     rbx, [rsp+38h+arg_8]
0x180015629  mov     eax, r14d
0x18001562c  mov     rsi, [rsp+38h+arg_10]
0x180015631  add     rsp, 20h
0x180015635  pop     r15
0x180015637  pop     r14
0x180015639  pop     rdi
0x18001563a  retn
0x18001563c  mov     rax, [rbx+38h]
0x180015640  test    rax, rax
0x180015643  jz      short loc_180015624
0x180015645  mov     rdx, [rbx+40h]
0x180015649  mov     rsi, [rbx+48h]
0x18001564d  mov     rdi, [rbx+0F0h]
0x180015654  call    _guard_dispatch_icall
0x180015659  lea     rcx, [rsi+8]; RunRef
0x18001565d  call    cs:__imp_ExReleaseRundownProtection
0x180015664  nop     dword ptr [rax+rax+00h]
0x180015669  mov     ecx, cs:FltGlobals
0x18001566f  bt      ecx, 0Dh
0x180015673  jb      loc_1800157D4
0x180015679  bt      ecx, 0Eh
0x18001567d  jb      loc_180015751
0x180015683  bt      ecx, 0Fh
0x180015687  jb      loc_1800157E1
0x18001568d  mov     rcx, rdi; Object
0x180015690  call    cs:__imp_ObfDereferenceObject
0x180015697  nop     dword ptr [rax+rax+00h]
0x18001569c  jmp     short loc_180015624
0x18001569e  mov     eax, [rbx+4]
0x1800156a1  bt      eax, 1Dh
0x1800156a5  jb      loc_18001582C
0x1800156ab  mov     rdx, rbx; ListEntry
0x1800156ae  mov     rcx, r15; ListHead
0x1800156b1  call    cs:__imp_ExpInterlockedPushEntrySList
0x1800156b8  nop     dword ptr [rax+rax+00h]
0x1800156bd  jmp     loc_1800155F6
0x1800156c2  mov     eax, [rsi+10h]
0x1800156c5  test    al, 40h
0x1800156c7  jz      loc_180015610
0x1800156cd  mov     qword ptr [rsi+38h], 0
0x1800156d5  jmp     loc_180015610
0x1800156da  mov     rax, r8
0x1800156dd  shl     rax, 7
0x1800156e1  add     rax, 190h
0x1800156e7  cmp     rdx, rax
0x1800156ea  jz      loc_180015587
0x1800156f0  mov     rax, rcx
0x1800156f3  shl     rax, 7
0x1800156f7  add     rax, 190h
0x1800156fd  cmp     rdx, rax
0x180015700  jnz     loc_1800155E2
0x180015706  jmp     loc_180015587
0x18001570b  mov     rcx, [rbx+0A0h]; Entry
0x180015712  test    rcx, rcx
0x180015715  jz      short loc_18001572B
0x180015717  mov     rdx, [r8+50h]
0x18001571b  call    FltpFreeNameCacheCreateCtrl
0x180015720  mov     qword ptr [rbx+0A0h], 0
0x18001572b  mov     rcx, [rbx+0B8h]; P
0x180015732  test    rcx, rcx
0x180015735  jz      loc_180015541
0x18001573b  mov     edx, 6E744D46h; Tag
0x180015740  call    cs:__imp_ExFreePoolWithTag
0x180015747  nop     dword ptr [rax+rax+00h]
0x18001574c  jmp     loc_180015541
0x180015751  test    dword ptr [rsi], 4000000h
0x180015757  jz      loc_180015683
0x18001575d  mov     rcx, [rsi+20h]
0x180015761  test    rcx, rcx
0x180015764  jz      loc_18001568D
0x18001576a  mov     ebx, 1
0x18001576f  lock xadd [rcx], ebx
0x180015773  mov     rax, [rsi+20h]
0x180015777  inc     ebx
0x180015779  and     ebx, 3FFh
0x18001577f  mov     r8d, 70h ; 'p'; Size
0x180015785  shl     rbx, 7
0x180015789  mov     dword ptr [rbx+rax+8], 0FFFFFFFFh
0x180015791  mov     rdx, [rsi+20h]
0x180015795  mov     rax, [rsi+8]
0x180015799  mov     [rbx+rdx+10h], rax
0x18001579e  xor     edx, edx; Val
0x1800157a0  mov     rcx, [rsi+20h]
0x1800157a4  add     rcx, 18h
0x1800157a8  add     rcx, rbx; void *
0x1800157ab  call    memset
0x1800157b0  mov     rcx, [rsi+20h]
0x1800157b4  xor     r8d, r8d; Flags
0x1800157b7  add     rcx, 18h
0x1800157bb  mov     edx, 0Eh; Count
0x1800157c0  add     rcx, rbx; Callers
0x1800157c3  call    cs:__imp_RtlWalkFrameChain
0x1800157ca  nop     dword ptr [rax+rax+00h]
0x1800157cf  jmp     loc_18001568D
0x1800157d4  test    dword ptr [rsi], 2000000h
0x1800157da  jnz     short loc_18001575D
0x1800157dc  jmp     loc_180015679
0x1800157e1  test    dword ptr [rsi], 1000000h
0x1800157e7  jz      loc_18001568D
0x1800157ed  jmp     loc_18001575D
0x1800157f2  mov     rcx, [rbx+10h]; P
0x1800157f6  mov     edx, 6C694D46h; Tag
0x1800157fb  call    cs:__imp_ExFreePoolWithTag
0x180015802  nop     dword ptr [rax+rax+00h]
0x180015807  jmp     loc_18001554E
0x18001580c  mov     rdx, rdi
0x18001580f  mov     rcx, rbx; BugCheckParameter3
0x180015812  call    FltpFreeBackPocketIrpCtrl
0x180015817  jmp     loc_1800155F6
0x18001581c  mov     rdx, rdi
0x18001581f  mov     rcx, rbx
0x180015822  call    FltpFreeStaticIrpCtrl
0x180015827  jmp     loc_1800155F6
0x18001582c  btr     eax, 1Dh
0x180015830  mov     [rbx+4], eax
0x180015833  jmp     loc_1800156AB
```
