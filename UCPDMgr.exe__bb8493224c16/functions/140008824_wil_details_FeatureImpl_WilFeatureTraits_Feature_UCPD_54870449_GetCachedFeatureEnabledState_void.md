# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_54870449>::GetCachedFeatureEnabledState(void)

- ea: `0x140008824`
- end: `0x1400089b4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_54870449@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400058d4`
- `0x1400089bc`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140008824`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_54870449>::GetCachedFeatureEnabledState(
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
    v7 = v6(54870449, 0, &v19);
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
0x140008824  mov     [rsp+arg_10], rbx
0x140008829  mov     [rsp+arg_18], rbp
0x14000882e  push    rsi
0x14000882f  push    rdi
0x140008830  push    r15
0x140008832  sub     rsp, 30h
0x140008836  mov     rax, cs:__security_cookie
0x14000883d  xor     rax, rsp
0x140008840  mov     [rsp+48h+var_20], rax
0x140008845  mov     qword ptr [rdx], 0
0x14000884c  mov     rdi, rdx
0x14000884f  mov     eax, [rcx]
0x140008851  mov     rsi, rcx
0x140008854  mov     [rdx], eax
0x140008856  and     eax, 6
0x140008859  cmp     al, 6
0x14000885b  jz      loc_140008991
0x140008861  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140008866  mov     ebp, eax
0x140008868  mov     [rsp+48h+var_28], 0
0x140008870  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140008877  mov     r15d, 40h ; '@'
0x14000887d  test    rax, rax
0x140008880  jnz     short loc_14000888E
0x140008882  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140008889  test    rax, rax
0x14000888c  jz      short loc_1400088DA
0x14000888e  lea     r8, [rsp+48h+var_28]
0x140008893  xor     edx, edx
0x140008895  mov     ecx, 34541B1h
0x14000889a  call    _guard_dispatch_icall
0x14000889f  mov     r8d, eax
0x1400088a2  mov     edx, eax
0x1400088a4  and     r8d, 0FFFFFF3Fh
0x1400088ab  and     eax, r15d
0x1400088ae  and     edx, 80h
0x1400088b4  mov     ecx, r8d
0x1400088b7  and     ecx, 3
0x1400088ba  shl     ecx, 2
0x1400088bd  or      ecx, eax
0x1400088bf  shl     ecx, 2
0x1400088c2  or      ecx, edx
0x1400088c4  shl     ecx, 3
0x1400088c7  test    r8d, r8d
0x1400088ca  jz      short loc_1400088DC
0x1400088cc  xor     eax, eax
0x1400088ce  cmp     r8d, 2
0x1400088d2  cmovz   eax, r15d
0x1400088d6  or      eax, ecx
0x1400088d8  jmp     short loc_1400088DE
0x1400088da  xor     ecx, ecx
0x1400088dc  mov     eax, ecx
0x1400088de  mov     ebx, eax
0x1400088e0  shr     ebx, 6
0x1400088e3  and     ebx, 1
0x1400088e6  or      ebx, eax
0x1400088e8  test    ebp, ebp
0x1400088ea  jnz     short loc_1400088F0
0x1400088ec  mov     [rsp+48h+var_28], ebp
0x1400088f0  mov     eax, [rdi]
0x1400088f2  cmp     [rsp+48h+var_28], 0
0x1400088f7  mov     edx, eax
0x1400088f9  mov     [rdi], eax
0x1400088fb  mov     ecx, eax
0x1400088fd  jz      short loc_140008932
0x1400088ff  test    dl, 2
0x140008902  jnz     short loc_140008932
0x140008904  mov     eax, ebx
0x140008906  xor     eax, ecx
0x140008908  and     eax, 180h
0x14000890d  xor     eax, ecx
0x14000890f  mov     ecx, eax
0x140008911  xor     ecx, ebx
0x140008913  and     ecx, r15d
0x140008916  xor     ecx, eax
0x140008918  mov     eax, ecx
0x14000891a  xor     eax, ebx
0x14000891c  and     eax, 1
0x14000891f  xor     eax, ecx
0x140008921  mov     ecx, eax
0x140008923  xor     ecx, ebx
0x140008925  and     ecx, 800h
0x14000892b  xor     ecx, eax
0x14000892d  or      ecx, 2
0x140008930  mov     [rdi], ecx
0x140008932  test    dl, 4
0x140008935  jnz     short loc_140008947
0x140008937  mov     eax, ebx
0x140008939  xor     eax, ecx
0x14000893b  and     eax, 400h
0x140008940  xor     ecx, eax
0x140008942  or      ecx, 4
0x140008945  mov     [rdi], ecx
0x140008947  mov     eax, edx
0x140008949  lock cmpxchg [rsi], ecx
0x14000894d  jnz     short loc_1400088F2
0x14000894f  test    dl, 4
0x140008952  jnz     short loc_140008961
0x140008954  mov     r8d, ebp
0x140008957  xor     edx, edx
0x140008959  mov     rcx, rsi
0x14000895c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140008961  test    byte ptr [rdi], 2
0x140008964  jnz     short loc_140008991
0x140008966  mov     eax, ebx
0x140008968  xor     eax, [rdi]
0x14000896a  and     eax, 180h
0x14000896f  xor     eax, [rdi]
0x140008971  mov     ecx, eax
0x140008973  xor     ecx, ebx
0x140008975  and     ecx, r15d
0x140008978  xor     ecx, eax
0x14000897a  mov     edx, ecx
0x14000897c  xor     edx, ebx
0x14000897e  and     edx, 1
0x140008981  xor     edx, ecx
0x140008983  mov     ecx, edx
0x140008985  xor     ecx, ebx
0x140008987  and     ecx, 800h
0x14000898d  xor     ecx, edx
0x14000898f  mov     [rdi], ecx
0x140008991  mov     rax, rdi
0x140008994  mov     rcx, [rsp+48h+var_20]
0x140008999  xor     rcx, rsp; StackCookie
0x14000899c  call    __security_check_cookie
0x1400089a1  mov     rbx, [rsp+48h+arg_10]
0x1400089a6  mov     rbp, [rsp+48h+arg_18]
0x1400089ab  add     rsp, 30h
0x1400089af  pop     r15
0x1400089b1  pop     rdi
0x1400089b2  pop     rsi
0x1400089b3  retn
```
