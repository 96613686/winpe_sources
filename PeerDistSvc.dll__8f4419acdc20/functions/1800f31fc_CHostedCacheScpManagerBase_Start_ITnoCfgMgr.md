# CHostedCacheScpManagerBase::Start(ITnoCfgMgr *)

- ea: `0x1800f31fc`
- end: `0x1800f33cc`
- name: `?Start@CHostedCacheScpManagerBase@@IEAAJPEAVITnoCfgMgr@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(CHostedCacheScpManagerBase *__hidden this, struct ITnoCfgMgr *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800f1030`
- `0x1800f1c3c`

## callees

- `0x180004510`
- `0x180004874`
- `0x180008310`
- `0x1800f2f9c`
- `0x1800f31fc`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f336c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f336c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f33b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f33b1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800f3357`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800f3357`

## pseudocode

```c
__int64 __fastcall CHostedCacheScpManagerBase::Start(CHostedCacheScpManagerBase *this, struct ITnoCfgMgr *a2)
{
  int v4; // ebx
  CHostedCacheMsgEncoding *v5; // r10
  __int64 v6; // rdx
  __int64 v7; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  DWORD v10; // r8d
  _BYTE v12[32]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v13; // [rsp+70h] [rbp+20h] BYREF
  int v14; // [rsp+78h] [rbp+28h] BYREF
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp+30h] BYREF

  InCritSec::InCritSec((InCritSec *)v12, (CHostedCacheScpManagerBase *)((char *)this + 64), 1);
  *((_QWORD *)this + 1) = a2;
  *((_BYTE *)this + 224) = 1;
  v13 = 0;
  v14 = 4;
  v4 = (*(__int64 (__fastcall **)(struct ITnoCfgMgr *, __int64, int *, unsigned int *, _QWORD))(*(_QWORD *)a2 + 88LL))(
         a2,
         155,
         &v14,
         &v13,
         0);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(CHostedCacheScpManagerBase *))(*(_QWORD *)this + 24LL))(this);
    if ( v4 >= 0 )
    {
      v4 = CHostedCacheScpManagerBase::NotifySettingsChangedInternal(this, 0, 0);
      if ( v4 >= 0 )
      {
        ThreadpoolTimer = CreateThreadpoolTimer(CHostedCacheScpManagerBase::UpdateTimerCallback, this, 0);
        *((_QWORD *)this + 29) = ThreadpoolTimer;
        if ( ThreadpoolTimer )
        {
          v10 = 1000 * v13;
          pftDueTime = (struct _FILETIME)(-10000000LL * v13);
          if ( 1000 * v13 < v13 )
            v10 = -1;
          SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, v10, 0);
          v4 = 0;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v4 = LastError;
        }
      }
      else if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v7 = *((_QWORD *)WPP_GLOBAL_Control + 12);
        v6 = 12;
        goto LABEL_17;
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v6 = 11;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v6 = 10;
LABEL_6:
      v7 = *((_QWORD *)v5 + 12);
LABEL_17:
      WPP_SF_qD(v7, v6, WPP_38c68fbe15433a6b91ef6ada69961fb5_Traceguids, this, v4);
    }
  }
  InCritSec::~InCritSec((InCritSec *)v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800f31fc  push    rbp
0x1800f31fe  push    rbx
0x1800f31ff  push    rdi
0x1800f3200  mov     rbp, rsp
0x1800f3203  sub     rsp, 50h
0x1800f3207  mov     rbx, rdx
0x1800f320a  mov     rdi, rcx
0x1800f320d  lea     rdx, [rcx+40h]; struct CritSec *
0x1800f3211  mov     r8b, 1; bool
0x1800f3214  lea     rcx, [rbp+var_20]; this
0x1800f3218  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1800f321d  mov     [rdi+8], rbx
0x1800f3221  lea     r9, [rbp+arg_0]
0x1800f3225  mov     byte ptr [rdi+0E0h], 1
0x1800f322c  lea     r8, [rbp+arg_8]
0x1800f3230  mov     [rbp+arg_0], 0
0x1800f3237  mov     edx, 9Bh
0x1800f323c  mov     [rbp+arg_8], 4
0x1800f3243  mov     rcx, rbx
0x1800f3246  mov     rax, [rbx]
0x1800f3249  mov     [rsp+50h+var_30], 0
0x1800f3252  mov     rax, [rax+58h]
0x1800f3256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f325b  mov     ebx, eax
0x1800f325d  test    eax, eax
0x1800f325f  jns     short loc_1800F329F
0x1800f3261  mov     r10, cs:WPP_GLOBAL_Control
0x1800f3268  lea     rcx, WPP_GLOBAL_Control
0x1800f326f  cmp     r10, rcx
0x1800f3272  jz      loc_1800F33B9
0x1800f3278  test    dword ptr [r10+6Ch], 1000h
0x1800f3280  jz      loc_1800F33B9
0x1800f3286  cmp     byte ptr [r10+69h], 1
0x1800f328b  jb      loc_1800F33B9
0x1800f3291  mov     edx, 0Ah
0x1800f3296  mov     rcx, [r10+60h]
0x1800f329a  jmp     loc_1800F3335
0x1800f329f  mov     rax, [rdi]
0x1800f32a2  mov     rcx, rdi
0x1800f32a5  mov     rax, [rax+18h]
0x1800f32a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f32ae  mov     ebx, eax
0x1800f32b0  test    eax, eax
0x1800f32b2  jns     short loc_1800F32EB
0x1800f32b4  mov     r10, cs:WPP_GLOBAL_Control
0x1800f32bb  lea     rcx, WPP_GLOBAL_Control
0x1800f32c2  cmp     r10, rcx
0x1800f32c5  jz      loc_1800F33B9
0x1800f32cb  test    dword ptr [r10+6Ch], 1000h
0x1800f32d3  jz      loc_1800F33B9
0x1800f32d9  cmp     byte ptr [r10+69h], 1
0x1800f32de  jb      loc_1800F33B9
0x1800f32e4  mov     edx, 0Bh
0x1800f32e9  jmp     short loc_1800F3296
0x1800f32eb  xor     r8d, r8d; int *
0x1800f32ee  xor     edx, edx; void *
0x1800f32f0  mov     rcx, rdi; this
0x1800f32f3  call    ?NotifySettingsChangedInternal@CHostedCacheScpManagerBase@@AEAAJPEAXPEAJ@Z; CHostedCacheScpManagerBase::NotifySettingsChangedInternal(void *,long *)
0x1800f32f8  mov     ebx, eax
0x1800f32fa  test    eax, eax
0x1800f32fc  jns     short loc_1800F334A
0x1800f32fe  mov     rax, cs:WPP_GLOBAL_Control
0x1800f3305  lea     rcx, WPP_GLOBAL_Control
0x1800f330c  cmp     rax, rcx
0x1800f330f  jz      loc_1800F33B9
0x1800f3315  test    dword ptr [rax+6Ch], 1000h
0x1800f331c  jz      loc_1800F33B9
0x1800f3322  cmp     byte ptr [rax+69h], 1
0x1800f3326  jb      loc_1800F33B9
0x1800f332c  mov     rcx, [rax+60h]
0x1800f3330  mov     edx, 0Ch
0x1800f3335  mov     r9, rdi
0x1800f3338  mov     dword ptr [rsp+50h+var_30], ebx
0x1800f333c  lea     r8, WPP_38c68fbe15433a6b91ef6ada69961fb5_Traceguids
0x1800f3343  call    WPP_SF_qD
0x1800f3348  jmp     short loc_1800F33B9
0x1800f334a  xor     r8d, r8d; pcbe
0x1800f334d  lea     rcx, ?UpdateTimerCallback@CHostedCacheScpManagerBase@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800f3354  mov     rdx, rdi; pv
0x1800f3357  call    cs:__imp_CreateThreadpoolTimer
0x1800f335d  mov     [rdi+0E8h], rax
0x1800f3364  mov     r10, rax
0x1800f3367  test    rax, rax
0x1800f336a  jnz     short loc_1800F3382
0x1800f336c  call    cs:__imp_GetLastError
0x1800f3372  test    eax, eax
0x1800f3374  jle     short loc_1800F337E
0x1800f3376  movzx   eax, ax
0x1800f3379  or      eax, 80070000h
0x1800f337e  mov     ebx, eax
0x1800f3380  jmp     short loc_1800F33B9
0x1800f3382  mov     ecx, [rbp+arg_0]
0x1800f3385  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x1800f3389  imul    rax, rcx, 0FFFFFFFFFF676980h
0x1800f3390  imul    r8d, ecx, 3E8h
0x1800f3397  mov     [rbp+pftDueTime.dwLowDateTime], eax
0x1800f339a  shr     rax, 20h
0x1800f339e  mov     [rbp+pftDueTime.dwHighDateTime], eax
0x1800f33a1  or      eax, 0FFFFFFFFh
0x1800f33a4  cmp     r8d, ecx
0x1800f33a7  mov     rcx, r10; pti
0x1800f33aa  cmovb   r8d, eax; msPeriod
0x1800f33ae  xor     r9d, r9d; msWindowLength
0x1800f33b1  call    cs:__imp_SetThreadpoolTimer
0x1800f33b7  xor     ebx, ebx
0x1800f33b9  lea     rcx, [rbp+var_20]; this
0x1800f33bd  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800f33c2  mov     eax, ebx
0x1800f33c4  add     rsp, 50h
0x1800f33c8  pop     rdi
0x1800f33c9  pop     rbx
0x1800f33ca  pop     rbp
0x1800f33cb  retn
```
