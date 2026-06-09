# AfdRioConnectedReceiveEventHandler

- ea: `0x140044090`
- end: `0x14004448a`
- name: `AfdRioConnectedReceiveEventHandler`
- size: `1018`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400063e8`
- `0x140006f78`
- `0x140014460`
- `0x140044090`
- `0x140044490`
- `0x140072840`
- `0x140072870`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140044445`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140044445`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140044129`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140044129`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044453`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044453`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044137`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044137`
- `NETIO!RtlCopyMdlToMdl` at `0x1400442ef`
- `NETIO!RtlCopyMdlToMdl` at `0x1400442ef`

## pseudocode

```c
__int64 __fastcall AfdRioConnectedReceiveEventHandler(__int64 a1, int *a2)
{
  int v4; // eax
  __int64 **v6; // rsi
  unsigned __int64 v7; // r15
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
  unsigned int v31; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v32; // [rsp+58h] [rbp-A8h]
  __int64 v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+68h] [rbp-98h]
  unsigned __int64 v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  int *v37; // [rsp+80h] [rbp-80h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v39[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+C0h] [rbp-40h]
  _DWORD v41[20]; // [rsp+D0h] [rbp-30h] BYREF

  v37 = a2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(v41, 0, 0x48u);
  v40 = 0;
  v4 = *a2;
  memset(v39, 0, sizeof(v39));
  if ( (v4 & 1) != 0 )
    return 0;
  v6 = (__int64 **)*((_QWORD *)a2 + 2);
  v7 = *(_QWORD *)(a1 + 8);
  v34 = v4 & 8;
  v8 = 0;
  v9 = *((unsigned int *)v6 + 4);
  v10 = (KSPIN_LOCK *)(v7 + 56);
  v32 = (unsigned __int64)v6[3];
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
      v33 = v9;
      v13 = *(volatile __int32 **)(v11 + 128);
      v14 = 0;
      v35 = 0;
      v15 = 0;
      while ( 2 )
      {
        v16 = v32;
        do
        {
          v36 = 0;
          if ( !v16 )
          {
            v6 = (__int64 **)*v6;
            if ( !v6 )
            {
              if ( v15 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(v15 + 36));
                if ( (v41[15] & 4) == 0 )
                {
                  _InterlockedExchange(v13, v14);
                  v27 = AfdRioQueueReceiveCompletion((int)v11 + 112, (unsigned int)v41, *(_QWORD *)(v11 + 24), v7, 0);
                  if ( v27 < 0 && *(int *)(v11 + 16) >= 0 )
                    *(_DWORD *)(v11 + 16) = v27;
                }
                AfdRioDereferenceRequestBuffers(v11, v41, v39);
              }
              goto LABEL_53;
            }
            v32 = (unsigned __int64)v6[3];
            v33 = *((unsigned int *)v6 + 4);
          }
          if ( !v15 )
          {
            v17 = v37;
            for ( i = 0; ; i = 1 )
            {
              v19 = *(unsigned int *)v13;
              v20 = *(_DWORD *)(v11 + 136);
              v21 = *((_DWORD *)v13 + 1);
              v31 = v20;
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
            RtlCopyVolatileMemory(v41, (const void *)&v13[16 * v19 + 4 + 2 * v19], 0x48u);
            v31 = ((int)v19 + 1) % v31;
            if ( *(_DWORD *)(v11 + 148) < v41[2] )
            {
              if ( (unsigned __int8)AfdRioValidateAndReferenceRequestBuffers(v11, v41, 0, v39) )
              {
                v15 = v40;
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
            AFDETW_TRACERECV(0, 4163, v7, 0, 1, 0, v41[2], 0, v11 + 112, 1);
            if ( !v22 )
            {
              v14 = v31;
              goto LABEL_29;
            }
            _InterlockedExchange(v13, v31);
            if ( *(int *)(v11 + 16) >= 0 )
              *(_DWORD *)(v11 + 16) = v22;
            v26 = AfdRioQueueReceiveCompletion((int)v11 + 112, (unsigned int)v41, *(_QWORD *)(v11 + 24), v7, v22);
            if ( v26 < 0 )
            {
              v28 = *(int *)(v11 + 16) < 0;
              goto LABEL_51;
            }
            goto LABEL_53;
          }
LABEL_29:
          v23 = *(_DWORD *)(v11 + 148);
          v24 = (unsigned int)(v41[2] - v23);
          if ( v32 < v24 )
            v24 = v32;
          RtlCopyMdlToMdl(v6[1], v33, *(_QWORD *)v15, (unsigned int)(v23 + v41[1]), v24, &v36);
          v12 = v36 + v35;
          v33 += v36;
          v16 = v32 - v36;
          *(_DWORD *)(v11 + 148) += v36;
          v25 = *(_DWORD *)(v11 + 148);
          v35 = v12;
          v32 = v16;
        }
        while ( v25 != v41[2] );
        LODWORD(v30) = 0;
        _InterlockedExchange(v13, v14);
        _InterlockedDecrement((volatile signed __int32 *)(v15 + 36));
        v31 = AfdRioQueueReceiveCompletion((int)v11 + 112, (unsigned int)v41, *(_QWORD *)(v11 + 24), v7, v30);
        AfdRioDereferenceRequestBuffers(v11, v41, v39);
        v26 = v31;
        v15 = 0;
        if ( (v31 & 0x80000000) == 0 )
        {
          v12 = v35;
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
  if ( v34 )
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  else
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  return v8;
}

```

## disassembly

```asm
0x140044090  mov     [rsp-8+arg_10], rbx
0x140044095  push    rbp
0x140044096  push    rsi
0x140044097  push    rdi
0x140044098  push    r12
0x14004409a  push    r13
0x14004409c  push    r14
0x14004409e  push    r15
0x1400440a0  lea     rbp, [rsp-30h]
0x1400440a5  sub     rsp, 130h
0x1400440ac  mov     rax, cs:__security_cookie
0x1400440b3  xor     rax, rsp
0x1400440b6  mov     [rbp+60h+var_40], rax
0x1400440ba  xor     eax, eax
0x1400440bc  mov     [rbp+60h+var_E0], rdx
0x1400440c0  mov     rbx, rdx
0x1400440c3  mov     qword ptr [rbp+60h+LockHandle.OldIrql], rax
0x1400440c7  mov     r15, rcx
0x1400440ca  xorps   xmm0, xmm0
0x1400440cd  xor     edx, edx; Val
0x1400440cf  lea     rcx, [rbp+60h+var_90]; void *
0x1400440d3  lea     r8d, [rax+48h]; Size
0x1400440d7  movups  xmmword ptr [rbp+60h+LockHandle.LockQueue.Next], xmm0
0x1400440db  call    memset
0x1400440e0  xor     eax, eax
0x1400440e2  xorps   xmm0, xmm0
0x1400440e5  mov     [rbp+60h+var_A0], rax
0x1400440e9  mov     eax, [rbx]
0x1400440eb  movups  [rbp+60h+var_C0], xmm0
0x1400440ef  movups  [rbp+60h+var_B0], xmm0
0x1400440f3  test    al, 1
0x1400440f5  jz      short loc_1400440FE
0x1400440f7  xor     eax, eax
0x1400440f9  jmp     loc_140044462
0x1400440fe  mov     rsi, [rbx+10h]
0x140044102  lea     rdx, [rbp+60h+LockHandle]; LockHandle
0x140044106  mov     r15, [r15+8]
0x14004410a  and     eax, 8
0x14004410d  mov     [rsp+160h+var_F8], eax
0x140044111  mov     r13d, 0
0x140044117  mov     rax, [rsi+18h]
0x14004411b  mov     edi, [rsi+10h]
0x14004411e  lea     rcx, [r15+38h]; SpinLock
0x140044122  mov     [rsp+160h+var_108], rax
0x140044127  jz      short loc_140044137
0x140044129  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140044130  nop     dword ptr [rax+rax+00h]
0x140044135  jmp     short loc_140044143
0x140044137  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004413e  nop     dword ptr [rax+rax+00h]
0x140044143  test    dword ptr [r15+8], 840h
0x14004414b  jnz     loc_14004443A
0x140044151  mov     rbx, [r15+50h]
0x140044155  test    rbx, rbx
0x140044158  jnz     short loc_140044165
0x14004415a  mov     r13d, 0C000021Bh
0x140044160  jmp     loc_14004443A
0x140044165  xor     edx, edx
0x140044167  mov     [rsp+160h+var_100], rdi
0x14004416c  mov     rdi, [rbx+80h]
0x140044173  xor     r14d, r14d
0x140044176  mov     [rsp+160h+var_F0], rdx
0x14004417b  xor     r12d, r12d
0x14004417e  mov     rcx, [rsp+160h+var_108]
0x140044183  mov     [rsp+160h+var_E8], r13
0x140044188  test    rcx, rcx
0x14004418b  jnz     short loc_1400441AA
0x14004418d  mov     rsi, [rsi]
0x140044190  test    rsi, rsi
0x140044193  jz      loc_140044385
0x140044199  mov     rax, [rsi+18h]
0x14004419d  mov     [rsp+160h+var_108], rax
0x1400441a2  mov     eax, [rsi+10h]
0x1400441a5  mov     [rsp+160h+var_100], rax
0x1400441aa  test    r12, r12
0x1400441ad  jnz     loc_1400442B6
0x1400441b3  mov     rcx, [rbp+60h+var_E0]
0x1400441b7  xor     r9b, r9b
0x1400441ba  mov     r14d, [rdi]
0x1400441bd  mov     eax, [rbx+88h]
0x1400441c3  mov     r8d, [rdi+4]
0x1400441c7  mov     [rsp+160h+var_110], eax
0x1400441cb  cmp     r14d, eax
0x1400441ce  jnb     loc_140044422
0x1400441d4  cmp     r8d, eax
0x1400441d7  jnb     loc_140044422
0x1400441dd  cmp     r8d, r14d
0x1400441e0  jnz     short loc_14004420A
0x1400441e2  test    r9b, r9b
0x1400441e5  jnz     loc_1400443D5
0x1400441eb  cmp     rdx, [rcx+18h]
0x1400441ef  jnb     loc_14004443A
0x1400441f5  mov     rax, [rbx+80h]
0x1400441fc  mov     byte ptr [rax+8], 1
0x140044200  lock or [rsp+160h+var_160], r13d
0x140044205  mov     r9b, 1
0x140044208  jmp     short loc_1400441BA
0x14004420a  lea     rcx, ds:2[r14*8]
0x140044212  mov     r8d, 48h ; 'H'; Size
0x140044218  add     rcx, r14
0x14004421b  lea     rdx, [rdi+rcx*8]; Src
0x14004421f  lea     rcx, [rbp+60h+var_90]; void *
0x140044223  call    RtlCopyVolatileMemory
0x140044228  xor     edx, edx
0x14004422a  lea     eax, [r14+1]
0x14004422e  div     [rsp+160h+var_110]
0x140044232  mov     eax, [rbp+60h+var_88]
0x140044235  mov     [rsp+160h+var_110], edx
0x140044239  cmp     [rbx+94h], eax
0x14004423f  jb      short loc_140044249
0x140044241  mov     r14d, 0C0000232h
0x140044247  jmp     short loc_14004426F
0x140044249  lea     r9, [rbp+60h+var_C0]
0x14004424d  xor     r8d, r8d
0x140044250  lea     rdx, [rbp+60h+var_90]
0x140044254  mov     rcx, rbx
0x140044257  call    AfdRioValidateAndReferenceRequestBuffers
0x14004425c  test    al, al
0x14004425e  jnz     short loc_140044268
0x140044260  mov     r14d, 0C000000Dh
0x140044266  jmp     short loc_14004426F
0x140044268  mov     r12, [rbp+60h+var_A0]
0x14004426c  xor     r14d, r14d
0x14004426f  mov     [rsp+160h+var_118], 1
0x140044274  lea     rax, [rbx+70h]
0x140044278  mov     [rsp+160h+var_120], rax
0x14004427d  xor     r9d, r9d
0x140044280  mov     eax, [rbp+60h+var_88]
0x140044283  mov     r8, r15
0x140044286  mov     [rsp+160h+var_128], r13d
0x14004428b  mov     edx, 1043h
0x140044290  mov     [rsp+160h+var_130], eax
0x140044294  xor     ecx, ecx
0x140044296  mov     [rsp+160h+var_138], r13
0x14004429b  mov     dword ptr [rsp+160h+var_140], 1
0x1400442a3  call    AFDETW_TRACERECV
0x1400442a8  test    r14d, r14d
0x1400442ab  jnz     loc_1400443EF
0x1400442b1  mov     r14d, [rsp+160h+var_110]
0x1400442b6  mov     edx, [rbp+60h+var_88]
0x1400442b9  lea     rax, [rsp+160h+var_E8]
0x1400442be  mov     ecx, [rbx+94h]
0x1400442c4  sub     edx, ecx
0x1400442c6  cmp     [rsp+160h+var_108], rdx
0x1400442cb  mov     r9d, [rbp+60h+var_8C]
0x1400442cf  cmovb   rdx, [rsp+160h+var_108]
0x1400442d5  add     r9d, ecx
0x1400442d8  mov     r8, [r12]
0x1400442dc  mov     rcx, [rsi+8]
0x1400442e0  mov     [rsp+160h+var_138], rax
0x1400442e5  mov     [rsp+160h+var_140], rdx
0x1400442ea  mov     rdx, [rsp+160h+var_100]
0x1400442ef  call    cs:__imp_RtlCopyMdlToMdl
0x1400442f6  nop     dword ptr [rax+rax+00h]
0x1400442fb  mov     rax, [rsp+160h+var_E8]
0x140044300  mov     rdx, [rsp+160h+var_F0]
0x140044305  mov     rcx, [rsp+160h+var_108]
0x14004430a  add     rdx, rax
0x14004430d  add     [rsp+160h+var_100], rax
0x140044312  sub     rcx, rax
0x140044315  add     [rbx+94h], eax
0x14004431b  mov     eax, [rbx+94h]
0x140044321  mov     [rsp+160h+var_F0], rdx
0x140044326  mov     [rsp+160h+var_108], rcx
0x14004432b  cmp     eax, [rbp+60h+var_88]
0x14004432e  jnz     loc_140044183
0x140044334  mov     eax, r14d
0x140044337  mov     dword ptr [rsp+160h+var_140], r13d
0x14004433c  xchg    eax, [rdi]
0x14004433e  lock dec dword ptr [r12+24h]
0x140044344  lea     rdx, [rbp+60h+var_90]
0x140044348  mov     r8, [rbx+18h]
0x14004434c  lea     rcx, [rbx+70h]
0x140044350  mov     r9, r15
0x140044353  call    AfdRioQueueReceiveCompletion
0x140044358  lea     r8, [rbp+60h+var_C0]
0x14004435c  mov     [rsp+160h+var_110], eax
0x140044360  lea     rdx, [rbp+60h+var_90]
0x140044364  mov     rcx, rbx
0x140044367  call    AfdRioDereferenceRequestBuffers
0x14004436c  mov     eax, [rsp+160h+var_110]
0x140044370  xor     r12d, r12d
0x140044373  test    eax, eax
0x140044375  js      loc_140044431
0x14004437b  mov     rdx, [rsp+160h+var_F0]
0x140044380  jmp     loc_14004417E
0x140044385  test    r12, r12
0x140044388  jz      loc_14004443A
0x14004438e  lock dec dword ptr [r12+24h]
0x140044394  test    [rbp+60h+var_54], 4
0x140044398  jnz     short loc_1400443C3
0x14004439a  xchg    r14d, [rdi]
0x14004439d  mov     r8, [rbx+18h]
0x1400443a1  lea     rdx, [rbp+60h+var_90]
0x1400443a5  mov     r9, r15
0x1400443a8  mov     dword ptr [rsp+160h+var_140], r13d
0x1400443ad  lea     rcx, [rbx+70h]
0x1400443b1  call    AfdRioQueueReceiveCompletion
0x1400443b6  test    eax, eax
0x1400443b8  jns     short loc_1400443C3
0x1400443ba  cmp     [rbx+10h], r13d
0x1400443be  jl      short loc_1400443C3
0x1400443c0  mov     [rbx+10h], eax
0x1400443c3  lea     r8, [rbp+60h+var_C0]
0x1400443c7  mov     rcx, rbx
0x1400443ca  lea     rdx, [rbp+60h+var_90]
0x1400443ce  call    AfdRioDereferenceRequestBuffers
0x1400443d3  jmp     short loc_14004443A
0x1400443d5  test    rdx, rdx
0x1400443d8  jnz     short loc_1400443E2
0x1400443da  mov     r13d, 0C000021Bh
0x1400443e0  jmp     short loc_1400443E6
0x1400443e2  mov     [rcx+20h], rdx
0x1400443e6  mov     byte ptr [rbx+90h], 1
0x1400443ed  jmp     short loc_14004443A
0x1400443ef  mov     eax, [rsp+160h+var_110]
0x1400443f3  xchg    eax, [rdi]
0x1400443f5  cmp     [rbx+10h], r13d
0x1400443f9  jl      short loc_1400443FF
0x1400443fb  mov     [rbx+10h], r14d
0x1400443ff  mov     r8, [rbx+18h]
0x140044403  lea     rdx, [rbp+60h+var_90]
0x140044407  mov     r9, r15
0x14004440a  mov     dword ptr [rsp+160h+var_140], r14d
0x14004440f  lea     rcx, [rbx+70h]
0x140044413  call    AfdRioQueueReceiveCompletion
0x140044418  test    eax, eax
0x14004441a  jns     short loc_14004443A
0x14004441c  cmp     [rbx+10h], r13d
0x140044420  jmp     short loc_140044435
0x140044422  cmp     [rbx+10h], r13d
0x140044426  jl      short loc_14004443A
0x140044428  mov     dword ptr [rbx+10h], 0C0000232h
0x14004442f  jmp     short loc_14004443A
0x140044431  cmp     [rbx+10h], r12d
0x140044435  jl      short loc_14004443A
0x140044437  mov     [rbx+10h], eax
0x14004443a  cmp     [rsp+160h+var_F8], 0
0x14004443f  lea     rcx, [rbp+60h+LockHandle]; LockHandle
0x140044443  jz      short loc_140044453
0x140044445  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14004444c  nop     dword ptr [rax+rax+00h]
0x140044451  jmp     short loc_14004445F
0x140044453  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004445a  nop     dword ptr [rax+rax+00h]
0x14004445f  mov     eax, r13d
0x140044462  mov     rcx, [rbp+60h+var_40]
0x140044466  xor     rcx, rsp; StackCookie
0x140044469  call    __security_check_cookie
0x14004446e  mov     rbx, [rsp+160h+arg_10]
0x140044476  add     rsp, 130h
0x14004447d  pop     r15
0x14004447f  pop     r14
0x140044481  pop     r13
0x140044483  pop     r12
0x140044485  pop     rdi
0x140044486  pop     rsi
0x140044487  pop     rbp
0x140044488  retn
```
