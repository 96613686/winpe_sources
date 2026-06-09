# WskTdiConnectCore

- ea: `0x14003ffbc`
- end: `0x140040286`
- name: `WskTdiConnectCore`
- size: `714`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140065f30`
- `0x140066380`

## callees

- `0x140005b60`
- `0x1400309d0`
- `0x140037624`
- `0x14003ffbc`
- `0x140043aa4`
- `0x1400627a0`
- `0x14006294c`
- `0x140072800`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400400a6`
- `ntoskrnl!IoFreeIrp` at `0x1400400e2`
- `ntoskrnl!IoFreeIrp` at `0x1400400a6`
- `ntoskrnl!IoFreeIrp` at `0x1400400e2`
- `ntoskrnl!IoAllocateIrp` at `0x14004004d`
- `ntoskrnl!IoAllocateIrp` at `0x14004004d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004008f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004008f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400400d3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400400d3`
- `ntoskrnl!IofCallDriver` at `0x14004026e`
- `ntoskrnl!IofCallDriver` at `0x14004026e`

## pseudocode

```c
NTSTATUS __fastcall WskTdiConnectCore(__int64 a1)
{
  int v1; // r8d
  __int64 v3; // r14
  int v4; // r8d
  int AO; // eax
  PIRP Irp; // rbp
  __int64 v7; // rdx
  _QWORD *v9; // rdi
  bool v10; // zf
  int *v11; // rax
  size_t v12; // r8
  __int64 v13; // rdx
  void *v14; // rcx
  __int16 v15; // r9
  _WORD *v16; // rdx
  _DWORD *v17; // rdx
  UCHAR v18; // al
  __int64 v19; // rdx
  UCHAR v20; // al
  __int64 v21; // rdx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v23; // rcx
  _WORD v24[2]; // [rsp+20h] [rbp-38h] BYREF
  int v25; // [rsp+24h] [rbp-34h]
  __int64 v26; // [rsp+28h] [rbp-30h]

  v1 = *(_DWORD *)(a1 + 16);
  v3 = *(_QWORD *)(a1 + 200);
  if ( (v1 & 0x400) != 0 )
  {
    AO = WskTdiResolveFamilyAndCreateAO(a1);
    if ( AO < 0 )
    {
LABEL_11:
      v7 = (unsigned int)AO;
      return WskTdiConnectFinish(a1, v7);
    }
  }
  else if ( (v1 & 0x20) != 0 && IN6_IS_ADDR_V4MAPPED((const IN6_ADDR *)(v3 + 8)) )
  {
    *(_DWORD *)(a1 + 16) = v4 | 0x10;
  }
  if ( *(_QWORD *)(a1 + 144) )
    WskTdiCloseCO(a1 + 144);
  AO = WskTdiCreateCO(
         *(_QWORD *)(((*(_DWORD *)(a1 + 16) & 0x10) != 0 ? 0x48 : 0) + a1 + 32),
         *(_QWORD *)(((*(_DWORD *)(a1 + 16) & 0x10) != 0 ? 0x18 : 0) + a1 + 56),
         a1,
         a1 + 144);
  if ( AO < 0 )
    goto LABEL_11;
  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(a1 + 160) + 76LL), 0);
  if ( !Irp )
  {
LABEL_9:
    WskTdiCloseCO(a1 + 144);
    v7 = 3221225626LL;
    return WskTdiConnectFinish(a1, v7);
  }
  v9 = ExAllocateFromNPagedLookasideList(&stru_1400877C0);
  if ( !v9 )
  {
    IoFreeIrp(Irp);
    goto LABEL_9;
  }
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(a1 + 280) + 96LL), (signed __int64)Irp, 0) == 1 )
  {
    ExFreeToNPagedLookasideList(&stru_1400877C0, v9);
    IoFreeIrp(Irp);
    WskTdiCloseCO(a1 + 144);
    v7 = 3221225760LL;
    return WskTdiConnectFinish(a1, v7);
  }
  *v9 = a1;
  *((_DWORD *)v9 + 2) = 0;
  v9[6] = v9 + 7;
  v9[2] = 0;
  *((_DWORD *)v9 + 6) = 0;
  v9[4] = 0;
  if ( (*(_DWORD *)(a1 + 16) & 0x10) != 0 )
  {
    v10 = *(_WORD *)v3 == 23;
    v24[1] = *(_WORD *)(v3 + 2);
    v11 = (int *)(v3 + 20);
    v26 = 0;
    v24[0] = 2;
    if ( !v10 )
      v11 = (int *)(v3 + 16);
    v25 = *v11;
    *((_DWORD *)v9 + 10) = sockaddr_size[2] + 6;
    *((_DWORD *)v9 + 14) = 1;
    v12 = SOCKADDR_SIZE(2u);
    v14 = (void *)(v13 + 6);
    *(_WORD *)(v13 + 4) = v12 - v15;
    v16 = v24;
  }
  else
  {
    *((_DWORD *)v9 + 10) = SOCKADDR_SIZE(**(_WORD **)(a1 + 200)) + 6;
    *v17 = 1;
    v18 = SOCKADDR_SIZE(*(_WORD *)v3);
    *(_WORD *)(v19 + 4) = v18 - 2;
    v20 = SOCKADDR_SIZE(*(_WORD *)v3);
    v14 = (void *)(v21 + 6);
    v12 = v20;
    v16 = (_WORD *)v3;
  }
  memmove(v14, v16, v12);
  Irp->RequestorMode = 0;
  Irp->Tail.Overlay.Thread = KeGetCurrentThread();
  Irp->Tail.Overlay.OriginalFileObject = *(PFILE_OBJECT *)(a1 + 152);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskTdiCOMPConnect;
  CurrentStackLocation[-1].Context = v9;
  CurrentStackLocation[-1].Control = -32;
  v23 = Irp->Tail.Overlay.CurrentStackLocation;
  *(_WORD *)&v23[-1].MajorFunction = 783;
  v23[-1].DeviceObject = *(PDEVICE_OBJECT *)(a1 + 160);
  v23[-1].FileObject = *(PFILE_OBJECT *)(a1 + 152);
  v23[-1].Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)&AfdInfiniteTimeout;
  v23[-1].Parameters.QueryDirectory.FileName = (PUNICODE_STRING)(v9 + 1);
  v23[-1].Parameters.Read.ByteOffset.QuadPart = 0;
  return IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 160), Irp);
}

```

## disassembly

```asm
0x14003ffbc  push    rbx
0x14003ffbe  push    rbp
0x14003ffbf  push    rsi
0x14003ffc0  push    rdi
0x14003ffc1  push    r14
0x14003ffc3  sub     rsp, 30h
0x14003ffc7  mov     r8d, [rcx+10h]
0x14003ffcb  mov     rbx, rcx
0x14003ffce  mov     r14, [rcx+0C8h]
0x14003ffd5  bt      r8d, 0Ah
0x14003ffda  jb      loc_140040070
0x14003ffe0  test    r8b, 20h
0x14003ffe4  jz      short loc_14003FFFB
0x14003ffe6  lea     rcx, [r14+8]; a
0x14003ffea  call    IN6_IS_ADDR_V4MAPPED
0x14003ffef  test    al, al
0x14003fff1  jz      short loc_14003FFFB
0x14003fff3  or      r8d, 10h
0x14003fff7  mov     [rbx+10h], r8d
0x14003fffb  lea     rsi, [rbx+90h]
0x140040002  cmp     qword ptr [rsi], 0
0x140040006  jz      short loc_140040010
0x140040008  mov     rcx, rsi
0x14004000b  call    WskTdiCloseCO
0x140040010  mov     ecx, [rbx+10h]
0x140040013  mov     r9, rsi
0x140040016  and     ecx, 10h
0x140040019  mov     r8, rbx
0x14004001c  mov     eax, ecx
0x14004001e  neg     eax
0x140040020  sbb     rdx, rdx
0x140040023  and     edx, 18h
0x140040026  neg     ecx
0x140040028  sbb     rcx, rcx
0x14004002b  mov     rdx, [rdx+rbx+38h]
0x140040030  and     ecx, 48h
0x140040033  mov     rcx, [rcx+rbx+20h]
0x140040038  call    WskTdiCreateCO
0x14004003d  test    eax, eax
0x14004003f  js      short loc_140040079
0x140040041  mov     rcx, [rbx+0A0h]
0x140040048  xor     edx, edx; ChargeQuota
0x14004004a  mov     cl, [rcx+4Ch]; StackSize
0x14004004d  call    cs:__imp_IoAllocateIrp
0x140040054  nop     dword ptr [rax+rax+00h]
0x140040059  mov     rbp, rax
0x14004005c  test    rax, rax
0x14004005f  jnz     short loc_140040088
0x140040061  mov     rcx, rsi
0x140040064  call    WskTdiCloseCO
0x140040069  mov     edx, 0C000009Ah
0x14004006e  jmp     short loc_14004007B
0x140040070  call    WskTdiResolveFamilyAndCreateAO
0x140040075  test    eax, eax
0x140040077  jns     short loc_14003FFFB
0x140040079  mov     edx, eax
0x14004007b  mov     rcx, rbx
0x14004007e  call    WskTdiConnectFinish
0x140040083  jmp     loc_14004027A
0x140040088  lea     rcx, stru_1400877C0; Lookaside
0x14004008f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140040096  nop     dword ptr [rax+rax+00h]
0x14004009b  mov     rdi, rax
0x14004009e  test    rax, rax
0x1400400a1  jnz     short loc_1400400B4
0x1400400a3  mov     rcx, rbp; Irp
0x1400400a6  call    cs:__imp_IoFreeIrp
0x1400400ad  nop     dword ptr [rax+rax+00h]
0x1400400b2  jmp     short loc_140040061
0x1400400b4  mov     rdx, [rbx+118h]
0x1400400bb  xor     eax, eax
0x1400400bd  lock cmpxchg [rdx+60h], rbp
0x1400400c3  cmp     rax, 1
0x1400400c7  jnz     short loc_140040100
0x1400400c9  mov     rdx, rdi; Entry
0x1400400cc  lea     rcx, stru_1400877C0; Lookaside
0x1400400d3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400400da  nop     dword ptr [rax+rax+00h]
0x1400400df  mov     rcx, rbp; Irp
0x1400400e2  call    cs:__imp_IoFreeIrp
0x1400400e9  nop     dword ptr [rax+rax+00h]
0x1400400ee  mov     rcx, rsi
0x1400400f1  call    WskTdiCloseCO
0x1400400f6  mov     edx, 0C0000120h
0x1400400fb  jmp     loc_14004007B
0x140040100  lea     rsi, [rdi+8]
0x140040104  mov     [rdi], rbx
0x140040107  lea     rdx, [rdi+38h]
0x14004010b  mov     dword ptr [rsi], 0
0x140040111  mov     [rdi+30h], rdx
0x140040115  mov     qword ptr [rdi+10h], 0
0x14004011d  mov     dword ptr [rdi+18h], 0
0x140040124  mov     qword ptr [rdi+20h], 0
0x14004012c  mov     eax, [rbx+10h]
0x14004012f  test    al, 10h
0x140040131  jz      short loc_14004019D
0x140040133  cmp     word ptr [r14], 17h
0x140040138  mov     r9d, 2
0x14004013e  movzx   eax, word ptr [r14+2]
0x140040143  mov     [rsp+58h+var_36], ax
0x140040148  lea     rax, [r14+14h]
0x14004014c  mov     [rsp+58h+var_30], 0
0x140040155  mov     [rsp+58h+var_38], r9w
0x14004015b  jz      short loc_140040161
0x14004015d  lea     rax, [r14+10h]
0x140040161  mov     eax, [rax]
0x140040163  mov     ecx, r9d; af
0x140040166  mov     [rsp+58h+var_34], eax
0x14004016a  movzx   eax, cs:sockaddr_size+2
0x140040171  add     eax, 6
0x140040174  mov     [rdi+28h], eax
0x140040177  mov     dword ptr [rdx], 1
0x14004017d  call    SOCKADDR_SIZE
0x140040182  movzx   r8d, al
0x140040186  lea     rcx, [rdx+6]
0x14004018a  movzx   eax, r8w
0x14004018e  sub     ax, r9w
0x140040192  mov     [rdx+4], ax
0x140040196  lea     rdx, [rsp+58h+var_38]
0x14004019b  jmp     short loc_1400401E9
0x14004019d  mov     rcx, [rbx+0C8h]
0x1400401a4  movzx   ecx, word ptr [rcx]; af
0x1400401a7  call    SOCKADDR_SIZE
0x1400401ac  movzx   r8d, al
0x1400401b0  add     r8d, 6
0x1400401b4  mov     [rdi+28h], r8d
0x1400401b8  mov     dword ptr [rdx], 1
0x1400401be  movzx   ecx, word ptr [r14]; af
0x1400401c2  call    SOCKADDR_SIZE
0x1400401c7  movzx   r8d, al
0x1400401cb  sub     r8w, 2
0x1400401d0  mov     [rdx+4], r8w
0x1400401d5  movzx   ecx, word ptr [r14]; af
0x1400401d9  call    SOCKADDR_SIZE
0x1400401de  lea     rcx, [rdx+6]; void *
0x1400401e2  movzx   r8d, al; Size
0x1400401e6  mov     rdx, r14; Src
0x1400401e9  call    memmove
0x1400401ee  mov     byte ptr [rbp+40h], 0
0x1400401f2  lea     rcx, WskTdiCOMPConnect
0x1400401f9  mov     rax, gs:188h
0x140040202  mov     rdx, rbp; Irp
0x140040205  mov     [rbp+98h], rax
0x14004020c  mov     rax, [rbx+98h]
0x140040213  mov     [rbp+0C0h], rax
0x14004021a  mov     rax, [rbp+0B8h]
0x140040221  mov     [rax-10h], rcx
0x140040225  mov     [rax-8], rdi
0x140040229  mov     byte ptr [rax-45h], 0E0h
0x14004022d  mov     rcx, [rbp+0B8h]
0x140040234  mov     word ptr [rcx-48h], 30Fh
0x14004023a  mov     rax, [rbx+0A0h]
0x140040241  mov     [rcx-20h], rax
0x140040245  mov     rax, [rbx+98h]
0x14004024c  mov     [rcx-18h], rax
0x140040250  lea     rax, AfdInfiniteTimeout
0x140040257  mov     [rcx-28h], rax
0x14004025b  mov     [rcx-38h], rsi
0x14004025f  mov     qword ptr [rcx-30h], 0
0x140040267  mov     rcx, [rbx+0A0h]; DeviceObject
0x14004026e  call    cs:__imp_IofCallDriver
0x140040275  nop     dword ptr [rax+rax+00h]
0x14004027a  add     rsp, 30h
0x14004027e  pop     r14
0x140040280  pop     rdi
0x140040281  pop     rsi
0x140040282  pop     rbp
0x140040283  pop     rbx
0x140040284  retn
```
