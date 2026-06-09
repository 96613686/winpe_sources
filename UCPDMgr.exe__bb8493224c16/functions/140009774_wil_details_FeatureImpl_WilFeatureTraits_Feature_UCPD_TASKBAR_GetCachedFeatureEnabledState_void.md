# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::GetCachedFeatureEnabledState(void)

- ea: `0x140009774`
- end: `0x140009904`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140005a78`
- `0x14000990c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140009774`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::GetCachedFeatureEnabledState(
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
    v7 = v6(47443885, 0, &v19);
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
0x140009774  mov     [rsp+arg_10], rbx
0x140009779  mov     [rsp+arg_18], rbp
0x14000977e  push    rsi
0x14000977f  push    rdi
0x140009780  push    r15
0x140009782  sub     rsp, 30h
0x140009786  mov     rax, cs:__security_cookie
0x14000978d  xor     rax, rsp
0x140009790  mov     [rsp+48h+var_20], rax
0x140009795  mov     qword ptr [rdx], 0
0x14000979c  mov     rdi, rdx
0x14000979f  mov     eax, [rcx]
0x1400097a1  mov     rsi, rcx
0x1400097a4  mov     [rdx], eax
0x1400097a6  and     eax, 6
0x1400097a9  cmp     al, 6
0x1400097ab  jz      loc_1400098E1
0x1400097b1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400097b6  mov     ebp, eax
0x1400097b8  mov     [rsp+48h+var_28], 0
0x1400097c0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400097c7  mov     r15d, 40h ; '@'
0x1400097cd  test    rax, rax
0x1400097d0  jnz     short loc_1400097DE
0x1400097d2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400097d9  test    rax, rax
0x1400097dc  jz      short loc_14000982A
0x1400097de  lea     r8, [rsp+48h+var_28]
0x1400097e3  xor     edx, edx
0x1400097e5  mov     ecx, 2D3EFADh
0x1400097ea  call    _guard_dispatch_icall
0x1400097ef  mov     r8d, eax
0x1400097f2  mov     edx, eax
0x1400097f4  and     r8d, 0FFFFFF3Fh
0x1400097fb  and     eax, r15d
0x1400097fe  and     edx, 80h
0x140009804  mov     ecx, r8d
0x140009807  and     ecx, 3
0x14000980a  shl     ecx, 2
0x14000980d  or      ecx, eax
0x14000980f  shl     ecx, 2
0x140009812  or      ecx, edx
0x140009814  shl     ecx, 3
0x140009817  test    r8d, r8d
0x14000981a  jz      short loc_14000982C
0x14000981c  xor     eax, eax
0x14000981e  cmp     r8d, 2
0x140009822  cmovz   eax, r15d
0x140009826  or      eax, ecx
0x140009828  jmp     short loc_14000982E
0x14000982a  xor     ecx, ecx
0x14000982c  mov     eax, ecx
0x14000982e  mov     ebx, eax
0x140009830  shr     ebx, 6
0x140009833  and     ebx, 1
0x140009836  or      ebx, eax
0x140009838  test    ebp, ebp
0x14000983a  jnz     short loc_140009840
0x14000983c  mov     [rsp+48h+var_28], ebp
0x140009840  mov     eax, [rdi]
0x140009842  cmp     [rsp+48h+var_28], 0
0x140009847  mov     edx, eax
0x140009849  mov     [rdi], eax
0x14000984b  mov     ecx, eax
0x14000984d  jz      short loc_140009882
0x14000984f  test    dl, 2
0x140009852  jnz     short loc_140009882
0x140009854  mov     eax, ebx
0x140009856  xor     eax, ecx
0x140009858  and     eax, 180h
0x14000985d  xor     eax, ecx
0x14000985f  mov     ecx, eax
0x140009861  xor     ecx, ebx
0x140009863  and     ecx, r15d
0x140009866  xor     ecx, eax
0x140009868  mov     eax, ecx
0x14000986a  xor     eax, ebx
0x14000986c  and     eax, 1
0x14000986f  xor     eax, ecx
0x140009871  mov     ecx, eax
0x140009873  xor     ecx, ebx
0x140009875  and     ecx, 800h
0x14000987b  xor     ecx, eax
0x14000987d  or      ecx, 2
0x140009880  mov     [rdi], ecx
0x140009882  test    dl, 4
0x140009885  jnz     short loc_140009897
0x140009887  mov     eax, ebx
0x140009889  xor     eax, ecx
0x14000988b  and     eax, 400h
0x140009890  xor     ecx, eax
0x140009892  or      ecx, 4
0x140009895  mov     [rdi], ecx
0x140009897  mov     eax, edx
0x140009899  lock cmpxchg [rsi], ecx
0x14000989d  jnz     short loc_140009842
0x14000989f  test    dl, 4
0x1400098a2  jnz     short loc_1400098B1
0x1400098a4  mov     r8d, ebp
0x1400098a7  xor     edx, edx
0x1400098a9  mov     rcx, rsi
0x1400098ac  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400098b1  test    byte ptr [rdi], 2
0x1400098b4  jnz     short loc_1400098E1
0x1400098b6  mov     eax, ebx
0x1400098b8  xor     eax, [rdi]
0x1400098ba  and     eax, 180h
0x1400098bf  xor     eax, [rdi]
0x1400098c1  mov     ecx, eax
0x1400098c3  xor     ecx, ebx
0x1400098c5  and     ecx, r15d
0x1400098c8  xor     ecx, eax
0x1400098ca  mov     edx, ecx
0x1400098cc  xor     edx, ebx
0x1400098ce  and     edx, 1
0x1400098d1  xor     edx, ecx
0x1400098d3  mov     ecx, edx
0x1400098d5  xor     ecx, ebx
0x1400098d7  and     ecx, 800h
0x1400098dd  xor     ecx, edx
0x1400098df  mov     [rdi], ecx
0x1400098e1  mov     rax, rdi
0x1400098e4  mov     rcx, [rsp+48h+var_20]
0x1400098e9  xor     rcx, rsp; StackCookie
0x1400098ec  call    __security_check_cookie
0x1400098f1  mov     rbx, [rsp+48h+arg_10]
0x1400098f6  mov     rbp, [rsp+48h+arg_18]
0x1400098fb  add     rsp, 30h
0x1400098ff  pop     r15
0x140009901  pop     rdi
0x140009902  pop     rsi
0x140009903  retn
```
