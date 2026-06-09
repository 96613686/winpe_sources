# AfdTLDgramSendToComplete

- ea: `0x14000ff20`
- end: `0x14001034e`
- name: `AfdTLDgramSendToComplete`
- size: `1070`
- prototype: `void __fastcall(unsigned int *P, int, ULONG_PTR Length)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007350`

## callees

- `0x14000f390`
- `0x14000fa00`
- `0x14000ff20`
- `0x140010948`
- `0x1400129d0`
- `0x140013030`
- `0x140025690`
- `0x14002b1b0`
- `0x14002bf60`
- `0x140094900`

## import_xrefs

- `ntoskrnl!PsReturnPoolQuota` at `0x1400101a0`
- `ntoskrnl!PsReturnPoolQuota` at `0x140010218`
- `ntoskrnl!PsReturnPoolQuota` at `0x140010298`
- `ntoskrnl!PsReturnPoolQuota` at `0x14001033d`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400101a0`
- `ntoskrnl!PsReturnPoolQuota` at `0x140010218`
- `ntoskrnl!PsReturnPoolQuota` at `0x140010298`
- `ntoskrnl!PsReturnPoolQuota` at `0x14001033d`
- `ntoskrnl!IofCompleteRequest` at `0x140010064`
- `ntoskrnl!IofCompleteRequest` at `0x140010064`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140010037`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140010037`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400101fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400101fa`
- `TDI!TdiReturnChainedReceives` at `0x14001024a`
- `TDI!TdiReturnChainedReceives` at `0x14001024a`

## pseudocode

```c
void __fastcall AfdTLDgramSendToComplete(unsigned int *P, int a2, ULONG_PTR Length)
{
  IRP *v3; // rdi
  NTSTATUS v6; // esi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  __int64 FsContext; // r14
  SIZE_T v9; // rcx
  struct _KPROCESS *v10; // r13
  _BYTE *v11; // r12
  ULONG_PTR v12; // r8
  unsigned __int64 v13; // rbp
  CCHAR v14; // dl
  __int16 v15; // ax
  __int64 *v16; // rdx
  __int64 v17; // rcx
  unsigned int *v18; // rdx
  unsigned int v19; // eax

  v3 = (IRP *)*((_QWORD *)P + 6);
  v6 = a2;
  CurrentStackLocation = v3->Tail.Overlay.CurrentStackLocation;
  FsContext = (__int64)CurrentStackLocation->FileObject->FsContext;
  if ( a2 != -1073741252 )
  {
    if ( a2 <= -1073741503 )
    {
      if ( a2 == -1073741503 )
        goto LABEL_2;
      if ( a2 > -1073741790 )
      {
        if ( a2 == -1073741670 || a2 == -1073741634 || a2 == -1073741536 )
          goto LABEL_2;
      }
      else if ( a2 == -1073741790 || a2 == -1073741823 || a2 == -1073741811 || a2 == -1073741801 )
      {
        goto LABEL_2;
      }
    }
    else if ( a2 <= -1073741251 )
    {
      if ( a2 == -1073741251 || a2 == -1073741306 || a2 == -1073741305 || a2 == -1073741275 )
        goto LABEL_2;
    }
    else if ( !a2 || a2 == 259 )
    {
      goto LABEL_2;
    }
    Length = CurrentStackLocation->Parameters.Read.Length;
    v6 = 0;
  }
LABEL_2:
  AFDETW_TRACESENDTO(1, 3038, FsContext);
  if ( (BYTE1(xmmword_1400875E0) & 4) != 0 )
    WPP_SF_qqD(1034, 23, WPP_c50ec9d9ea093d45966feac367cb7ead_Traceguids, v3, FsContext, v6);
  v9 = P[18];
  v10 = *(struct _KPROCESS **)(FsContext + 48);
  if ( (_DWORD)v9 == AfdBufferTagSize )
  {
    v15 = *((_WORD *)P + 48);
    if ( (v15 & 0x10) != 0 )
    {
      v16 = (__int64 *)*((_QWORD *)P + 6);
      v17 = *v16;
      *v16 = 0;
      *((_WORD *)P + 48) &= 0xFFEDu;
      AfdTLReleaseIndications(v17);
    }
    else if ( (v15 & 8) != 0 )
    {
      *((_WORD *)P + 48) = v15 & 0xFFF7;
      TdiReturnChainedReceives((PVOID *)P + 6, 1u);
    }
    v18 = (unsigned int *)*((_QWORD *)P + 5);
    if ( v18 == P + 26 )
    {
      if ( v10 )
        PsReturnPoolQuota(v10, (POOL_TYPE)512, *((unsigned __int16 *)P + 49) + 104LL);
      ExFreePoolWithTag(P, 0x42646641u);
    }
    else
    {
      if ( v18 )
      {
        PplFreeToLookasideList(PplAddressPool, v18);
        *((_QWORD *)P + 5) = 0;
      }
      if ( (P[24] & 0x100) == 0 )
      {
        if ( v10 )
          PsReturnPoolQuota(v10, (POOL_TYPE)512, *((unsigned __int16 *)P + 49) + 104LL);
        *((_WORD *)P + 48) |= 0x100u;
      }
      PplFreeToLookasideListProcessor(AfdPplBufferTagPool, P, P[23]);
    }
  }
  else if ( *((unsigned __int16 *)P + 49) == (_DWORD)AfdStandardAddressLength
         && (unsigned int)v9 <= (unsigned int)AfdHugeBufferSize )
  {
    if ( (_DWORD)v9 == (_DWORD)AfdSmallBufferSize )
    {
      v11 = AfdPplSmallBufferPool;
      v12 = AfdPplSmallBufferSize;
    }
    else if ( (_DWORD)v9 == (_DWORD)AfdMediumBufferSize )
    {
      v11 = AfdPplMediumBufferPool;
      v12 = AfdPplMediumBufferSize;
    }
    else if ( (_DWORD)v9 == (_DWORD)AfdLargeBufferSize )
    {
      v11 = AfdPplLargeBufferPool;
      v12 = AfdPplLargeBufferSize;
    }
    else
    {
      v11 = AfdPplHugeBufferPool;
      v12 = AfdPplHugeBufferSize;
    }
    if ( (P[24] & 0x100) == 0 )
    {
      if ( v10 )
        PsReturnPoolQuota(v10, (POOL_TYPE)512, v12);
      *((_WORD *)P + 48) |= 0x100u;
    }
    v13 = (unsigned __int64)(P[23] + 1) << 7;
    if ( !v11[v13 + 176] )
      PplpLazyInitializeLookasideList(v11, &v11[v13 + 64]);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)&v11[v13 + 64], P);
  }
  else
  {
    if ( v10 )
    {
      v19 = AfdCalculateBufferSize(v9);
      PsReturnPoolQuota(v10, (POOL_TYPE)512, v19);
    }
    AfdFreeBuffer(P, 0);
  }
  AfdDereferenceEndpoint(FsContext);
  v14 = AfdPriorityBoost;
  v3->IoStatus.Information = Length;
  v3->IoStatus.Status = v6;
  IofCompleteRequest(v3, v14);
}

```

## disassembly

```asm
0x14000ff20  mov     [rsp+arg_8], rbx
0x14000ff25  mov     [rsp+arg_10], rbp
0x14000ff2a  push    rsi
0x14000ff2b  push    rdi
0x14000ff2c  push    r13
0x14000ff2e  push    r14
0x14000ff30  push    r15
0x14000ff32  sub     rsp, 60h
0x14000ff36  mov     rdi, [rcx+30h]
0x14000ff3a  mov     rbx, rcx
0x14000ff3d  mov     r15, r8
0x14000ff40  mov     esi, edx
0x14000ff42  mov     rcx, [rdi+0B8h]
0x14000ff49  mov     rax, [rcx+30h]
0x14000ff4d  mov     r14, [rax+18h]
0x14000ff51  cmp     edx, 0C000023Ch
0x14000ff57  jnz     loc_14001008A
0x14000ff5d  mov     rax, [rbx+28h]
0x14000ff61  xor     r9d, r9d
0x14000ff64  mov     [rsp+88h+var_40], rdi
0x14000ff69  mov     r8, r14
0x14000ff6c  mov     [rsp+88h+var_48], rax
0x14000ff71  mov     edx, 0BDEh
0x14000ff76  mov     rax, [rdi+8]
0x14000ff7a  mov     ecx, 1
0x14000ff7f  mov     [rsp+88h+var_50], esi
0x14000ff83  mov     [rsp+88h+var_58], r15d
0x14000ff88  mov     [rsp+88h+var_60], rax
0x14000ff8d  mov     dword ptr [rsp+88h+var_68], 1
0x14000ff95  call    AFDETW_TRACESENDTO
0x14000ff9a  test    byte ptr cs:xmmword_1400875E0+1, 4
0x14000ffa1  jnz     loc_1400102AD
0x14000ffa7  mov     ecx, [rbx+48h]; Length
0x14000ffaa  cmp     ecx, cs:AfdBufferTagSize
0x14000ffb0  mov     r13, [r14+30h]
0x14000ffb4  jz      loc_140010123
0x14000ffba  movzx   edx, word ptr [rbx+62h]
0x14000ffbe  cmp     edx, cs:AfdStandardAddressLength
0x14000ffc4  jnz     loc_1400100B4
0x14000ffca  cmp     ecx, cs:AfdHugeBufferSize
0x14000ffd0  ja      loc_1400100B4
0x14000ffd6  cmp     ecx, cs:AfdSmallBufferSize
0x14000ffdc  mov     [rsp+88h+arg_0], r12
0x14000ffe4  jz      loc_140010110
0x14000ffea  cmp     ecx, cs:AfdMediumBufferSize
0x14000fff0  jnz     loc_1400101B1
0x14000fff6  mov     r12, cs:AfdPplMediumBufferPool
0x14000fffd  mov     r8, cs:AfdPplMediumBufferSize; Amount
0x140010004  mov     ebp, 100h
0x140010009  test    [rbx+60h], bp
0x14001000d  jz      loc_14001020B
0x140010013  mov     ebp, [rbx+5Ch]
0x140010016  inc     ebp
0x140010018  shl     rbp, 7
0x14001001c  movzx   eax, byte ptr [rbp+r12+0B0h]
0x140010025  test    al, al
0x140010027  jz      loc_14001026E
0x14001002d  lea     rcx, [rbp+40h]
0x140010031  mov     rdx, rbx; Entry
0x140010034  add     rcx, r12; Lookaside
0x140010037  call    cs:__imp_ExFreeToLookasideListEx
0x14001003e  nop     dword ptr [rax+rax+00h]
0x140010043  mov     r12, [rsp+88h+arg_0]
0x14001004b  mov     rcx, r14
0x14001004e  call    AfdDereferenceEndpoint
0x140010053  movzx   edx, cs:AfdPriorityBoost; PriorityBoost
0x14001005a  mov     rcx, rdi; Irp
0x14001005d  mov     [rdi+38h], r15
0x140010061  mov     [rdi+30h], esi
0x140010064  call    cs:__imp_IofCompleteRequest
0x14001006b  nop     dword ptr [rax+rax+00h]
0x140010070  lea     r11, [rsp+88h+var_28]
0x140010075  mov     rbx, [r11+38h]
0x140010079  mov     rbp, [r11+40h]
0x14001007d  mov     rsp, r11
0x140010080  pop     r15
0x140010082  pop     r14
0x140010084  pop     r13
0x140010086  pop     rdi
0x140010087  pop     rsi
0x140010088  retn
0x14001008a  cmp     edx, 0C0000141h
0x140010090  jle     short loc_1400100C9
0x140010092  cmp     edx, 0C000023Dh
0x140010098  jle     loc_1400102FD
0x14001009e  test    edx, edx
0x1400100a0  jz      loc_14000FF5D
0x1400100a6  cmp     edx, 103h
0x1400100ac  jz      loc_14000FF5D
0x1400100b2  jmp     short loc_140010105
0x1400100b4  test    r13, r13
0x1400100b7  jnz     loc_140010188
0x1400100bd  xor     edx, edx
0x1400100bf  mov     rcx, rbx
0x1400100c2  call    AfdFreeBuffer
0x1400100c7  jmp     short loc_14001004B
0x1400100c9  jz      loc_14000FF5D
0x1400100cf  cmp     edx, 0C0000022h
0x1400100d5  jg      loc_1400102D4
0x1400100db  jz      loc_14000FF5D
0x1400100e1  cmp     edx, 0C0000001h
0x1400100e7  jz      loc_14000FF5D
0x1400100ed  cmp     edx, 0C000000Dh
0x1400100f3  jz      loc_14000FF5D
0x1400100f9  cmp     edx, 0C0000017h
0x1400100ff  jz      loc_14000FF5D
0x140010105  mov     r15d, [rcx+8]
0x140010109  xor     esi, esi
0x14001010b  jmp     loc_14000FF5D
0x140010110  mov     r12, cs:AfdPplSmallBufferPool
0x140010117  mov     r8, cs:AfdPplSmallBufferSize
0x14001011e  jmp     loc_140010004
0x140010123  movzx   eax, word ptr [rbx+60h]
0x140010127  test    al, 10h
0x140010129  jz      loc_14001022D
0x14001012f  mov     rdx, [rbx+30h]
0x140010133  mov     eax, 0FFEDh
0x140010138  mov     rcx, [rdx]
0x14001013b  mov     qword ptr [rdx], 0
0x140010142  and     [rbx+60h], ax
0x140010146  call    AfdTLReleaseIndications
0x14001014b  mov     rdx, [rbx+28h]
0x14001014f  lea     rax, [rbx+68h]
0x140010153  cmp     rdx, rax
0x140010156  jz      loc_1400101E9
0x14001015c  test    rdx, rdx
0x14001015f  jnz     short loc_1400101D0
0x140010161  mov     ebp, 100h
0x140010166  test    [rbx+60h], bp
0x14001016a  jz      loc_140010282
0x140010170  mov     r8d, [rbx+5Ch]
0x140010174  mov     rdx, rbx
0x140010177  mov     rcx, cs:AfdPplBufferTagPool
0x14001017e  call    PplFreeToLookasideListProcessor
0x140010183  jmp     loc_14001004B
0x140010188  movzx   r8d, cs:AfdTdiStackSize
0x140010190  call    AfdCalculateBufferSize
0x140010195  mov     r8d, eax; Amount
0x140010198  mov     edx, 200h; PoolType
0x14001019d  mov     rcx, r13; Process
0x1400101a0  call    cs:__imp_PsReturnPoolQuota
0x1400101a7  nop     dword ptr [rax+rax+00h]
0x1400101ac  jmp     loc_1400100BD
0x1400101b1  cmp     ecx, cs:AfdLargeBufferSize
0x1400101b7  jnz     loc_14001025B
0x1400101bd  mov     r12, cs:AfdPplLargeBufferPool
0x1400101c4  mov     r8, cs:AfdPplLargeBufferSize
0x1400101cb  jmp     loc_140010004
0x1400101d0  mov     rcx, cs:PplAddressPool
0x1400101d7  call    PplFreeToLookasideList
0x1400101dc  mov     qword ptr [rbx+28h], 0
0x1400101e4  jmp     loc_140010161
0x1400101e9  test    r13, r13
0x1400101ec  jnz     loc_14001032C
0x1400101f2  mov     edx, 42646641h; Tag
0x1400101f7  mov     rcx, rbx; P
0x1400101fa  call    cs:__imp_ExFreePoolWithTag
0x140010201  nop     dword ptr [rax+rax+00h]
0x140010206  jmp     loc_14001004B
0x14001020b  test    r13, r13
0x14001020e  jz      short loc_140010224
0x140010210  mov     edx, 200h; PoolType
0x140010215  mov     rcx, r13; Process
0x140010218  call    cs:__imp_PsReturnPoolQuota
0x14001021f  nop     dword ptr [rax+rax+00h]
0x140010224  or      [rbx+60h], bp
0x140010228  jmp     loc_140010013
0x14001022d  test    al, 8
0x14001022f  jz      loc_14001014B
0x140010235  mov     ecx, 0FFF7h
0x14001023a  mov     edx, 1; NumberOfTsdus
0x14001023f  and     ax, cx
0x140010242  lea     rcx, [rbx+30h]; TsduDescriptors
0x140010246  mov     [rbx+60h], ax
0x14001024a  call    cs:__imp_TdiReturnChainedReceives
0x140010251  nop     dword ptr [rax+rax+00h]
0x140010256  jmp     loc_14001014B
0x14001025b  mov     r12, cs:AfdPplHugeBufferPool
0x140010262  mov     r8, cs:AfdPplHugeBufferSize
0x140010269  jmp     loc_140010004
0x14001026e  lea     rdx, [rbp+40h]
0x140010272  mov     rcx, r12
0x140010275  add     rdx, r12
0x140010278  call    PplpLazyInitializeLookasideList
0x14001027d  jmp     loc_14001002D
0x140010282  test    r13, r13
0x140010285  jz      short loc_1400102A4
0x140010287  movzx   r8d, word ptr [rbx+62h]
0x14001028c  mov     edx, 200h; PoolType
0x140010291  add     r8, 68h ; 'h'; Amount
0x140010295  mov     rcx, r13; Process
0x140010298  call    cs:__imp_PsReturnPoolQuota
0x14001029f  nop     dword ptr [rax+rax+00h]
0x1400102a4  or      [rbx+60h], bp
0x1400102a8  jmp     loc_140010170
0x1400102ad  mov     edx, 17h
0x1400102b2  mov     dword ptr [rsp+88h+var_60], esi
0x1400102b6  mov     ecx, 40Ah
0x1400102bb  mov     [rsp+88h+var_68], r14
0x1400102c0  mov     r9, rdi
0x1400102c3  lea     r8, WPP_c50ec9d9ea093d45966feac367cb7ead_Traceguids
0x1400102ca  call    WPP_SF_qqD
0x1400102cf  jmp     loc_14000FFA7
0x1400102d4  cmp     edx, 0C000009Ah
0x1400102da  jz      loc_14000FF5D
0x1400102e0  cmp     edx, 0C00000BEh
0x1400102e6  jz      loc_14000FF5D
0x1400102ec  cmp     edx, 0C0000120h
0x1400102f2  jz      loc_14000FF5D
0x1400102f8  jmp     loc_140010105
0x1400102fd  jz      loc_14000FF5D
0x140010303  cmp     edx, 0C0000206h
0x140010309  jz      loc_14000FF5D
0x14001030f  cmp     edx, 0C0000207h
0x140010315  jz      loc_14000FF5D
0x14001031b  cmp     edx, 0C0000225h
0x140010321  jz      loc_14000FF5D
0x140010327  jmp     loc_140010105
0x14001032c  movzx   r8d, word ptr [rbx+62h]
0x140010331  mov     edx, 200h; PoolType
0x140010336  add     r8, 68h ; 'h'; Amount
0x14001033a  mov     rcx, r13; Process
0x14001033d  call    cs:__imp_PsReturnPoolQuota
0x140010344  nop     dword ptr [rax+rax+00h]
0x140010349  jmp     loc_1400101F2
```
