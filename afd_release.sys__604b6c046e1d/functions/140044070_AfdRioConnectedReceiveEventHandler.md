# AfdRioConnectedReceiveEventHandler

- ea: `0x140044070`
- end: `0x14004446a`
- name: `AfdRioConnectedReceiveEventHandler`
- size: `1018`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400063e8`
- `0x140006f78`
- `0x140014460`
- `0x140044070`
- `0x140044470`
- `0x1400726a0`
- `0x1400726d0`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140044425`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140044425`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140044109`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140044109`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044433`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044433`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044117`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044117`
- `NETIO!RtlCopyMdlToMdl` at `0x1400442cf`
- `NETIO!RtlCopyMdlToMdl` at `0x1400442cf`

## pseudocode

```c
__int64 __fastcall AfdRioConnectedReceiveEventHandler(__int64 a1, int *a2)
{
  int v4; // eax
  __int64 **v6; // rsi
  __int64 v7; // r15
  unsigned int v8; // r13d
  __int64 v9; // rdi
  KSPIN_LOCK *v10; // rcx
  __int64 v11; // rbx
  unsigned __int64 v12; // rdx
  volatile __int32 *v13; // rdi
  __int32 v14; // r14d
  __int64 v15; // r12
  unsigned __int64 v16; // rcx
  int *v17; // rcx
  char i; // r9
  __int64 v19; // r14
  unsigned int v20; // eax
  unsigned int v21; // r8d
  int v22; // r14d
  int v23; // ecx
  unsigned __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  bool v28; // sf
  signed __int32 v29[8]; // [rsp+0h] [rbp-100h] BYREF
  __int64 v30; // [rsp+20h] [rbp-E0h]
  __int64 v31; // [rsp+48h] [rbp-B8h]
  unsigned __int32 v32; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  int v35; // [rsp+68h] [rbp-98h]
  unsigned __int64 v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  int *v38; // [rsp+80h] [rbp-80h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v40[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+C0h] [rbp-40h]
  unsigned int v42[20]; // [rsp+D0h] [rbp-30h] BYREF

  v38 = a2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(v42, 0, 0x48u);
  v41 = 0;
  v4 = *a2;
  memset(v40, 0, sizeof(v40));
  if ( (v4 & 1) != 0 )
    return 0;
  v6 = (__int64 **)*((_QWORD *)a2 + 2);
  v7 = *(_QWORD *)(a1 + 8);
  v35 = v4 & 8;
  v8 = 0;
  v9 = *((unsigned int *)v6 + 4);
  v10 = (KSPIN_LOCK *)(v7 + 56);
  v33 = (unsigned __int64)v6[3];
  if ( (v4 & 8) != 0 )
    KeAcquireInStackQueuedSpinLockAtDpcLevel(v10, &LockHandle);
  else
    KeAcquireInStackQueuedSpinLock(v10, &LockHandle);
  if ( (*(_DWORD *)(v7 + 8) & 0x840) == 0 )
  {
    v11 = *(_QWORD *)(v7 + 80);
    if ( v11 )
    {
      v12 = 0;
      v34 = v9;
      v13 = *(volatile __int32 **)(v11 + 128);
      v14 = 0;
      v36 = 0;
      v15 = 0;
      while ( 2 )
      {
        v16 = v33;
        do
        {
          v37 = 0;
          if ( !v16 )
          {
            v6 = (__int64 **)*v6;
            if ( !v6 )
            {
              if ( v15 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(v15 + 36));
                if ( (v42[15] & 4) == 0 )
                {
                  _InterlockedExchange(v13, v14);
                  v27 = AfdRioQueueReceiveCompletion(v11 + 112, (__int64)v42, *(_QWORD *)(v11 + 24), v7, 0);
                  if ( v27 < 0 && *(int *)(v11 + 16) >= 0 )
                    *(_DWORD *)(v11 + 16) = v27;
                }
                AfdRioDereferenceRequestBuffers(v11, v42, v40);
              }
              goto LABEL_53;
            }
            v33 = (unsigned __int64)v6[3];
            v34 = *((unsigned int *)v6 + 4);
          }
          if ( !v15 )
          {
            v17 = v38;
            for ( i = 0; ; i = 1 )
            {
              v19 = *(unsigned int *)v13;
              v20 = *(_DWORD *)(v11 + 136);
              v21 = *((_DWORD *)v13 + 1);
              v32 = v20;
              if ( (unsigned int)v19 >= v20 || v21 >= v20 )
              {
                if ( *(int *)(v11 + 16) >= 0 )
                  *(_DWORD *)(v11 + 16) = -1073741262;
                goto LABEL_53;
              }
              if ( v21 != (_DWORD)v19 )
                break;
              if ( i )
              {
                if ( v12 )
                  *((_QWORD *)v17 + 4) = v12;
                else
                  v8 = -1073741285;
                *(_BYTE *)(v11 + 144) = 1;
                goto LABEL_53;
              }
              if ( v12 >= *((_QWORD *)v17 + 3) )
                goto LABEL_53;
              *(_BYTE *)(*(_QWORD *)(v11 + 128) + 8LL) = 1;
              _InterlockedOr(v29, 0);
            }
            RtlCopyVolatileMemory(v42, (const void *)&v13[16 * v19 + 4 + 2 * v19], 0x48u);
            v32 = ((int)v19 + 1) % v32;
            if ( *(_DWORD *)(v11 + 148) < v42[2] )
            {
              if ( AfdRioValidateAndReferenceRequestBuffers((_QWORD *)v11, v42, 0, (__int64)v40) )
              {
                v15 = v41;
                v22 = 0;
              }
              else
              {
                v22 = -1073741811;
              }
            }
            else
            {
              v22 = -1073741262;
            }
            LOBYTE(v31) = 1;
            AFDETW_TRACERECV(0, 4163, v7, 0, 1, 0, v42[2], 0, v11 + 112, v31);
            if ( !v22 )
            {
              v14 = v32;
              goto LABEL_29;
            }
            _InterlockedExchange(v13, v32);
            if ( *(int *)(v11 + 16) >= 0 )
              *(_DWORD *)(v11 + 16) = v22;
            v26 = AfdRioQueueReceiveCompletion(v11 + 112, (__int64)v42, *(_QWORD *)(v11 + 24), v7, v22);
            if ( v26 < 0 )
            {
              v28 = *(int *)(v11 + 16) < 0;
              goto LABEL_51;
            }
            goto LABEL_53;
          }
LABEL_29:
          v23 = *(_DWORD *)(v11 + 148);
          v24 = v42[2] - v23;
          if ( v33 < v24 )
            v24 = v33;
          RtlCopyMdlToMdl(v6[1], v34, *(_QWORD *)v15, v23 + v42[1], v24, &v37);
          v12 = v37 + v36;
          v34 += v37;
          v16 = v33 - v37;
          *(_DWORD *)(v11 + 148) += v37;
          v25 = *(_DWORD *)(v11 + 148);
          v36 = v12;
          v33 = v16;
        }
        while ( v25 != v42[2] );
        LODWORD(v30) = 0;
        _InterlockedExchange(v13, v14);
        _InterlockedDecrement((volatile signed __int32 *)(v15 + 36));
        v32 = AfdRioQueueReceiveCompletion(v11 + 112, (__int64)v42, *(_QWORD *)(v11 + 24), v7, v30);
        AfdRioDereferenceRequestBuffers(v11, v42, v40);
        v26 = v32;
        v15 = 0;
        if ( (v32 & 0x80000000) == 0 )
        {
          v12 = v36;
          continue;
        }
        break;
      }
      v28 = *(int *)(v11 + 16) < 0;
LABEL_51:
      if ( !v28 )
        *(_DWORD *)(v11 + 16) = v26;
    }
    else
    {
      v8 = -1073741285;
    }
  }
LABEL_53:
  if ( v35 )
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  else
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  return v8;
}

```

## disassembly

```asm
0x140044070  mov     [rsp-8+arg_10], rbx
0x140044075  push    rbp
0x140044076  push    rsi
0x140044077  push    rdi
0x140044078  push    r12
0x14004407a  push    r13
0x14004407c  push    r14
0x14004407e  push    r15
0x140044080  lea     rbp, [rsp-30h]
0x140044085  sub     rsp, 130h
0x14004408c  mov     rax, cs:__security_cookie
0x140044093  xor     rax, rsp
0x140044096  mov     [rbp+60h+var_40], rax
0x14004409a  xor     eax, eax
0x14004409c  mov     [rbp+60h+var_E0], rdx
0x1400440a0  mov     rbx, rdx
0x1400440a3  mov     qword ptr [rbp+60h+LockHandle.OldIrql], rax
0x1400440a7  mov     r15, rcx
0x1400440aa  xorps   xmm0, xmm0
0x1400440ad  xor     edx, edx; Val
0x1400440af  lea     rcx, [rbp+60h+var_90]; void *
0x1400440b3  lea     r8d, [rax+48h]; Size
0x1400440b7  movups  xmmword ptr [rbp+60h+LockHandle.LockQueue.Next], xmm0
0x1400440bb  call    memset
0x1400440c0  xor     eax, eax
0x1400440c2  xorps   xmm0, xmm0
0x1400440c5  mov     [rbp+60h+var_A0], rax
0x1400440c9  mov     eax, [rbx]
0x1400440cb  movups  [rbp+60h+var_C0], xmm0
0x1400440cf  movups  [rbp+60h+var_B0], xmm0
0x1400440d3  test    al, 1
0x1400440d5  jz      short loc_1400440DE
0x1400440d7  xor     eax, eax
0x1400440d9  jmp     loc_140044442
0x1400440de  mov     rsi, [rbx+10h]
0x1400440e2  lea     rdx, [rbp+60h+LockHandle]; LockHandle
0x1400440e6  mov     r15, [r15+8]
0x1400440ea  and     eax, 8
0x1400440ed  mov     [rsp+160h+var_F8], eax
0x1400440f1  mov     r13d, 0
0x1400440f7  mov     rax, [rsi+18h]
0x1400440fb  mov     edi, [rsi+10h]
0x1400440fe  lea     rcx, [r15+38h]; SpinLock
0x140044102  mov     [rsp+160h+var_108], rax
0x140044107  jz      short loc_140044117
0x140044109  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140044110  nop     dword ptr [rax+rax+00h]
0x140044115  jmp     short loc_140044123
0x140044117  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004411e  nop     dword ptr [rax+rax+00h]
0x140044123  test    dword ptr [r15+8], 840h
0x14004412b  jnz     loc_14004441A
0x140044131  mov     rbx, [r15+50h]
0x140044135  test    rbx, rbx
0x140044138  jnz     short loc_140044145
0x14004413a  mov     r13d, 0C000021Bh
0x140044140  jmp     loc_14004441A
0x140044145  xor     edx, edx
0x140044147  mov     [rsp+160h+var_100], rdi
0x14004414c  mov     rdi, [rbx+80h]
0x140044153  xor     r14d, r14d
0x140044156  mov     [rsp+160h+var_F0], rdx
0x14004415b  xor     r12d, r12d
0x14004415e  mov     rcx, [rsp+160h+var_108]
0x140044163  mov     [rsp+160h+var_E8], r13
0x140044168  test    rcx, rcx
0x14004416b  jnz     short loc_14004418A
0x14004416d  mov     rsi, [rsi]
0x140044170  test    rsi, rsi
0x140044173  jz      loc_140044365
0x140044179  mov     rax, [rsi+18h]
0x14004417d  mov     [rsp+160h+var_108], rax
0x140044182  mov     eax, [rsi+10h]
0x140044185  mov     [rsp+160h+var_100], rax
0x14004418a  test    r12, r12
0x14004418d  jnz     loc_140044296
0x140044193  mov     rcx, [rbp+60h+var_E0]
0x140044197  xor     r9b, r9b
0x14004419a  mov     r14d, [rdi]
0x14004419d  mov     eax, [rbx+88h]
0x1400441a3  mov     r8d, [rdi+4]
0x1400441a7  mov     [rsp+160h+var_110], eax
0x1400441ab  cmp     r14d, eax
0x1400441ae  jnb     loc_140044402
0x1400441b4  cmp     r8d, eax
0x1400441b7  jnb     loc_140044402
0x1400441bd  cmp     r8d, r14d
0x1400441c0  jnz     short loc_1400441EA
0x1400441c2  test    r9b, r9b
0x1400441c5  jnz     loc_1400443B5
0x1400441cb  cmp     rdx, [rcx+18h]
0x1400441cf  jnb     loc_14004441A
0x1400441d5  mov     rax, [rbx+80h]
0x1400441dc  mov     byte ptr [rax+8], 1
0x1400441e0  lock or [rsp+160h+var_160], r13d
0x1400441e5  mov     r9b, 1
0x1400441e8  jmp     short loc_14004419A
0x1400441ea  lea     rcx, ds:2[r14*8]
0x1400441f2  mov     r8d, 48h ; 'H'; Size
0x1400441f8  add     rcx, r14
0x1400441fb  lea     rdx, [rdi+rcx*8]; Src
0x1400441ff  lea     rcx, [rbp+60h+var_90]; void *
0x140044203  call    RtlCopyVolatileMemory
0x140044208  xor     edx, edx
0x14004420a  lea     eax, [r14+1]
0x14004420e  div     [rsp+160h+var_110]
0x140044212  mov     eax, [rbp+60h+var_88]
0x140044215  mov     [rsp+160h+var_110], edx
0x140044219  cmp     [rbx+94h], eax
0x14004421f  jb      short loc_140044229
0x140044221  mov     r14d, 0C0000232h
0x140044227  jmp     short loc_14004424F
0x140044229  lea     r9, [rbp+60h+var_C0]
0x14004422d  xor     r8d, r8d
0x140044230  lea     rdx, [rbp+60h+var_90]
0x140044234  mov     rcx, rbx
0x140044237  call    AfdRioValidateAndReferenceRequestBuffers
0x14004423c  test    al, al
0x14004423e  jnz     short loc_140044248
0x140044240  mov     r14d, 0C000000Dh
0x140044246  jmp     short loc_14004424F
0x140044248  mov     r12, [rbp+60h+var_A0]
0x14004424c  xor     r14d, r14d
0x14004424f  mov     byte ptr [rsp+160h+var_118], 1
0x140044254  lea     rax, [rbx+70h]
0x140044258  mov     [rsp+160h+var_120], rax
0x14004425d  xor     r9d, r9d
0x140044260  mov     eax, [rbp+60h+var_88]
0x140044263  mov     r8, r15
0x140044266  mov     [rsp+160h+var_128], r13d
0x14004426b  mov     edx, 1043h
0x140044270  mov     [rsp+160h+var_130], eax
0x140044274  xor     ecx, ecx
0x140044276  mov     [rsp+160h+var_138], r13
0x14004427b  mov     dword ptr [rsp+160h+var_140], 1
0x140044283  call    AFDETW_TRACERECV
0x140044288  test    r14d, r14d
0x14004428b  jnz     loc_1400443CF
0x140044291  mov     r14d, [rsp+160h+var_110]
0x140044296  mov     edx, [rbp+60h+var_88]
0x140044299  lea     rax, [rsp+160h+var_E8]
0x14004429e  mov     ecx, [rbx+94h]
0x1400442a4  sub     edx, ecx
0x1400442a6  cmp     [rsp+160h+var_108], rdx
0x1400442ab  mov     r9d, [rbp+60h+var_8C]
0x1400442af  cmovb   rdx, [rsp+160h+var_108]
0x1400442b5  add     r9d, ecx
0x1400442b8  mov     r8, [r12]
0x1400442bc  mov     rcx, [rsi+8]
0x1400442c0  mov     [rsp+160h+var_138], rax
0x1400442c5  mov     [rsp+160h+var_140], rdx
0x1400442ca  mov     rdx, [rsp+160h+var_100]
0x1400442cf  call    cs:__imp_RtlCopyMdlToMdl
0x1400442d6  nop     dword ptr [rax+rax+00h]
0x1400442db  mov     rax, [rsp+160h+var_E8]
0x1400442e0  mov     rdx, [rsp+160h+var_F0]
0x1400442e5  mov     rcx, [rsp+160h+var_108]
0x1400442ea  add     rdx, rax
0x1400442ed  add     [rsp+160h+var_100], rax
0x1400442f2  sub     rcx, rax
0x1400442f5  add     [rbx+94h], eax
0x1400442fb  mov     eax, [rbx+94h]
0x140044301  mov     [rsp+160h+var_F0], rdx
0x140044306  mov     [rsp+160h+var_108], rcx
0x14004430b  cmp     eax, [rbp+60h+var_88]
0x14004430e  jnz     loc_140044163
0x140044314  mov     eax, r14d
0x140044317  mov     dword ptr [rsp+160h+var_140], r13d
0x14004431c  xchg    eax, [rdi]
0x14004431e  lock dec dword ptr [r12+24h]
0x140044324  lea     rdx, [rbp+60h+var_90]
0x140044328  mov     r8, [rbx+18h]
0x14004432c  lea     rcx, [rbx+70h]
0x140044330  mov     r9, r15
0x140044333  call    AfdRioQueueReceiveCompletion
0x140044338  lea     r8, [rbp+60h+var_C0]
0x14004433c  mov     [rsp+160h+var_110], eax
0x140044340  lea     rdx, [rbp+60h+var_90]
0x140044344  mov     rcx, rbx
0x140044347  call    AfdRioDereferenceRequestBuffers
0x14004434c  mov     eax, [rsp+160h+var_110]
0x140044350  xor     r12d, r12d
0x140044353  test    eax, eax
0x140044355  js      loc_140044411
0x14004435b  mov     rdx, [rsp+160h+var_F0]
0x140044360  jmp     loc_14004415E
0x140044365  test    r12, r12
0x140044368  jz      loc_14004441A
0x14004436e  lock dec dword ptr [r12+24h]
0x140044374  test    [rbp+60h+var_54], 4
0x140044378  jnz     short loc_1400443A3
0x14004437a  xchg    r14d, [rdi]
0x14004437d  mov     r8, [rbx+18h]
0x140044381  lea     rdx, [rbp+60h+var_90]
0x140044385  mov     r9, r15
0x140044388  mov     dword ptr [rsp+160h+var_140], r13d
0x14004438d  lea     rcx, [rbx+70h]
0x140044391  call    AfdRioQueueReceiveCompletion
0x140044396  test    eax, eax
0x140044398  jns     short loc_1400443A3
0x14004439a  cmp     [rbx+10h], r13d
0x14004439e  jl      short loc_1400443A3
0x1400443a0  mov     [rbx+10h], eax
0x1400443a3  lea     r8, [rbp+60h+var_C0]
0x1400443a7  mov     rcx, rbx
0x1400443aa  lea     rdx, [rbp+60h+var_90]
0x1400443ae  call    AfdRioDereferenceRequestBuffers
0x1400443b3  jmp     short loc_14004441A
0x1400443b5  test    rdx, rdx
0x1400443b8  jnz     short loc_1400443C2
0x1400443ba  mov     r13d, 0C000021Bh
0x1400443c0  jmp     short loc_1400443C6
0x1400443c2  mov     [rcx+20h], rdx
0x1400443c6  mov     byte ptr [rbx+90h], 1
0x1400443cd  jmp     short loc_14004441A
0x1400443cf  mov     eax, [rsp+160h+var_110]
0x1400443d3  xchg    eax, [rdi]
0x1400443d5  cmp     [rbx+10h], r13d
0x1400443d9  jl      short loc_1400443DF
0x1400443db  mov     [rbx+10h], r14d
0x1400443df  mov     r8, [rbx+18h]
0x1400443e3  lea     rdx, [rbp+60h+var_90]
0x1400443e7  mov     r9, r15
0x1400443ea  mov     dword ptr [rsp+160h+var_140], r14d
0x1400443ef  lea     rcx, [rbx+70h]
0x1400443f3  call    AfdRioQueueReceiveCompletion
0x1400443f8  test    eax, eax
0x1400443fa  jns     short loc_14004441A
0x1400443fc  cmp     [rbx+10h], r13d
0x140044400  jmp     short loc_140044415
0x140044402  cmp     [rbx+10h], r13d
0x140044406  jl      short loc_14004441A
0x140044408  mov     dword ptr [rbx+10h], 0C0000232h
0x14004440f  jmp     short loc_14004441A
0x140044411  cmp     [rbx+10h], r12d
0x140044415  jl      short loc_14004441A
0x140044417  mov     [rbx+10h], eax
0x14004441a  cmp     [rsp+160h+var_F8], 0
0x14004441f  lea     rcx, [rbp+60h+LockHandle]; LockHandle
0x140044423  jz      short loc_140044433
0x140044425  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14004442c  nop     dword ptr [rax+rax+00h]
0x140044431  jmp     short loc_14004443F
0x140044433  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004443a  nop     dword ptr [rax+rax+00h]
0x14004443f  mov     eax, r13d
0x140044442  mov     rcx, [rbp+60h+var_40]
0x140044446  xor     rcx, rsp; StackCookie
0x140044449  call    __security_check_cookie
0x14004444e  mov     rbx, [rsp+160h+arg_10]
0x140044456  add     rsp, 130h
0x14004445d  pop     r15
0x14004445f  pop     r14
0x140044461  pop     r13
0x140044463  pop     r12
0x140044465  pop     rdi
0x140044466  pop     rsi
0x140044467  pop     rbp
0x140044468  retn
```
