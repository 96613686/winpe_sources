# CInputHostLayout::_QueueNotification(IHM_NOTIFICATION_DATA const *)

- ea: `0x1800857c4`
- end: `0x180085ab8`
- name: `?_QueueNotification@CInputHostLayout@@AEAAJPEBUIHM_NOTIFICATION_DATA@@@Z`
- size: `756`
- prototype: `__int64 __fastcall(CInputHostLayout *__hidden this, const struct IHM_NOTIFICATION_DATA *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180085660`
- `0x1802622c0`

## callees

- `0x180009dd0`
- `0x1800112b0`
- `0x180018c80`
- `0x1800857c4`
- `0x180085ac0`
- `0x180085b98`
- `0x180142e10`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800857f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180085904`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800857f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180085904`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800858a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008593f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800858a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008593f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180085966`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180085966`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1800859c2`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1800859d6`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1800859ea`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1800859c2`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1800859d6`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1800859ea`

## pseudocode

```c
__int64 __fastcall CInputHostLayout::_QueueNotification(CInputHostLayout *this, const RECT *a2)
{
  RTL_SRWLOCK *v2; // r13
  __int64 v5; // rbx
  _QWORD *v6; // rdi
  unsigned __int64 v7; // r14
  int v8; // ebx
  __int64 v9; // rdx
  struct IPerWindowNotificationQueue **v10; // rdx
  struct IPerWindowNotificationQueue *v11; // rcx
  struct IPerWindowNotificationQueue *v12; // rcx
  __int64 v14; // rdx
  volatile int *v15; // rdx
  struct IPerWindowNotificationQueue *v16; // r14
  unsigned __int64 v17; // r12
  unsigned __int64 i; // r14
  RECT *v19; // rdx
  struct IPerWindowNotificationQueue *v20; // [rsp+20h] [rbp-50h] BYREF
  LONG bottom; // [rsp+28h] [rbp-48h] BYREF
  struct tagRECT rcDst; // [rsp+2Ch] [rbp-44h] BYREF
  struct tagRECT v23; // [rsp+3Ch] [rbp-34h] BYREF
  struct tagRECT v24; // [rsp+4Ch] [rbp-24h] BYREF
  LONG right; // [rsp+5Ch] [rbp-14h]

  v2 = (RTL_SRWLOCK *)((char *)this + 256);
  AcquireSRWLockExclusive((PSRWLOCK)this + 32);
  v5 = *(_QWORD *)&a2->left;
  v6 = (_QWORD *)((char *)this + 264);
  v7 = 0;
  v20 = 0;
  while ( v7 < *((_QWORD *)this + 34) )
  {
    if ( v5 == (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*v6 + 8 * v7) + 24LL))(*(_QWORD *)(*v6 + 8 * v7)) )
    {
      v8 = 0;
      v16 = *(struct IPerWindowNotificationQueue **)(*v6 + 8 * v7);
      if ( v20 != v16 )
      {
        if ( v16 )
          (*(void (__fastcall **)(struct IPerWindowNotificationQueue *))(*(_QWORD *)v16 + 8LL))(v16);
        v20 = v16;
      }
LABEL_23:
      bottom = a2->bottom;
      right = a2->right;
      CopyRect(&rcDst, a2 + 1);
      CopyRect(&v23, a2 + 2);
      CopyRect(&v24, a2 + 3);
      if ( a2->bottom == 1 )
      {
        v8 = (*(__int64 (__fastcall **)(struct IPerWindowNotificationQueue *, LONG *))(*(_QWORD *)v20 + 40LL))(
               v20,
               &bottom);
      }
      else
      {
        v17 = *((_QWORD *)this + 34);
        for ( i = 0; i < v17; ++i )
          (*(void (__fastcall **)(_QWORD, LONG *))(**(_QWORD **)(*v6 + 8 * i) + 40LL))(
            *(_QWORD *)(*v6 + 8 * i),
            &bottom);
      }
      goto LABEL_11;
    }
    ++v7;
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v20);
  v8 = CPerWindowNotificationQueue_CreateInstance(*(HWND *)&a2->left, &v20);
  if ( v8 >= 0 )
  {
    v9 = *((_QWORD *)this + 34);
    v8 = 0;
    if ( v9 != *((_QWORD *)this + 36)
      || (v8 = CTSimpleArray<IGestureClient *,4294967294,CTPolicyCoTaskMem<IGestureClient *>,CSimpleArrayStandardCompareHelper<IGestureClient *>,CSimpleArrayStandardMergeHelper<IGestureClient *>>::_EnsureCapacity(
                 (char *)this + 264,
                 v9 + 1),
          v8 >= 0) )
    {
      v10 = (struct IPerWindowNotificationQueue **)(*((_QWORD *)this + 33) + 8 * (*((_QWORD *)this + 34))++);
      if ( v10 )
      {
        v11 = v20;
        *v10 = v20;
        if ( v11 )
          (*(void (__fastcall **)(struct IPerWindowNotificationQueue *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    if ( v8 >= 0 )
      goto LABEL_23;
  }
LABEL_11:
  ReleaseSRWLockExclusive(v2);
  if ( v8 >= 0 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 37);
    v8 = 0;
    v14 = *((_QWORD *)this + 39);
    if ( v14 != *((_QWORD *)this + 41)
      || (v8 = CTSimpleArray<IHM_NOTIFICATION_DATA,4294967294,CTPolicyCoTaskMem<IHM_NOTIFICATION_DATA>,CSimpleArrayStandardCompareHelper<IHM_NOTIFICATION_DATA>,CSimpleArrayStandardMergeHelper<IHM_NOTIFICATION_DATA>>::_EnsureCapacity(
                 (char *)this + 304,
                 v14 + 1),
          v8 >= 0) )
    {
      v19 = (RECT *)((++*((_QWORD *)this + 39) << 6) + *((_QWORD *)this + 38) - 64LL);
      if ( v19 )
      {
        *v19 = *a2;
        v19[1] = a2[1];
        v19[2] = a2[2];
        v19[3] = a2[3];
      }
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 37);
    if ( v8 >= 0 )
    {
      Microsoft::WRL::Details::SafeUnknownIncrementReference((CInputHostLayout *)((char *)this + 156), v15);
      SubmitThreadpoolWork(*((PTP_WORK *)this + 42));
    }
  }
  v12 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(struct IPerWindowNotificationQueue *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800857c4  mov     [rsp-38h+arg_10], rbx
0x1800857c9  push    rbp
0x1800857ca  push    rsi
0x1800857cb  push    rdi
0x1800857cc  push    r12
0x1800857ce  push    r13
0x1800857d0  push    r14
0x1800857d2  push    r15
0x1800857d4  mov     rbp, rsp
0x1800857d7  sub     rsp, 70h
0x1800857db  mov     rax, cs:__security_cookie
0x1800857e2  xor     rax, rsp
0x1800857e5  mov     [rbp+var_10], rax
0x1800857e9  lea     r13, [rcx+100h]
0x1800857f0  mov     r15, rcx
0x1800857f3  mov     rcx, r13; SRWLock
0x1800857f6  mov     rsi, rdx
0x1800857f9  call    cs:__imp_AcquireSRWLockExclusive
0x180085800  nop     dword ptr [rax+rax+00h]
0x180085805  mov     rbx, [rsi]
0x180085808  lea     rdi, [r15+108h]
0x18008580f  xor     r14d, r14d
0x180085812  mov     [rbp+var_50], 0
0x18008581a  cmp     r14, [rdi+8]
0x18008581e  jnb     short loc_180085841
0x180085820  mov     rax, [rdi]
0x180085823  mov     rcx, [rax+r14*8]
0x180085827  mov     rax, [rcx]
0x18008582a  mov     rax, [rax+18h]
0x18008582e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085833  cmp     rbx, rax
0x180085836  jz      loc_180085977
0x18008583c  inc     r14
0x18008583f  jmp     short loc_18008581A
0x180085841  lea     rcx, [rbp+var_50]
0x180085845  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18008584a  mov     rcx, [rsi]; HWND
0x18008584d  lea     rdx, [rbp+var_50]; struct IPerWindowNotificationQueue **
0x180085851  call    ?CPerWindowNotificationQueue_CreateInstance@@YAJPEAUHWND__@@PEAPEAUIPerWindowNotificationQueue@@@Z; CPerWindowNotificationQueue_CreateInstance(HWND__ *,IPerWindowNotificationQueue * *)
0x180085856  mov     ebx, eax
0x180085858  test    eax, eax
0x18008585a  js      short loc_1800858A3
0x18008585c  mov     rdx, [rdi+8]
0x180085860  xor     ebx, ebx
0x180085862  cmp     rdx, [rdi+18h]
0x180085866  jz      loc_180085A5F
0x18008586c  inc     qword ptr [rdi+8]
0x180085870  mov     rdx, [rdi+8]
0x180085874  mov     rax, [rdi]
0x180085877  dec     rdx
0x18008587a  lea     rdx, [rax+rdx*8]
0x18008587e  test    rdx, rdx
0x180085881  jz      short loc_18008589B
0x180085883  mov     rcx, [rbp+var_50]
0x180085887  mov     [rdx], rcx
0x18008588a  test    rcx, rcx
0x18008588d  jz      short loc_18008589B
0x18008588f  mov     rax, [rcx]
0x180085892  mov     rax, [rax+8]
0x180085896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008589b  test    ebx, ebx
0x18008589d  jns     loc_1800859AE
0x1800858a3  mov     rcx, r13; SRWLock
0x1800858a6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800858ad  nop     dword ptr [rax+rax+00h]
0x1800858b2  test    ebx, ebx
0x1800858b4  jns     short loc_1800858FA
0x1800858b6  mov     rcx, [rbp+var_50]
0x1800858ba  test    rcx, rcx
0x1800858bd  jz      short loc_1800858D3
0x1800858bf  mov     [rbp+var_50], 0
0x1800858c7  mov     rax, [rcx]
0x1800858ca  mov     rax, [rax+10h]
0x1800858ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800858d3  mov     eax, ebx
0x1800858d5  mov     rcx, [rbp+var_10]
0x1800858d9  xor     rcx, rsp; StackCookie
0x1800858dc  call    __security_check_cookie
0x1800858e1  mov     rbx, [rsp+70h+arg_10]
0x1800858e9  add     rsp, 70h
0x1800858ed  pop     r15
0x1800858ef  pop     r14
0x1800858f1  pop     r13
0x1800858f3  pop     r12
0x1800858f5  pop     rdi
0x1800858f6  pop     rsi
0x1800858f7  pop     rbp
0x1800858f8  retn
0x1800858fa  lea     r14, [r15+128h]
0x180085901  mov     rcx, r14; SRWLock
0x180085904  call    cs:__imp_AcquireSRWLockExclusive
0x18008590b  nop     dword ptr [rax+rax+00h]
0x180085910  lea     rdi, [r15+130h]
0x180085917  xor     ebx, ebx
0x180085919  mov     rdx, [rdi+8]
0x18008591d  cmp     rdx, [rdi+18h]
0x180085921  jnz     loc_180085A79
0x180085927  inc     rdx
0x18008592a  mov     rcx, rdi
0x18008592d  call    ?_EnsureCapacity@?$CTSimpleArray@UIHM_NOTIFICATION_DATA@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UIHM_NOTIFICATION_DATA@@@@V?$CSimpleArrayStandardCompareHelper@UIHM_NOTIFICATION_DATA@@@@V?$CSimpleArrayStandardMergeHelper@UIHM_NOTIFICATION_DATA@@@@@@QEAAJ_K0@Z; CTSimpleArray<IHM_NOTIFICATION_DATA,4294967294,CTPolicyCoTaskMem<IHM_NOTIFICATION_DATA>,CSimpleArrayStandardCompareHelper<IHM_NOTIFICATION_DATA>,CSimpleArrayStandardMergeHelper<IHM_NOTIFICATION_DATA>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180085932  mov     ebx, eax
0x180085934  test    eax, eax
0x180085936  jns     loc_180085A79
0x18008593c  mov     rcx, r14; SRWLock
0x18008593f  call    cs:__imp_ReleaseSRWLockExclusive
0x180085946  nop     dword ptr [rax+rax+00h]
0x18008594b  test    ebx, ebx
0x18008594d  js      loc_1800858B6
0x180085953  lea     rcx, [r15+9Ch]; this
0x18008595a  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18008595f  mov     rcx, [r15+150h]; pwk
0x180085966  call    cs:__imp_SubmitThreadpoolWork
0x18008596d  nop     dword ptr [rax+rax+00h]
0x180085972  jmp     loc_1800858B6
0x180085977  mov     rax, [rdi]
0x18008597a  xor     ebx, ebx
0x18008597c  mov     rcx, [rbp+var_50]
0x180085980  mov     r14, [rax+r14*8]
0x180085984  cmp     rcx, r14
0x180085987  jz      short loc_1800859AE
0x180085989  test    r14, r14
0x18008598c  jz      short loc_1800859A1
0x18008598e  mov     rax, [r14]
0x180085991  mov     rcx, r14
0x180085994  mov     rax, [rax+8]
0x180085998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008599d  mov     rcx, [rbp+var_50]
0x1800859a1  mov     [rbp+var_50], r14
0x1800859a5  test    rcx, rcx
0x1800859a8  jnz     loc_180085A33
0x1800859ae  mov     eax, [rsi+0Ch]
0x1800859b1  lea     rdx, [rsi+10h]; lprcSrc
0x1800859b5  mov     [rbp+var_48], eax
0x1800859b8  lea     rcx, [rbp+rcDst]; lprcDst
0x1800859bc  mov     eax, [rsi+8]
0x1800859bf  mov     [rbp+var_14], eax
0x1800859c2  call    cs:__imp_CopyRect
0x1800859c9  nop     dword ptr [rax+rax+00h]
0x1800859ce  lea     rdx, [rsi+20h]; lprcSrc
0x1800859d2  lea     rcx, [rbp+var_34]; lprcDst
0x1800859d6  call    cs:__imp_CopyRect
0x1800859dd  nop     dword ptr [rax+rax+00h]
0x1800859e2  lea     rdx, [rsi+30h]; lprcSrc
0x1800859e6  lea     rcx, [rbp+var_24]; lprcDst
0x1800859ea  call    cs:__imp_CopyRect
0x1800859f1  nop     dword ptr [rax+rax+00h]
0x1800859f6  cmp     dword ptr [rsi+0Ch], 1
0x1800859fa  jz      short loc_180085A44
0x1800859fc  mov     r12, [r15+110h]
0x180085a03  xor     r14d, r14d
0x180085a06  test    r12, r12
0x180085a09  jz      loc_1800858A3
0x180085a0f  mov     rax, [rdi]
0x180085a12  lea     rdx, [rbp+var_48]
0x180085a16  mov     rcx, [rax+r14*8]
0x180085a1a  mov     rax, [rcx]
0x180085a1d  mov     rax, [rax+28h]
0x180085a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085a26  inc     r14
0x180085a29  cmp     r14, r12
0x180085a2c  jb      short loc_180085A0F
0x180085a2e  jmp     loc_1800858A3
0x180085a33  mov     rax, [rcx]
0x180085a36  mov     rax, [rax+10h]
0x180085a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085a3f  jmp     loc_1800859AE
0x180085a44  mov     rcx, [rbp+var_50]
0x180085a48  lea     rdx, [rbp+var_48]
0x180085a4c  mov     rax, [rcx]
0x180085a4f  mov     rax, [rax+28h]
0x180085a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085a58  mov     ebx, eax
0x180085a5a  jmp     loc_1800858A3
0x180085a5f  inc     rdx
0x180085a62  mov     rcx, rdi
0x180085a65  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUIGestureClient@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUIGestureClient@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIGestureClient@@@@V?$CSimpleArrayStandardMergeHelper@PEAUIGestureClient@@@@@@QEAAJ_K0@Z; CTSimpleArray<IGestureClient *,4294967294,CTPolicyCoTaskMem<IGestureClient *>,CSimpleArrayStandardCompareHelper<IGestureClient *>,CSimpleArrayStandardMergeHelper<IGestureClient *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180085a6a  mov     ebx, eax
0x180085a6c  test    eax, eax
0x180085a6e  js      loc_18008589B
0x180085a74  jmp     loc_18008586C
0x180085a79  inc     qword ptr [rdi+8]
0x180085a7d  mov     rcx, [rdi+8]
0x180085a81  mov     rdx, [rdi]
0x180085a84  shl     rcx, 6
0x180085a88  add     rdx, 0FFFFFFFFFFFFFFC0h
0x180085a8c  add     rdx, rcx
0x180085a8f  jz      loc_18008593C
0x180085a95  movups  xmm0, xmmword ptr [rsi]
0x180085a98  movups  xmmword ptr [rdx], xmm0
0x180085a9b  movups  xmm1, xmmword ptr [rsi+10h]
0x180085a9f  movups  xmmword ptr [rdx+10h], xmm1
0x180085aa3  movups  xmm0, xmmword ptr [rsi+20h]
0x180085aa7  movups  xmmword ptr [rdx+20h], xmm0
0x180085aab  movups  xmm1, xmmword ptr [rsi+30h]
0x180085aaf  movups  xmmword ptr [rdx+30h], xmm1
0x180085ab3  jmp     loc_18008593C
```
