# Bulk_CompleteTransfers

- ea: `0x140027b5c`
- end: `0x140027fc5`
- name: `Bulk_CompleteTransfers`
- size: `1129`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140027988`

## callees

- `0x140009c48`
- `0x14000c9b0`
- `0x14000d190`
- `0x140014d30`
- `0x140027b5c`
- `0x14002e6b0`
- `0x140033854`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140027f23`
- `ntoskrnl!IoFreeMdl` at `0x140027f23`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027c1c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027dbf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027c1c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027dbf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027bae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027c36`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027bae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027c36`

## pseudocode

```c
_QWORD **__fastcall Bulk_CompleteTransfers(__int64 a1, __int64 ****a2)
{
  KSPIN_LOCK *v3; // r12
  __int64 ***v5; // rbx
  __int64 **v6; // rax
  __int64 NextStage; // r14
  _QWORD *v8; // rax
  __int64 v9; // rdx
  int v10; // r8d
  __int64 **v11; // rcx
  int v12; // eax
  __int64 ****v13; // rax
  _QWORD *v14; // rax
  __int64 *v15; // rdx
  __int64 *v16; // rax
  __int64 *v17; // rdx
  __int64 *v18; // rax
  _QWORD **result; // rax
  __int64 ***v20; // rbx
  __int64 ****v21; // rax
  __int64 **v22; // rdx
  struct _MDL *v23; // rcx
  __int64 **v24; // r8
  __int64 v25; // rdx
  int v26; // r8d
  _QWORD *v27; // [rsp+50h] [rbp-30h] BYREF
  __int64 ***v28; // [rsp+58h] [rbp-28h]
  __int64 *v29; // [rsp+60h] [rbp-20h] BYREF
  __int64 **v30; // [rsp+68h] [rbp-18h]
  __int64 *v31; // [rsp+70h] [rbp-10h] BYREF
  __int64 **v32; // [rsp+78h] [rbp-8h]

  v30 = &v29;
  v3 = (KSPIN_LOCK *)(a1 + 96);
  v29 = (__int64 *)&v29;
  v32 = &v31;
  v31 = (__int64 *)&v31;
  v28 = (__int64 ***)&v27;
  v27 = &v27;
  *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  while ( 1 )
  {
    v5 = *a2;
    if ( *a2 == (__int64 ***)a2 )
      break;
    if ( v5[1] != (__int64 **)a2 )
      goto LABEL_54;
    v6 = *v5;
    if ( (*v5)[1] != (__int64 *)v5 )
      goto LABEL_54;
    *a2 = (__int64 ***)v6;
    v6[1] = (__int64 *)a2;
    v5[1] = (__int64 **)v5;
    *v5 = (__int64 **)v5;
    *((_BYTE *)v5 + 133) = *((_BYTE *)v5 + 132);
    *((_BYTE *)v5 + 134) = *((_BYTE *)v5 + 130);
    while ( 1 )
    {
      NextStage = StageQueue_ForwardScanGetNextStage(v5 + 16);
      if ( !NextStage )
        break;
      KeReleaseSpinLock(v3, *(_BYTE *)(a1 + 104));
      Bulk_Stage_FreeScatterGatherList(a1, NextStage);
      *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc(v3);
      Bulk_Stage_Release(a1, NextStage);
      ++*((_DWORD *)v5 + 29);
      if ( *(_BYTE *)(*(_QWORD *)(a1 + 40) + 1044LL) == 1 )
        _InterlockedDecrement((volatile signed __int32 *)(a1 + 356));
      else
        --*(_DWORD *)(a1 + 356);
    }
    if ( *((_DWORD *)v5 + 16) == 3 )
    {
      v8 = v30;
      if ( *v30 != (__int64 *)&v29 )
        goto LABEL_54;
      v5[1] = v30;
      *v5 = &v29;
      *v8 = v5;
      v30 = (__int64 **)v5;
    }
    else if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 **))(WdfFunctions_01033 + 2048))(
                WdfDriverGlobals,
                v5[3]) >= 0 )
    {
      v12 = *((_DWORD *)v5 + 17);
      *((_DWORD *)v5 + 16) = 0;
      if ( v12 == 1 || v12 == 28 )
      {
        v14 = v32;
        if ( *v32 != (__int64 *)&v31 )
          goto LABEL_54;
        v5[1] = v32;
        *v5 = &v31;
        *v14 = v5;
        v32 = (__int64 **)v5;
      }
      else
      {
        v13 = (__int64 ****)v28;
        if ( *v28 != &v27 )
          goto LABEL_54;
        v5[1] = (__int64 **)v28;
        *v5 = &v27;
        *v13 = v5;
        v28 = v5;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v9 = *(_QWORD *)(a1 + 48);
        v10 = *(unsigned __int8 *)(v9 + 143);
        LOBYTE(v9) = 4;
        WPP_RECORDER_SF_DDDqd(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL), v9, v10, 14);
      }
      *((_DWORD *)v5 + 16) = 2;
      v11 = *(__int64 ***)(a1 + 400);
      if ( *v11 != (__int64 *)(a1 + 392) )
LABEL_54:
        __fastfail(3u);
      *v5 = (__int64 **)(a1 + 392);
      v5[1] = v11;
      *v11 = (__int64 *)v5;
      *(_QWORD *)(a1 + 400) = v5;
    }
  }
  KeReleaseSpinLock(v3, *(_BYTE *)(a1 + 104));
  while ( 1 )
  {
    v15 = v29;
    if ( v29 == (__int64 *)&v29 )
      break;
    if ( (__int64 **)v29[1] != &v29 )
      goto LABEL_54;
    v16 = (__int64 *)*v29;
    if ( *(__int64 **)(*v29 + 8) != v29 )
      goto LABEL_54;
    v29 = (__int64 *)*v29;
    v16[1] = (__int64)&v29;
    v15[1] = (__int64)v15;
    *v15 = (__int64)v15;
    if ( *(_DWORD *)(a1 + 64) && !*((_DWORD *)v15 + 17) )
      *((_DWORD *)v15 + 17) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 144LL) + 24LL);
    Bulk_Transfer_Complete(a1, v15, 3221291008LL);
  }
  while ( 1 )
  {
    v17 = v31;
    if ( v31 == (__int64 *)&v31 )
      break;
    if ( (__int64 **)v31[1] != &v31 )
      goto LABEL_54;
    v18 = (__int64 *)*v31;
    if ( *(__int64 **)(*v31 + 8) != v31 )
      goto LABEL_54;
    v31 = (__int64 *)*v31;
    v18[1] = (__int64)&v31;
    v17[1] = (__int64)v17;
    *v17 = (__int64)v17;
    Bulk_Transfer_Complete(a1, v17, 0xFFFFFFFFLL);
  }
  while ( 1 )
  {
    result = &v27;
    if ( v27 == &v27 )
      return result;
    v20 = v28;
    if ( *v28 != &v27 )
      goto LABEL_54;
    v21 = (__int64 ****)v28[1];
    if ( *v21 != v28 )
      goto LABEL_54;
    v28 = (__int64 ***)v28[1];
    *v21 = (__int64 ***)&v27;
    v20[1] = (__int64 **)v20;
    *v20 = (__int64 **)v20;
    v22 = v20[12];
    *((_DWORD *)v20 + 28) = *((_DWORD *)v20 + 27);
    if ( v22 )
    {
      TR_ReleaseDoubleBuffer(a1);
      v20[12] = 0;
    }
    v23 = (struct _MDL *)v20[10];
    if ( v23 )
    {
      if ( (v24 = v20[6], *((_WORD *)v24 + 1) != 8)
        && *((_WORD *)v24 + 1) != 9
        && *((_WORD *)v24 + 1) != 10
        && *((_WORD *)v24 + 1) != 50
        && *((_WORD *)v24 + 1) != 55
        && *((_WORD *)v24 + 1) != 56
        && (unsigned int)*((unsigned __int16 *)v24 + 1) - 57 < 2
        || v23 != (struct _MDL *)v24[6] )
      {
        if ( v23 != (struct _MDL *)v20[7][15] )
        {
          IoFreeMdl(v23);
          v20[10] = 0;
        }
      }
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 **))(WdfFunctions_01033 + 2264))(WdfDriverGlobals, v20[3]);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v25 = *(_QWORD *)(a1 + 48);
      v26 = *(unsigned __int8 *)(v25 + 143);
      LOBYTE(v25) = 4;
      WPP_RECORDER_SF_DDDqd(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL), v25, v26, 15);
    }
  }
}

```

## disassembly

```asm
0x140027b5c  push    rbp
0x140027b5e  push    rbx
0x140027b5f  push    rsi
0x140027b60  push    rdi
0x140027b61  push    r12
0x140027b63  push    r14
0x140027b65  push    r15
0x140027b67  mov     rbp, rsp
0x140027b6a  sub     rsp, 80h
0x140027b71  lea     rax, [rbp+var_20]
0x140027b75  mov     rdi, rcx
0x140027b78  mov     [rbp+var_18], rax
0x140027b7c  lea     r12, [rcx+60h]
0x140027b80  lea     rax, [rbp+var_20]
0x140027b84  mov     rcx, r12; SpinLock
0x140027b87  mov     [rbp+var_20], rax
0x140027b8b  mov     rsi, rdx
0x140027b8e  lea     rax, [rbp+var_10]
0x140027b92  mov     [rbp+var_8], rax
0x140027b96  lea     rax, [rbp+var_10]
0x140027b9a  mov     [rbp+var_10], rax
0x140027b9e  lea     rax, [rbp+var_30]
0x140027ba2  mov     [rbp+var_28], rax
0x140027ba6  lea     rax, [rbp+var_30]
0x140027baa  mov     [rbp+var_30], rax
0x140027bae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140027bb5  nop     dword ptr [rax+rax+00h]
0x140027bba  mov     [rdi+68h], al
0x140027bbd  lea     r14, WPP_RECORDER_INITIALIZED
0x140027bc4  mov     rbx, [rsi]
0x140027bc7  cmp     rbx, rsi
0x140027bca  jz      loc_140027DB9
0x140027bd0  cmp     [rbx+8], rsi
0x140027bd4  jnz     loc_140027FAB
0x140027bda  mov     rax, [rbx]
0x140027bdd  cmp     [rax+8], rbx
0x140027be1  jnz     loc_140027FAB
0x140027be7  mov     [rsi], rax
0x140027bea  lea     r15, [rbx+80h]
0x140027bf1  mov     [rax+8], rsi
0x140027bf5  mov     [rbx+8], rbx
0x140027bf9  mov     [rbx], rbx
0x140027bfc  mov     al, [rbx+84h]
0x140027c02  mov     [rbx+85h], al
0x140027c08  mov     al, [rbx+82h]
0x140027c0e  mov     [rbx+86h], al
0x140027c14  jmp     short loc_140027C6F
0x140027c16  mov     dl, [rdi+68h]; NewIrql
0x140027c19  mov     rcx, r12; SpinLock
0x140027c1c  call    cs:__imp_KeReleaseSpinLock
0x140027c23  nop     dword ptr [rax+rax+00h]
0x140027c28  mov     rdx, r14
0x140027c2b  mov     rcx, rdi
0x140027c2e  call    Bulk_Stage_FreeScatterGatherList
0x140027c33  mov     rcx, r12; SpinLock
0x140027c36  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140027c3d  nop     dword ptr [rax+rax+00h]
0x140027c42  mov     rdx, r14
0x140027c45  mov     rcx, rdi
0x140027c48  mov     [rdi+68h], al
0x140027c4b  call    Bulk_Stage_Release
0x140027c50  inc     dword ptr [rbx+74h]
0x140027c53  mov     rax, [rdi+28h]
0x140027c57  cmp     byte ptr [rax+414h], 1
0x140027c5e  jnz     short loc_140027C69
0x140027c60  lock dec dword ptr [rdi+164h]
0x140027c67  jmp     short loc_140027C6F
0x140027c69  dec     dword ptr [rdi+164h]
0x140027c6f  mov     rcx, r15
0x140027c72  call    StageQueue_ForwardScanGetNextStage
0x140027c77  mov     r14, rax
0x140027c7a  test    rax, rax
0x140027c7d  jnz     short loc_140027C16
0x140027c7f  cmp     dword ptr [rbx+40h], 3
0x140027c83  jnz     short loc_140027CAD
0x140027c85  mov     rax, [rbp+var_18]
0x140027c89  lea     rcx, [rbp+var_20]
0x140027c8d  cmp     [rax], rcx
0x140027c90  jnz     loc_140027FAB
0x140027c96  mov     [rbx+8], rax
0x140027c9a  lea     rcx, [rbp+var_20]
0x140027c9e  mov     [rbx], rcx
0x140027ca1  mov     [rax], rbx
0x140027ca4  mov     [rbp+var_18], rbx
0x140027ca8  jmp     loc_140027BBD
0x140027cad  mov     rax, cs:WdfFunctions_01033
0x140027cb4  mov     rdx, [rbx+18h]
0x140027cb8  mov     rcx, cs:WdfDriverGlobals
0x140027cbf  mov     rax, [rax+800h]
0x140027cc6  call    _guard_dispatch_icall
0x140027ccb  test    eax, eax
0x140027ccd  jns     loc_140027D55
0x140027cd3  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140027cda  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140027ce1  jz      short loc_140027D27
0x140027ce3  mov     rcx, [rdi+38h]
0x140027ce7  mov     r9d, 0Eh
0x140027ced  mov     rdx, [rdi+30h]
0x140027cf1  mov     [rsp+80h+var_38], eax
0x140027cf5  mov     rax, [rbx+18h]
0x140027cf9  mov     [rsp+80h+var_40], rax
0x140027cfe  mov     eax, [rdi+40h]
0x140027d01  movzx   r8d, byte ptr [rdx+8Fh]
0x140027d09  mov     dl, 4
0x140027d0b  mov     [rsp+80h+var_48], eax
0x140027d0f  mov     eax, [rcx+98h]
0x140027d15  mov     rcx, [rcx+50h]
0x140027d19  mov     [rsp+80h+var_50], eax
0x140027d1d  mov     [rsp+80h+var_58], r8d
0x140027d22  call    WPP_RECORDER_SF_DDDqd
0x140027d27  lea     rax, [rdi+188h]
0x140027d2e  mov     dword ptr [rbx+40h], 2
0x140027d35  mov     rcx, [rax+8]
0x140027d39  cmp     [rcx], rax
0x140027d3c  jnz     loc_140027FAB
0x140027d42  mov     [rbx], rax
0x140027d45  mov     [rbx+8], rcx
0x140027d49  mov     [rcx], rbx
0x140027d4c  mov     [rax+8], rbx
0x140027d50  jmp     loc_140027BC4
0x140027d55  mov     eax, [rbx+44h]
0x140027d58  mov     dword ptr [rbx+40h], 0
0x140027d5f  cmp     eax, 1
0x140027d62  jz      short loc_140027D91
0x140027d64  cmp     eax, 1Ch
0x140027d67  jz      short loc_140027D91
0x140027d69  mov     rax, [rbp+var_28]
0x140027d6d  lea     rcx, [rbp+var_30]
0x140027d71  cmp     [rax], rcx
0x140027d74  jnz     loc_140027FAB
0x140027d7a  mov     [rbx+8], rax
0x140027d7e  lea     rcx, [rbp+var_30]
0x140027d82  mov     [rbx], rcx
0x140027d85  mov     [rax], rbx
0x140027d88  mov     [rbp+var_28], rbx
0x140027d8c  jmp     loc_140027BBD
0x140027d91  mov     rax, [rbp+var_8]
0x140027d95  lea     rcx, [rbp+var_10]
0x140027d99  cmp     [rax], rcx
0x140027d9c  jnz     loc_140027FAB
0x140027da2  mov     [rbx+8], rax
0x140027da6  lea     rcx, [rbp+var_10]
0x140027daa  mov     [rbx], rcx
0x140027dad  mov     [rax], rbx
0x140027db0  mov     [rbp+var_8], rbx
0x140027db4  jmp     loc_140027BBD
0x140027db9  mov     dl, [rdi+68h]; NewIrql
0x140027dbc  mov     rcx, r12; SpinLock
0x140027dbf  call    cs:__imp_KeReleaseSpinLock
0x140027dc6  nop     dword ptr [rax+rax+00h]
0x140027dcb  mov     rdx, [rbp+var_20]
0x140027dcf  lea     rax, [rbp+var_20]
0x140027dd3  cmp     rdx, rax
0x140027dd6  jz      short loc_140027E33
0x140027dd8  lea     rax, [rbp+var_20]
0x140027ddc  cmp     [rdx+8], rax
0x140027de0  jnz     loc_140027FAB
0x140027de6  mov     rax, [rdx]
0x140027de9  cmp     [rax+8], rdx
0x140027ded  jnz     loc_140027FAB
0x140027df3  mov     [rbp+var_20], rax
0x140027df7  lea     rcx, [rbp+var_20]
0x140027dfb  mov     [rax+8], rcx
0x140027dff  mov     [rdx+8], rdx
0x140027e03  mov     [rdx], rdx
0x140027e06  cmp     dword ptr [rdi+40h], 0
0x140027e0a  jz      short loc_140027E23
0x140027e0c  cmp     dword ptr [rdx+44h], 0
0x140027e10  jnz     short loc_140027E23
0x140027e12  mov     rax, [rdi+38h]
0x140027e16  mov     rcx, [rax+90h]
0x140027e1d  mov     eax, [rcx+18h]
0x140027e20  mov     [rdx+44h], eax
0x140027e23  mov     r8d, 0C0010000h
0x140027e29  mov     rcx, rdi
0x140027e2c  call    Bulk_Transfer_Complete
0x140027e31  jmp     short loc_140027DCB
0x140027e33  mov     rdx, [rbp+var_10]
0x140027e37  lea     rax, [rbp+var_10]
0x140027e3b  cmp     rdx, rax
0x140027e3e  jz      short loc_140027E7C
0x140027e40  lea     rax, [rbp+var_10]
0x140027e44  cmp     [rdx+8], rax
0x140027e48  jnz     loc_140027FAB
0x140027e4e  mov     rax, [rdx]
0x140027e51  cmp     [rax+8], rdx
0x140027e55  jnz     loc_140027FAB
0x140027e5b  mov     [rbp+var_10], rax
0x140027e5f  lea     rcx, [rbp+var_10]
0x140027e63  mov     [rax+8], rcx
0x140027e67  or      r8d, 0FFFFFFFFh
0x140027e6b  mov     rcx, rdi
0x140027e6e  mov     [rdx+8], rdx
0x140027e72  mov     [rdx], rdx
0x140027e75  call    Bulk_Transfer_Complete
0x140027e7a  jmp     short loc_140027E33
0x140027e7c  lea     rax, [rbp+var_30]
0x140027e80  cmp     [rbp+var_30], rax
0x140027e84  jz      loc_140027FB2
0x140027e8a  mov     rbx, [rbp+var_28]
0x140027e8e  lea     rax, [rbp+var_30]
0x140027e92  cmp     [rbx], rax
0x140027e95  jnz     loc_140027FAB
0x140027e9b  mov     rax, [rbx+8]
0x140027e9f  cmp     [rax], rbx
0x140027ea2  jnz     loc_140027FAB
0x140027ea8  mov     [rbp+var_28], rax
0x140027eac  lea     rcx, [rbp+var_30]
0x140027eb0  mov     [rax], rcx
0x140027eb3  mov     [rbx+8], rbx
0x140027eb7  mov     [rbx], rbx
0x140027eba  mov     rdx, [rbx+60h]
0x140027ebe  mov     eax, [rbx+6Ch]
0x140027ec1  mov     [rbx+70h], eax
0x140027ec4  test    rdx, rdx
0x140027ec7  jz      short loc_140027ED9
0x140027ec9  mov     rcx, rdi
0x140027ecc  call    TR_ReleaseDoubleBuffer
0x140027ed1  mov     qword ptr [rbx+60h], 0
0x140027ed9  mov     rcx, [rbx+50h]; Mdl
0x140027edd  test    rcx, rcx
0x140027ee0  jz      short loc_140027F37
0x140027ee2  mov     r8, [rbx+30h]
0x140027ee6  movzx   edx, word ptr [r8+2]
0x140027eeb  sub     edx, 8
0x140027eee  jz      short loc_140027F13
0x140027ef0  sub     edx, 1
0x140027ef3  jz      short loc_140027F13
0x140027ef5  sub     edx, 1
0x140027ef8  jz      short loc_140027F13
0x140027efa  sub     edx, 28h ; '('
0x140027efd  jz      short loc_140027F13
0x140027eff  sub     edx, 5
0x140027f02  jz      short loc_140027F13
0x140027f04  sub     edx, 1
0x140027f07  jz      short loc_140027F13
0x140027f09  sub     edx, 1
0x140027f0c  jz      short loc_140027F19
0x140027f0e  cmp     edx, 1
0x140027f11  jz      short loc_140027F19
0x140027f13  cmp     rcx, [r8+30h]
0x140027f17  jz      short loc_140027F37
0x140027f19  mov     rax, [rbx+38h]
0x140027f1d  cmp     rcx, [rax+78h]
0x140027f21  jz      short loc_140027F37
0x140027f23  call    cs:__imp_IoFreeMdl
0x140027f2a  nop     dword ptr [rax+rax+00h]
0x140027f2f  mov     qword ptr [rbx+50h], 0
0x140027f37  mov     rax, cs:WdfFunctions_01033
0x140027f3e  mov     rdx, [rbx+18h]
0x140027f42  mov     rcx, cs:WdfDriverGlobals
0x140027f49  mov     rax, [rax+8D8h]
0x140027f50  call    _guard_dispatch_icall
0x140027f55  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140027f5c  jz      loc_140027E7C
0x140027f62  mov     rcx, [rdi+38h]
0x140027f66  mov     r9d, 0Fh
0x140027f6c  mov     rdx, [rdi+30h]
0x140027f70  mov     [rsp+80h+var_38], eax
0x140027f74  mov     rax, [rbx+18h]
0x140027f78  mov     [rsp+80h+var_40], rax
0x140027f7d  mov     eax, [rdi+40h]
0x140027f80  movzx   r8d, byte ptr [rdx+8Fh]
0x140027f88  mov     dl, 4
0x140027f8a  mov     [rsp+80h+var_48], eax
0x140027f8e  mov     eax, [rcx+98h]
0x140027f94  mov     rcx, [rcx+50h]
0x140027f98  mov     [rsp+80h+var_50], eax
0x140027f9c  mov     [rsp+80h+var_58], r8d
0x140027fa1  call    WPP_RECORDER_SF_DDDqd
0x140027fa6  jmp     loc_140027E7C
0x140027fab  mov     ecx, 3
0x140027fb0  int     29h; Win8: RtlFailFast(ecx)
0x140027fb2  add     rsp, 80h
0x140027fb9  pop     r15
0x140027fbb  pop     r14
0x140027fbd  pop     r12
0x140027fbf  pop     rdi
0x140027fc0  pop     rsi
0x140027fc1  pop     rbx
0x140027fc2  pop     rbp
0x140027fc3  retn
```
