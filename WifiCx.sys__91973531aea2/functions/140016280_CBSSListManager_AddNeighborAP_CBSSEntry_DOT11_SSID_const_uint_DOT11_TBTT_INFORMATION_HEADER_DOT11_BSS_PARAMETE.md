# CBSSListManager::AddNeighborAP(CBSSEntry *,_DOT11_SSID * const,uint,DOT11_TBTT_INFORMATION_HEADER,DOT11_BSS_PARAMETERS,DOT11_MLD_PARAMETERS,uchar (*)[6],_DOT11_BAND_ID,uchar)

- ea: `0x140016280`
- end: `0x1400165e2`
- name: `?AddNeighborAP@CBSSListManager@@QEAAPEAVCBSSEntry@@PEAV2@QEAU_DOT11_SSID@@ITDOT11_TBTT_INFORMATION_HEADER@@TDOT11_BSS_PARAMETERS@@TDOT11_MLD_PARAMETERS@@PEAY05EW4_DOT11_BAND_ID@@E@Z`
- size: `866`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140015ac0`

## callees

- `0x140009420`
- `0x140013ca0`
- `0x1400158e0`
- `0x140016280`
- `0x14001b910`
- `0x1400205a4`
- `0x140098814`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall CBSSListManager::AddNeighborAP(
        _QWORD *a1,
        struct CBSSEntry *a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int16 a5,
        unsigned __int8 a6,
        __int64 a7,
        unsigned __int8 (*a8)[6],
        int a9,
        unsigned __int8 a10)
{
  int v12; // ebx
  unsigned __int8 *v13; // r14
  __int64 v14; // rsi
  _QWORD *v15; // r8
  __int64 v16; // rdx
  _QWORD *i; // rcx
  int v18; // eax
  int v19; // r12d
  CBSSEntry *v20; // rax
  int v21; // edx
  int v22; // r8d
  CBSSEntry *v23; // rax
  char v24; // r15
  unsigned __int8 v26; // bl
  int v27; // edx
  int v28; // r8d
  int v29; // edx
  int v30; // r8d
  __int64 *v31; // [rsp+20h] [rbp-68h]
  int v32; // [rsp+38h] [rbp-50h]
  __int64 v35; // [rsp+A0h] [rbp+18h] BYREF

  v35 = a3;
  switch ( a9 )
  {
    case -1:
      v12 = -1;
      break;
    case 0:
      v12 = 0;
      break;
    case 1:
      v12 = 1;
      break;
    case 2:
      v12 = 2;
      break;
    case 3:
      v12 = 3;
      break;
    case 4:
      v12 = 4;
      break;
    case 5:
      v12 = 5;
      break;
    default:
      v12 = a9;
      break;
  }
  v13 = (unsigned __int8 *)a8;
  if ( a4 )
  {
    v15 = a1 + 43;
    v16 = 0;
    for ( i = (_QWORD *)a1[43]; i != v15; i = (_QWORD *)*i )
    {
      if ( i )
        v14 = i[2];
      else
        v14 = 0;
      if ( *(_DWORD *)a8 == *(_DWORD *)(v14 + 32) && *(_WORD *)&(*a8)[4] == *(_WORD *)(v14 + 36) )
      {
        v18 = *(_DWORD *)(v14 + 688);
        if ( a4 == v18 )
          goto LABEL_22;
        if ( !v18 )
          v16 = v14;
      }
    }
    v14 = v16;
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int8 *))*a1)(a1, (unsigned __int8 *)a8);
  }
LABEL_22:
  v19 = a10;
  if ( !v14 )
  {
    v20 = (CBSSEntry *)operator new(0x3C0u);
    if ( v20 )
    {
      v23 = CBSSEntry::CBSSEntry(v20, (const unsigned __int8 (*)[6])v13, 0);
      v14 = (__int64)v23;
      if ( v23 )
      {
        v24 = 1;
        *((_DWORD *)v23 + 172) = a4;
        goto LABEL_32;
      }
    }
    else
    {
      v14 = 0;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D_MAC__MAC_(WPP_GLOBAL_Control->DeviceExtension, v21, v22, 156);
    return v14;
  }
  v24 = 0;
  if ( v12 == -1 )
  {
    v12 = *(_DWORD *)(v14 + 684);
LABEL_32:
    if ( v12 == -1 )
      goto LABEL_36;
  }
  if ( (_BYTE)v19 && (unsigned int)(*(_DWORD *)(v14 + 684) + 1) <= 1 )
  {
    *(_DWORD *)(v14 + 680) = v19;
    *(_DWORD *)(v14 + 684) = v12;
  }
LABEL_36:
  v26 = a6;
  LOWORD(v35) = *(_WORD *)a7;
  BYTE2(v35) = *(_BYTE *)(a7 + 2);
  v31 = &v35;
  if ( (unsigned int)CBSSEntry::AddIncomingLinkFromNeighborAP(v14, a2, a5, a6) )
    goto LABEL_43;
  LOWORD(v35) = *(_WORD *)a7;
  BYTE2(v35) = *(_BYTE *)(a7 + 2);
  v32 = a9;
  LOBYTE(v31) = v26;
  if ( (unsigned int)CBSSEntry::AddOutgoingLinkToNeighborAP(a2, v14, a4, a5) )
  {
    CBSSEntry::RemoveIncomingLinkFromNeighborAP((CBSSEntry *)v14, a2);
LABEL_43:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D_MAC__MAC_(WPP_GLOBAL_Control->DeviceExtension, v27, v28, 158);
    goto LABEL_45;
  }
  if ( !v24
    || !(*(unsigned int (__fastcall **)(_QWORD *, __int64, struct CBSSEntry *, _QWORD, __int64 *, __int64 *, unsigned __int8 *, int, _BYTE))(*a1 + 8LL))(
          a1,
          v14,
          a2,
          0,
          v31,
          &v35,
          v13,
          v32,
          v19) )
  {
    return v14;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D_MAC__MAC_(WPP_GLOBAL_Control->DeviceExtension, v29, v30, 157);
LABEL_45:
  if ( !v14 || !v24 )
    return v14;
  (**(void (__fastcall ***)(__int64, __int64))v14)(v14, 1);
  return 0;
}

```

## disassembly

```asm
0x140016280  mov     [rsp+arg_10], r8
0x140016285  mov     [rsp+arg_8], rdx
0x14001628a  mov     [rsp+arg_0], rcx
0x14001628f  push    rbx
0x140016290  push    rbp
0x140016291  push    rsi
0x140016292  push    r12
0x140016294  push    r13
0x140016296  sub     rsp, 60h
0x14001629a  mov     r13, rdx
0x14001629d  mov     ebp, r9d
0x1400162a0  mov     edx, [rsp+88h+arg_40]
0x1400162a7  lea     eax, [rdx+1]; switch 7 cases
0x1400162aa  cmp     eax, 6
0x1400162ad  ja      short def_1400162C3; jumptable 00000001400162C3 default case
0x1400162af  lea     r9, cs:140000000h
0x1400162b6  cdqe
0x1400162b8  mov     r8d, ds:(jpt_1400162C3 - 140000000h)[r9+rax*4]
0x1400162c0  add     r8, r9
0x1400162c3  jmp     r8; switch jump
0x1400162c9  xor     ebx, ebx; jumptable 00000001400162C3 case 0
0x1400162cb  jmp     short loc_1400162F9
0x1400162cd  mov     ebx, 1; jumptable 00000001400162C3 case 1
0x1400162d2  jmp     short loc_1400162F9
0x1400162d4  mov     ebx, 2; jumptable 00000001400162C3 case 2
0x1400162d9  jmp     short loc_1400162F9
0x1400162db  mov     ebx, 5; jumptable 00000001400162C3 case 5
0x1400162e0  jmp     short loc_1400162F9
0x1400162e2  mov     ebx, 3; jumptable 00000001400162C3 case 3
0x1400162e7  jmp     short loc_1400162F9
0x1400162e9  mov     ebx, 4; jumptable 00000001400162C3 case 4
0x1400162ee  jmp     short loc_1400162F9
0x1400162f0  mov     ebx, 0FFFFFFFFh; jumptable 00000001400162C3 case -1
0x1400162f5  jmp     short loc_1400162F9
0x1400162f7  mov     ebx, edx; jumptable 00000001400162C3 default case
0x1400162f9  mov     [rsp+88h+var_30], r14
0x1400162fe  mov     r14, [rsp+88h+arg_38]
0x140016306  test    ebp, ebp
0x140016308  jnz     short loc_14001631D
0x14001630a  mov     rax, [rcx]
0x14001630d  mov     rdx, r14
0x140016310  mov     rax, [rax]
0x140016313  call    _guard_dispatch_icall
0x140016318  mov     rsi, rax
0x14001631b  jmp     short loc_14001636B
0x14001631d  lea     r8, [rcx+158h]
0x140016324  xor     edx, edx
0x140016326  mov     rcx, [r8]
0x140016329  cmp     rcx, r8
0x14001632c  jz      short loc_140016368
0x14001632e  xchg    ax, ax
0x140016330  test    rcx, rcx
0x140016333  jnz     short loc_140016339
0x140016335  xor     esi, esi
0x140016337  jmp     short loc_14001633D
0x140016339  mov     rsi, [rcx+10h]
0x14001633d  mov     eax, [r14]
0x140016340  cmp     eax, [rsi+20h]
0x140016343  jnz     short loc_140016360
0x140016345  movzx   eax, word ptr [r14+4]
0x14001634a  cmp     ax, [rsi+24h]
0x14001634e  jnz     short loc_140016360
0x140016350  mov     eax, [rsi+2B0h]
0x140016356  cmp     ebp, eax
0x140016358  jz      short loc_14001636B
0x14001635a  test    eax, eax
0x14001635c  cmovz   rdx, rsi
0x140016360  mov     rcx, [rcx]
0x140016363  cmp     rcx, r8
0x140016366  jnz     short loc_140016330
0x140016368  mov     rsi, rdx
0x14001636b  movzx   r12d, [rsp+88h+arg_48]
0x140016374  mov     [rsp+88h+var_38], r15
0x140016379  test    rsi, rsi
0x14001637c  jnz     loc_140016406
0x140016382  mov     ecx, 3C0h; unsigned __int64
0x140016387  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001638c  test    rax, rax
0x14001638f  jz      short loc_1400163B2
0x140016391  xor     r8d, r8d; unsigned __int8
0x140016394  mov     rdx, r14; unsigned __int8 (*)[6]
0x140016397  mov     rcx, rax; this
0x14001639a  call    ??0CBSSEntry@@QEAA@AEAY05$$CBEE@Z; CBSSEntry::CBSSEntry(uchar const (&)[6],uchar)
0x14001639f  mov     rsi, rax
0x1400163a2  test    rax, rax
0x1400163a5  jz      short loc_1400163B4
0x1400163a7  mov     r15b, 1
0x1400163aa  mov     [rax+2B0h], ebp
0x1400163b0  jmp     short loc_140016414
0x1400163b2  xor     esi, esi
0x1400163b4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400163bb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400163c2  jz      short loc_1400163EC
0x1400163c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400163cb  lea     rax, [r13+20h]
0x1400163cf  mov     [rsp+88h+var_50], rax
0x1400163d4  mov     r9d, 9Ch
0x1400163da  mov     [rsp+88h+var_58], r14
0x1400163df  mov     dword ptr [rsp+88h+var_60], ebp
0x1400163e3  mov     rcx, [rcx+40h]
0x1400163e7  call    WPP_RECORDER_SF_D_MAC__MAC_
0x1400163ec  mov     rax, rsi
0x1400163ef  mov     r15, [rsp+88h+var_38]
0x1400163f4  mov     r14, [rsp+88h+var_30]
0x1400163f9  add     rsp, 60h
0x1400163fd  pop     r13
0x1400163ff  pop     r12
0x140016401  pop     rsi
0x140016402  pop     rbp
0x140016403  pop     rbx
0x140016404  retn
0x140016406  xor     r15b, r15b
0x140016409  cmp     ebx, 0FFFFFFFFh
0x14001640c  jnz     short loc_140016419
0x14001640e  mov     ebx, [rsi+2ACh]
0x140016414  cmp     ebx, 0FFFFFFFFh
0x140016417  jz      short loc_140016438
0x140016419  test    r12b, r12b
0x14001641c  jz      short loc_140016438
0x14001641e  mov     eax, [rsi+2ACh]
0x140016424  inc     eax
0x140016426  cmp     eax, 1
0x140016429  ja      short loc_140016438
0x14001642b  mov     [rsi+2A8h], r12d
0x140016432  mov     [rsi+2ACh], ebx
0x140016438  mov     rcx, [rsp+88h+arg_30]
0x140016440  mov     rdx, r13
0x140016443  movzx   ebx, [rsp+88h+arg_28]
0x14001644b  movzx   r8d, [rsp+88h+arg_20]
0x140016454  movzx   r9d, bl
0x140016458  movzx   eax, word ptr [rcx]
0x14001645b  mov     word ptr [rsp+88h+arg_10], ax
0x140016463  movzx   eax, byte ptr [rcx+2]
0x140016467  mov     rcx, rsi
0x14001646a  mov     byte ptr [rsp+88h+arg_10+2], al
0x140016471  lea     rax, [rsp+88h+arg_10]
0x140016479  mov     [rsp+88h+var_68], rax
0x14001647e  call    ?AddIncomingLinkFromNeighborAP@CBSSEntry@@QEAAHPEAV1@TDOT11_TBTT_INFORMATION_HEADER@@TDOT11_BSS_PARAMETERS@@TDOT11_MLD_PARAMETERS@@@Z; CBSSEntry::AddIncomingLinkFromNeighborAP(CBSSEntry *,DOT11_TBTT_INFORMATION_HEADER,DOT11_BSS_PARAMETERS,DOT11_MLD_PARAMETERS)
0x140016483  mov     r13d, eax
0x140016486  test    eax, eax
0x140016488  jnz     loc_14001656D
0x14001648e  mov     rcx, [rsp+88h+arg_30]
0x140016496  mov     r8d, ebp
0x140016499  movzx   r9d, [rsp+88h+arg_20]
0x1400164a2  mov     rdx, rsi
0x1400164a5  mov     [rsp+88h+var_48], r12b
0x1400164aa  movzx   eax, word ptr [rcx]
0x1400164ad  mov     word ptr [rsp+88h+arg_10], ax
0x1400164b5  movzx   eax, byte ptr [rcx+2]
0x1400164b9  mov     byte ptr [rsp+88h+arg_10+2], al
0x1400164c0  mov     eax, [rsp+88h+arg_40]
0x1400164c7  mov     dword ptr [rsp+88h+var_50], eax
0x1400164cb  lea     rax, [rsp+88h+arg_10]
0x1400164d3  mov     [rsp+88h+var_58], r14
0x1400164d8  mov     [rsp+88h+var_60], rax
0x1400164dd  mov     byte ptr [rsp+88h+var_68], bl
0x1400164e1  mov     rbx, [rsp+88h+arg_8]
0x1400164e9  mov     rcx, rbx
0x1400164ec  call    ?AddOutgoingLinkToNeighborAP@CBSSEntry@@QEAAHPEAV1@ITDOT11_TBTT_INFORMATION_HEADER@@TDOT11_BSS_PARAMETERS@@TDOT11_MLD_PARAMETERS@@PEAY05EW4_DOT11_BAND_ID@@E@Z; CBSSEntry::AddOutgoingLinkToNeighborAP(CBSSEntry *,uint,DOT11_TBTT_INFORMATION_HEADER,DOT11_BSS_PARAMETERS,DOT11_MLD_PARAMETERS,uchar (*)[6],_DOT11_BAND_ID,uchar)
0x1400164f1  mov     r13d, eax
0x1400164f4  test    eax, eax
0x1400164f6  jz      short loc_140016505
0x1400164f8  mov     rdx, rbx; struct CBSSEntry *
0x1400164fb  mov     rcx, rsi; this
0x1400164fe  call    ?RemoveIncomingLinkFromNeighborAP@CBSSEntry@@QEAAXPEAV1@@Z; CBSSEntry::RemoveIncomingLinkFromNeighborAP(CBSSEntry *)
0x140016503  jmp     short loc_140016575
0x140016505  test    r15b, r15b
0x140016508  jz      loc_1400163EC
0x14001650e  mov     rcx, [rsp+88h+arg_0]
0x140016516  xor     r9d, r9d
0x140016519  mov     r8, rbx
0x14001651c  mov     rdx, rsi
0x14001651f  mov     rax, [rcx]
0x140016522  mov     rax, [rax+8]
0x140016526  call    _guard_dispatch_icall
0x14001652b  test    eax, eax
0x14001652d  jz      loc_1400163EC
0x140016533  lea     rax, WPP_RECORDER_INITIALIZED
0x14001653a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140016541  jz      short loc_1400165B6
0x140016543  mov     rcx, cs:WPP_GLOBAL_Control
0x14001654a  lea     rax, [rbx+20h]
0x14001654e  mov     [rsp+88h+var_50], rax
0x140016553  mov     r9d, 9Dh
0x140016559  mov     [rsp+88h+var_58], r14
0x14001655e  mov     dword ptr [rsp+88h+var_60], ebp
0x140016562  mov     rcx, [rcx+40h]
0x140016566  call    WPP_RECORDER_SF_D_MAC__MAC_
0x14001656b  jmp     short loc_1400165B6
0x14001656d  mov     rbx, [rsp+88h+arg_8]
0x140016575  lea     rax, WPP_RECORDER_INITIALIZED
0x14001657c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140016583  jz      short loc_1400165B6
0x140016585  mov     rcx, cs:WPP_GLOBAL_Control
0x14001658c  lea     rax, [rbx+20h]
0x140016590  mov     [rsp+88h+var_50], rax
0x140016595  mov     r9d, 9Eh
0x14001659b  mov     [rsp+88h+var_58], r14
0x1400165a0  mov     dword ptr [rsp+88h+var_60], ebp
0x1400165a4  mov     rcx, [rcx+40h]
0x1400165a8  call    WPP_RECORDER_SF_D_MAC__MAC_
0x1400165ad  test    r13d, r13d
0x1400165b0  jz      loc_1400163EC
0x1400165b6  test    rsi, rsi
0x1400165b9  jz      loc_1400163EC
0x1400165bf  test    r15b, r15b
0x1400165c2  jz      loc_1400163EC
0x1400165c8  mov     rax, [rsi]
0x1400165cb  mov     edx, 1
0x1400165d0  mov     rcx, rsi
0x1400165d3  mov     rax, [rax]
0x1400165d6  call    _guard_dispatch_icall
0x1400165db  xor     eax, eax
0x1400165dd  jmp     loc_1400163EF
```
