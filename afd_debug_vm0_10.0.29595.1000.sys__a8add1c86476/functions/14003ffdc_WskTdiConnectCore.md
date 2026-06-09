# WskTdiConnectCore

- ea: `0x14003ffdc`
- end: `0x1400402a6`
- name: `WskTdiConnectCore`
- size: `714`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400660d0`
- `0x140066520`

## callees

- `0x140005b60`
- `0x1400309f0`
- `0x140037644`
- `0x14003ffdc`
- `0x140043ac4`
- `0x140062940`
- `0x140062aec`
- `0x140072980`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400400c6`
- `ntoskrnl!IoFreeIrp` at `0x140040102`
- `ntoskrnl!IoFreeIrp` at `0x1400400c6`
- `ntoskrnl!IoFreeIrp` at `0x140040102`
- `ntoskrnl!IoAllocateIrp` at `0x14004006d`
- `ntoskrnl!IoAllocateIrp` at `0x14004006d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400400af`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400400af`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400400f3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400400f3`
- `ntoskrnl!IofCallDriver` at `0x14004028e`
- `ntoskrnl!IofCallDriver` at `0x14004028e`

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
0x14003ffdc  push    rbx
0x14003ffde  push    rbp
0x14003ffdf  push    rsi
0x14003ffe0  push    rdi
0x14003ffe1  push    r14
0x14003ffe3  sub     rsp, 30h
0x14003ffe7  mov     r8d, [rcx+10h]
0x14003ffeb  mov     rbx, rcx
0x14003ffee  mov     r14, [rcx+0C8h]
0x14003fff5  bt      r8d, 0Ah
0x14003fffa  jb      loc_140040090
0x140040000  test    r8b, 20h
0x140040004  jz      short loc_14004001B
0x140040006  lea     rcx, [r14+8]; a
0x14004000a  call    IN6_IS_ADDR_V4MAPPED
0x14004000f  test    al, al
0x140040011  jz      short loc_14004001B
0x140040013  or      r8d, 10h
0x140040017  mov     [rbx+10h], r8d
0x14004001b  lea     rsi, [rbx+90h]
0x140040022  cmp     qword ptr [rsi], 0
0x140040026  jz      short loc_140040030
0x140040028  mov     rcx, rsi
0x14004002b  call    WskTdiCloseCO
0x140040030  mov     ecx, [rbx+10h]
0x140040033  mov     r9, rsi
0x140040036  and     ecx, 10h
0x140040039  mov     r8, rbx
0x14004003c  mov     eax, ecx
0x14004003e  neg     eax
0x140040040  sbb     rdx, rdx
0x140040043  and     edx, 18h
0x140040046  neg     ecx
0x140040048  sbb     rcx, rcx
0x14004004b  mov     rdx, [rdx+rbx+38h]
0x140040050  and     ecx, 48h
0x140040053  mov     rcx, [rcx+rbx+20h]
0x140040058  call    WskTdiCreateCO
0x14004005d  test    eax, eax
0x14004005f  js      short loc_140040099
0x140040061  mov     rcx, [rbx+0A0h]
0x140040068  xor     edx, edx; ChargeQuota
0x14004006a  mov     cl, [rcx+4Ch]; StackSize
0x14004006d  call    cs:__imp_IoAllocateIrp
0x140040074  nop     dword ptr [rax+rax+00h]
0x140040079  mov     rbp, rax
0x14004007c  test    rax, rax
0x14004007f  jnz     short loc_1400400A8
0x140040081  mov     rcx, rsi
0x140040084  call    WskTdiCloseCO
0x140040089  mov     edx, 0C000009Ah
0x14004008e  jmp     short loc_14004009B
0x140040090  call    WskTdiResolveFamilyAndCreateAO
0x140040095  test    eax, eax
0x140040097  jns     short loc_14004001B
0x140040099  mov     edx, eax
0x14004009b  mov     rcx, rbx
0x14004009e  call    WskTdiConnectFinish
0x1400400a3  jmp     loc_14004029A
0x1400400a8  lea     rcx, stru_1400877C0; Lookaside
0x1400400af  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400400b6  nop     dword ptr [rax+rax+00h]
0x1400400bb  mov     rdi, rax
0x1400400be  test    rax, rax
0x1400400c1  jnz     short loc_1400400D4
0x1400400c3  mov     rcx, rbp; Irp
0x1400400c6  call    cs:__imp_IoFreeIrp
0x1400400cd  nop     dword ptr [rax+rax+00h]
0x1400400d2  jmp     short loc_140040081
0x1400400d4  mov     rdx, [rbx+118h]
0x1400400db  xor     eax, eax
0x1400400dd  lock cmpxchg [rdx+60h], rbp
0x1400400e3  cmp     rax, 1
0x1400400e7  jnz     short loc_140040120
0x1400400e9  mov     rdx, rdi; Entry
0x1400400ec  lea     rcx, stru_1400877C0; Lookaside
0x1400400f3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400400fa  nop     dword ptr [rax+rax+00h]
0x1400400ff  mov     rcx, rbp; Irp
0x140040102  call    cs:__imp_IoFreeIrp
0x140040109  nop     dword ptr [rax+rax+00h]
0x14004010e  mov     rcx, rsi
0x140040111  call    WskTdiCloseCO
0x140040116  mov     edx, 0C0000120h
0x14004011b  jmp     loc_14004009B
0x140040120  lea     rsi, [rdi+8]
0x140040124  mov     [rdi], rbx
0x140040127  lea     rdx, [rdi+38h]
0x14004012b  mov     dword ptr [rsi], 0
0x140040131  mov     [rdi+30h], rdx
0x140040135  mov     qword ptr [rdi+10h], 0
0x14004013d  mov     dword ptr [rdi+18h], 0
0x140040144  mov     qword ptr [rdi+20h], 0
0x14004014c  mov     eax, [rbx+10h]
0x14004014f  test    al, 10h
0x140040151  jz      short loc_1400401BD
0x140040153  cmp     word ptr [r14], 17h
0x140040158  mov     r9d, 2
0x14004015e  movzx   eax, word ptr [r14+2]
0x140040163  mov     [rsp+58h+var_36], ax
0x140040168  lea     rax, [r14+14h]
0x14004016c  mov     [rsp+58h+var_30], 0
0x140040175  mov     [rsp+58h+var_38], r9w
0x14004017b  jz      short loc_140040181
0x14004017d  lea     rax, [r14+10h]
0x140040181  mov     eax, [rax]
0x140040183  mov     ecx, r9d; af
0x140040186  mov     [rsp+58h+var_34], eax
0x14004018a  movzx   eax, cs:sockaddr_size+2
0x140040191  add     eax, 6
0x140040194  mov     [rdi+28h], eax
0x140040197  mov     dword ptr [rdx], 1
0x14004019d  call    SOCKADDR_SIZE
0x1400401a2  movzx   r8d, al
0x1400401a6  lea     rcx, [rdx+6]
0x1400401aa  movzx   eax, r8w
0x1400401ae  sub     ax, r9w
0x1400401b2  mov     [rdx+4], ax
0x1400401b6  lea     rdx, [rsp+58h+var_38]
0x1400401bb  jmp     short loc_140040209
0x1400401bd  mov     rcx, [rbx+0C8h]
0x1400401c4  movzx   ecx, word ptr [rcx]; af
0x1400401c7  call    SOCKADDR_SIZE
0x1400401cc  movzx   r8d, al
0x1400401d0  add     r8d, 6
0x1400401d4  mov     [rdi+28h], r8d
0x1400401d8  mov     dword ptr [rdx], 1
0x1400401de  movzx   ecx, word ptr [r14]; af
0x1400401e2  call    SOCKADDR_SIZE
0x1400401e7  movzx   r8d, al
0x1400401eb  sub     r8w, 2
0x1400401f0  mov     [rdx+4], r8w
0x1400401f5  movzx   ecx, word ptr [r14]; af
0x1400401f9  call    SOCKADDR_SIZE
0x1400401fe  lea     rcx, [rdx+6]; void *
0x140040202  movzx   r8d, al; Size
0x140040206  mov     rdx, r14; Src
0x140040209  call    memmove
0x14004020e  mov     byte ptr [rbp+40h], 0
0x140040212  lea     rcx, WskTdiCOMPConnect
0x140040219  mov     rax, gs:188h
0x140040222  mov     rdx, rbp; Irp
0x140040225  mov     [rbp+98h], rax
0x14004022c  mov     rax, [rbx+98h]
0x140040233  mov     [rbp+0C0h], rax
0x14004023a  mov     rax, [rbp+0B8h]
0x140040241  mov     [rax-10h], rcx
0x140040245  mov     [rax-8], rdi
0x140040249  mov     byte ptr [rax-45h], 0E0h
0x14004024d  mov     rcx, [rbp+0B8h]
0x140040254  mov     word ptr [rcx-48h], 30Fh
0x14004025a  mov     rax, [rbx+0A0h]
0x140040261  mov     [rcx-20h], rax
0x140040265  mov     rax, [rbx+98h]
0x14004026c  mov     [rcx-18h], rax
0x140040270  lea     rax, AfdInfiniteTimeout
0x140040277  mov     [rcx-28h], rax
0x14004027b  mov     [rcx-38h], rsi
0x14004027f  mov     qword ptr [rcx-30h], 0
0x140040287  mov     rcx, [rbx+0A0h]; DeviceObject
0x14004028e  call    cs:__imp_IofCallDriver
0x140040295  nop     dword ptr [rax+rax+00h]
0x14004029a  add     rsp, 30h
0x14004029e  pop     r14
0x1400402a0  pop     rdi
0x1400402a1  pop     rsi
0x1400402a2  pop     rbp
0x1400402a3  pop     rbx
0x1400402a4  retn
```
