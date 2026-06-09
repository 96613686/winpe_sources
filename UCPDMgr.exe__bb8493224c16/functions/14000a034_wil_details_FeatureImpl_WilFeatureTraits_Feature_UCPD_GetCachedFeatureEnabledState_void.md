# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD>::GetCachedFeatureEnabledState(void)

- ea: `0x14000a034`
- end: `0x14000a1c5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `401`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005b68`
- `0x14000a1cc`

## callees

- `0x140004168`
- `0x14000422c`
- `0x14000a034`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD>::GetCachedFeatureEnabledState(
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
  unsigned int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  int v16; // ecx
  int v18; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v18 = 0;
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(44860385, 0, &v18);
    v8 = v7 & 0xFFFFFF3F;
    v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = 0;
  }
  v10 = 64;
LABEL_10:
  v11 = v10 | v9 | ((v10 | (unsigned int)v9) >> 6) & 1;
  if ( !v5 )
    v18 = 0;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = v18 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    v15 = v12;
    if ( !v13 && (v12 & 2) == 0 )
    {
      v16 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40;
      v15 = v16
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)v16)
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v16 ^ ((unsigned __int8)v11 ^ (unsigned __int8)v16) & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    if ( (v12 & 4) == 0 )
    {
      v15 = ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 ^ v15 | 4;
      *(_DWORD *)a2 = v15;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v15, v12);
  }
  while ( v14 != v12 );
  if ( (v14 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 0, v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (*(_DWORD *)a2
                    ^ v11)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ (*(_DWORD *)a2
                     ^ v11)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ (*(_BYTE *)a2
                     ^ (unsigned __int8)v11)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v11)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ (*(_WORD *)a2
                     ^ (unsigned __int16)v11)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ (*(_WORD *)a2
                      ^ (unsigned __int16)v11)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v11)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ (*(_BYTE *)a2
                       ^ (unsigned __int8)v11)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x14000a034  mov     [rsp+arg_10], rbx
0x14000a039  mov     [rsp+arg_18], rbp
0x14000a03e  push    rsi
0x14000a03f  push    rdi
0x14000a040  push    r15
0x14000a042  sub     rsp, 30h
0x14000a046  mov     rax, cs:__security_cookie
0x14000a04d  xor     rax, rsp
0x14000a050  mov     [rsp+48h+var_20], rax
0x14000a055  mov     qword ptr [rdx], 0
0x14000a05c  mov     rdi, rdx
0x14000a05f  mov     eax, [rcx]
0x14000a061  mov     rsi, rcx
0x14000a064  mov     [rdx], eax
0x14000a066  and     eax, 6
0x14000a069  cmp     al, 6
0x14000a06b  jz      loc_14000A1A2
0x14000a071  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000a076  mov     ebp, eax
0x14000a078  mov     [rsp+48h+var_28], 0
0x14000a080  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000a087  mov     r15d, 40h ; '@'
0x14000a08d  test    rax, rax
0x14000a090  jnz     short loc_14000A09E
0x14000a092  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000a099  test    rax, rax
0x14000a09c  jz      short loc_14000A0E8
0x14000a09e  lea     r8, [rsp+48h+var_28]
0x14000a0a3  xor     edx, edx
0x14000a0a5  mov     ecx, 2AC83E1h
0x14000a0aa  call    _guard_dispatch_icall
0x14000a0af  mov     r8d, eax
0x14000a0b2  mov     edx, eax
0x14000a0b4  and     r8d, 0FFFFFF3Fh
0x14000a0bb  and     eax, r15d
0x14000a0be  and     edx, 80h
0x14000a0c4  mov     ecx, r8d
0x14000a0c7  and     ecx, 3
0x14000a0ca  shl     ecx, 2
0x14000a0cd  or      ecx, eax
0x14000a0cf  shl     ecx, 2
0x14000a0d2  or      ecx, edx
0x14000a0d4  shl     ecx, 3
0x14000a0d7  test    r8d, r8d
0x14000a0da  jz      short loc_14000A0EA
0x14000a0dc  xor     eax, eax
0x14000a0de  cmp     r8d, 2
0x14000a0e2  cmovz   eax, r15d
0x14000a0e6  jmp     short loc_14000A0ED
0x14000a0e8  xor     ecx, ecx
0x14000a0ea  mov     eax, r15d
0x14000a0ed  or      ecx, eax
0x14000a0ef  mov     ebx, ecx
0x14000a0f1  shr     ebx, 6
0x14000a0f4  and     ebx, 1
0x14000a0f7  or      ebx, ecx
0x14000a0f9  test    ebp, ebp
0x14000a0fb  jnz     short loc_14000A101
0x14000a0fd  mov     [rsp+48h+var_28], ebp
0x14000a101  mov     eax, [rdi]
0x14000a103  cmp     [rsp+48h+var_28], 0
0x14000a108  mov     edx, eax
0x14000a10a  mov     [rdi], eax
0x14000a10c  mov     ecx, eax
0x14000a10e  jz      short loc_14000A143
0x14000a110  test    dl, 2
0x14000a113  jnz     short loc_14000A143
0x14000a115  mov     eax, ebx
0x14000a117  xor     eax, ecx
0x14000a119  and     eax, 180h
0x14000a11e  xor     eax, ecx
0x14000a120  mov     ecx, eax
0x14000a122  xor     ecx, ebx
0x14000a124  and     ecx, r15d
0x14000a127  xor     ecx, eax
0x14000a129  mov     eax, ecx
0x14000a12b  xor     eax, ebx
0x14000a12d  and     eax, 1
0x14000a130  xor     eax, ecx
0x14000a132  mov     ecx, eax
0x14000a134  xor     ecx, ebx
0x14000a136  and     ecx, 800h
0x14000a13c  xor     ecx, eax
0x14000a13e  or      ecx, 2
0x14000a141  mov     [rdi], ecx
0x14000a143  test    dl, 4
0x14000a146  jnz     short loc_14000A158
0x14000a148  mov     eax, ebx
0x14000a14a  xor     eax, ecx
0x14000a14c  and     eax, 400h
0x14000a151  xor     ecx, eax
0x14000a153  or      ecx, 4
0x14000a156  mov     [rdi], ecx
0x14000a158  mov     eax, edx
0x14000a15a  lock cmpxchg [rsi], ecx
0x14000a15e  jnz     short loc_14000A103
0x14000a160  test    dl, 4
0x14000a163  jnz     short loc_14000A172
0x14000a165  mov     r8d, ebp
0x14000a168  xor     edx, edx
0x14000a16a  mov     rcx, rsi
0x14000a16d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000a172  test    byte ptr [rdi], 2
0x14000a175  jnz     short loc_14000A1A2
0x14000a177  mov     eax, ebx
0x14000a179  xor     eax, [rdi]
0x14000a17b  and     eax, 180h
0x14000a180  xor     eax, [rdi]
0x14000a182  mov     ecx, eax
0x14000a184  xor     ecx, ebx
0x14000a186  and     ecx, r15d
0x14000a189  xor     ecx, eax
0x14000a18b  mov     edx, ecx
0x14000a18d  xor     edx, ebx
0x14000a18f  and     edx, 1
0x14000a192  xor     edx, ecx
0x14000a194  mov     ecx, edx
0x14000a196  xor     ecx, ebx
0x14000a198  and     ecx, 800h
0x14000a19e  xor     ecx, edx
0x14000a1a0  mov     [rdi], ecx
0x14000a1a2  mov     rax, rdi
0x14000a1a5  mov     rcx, [rsp+48h+var_20]
0x14000a1aa  xor     rcx, rsp; StackCookie
0x14000a1ad  call    __security_check_cookie
0x14000a1b2  mov     rbx, [rsp+48h+arg_10]
0x14000a1b7  mov     rbp, [rsp+48h+arg_18]
0x14000a1bc  add     rsp, 30h
0x14000a1c0  pop     r15
0x14000a1c2  pop     rdi
0x14000a1c3  pop     rsi
0x14000a1c4  retn
```
