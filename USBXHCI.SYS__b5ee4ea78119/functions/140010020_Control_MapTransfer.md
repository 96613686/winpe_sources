# Control_MapTransfer

- ea: `0x140010020`
- end: `0x140010622`
- name: `Control_MapTransfer`
- size: `1538`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000f9f0`
- `0x140032f80`

## callees

- `0x140002568`
- `0x140006438`
- `0x140006810`
- `0x14000c678`
- `0x14000ea20`
- `0x140010020`
- `0x140026550`
- `0x1400283c8`
- `0x14004c834`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14001037b`
- `ntoskrnl!IoAllocateMdl` at `0x14001037b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010398`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010398`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010354`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010354`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400100f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001026d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400103db`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400100f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001026d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400103db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400100a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010233`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400100a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010233`

## pseudocode

```c
void __fastcall Control_MapTransfer(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v3; // edx
  __int64 v4; // r8
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rsi
  __int64 v8; // rdx
  int v9; // ecx
  __int64 v10; // rdi
  int v11; // ecx
  __int64 v12; // rsi
  __int64 v13; // rax
  __int64 v14; // r11
  int v15; // ecx
  unsigned int v16; // r8d
  unsigned int v17; // r10d
  int v18; // edi
  __int64 v19; // rcx
  PVOID v20; // rax
  int v21; // r9d
  int v22; // edx
  KIRQL v23; // al
  __int64 v24; // rdx
  int v25; // ecx
  __int64 v26; // rax
  int v27; // edx
  PMDL Mdl; // rax
  KIRQL v29; // dl
  __int64 v30; // rcx
  __int64 v31; // rax
  int v32; // edx
  __int64 v33; // r10
  __int64 v34; // r9
  __int64 v35; // rdx
  int v36; // edx

  v1 = *(_QWORD *)(a1 + 360);
  v3 = *(_DWORD *)(v1 + 104);
  if ( !v3 )
  {
    v9 = 0;
    goto LABEL_15;
  }
  v4 = *(_QWORD *)(v1 + 48);
  if ( *(_BYTE *)(a1 + 328) && v3 <= 8 && (*(_DWORD *)(v4 + 32) & 1) == 0 )
  {
    v9 = 1;
    goto LABEL_15;
  }
  if ( *(_WORD *)(v4 + 2) != 56 )
  {
    switch ( *(_WORD *)(v4 + 2) )
    {
      case '9':
      case ':':
        goto LABEL_8;
      default:
        break;
    }
  }
  v5 = *(_QWORD **)(v4 + 48);
  if ( v5 && *v5 )
  {
LABEL_36:
    v9 = 3;
    goto LABEL_15;
  }
LABEL_8:
  if ( v3 > *(_DWORD *)(a1 + 24) )
    goto LABEL_36;
  *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v6 = (_QWORD *)(a1 + 224);
  v7 = *(_QWORD **)(a1 + 224);
  if ( v7 == (_QWORD *)(a1 + 224) )
  {
    v7 = (_QWORD *)CommonBuffer_AcquireBuffer(*(PVOID *)(*(_QWORD *)(a1 + 40) + 120LL));
  }
  else
  {
    if ( (_QWORD *)v7[1] != v6 || (v8 = *v7, *(_QWORD **)(*v7 + 8LL) != v7) )
      __fastfail(3u);
    *v6 = v8;
    *(_QWORD *)(v8 + 8) = v6;
    v7[1] = v7;
    *v7 = v7;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
  *(_QWORD *)(v1 + 88) = v7;
  if ( !v7 )
    goto LABEL_36;
  v9 = 2;
LABEL_15:
  *(_DWORD *)(v1 + 64) = v9;
  v10 = *(_QWORD *)(a1 + 360);
  v11 = *(_DWORD *)(v10 + 64);
  v12 = *(_QWORD *)(v10 + 48);
  if ( v11 == 2 || (v25 = v11 - 1) == 0 )
  {
    v13 = *(_QWORD *)(v12 + 40);
    if ( v13 )
    {
      *(_QWORD *)(v10 + 80) = v13;
      goto LABEL_18;
    }
    v19 = *(_QWORD *)(v12 + 48);
    if ( (*(_BYTE *)(v19 + 10) & 5) != 0 )
      v20 = *(PVOID *)(v19 + 24);
    else
      v20 = MmMapLockedPagesSpecifyCache((PMDL)v19, 0, MmCached, 0, 0, 0x40000010u);
    *(_QWORD *)(v10 + 80) = v20;
    if ( v20 )
    {
LABEL_18:
      v14 = *(_QWORD *)(a1 + 360);
      v15 = *(_DWORD *)(v14 + 64);
      if ( v15 )
      {
        v16 = *(_DWORD *)(v14 + 104);
        if ( v16 > 0x10000 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_DDqDD(
              *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
              *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL),
              v16,
              30,
              (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
              *(_BYTE *)(*(_QWORD *)(a1 + 48) + 143LL),
              *(_DWORD *)(*(_QWORD *)(a1 + 56) + 152LL),
              *(_QWORD *)(v14 + 24),
              v16,
              0);
            v18 = -1073741637;
            goto LABEL_24;
          }
LABEL_45:
          v18 = -1073741637;
          goto LABEL_24;
        }
        v17 = *(_DWORD *)(a1 + 4);
        if ( v16 > v17 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_DDqDD(
              *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
              *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL),
              v16,
              31,
              (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
              *(_BYTE *)(*(_QWORD *)(a1 + 48) + 143LL),
              *(_DWORD *)(*(_QWORD *)(a1 + 56) + 152LL),
              *(_QWORD *)(v14 + 24),
              v16,
              *(_DWORD *)(a1 + 4));
          goto LABEL_67;
        }
        if ( v16 == v17 && (*(_DWORD *)(v14 + 80) & 0xFFFLL) != 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v36 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL);
            LOBYTE(v36) = 2;
            WPP_RECORDER_SF_DDqD(
              *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
              v36,
              v16,
              32,
              (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
              *(_BYTE *)(*(_QWORD *)(a1 + 48) + 143LL),
              *(_DWORD *)(*(_QWORD *)(a1 + 56) + 152LL),
              *(_QWORD *)(v14 + 24),
              *(_DWORD *)(v14 + 104));
            v18 = -1073741670;
LABEL_24:
            if ( v18 >= 0 )
              return;
            goto LABEL_34;
          }
LABEL_67:
          v18 = -1073741670;
          goto LABEL_24;
        }
        if ( v15 == 3 && **(_QWORD **)(v14 + 72) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v27 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL);
            LOBYTE(v27) = 2;
            WPP_RECORDER_SF_DDi(
              *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
              v27,
              v16,
              33,
              (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
              *(_BYTE *)(*(_QWORD *)(a1 + 48) + 143LL),
              *(_DWORD *)(*(_QWORD *)(a1 + 56) + 152LL),
              *(_QWORD *)(v14 + 24));
          }
          goto LABEL_45;
        }
      }
      v18 = Control_Transfer_Map(a1);
      goto LABEL_24;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = 27;
LABEL_32:
      v22 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL);
      LOBYTE(v22) = 2;
      WPP_RECORDER_SF_DD(
        *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
        v22,
        14,
        v21,
        (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
        *(_BYTE *)(*(_QWORD *)(a1 + 48) + 143LL),
        *(_DWORD *)(*(_QWORD *)(a1 + 56) + 152LL));
    }
  }
  else
  {
    if ( v25 != 2 )
      goto LABEL_18;
    v26 = *(_QWORD *)(v12 + 48);
    if ( v26 )
    {
      *(_QWORD *)(v10 + 72) = v26;
      goto LABEL_18;
    }
    Mdl = IoAllocateMdl(*(PVOID *)(v12 + 40), *(_DWORD *)(v10 + 104), 0, 0, 0);
    *(_QWORD *)(v10 + 72) = Mdl;
    if ( Mdl )
      goto LABEL_50;
    if ( (*(_DWORD *)(v12 + 32) & 0x10) != 0 && *(_QWORD *)(a1 + 120) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        v32 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL);
        LOBYTE(v32) = 5;
        WPP_RECORDER_SF_DD(
          *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
          v32,
          14,
          28,
          (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
          *(_BYTE *)(*(_QWORD *)(a1 + 48) + 143LL),
          *(_DWORD *)(*(_QWORD *)(a1 + 56) + 152LL));
      }
      v33 = *(_QWORD *)(a1 + 120);
      v34 = *(unsigned int *)(v10 + 104);
      *(_QWORD *)(v10 + 72) = v33;
      v35 = *(_QWORD *)(v12 + 40);
      *(_QWORD *)v33 = 0;
      *(_DWORD *)(v33 + 40) = v34;
      *(_WORD *)(v33 + 10) = 0;
      *(_WORD *)(v33 + 8) = 8 * ((((unsigned __int64)(v35 & 0xFFF) + v34 + 4095) >> 12) + 6);
      *(_DWORD *)(v33 + 44) = v35 & 0xFFF;
      *(_QWORD *)(v33 + 32) = v35 & 0xFFFFFFFFFFFFF000uLL;
LABEL_50:
      MmBuildMdlForNonPagedPool(*(PMDL *)(v10 + 72));
      goto LABEL_18;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = 29;
      goto LABEL_32;
    }
  }
  v18 = -1073741670;
LABEL_34:
  v23 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v24 = *(_QWORD *)(a1 + 360);
  *(_BYTE *)(a1 + 104) = v23;
  *(_DWORD *)(v24 + 120) = v18;
  if ( *(_DWORD *)(a1 + 108) == 3 )
  {
    *(_DWORD *)(a1 + 108) = 2;
    Control_Transfer_CompleteCancelable(a1);
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
  }
  else
  {
    v29 = *(_BYTE *)(a1 + 104);
    *(_DWORD *)(a1 + 108) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v29);
    v30 = *(_QWORD *)(a1 + 56);
    if ( !*(_BYTE *)(v30 + 37)
      || (v31 = *(_QWORD *)(v30 + 144),
          _InterlockedIncrement((volatile signed __int32 *)(v31 + 20)) == *(_DWORD *)(v31 + 8)) )
    {
      ESM_AddEvent((PVOID)(v30 + 312));
    }
  }
}

```

## disassembly

```asm
0x140010020  mov     [rsp+arg_8], rbx
0x140010025  mov     [rsp+arg_10], rbp
0x14001002a  push    rsi
0x14001002b  push    rdi
0x14001002c  push    r14
0x14001002e  sub     rsp, 50h
0x140010032  mov     rdi, [rcx+168h]
0x140010039  mov     rbx, rcx
0x14001003c  mov     r14d, 1
0x140010042  mov     edx, [rdi+68h]
0x140010045  test    edx, edx
0x140010047  jz      loc_140010288
0x14001004d  cmp     byte ptr [rcx+148h], 0
0x140010054  mov     r8, [rdi+30h]
0x140010058  jz      short loc_14001006C
0x14001005a  cmp     edx, 8
0x14001005d  ja      short loc_14001006C
0x14001005f  mov     eax, [r8+20h]
0x140010063  test    r14b, al
0x140010066  jz      loc_1400101B3
0x14001006c  movzx   eax, word ptr [r8+2]
0x140010071  cmp     eax, 38h ; '8'
0x140010074  jz      short def_1400103C6; jumptable 00000001400103C6 default case, cases 8-56
0x140010076  add     eax, 0FFFFFFF8h; switch 51 cases
0x140010079  cmp     eax, 32h
0x14001007c  jbe     loc_1400103A9
0x140010082  mov     rax, [r8+30h]; jumptable 00000001400103C6 default case, cases 8-56
0x140010086  test    rax, rax
0x140010089  jz      short loc_140010095; jumptable 00000001400103C6 cases 57,58
0x14001008b  cmp     qword ptr [rax], 0
0x14001008f  jnz     loc_14001027E
0x140010095  cmp     edx, [rbx+18h]; jumptable 00000001400103C6 cases 57,58
0x140010098  ja      loc_14001027E
0x14001009e  lea     rcx, [rbx+60h]; SpinLock
0x1400100a2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400100a9  nop     dword ptr [rax+rax+00h]
0x1400100ae  mov     [rbx+68h], al
0x1400100b1  lea     rax, [rbx+0E0h]
0x1400100b8  mov     rsi, [rax]
0x1400100bb  cmp     rsi, rax
0x1400100be  jz      loc_140010314
0x1400100c4  cmp     [rsi+8], rax
0x1400100c8  jnz     loc_140010335
0x1400100ce  mov     rdx, [rsi]
0x1400100d1  cmp     [rdx+8], rsi
0x1400100d5  jnz     loc_140010335
0x1400100db  mov     [rax], rdx
0x1400100de  mov     [rdx+8], rax
0x1400100e2  mov     [rsi+8], rsi
0x1400100e6  mov     [rsi], rsi
0x1400100e9  movzx   edx, byte ptr [rbx+68h]; NewIrql
0x1400100ed  lea     rcx, [rbx+60h]; SpinLock
0x1400100f1  call    cs:__imp_KeReleaseSpinLock
0x1400100f8  nop     dword ptr [rax+rax+00h]
0x1400100fd  mov     [rdi+58h], rsi
0x140010101  test    rsi, rsi
0x140010104  jz      loc_14001027E
0x14001010a  mov     ecx, 2
0x14001010f  mov     [rdi+40h], ecx
0x140010112  lea     rbp, WPP_RECORDER_INITIALIZED
0x140010119  mov     rdi, [rbx+168h]
0x140010120  mov     [rsp+68h+arg_0], r15
0x140010125  lea     r15, WPP_033405c12d5f32917339b215e0870938_Traceguids
0x14001012c  mov     ecx, [rdi+40h]
0x14001012f  mov     rsi, [rdi+30h]
0x140010133  cmp     ecx, 2
0x140010136  jnz     loc_14001028F
0x14001013c  mov     rax, [rsi+28h]
0x140010140  test    rax, rax
0x140010143  jz      short loc_1400101BB
0x140010145  mov     [rdi+50h], rax
0x140010149  mov     r11, [rbx+168h]
0x140010150  mov     ecx, [r11+40h]
0x140010154  test    ecx, ecx
0x140010156  jz      short loc_140010185
0x140010158  mov     r8d, [r11+68h]
0x14001015c  cmp     r8d, 10000h
0x140010163  ja      loc_140010509
0x140010169  mov     r10d, [rbx+4]
0x14001016d  cmp     r8d, r10d
0x140010170  ja      loc_140010567
0x140010176  jz      loc_1400105BE
0x14001017c  cmp     ecx, 3
0x14001017f  jz      loc_1400102B7
0x140010185  mov     rcx, rbx
0x140010188  call    Control_Transfer_Map
0x14001018d  mov     edi, eax
0x14001018f  test    edi, edi
0x140010191  js      loc_14001022F
0x140010197  mov     r15, [rsp+68h+arg_0]
0x14001019c  mov     rbx, [rsp+68h+arg_8]
0x1400101a1  mov     rbp, [rsp+68h+arg_10]
0x1400101a9  add     rsp, 50h
0x1400101ad  pop     r14
0x1400101af  pop     rdi
0x1400101b0  pop     rsi
0x1400101b1  retn
0x1400101b3  mov     ecx, r14d
0x1400101b6  jmp     loc_14001010F
0x1400101bb  mov     rcx, [rsi+30h]; MemoryDescriptorList
0x1400101bf  test    byte ptr [rcx+0Ah], 5
0x1400101c3  jz      loc_14001033C
0x1400101c9  mov     rax, [rcx+18h]
0x1400101cd  mov     [rdi+50h], rax
0x1400101d1  test    rax, rax
0x1400101d4  jnz     loc_140010149
0x1400101da  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400101e1  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400101e8  jz      short loc_14001022A
0x1400101ea  mov     r9d, 1Bh
0x1400101f0  mov     rax, [rbx+30h]
0x1400101f4  lea     r15, WPP_033405c12d5f32917339b215e0870938_Traceguids
0x1400101fb  mov     rcx, [rbx+38h]
0x1400101ff  mov     r8d, 0Eh
0x140010205  movzx   edx, byte ptr [rax+8Fh]
0x14001020c  mov     eax, [rcx+98h]
0x140010212  mov     rcx, [rcx+50h]
0x140010216  mov     [rsp+68h+var_38], eax
0x14001021a  mov     [rsp+68h+Priority], edx
0x14001021e  mov     dl, 2
0x140010220  mov     qword ptr [rsp+68h+BugCheckOnFailure], r15
0x140010225  call    WPP_RECORDER_SF_DD
0x14001022a  mov     edi, 0C000009Ah
0x14001022f  lea     rcx, [rbx+60h]; SpinLock
0x140010233  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001023a  nop     dword ptr [rax+rax+00h]
0x14001023f  mov     rdx, [rbx+168h]
0x140010246  mov     [rbx+68h], al
0x140010249  mov     [rdx+78h], edi
0x14001024c  cmp     dword ptr [rbx+6Ch], 3
0x140010250  jnz     loc_1400103CC
0x140010256  mov     rcx, rbx
0x140010259  mov     dword ptr [rbx+6Ch], 2
0x140010260  call    Control_Transfer_CompleteCancelable
0x140010265  movzx   edx, byte ptr [rbx+68h]; NewIrql
0x140010269  lea     rcx, [rbx+60h]; SpinLock
0x14001026d  call    cs:__imp_KeReleaseSpinLock
0x140010274  nop     dword ptr [rax+rax+00h]
0x140010279  jmp     loc_140010197
0x14001027e  mov     ecx, 3
0x140010283  jmp     loc_14001010F
0x140010288  xor     ecx, ecx
0x14001028a  jmp     loc_14001010F
0x14001028f  sub     ecx, r14d
0x140010292  jz      loc_14001013C
0x140010298  cmp     ecx, 2
0x14001029b  jnz     loc_140010149
0x1400102a1  mov     rax, [rsi+30h]
0x1400102a5  test    rax, rax
0x1400102a8  jz      loc_140010365
0x1400102ae  mov     [rdi+48h], rax
0x1400102b2  jmp     loc_140010149
0x1400102b7  mov     rax, [r11+48h]
0x1400102bb  cmp     qword ptr [rax], 0
0x1400102bf  jz      loc_140010185
0x1400102c5  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x1400102cc  jz      short loc_14001030A
0x1400102ce  mov     rax, [rbx+30h]
0x1400102d2  mov     r9d, 21h ; '!'
0x1400102d8  mov     rcx, [rbx+38h]
0x1400102dc  movzx   edx, byte ptr [rax+8Fh]
0x1400102e3  mov     rax, [r11+18h]
0x1400102e7  mov     [rsp+68h+var_30], rax
0x1400102ec  mov     eax, [rcx+98h]
0x1400102f2  mov     rcx, [rcx+50h]
0x1400102f6  mov     [rsp+68h+var_38], eax
0x1400102fa  mov     [rsp+68h+Priority], edx
0x1400102fe  mov     dl, 2
0x140010300  mov     qword ptr [rsp+68h+BugCheckOnFailure], r15
0x140010305  call    WPP_RECORDER_SF_DDi
0x14001030a  mov     edi, 0C00000BBh
0x14001030f  jmp     loc_14001018F
0x140010314  mov     rcx, [rbx+28h]
0x140010318  mov     r9d, 32676E52h
0x14001031e  mov     edx, [rbx+18h]
0x140010321  mov     r8, rbx
0x140010324  mov     rcx, [rcx+78h]; Context
0x140010328  call    CommonBuffer_AcquireBuffer
0x14001032d  mov     rsi, rax
0x140010330  jmp     loc_1400100E9
0x140010335  mov     ecx, 3
0x14001033a  int     29h; Win8: RtlFailFast(ecx)
0x14001033c  mov     [rsp+68h+Priority], 40000010h; Priority
0x140010344  xor     r9d, r9d; RequestedAddress
0x140010347  mov     r8d, r14d; CacheType
0x14001034a  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140010352  xor     edx, edx; AccessMode
0x140010354  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001035b  nop     dword ptr [rax+rax+00h]
0x140010360  jmp     loc_1400101CD
0x140010365  mov     edx, [rdi+68h]; Length
0x140010368  xor     r9d, r9d; ChargeQuota
0x14001036b  mov     rcx, [rsi+28h]; VirtualAddress
0x14001036f  xor     r8d, r8d; SecondaryBuffer
0x140010372  mov     qword ptr [rsp+68h+BugCheckOnFailure], 0; Irp
0x14001037b  call    cs:__imp_IoAllocateMdl
0x140010382  nop     dword ptr [rax+rax+00h]
0x140010387  mov     [rdi+48h], rax
0x14001038b  test    rax, rax
0x14001038e  jz      loc_140010421
0x140010394  mov     rcx, [rdi+48h]; MemoryDescriptorList
0x140010398  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001039f  nop     dword ptr [rax+rax+00h]
0x1400103a4  jmp     loc_140010149
0x1400103a9  lea     r9, cs:140000000h
0x1400103b0  cdqe
0x1400103b2  movzx   eax, ds:(byte_1400646A8 - 140000000h)[r9+rax]
0x1400103bb  mov     ecx, ds:(jpt_1400103C6 - 140000000h)[r9+rax*4]
0x1400103c3  add     rcx, r9
0x1400103c6  jmp     rcx; switch jump
0x1400103cc  movzx   edx, byte ptr [rbx+68h]; NewIrql
0x1400103d0  lea     rcx, [rbx+60h]; SpinLock
0x1400103d4  mov     dword ptr [rbx+6Ch], 0
0x1400103db  call    cs:__imp_KeReleaseSpinLock
0x1400103e2  nop     dword ptr [rax+rax+00h]
0x1400103e7  mov     rcx, [rbx+38h]
0x1400103eb  cmp     byte ptr [rcx+25h], 0
0x1400103ef  jz      short loc_14001040B
0x1400103f1  mov     rax, [rcx+90h]
0x1400103f8  lock xadd [rax+14h], r14d
0x1400103fe  inc     r14d
0x140010401  cmp     r14d, [rax+8]
0x140010405  jnz     loc_140010197
0x14001040b  mov     edx, 14h
0x140010410  add     rcx, 138h; Context
0x140010417  call    ESM_AddEvent
0x14001041c  jmp     loc_140010197
0x140010421  mov     eax, [rsi+20h]
0x140010424  test    al, 10h
0x140010426  jz      loc_1400104EA
0x14001042c  cmp     qword ptr [rbx+78h], 0
0x140010431  jz      loc_1400104EA
0x140010437  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001043e  jz      short loc_140010487
0x140010440  mov     rax, cs:WPP_GLOBAL_Control
0x140010447  cmp     word ptr [rax+48h], 0
0x14001044c  jz      short loc_140010487
0x14001044e  mov     rax, [rbx+30h]
0x140010452  mov     r9d, 1Ch
0x140010458  mov     rcx, [rbx+38h]
0x14001045c  mov     r8d, 0Eh
0x140010462  movzx   edx, byte ptr [rax+8Fh]
0x140010469  mov     eax, [rcx+98h]
0x14001046f  mov     rcx, [rcx+50h]
0x140010473  mov     [rsp+68h+var_38], eax
0x140010477  mov     [rsp+68h+Priority], edx
0x14001047b  mov     dl, 5
0x14001047d  mov     qword ptr [rsp+68h+BugCheckOnFailure], r15
0x140010482  call    WPP_RECORDER_SF_DD
0x140010487  mov     r10, [rbx+78h]
0x14001048b  mov     r9d, [rdi+68h]
0x14001048f  mov     [rdi+48h], r10
0x140010493  mov     rdx, [rsi+28h]
0x140010497  mov     r8d, edx
0x14001049a  mov     qword ptr [r10], 0
0x1400104a1  mov     eax, r8d
0x1400104a4  mov     [r10+28h], r9d
0x1400104a8  and     eax, 0FFFh
0x1400104ad  lea     rcx, [r9+0FFFh]
0x1400104b4  add     rcx, rax
0x1400104b7  and     rdx, 0FFFFFFFFFFFFF000h
0x1400104be  shr     rcx, 0Ch
0x1400104c2  xor     eax, eax
0x1400104c4  add     cx, 6
0x1400104c8  mov     [r10+0Ah], ax
0x1400104cd  shl     cx, 3
0x1400104d1  and     r8d, 0FFFh
0x1400104d8  mov     [r10+8], cx
0x1400104dd  mov     [r10+2Ch], r8d
0x1400104e1  mov     [r10+20h], rdx
0x1400104e5  jmp     loc_140010394
0x1400104ea  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400104f1  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400104f8  jz      loc_14001022A
0x1400104fe  mov     r9d, 1Dh
0x140010504  jmp     loc_1400101F0
0x140010509  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140010510  jz      loc_14001030A
0x140010516  mov     rax, [rbx+30h]
0x14001051a  mov     r9d, 1Eh
0x140010520  mov     rcx, [rbx+38h]
0x140010524  mov     [rsp+68h+var_20], 10000h
0x14001052c  mov     [rsp+68h+var_28], r8d
0x140010531  movzx   edx, byte ptr [rax+8Fh]
0x140010538  mov     rax, [r11+18h]
0x14001053c  mov     [rsp+68h+var_30], rax
0x140010541  mov     eax, [rcx+98h]
0x140010547  mov     rcx, [rcx+50h]
0x14001054b  mov     [rsp+68h+var_38], eax
0x14001054f  mov     [rsp+68h+Priority], edx
0x140010553  mov     qword ptr [rsp+68h+BugCheckOnFailure], r15
0x140010558  call    WPP_RECORDER_SF_DDqDD
0x14001055d  mov     edi, 0C00000BBh
0x140010562  jmp     loc_14001018F
0x140010567  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001056e  jz      short loc_1400105B4
0x140010570  mov     rax, [rbx+30h]
0x140010574  mov     r9d, 1Fh
0x14001057a  mov     rcx, [rbx+38h]
0x14001057e  mov     [rsp+68h+var_20], r10d
  ... truncated ...
```
