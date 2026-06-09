# MatchesRequiredForOpenAuthorityKeySet(_CARD_STATE *,uchar *)

- ea: `0x1800254b0`
- end: `0x1800255db`
- name: `?MatchesRequiredForOpenAuthorityKeySet@@YAKPEAU_CARD_STATE@@PEAE@Z`
- size: `299`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180024b90`

## callees

- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x1800254b0`
- `0x18002e010`

## pseudocode

```c
__int64 __fastcall MatchesRequiredForOpenAuthorityKeySet(struct _CARD_STATE *a1, unsigned __int8 *a2)
{
  PVOID v4; // rcx
  __int64 v5; // rax
  unsigned int v6; // ebx
  int v8; // [rsp+40h] [rbp+8h] BYREF

  v8 = 0;
  WppTraceIndent((__int64)a1, 0);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  v5 = *((_QWORD *)a1 + 1);
  if ( *(_DWORD *)(v5 + 512) )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, int *))(v5 + 520))(*((_QWORD *)a1 + 1), &v8);
    if ( v6 )
    {
      WppTraceIndent((__int64)v4, 2u);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          (_DWORD)WPP_pszIndent,
          v6);
      }
    }
    else
    {
      *a2 = v8;
    }
  }
  else
  {
    v6 = -2146435024;
  }
  WppTraceIndent((__int64)v4, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800254b0  mov     [rsp+arg_8], rbx
0x1800254b5  mov     [rsp+arg_10], rbp
0x1800254ba  push    rdi
0x1800254bb  sub     rsp, 30h
0x1800254bf  mov     rdi, rdx
0x1800254c2  mov     [rsp+38h+arg_0], 0
0x1800254ca  xor     edx, edx
0x1800254cc  mov     rbx, rcx
0x1800254cf  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800254d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254db  lea     rbp, WPP_GLOBAL_Control
0x1800254e2  cmp     rcx, rbp
0x1800254e5  jz      short loc_18002550F
0x1800254e7  test    byte ptr [rcx+1Ch], 2
0x1800254eb  jz      short loc_18002550F
0x1800254ed  cmp     byte ptr [rcx+19h], 5
0x1800254f1  jb      short loc_18002550F
0x1800254f3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800254fa  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025501  mov     rcx, [rcx+10h]
0x180025505  mov     edx, 26h ; '&'
0x18002550a  call    WPP_SF_s
0x18002550f  mov     rax, [rbx+8]
0x180025513  cmp     dword ptr [rax+200h], 1
0x18002551a  jnb     short loc_180025523
0x18002551c  mov     ebx, 80100030h
0x180025521  jmp     short loc_180025587
0x180025523  mov     rcx, rax
0x180025526  lea     rdx, [rsp+38h+arg_0]
0x18002552b  mov     rax, [rax+208h]
0x180025532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025537  mov     ebx, eax
0x180025539  test    eax, eax
0x18002553b  jz      short loc_180025581
0x18002553d  mov     edx, 2
0x180025542  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025547  mov     rcx, cs:WPP_GLOBAL_Control
0x18002554e  cmp     rcx, rbp
0x180025551  jz      short loc_180025587
0x180025553  test    byte ptr [rcx+1Ch], 1
0x180025557  jz      short loc_180025587
0x180025559  cmp     byte ptr [rcx+19h], 2
0x18002555d  jb      short loc_180025587
0x18002555f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025566  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18002556d  mov     rcx, [rcx+10h]
0x180025571  mov     edx, 27h ; '''
0x180025576  mov     [rsp+38h+var_18], ebx
0x18002557a  call    WPP_SF_sD
0x18002557f  jmp     short loc_180025587
0x180025581  mov     al, byte ptr [rsp+38h+arg_0]
0x180025585  mov     [rdi], al
0x180025587  mov     edx, 1
0x18002558c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025591  mov     rcx, cs:WPP_GLOBAL_Control
0x180025598  cmp     rcx, rbp
0x18002559b  jz      short loc_1800255C9
0x18002559d  test    byte ptr [rcx+1Ch], 2
0x1800255a1  jz      short loc_1800255C9
0x1800255a3  cmp     byte ptr [rcx+19h], 5
0x1800255a7  jb      short loc_1800255C9
0x1800255a9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800255b0  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800255b7  mov     rcx, [rcx+10h]
0x1800255bb  mov     edx, 28h ; '('
0x1800255c0  mov     [rsp+38h+var_18], ebx
0x1800255c4  call    WPP_SF_sD
0x1800255c9  mov     rbp, [rsp+38h+arg_10]
0x1800255ce  mov     eax, ebx
0x1800255d0  mov     rbx, [rsp+38h+arg_8]
0x1800255d5  add     rsp, 30h
0x1800255d9  pop     rdi
0x1800255da  retn
```
