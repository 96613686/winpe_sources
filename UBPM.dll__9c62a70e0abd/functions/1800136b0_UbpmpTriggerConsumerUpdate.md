# UbpmpTriggerConsumerUpdate

- ea: `0x1800136b0`
- end: `0x180013c8a`
- name: `UbpmpTriggerConsumerUpdate`
- size: `1498`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x180012b70`

## callees

- `0x1800017a4`
- `0x180001824`
- `0x180001f40`
- `0x180012570`
- `0x180012950`
- `0x180012b70`
- `0x1800136b0`
- `0x180015670`
- `0x1800156f0`
- `0x18001575c`
- `0x1800157b8`
- `0x18001af64`
- `0x180037df4`
- `0x180040260`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180013a3c`
- `ntdll!RtlFreeHeap` at `0x180013a3c`
- `ntdll!RtlReleaseSRWLockShared` at `0x180013759`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800137d7`
- `ntdll!RtlReleaseSRWLockShared` at `0x180013759`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800137d7`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800137c3`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800137c3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800137a4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800137f4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180013a9e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800137a4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800137f4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180013a9e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800138bb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800138eb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800139d4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013b23`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800138bb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800138eb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800139d4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013b23`
- `ntdll!NtDeleteWnfStateName` at `0x180013c79`
- `ntdll!NtDeleteWnfStateName` at `0x180013c79`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001372c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001372c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013800`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013aaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013800`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013aaa`

## pseudocode

```c
__int64 __fastcall UbpmpTriggerConsumerUpdate(
        struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *a1,
        char a2,
        __int64 a3,
        _QWORD *a4)
{
  void *v4; // r12
  __int64 *Value; // rax
  __int64 v8; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rbx
  char v12; // di
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // rdx
  __int64 i; // rdx
  __int64 v26; // rax
  __int64 v27; // rcx
  _QWORD *v28; // rcx
  int v29; // edx
  _QWORD *v31; // rcx
  _QWORD *v32; // rdx
  _QWORD *v33; // rax
  _QWORD *v34; // r8
  char v35; // [rsp+30h] [rbp-29h]
  _QWORD *v36; // [rsp+40h] [rbp-19h] BYREF
  _QWORD **v37; // [rsp+48h] [rbp-11h]
  __int64 v38; // [rsp+50h] [rbp-9h]
  int v39; // [rsp+58h] [rbp-1h] BYREF
  int v40; // [rsp+60h] [rbp+7h]
  __int64 v41; // [rsp+68h] [rbp+Fh] BYREF

  v4 = 0;
  v36 = &v36;
  v37 = &v36;
  v38 = 0;
  v41 = 0;
  v39 = 0;
  if ( !a1 || (*((_DWORD *)a1 + 4) & 0x100) == 0 || !a2 )
    return 183;
  if ( UbpmpLockTrackerId != -1 )
  {
    Value = (__int64 *)TlsGetValue(UbpmpLockTrackerId);
    v8 = *Value;
    if ( (*Value & 1) == 0 )
      __int2c();
    if ( Value[1]-- == 1 )
      *Value = v8 & 0xFFFFFFFFFFFFFFFEuLL;
  }
  RtlReleaseSRWLockShared(&g_ConsumerUpdateLock);
  v10 = UbpmpOpenTriggerConsumer(*(UUID **)a1, *((wchar_t **)a1 + 1));
  if ( !v10 )
  {
    UbpmpAcquireUpdateLockExclusive();
    v11 = v38;
    RtlAcquireSRWLockExclusive(v38 + 48);
    *(_DWORD *)(v11 + 56) = GetCurrentThreadId();
    RtlAcquireSRWLockShared(v11 + 72);
    v12 = *(_BYTE *)(v11 + 92);
    RtlReleaseSRWLockShared(v11 + 72);
    if ( (v12 & 1) != 0 )
    {
      *(_DWORD *)(v11 + 56) = 0;
      RtlReleaseSRWLockExclusive(v11 + 48);
      v20 = 4320;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_30;
      v29 = 159;
      goto LABEL_28;
    }
    RtlAcquireSRWLockExclusive(v11 + 208);
    *(_DWORD *)(v11 + 216) = GetCurrentThreadId();
    v13 = (_QWORD *)(v11 + 224);
    v14 = *(_QWORD **)(v11 + 224);
    if ( v14 != (_QWORD *)(v11 + 224) )
    {
      if ( (_QWORD *)v14[1] != v13 )
        goto LABEL_45;
      v15 = *(_QWORD **)(v11 + 232);
      if ( (_QWORD *)*v15 != v13 )
        goto LABEL_45;
      *v15 = v14;
      v14[1] = v15;
      *(_QWORD *)(v11 + 232) = v11 + 224;
      *v13 = v13;
      v16 = *v14;
      if ( *(_QWORD **)(*v14 + 8LL) != v14 )
        goto LABEL_45;
      v36 = (_QWORD *)*v14;
      v37 = (_QWORD **)v14;
      *(_QWORD *)(v16 + 8) = &v36;
      *v14 = &v36;
    }
    v35 = *(_BYTE *)(v11 + 304);
    v41 = *(_QWORD *)(v11 + 336);
    *(_QWORD *)(v11 + 336) = 0;
    v17 = *(_DWORD *)(v11 + 344);
    *(_DWORD *)(v11 + 344) = 0;
    v4 = *(void **)(v11 + 352);
    *(_QWORD *)(v11 + 352) = 0;
    v40 = v17;
    v18 = *(_DWORD *)(v11 + 44);
    *(_DWORD *)(v11 + 216) = 0;
    LODWORD(v38) = v18;
    RtlReleaseSRWLockExclusive(v11 + 208);
    v19 = UbpmpTriggerConsumerUnregister(v11, &v39, 0, 0, 1);
    *(_DWORD *)(v11 + 56) = 0;
    v20 = v19;
    RtlReleaseSRWLockExclusive(v11 + 48);
    if ( v20 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_30;
      v29 = 160;
      goto LABEL_28;
    }
    UbpmpAcquireListLockExclusive();
    v22 = *(_QWORD *)(v11 + 8);
    v23 = (_QWORD *)(v11 + 8);
    if ( *(_QWORD *)(v22 + 8) == v11 + 8 )
    {
      v24 = *(_QWORD **)(v11 + 16);
      if ( (_QWORD *)*v24 == v23 )
      {
        --g_cTotalConsumers;
        *v24 = v22;
        *(_QWORD *)(v22 + 8) = v24;
        *(_QWORD *)(v11 + 16) = v11 + 8;
        *v23 = v23;
        UbpmpReleaseListLockExclusive();
        for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 8); i = (unsigned int)(i + 1) )
        {
          v26 = *((_QWORD *)a1 + 5);
          if ( *(_DWORD *)(v26 + 40 * i + 16) == 1 )
          {
            v27 = *(_QWORD *)(*(_QWORD *)(v26 + 40 * i + 24) + 32LL);
            if ( v27 )
              *(_QWORD *)(v27 + 40) &= ~0x8000000000000000uLL;
          }
        }
        v20 = UbpmpTriggerConsumerRegister(a1);
        if ( v20 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_30;
          v29 = 161;
LABEL_28:
          WPP_SF_Sd(
            v28[2],
            v29,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            *(_QWORD *)(*(_QWORD *)(v11 + 24) + 8LL),
            v20);
LABEL_30:
          UbpmTelemConsumerUpdated(a1, v21, v20);
          UbpmpReleaseUpdateLockExclusive();
          UbpmpAcquireUpdateLockShared();
          if ( v41 )
            NtDeleteWnfStateName(&v41);
          if ( v4 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
          if ( v11 )
            UbpmpCloseTriggerConsumer(v11);
          return v20;
        }
        RtlAcquireSRWLockExclusive(208);
        MEMORY[0xD8] = GetCurrentThreadId();
        v31 = v36;
        if ( v36 == &v36 )
        {
LABEL_38:
          MEMORY[0x130] = v35;
          MEMORY[0x150] = v41;
          v41 = 0;
          MEMORY[0x158] = v40;
          MEMORY[0x160] = v4;
          v4 = 0;
          MEMORY[0x2C] = v38;
          MEMORY[0xD8] = 0;
          RtlReleaseSRWLockExclusive(208);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_qqS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              *(_QWORD *)(MEMORY[0x18] + 8LL),
              0,
              v11,
              0,
              *(_QWORD *)(MEMORY[0x18] + 8LL));
          *a4 = 0;
          goto LABEL_30;
        }
        while ( 1 )
        {
          v32 = (_QWORD *)*v31;
          if ( *(_QWORD **)(*v31 + 8LL) != v31 )
            break;
          v33 = (_QWORD *)v31[1];
          if ( (_QWORD *)*v33 != v31 )
            break;
          *v33 = v32;
          v32[1] = v33;
          v31[1] = v31;
          *v31 = v31;
          v34 = (_QWORD *)MEMORY[0xE8];
          if ( *MEMORY[0xE8] != 224 )
            break;
          *v31 = 224;
          v31[1] = v34;
          *v34 = v31;
          MEMORY[0xE8] = v31;
          v31 = v32;
          if ( v32 == &v36 )
            goto LABEL_38;
        }
      }
    }
LABEL_45:
    __fastfail(3u);
  }
  UbpmpAcquireUpdateLockShared();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      158,
      (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
      *((_QWORD *)a1 + 1),
      v10);
  return v10;
}

```

## disassembly

```asm
0x1800136b0  push    rbp
0x1800136b2  push    r12
0x1800136b4  push    r13
0x1800136b6  push    r14
0x1800136b8  lea     rbp, [rsp-3Fh]
0x1800136bd  sub     rsp, 98h
0x1800136c4  mov     rax, cs:__security_cookie
0x1800136cb  xor     rax, rsp
0x1800136ce  mov     [rbp+57h+var_40], rax
0x1800136d2  xor     r12d, r12d
0x1800136d5  lea     rax, [rbp+57h+var_70]
0x1800136d9  mov     [rbp+57h+var_70], rax
0x1800136dd  lea     rax, [rbp+57h+var_70]
0x1800136e1  mov     [rbp+57h+var_68], rax
0x1800136e5  mov     r13, r9
0x1800136e8  mov     [rbp+57h+var_60], r12
0x1800136ec  mov     r14, rcx
0x1800136ef  mov     [rbp+57h+var_78], r12
0x1800136f3  mov     [rbp+57h+var_48], r12
0x1800136f7  mov     [rbp+57h+var_58], r12d
0x1800136fb  test    rcx, rcx
0x1800136fe  jz      loc_180013BE7
0x180013704  test    dword ptr [rcx+10h], 100h
0x18001370b  jz      loc_180013BE7
0x180013711  test    dl, dl
0x180013713  jz      loc_180013BE7
0x180013719  mov     ecx, cs:UbpmpLockTrackerId; dwTlsIndex
0x18001371f  mov     [rsp+0B0h+arg_8], rbx
0x180013727  cmp     ecx, 0FFFFFFFFh
0x18001372a  jz      short loc_180013752
0x18001372c  call    cs:__imp_TlsGetValue
0x180013733  nop     dword ptr [rax+rax+00h]
0x180013738  mov     rdx, [rax]
0x18001373b  test    dl, 1
0x18001373e  jz      loc_180013C47
0x180013744  sub     qword ptr [rax+8], 1
0x180013749  jnz     short loc_180013752
0x18001374b  and     rdx, 0FFFFFFFFFFFFFFFEh
0x18001374f  mov     [rax], rdx
0x180013752  lea     rcx, ?g_ConsumerUpdateLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerUpdateLock
0x180013759  call    cs:__imp_RtlReleaseSRWLockShared
0x180013760  nop     dword ptr [rax+rax+00h]
0x180013765  mov     rdx, [r14+8]; String2
0x180013769  lea     r8, [rbp+57h+var_60]
0x18001376d  mov     rcx, [r14]; Uuid2
0x180013770  call    UbpmpOpenTriggerConsumer
0x180013775  mov     ebx, eax
0x180013777  test    eax, eax
0x180013779  jnz     loc_180013BF1
0x18001377f  mov     [rsp+0B0h+var_20], rsi
0x180013787  mov     [rsp+0B0h+var_28], rdi
0x18001378f  mov     [rsp+0B0h+var_30], r15
0x180013797  call    UbpmpAcquireUpdateLockExclusive
0x18001379c  mov     rbx, [rbp+57h+var_60]
0x1800137a0  lea     rcx, [rbx+30h]
0x1800137a4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800137ab  nop     dword ptr [rax+rax+00h]
0x1800137b0  call    cs:__imp_GetCurrentThreadId
0x1800137b7  nop     dword ptr [rax+rax+00h]
0x1800137bc  lea     rcx, [rbx+48h]
0x1800137c0  mov     [rbx+38h], eax
0x1800137c3  call    cs:__imp_RtlAcquireSRWLockShared
0x1800137ca  nop     dword ptr [rax+rax+00h]
0x1800137cf  movzx   edi, byte ptr [rbx+5Ch]
0x1800137d3  lea     rcx, [rbx+48h]
0x1800137d7  call    cs:__imp_RtlReleaseSRWLockShared
0x1800137de  nop     dword ptr [rax+rax+00h]
0x1800137e3  test    dil, 1
0x1800137e7  jnz     loc_1800139CB
0x1800137ed  lea     rcx, [rbx+0D0h]
0x1800137f4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800137fb  nop     dword ptr [rax+rax+00h]
0x180013800  call    cs:__imp_GetCurrentThreadId
0x180013807  nop     dword ptr [rax+rax+00h]
0x18001380c  mov     [rbx+0D8h], eax
0x180013812  lea     rax, [rbx+0E0h]
0x180013819  mov     rcx, [rax]
0x18001381c  cmp     rcx, rax
0x18001381f  jz      short loc_18001386A
0x180013821  cmp     [rcx+8], rax
0x180013825  jnz     loc_180013B8D
0x18001382b  mov     rdx, [rax+8]
0x18001382f  cmp     [rdx], rax
0x180013832  jnz     loc_180013B8D
0x180013838  mov     [rdx], rcx
0x18001383b  mov     [rcx+8], rdx
0x18001383f  mov     [rax+8], rax
0x180013843  mov     [rax], rax
0x180013846  mov     rax, [rcx]
0x180013849  cmp     [rax+8], rcx
0x18001384d  jnz     loc_180013B8D
0x180013853  mov     [rbp+57h+var_70], rax
0x180013857  lea     rdx, [rbp+57h+var_70]
0x18001385b  mov     [rbp+57h+var_68], rcx
0x18001385f  mov     [rax+8], rdx
0x180013863  lea     rax, [rbp+57h+var_70]
0x180013867  mov     [rcx], rax
0x18001386a  movzx   eax, byte ptr [rbx+130h]
0x180013871  xor     ecx, ecx
0x180013873  mov     [rbp+57h+var_80], al
0x180013876  mov     rax, [rbx+150h]
0x18001387d  mov     [rbp+57h+var_48], rax
0x180013881  xor     eax, eax
0x180013883  mov     [rbx+150h], rax
0x18001388a  mov     eax, [rbx+158h]
0x180013890  mov     [rbx+158h], r12d
0x180013897  mov     r12, [rbx+160h]
0x18001389e  mov     [rbx+160h], rcx
0x1800138a5  mov     [rbp+57h+var_50], eax
0x1800138a8  mov     eax, [rbx+2Ch]
0x1800138ab  mov     [rbx+0D8h], ecx
0x1800138b1  lea     rcx, [rbx+0D0h]
0x1800138b8  mov     dword ptr [rbp+57h+var_60], eax
0x1800138bb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800138c2  nop     dword ptr [rax+rax+00h]
0x1800138c7  xor     r9d, r9d
0x1800138ca  mov     byte ptr [rsp+0B0h+var_90], 1
0x1800138cf  xor     r8d, r8d
0x1800138d2  lea     rdx, [rbp+57h+var_58]
0x1800138d6  mov     rcx, rbx
0x1800138d9  call    UbpmpTriggerConsumerUnregister
0x1800138de  lea     rcx, [rbx+30h]
0x1800138e2  mov     dword ptr [rbx+38h], 0
0x1800138e9  mov     esi, eax
0x1800138eb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800138f2  nop     dword ptr [rax+rax+00h]
0x1800138f7  test    esi, esi
0x1800138f9  jnz     loc_180013B62
0x1800138ff  call    UbpmpAcquireListLockExclusive
0x180013904  mov     rcx, [rbx+8]
0x180013908  lea     rax, [rbx+8]
0x18001390c  cmp     [rcx+8], rax
0x180013910  jnz     loc_180013B8D
0x180013916  mov     rdx, [rax+8]
0x18001391a  cmp     [rdx], rax
0x18001391d  jnz     loc_180013B8D
0x180013923  dec     cs:g_cTotalConsumers
0x180013929  mov     [rdx], rcx
0x18001392c  mov     [rcx+8], rdx
0x180013930  mov     [rax+8], rax
0x180013934  mov     [rax], rax
0x180013937  call    UbpmpReleaseListLockExclusive
0x18001393c  xor     edx, edx
0x18001393e  cmp     [r14+20h], edx
0x180013942  jbe     short loc_180013977
0x180013944  mov     r8, 7FFFFFFFFFFFFFFFh
0x18001394e  mov     rax, [r14+28h]
0x180013952  lea     rcx, [rdx+rdx*4]
0x180013956  cmp     dword ptr [rax+rcx*8+10h], 1
0x18001395b  jnz     short loc_18001396F
0x18001395d  mov     rax, [rax+rcx*8+18h]
0x180013962  mov     rcx, [rax+20h]
0x180013966  test    rcx, rcx
0x180013969  jnz     loc_180013B59
0x18001396f  inc     edx
0x180013971  cmp     edx, [r14+20h]
0x180013975  jb      short loc_18001394E
0x180013977  lea     r8, [rbp+57h+var_78]
0x18001397b  mov     dl, 1
0x18001397d  mov     rcx, r14; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x180013980  call    UbpmpTriggerConsumerRegister
0x180013985  mov     esi, eax
0x180013987  test    eax, eax
0x180013989  jz      loc_180013A93
0x18001398f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013996  lea     rax, WPP_GLOBAL_Control
0x18001399d  cmp     rcx, rax
0x1800139a0  jz      short loc_1800139FC
0x1800139a2  test    byte ptr [rcx+1Ch], 1
0x1800139a6  jz      short loc_1800139FC
0x1800139a8  mov     edx, 0A1h
0x1800139ad  mov     r9, [rbx+18h]
0x1800139b1  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x1800139b8  mov     rcx, [rcx+10h]
0x1800139bc  mov     dword ptr [rsp+0B0h+var_90], esi
0x1800139c0  mov     r9, [r9+8]
0x1800139c4  call    WPP_SF_Sd
0x1800139c9  jmp     short loc_1800139FC
0x1800139cb  xor     edx, edx
0x1800139cd  lea     rcx, [rbx+30h]
0x1800139d1  mov     [rbx+38h], edx
0x1800139d4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800139db  nop     dword ptr [rax+rax+00h]
0x1800139e0  mov     esi, 10E0h
0x1800139e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139ec  lea     rax, WPP_GLOBAL_Control
0x1800139f3  cmp     rcx, rax
0x1800139f6  jnz     loc_180013C33
0x1800139fc  mov     r8d, esi
0x1800139ff  mov     rcx, r14
0x180013a02  call    UbpmTelemConsumerUpdated
0x180013a07  call    UbpmpReleaseUpdateLockExclusive
0x180013a0c  call    UbpmpAcquireUpdateLockShared
0x180013a11  cmp     dword ptr [rbp+57h+var_48], 0
0x180013a15  jnz     loc_180013C75
0x180013a1b  cmp     dword ptr [rbp+57h+var_48+4], 0
0x180013a1f  jnz     loc_180013C75
0x180013a25  test    r12, r12
0x180013a28  jz      short loc_180013A48
0x180013a2a  mov     rcx, gs:60h
0x180013a33  mov     r8, r12; P
0x180013a36  xor     edx, edx; Flags
0x180013a38  mov     rcx, [rcx+30h]; HeapHandle
0x180013a3c  call    cs:__imp_RtlFreeHeap
0x180013a43  nop     dword ptr [rax+rax+00h]
0x180013a48  test    rbx, rbx
0x180013a4b  jz      short loc_180013A55
0x180013a4d  mov     rcx, rbx
0x180013a50  call    UbpmpCloseTriggerConsumer
0x180013a55  mov     rdi, [rsp+0B0h+var_28]
0x180013a5d  mov     eax, esi
0x180013a5f  mov     rsi, [rsp+0B0h+var_20]
0x180013a67  mov     r15, [rsp+0B0h+var_30]
0x180013a6f  mov     rbx, [rsp+0B0h+arg_8]
0x180013a77  mov     rcx, [rbp+57h+var_40]
0x180013a7b  xor     rcx, rsp; StackCookie
0x180013a7e  call    __security_check_cookie
0x180013a83  add     rsp, 98h
0x180013a8a  pop     r14
0x180013a8c  pop     r13
0x180013a8e  pop     r12
0x180013a90  pop     rbp
0x180013a91  retn
0x180013a93  mov     rdi, [rbp+57h+var_78]
0x180013a97  lea     rcx, [rdi+0D0h]
0x180013a9e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180013aa5  nop     dword ptr [rax+rax+00h]
0x180013aaa  call    cs:__imp_GetCurrentThreadId
0x180013ab1  nop     dword ptr [rax+rax+00h]
0x180013ab6  mov     [rdi+0D8h], eax
0x180013abc  lea     rax, [rbp+57h+var_70]
0x180013ac0  mov     rcx, [rbp+57h+var_70]
0x180013ac4  cmp     rcx, rax
0x180013ac7  jnz     loc_180013B94
0x180013acd  mov     rax, [rbp+57h+var_78]
0x180013ad1  xor     edx, edx
0x180013ad3  movzx   ecx, [rbp+57h+var_80]
0x180013ad7  mov     [rax+130h], cl
0x180013add  mov     rcx, [rbp+57h+var_78]
0x180013ae1  mov     rax, [rbp+57h+var_48]
0x180013ae5  mov     [rcx+150h], rax
0x180013aec  mov     rax, [rbp+57h+var_78]
0x180013af0  mov     ecx, [rbp+57h+var_50]
0x180013af3  mov     [rbp+57h+var_48], rdx
0x180013af7  mov     [rax+158h], ecx
0x180013afd  mov     rax, [rbp+57h+var_78]
0x180013b01  mov     ecx, dword ptr [rbp+57h+var_60]
0x180013b04  mov     [rax+160h], r12
0x180013b0b  mov     r12d, edx
0x180013b0e  mov     rax, [rbp+57h+var_78]
0x180013b12  mov     [rax+2Ch], ecx
0x180013b15  mov     rcx, [rbp+57h+var_78]
0x180013b19  add     rcx, 0D0h
0x180013b20  mov     [rcx+8], edx
0x180013b23  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180013b2a  nop     dword ptr [rax+rax+00h]
0x180013b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b36  lea     rax, WPP_GLOBAL_Control
0x180013b3d  cmp     rcx, rax
0x180013b40  jz      short loc_180013B4C
0x180013b42  test    byte ptr [rcx+1Ch], 4
0x180013b46  jnz     loc_180013C4E
0x180013b4c  mov     rax, [rbp+57h+var_78]
0x180013b50  mov     [r13+0], rax
0x180013b54  jmp     loc_1800139FC
0x180013b59  and     [rcx+28h], r8
0x180013b5d  jmp     loc_18001396F
0x180013b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b69  lea     rax, WPP_GLOBAL_Control
0x180013b70  cmp     rcx, rax
0x180013b73  jz      loc_1800139FC
0x180013b79  test    byte ptr [rcx+1Ch], 1
0x180013b7d  jz      loc_1800139FC
0x180013b83  mov     edx, 0A0h
0x180013b88  jmp     loc_1800139AD
0x180013b8d  mov     ecx, 3
0x180013b92  int     29h; Win8: RtlFailFast(ecx)
0x180013b94  mov     rdx, [rcx]
0x180013b97  cmp     [rdx+8], rcx
0x180013b9b  jnz     short loc_180013B8D
0x180013b9d  mov     rax, [rcx+8]
0x180013ba1  cmp     [rax], rcx
0x180013ba4  jnz     short loc_180013B8D
0x180013ba6  mov     [rax], rdx
0x180013ba9  mov     [rdx+8], rax
0x180013bad  mov     [rcx+8], rcx
0x180013bb1  mov     [rcx], rcx
0x180013bb4  mov     rax, [rbp+57h+var_78]
0x180013bb8  add     rax, 0E0h
0x180013bbe  mov     r8, [rax+8]
0x180013bc2  cmp     [r8], rax
0x180013bc5  jnz     short loc_180013B8D
0x180013bc7  mov     [rcx], rax
0x180013bca  mov     [rcx+8], r8
0x180013bce  mov     [r8], rcx
0x180013bd1  mov     [rax+8], rcx
0x180013bd5  lea     rax, [rbp+57h+var_70]
0x180013bd9  mov     rcx, rdx
0x180013bdc  cmp     rdx, rax
0x180013bdf  jz      loc_180013ACD
  ... truncated ...
```
