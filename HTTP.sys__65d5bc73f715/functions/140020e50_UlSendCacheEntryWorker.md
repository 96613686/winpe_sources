# UlSendCacheEntryWorker

- ea: `0x140020e50`
- end: `0x140021790`
- name: `UlSendCacheEntryWorker`
- size: `2368`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a350`
- `0x14000a520`
- `0x14000e420`
- `0x140020e50`
- `0x14002186c`
- `0x140022420`
- `0x140022610`
- `0x140035a50`
- `0x1400397b0`
- `0x140039c60`
- `0x14003bf00`
- `0x1400ca7e4`
- `0x14012a480`
- `0x1401678f0`
- `0x1401c3008`
- `0x1401c37f8`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d32ac`
- `0x1401d35ac`
- `0x1401d9cac`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14002137a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021684`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002137a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021684`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400213a6`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400213a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020fbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002135e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020fbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002135e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400212b3`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400212b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020f52`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021330`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020f52`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021330`

## pseudocode

```c
__int64 __fastcall UlSendCacheEntryWorker(__int64 a1)
{
  __int64 v2; // rcx
  _QWORD *i; // rdi
  __int64 v4; // rbp
  int v5; // eax
  unsigned __int8 v6; // r12
  __int64 v7; // rdi
  __int64 *j; // rax
  int v9; // ecx
  __int64 v10; // r14
  __int64 v11; // rsi
  KIRQL v12; // al
  __int64 v13; // r9
  KIRQL v14; // r13
  __int64 v15; // r12
  __int16 v16; // cx
  bool v17; // zf
  __int64 v18; // rdi
  int v19; // r8d
  __int16 v20; // si
  __int64 v21; // r13
  int v22; // r15d
  __int64 v23; // r14
  __int64 v24; // rbx
  __int64 v25; // rdx
  int v26; // edi
  __int64 v27; // r8
  __int64 result; // rax
  unsigned int v29; // r12d
  __int64 v30; // r14
  unsigned int v31; // eax
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v33; // r9
  __int64 v34; // rdi
  __int64 v35; // rcx
  KIRQL v36; // al
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rsi
  __int64 v44; // r14
  unsigned int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // [rsp+80h] [rbp-68h]
  __int64 v49[4]; // [rsp+88h] [rbp-60h] BYREF
  char v50; // [rsp+F0h] [rbp+8h] BYREF
  unsigned __int8 v51; // [rsp+F8h] [rbp+10h] BYREF
  int v52; // [rsp+100h] [rbp+18h]
  __int64 v53; // [rsp+108h] [rbp+20h] BYREF

  v51 = 0;
  v50 = 1;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 191, WPP_173ede4a325638307373c19033e5a27a_Traceguids, a1);
  v2 = *(_QWORD *)(a1 + 48);
  for ( i = *(_QWORD **)(v2 + 616); i != (_QWORD *)(v2 + 616); i = (_QWORD *)*i )
  {
    v42 = *(_QWORD *)(a1 + 96);
    v43 = *(_QWORD *)(v42 + 24);
    v44 = v42 + 3216;
    if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v43 + 496, 8, i - 3, 0, v42 + 3216, 0);
    v45 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, _QWORD, __int64, _QWORD))(*(_QWORD *)(v43 + 504) + 136LL))(
            *(_QWORD *)(v43 + 496),
            8,
            i - 3,
            0,
            v44,
            0);
    if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v45);
    v2 = *(_QWORD *)(a1 + 48);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 96) + 1696LL) = v2;
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 24LL);
  v5 = _InterlockedIncrement((volatile signed __int32 *)(v4 + 40));
  if ( UxDebugCheckRefcount && v5 <= -1 )
    UlBugCheckEx(3u, v4 + 40, 0x21u, v5);
  if ( (*(_DWORD *)(a1 + 120) & 1) != 0 )
  {
    v6 = 1;
    v51 = 1;
  }
  else
  {
    v6 = v51;
  }
  v7 = *(_QWORD *)(a1 + 112);
  if ( v7 )
  {
    LODWORD(v7) = *(_DWORD *)(v7 + 88);
  }
  else
  {
    for ( j = *(__int64 **)(a1 + 248); j; LODWORD(v7) = v9 + v7 )
    {
      v9 = *((_DWORD *)j + 10);
      j = (__int64 *)*j;
    }
  }
  v10 = *(_QWORD *)(a1 + 96);
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
  {
    if ( v10 )
      v46 = *(_QWORD *)(v10 + 64);
    else
      v46 = 0;
    WPP_SF_qiIlqq((unsigned int)v7, v46, &v50, v10, v46, (unsigned int)v7, v6, 0, &v50);
  }
  if ( UxEnableIrqlEnforcement && KeGetCurrentIrql() )
    UlBugCheckEx(4u, 0, (ULONG_PTR)"minio\\http\\sys\\sendresponse.c", 0x15DEu);
  v11 = *(_QWORD *)(v10 + 24);
  v48 = a1 - 32;
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 640));
  ++*(_DWORD *)(v10 + 1624);
  v14 = v12;
  ++*(_DWORD *)(v11 + 336);
  if ( v50 && *(_DWORD *)(v11 + 336) >= 3u )
  {
    *(_BYTE *)(v11 + 521) = 1;
    *(_BYTE *)(v11 + 522) = v6;
    *(_BYTE *)(v11 + 523) = 1;
    v50 = 0;
  }
  LOBYTE(v13) = 1;
  UlSetBundleTimerEx(v11 + 648, 2, (unsigned int)v7, v13);
  KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 640), v14);
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1033, 82, WPP_173ede4a325638307373c19033e5a27a_Traceguids);
  v15 = a1 + 240;
  v16 = 20;
  if ( !(_DWORD)v7 )
    v15 = 0;
  v17 = (_DWORD)v7 == 0;
  v49[0] = v15;
  v18 = *(_QWORD *)(a1 + 96);
  v19 = !v17;
  v52 = v19;
  if ( v51 )
    v16 = 19;
  v20 = v16 | 0x20;
  if ( !*(_BYTE *)(a1 - 11) )
    v20 = v16;
  if ( *(_BYTE *)(v18 + 3214) )
  {
    v29 = *(_DWORD *)(a1 + 148);
    v21 = a1 + 200;
    v30 = *(_QWORD *)(a1 + 152);
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    {
      if ( v18 )
        v47 = *(_QWORD *)(v18 + 64);
      else
        v47 = 0;
      WPP_SF_qiqLqq(1033, 22, WPP_173ede4a325638307373c19033e5a27a_Traceguids, v18, v47, a1 + 160, 1, v30, a1 + 200);
    }
    v31 = UlpSanitizeResponseHeaders(v18, a1 + 160, v30, v29, a1 + 200);
    v26 = v31;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1033, 23, WPP_173ede4a325638307373c19033e5a27a_Traceguids, v31);
    if ( v26 < 0 )
    {
      v23 = v4;
LABEL_60:
      UlpCompleteSendCacheEntry(v48, (unsigned int)v26, 0);
      goto LABEL_45;
    }
    v18 = *(_QWORD *)(a1 + 96);
    LODWORD(v15) = v49[0];
    v19 = v52;
  }
  else
  {
    v21 = 0;
  }
  if ( (*(_DWORD *)(a1 + 120) & 2) == 0 )
  {
    if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
    {
      WPP_SF_q(1040, 192, WPP_173ede4a325638307373c19033e5a27a_Traceguids, *(_QWORD *)(v18 + 56));
      v19 = v52;
      v18 = *(_QWORD *)(a1 + 96);
    }
    v20 |= 0x100u;
  }
  v22 = *(_DWORD *)(a1 + 144);
  *(_OWORD *)v49 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( v18 )
      v40 = *(_QWORD *)(v18 + 64);
    else
      LODWORD(v40) = 0;
    v23 = v4;
    if ( v4 )
      v41 = *(_QWORD *)(v4 + 48);
    else
      LODWORD(v41) = 0;
    WPP_SF_qiqlLlqqiqqqq(
      v41,
      v40,
      v19,
      v4,
      v41,
      v15,
      v19,
      v22,
      v20,
      0,
      v18,
      v40,
      (char)UlpCompleteSendCacheEntry,
      a1 - 32,
      v18,
      (char)UlpSendResponseEntityBodyToExtension);
  }
  else
  {
    v23 = v4;
  }
  if ( (v20 & 1) != 0 )
  {
    v36 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v23 + 640));
    if ( *(_BYTE *)(v23 + 790) )
      v20 &= ~2u;
    else
      *(_WORD *)(v23 + 788) = 256;
    KeReleaseSpinLock((PKSPIN_LOCK)(v23 + 640), v36);
  }
  v24 = 0;
  v53 = 0;
  if ( UlHkeQosClassficationEnabled && (UlpHkeAcquireQoS(v18, &v53), (v24 = v53) != 0) )
  {
    v20 |= 0x8000u;
    v25 = v53;
  }
  else
  {
    v25 = *(_QWORD *)(v18 + 2480);
    if ( v25 )
      v20 |= 0x4000u;
  }
  if ( *(_QWORD *)(v18 + 64) )
    v49[0] = v18 + 72;
  v26 = UxTpTransmitPacket(
          (int)v23 + 976,
          v15,
          v52,
          v22,
          v20,
          0,
          (__int64)UlpCompleteSendCacheEntry,
          v48,
          v18,
          v25,
          v18,
          (__int64)UlpSendResponseEntityBodyToExtension,
          (__int64)v49,
          v21,
          0);
  if ( v24 )
    UlHkeDereferenceCalloutContext(v24, 10, v27);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 107, WPP_682cf469470432b235cb9a4961616e40_Traceguids, (unsigned int)v26);
  if ( v50 || (UlSetPostSendState(v23, &v50, &v51), v50) )
    UlResumeParsing(v23, v51);
  if ( v26 < 0 )
    goto LABEL_60;
LABEL_45:
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(v4 + 40));
  if ( UxDebugCheckRefcount && (int)result <= -1 )
    UlBugCheckEx(3u, v4 + 40, 0x21u, (int)result);
  if ( !(_DWORD)result )
  {
    CurrentProcess = IoGetCurrentProcess();
    v34 = *(_QWORD *)(v23 + 1088);
    v35 = *(_QWORD *)(v23 + 64);
    if ( UxSystemProcess == CurrentProcess )
    {
      if ( v35 || *(_QWORD *)(v23 + 80) || *(_QWORD *)(v23 + 96) )
        UlBugCheckEx(1u, v23 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
      if ( !KeGetCurrentIrql() )
      {
        *(_OWORD *)v49 = 0;
        if ( v34 != -1 )
        {
          LOBYTE(v49[0]) = 1;
          v39 = PsAttachSiloToCurrentThread(v34);
          v49[1] = v39;
          if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
            WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v39, v34);
        }
        UlFreeHttpConnection(v23 + 64, v37, v38, v33);
        result = UxPodDetachThread(v49);
        goto LABEL_47;
      }
    }
    else if ( v35 || *(_QWORD *)(v23 + 80) || *(_QWORD *)(v23 + 96) )
    {
      UlBugCheckEx(1u, v23 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
    }
    LOBYTE(v33) = 1;
    result = UlThreadPoolEnqueueWorkItem(0, v23 + 64, UlFreeHttpConnection, v33, v34, -1);
  }
LABEL_47:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    return WPP_SF_(1033, 193, WPP_173ede4a325638307373c19033e5a27a_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140020e50  mov     rax, rsp
0x140020e53  push    rbx
0x140020e54  push    rbp
0x140020e55  push    rdi
0x140020e56  sub     rsp, 0D0h
0x140020e5d  mov     rbx, rcx
0x140020e60  mov     byte ptr [rax+10h], 0
0x140020e64  mov     byte ptr [rax+8], 1
0x140020e68  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140020e6f  jnz     loc_14002165E
0x140020e75  mov     rcx, [rbx+30h]
0x140020e79  mov     [rsp+0E8h+var_20], rsi
0x140020e81  mov     [rsp+0E8h+var_38], r14
0x140020e89  lea     rax, [rcx+268h]
0x140020e90  mov     rdi, [rax]
0x140020e93  cmp     rdi, rax
0x140020e96  jnz     loc_140021505
0x140020e9c  mov     rax, [rbx+60h]
0x140020ea0  mov     [rax+6A0h], rcx
0x140020ea7  mov     rax, [rbx+60h]
0x140020eab  mov     rbp, [rax+18h]
0x140020eaf  mov     eax, 1
0x140020eb4  lock xadd [rbp+28h], eax
0x140020eb9  inc     eax
0x140020ebb  cmp     cs:UxDebugCheckRefcount, 0
0x140020ec2  jnz     loc_14002126B
0x140020ec8  mov     eax, [rbx+78h]
0x140020ecb  mov     [rsp+0E8h+var_28], r12
0x140020ed3  test    al, 1
0x140020ed5  jz      loc_14002125D
0x140020edb  mov     r12b, 1
0x140020ede  mov     [rsp+0E8h+arg_8], r12b
0x140020ee6  mov     rdi, [rbx+70h]
0x140020eea  test    rdi, rdi
0x140020eed  jnz     loc_14002167C
0x140020ef3  mov     rax, [rbx+0F8h]
0x140020efa  test    rax, rax
0x140020efd  jz      short loc_140020F0D
0x140020eff  mov     ecx, [rax+28h]
0x140020f02  mov     rax, [rax]
0x140020f05  add     rdi, rcx
0x140020f08  test    rax, rax
0x140020f0b  jnz     short loc_140020EFF
0x140020f0d  mov     r14, [rbx+60h]
0x140020f11  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140020f18  jnz     loc_1400215D3
0x140020f1e  cmp     cs:UxEnableIrqlEnforcement, 0
0x140020f25  jnz     loc_140021684
0x140020f2b  mov     rsi, [r14+18h]
0x140020f2f  lea     rax, [rbx-20h]
0x140020f33  mov     [rsp+0E8h+var_30], r13
0x140020f3b  mov     [rsp+0E8h+var_40], r15
0x140020f43  mov     [rsp+0E8h+var_68], rax
0x140020f4b  lea     rcx, [rsi+280h]; SpinLock
0x140020f52  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140020f59  nop     dword ptr [rax+rax+00h]
0x140020f5e  inc     dword ptr [r14+658h]
0x140020f65  movzx   r13d, al
0x140020f69  cmp     cs:UxKirHttpBugFix25Q1, 0
0x140020f70  jz      loc_14002136F
0x140020f76  mov     eax, [rsi+150h]
0x140020f7c  inc     eax
0x140020f7e  mov     [rsi+150h], eax
0x140020f84  cmp     [rsp+0E8h+arg_0], 0
0x140020f8c  jz      short loc_140020F9B
0x140020f8e  cmp     dword ptr [rsi+150h], 3
0x140020f95  jnb     loc_1400216B2
0x140020f9b  mov     r8d, edi
0x140020f9e  lea     rcx, [rsi+288h]
0x140020fa5  mov     r9b, 1
0x140020fa8  mov     edx, 2
0x140020fad  call    UlSetBundleTimerEx
0x140020fb2  movzx   edx, r13b; NewIrql
0x140020fb6  lea     rcx, [rsi+280h]; SpinLock
0x140020fbd  call    cs:__imp_KeReleaseSpinLock
0x140020fc4  nop     dword ptr [rax+rax+00h]
0x140020fc9  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140020fd0  jnz     loc_1400216D4
0x140020fd6  xor     eax, eax
0x140020fd8  lea     r12, [rbx+0F0h]
0x140020fdf  test    edi, edi
0x140020fe1  mov     ecx, 14h
0x140020fe6  cmovz   r12, rax
0x140020fea  xor     r8d, r8d
0x140020fed  test    edi, edi
0x140020fef  mov     [rsp+0E8h+var_60], r12
0x140020ff7  mov     rdi, [rbx+60h]
0x140020ffb  mov     eax, 13h
0x140021000  setnz   r8b
0x140021004  cmp     [rsp+0E8h+arg_8], 0
0x14002100c  mov     [rsp+0E8h+arg_10], r8d
0x140021014  cmovnz  cx, ax
0x140021018  movzx   esi, cx
0x14002101b  or      si, 20h
0x14002101f  cmp     byte ptr [rbx-0Bh], 0
0x140021023  cmovz   si, cx
0x140021027  cmp     byte ptr [rdi+0C8Eh], 0
0x14002102e  jnz     loc_1400211F2
0x140021034  xor     r13d, r13d
0x140021037  mov     eax, [rbx+78h]
0x14002103a  test    al, 2
0x14002103c  jnz     short loc_140021050
0x14002103e  test    byte ptr cs:xmmword_1401A2CA0+2, 1
0x140021045  jnz     loc_1400216EF
0x14002104b  or      si, 100h
0x140021050  mov     r15d, [rbx+90h]
0x140021057  xorps   xmm0, xmm0
0x14002105a  movups  xmmword ptr [rsp+0E8h+var_60], xmm0
0x140021062  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140021069  lea     r9, UlpSendResponseEntityBodyToExtension
0x140021070  lea     r10, UlpCompleteSendCacheEntry
0x140021077  jnz     loc_140021436
0x14002107d  mov     r14, rbp
0x140021080  test    sil, 1
0x140021084  jnz     loc_140021329
0x14002108a  xor     ebx, ebx
0x14002108c  cmp     cs:UlHkeQosClassficationEnabled, ebx
0x140021092  mov     [rsp+0E8h+arg_18], rbx
0x14002109a  jz      short loc_1400210BD
0x14002109c  lea     rdx, [rsp+0E8h+arg_18]
0x1400210a4  mov     rcx, rdi
0x1400210a7  call    UlpHkeAcquireQoS
0x1400210ac  mov     rbx, [rsp+0E8h+arg_18]
0x1400210b4  test    rbx, rbx
0x1400210b7  jnz     loc_14002128C
0x1400210bd  mov     rdx, [rdi+9B0h]
0x1400210c4  test    rdx, rdx
0x1400210c7  jnz     loc_1400214D8
0x1400210cd  cmp     qword ptr [rdi+40h], 0
0x1400210d2  jz      short loc_1400210E0
0x1400210d4  lea     rax, [rdi+48h]
0x1400210d8  mov     [rsp+0E8h+var_60], rax
0x1400210e0  xor     r8d, r8d
0x1400210e3  lea     rax, [rsp+0E8h+var_60]
0x1400210eb  mov     [rsp+0E8h+var_78], r8; __int64
0x1400210f0  lea     rcx, [r14+3D0h]; int
0x1400210f7  mov     [rsp+0E8h+var_80], r13; __int64
0x1400210fc  mov     r9d, r15d; int
0x1400210ff  mov     [rsp+0E8h+var_88], rax; __int64
0x140021104  lea     rax, UlpSendResponseEntityBodyToExtension
0x14002110b  mov     [rsp+0E8h+var_90], rax; __int64
0x140021110  mov     rax, [rsp+0E8h+var_68]
0x140021118  mov     [rsp+0E8h+var_98], rdi; __int64
0x14002111d  mov     [rsp+0E8h+var_A0], rdx; __int64
0x140021122  mov     rdx, r12; int
0x140021125  mov     [rsp+0E8h+var_A8], rdi; __int64
0x14002112a  mov     [rsp+0E8h+var_B0], rax; __int64
0x14002112f  lea     rax, UlpCompleteSendCacheEntry
0x140021136  mov     [rsp+0E8h+var_B8], rax; __int64
0x14002113b  mov     [rsp+0E8h+Irp], r8; Irp
0x140021140  mov     r8d, [rsp+0E8h+arg_10]; int
0x140021148  mov     [rsp+0E8h+var_C8], si; __int16
0x14002114d  call    UxTpTransmitPacket
0x140021152  mov     edi, eax
0x140021154  test    rbx, rbx
0x140021157  jnz     loc_14002171A
0x14002115d  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140021164  jnz     loc_14002172C
0x14002116a  cmp     [rsp+0E8h+arg_0], 0
0x140021172  jz      loc_14002174A
0x140021178  movzx   edx, [rsp+0E8h+arg_8]
0x140021180  mov     rcx, r14
0x140021183  call    UlResumeParsing
0x140021188  test    edi, edi
0x14002118a  js      loc_14002129C
0x140021190  mov     eax, 0FFFFFFFFh
0x140021195  lock xadd [rbp+28h], eax
0x14002119a  mov     r15, [rsp+0E8h+var_40]
0x1400211a2  dec     eax
0x1400211a4  cmp     cs:UxDebugCheckRefcount, 0
0x1400211ab  mov     r13, [rsp+0E8h+var_30]
0x1400211b3  jnz     loc_140021308
0x1400211b9  test    eax, eax
0x1400211bb  jz      loc_1400212B3
0x1400211c1  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400211c8  jnz     loc_140021775
0x1400211ce  mov     r12, [rsp+0E8h+var_28]
0x1400211d6  mov     r14, [rsp+0E8h+var_38]
0x1400211de  mov     rsi, [rsp+0E8h+var_20]
0x1400211e6  add     rsp, 0D0h
0x1400211ed  pop     rdi
0x1400211ee  pop     rbp
0x1400211ef  pop     rbx
0x1400211f0  retn
0x1400211f2  mov     r12d, [rbx+94h]
0x1400211f9  lea     r13, [rbx+0C8h]
0x140021200  mov     r14, [rbx+98h]
0x140021207  lea     r15, [rbx+0A0h]
0x14002120e  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140021215  jnz     loc_140021617
0x14002121b  mov     r9d, r12d
0x14002121e  mov     qword ptr [rsp+0E8h+var_C8], r13
0x140021223  mov     r8, r14
0x140021226  mov     rdx, r15
0x140021229  mov     rcx, rdi
0x14002122c  call    UlpSanitizeResponseHeaders
0x140021231  mov     edi, eax
0x140021233  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14002123a  jnz     loc_1400214A2
0x140021240  test    edi, edi
0x140021242  js      short loc_140021299
0x140021244  mov     rdi, [rbx+60h]
0x140021248  mov     r12, [rsp+0E8h+var_60]
0x140021250  mov     r8d, [rsp+0E8h+arg_10]
0x140021258  jmp     loc_140021037
0x14002125d  movzx   r12d, [rsp+0E8h+arg_8]
0x140021266  jmp     loc_140020EE6
0x14002126b  cmp     eax, 0FFFFFFFFh
0x14002126e  jg      loc_140020EC8
0x140021274  movsxd  r9, eax; BugCheckParameter4
0x140021277  lea     rdx, [rbp+28h]; BugCheckParameter2
0x14002127b  mov     r8d, 21h ; '!'; BugCheckParameter3
0x140021281  mov     ecx, 3; BugCheckParameter1
0x140021286  call    UlBugCheckEx
0x14002128c  or      si, 8000h
0x140021291  mov     rdx, rbx
0x140021294  jmp     loc_1400210CD
0x140021299  mov     r14, rbp
0x14002129c  mov     rcx, [rsp+0E8h+var_68]
0x1400212a4  xor     r8d, r8d
0x1400212a7  mov     edx, edi
0x1400212a9  call    UlpCompleteSendCacheEntry
0x1400212ae  jmp     loc_140021190
0x1400212b3  call    cs:__imp_IoGetCurrentProcess
0x1400212ba  nop     dword ptr [rax+rax+00h]
0x1400212bf  cmp     cs:UxSystemProcess, rax
0x1400212c6  mov     rdi, [r14+440h]
0x1400212cd  mov     rcx, [r14+40h]
0x1400212d1  jnz     loc_140021409
0x1400212d7  test    rcx, rcx
0x1400212da  jnz     short loc_1400212EC
0x1400212dc  cmp     [r14+50h], rcx
0x1400212e0  jnz     short loc_1400212EC
0x1400212e2  cmp     [r14+60h], rcx
0x1400212e6  jz      loc_14002137A
0x1400212ec  mov     r9d, 0E1h; BugCheckParameter4
0x1400212f2  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x1400212f9  lea     rdx, [r14+40h]; BugCheckParameter2
0x1400212fd  mov     ecx, 1; BugCheckParameter1
0x140021302  call    UlBugCheckEx
0x140021308  cmp     eax, 0FFFFFFFFh
0x14002130b  jg      loc_1400211B9
0x140021311  movsxd  r9, eax; BugCheckParameter4
0x140021314  lea     rdx, [rbp+28h]; BugCheckParameter2
0x140021318  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14002131e  mov     ecx, 3; BugCheckParameter1
0x140021323  call    UlBugCheckEx
0x140021329  lea     rcx, [r14+280h]; SpinLock
0x140021330  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140021337  nop     dword ptr [rax+rax+00h]
0x14002133c  cmp     byte ptr [r14+316h], 0
0x140021344  jnz     loc_1400214CB
0x14002134a  mov     word ptr [r14+314h], 100h
0x140021354  movzx   edx, al; NewIrql
0x140021357  lea     rcx, [r14+280h]; SpinLock
0x14002135e  call    cs:__imp_KeReleaseSpinLock
0x140021365  nop     dword ptr [rax+rax+00h]
0x14002136a  jmp     loc_14002108A
0x14002136f  inc     dword ptr [rsi+150h]
0x140021375  jmp     loc_140020F84
0x14002137a  call    cs:__imp_KeGetCurrentIrql
0x140021381  nop     dword ptr [rax+rax+00h]
0x140021386  test    al, al
0x140021388  jnz     short loc_1400213E2
0x14002138a  xorps   xmm0, xmm0
0x14002138d  movups  xmmword ptr [rsp+0E8h+var_60], xmm0
0x140021395  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140021399  jz      short loc_1400213C7
0x14002139b  mov     rcx, rdi
0x14002139e  mov     byte ptr [rsp+0E8h+var_60], 1
0x1400213a6  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400213ad  nop     dword ptr [rax+rax+00h]
0x1400213b2  mov     [rsp+0E8h+var_60+8], rax
0x1400213ba  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400213c1  jnz     loc_1400214E2
0x1400213c7  lea     rcx, [r14+40h]
0x1400213cb  call    UlFreeHttpConnection
0x1400213d0  lea     rcx, [rsp+0E8h+var_60]
0x1400213d8  call    UxPodDetachThread
0x1400213dd  jmp     loc_1400211C1
0x1400213e2  mov     dword ptr [rsp+0E8h+Irp], 0FFFFFFFFh
0x1400213ea  lea     r8, UlFreeHttpConnection
0x1400213f1  mov     r9b, 1
0x1400213f4  mov     qword ptr [rsp+0E8h+var_C8], rdi
0x1400213f9  lea     rdx, [r14+40h]
0x1400213fd  xor     ecx, ecx
0x1400213ff  call    UlThreadPoolEnqueueWorkItem
0x140021404  jmp     loc_1400211C1
0x140021409  test    rcx, rcx
0x14002140c  jnz     short loc_14002141A
0x14002140e  cmp     [r14+50h], rcx
0x140021412  jnz     short loc_14002141A
0x140021414  cmp     [r14+60h], rcx
0x140021418  jz      short loc_1400213E2
0x14002141a  mov     r9d, 0DBh; BugCheckParameter4
0x140021420  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140021427  lea     rdx, [r14+40h]; BugCheckParameter2
0x14002142b  mov     ecx, 1; BugCheckParameter1
0x140021430  call    UlBugCheckEx
0x140021436  test    rdi, rdi
  ... truncated ...
```
