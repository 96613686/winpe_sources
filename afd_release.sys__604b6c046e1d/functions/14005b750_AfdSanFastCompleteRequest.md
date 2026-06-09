# AfdSanFastCompleteRequest

- ea: `0x14005b750`
- end: `0x14005bc56`
- name: `AfdSanFastCompleteRequest`
- size: `1286`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, KPROCESSOR_MODE, void *, unsigned int, volatile void *Address, unsigned int Length, _QWORD *Irql)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14002fd5c`
- `0x1400368c8`
- `0x14003f97c`
- `0x1400445b8`
- `0x14005aa70`
- `0x14005b750`
- `0x1400726d0`
- `0x1400931d0`
- `0x140093e58`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14005b7dd`
- `ntoskrnl!ExRaiseStatus` at `0x14005b8db`
- `ntoskrnl!ExRaiseStatus` at `0x14005b7dd`
- `ntoskrnl!ExRaiseStatus` at `0x14005b8db`
- `ntoskrnl!ProbeForRead` at `0x14005bab7`
- `ntoskrnl!ProbeForRead` at `0x14005bab7`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b7f4`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b87d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b7f4`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b87d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005bbfa`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005bbfa`
- `ntoskrnl!IofCompleteRequest` at `0x14005bc17`
- `ntoskrnl!IofCompleteRequest` at `0x14005bc17`
- `ntoskrnl!ObfDereferenceObject` at `0x14005bc2f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005bc2f`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005bbe7`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005bbe7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005bbab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005bbc1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005bbab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005bbc1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005bb50`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005bb50`
- `ntoskrnl!IoIs32bitProcess` at `0x14005b7a5`
- `ntoskrnl!IoIs32bitProcess` at `0x14005b7a5`
- `ntoskrnl!ProbeForWrite` at `0x14005b9ef`
- `ntoskrnl!ProbeForWrite` at `0x14005b9ef`
- `NETIO!RtlCopyBufferToMdlFromMode` at `0x14005bae1`
- `NETIO!RtlCopyBufferToMdlFromMode` at `0x14005bae1`
- `NETIO!RtlCopyMdlToBufferToMode` at `0x14005ba18`
- `NETIO!RtlCopyMdlToBufferToMode` at `0x14005ba18`

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
  __int64 v18; // rdx
  _QWORD *v19; // rsi
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // [rsp+30h] [rbp-B8h]
  int v29; // [rsp+40h] [rbp-A8h]
  int v30; // [rsp+40h] [rbp-A8h]
  __int128 v31; // [rsp+48h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+58h] [rbp-90h]
  __int64 v33; // [rsp+68h] [rbp-80h] BYREF
  PVOID Object; // [rsp+70h] [rbp-78h] BYREF
  _DWORD v35[6]; // [rsp+78h] [rbp-70h] BYREF
  __int64 v36; // [rsp+90h] [rbp-58h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+98h] [rbp-50h] BYREF

  v33 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  Object = 0;
  v31 = 0;
  v32 = 0;
  v12 = Irql;
  *Irql = 0;
  if ( IoIs32bitProcess(0) )
  {
    memset(v35, 0, 20);
    if ( a5 < 0x14 )
      ExRaiseStatus(-1073741811);
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(v35, a4, 0x14u);
    }
    else
    {
      RtlCopyVolatileMemory(v35, a4, 0x14u);
    }
    v13 = (void *)v35[0];
    *(_QWORD *)&v31 = v35[0];
    v14 = v35[1];
    *((_QWORD *)&v31 + 1) = v35[1];
    *(_QWORD *)&v32 = v35[2];
    *((_QWORD *)&v32 + 1) = *(_QWORD *)&v35[3];
  }
  else
  {
    if ( a5 < 0x20 )
      return 3221225485LL;
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(&v31, a4, 0x20u);
    }
    else
    {
      RtlCopyVolatileMemory(&v31, a4, 0x20u);
    }
    v14 = *((_QWORD *)&v31 + 1);
    v13 = (void *)v31;
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
    v36 = v17;
    v19 = AfdSanDequeueRequest(v17, v32);
    Irql = v19;
    if ( !v19 )
    {
      v16 = -1073741536;
      goto LABEL_63;
    }
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_qqqL(1043, 34, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v17, v19, v32, DWORD2(v32));
    if ( *(_BYTE *)v19[23] == 3 )
    {
      if ( SDWORD2(v32) < 0 )
        goto LABEL_50;
      v24 = v19[1];
      if ( v24 )
      {
        if ( *(_DWORD *)(v24 + 40) > HIDWORD(v32) )
        {
          if ( a3 )
            ProbeForRead(Address, Length, 1u);
          LOBYTE(v21) = a3;
          v30 = RtlCopyBufferToMdlFromMode(v19[1], Address, HIDWORD(v32), v21, Length, &v33);
          if ( v30 >= 0 )
          {
            v25 = v33;
            *v12 = v33;
            v19[7] += v25;
          }
          v16 = v30;
          goto LABEL_50;
        }
LABEL_49:
        v16 = -1073741811;
        goto LABEL_50;
      }
    }
    else
    {
      if ( *(_BYTE *)v19[23] != 4 )
      {
        v16 = -1073741808;
        goto LABEL_50;
      }
      if ( SDWORD2(v32) < 0 )
      {
LABEL_50:
        if ( v16 < 0 || DWORD2(v32) == 259 )
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v17 + 56), &LockHandle);
          _InterlockedExchange64(v19 + 13, (__int64)AfdSanCancelRequest);
          if ( !*((_BYTE *)v19 + 68) && !*(_BYTE *)(v17 + 161) )
          {
            v26 = (_QWORD *)(v17 + 128);
            v27 = *(_QWORD *)(v17 + 128);
            if ( *(_QWORD *)(v27 + 8) != v17 + 128 )
              __fastfail(3u);
            v19[21] = v27;
            v19[22] = v26;
            *(_QWORD *)(v27 + 8) = v19 + 21;
            *v26 = v19 + 21;
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            goto LABEL_63;
          }
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( !_InterlockedExchange64(v19 + 13, 0) )
          {
            LOBYTE(Irql) = 0;
            IoAcquireCancelSpinLock((PKIRQL)&Irql);
            IoReleaseCancelSpinLock((KIRQL)Irql);
          }
          v16 = -1073741536;
          *((_DWORD *)v19 + 12) = -1073741536;
        }
        else
        {
          *((_DWORD *)v19 + 12) = AfdValidateStatus(DWORD2(v32), v18, v20);
        }
        IofCompleteRequest((PIRP)v19, AfdPriorityBoost);
LABEL_63:
        ObfDereferenceObject(Object);
        return (unsigned int)v16;
      }
      v22 = v19[1];
      if ( v22 )
      {
        if ( *(_DWORD *)(v22 + 40) > HIDWORD(v32) )
        {
          if ( a3 )
            ProbeForWrite(Address, Length, 1u);
          LOBYTE(v21) = a3;
          v29 = RtlCopyMdlToBufferToMode(v19[1], HIDWORD(v32), Address, v21, Length, &v33, v28);
          if ( v29 >= 0 )
          {
            v23 = v33;
            *v12 = v33;
            v19[7] += v23;
          }
          v16 = v29;
          goto LABEL_50;
        }
        goto LABEL_49;
      }
    }
    if ( !HIDWORD(v32) && !Length )
      goto LABEL_50;
    goto LABEL_49;
  }
  return result;
}

```

## disassembly

```asm
0x14005b750  mov     r11, rsp
0x14005b753  push    rsi
0x14005b754  push    rdi
0x14005b755  push    r12
0x14005b757  push    r13
0x14005b759  push    r14
0x14005b75b  push    r15
0x14005b75d  sub     rsp, 0B8h
0x14005b764  mov     rdi, r9
0x14005b767  mov     r12b, r8b
0x14005b76a  mov     esi, edx
0x14005b76c  mov     r14, rcx
0x14005b76f  mov     qword ptr [r11-80h], 0
0x14005b777  xorps   xmm0, xmm0
0x14005b77a  xor     eax, eax
0x14005b77c  movups  xmmword ptr [r11-50h], xmm0
0x14005b781  mov     [r11-40h], rax
0x14005b785  mov     [r11-78h], rax
0x14005b789  movups  [rsp+0E8h+var_A0], xmm0
0x14005b78e  movups  [rsp+0E8h+var_90], xmm0
0x14005b793  mov     r13, [rsp+0E8h+Irql]
0x14005b79b  mov     [r13+0], rax
0x14005b79f  mov     [rsp+0E8h+var_A8], eax
0x14005b7a3  xor     ecx, ecx; Irp
0x14005b7a5  call    cs:__imp_IoIs32bitProcess
0x14005b7ac  nop     dword ptr [rax+rax+00h]
0x14005b7b1  test    al, al
0x14005b7b3  jz      loc_14005B858
0x14005b7b9  xorps   xmm0, xmm0
0x14005b7bc  xor     eax, eax
0x14005b7be  movups  xmmword ptr [rsp+0E8h+var_70], xmm0
0x14005b7c3  mov     [rsp+0E8h+var_70+10h], eax
0x14005b7ca  lea     r8d, [rax+14h]; Size
0x14005b7ce  cmp     [rsp+0E8h+arg_20], r8d
0x14005b7d6  jnb     short loc_14005B7E9
0x14005b7d8  mov     ecx, 0C000000Dh; Status
0x14005b7dd  call    cs:__imp_ExRaiseStatus
0x14005b7e9  test    r12b, r12b
0x14005b7ec  jz      short loc_14005B814
0x14005b7ee  test    dil, 3
0x14005b7f2  jz      short loc_14005B800
0x14005b7f4  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005b7fb  nop     dword ptr [rax+rax+00h]
0x14005b800  test    r12b, r12b
0x14005b803  jz      short loc_14005B814
0x14005b805  mov     rdx, rdi; Src
0x14005b808  lea     rcx, [rsp+0E8h+var_70]; void *
0x14005b80d  call    RtlCopyFromUser
0x14005b812  jmp     short loc_14005B821
0x14005b814  mov     rdx, rdi; Src
0x14005b817  lea     rcx, [rsp+0E8h+var_70]; void *
0x14005b81c  call    RtlCopyVolatileMemory
0x14005b821  movsxd  r10, [rsp+0E8h+var_70]
0x14005b826  mov     qword ptr [rsp+0E8h+var_A0], r10
0x14005b82b  mov     ecx, [rsp+0E8h+var_70+4]
0x14005b82f  mov     qword ptr [rsp+0E8h+var_A0+8], rcx
0x14005b834  mov     eax, [rsp+0E8h+var_70+8]
0x14005b83b  mov     qword ptr [rsp+0E8h+var_90], rax
0x14005b840  mov     eax, [rsp+0E8h+var_70+0Ch]
0x14005b847  mov     dword ptr [rsp+0E8h+var_90+8], eax
0x14005b84b  mov     eax, [rsp+0E8h+var_70+10h]
0x14005b852  mov     dword ptr [rsp+0E8h+var_90+0Ch], eax
0x14005b856  jmp     short loc_14005B8B4
0x14005b858  mov     r8d, 20h ; ' '; Size
0x14005b85e  cmp     [rsp+0E8h+arg_20], r8d
0x14005b866  jnb     short loc_14005B872
0x14005b868  mov     eax, 0C000000Dh
0x14005b86d  jmp     loc_14005BC43
0x14005b872  test    r12b, r12b
0x14005b875  jz      short loc_14005B89D
0x14005b877  test    dil, 3
0x14005b87b  jz      short loc_14005B889
0x14005b87d  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005b884  nop     dword ptr [rax+rax+00h]
0x14005b889  test    r12b, r12b
0x14005b88c  jz      short loc_14005B89D
0x14005b88e  mov     rdx, rdi; Src
0x14005b891  lea     rcx, [rsp+0E8h+var_A0]; void *
0x14005b896  call    RtlCopyFromUser
0x14005b89b  jmp     short loc_14005B8AA
0x14005b89d  mov     rdx, rdi; Src
0x14005b8a0  lea     rcx, [rsp+0E8h+var_A0]; void *
0x14005b8a5  call    RtlCopyVolatileMemory
0x14005b8aa  mov     rcx, qword ptr [rsp+0E8h+var_A0+8]
0x14005b8af  mov     r10, qword ptr [rsp+0E8h+var_A0]
0x14005b8b4  test    rcx, rcx
0x14005b8b7  jnz     short loc_14005B8E8
0x14005b8b9  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005b8c0  jz      short loc_14005B8D6
0x14005b8c2  lea     edx, [rcx+21h]
0x14005b8c5  mov     ecx, 413h
0x14005b8ca  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005b8d1  call    WPP_SF_
0x14005b8d6  mov     ecx, 0C000000Dh; Status
0x14005b8db  call    cs:__imp_ExRaiseStatus
0x14005b8e8  shr     esi, 0Eh
0x14005b8eb  and     esi, 3
0x14005b8ee  lea     rax, [rsp+0E8h+Object]
0x14005b8f3  mov     [rsp+0E8h+var_C0], rax; __int64
0x14005b8f8  mov     [rsp+0E8h+var_C8], rcx; __int64
0x14005b8fd  mov     r9, [r14+18h]
0x14005b901  mov     r8b, r12b; AccessMode
0x14005b904  mov     edx, esi; DesiredAccess
0x14005b906  mov     rcx, r10; Handle
0x14005b909  call    AfdSanReferenceSwitchSocketByHandle
0x14005b90e  mov     edi, eax
0x14005b910  mov     [rsp+0E8h+var_A8], eax
0x14005b914  test    eax, eax
0x14005b916  js      loc_14005BC43
0x14005b91c  mov     rax, [rsp+0E8h+Object]
0x14005b921  mov     r15, [rax+18h]
0x14005b925  mov     [rsp+0E8h+var_58], r15
0x14005b92d  mov     rdx, qword ptr [rsp+0E8h+var_90]
0x14005b932  mov     rcx, r15
0x14005b935  call    AfdSanDequeueRequest
0x14005b93a  mov     rsi, rax
0x14005b93d  mov     [rsp+0E8h+Irql], rax
0x14005b945  test    rax, rax
0x14005b948  jz      loc_14005BC25
0x14005b94e  mov     r14d, dword ptr [rsp+0E8h+Length]
0x14005b956  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005b95d  jz      short loc_14005B98F
0x14005b95f  mov     edx, 22h ; '"'
0x14005b964  mov     ecx, 413h
0x14005b969  mov     eax, dword ptr [rsp+0E8h+var_90+8]
0x14005b96d  mov     [rsp+0E8h+var_B8], eax
0x14005b971  mov     rax, qword ptr [rsp+0E8h+var_90]
0x14005b976  mov     [rsp+0E8h+var_C0], rax
0x14005b97b  mov     [rsp+0E8h+var_C8], rsi
0x14005b980  mov     r9, r15
0x14005b983  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005b98a  call    WPP_SF_qqqL
0x14005b98f  mov     rax, [rsi+0B8h]
0x14005b996  movzx   ecx, byte ptr [rax]
0x14005b999  sub     ecx, 3
0x14005b99c  jz      loc_14005BA81
0x14005b9a2  cmp     ecx, 1
0x14005b9a5  jz      short loc_14005B9B1
0x14005b9a7  mov     edi, 0C0000010h
0x14005b9ac  jmp     loc_14005BB27
0x14005b9b1  cmp     dword ptr [rsp+0E8h+var_90+8], 0
0x14005b9b6  jl      loc_14005BB27
0x14005b9bc  mov     rcx, [rsi+8]
0x14005b9c0  test    rcx, rcx
0x14005b9c3  jz      loc_14005BA68
0x14005b9c9  mov     eax, dword ptr [rsp+0E8h+var_90+0Ch]
0x14005b9cd  cmp     [rcx+28h], eax
0x14005b9d0  jbe     loc_14005BA5F
0x14005b9d6  mov     rdi, [rsp+0E8h+Address]
0x14005b9de  test    r12b, r12b
0x14005b9e1  jz      short loc_14005B9FB
0x14005b9e3  mov     rdx, r14; Length
0x14005b9e6  mov     r8d, 1; Alignment
0x14005b9ec  mov     rcx, rdi; Address
0x14005b9ef  call    cs:__imp_ProbeForWrite
0x14005b9f6  nop     dword ptr [rax+rax+00h]
0x14005b9fb  mov     edx, dword ptr [rsp+0E8h+var_90+0Ch]
0x14005b9ff  lea     rcx, [rsp+0E8h+var_80]
0x14005ba04  mov     [rsp+0E8h+var_C0], rcx
0x14005ba09  mov     [rsp+0E8h+var_C8], r14
0x14005ba0e  mov     r9b, r12b
0x14005ba11  mov     r8, rdi
0x14005ba14  mov     rcx, [rsi+8]
0x14005ba18  call    cs:__imp_RtlCopyMdlToBufferToMode
0x14005ba1f  nop     dword ptr [rax+rax+00h]
0x14005ba24  mov     [rsp+0E8h+var_A8], eax
0x14005ba28  mov     eax, [rsp+0E8h+var_A8]
0x14005ba2c  test    eax, eax
0x14005ba2e  js      short loc_14005BA3D
0x14005ba30  mov     rax, [rsp+0E8h+var_80]
0x14005ba35  mov     [r13+0], rax
0x14005ba39  add     [rsi+38h], rax
0x14005ba3d  mov     edi, [rsp+0E8h+var_A8]
0x14005ba41  jmp     loc_14005BB27
0x14005ba46  mov     edi, [rsp+0E8h+var_A8]
0x14005ba4a  mov     rsi, [rsp+0E8h+Irql]
0x14005ba52  mov     r15, [rsp+0E8h+var_58]
0x14005ba5a  jmp     loc_14005BB27
0x14005ba5f  test    rcx, rcx
0x14005ba62  jnz     loc_14005BB22
0x14005ba68  cmp     dword ptr [rsp+0E8h+var_90+0Ch], 0
0x14005ba6d  jnz     loc_14005BB22
0x14005ba73  test    r14d, r14d
0x14005ba76  jnz     loc_14005BB22
0x14005ba7c  jmp     loc_14005BB27
0x14005ba81  cmp     dword ptr [rsp+0E8h+var_90+8], 0
0x14005ba86  jl      loc_14005BB27
0x14005ba8c  mov     rcx, [rsi+8]
0x14005ba90  test    rcx, rcx
0x14005ba93  jz      short loc_14005BA68
0x14005ba95  mov     eax, dword ptr [rsp+0E8h+var_90+0Ch]
0x14005ba99  cmp     [rcx+28h], eax
0x14005ba9c  jbe     short loc_14005BA5F
0x14005ba9e  mov     rdi, [rsp+0E8h+Address]
0x14005baa6  test    r12b, r12b
0x14005baa9  jz      short loc_14005BAC3
0x14005baab  mov     rdx, r14; Length
0x14005baae  mov     r8d, 1; Alignment
0x14005bab4  mov     rcx, rdi; Address
0x14005bab7  call    cs:__imp_ProbeForRead
0x14005babe  nop     dword ptr [rax+rax+00h]
0x14005bac3  mov     r8d, dword ptr [rsp+0E8h+var_90+0Ch]
0x14005bac8  lea     rcx, [rsp+0E8h+var_80]
0x14005bacd  mov     [rsp+0E8h+var_C0], rcx
0x14005bad2  mov     [rsp+0E8h+var_C8], r14
0x14005bad7  mov     r9b, r12b
0x14005bada  mov     rdx, rdi
0x14005badd  mov     rcx, [rsi+8]
0x14005bae1  call    cs:__imp_RtlCopyBufferToMdlFromMode
0x14005bae8  nop     dword ptr [rax+rax+00h]
0x14005baed  mov     [rsp+0E8h+var_A8], eax
0x14005baf1  mov     eax, [rsp+0E8h+var_A8]
0x14005baf5  test    eax, eax
0x14005baf7  js      short loc_14005BB06
0x14005baf9  mov     rax, [rsp+0E8h+var_80]
0x14005bafe  mov     [r13+0], rax
0x14005bb02  add     [rsi+38h], rax
0x14005bb06  mov     edi, [rsp+0E8h+var_A8]
0x14005bb0a  jmp     short loc_14005BB27
0x14005bb0c  mov     edi, [rsp+0E8h+var_A8]
0x14005bb10  mov     rsi, [rsp+0E8h+Irql]
0x14005bb18  mov     r15, [rsp+0E8h+var_58]
0x14005bb20  jmp     short loc_14005BB27
0x14005bb22  mov     edi, 0C000000Dh
0x14005bb27  test    edi, edi
0x14005bb29  js      short loc_14005BB44
0x14005bb2b  mov     ecx, dword ptr [rsp+0E8h+var_90+8]
0x14005bb2f  cmp     ecx, 103h
0x14005bb35  jz      short loc_14005BB44
0x14005bb37  call    AfdValidateStatus
0x14005bb3c  mov     [rsi+30h], eax
0x14005bb3f  jmp     loc_14005BC0E
0x14005bb44  lea     rcx, [r15+38h]; SpinLock
0x14005bb48  lea     rdx, [rsp+0E8h+LockHandle]; LockHandle
0x14005bb50  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005bb57  nop     dword ptr [rax+rax+00h]
0x14005bb5c  lea     rax, AfdSanCancelRequest
0x14005bb63  xchg    rax, [rsi+68h]
0x14005bb67  cmp     byte ptr [rsi+44h], 0
0x14005bb6b  jnz     short loc_14005BBB9
0x14005bb6d  cmp     byte ptr [r15+0A1h], 0
0x14005bb75  jnz     short loc_14005BBB9
0x14005bb77  lea     rcx, [r15+80h]
0x14005bb7e  mov     rdx, [rcx]
0x14005bb81  cmp     [rdx+8], rcx
0x14005bb85  jz      short loc_14005BB8E
0x14005bb87  mov     ecx, 3
0x14005bb8c  int     29h; Win8: RtlFailFast(ecx)
0x14005bb8e  lea     rax, [rsi+0A8h]
0x14005bb95  mov     [rax], rdx
0x14005bb98  mov     [rax+8], rcx
0x14005bb9c  mov     [rdx+8], rax
0x14005bba0  mov     [rcx], rax
0x14005bba3  lea     rcx, [rsp+0E8h+LockHandle]; LockHandle
0x14005bbab  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005bbb2  nop     dword ptr [rax+rax+00h]
0x14005bbb7  jmp     short loc_14005BC2A
0x14005bbb9  lea     rcx, [rsp+0E8h+LockHandle]; LockHandle
0x14005bbc1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005bbc8  nop     dword ptr [rax+rax+00h]
0x14005bbcd  xor     eax, eax
0x14005bbcf  xchg    rax, [rsi+68h]
0x14005bbd3  test    rax, rax
0x14005bbd6  jnz     short loc_14005BC06
0x14005bbd8  mov     byte ptr [rsp+0E8h+Irql], al
0x14005bbdf  lea     rcx, [rsp+0E8h+Irql]; Irql
0x14005bbe7  call    cs:__imp_IoAcquireCancelSpinLock
0x14005bbee  nop     dword ptr [rax+rax+00h]
0x14005bbf3  mov     cl, byte ptr [rsp+0E8h+Irql]; Irql
0x14005bbfa  call    cs:__imp_IoReleaseCancelSpinLock
0x14005bc01  nop     dword ptr [rax+rax+00h]
0x14005bc06  mov     edi, 0C0000120h
0x14005bc0b  mov     [rsi+30h], edi
0x14005bc0e  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14005bc14  mov     rcx, rsi; Irp
0x14005bc17  call    cs:__imp_IofCompleteRequest
0x14005bc1e  nop     dword ptr [rax+rax+00h]
0x14005bc23  jmp     short loc_14005BC2A
0x14005bc25  mov     edi, 0C0000120h
0x14005bc2a  mov     rcx, [rsp+0E8h+Object]; Object
0x14005bc2f  call    cs:__imp_ObfDereferenceObject
0x14005bc36  nop     dword ptr [rax+rax+00h]
0x14005bc3b  mov     eax, edi
0x14005bc3d  jmp     short loc_14005BC43
0x14005bc3f  mov     eax, [rsp+0E8h+var_A8]
0x14005bc43  add     rsp, 0B8h
0x14005bc4a  pop     r15
0x14005bc4c  pop     r14
0x14005bc4e  pop     r13
0x14005bc50  pop     r12
0x14005bc52  pop     rdi
0x14005bc53  pop     rsi
0x14005bc54  retn
0x14007428e  push    rbp
0x140074290  sub     rsp, 40h
0x140074294  mov     rbp, rdx
0x140074297  mov     r8, rcx
0x14007429a  lea     r9, [rbp+40h]
0x14007429e  mov     edx, 8B3h
0x1400742a3  lea     rcx, aMinioSocketsWi_11; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
  ... truncated ...
```
