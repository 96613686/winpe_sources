# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetCachedFeatureEnabledState(void)

- ea: `0x180009128`
- end: `0x1800092df`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c84`
- `0x18000a368`

## callees

- `0x1800044e4`
- `0x180007690`
- `0x180009128`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // al
  int v10; // eax
  int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  int v15; // r8d
  int v16; // r9d
  signed __int32 v17; // ecx
  wil::details *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ModernizeSecMgrCreationInShell__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ModernizeSecMgrCreationInShell__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(54845141, 3, &v19);
  }
  else
  {
    v6 = 0;
  }
  v7 = 0;
  if ( (v6 & 0xFFFFFF3F) == 2 )
    v7 = 64;
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
      goto LABEL_15;
    v9 = 0;
  }
  if ( (v8 & 0x40) == 0 || !v9 )
  {
    v10 = 0;
    goto LABEL_16;
  }
LABEL_15:
  v10 = 1;
LABEL_16:
  v11 = v10 | v8;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = (_DWORD)v19 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    if ( v13 || (v12 & 2) != 0 )
    {
      v15 = v12;
    }
    else
    {
      v15 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v11)
                              & 0x180
                              ^ (v11
                               ^ v12
                               ^ (v12
                                ^ v11)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v11
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v16 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v17 = v15;
    }
    else
    {
      v17 = v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 | 4;
      *(_DWORD *)a2 = v17;
    }
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_ModernizeSecMgrCreationInShell__descriptor,
            v17,
            v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_ModernizeSecMgrCreationInShell__descriptor,
      3,
      v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v11
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v11
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v11
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x180009128  mov     [rsp+arg_8], rbx
0x18000912d  mov     [rsp+arg_10], rbp
0x180009132  mov     [rsp+arg_0], rcx
0x180009137  push    rsi
0x180009138  push    rdi
0x180009139  push    r12
0x18000913b  sub     rsp, 20h
0x18000913f  mov     rsi, cs:Feature_ModernizeSecMgrCreationInShell__descriptor
0x180009146  mov     rdi, rdx
0x180009149  mov     qword ptr [rdx], 0
0x180009150  mov     eax, [rsi]
0x180009152  mov     [rdx], eax
0x180009154  and     eax, 6
0x180009157  cmp     al, 6
0x180009159  jz      loc_1800092C9
0x18000915f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180009164  mov     ebp, eax
0x180009166  mov     dword ptr [rsp+38h+arg_0], 0
0x18000916e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180009175  test    rax, rax
0x180009178  jz      short loc_180009192
0x18000917a  lea     r8, [rsp+38h+arg_0]
0x18000917f  mov     edx, 3
0x180009184  mov     ecx, 344DED5h
0x180009189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000918e  mov     edx, eax
0x180009190  jmp     short loc_1800091A0
0x180009192  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180009199  test    rax, rax
0x18000919c  jnz     short loc_18000917A
0x18000919e  xor     edx, edx
0x1800091a0  mov     r8d, edx
0x1800091a3  mov     eax, edx
0x1800091a5  and     r8d, 0FFFFFF3Fh
0x1800091ac  and     edx, 80h
0x1800091b2  mov     ecx, r8d
0x1800091b5  mov     r12d, 40h ; '@'
0x1800091bb  and     ecx, 3
0x1800091be  and     eax, r12d
0x1800091c1  shl     ecx, 2
0x1800091c4  or      ecx, eax
0x1800091c6  xor     eax, eax
0x1800091c8  shl     ecx, 2
0x1800091cb  or      ecx, edx
0x1800091cd  lea     ebx, ds:0[rcx*8]
0x1800091d4  test    r8d, r8d
0x1800091d7  jz      short loc_1800091E1
0x1800091d9  cmp     r8d, 2
0x1800091dd  cmovz   eax, r12d
0x1800091e1  or      ebx, eax
0x1800091e3  mov     edx, 0C00h
0x1800091e8  mov     ecx, ebx
0x1800091ea  mov     eax, ebx
0x1800091ec  and     ecx, r12d
0x1800091ef  and     eax, edx
0x1800091f1  cmp     eax, edx
0x1800091f3  jnz     short loc_1800091F9
0x1800091f5  mov     al, 1
0x1800091f7  jmp     short loc_1800091FF
0x1800091f9  test    ecx, ecx
0x1800091fb  jnz     short loc_18000920B
0x1800091fd  xor     al, al
0x1800091ff  test    ecx, ecx
0x180009201  jz      short loc_180009207
0x180009203  test    al, al
0x180009205  jnz     short loc_18000920B
0x180009207  xor     eax, eax
0x180009209  jmp     short loc_180009210
0x18000920b  mov     eax, 1
0x180009210  or      ebx, eax
0x180009212  mov     eax, [rdi]
0x180009214  cmp     dword ptr [rsp+38h+arg_0], 0
0x180009219  mov     edx, eax
0x18000921b  mov     [rdi], eax
0x18000921d  jz      short loc_18000925A
0x18000921f  test    dl, 2
0x180009222  jnz     short loc_18000925A
0x180009224  mov     eax, ebx
0x180009226  xor     eax, edx
0x180009228  and     eax, 180h
0x18000922d  xor     eax, edx
0x18000922f  mov     ecx, eax
0x180009231  xor     ecx, ebx
0x180009233  and     ecx, r12d
0x180009236  xor     ecx, eax
0x180009238  mov     eax, ecx
0x18000923a  xor     eax, ebx
0x18000923c  and     eax, 1
0x18000923f  xor     eax, ecx
0x180009241  mov     r8d, eax
0x180009244  xor     r8d, ebx
0x180009247  and     r8d, 800h
0x18000924e  xor     r8d, eax
0x180009251  or      r8d, 2
0x180009255  mov     [rdi], r8d
0x180009258  jmp     short loc_18000925D
0x18000925a  mov     r8d, edx
0x18000925d  mov     r9d, edx
0x180009260  and     r9d, 4
0x180009264  jnz     short loc_18000927B
0x180009266  mov     ecx, ebx
0x180009268  xor     ecx, r8d
0x18000926b  and     ecx, 400h
0x180009271  xor     ecx, r8d
0x180009274  or      ecx, 4
0x180009277  mov     [rdi], ecx
0x180009279  jmp     short loc_18000927E
0x18000927b  mov     ecx, r8d
0x18000927e  mov     eax, edx
0x180009280  lock cmpxchg [rsi], ecx
0x180009284  jnz     short loc_180009214
0x180009286  test    r9d, r9d
0x180009289  jnz     short loc_18000929A
0x18000928b  mov     r8d, ebp
0x18000928e  lea     edx, [r9+3]
0x180009292  mov     rcx, rsi
0x180009295  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000929a  test    byte ptr [rdi], 2
0x18000929d  jnz     short loc_1800092C9
0x18000929f  mov     eax, [rdi]
0x1800092a1  xor     eax, ebx
0x1800092a3  and     eax, 180h
0x1800092a8  xor     eax, [rdi]
0x1800092aa  mov     ecx, eax
0x1800092ac  xor     ecx, ebx
0x1800092ae  and     ecx, r12d
0x1800092b1  xor     ecx, eax
0x1800092b3  mov     edx, ecx
0x1800092b5  xor     edx, ebx
0x1800092b7  and     edx, 1
0x1800092ba  xor     edx, ecx
0x1800092bc  mov     eax, edx
0x1800092be  xor     eax, ebx
0x1800092c0  and     eax, 800h
0x1800092c5  xor     eax, edx
0x1800092c7  mov     [rdi], eax
0x1800092c9  mov     rbx, [rsp+38h+arg_8]
0x1800092ce  mov     rax, rdi
0x1800092d1  mov     rbp, [rsp+38h+arg_10]
0x1800092d6  add     rsp, 20h
0x1800092da  pop     r12
0x1800092dc  pop     rdi
0x1800092dd  pop     rsi
0x1800092de  retn
```
