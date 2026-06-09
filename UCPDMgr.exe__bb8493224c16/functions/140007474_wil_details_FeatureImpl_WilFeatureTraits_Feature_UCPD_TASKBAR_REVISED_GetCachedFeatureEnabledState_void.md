# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::GetCachedFeatureEnabledState(void)

- ea: `0x140007474`
- end: `0x140007604`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400056b8`
- `0x14000760c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140007474`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v5; // ebp
  __int64 (__fastcall *v6)(__int64, _QWORD, int *); // rax
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // eax
  int v12; // ebx
  signed __int32 v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  signed __int32 v16; // ecx
  int v17; // ecx
  int v19; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v19 = 0;
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(57398953, 0, &v19);
    v8 = v7 & 0xFFFFFF3F;
    v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
      v11 = v9 | v10;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = 0;
  }
  v11 = v9;
LABEL_10:
  v12 = v11 | (v11 >> 6) & 1;
  if ( !v5 )
    v19 = 0;
  v13 = *(_DWORD *)a2;
  do
  {
    v14 = v19 == 0;
    v15 = v13;
    *(_DWORD *)a2 = v13;
    v16 = v13;
    if ( !v14 && (v13 & 2) == 0 )
    {
      v17 = v13
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)v12)
          & 0x180
          ^ (v12
           ^ v13
           ^ ((unsigned __int16)v13
            ^ (unsigned __int16)v12)
           & 0x180)
          & 0x40;
      v16 = v17
          ^ ((unsigned __int8)v12
           ^ (unsigned __int8)v17)
          & 1
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)(v17 ^ ((unsigned __int8)v12 ^ (unsigned __int8)v17) & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    if ( (v13 & 4) == 0 )
    {
      v16 = ((unsigned __int16)v16 ^ (unsigned __int16)v12) & 0x400 ^ v16 | 4;
      *(_DWORD *)a2 = v16;
    }
    v13 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v16, v13);
  }
  while ( v15 != v13 );
  if ( (v15 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 0, v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (*(_DWORD *)a2
                    ^ v12)
                   & 0x180
                   ^ (v12
                    ^ *(_DWORD *)a2
                    ^ (*(_DWORD *)a2
                     ^ v12)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v12
                    ^ *(_BYTE *)a2
                    ^ (*(_BYTE *)a2
                     ^ (unsigned __int8)v12)
                    & 0x80
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v12)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v12
                    ^ *(_WORD *)a2
                    ^ (*(_WORD *)a2
                     ^ (unsigned __int16)v12)
                    & 0x180
                    ^ ((unsigned __int16)v12
                     ^ *(_WORD *)a2
                     ^ (*(_WORD *)a2
                      ^ (unsigned __int16)v12)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v12)
                     & 0x80
                     ^ ((unsigned __int8)v12
                      ^ *(_BYTE *)a2
                      ^ (*(_BYTE *)a2
                       ^ (unsigned __int8)v12)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140007474  mov     [rsp+arg_10], rbx
0x140007479  mov     [rsp+arg_18], rbp
0x14000747e  push    rsi
0x14000747f  push    rdi
0x140007480  push    r15
0x140007482  sub     rsp, 30h
0x140007486  mov     rax, cs:__security_cookie
0x14000748d  xor     rax, rsp
0x140007490  mov     [rsp+48h+var_20], rax
0x140007495  mov     qword ptr [rdx], 0
0x14000749c  mov     rdi, rdx
0x14000749f  mov     eax, [rcx]
0x1400074a1  mov     rsi, rcx
0x1400074a4  mov     [rdx], eax
0x1400074a6  and     eax, 6
0x1400074a9  cmp     al, 6
0x1400074ab  jz      loc_1400075E1
0x1400074b1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400074b6  mov     ebp, eax
0x1400074b8  mov     [rsp+48h+var_28], 0
0x1400074c0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400074c7  mov     r15d, 40h ; '@'
0x1400074cd  test    rax, rax
0x1400074d0  jnz     short loc_1400074DE
0x1400074d2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400074d9  test    rax, rax
0x1400074dc  jz      short loc_14000752A
0x1400074de  lea     r8, [rsp+48h+var_28]
0x1400074e3  xor     edx, edx
0x1400074e5  mov     ecx, 36BD6A9h
0x1400074ea  call    _guard_dispatch_icall
0x1400074ef  mov     r8d, eax
0x1400074f2  mov     edx, eax
0x1400074f4  and     r8d, 0FFFFFF3Fh
0x1400074fb  and     eax, r15d
0x1400074fe  and     edx, 80h
0x140007504  mov     ecx, r8d
0x140007507  and     ecx, 3
0x14000750a  shl     ecx, 2
0x14000750d  or      ecx, eax
0x14000750f  shl     ecx, 2
0x140007512  or      ecx, edx
0x140007514  shl     ecx, 3
0x140007517  test    r8d, r8d
0x14000751a  jz      short loc_14000752C
0x14000751c  xor     eax, eax
0x14000751e  cmp     r8d, 2
0x140007522  cmovz   eax, r15d
0x140007526  or      eax, ecx
0x140007528  jmp     short loc_14000752E
0x14000752a  xor     ecx, ecx
0x14000752c  mov     eax, ecx
0x14000752e  mov     ebx, eax
0x140007530  shr     ebx, 6
0x140007533  and     ebx, 1
0x140007536  or      ebx, eax
0x140007538  test    ebp, ebp
0x14000753a  jnz     short loc_140007540
0x14000753c  mov     [rsp+48h+var_28], ebp
0x140007540  mov     eax, [rdi]
0x140007542  cmp     [rsp+48h+var_28], 0
0x140007547  mov     edx, eax
0x140007549  mov     [rdi], eax
0x14000754b  mov     ecx, eax
0x14000754d  jz      short loc_140007582
0x14000754f  test    dl, 2
0x140007552  jnz     short loc_140007582
0x140007554  mov     eax, ebx
0x140007556  xor     eax, ecx
0x140007558  and     eax, 180h
0x14000755d  xor     eax, ecx
0x14000755f  mov     ecx, eax
0x140007561  xor     ecx, ebx
0x140007563  and     ecx, r15d
0x140007566  xor     ecx, eax
0x140007568  mov     eax, ecx
0x14000756a  xor     eax, ebx
0x14000756c  and     eax, 1
0x14000756f  xor     eax, ecx
0x140007571  mov     ecx, eax
0x140007573  xor     ecx, ebx
0x140007575  and     ecx, 800h
0x14000757b  xor     ecx, eax
0x14000757d  or      ecx, 2
0x140007580  mov     [rdi], ecx
0x140007582  test    dl, 4
0x140007585  jnz     short loc_140007597
0x140007587  mov     eax, ebx
0x140007589  xor     eax, ecx
0x14000758b  and     eax, 400h
0x140007590  xor     ecx, eax
0x140007592  or      ecx, 4
0x140007595  mov     [rdi], ecx
0x140007597  mov     eax, edx
0x140007599  lock cmpxchg [rsi], ecx
0x14000759d  jnz     short loc_140007542
0x14000759f  test    dl, 4
0x1400075a2  jnz     short loc_1400075B1
0x1400075a4  mov     r8d, ebp
0x1400075a7  xor     edx, edx
0x1400075a9  mov     rcx, rsi
0x1400075ac  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400075b1  test    byte ptr [rdi], 2
0x1400075b4  jnz     short loc_1400075E1
0x1400075b6  mov     eax, ebx
0x1400075b8  xor     eax, [rdi]
0x1400075ba  and     eax, 180h
0x1400075bf  xor     eax, [rdi]
0x1400075c1  mov     ecx, eax
0x1400075c3  xor     ecx, ebx
0x1400075c5  and     ecx, r15d
0x1400075c8  xor     ecx, eax
0x1400075ca  mov     edx, ecx
0x1400075cc  xor     edx, ebx
0x1400075ce  and     edx, 1
0x1400075d1  xor     edx, ecx
0x1400075d3  mov     ecx, edx
0x1400075d5  xor     ecx, ebx
0x1400075d7  and     ecx, 800h
0x1400075dd  xor     ecx, edx
0x1400075df  mov     [rdi], ecx
0x1400075e1  mov     rax, rdi
0x1400075e4  mov     rcx, [rsp+48h+var_20]
0x1400075e9  xor     rcx, rsp; StackCookie
0x1400075ec  call    __security_check_cookie
0x1400075f1  mov     rbx, [rsp+48h+arg_10]
0x1400075f6  mov     rbp, [rsp+48h+arg_18]
0x1400075fb  add     rsp, 30h
0x1400075ff  pop     r15
0x140007601  pop     rdi
0x140007602  pop     rsi
0x140007603  retn
```
