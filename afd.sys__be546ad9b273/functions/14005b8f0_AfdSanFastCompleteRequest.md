# AfdSanFastCompleteRequest

- ea: `0x14005b8f0`
- end: `0x14005bdf6`
- name: `AfdSanFastCompleteRequest`
- size: `1286`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14002fd7c`
- `0x1400368e8`
- `0x14003f99c`
- `0x1400445d8`
- `0x14005ac10`
- `0x14005b8f0`
- `0x140072870`
- `0x1400931d0`
- `0x140093e58`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14005b97d`
- `ntoskrnl!ExRaiseStatus` at `0x14005ba7b`
- `ntoskrnl!ExRaiseStatus` at `0x14005b97d`
- `ntoskrnl!ExRaiseStatus` at `0x14005ba7b`
- `ntoskrnl!ProbeForRead` at `0x14005bc57`
- `ntoskrnl!ProbeForRead` at `0x14005bc57`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b994`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005ba1d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b994`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005ba1d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005bd9a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005bd9a`
- `ntoskrnl!IofCompleteRequest` at `0x14005bdb7`
- `ntoskrnl!IofCompleteRequest` at `0x14005bdb7`
- `ntoskrnl!ObfDereferenceObject` at `0x14005bdcf`
- `ntoskrnl!ObfDereferenceObject` at `0x14005bdcf`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005bd87`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005bd87`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005bd4b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005bd61`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005bd4b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005bd61`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005bcf0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005bcf0`
- `ntoskrnl!IoIs32bitProcess` at `0x14005b945`
- `ntoskrnl!IoIs32bitProcess` at `0x14005b945`
- `ntoskrnl!ProbeForWrite` at `0x14005bb8f`
- `ntoskrnl!ProbeForWrite` at `0x14005bb8f`
- `NETIO!RtlCopyBufferToMdlFromMode` at `0x14005bc81`
- `NETIO!RtlCopyBufferToMdlFromMode` at `0x14005bc81`
- `NETIO!RtlCopyMdlToBufferToMode` at `0x14005bbb8`
- `NETIO!RtlCopyMdlToBufferToMode` at `0x14005bbb8`

## pseudocode

```c
__int64 __fastcall AfdSanFastCompleteRequest(
        __int64 a1,
        unsigned __int16 a2,
        KPROCESSOR_MODE a3,
        void *a4,
        unsigned int a5,
        volatile void *Address,
        unsigned int Length,
        _QWORD *Irql)
{
  _QWORD *v12; // r13
  void *v13; // r10
  __int64 v14; // rcx
  __int64 result; // rax
  int v16; // edi
  __int64 v17; // r15
  __int64 v18; // rsi
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // [rsp+30h] [rbp-B8h]
  int v27; // [rsp+40h] [rbp-A8h]
  int v28; // [rsp+40h] [rbp-A8h]
  __int128 v29; // [rsp+48h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+58h] [rbp-90h]
  __int64 v31; // [rsp+68h] [rbp-80h] BYREF
  PVOID Object; // [rsp+70h] [rbp-78h] BYREF
  _DWORD v33[6]; // [rsp+78h] [rbp-70h] BYREF
  __int64 v34; // [rsp+90h] [rbp-58h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+98h] [rbp-50h] BYREF

  v31 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  Object = 0;
  v29 = 0;
  v30 = 0;
  v12 = Irql;
  *Irql = 0;
  if ( IoIs32bitProcess(0) )
  {
    memset(v33, 0, 20);
    if ( a5 < 0x14 )
      ExRaiseStatus(-1073741811);
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(v33, a4, 0x14u);
    }
    else
    {
      RtlCopyVolatileMemory(v33, a4, 0x14u);
    }
    v13 = (void *)v33[0];
    *(_QWORD *)&v29 = v33[0];
    v14 = v33[1];
    *((_QWORD *)&v29 + 1) = v33[1];
    *(_QWORD *)&v30 = v33[2];
    *((_QWORD *)&v30 + 1) = *(_QWORD *)&v33[3];
  }
  else
  {
    if ( a5 < 0x20 )
      return 3221225485LL;
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(&v29, a4, 0x20u);
    }
    else
    {
      RtlCopyVolatileMemory(&v29, a4, 0x20u);
    }
    v14 = *((_QWORD *)&v29 + 1);
    v13 = (void *)v29;
  }
  if ( !v14 )
  {
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_(1043, 33, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids);
    ExRaiseStatus(-1073741811);
  }
  result = AfdSanReferenceSwitchSocketByHandle(v13, a2 >> 14, a3, *(_QWORD *)(a1 + 24), v14, &Object);
  v16 = result;
  if ( (int)result >= 0 )
  {
    v17 = *((_QWORD *)Object + 3);
    v34 = v17;
    v18 = AfdSanDequeueRequest(v17);
    Irql = (_QWORD *)v18;
    if ( !v18 )
    {
      v16 = -1073741536;
      goto LABEL_63;
    }
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_qqqL(1043, 34, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v17, v18, v30, DWORD2(v30));
    if ( **(_BYTE **)(v18 + 184) == 3 )
    {
      if ( SDWORD2(v30) < 0 )
        goto LABEL_50;
      v22 = *(_QWORD *)(v18 + 8);
      if ( v22 )
      {
        if ( *(_DWORD *)(v22 + 40) > HIDWORD(v30) )
        {
          if ( a3 )
            ProbeForRead(Address, Length, 1u);
          LOBYTE(v19) = a3;
          v28 = RtlCopyBufferToMdlFromMode(*(_QWORD *)(v18 + 8), Address, HIDWORD(v30), v19, Length, &v31);
          if ( v28 >= 0 )
          {
            v23 = v31;
            *v12 = v31;
            *(_QWORD *)(v18 + 56) += v23;
          }
          v16 = v28;
          goto LABEL_50;
        }
LABEL_49:
        v16 = -1073741811;
        goto LABEL_50;
      }
    }
    else
    {
      if ( **(_BYTE **)(v18 + 184) != 4 )
      {
        v16 = -1073741808;
        goto LABEL_50;
      }
      if ( SDWORD2(v30) < 0 )
      {
LABEL_50:
        if ( v16 < 0 || DWORD2(v30) == 259 )
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v17 + 56), &LockHandle);
          _InterlockedExchange64((volatile __int64 *)(v18 + 104), (__int64)&AfdSanCancelRequest);
          if ( !*(_BYTE *)(v18 + 68) && !*(_BYTE *)(v17 + 161) )
          {
            v24 = (_QWORD *)(v17 + 128);
            v25 = *(_QWORD *)(v17 + 128);
            if ( *(_QWORD *)(v25 + 8) != v17 + 128 )
              __fastfail(3u);
            *(_QWORD *)(v18 + 168) = v25;
            *(_QWORD *)(v18 + 176) = v24;
            *(_QWORD *)(v25 + 8) = v18 + 168;
            *v24 = v18 + 168;
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            goto LABEL_63;
          }
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( !_InterlockedExchange64((volatile __int64 *)(v18 + 104), 0) )
          {
            LOBYTE(Irql) = 0;
            IoAcquireCancelSpinLock((PKIRQL)&Irql);
            IoReleaseCancelSpinLock((KIRQL)Irql);
          }
          v16 = -1073741536;
          *(_DWORD *)(v18 + 48) = -1073741536;
        }
        else
        {
          *(_DWORD *)(v18 + 48) = AfdValidateStatus(DWORD2(v30));
        }
        IofCompleteRequest((PIRP)v18, AfdPriorityBoost);
LABEL_63:
        ObfDereferenceObject(Object);
        return (unsigned int)v16;
      }
      v20 = *(_QWORD *)(v18 + 8);
      if ( v20 )
      {
        if ( *(_DWORD *)(v20 + 40) > HIDWORD(v30) )
        {
          if ( a3 )
            ProbeForWrite(Address, Length, 1u);
          LOBYTE(v19) = a3;
          v27 = RtlCopyMdlToBufferToMode(*(_QWORD *)(v18 + 8), HIDWORD(v30), Address, v19, Length, &v31, v26);
          if ( v27 >= 0 )
          {
            v21 = v31;
            *v12 = v31;
            *(_QWORD *)(v18 + 56) += v21;
          }
          v16 = v27;
          goto LABEL_50;
        }
        goto LABEL_49;
      }
    }
    if ( !HIDWORD(v30) && !Length )
      goto LABEL_50;
    goto LABEL_49;
  }
  return result;
}

```

## disassembly

```asm
0x14005b8f0  mov     r11, rsp
0x14005b8f3  push    rsi
0x14005b8f4  push    rdi
0x14005b8f5  push    r12
0x14005b8f7  push    r13
0x14005b8f9  push    r14
0x14005b8fb  push    r15
0x14005b8fd  sub     rsp, 0B8h
0x14005b904  mov     rdi, r9
0x14005b907  mov     r12b, r8b
0x14005b90a  mov     esi, edx
0x14005b90c  mov     r14, rcx
0x14005b90f  mov     qword ptr [r11-80h], 0
0x14005b917  xorps   xmm0, xmm0
0x14005b91a  xor     eax, eax
0x14005b91c  movups  xmmword ptr [r11-50h], xmm0
0x14005b921  mov     [r11-40h], rax
0x14005b925  mov     [r11-78h], rax
0x14005b929  movups  [rsp+0E8h+var_A0], xmm0
0x14005b92e  movups  [rsp+0E8h+var_90], xmm0
0x14005b933  mov     r13, [rsp+0E8h+Irql]
0x14005b93b  mov     [r13+0], rax
0x14005b93f  mov     [rsp+0E8h+var_A8], eax
0x14005b943  xor     ecx, ecx; Irp
0x14005b945  call    cs:__imp_IoIs32bitProcess
0x14005b94c  nop     dword ptr [rax+rax+00h]
0x14005b951  test    al, al
0x14005b953  jz      loc_14005B9F8
0x14005b959  xorps   xmm0, xmm0
0x14005b95c  xor     eax, eax
0x14005b95e  movups  xmmword ptr [rsp+0E8h+var_70], xmm0
0x14005b963  mov     [rsp+0E8h+var_70+10h], eax
0x14005b96a  lea     r8d, [rax+14h]; Size
0x14005b96e  cmp     [rsp+0E8h+arg_20], r8d
0x14005b976  jnb     short loc_14005B989
0x14005b978  mov     ecx, 0C000000Dh; Status
0x14005b97d  call    cs:__imp_ExRaiseStatus
0x14005b989  test    r12b, r12b
0x14005b98c  jz      short loc_14005B9B4
0x14005b98e  test    dil, 3
0x14005b992  jz      short loc_14005B9A0
0x14005b994  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005b99b  nop     dword ptr [rax+rax+00h]
0x14005b9a0  test    r12b, r12b
0x14005b9a3  jz      short loc_14005B9B4
0x14005b9a5  mov     rdx, rdi; Src
0x14005b9a8  lea     rcx, [rsp+0E8h+var_70]; void *
0x14005b9ad  call    RtlCopyFromUser
0x14005b9b2  jmp     short loc_14005B9C1
0x14005b9b4  mov     rdx, rdi; Src
0x14005b9b7  lea     rcx, [rsp+0E8h+var_70]; void *
0x14005b9bc  call    RtlCopyVolatileMemory
0x14005b9c1  movsxd  r10, [rsp+0E8h+var_70]
0x14005b9c6  mov     qword ptr [rsp+0E8h+var_A0], r10
0x14005b9cb  mov     ecx, [rsp+0E8h+var_70+4]
0x14005b9cf  mov     qword ptr [rsp+0E8h+var_A0+8], rcx
0x14005b9d4  mov     eax, [rsp+0E8h+var_70+8]
0x14005b9db  mov     qword ptr [rsp+0E8h+var_90], rax
0x14005b9e0  mov     eax, [rsp+0E8h+var_70+0Ch]
0x14005b9e7  mov     dword ptr [rsp+0E8h+var_90+8], eax
0x14005b9eb  mov     eax, [rsp+0E8h+var_70+10h]
0x14005b9f2  mov     dword ptr [rsp+0E8h+var_90+0Ch], eax
0x14005b9f6  jmp     short loc_14005BA54
0x14005b9f8  mov     r8d, 20h ; ' '; Size
0x14005b9fe  cmp     [rsp+0E8h+arg_20], r8d
0x14005ba06  jnb     short loc_14005BA12
0x14005ba08  mov     eax, 0C000000Dh
0x14005ba0d  jmp     loc_14005BDE3
0x14005ba12  test    r12b, r12b
0x14005ba15  jz      short loc_14005BA3D
0x14005ba17  test    dil, 3
0x14005ba1b  jz      short loc_14005BA29
0x14005ba1d  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005ba24  nop     dword ptr [rax+rax+00h]
0x14005ba29  test    r12b, r12b
0x14005ba2c  jz      short loc_14005BA3D
0x14005ba2e  mov     rdx, rdi; Src
0x14005ba31  lea     rcx, [rsp+0E8h+var_A0]; void *
0x14005ba36  call    RtlCopyFromUser
0x14005ba3b  jmp     short loc_14005BA4A
0x14005ba3d  mov     rdx, rdi; Src
0x14005ba40  lea     rcx, [rsp+0E8h+var_A0]; void *
0x14005ba45  call    RtlCopyVolatileMemory
0x14005ba4a  mov     rcx, qword ptr [rsp+0E8h+var_A0+8]
0x14005ba4f  mov     r10, qword ptr [rsp+0E8h+var_A0]
0x14005ba54  test    rcx, rcx
0x14005ba57  jnz     short loc_14005BA88
0x14005ba59  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005ba60  jz      short loc_14005BA76
0x14005ba62  lea     edx, [rcx+21h]
0x14005ba65  mov     ecx, 413h
0x14005ba6a  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005ba71  call    WPP_SF_
0x14005ba76  mov     ecx, 0C000000Dh; Status
0x14005ba7b  call    cs:__imp_ExRaiseStatus
0x14005ba88  shr     esi, 0Eh
0x14005ba8b  and     esi, 3
0x14005ba8e  lea     rax, [rsp+0E8h+Object]
0x14005ba93  mov     [rsp+0E8h+var_C0], rax; __int64
0x14005ba98  mov     [rsp+0E8h+var_C8], rcx; __int64
0x14005ba9d  mov     r9, [r14+18h]
0x14005baa1  mov     r8b, r12b; AccessMode
0x14005baa4  mov     edx, esi; DesiredAccess
0x14005baa6  mov     rcx, r10; Handle
0x14005baa9  call    AfdSanReferenceSwitchSocketByHandle
0x14005baae  mov     edi, eax
0x14005bab0  mov     [rsp+0E8h+var_A8], eax
0x14005bab4  test    eax, eax
0x14005bab6  js      loc_14005BDE3
0x14005babc  mov     rax, [rsp+0E8h+Object]
0x14005bac1  mov     r15, [rax+18h]
0x14005bac5  mov     [rsp+0E8h+var_58], r15
0x14005bacd  mov     rdx, qword ptr [rsp+0E8h+var_90]
0x14005bad2  mov     rcx, r15
0x14005bad5  call    AfdSanDequeueRequest
0x14005bada  mov     rsi, rax
0x14005badd  mov     [rsp+0E8h+Irql], rax
0x14005bae5  test    rax, rax
0x14005bae8  jz      loc_14005BDC5
0x14005baee  mov     r14d, dword ptr [rsp+0E8h+Length]
0x14005baf6  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005bafd  jz      short loc_14005BB2F
0x14005baff  mov     edx, 22h ; '"'
0x14005bb04  mov     ecx, 413h
0x14005bb09  mov     eax, dword ptr [rsp+0E8h+var_90+8]
0x14005bb0d  mov     [rsp+0E8h+var_B8], eax
0x14005bb11  mov     rax, qword ptr [rsp+0E8h+var_90]
0x14005bb16  mov     [rsp+0E8h+var_C0], rax
0x14005bb1b  mov     [rsp+0E8h+var_C8], rsi
0x14005bb20  mov     r9, r15
0x14005bb23  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005bb2a  call    WPP_SF_qqqL
0x14005bb2f  mov     rax, [rsi+0B8h]
0x14005bb36  movzx   ecx, byte ptr [rax]
0x14005bb39  sub     ecx, 3
0x14005bb3c  jz      loc_14005BC21
0x14005bb42  cmp     ecx, 1
0x14005bb45  jz      short loc_14005BB51
0x14005bb47  mov     edi, 0C0000010h
0x14005bb4c  jmp     loc_14005BCC7
0x14005bb51  cmp     dword ptr [rsp+0E8h+var_90+8], 0
0x14005bb56  jl      loc_14005BCC7
0x14005bb5c  mov     rcx, [rsi+8]
0x14005bb60  test    rcx, rcx
0x14005bb63  jz      loc_14005BC08
0x14005bb69  mov     eax, dword ptr [rsp+0E8h+var_90+0Ch]
0x14005bb6d  cmp     [rcx+28h], eax
0x14005bb70  jbe     loc_14005BBFF
0x14005bb76  mov     rdi, [rsp+0E8h+Address]
0x14005bb7e  test    r12b, r12b
0x14005bb81  jz      short loc_14005BB9B
0x14005bb83  mov     rdx, r14; Length
0x14005bb86  mov     r8d, 1; Alignment
0x14005bb8c  mov     rcx, rdi; Address
0x14005bb8f  call    cs:__imp_ProbeForWrite
0x14005bb96  nop     dword ptr [rax+rax+00h]
0x14005bb9b  mov     edx, dword ptr [rsp+0E8h+var_90+0Ch]
0x14005bb9f  lea     rcx, [rsp+0E8h+var_80]
0x14005bba4  mov     [rsp+0E8h+var_C0], rcx
0x14005bba9  mov     [rsp+0E8h+var_C8], r14
0x14005bbae  mov     r9b, r12b
0x14005bbb1  mov     r8, rdi
0x14005bbb4  mov     rcx, [rsi+8]
0x14005bbb8  call    cs:__imp_RtlCopyMdlToBufferToMode
0x14005bbbf  nop     dword ptr [rax+rax+00h]
0x14005bbc4  mov     [rsp+0E8h+var_A8], eax
0x14005bbc8  mov     eax, [rsp+0E8h+var_A8]
0x14005bbcc  test    eax, eax
0x14005bbce  js      short loc_14005BBDD
0x14005bbd0  mov     rax, [rsp+0E8h+var_80]
0x14005bbd5  mov     [r13+0], rax
0x14005bbd9  add     [rsi+38h], rax
0x14005bbdd  mov     edi, [rsp+0E8h+var_A8]
0x14005bbe1  jmp     loc_14005BCC7
0x14005bbe6  mov     edi, [rsp+0E8h+var_A8]
0x14005bbea  mov     rsi, [rsp+0E8h+Irql]
0x14005bbf2  mov     r15, [rsp+0E8h+var_58]
0x14005bbfa  jmp     loc_14005BCC7
0x14005bbff  test    rcx, rcx
0x14005bc02  jnz     loc_14005BCC2
0x14005bc08  cmp     dword ptr [rsp+0E8h+var_90+0Ch], 0
0x14005bc0d  jnz     loc_14005BCC2
0x14005bc13  test    r14d, r14d
0x14005bc16  jnz     loc_14005BCC2
0x14005bc1c  jmp     loc_14005BCC7
0x14005bc21  cmp     dword ptr [rsp+0E8h+var_90+8], 0
0x14005bc26  jl      loc_14005BCC7
0x14005bc2c  mov     rcx, [rsi+8]
0x14005bc30  test    rcx, rcx
0x14005bc33  jz      short loc_14005BC08
0x14005bc35  mov     eax, dword ptr [rsp+0E8h+var_90+0Ch]
0x14005bc39  cmp     [rcx+28h], eax
0x14005bc3c  jbe     short loc_14005BBFF
0x14005bc3e  mov     rdi, [rsp+0E8h+Address]
0x14005bc46  test    r12b, r12b
0x14005bc49  jz      short loc_14005BC63
0x14005bc4b  mov     rdx, r14; Length
0x14005bc4e  mov     r8d, 1; Alignment
0x14005bc54  mov     rcx, rdi; Address
0x14005bc57  call    cs:__imp_ProbeForRead
0x14005bc5e  nop     dword ptr [rax+rax+00h]
0x14005bc63  mov     r8d, dword ptr [rsp+0E8h+var_90+0Ch]
0x14005bc68  lea     rcx, [rsp+0E8h+var_80]
0x14005bc6d  mov     [rsp+0E8h+var_C0], rcx
0x14005bc72  mov     [rsp+0E8h+var_C8], r14
0x14005bc77  mov     r9b, r12b
0x14005bc7a  mov     rdx, rdi
0x14005bc7d  mov     rcx, [rsi+8]
0x14005bc81  call    cs:__imp_RtlCopyBufferToMdlFromMode
0x14005bc88  nop     dword ptr [rax+rax+00h]
0x14005bc8d  mov     [rsp+0E8h+var_A8], eax
0x14005bc91  mov     eax, [rsp+0E8h+var_A8]
0x14005bc95  test    eax, eax
0x14005bc97  js      short loc_14005BCA6
0x14005bc99  mov     rax, [rsp+0E8h+var_80]
0x14005bc9e  mov     [r13+0], rax
0x14005bca2  add     [rsi+38h], rax
0x14005bca6  mov     edi, [rsp+0E8h+var_A8]
0x14005bcaa  jmp     short loc_14005BCC7
0x14005bcac  mov     edi, [rsp+0E8h+var_A8]
0x14005bcb0  mov     rsi, [rsp+0E8h+Irql]
0x14005bcb8  mov     r15, [rsp+0E8h+var_58]
0x14005bcc0  jmp     short loc_14005BCC7
0x14005bcc2  mov     edi, 0C000000Dh
0x14005bcc7  test    edi, edi
0x14005bcc9  js      short loc_14005BCE4
0x14005bccb  mov     ecx, dword ptr [rsp+0E8h+var_90+8]
0x14005bccf  cmp     ecx, 103h
0x14005bcd5  jz      short loc_14005BCE4
0x14005bcd7  call    AfdValidateStatus
0x14005bcdc  mov     [rsi+30h], eax
0x14005bcdf  jmp     loc_14005BDAE
0x14005bce4  lea     rcx, [r15+38h]; SpinLock
0x14005bce8  lea     rdx, [rsp+0E8h+LockHandle]; LockHandle
0x14005bcf0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005bcf7  nop     dword ptr [rax+rax+00h]
0x14005bcfc  lea     rax, AfdSanCancelRequest
0x14005bd03  xchg    rax, [rsi+68h]
0x14005bd07  cmp     byte ptr [rsi+44h], 0
0x14005bd0b  jnz     short loc_14005BD59
0x14005bd0d  cmp     byte ptr [r15+0A1h], 0
0x14005bd15  jnz     short loc_14005BD59
0x14005bd17  lea     rcx, [r15+80h]
0x14005bd1e  mov     rdx, [rcx]
0x14005bd21  cmp     [rdx+8], rcx
0x14005bd25  jz      short loc_14005BD2E
0x14005bd27  mov     ecx, 3
0x14005bd2c  int     29h; Win8: RtlFailFast(ecx)
0x14005bd2e  lea     rax, [rsi+0A8h]
0x14005bd35  mov     [rax], rdx
0x14005bd38  mov     [rax+8], rcx
0x14005bd3c  mov     [rdx+8], rax
0x14005bd40  mov     [rcx], rax
0x14005bd43  lea     rcx, [rsp+0E8h+LockHandle]; LockHandle
0x14005bd4b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005bd52  nop     dword ptr [rax+rax+00h]
0x14005bd57  jmp     short loc_14005BDCA
0x14005bd59  lea     rcx, [rsp+0E8h+LockHandle]; LockHandle
0x14005bd61  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005bd68  nop     dword ptr [rax+rax+00h]
0x14005bd6d  xor     eax, eax
0x14005bd6f  xchg    rax, [rsi+68h]
0x14005bd73  test    rax, rax
0x14005bd76  jnz     short loc_14005BDA6
0x14005bd78  mov     byte ptr [rsp+0E8h+Irql], al
0x14005bd7f  lea     rcx, [rsp+0E8h+Irql]; Irql
0x14005bd87  call    cs:__imp_IoAcquireCancelSpinLock
0x14005bd8e  nop     dword ptr [rax+rax+00h]
0x14005bd93  mov     cl, byte ptr [rsp+0E8h+Irql]; Irql
0x14005bd9a  call    cs:__imp_IoReleaseCancelSpinLock
0x14005bda1  nop     dword ptr [rax+rax+00h]
0x14005bda6  mov     edi, 0C0000120h
0x14005bdab  mov     [rsi+30h], edi
0x14005bdae  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14005bdb4  mov     rcx, rsi; Irp
0x14005bdb7  call    cs:__imp_IofCompleteRequest
0x14005bdbe  nop     dword ptr [rax+rax+00h]
0x14005bdc3  jmp     short loc_14005BDCA
0x14005bdc5  mov     edi, 0C0000120h
0x14005bdca  mov     rcx, [rsp+0E8h+Object]; Object
0x14005bdcf  call    cs:__imp_ObfDereferenceObject
0x14005bdd6  nop     dword ptr [rax+rax+00h]
0x14005bddb  mov     eax, edi
0x14005bddd  jmp     short loc_14005BDE3
0x14005bddf  mov     eax, [rsp+0E8h+var_A8]
0x14005bde3  add     rsp, 0B8h
0x14005bdea  pop     r15
0x14005bdec  pop     r14
0x14005bdee  pop     r13
0x14005bdf0  pop     r12
0x14005bdf2  pop     rdi
0x14005bdf3  pop     rsi
0x14005bdf4  retn
0x14007440e  push    rbp
0x140074410  sub     rsp, 40h
0x140074414  mov     rbp, rdx
0x140074417  mov     r8, rcx
0x14007441a  lea     r9, [rbp+40h]
0x14007441e  mov     edx, 8B3h
0x140074423  lea     rcx, aMinioSocketsWi_11; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
  ... truncated ...
```
