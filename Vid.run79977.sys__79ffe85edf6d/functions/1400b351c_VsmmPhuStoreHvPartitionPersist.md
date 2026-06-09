# VsmmPhuStoreHvPartitionPersist

- ea: `0x1400b351c`
- end: `0x1400b386b`
- name: `VsmmPhuStoreHvPartitionPersist`
- size: `847`
- prototype: `__int64 __fastcall(PVOID P, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400a05dc`

## callees

- `0x140021c60`
- `0x140021e00`
- `0x14002f724`
- `0x140076328`
- `0x1400b351c`
- `0x1400b856c`
- `0x1400ba7e4`
- `0x1400ba804`
- `0x1400fd3a8`

## import_xrefs

- `winhvr!WinHvGetSystemInformation` at `0x1400b3746`
- `winhvr!WinHvGetSystemInformation` at `0x1400b3746`
- `winhvr!WinHvSetPartitionProperty` at `0x1400b3773`
- `winhvr!WinHvSetPartitionProperty` at `0x1400b3773`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b35fe`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b363b`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b35fe`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b363b`
- `winhvr!WinHvCreatePartitionRemote` at `0x1400b36ee`
- `winhvr!WinHvCreatePartitionRemote` at `0x1400b36ee`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b37b9`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b37b9`

## pseudocode

```c
__int64 __fastcall VsmmPhuStoreHvPartitionPersist(char *P, char *a2)
{
  char *v2; // r14
  char v3; // r15
  int v5; // eax
  unsigned int v7; // edi
  int v8; // eax
  unsigned __int8 v9; // di
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 v15; // r8
  int v16; // eax
  int v17; // eax
  __int64 v18; // r8
  __int64 v20; // [rsp+40h] [rbp-40h] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+50h] [rbp-30h] BYREF
  __int64 v23; // [rsp+58h] [rbp-28h] BYREF
  __int128 v24; // [rsp+60h] [rbp-20h] BYREF
  __int64 v25; // [rsp+70h] [rbp-10h]

  v2 = P + 16;
  v25 = 0;
  v3 = 0;
  v21 = 0;
  v20 = 0;
  v5 = *((_DWORD *)P + 4);
  v24 = 0;
  if ( (v5 & 0x200) != 0 )
  {
    v7 = -1070137298;
    VidTraceErrorStatusInternal0(
      "VsmmPhuStoreHvPartitionPersist",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      3223,
      3224829998LL);
    goto LABEL_20;
  }
  v8 = VsmmPhuStorepSerializationChargeIncrease(*((_QWORD *)P + 1081), 144, 1);
  v7 = v8;
  if ( v8 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStoreHvPartitionPersist",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      3233,
      (unsigned int)v8);
    goto LABEL_20;
  }
  v24 = 0;
  v25 = 0;
  v9 = 0;
  v3 = 1;
  do
  {
    WinHvGetPartitionProperty(*((_QWORD *)P + 81), (unsigned int)v9 + 393226, &v21);
    v10 = v9++;
    *((_QWORD *)&v24 + v10) = ~v21;
  }
  while ( v9 < 2u );
  v11 = *((_QWORD *)P + 81);
  v22 = 0;
  WinHvGetPartitionProperty(v11, 393218, &v22);
  v25 = ~v22;
  v12 = *((_DWORD *)P + 2160);
  if ( (v12 & 2) == 0 )
    goto LABEL_16;
  if ( (v12 & 4) != 0 )
  {
    v13 = VsmmPhuStorepHvPartitionMirrorPrep(P);
    v7 = v13;
    if ( v13 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreHvPartitionPersist",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        3276,
        (unsigned int)v13);
      goto LABEL_20;
    }
    v14 = *((_QWORD *)P + 81);
LABEL_26:
    memset(a2, 0, 0x70u);
    *(_QWORD *)a2 = *((_QWORD *)P + 84);
    *((_DWORD *)a2 + 2) = *((_DWORD *)P + 170);
    VsmmPhuStoreCreationPropertiesSerialize(&v24, a2, v18);
    *((_DWORD *)a2 + 8) = *((_DWORD *)P + 800);
    VsmmPhuStoreHvPartitionMakeInvariantFlags(v2, P + 40, a2 + 40);
    *((_QWORD *)P + 1096) = v14;
    v7 = 0;
    *(_WORD *)(P + 8761) = 257;
    P[8760] = 1;
    return v7;
  }
  v15 = (unsigned __int8)P[2105];
  LODWORD(v15) = v15 | 0x80000000;
  if ( *v2 < 0 )
    v15 = (unsigned __int8)P[2105];
  v16 = WinHvCreatePartitionRemote(
          *((_QWORD *)P + 81),
          *((_QWORD *)P + 84),
          v15,
          *((unsigned int *)P + 170),
          &v24,
          &v20,
          VidHvMemLowMemPolicyCallbackRemote,
          P);
  v7 = v16;
  if ( v16 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStoreHvPartitionPersist",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      3306,
      (unsigned int)v16);
  }
  else
  {
LABEL_16:
    v23 = 0;
    if ( (int)WinHvGetSystemInformation(14, 0, 0, &v23, 8, 0) < 0
      || v23 != 1
      || (v17 = WinHvSetPartitionProperty(*((_QWORD *)P + 81)), v7 = v17, v17 >= 0) )
    {
      v14 = v20;
      goto LABEL_26;
    }
    VidTraceErrorStatusInternal0(
      "VsmmPhuStoreHvPartitionPersist",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      3338,
      (unsigned int)v17);
  }
LABEL_20:
  if ( v20 && (*((_DWORD *)P + 2160) & 4) == 0 )
    WinHvDeletePartitionRemote(*((_QWORD *)P + 81));
  if ( v3 )
    VsmmPhuStorepSerializationChargeDecrease(*((_QWORD *)P + 1081), 144);
  return v7;
}

```

## disassembly

```asm
0x1400b351c  mov     [rsp-28h+arg_10], rbx
0x1400b3521  mov     [rsp-28h+arg_18], rsi
0x1400b3526  push    rbp
0x1400b3527  push    rdi
0x1400b3528  push    r12
0x1400b352a  push    r14
0x1400b352c  push    r15
0x1400b352e  mov     rbp, rsp
0x1400b3531  sub     rsp, 80h
0x1400b3538  mov     rax, cs:__security_cookie
0x1400b353f  xor     rax, rsp
0x1400b3542  mov     [rbp+var_8], rax
0x1400b3546  xor     eax, eax
0x1400b3548  lea     r14, [rcx+10h]
0x1400b354c  mov     [rbp+var_10], rax
0x1400b3550  xor     r15b, r15b
0x1400b3553  mov     [rbp+var_38], rax
0x1400b3557  xorps   xmm0, xmm0
0x1400b355a  mov     [rbp+var_40], rax
0x1400b355e  mov     rsi, rdx
0x1400b3561  mov     eax, [r14]
0x1400b3564  mov     rbx, rcx
0x1400b3567  movups  [rbp+var_20], xmm0
0x1400b356b  bt      rax, 9
0x1400b3570  jnb     short loc_1400B3598
0x1400b3572  mov     edi, 0C037002Eh
0x1400b3577  mov     r9d, edi
0x1400b357a  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b3581  mov     r8d, 0C97h
0x1400b3587  lea     rcx, aVsmmphustorehv; "VsmmPhuStoreHvPartitionPersist"
0x1400b358e  call    VidTraceErrorStatusInternal0
0x1400b3593  jmp     loc_1400B37A1
0x1400b3598  mov     rcx, [rcx+21C8h]
0x1400b359f  mov     edx, 90h
0x1400b35a4  mov     r8d, 1
0x1400b35aa  call    VsmmPhuStorepSerializationChargeIncrease
0x1400b35af  mov     edi, eax
0x1400b35b1  test    eax, eax
0x1400b35b3  jns     short loc_1400B35D6
0x1400b35b5  mov     r9d, eax
0x1400b35b8  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b35bf  mov     r8d, 0CA1h
0x1400b35c5  lea     rcx, aVsmmphustorehv; "VsmmPhuStoreHvPartitionPersist"
0x1400b35cc  call    VidTraceErrorStatusInternal0
0x1400b35d1  jmp     loc_1400B37A1
0x1400b35d6  xor     eax, eax
0x1400b35d8  xorps   xmm0, xmm0
0x1400b35db  movups  [rbp+var_20], xmm0
0x1400b35df  mov     [rbp+var_10], rax
0x1400b35e3  xor     dil, dil
0x1400b35e6  mov     r15b, 1
0x1400b35e9  mov     rcx, [rbx+288h]
0x1400b35f0  lea     r8, [rbp+var_38]
0x1400b35f4  movzx   edx, dil
0x1400b35f8  add     edx, 6000Ah
0x1400b35fe  call    cs:__imp_WinHvGetPartitionProperty
0x1400b3605  nop     dword ptr [rax+rax+00h]
0x1400b360a  mov     rcx, [rbp+var_38]
0x1400b360e  movzx   eax, dil
0x1400b3612  not     rcx
0x1400b3615  inc     dil
0x1400b3618  mov     qword ptr [rbp+rax*8+var_20], rcx
0x1400b361d  cmp     dil, 2
0x1400b3621  jb      short loc_1400B35E9
0x1400b3623  mov     rcx, [rbx+288h]
0x1400b362a  lea     r8, [rbp+var_30]
0x1400b362e  mov     edx, 60002h
0x1400b3633  mov     [rbp+var_30], 0
0x1400b363b  call    cs:__imp_WinHvGetPartitionProperty
0x1400b3642  nop     dword ptr [rax+rax+00h]
0x1400b3647  mov     rax, [rbp+var_30]
0x1400b364b  not     rax
0x1400b364e  mov     [rbp+var_10], rax
0x1400b3652  mov     eax, [rbx+21C0h]
0x1400b3658  test    al, 2
0x1400b365a  jz      loc_1400B3721
0x1400b3660  test    al, 4
0x1400b3662  jz      short loc_1400B369F
0x1400b3664  mov     rcx, rbx; P
0x1400b3667  call    VsmmPhuStorepHvPartitionMirrorPrep
0x1400b366c  mov     edi, eax
0x1400b366e  test    eax, eax
0x1400b3670  jns     short loc_1400B3693
0x1400b3672  mov     r9d, eax
0x1400b3675  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b367c  mov     r8d, 0CCCh
0x1400b3682  lea     rcx, aVsmmphustorehv; "VsmmPhuStoreHvPartitionPersist"
0x1400b3689  call    VidTraceErrorStatusInternal0
0x1400b368e  jmp     loc_1400B37A1
0x1400b3693  mov     rdi, [rbx+288h]
0x1400b369a  jmp     loc_1400B37E1
0x1400b369f  movzx   ecx, byte ptr [rbx+839h]
0x1400b36a6  lea     rax, VidHvMemLowMemPolicyCallbackRemote
0x1400b36ad  mov     r9d, [rbx+2A8h]
0x1400b36b4  mov     r8d, ecx
0x1400b36b7  mov     rdx, [rbx+2A0h]
0x1400b36be  bts     r8d, 1Fh
0x1400b36c3  test    byte ptr [r14], 80h
0x1400b36c7  mov     [rsp+80h+var_48], rbx
0x1400b36cc  mov     [rsp+80h+var_50], rax
0x1400b36d1  cmovnz  r8d, ecx
0x1400b36d5  mov     rcx, [rbx+288h]
0x1400b36dc  lea     rax, [rbp+var_40]
0x1400b36e0  mov     [rsp+80h+var_58], rax
0x1400b36e5  lea     rax, [rbp+var_20]
0x1400b36e9  mov     [rsp+80h+var_60], rax
0x1400b36ee  call    cs:__imp_WinHvCreatePartitionRemote
0x1400b36f5  nop     dword ptr [rax+rax+00h]
0x1400b36fa  mov     edi, eax
0x1400b36fc  test    eax, eax
0x1400b36fe  jns     short loc_1400B3721
0x1400b3700  mov     r9d, eax
0x1400b3703  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b370a  mov     r8d, 0CEAh
0x1400b3710  lea     rcx, aVsmmphustorehv; "VsmmPhuStoreHvPartitionPersist"
0x1400b3717  call    VidTraceErrorStatusInternal0
0x1400b371c  jmp     loc_1400B37A1
0x1400b3721  xor     edx, edx
0x1400b3723  mov     [rsp+80h+var_58], 0
0x1400b372c  lea     r9, [rbp+var_28]
0x1400b3730  mov     [rbp+var_28], 0
0x1400b3738  xor     r8d, r8d
0x1400b373b  mov     dword ptr [rsp+80h+var_60], 8
0x1400b3743  lea     ecx, [rdx+0Eh]
0x1400b3746  call    cs:__imp_WinHvGetSystemInformation
0x1400b374d  nop     dword ptr [rax+rax+00h]
0x1400b3752  test    eax, eax
0x1400b3754  js      loc_1400B37DD
0x1400b375a  cmp     [rbp+var_28], 1
0x1400b375f  jnz     short loc_1400B37DD
0x1400b3761  mov     rcx, [rbx+288h]
0x1400b3768  mov     edx, 5001Fh
0x1400b376d  mov     r8d, 2
0x1400b3773  call    cs:__imp_WinHvSetPartitionProperty
0x1400b377a  nop     dword ptr [rax+rax+00h]
0x1400b377f  mov     edi, eax
0x1400b3781  test    eax, eax
0x1400b3783  jns     short loc_1400B37DD
0x1400b3785  mov     r9d, eax
0x1400b3788  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b378f  mov     r8d, 0D0Ah
0x1400b3795  lea     rcx, aVsmmphustorehv; "VsmmPhuStoreHvPartitionPersist"
0x1400b379c  call    VidTraceErrorStatusInternal0
0x1400b37a1  cmp     [rbp+var_40], 0
0x1400b37a6  jz      short loc_1400B37C5
0x1400b37a8  mov     eax, [rbx+21C0h]
0x1400b37ae  test    al, 4
0x1400b37b0  jnz     short loc_1400B37C5
0x1400b37b2  mov     rcx, [rbx+288h]
0x1400b37b9  call    cs:__imp_WinHvDeletePartitionRemote
0x1400b37c0  nop     dword ptr [rax+rax+00h]
0x1400b37c5  test    r15b, r15b
0x1400b37c8  jz      short loc_1400B3840
0x1400b37ca  mov     rcx, [rbx+21C8h]
0x1400b37d1  mov     edx, 90h
0x1400b37d6  call    VsmmPhuStorepSerializationChargeDecrease
0x1400b37db  jmp     short loc_1400B3840
0x1400b37dd  mov     rdi, [rbp+var_40]
0x1400b37e1  xor     edx, edx; Val
0x1400b37e3  mov     rcx, rsi; void *
0x1400b37e6  lea     r8d, [rdx+70h]; Size
0x1400b37ea  call    memset
0x1400b37ef  mov     rax, [rbx+2A0h]
0x1400b37f6  lea     rcx, [rbp+var_20]
0x1400b37fa  mov     [rsi], rax
0x1400b37fd  mov     rdx, rsi
0x1400b3800  mov     eax, [rbx+2A8h]
0x1400b3806  mov     [rsi+8], eax
0x1400b3809  call    VsmmPhuStoreCreationPropertiesSerialize
0x1400b380e  mov     edx, [rbx+0C80h]
0x1400b3814  lea     r8, [rsi+28h]
0x1400b3818  mov     [rsi+20h], edx
0x1400b381b  mov     rcx, r14
0x1400b381e  lea     rdx, [rbx+28h]
0x1400b3822  call    VsmmPhuStoreHvPartitionMakeInvariantFlags
0x1400b3827  mov     [rbx+2240h], rdi
0x1400b382e  xor     edi, edi
0x1400b3830  mov     word ptr [rbx+2239h], 101h
0x1400b3839  mov     [rbx+2238h], r15b
0x1400b3840  mov     eax, edi
0x1400b3842  mov     rcx, [rbp+var_8]
0x1400b3846  xor     rcx, rsp; StackCookie
0x1400b3849  call    __security_check_cookie
0x1400b384e  lea     r11, [rsp+80h+var_s0]
0x1400b3856  mov     rbx, [r11+40h]
0x1400b385a  mov     rsi, [r11+48h]
0x1400b385e  mov     rsp, r11
0x1400b3861  pop     r15
0x1400b3863  pop     r14
0x1400b3865  pop     r12
0x1400b3867  pop     rdi
0x1400b3868  pop     rbp
0x1400b3869  retn
```
