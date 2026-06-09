# FeedbackParamsCache<ForceFeedbackEffectParams>::CompareParams(ForceFeedbackEffectParams const &,ForceFeedbackEffectParams const &)

- ea: `0x1800123f0`
- end: `0x1800124e1`
- name: `?CompareParams@?$FeedbackParamsCache@UForceFeedbackEffectParams@@@@CA_NAEBUForceFeedbackEffectParams@@0@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ef98`

## callees

- `0x180012258`
- `0x1800122c4`
- `0x180012328`
- `0x180012390`
- `0x1800123f0`

## pseudocode

```c
char __fastcall FeedbackParamsCache<ForceFeedbackEffectParams>::CompareParams(__int64 a1, __int64 a2)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  char result; // al
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx

  if ( *(float *)a1 != *(float *)a2 )
    return 1;
  if ( *(_QWORD *)(a1 + 8) != *(_QWORD *)(a2 + 8) )
    return 1;
  v3 = *(_DWORD *)(a1 + 16);
  if ( v3 != *(_DWORD *)(a2 + 16) )
    return 1;
  if ( v3 > 5 )
  {
    v15 = v3 - 6;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( !v16 )
        return anonymous_namespace_::CompareForceFeedbackConditionParams(a1 + 24, a2 + 24);
      v17 = v16 - 1;
      if ( !v17 || (unsigned int)(v17 - 1) <= 1 )
        return anonymous_namespace_::CompareForceFeedbackConditionParams(a1 + 24, a2 + 24);
      return 1;
    }
    return anonymous_namespace_::CompareForceFeedbackPeriodicParams(a1 + 24, a2 + 24);
  }
  if ( v3 == 5 )
    return anonymous_namespace_::CompareForceFeedbackPeriodicParams(a1 + 24, a2 + 24);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( !v5 || (unsigned int)(v5 - 1) <= 1 )
        return anonymous_namespace_::CompareForceFeedbackPeriodicParams(a1 + 24, a2 + 24);
      return 1;
    }
    if ( (unsigned __int8)anonymous_namespace_::CompareForceFeedbackEnvelope(a1 + 24, a2 + 24)
      || (unsigned __int8)anonymous_namespace_::CompareForceFeedbackMagnitude(v7 + 72, v8 + 48) )
    {
      return 1;
    }
    v11 = v10 + 76;
    v12 = v9 + 100;
  }
  else
  {
    if ( (unsigned __int8)anonymous_namespace_::CompareForceFeedbackEnvelope(a1 + 24, a2 + 24) )
      return 1;
    v11 = v13 + 48;
    v12 = v14 + 48;
  }
  result = anonymous_namespace_::CompareForceFeedbackMagnitude(v12, v11);
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1800123f0  sub     rsp, 28h
0x1800123f4  movss   xmm0, dword ptr [rcx]
0x1800123f8  mov     r8, rcx
0x1800123fb  ucomiss xmm0, dword ptr [rdx]
0x1800123fe  jp      loc_1800124D9
0x180012404  jnz     loc_1800124D9
0x18001240a  mov     rax, [rdx+8]
0x18001240e  cmp     [rcx+8], rax
0x180012412  jnz     loc_1800124D9
0x180012418  mov     ecx, [rcx+10h]
0x18001241b  cmp     ecx, [rdx+10h]
0x18001241e  jnz     loc_1800124D9
0x180012424  cmp     ecx, 5
0x180012427  jg      loc_1800124AF
0x18001242d  jz      short loc_18001244B
0x18001242f  test    ecx, ecx
0x180012431  jz      short loc_180012494
0x180012433  sub     ecx, 1
0x180012436  jz      short loc_18001245C
0x180012438  sub     ecx, 1
0x18001243b  jz      short loc_18001244B
0x18001243d  sub     ecx, 1
0x180012440  jz      short loc_18001244B
0x180012442  cmp     ecx, 1
0x180012445  jnz     loc_1800124D9
0x18001244b  add     rdx, 18h
0x18001244f  lea     rcx, [r8+18h]
0x180012453  add     rsp, 28h
0x180012457  jmp     _anonymous_namespace___CompareForceFeedbackPeriodicParams
0x18001245c  lea     r9, [rdx+18h]
0x180012460  mov     rdx, r9
0x180012463  lea     rcx, [r8+18h]
0x180012467  call    _anonymous_namespace___CompareForceFeedbackEnvelope
0x18001246c  test    al, al
0x18001246e  jnz     short loc_1800124D9
0x180012470  lea     rdx, [r9+30h]
0x180012474  lea     rcx, [r8+48h]
0x180012478  call    _anonymous_namespace___CompareForceFeedbackMagnitude
0x18001247d  test    al, al
0x18001247f  jnz     short loc_1800124D9
0x180012481  lea     rdx, [r9+4Ch]
0x180012485  lea     rcx, [r8+64h]
0x180012489  call    _anonymous_namespace___CompareForceFeedbackMagnitude
0x18001248e  test    al, al
0x180012490  jnz     short loc_1800124D9
0x180012492  jmp     short loc_1800124DB
0x180012494  add     rdx, 18h
0x180012498  lea     rcx, [r8+18h]
0x18001249c  call    _anonymous_namespace___CompareForceFeedbackEnvelope
0x1800124a1  test    al, al
0x1800124a3  jnz     short loc_1800124D9
0x1800124a5  add     rdx, 30h ; '0'
0x1800124a9  add     rcx, 30h ; '0'
0x1800124ad  jmp     short loc_180012489
0x1800124af  sub     ecx, 6
0x1800124b2  jz      short loc_18001244B
0x1800124b4  sub     ecx, 1
0x1800124b7  jz      short loc_1800124C8
0x1800124b9  sub     ecx, 1
0x1800124bc  jz      short loc_1800124C8
0x1800124be  sub     ecx, 1
0x1800124c1  jz      short loc_1800124C8
0x1800124c3  cmp     ecx, 1
0x1800124c6  jnz     short loc_1800124D9
0x1800124c8  add     rdx, 18h
0x1800124cc  lea     rcx, [r8+18h]
0x1800124d0  add     rsp, 28h
0x1800124d4  jmp     _anonymous_namespace___CompareForceFeedbackConditionParams
0x1800124d9  mov     al, 1
0x1800124db  add     rsp, 28h
0x1800124df  retn
```
