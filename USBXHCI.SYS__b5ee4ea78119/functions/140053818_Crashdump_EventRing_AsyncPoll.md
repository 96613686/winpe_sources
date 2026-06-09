# Crashdump_EventRing_AsyncPoll

- ea: `0x140053818`
- end: `0x140053aee`
- name: `Crashdump_EventRing_AsyncPoll`
- size: `726`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400523d0`

## callees

- `0x14003c814`
- `0x140053818`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140053843`
- `ntoskrnl!DbgPrintEx` at `0x1400538c6`
- `ntoskrnl!DbgPrintEx` at `0x1400539dd`
- `ntoskrnl!DbgPrintEx` at `0x140053a3e`
- `ntoskrnl!DbgPrintEx` at `0x140053a64`
- `ntoskrnl!DbgPrintEx` at `0x140053ad2`
- `ntoskrnl!DbgPrintEx` at `0x140053843`
- `ntoskrnl!DbgPrintEx` at `0x1400538c6`
- `ntoskrnl!DbgPrintEx` at `0x1400539dd`
- `ntoskrnl!DbgPrintEx` at `0x140053a3e`
- `ntoskrnl!DbgPrintEx` at `0x140053a64`
- `ntoskrnl!DbgPrintEx` at `0x140053ad2`

## string_xrefs

- `0x1400539c2`: `XHCIDUMP: URB Status %u: URB Transfer Length %u, TRB Completion Code: %u, status =0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_EventRing_AsyncPoll(__int64 a1, __int64 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rbp
  int v6; // r10d
  __int64 v7; // rsi
  int v8; // ecx
  int v9; // edx
  __int64 v10; // r8
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // r9d
  int v16; // ecx
  int v17; // r9d
  int v18; // r9d
  int v19; // eax
  __int64 v20; // r8
  bool v21; // zf

  v4 = 259;
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_EventRing_Poll: begin\n");
  v5 = *(_QWORD *)(a1 + 72);
  v6 = *(_DWORD *)(a1 + 88);
  v7 = 2LL * *(unsigned int *)(a1 + 92);
  v8 = *(_DWORD *)(v5 + 16LL * *(unsigned int *)(a1 + 92) + 12);
  if ( (v8 & 1) != v6 )
    goto LABEL_34;
  v9 = (unsigned __int16)v8 >> 10;
  if ( v9 == 32 && (v8 & 4) != 0 )
    v10 = 0;
  else
    v10 = *(_QWORD *)(v5 + 16LL * *(unsigned int *)(a1 + 92));
  DbgPrintEx(
    0x93u,
    3u,
    "XHCIDUMP: EventRing: CS: %u, EI: %03u, ET: %u, CC: %u, Len: %u, Addr: 0x%I64X\n",
    v6,
    *(_DWORD *)(a1 + 92),
    v9,
    *(unsigned __int8 *)(v5 + 16LL * *(unsigned int *)(a1 + 92) + 11),
    *(_DWORD *)(v5 + 16LL * *(unsigned int *)(a1 + 92) + 8) & 0xFFFFFF,
    v10);
  v11 = *(unsigned int *)(v5 + 8 * v7 + 12);
  if ( (*(_DWORD *)(v5 + 8 * v7 + 12) & 0xFC00) != 0x8000 )
  {
    v17 = (unsigned __int16)v11 >> 10;
    if ( v17 == 34 )
    {
      v18 = *(unsigned __int8 *)(v5 + 8 * v7 + 3);
      DbgPrintEx(
        0x93u,
        3u,
        "XHCIDUMP: Ignoring port status change event for port %u, CCS: %u, CSC: %u\n",
        v18,
        *(_DWORD *)(*(_QWORD *)(**(_QWORD **)(a1 + 8) + 32LL) + 16 * ((unsigned int)(v18 - 1) + 64LL)) & 1,
        (*(_DWORD *)(*(_QWORD *)(**(_QWORD **)(a1 + 8) + 32LL) + 16 * ((unsigned int)(v18 - 1) + 64LL)) >> 17) & 1);
    }
    else
    {
      DbgPrintEx(
        0x93u,
        2u,
        "XHCIDUMP: Unsolicited event encountered: ET: %u, CC: %u\n",
        v17,
        *(unsigned __int8 *)(v5 + 8 * v7 + 11));
    }
    goto LABEL_28;
  }
  v12 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 576LL) + 8 * ((v11 >> 16) & 0x1F) + 112);
  *a2 = *(_QWORD *)(v12 + 176);
  v13 = *(_QWORD *)((-(__int64)(*(_DWORD *)(v12 + 160) != 0) & 0xFFFFFFFFFFFFFFE8uLL) + v12 + 112);
  *(_DWORD *)(v13 + 12) &= ~1u;
  ++*(_QWORD *)(v12 + 168);
  v14 = *a2;
  *(_DWORD *)(*a2 + 36) = 0;
  switch ( *(_BYTE *)(v5 + 8 * v7 + 11) )
  {
    case 1:
      if ( (*(_DWORD *)(v5 + 8 * v7 + 12) & 4) == 0 )
        goto LABEL_22;
      break;
    case 2:
      v15 = -1073741805;
      goto LABEL_23;
    case 3:
      v15 = -1073741806;
      goto LABEL_23;
    case 4:
      goto LABEL_22;
    case 6:
      v15 = -1073741820;
      goto LABEL_23;
    case 0xD:
      break;
    case 0x17:
      v15 = -1073545216;
      goto LABEL_23;
    case 0x24:
LABEL_22:
      v15 = -1073741807;
      goto LABEL_23;
    default:
      v15 = -2147481600;
LABEL_23:
      *(_DWORD *)(v14 + 4) = v15;
      v4 = -1073741823;
      v16 = 0;
      goto LABEL_24;
  }
  v4 = 0;
  v16 = *(_DWORD *)(v5 + 8 * v7 + 8) & 0xFFFFFF;
  *(_DWORD *)(v14 + 4) = 0;
  *(_DWORD *)(v14 + 36) = v16;
  v15 = 0;
LABEL_24:
  DbgPrintEx(
    0x93u,
    3u,
    "XHCIDUMP: URB Status %u: URB Transfer Length %u, TRB Completion Code: %u, status =0x%X\n",
    v15,
    v16,
    *(unsigned __int8 *)(v5 + 8 * v7 + 11),
    v4);
LABEL_28:
  if ( ++*(_DWORD *)(a1 + 92) == *(_DWORD *)(a1 + 84) )
  {
    v19 = ++*(_DWORD *)(a1 + 96);
    *(_DWORD *)(a1 + 92) = 0;
    if ( v19 == *(_DWORD *)(a1 + 80) )
    {
      v20 = *(_QWORD *)(a1 + 112);
      v21 = *(_DWORD *)(a1 + 88) == 0;
      *(_DWORD *)(a1 + 96) = 0;
      *(_DWORD *)(a1 + 88) = v21;
    }
    else
    {
      v20 = **(_QWORD **)(a1 + 104);
    }
    *(_QWORD *)(a1 + 104) = v20;
    *(_QWORD *)(a1 + 72) = *(_QWORD *)(v20 + 16);
  }
  Crashdump_EventRing_UpdateDequeuePointer(a1);
LABEL_34:
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_EventRing_Poll: end 0x%X\n", v4);
  return v4;
}

```

## disassembly

```asm
0x140053818  push    rbx
0x14005381a  push    rbp
0x14005381b  push    rsi
0x14005381c  push    rdi
0x14005381d  push    r12
0x14005381f  push    r14
0x140053821  sub     rsp, 58h
0x140053825  mov     r14, rdx
0x140053828  lea     r8, aXhcidumpCrashd_15; "XHCIDUMP: Crashdump_EventRing_Poll: beg"...
0x14005382f  mov     rdi, rcx
0x140053832  mov     ebx, 103h
0x140053837  mov     edx, 3; Level
0x14005383c  lea     r12d, [rbx-70h]
0x140053840  mov     ecx, r12d; ComponentId
0x140053843  call    cs:__imp_DbgPrintEx
0x14005384a  nop     dword ptr [rax+rax+00h]
0x14005384f  mov     r9d, [rdi+5Ch]
0x140053853  mov     rbp, [rdi+48h]
0x140053857  mov     esi, r9d
0x14005385a  mov     r10d, [rdi+58h]
0x14005385e  add     rsi, rsi
0x140053861  mov     ecx, [rbp+rsi*8+0Ch]
0x140053865  mov     eax, ecx
0x140053867  and     eax, 1
0x14005386a  cmp     eax, r10d
0x14005386d  jnz     loc_140053AC0
0x140053873  mov     edx, ecx
0x140053875  shr     edx, 0Ah
0x140053878  and     edx, 3Fh
0x14005387b  cmp     edx, 20h ; ' '
0x14005387e  jnz     short loc_14005388A
0x140053880  test    cl, 4
0x140053883  jz      short loc_14005388A
0x140053885  xor     r8d, r8d
0x140053888  jmp     short loc_14005388F
0x14005388a  mov     r8, [rbp+rsi*8+0]
0x14005388f  mov     ecx, [rbp+rsi*8+8]
0x140053893  movzx   eax, byte ptr [rbp+rsi*8+0Bh]
0x140053898  and     ecx, 0FFFFFFh
0x14005389e  mov     [rsp+88h+var_48], r8
0x1400538a3  lea     r8, aXhcidumpEventr; "XHCIDUMP: EventRing: CS: %u, EI: %03u, "...
0x1400538aa  mov     [rsp+88h+var_50], ecx
0x1400538ae  mov     ecx, r12d; ComponentId
0x1400538b1  mov     [rsp+88h+var_58], eax
0x1400538b5  mov     [rsp+88h+var_60], edx
0x1400538b9  mov     edx, 3; Level
0x1400538be  mov     [rsp+88h+var_68], r9d
0x1400538c3  mov     r9d, r10d
0x1400538c6  call    cs:__imp_DbgPrintEx
0x1400538cd  nop     dword ptr [rax+rax+00h]
0x1400538d2  mov     r9d, [rbp+rsi*8+0Ch]
0x1400538d7  mov     eax, r9d
0x1400538da  and     eax, 0FC00h
0x1400538df  cmp     eax, 8000h
0x1400538e4  jnz     loc_1400539EE
0x1400538ea  mov     rax, [rdi]
0x1400538ed  shr     r9, 10h
0x1400538f1  and     r9d, 1Fh
0x1400538f5  mov     rcx, [rax+240h]
0x1400538fc  mov     rdx, [rcx+r9*8+70h]
0x140053901  mov     rax, [rdx+0B0h]
0x140053908  mov     [r14], rax
0x14005390b  mov     eax, [rdx+0A0h]
0x140053911  neg     eax
0x140053913  sbb     rax, rax
0x140053916  and     rax, 0FFFFFFFFFFFFFFE8h
0x14005391a  mov     rax, [rax+rdx+70h]
0x14005391f  and     dword ptr [rax+0Ch], 0FFFFFFFEh
0x140053923  inc     qword ptr [rdx+0A8h]
0x14005392a  mov     rdx, [r14]
0x14005392d  mov     dword ptr [rdx+24h], 0
0x140053934  movzx   eax, byte ptr [rbp+rsi*8+0Bh]
0x140053939  sub     eax, 1
0x14005393c  jz      short loc_140053989
0x14005393e  sub     eax, 1
0x140053941  jz      short loc_140053981
0x140053943  sub     eax, 1
0x140053946  jz      short loc_140053979
0x140053948  sub     eax, 1
0x14005394b  jz      short loc_1400539AC
0x14005394d  sub     eax, 2
0x140053950  jz      short loc_140053971
0x140053952  sub     eax, 7
0x140053955  jz      short loc_140053991
0x140053957  sub     eax, 0Ah
0x14005395a  jz      short loc_140053969
0x14005395c  cmp     eax, 0Dh
0x14005395f  jz      short loc_1400539AC
0x140053961  mov     r9d, 80000800h
0x140053967  jmp     short loc_1400539B2
0x140053969  mov     r9d, 0C0030000h
0x14005396f  jmp     short loc_1400539B2
0x140053971  mov     r9d, 0C0000004h
0x140053977  jmp     short loc_1400539B2
0x140053979  mov     r9d, 0C0000012h
0x14005397f  jmp     short loc_1400539B2
0x140053981  mov     r9d, 0C0000013h
0x140053987  jmp     short loc_1400539B2
0x140053989  mov     eax, [rbp+rsi*8+0Ch]
0x14005398d  test    al, 4
0x14005398f  jz      short loc_1400539AC
0x140053991  mov     ecx, [rbp+rsi*8+8]
0x140053995  xor     ebx, ebx
0x140053997  and     ecx, 0FFFFFFh
0x14005399d  mov     dword ptr [rdx+4], 0
0x1400539a4  mov     [rdx+24h], ecx
0x1400539a7  xor     r9d, r9d
0x1400539aa  jmp     short loc_1400539BD
0x1400539ac  mov     r9d, 0C0000011h
0x1400539b2  mov     [rdx+4], r9d
0x1400539b6  mov     ebx, 0C0000001h
0x1400539bb  xor     ecx, ecx
0x1400539bd  movzx   eax, byte ptr [rbp+rsi*8+0Bh]
0x1400539c2  lea     r8, aXhcidumpUrbSta; "XHCIDUMP: URB Status %u: URB Transfer L"...
0x1400539c9  mov     [rsp+88h+var_58], ebx
0x1400539cd  mov     edx, 3; Level
0x1400539d2  mov     [rsp+88h+var_60], eax
0x1400539d6  mov     [rsp+88h+var_68], ecx
0x1400539da  mov     ecx, r12d; ComponentId
0x1400539dd  call    cs:__imp_DbgPrintEx
0x1400539e4  nop     dword ptr [rax+rax+00h]
0x1400539e9  jmp     loc_140053A70
0x1400539ee  shr     r9d, 0Ah
0x1400539f2  and     r9d, 3Fh
0x1400539f6  cmp     r9d, 22h ; '"'
0x1400539fa  jnz     short loc_140053A4C
0x1400539fc  mov     rax, [rdi+8]
0x140053a00  lea     r8, aXhcidumpIgnori; "XHCIDUMP: Ignoring port status change e"...
0x140053a07  movzx   r9d, byte ptr [rbp+rsi*8+3]
0x140053a0d  mov     rcx, [rax]
0x140053a10  lea     edx, [r9-1]
0x140053a14  add     rdx, 40h ; '@'
0x140053a18  add     rdx, rdx
0x140053a1b  mov     rax, [rcx+20h]
0x140053a1f  nop
0x140053a20  mov     eax, [rax+rdx*8]
0x140053a23  mov     ecx, eax
0x140053a25  shr     ecx, 11h
0x140053a28  and     eax, 1
0x140053a2b  and     ecx, 1
0x140053a2e  mov     edx, 3; Level
0x140053a33  mov     [rsp+88h+var_60], ecx
0x140053a37  mov     ecx, r12d; ComponentId
0x140053a3a  mov     [rsp+88h+var_68], eax
0x140053a3e  call    cs:__imp_DbgPrintEx
0x140053a45  nop     dword ptr [rax+rax+00h]
0x140053a4a  jmp     short loc_140053A70
0x140053a4c  movzx   eax, byte ptr [rbp+rsi*8+0Bh]
0x140053a51  lea     r8, aXhcidumpUnsoli; "XHCIDUMP: Unsolicited event encountered"...
0x140053a58  mov     edx, 2; Level
0x140053a5d  mov     [rsp+88h+var_68], eax
0x140053a61  mov     ecx, r12d; ComponentId
0x140053a64  call    cs:__imp_DbgPrintEx
0x140053a6b  nop     dword ptr [rax+rax+00h]
0x140053a70  inc     dword ptr [rdi+5Ch]
0x140053a73  mov     eax, [rdi+5Ch]
0x140053a76  cmp     eax, [rdi+54h]
0x140053a79  jnz     short loc_140053AB8
0x140053a7b  inc     dword ptr [rdi+60h]
0x140053a7e  mov     eax, [rdi+60h]
0x140053a81  mov     dword ptr [rdi+5Ch], 0
0x140053a88  cmp     eax, [rdi+50h]
0x140053a8b  jnz     short loc_140053AA5
0x140053a8d  mov     r8, [rdi+70h]
0x140053a91  xor     eax, eax
0x140053a93  cmp     [rdi+58h], eax
0x140053a96  mov     dword ptr [rdi+60h], 0
0x140053a9d  setz    al
0x140053aa0  mov     [rdi+58h], eax
0x140053aa3  jmp     short loc_140053AAC
0x140053aa5  mov     rax, [rdi+68h]
0x140053aa9  mov     r8, [rax]
0x140053aac  mov     [rdi+68h], r8
0x140053ab0  mov     r8, [r8+10h]
0x140053ab4  mov     [rdi+48h], r8
0x140053ab8  mov     rcx, rdi
0x140053abb  call    Crashdump_EventRing_UpdateDequeuePointer
0x140053ac0  mov     r9d, ebx
0x140053ac3  lea     r8, aXhcidumpCrashd_69; "XHCIDUMP: Crashdump_EventRing_Poll: end"...
0x140053aca  mov     edx, 3; Level
0x140053acf  mov     ecx, r12d; ComponentId
0x140053ad2  call    cs:__imp_DbgPrintEx
0x140053ad9  nop     dword ptr [rax+rax+00h]
0x140053ade  mov     eax, ebx
0x140053ae0  add     rsp, 58h
0x140053ae4  pop     r14
0x140053ae6  pop     r12
0x140053ae8  pop     rdi
0x140053ae9  pop     rsi
0x140053aea  pop     rbp
0x140053aeb  pop     rbx
0x140053aec  retn
```
