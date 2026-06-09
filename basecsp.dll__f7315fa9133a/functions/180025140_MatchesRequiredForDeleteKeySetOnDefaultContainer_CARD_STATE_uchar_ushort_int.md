# MatchesRequiredForDeleteKeySetOnDefaultContainer(_CARD_STATE *,uchar *,ushort * *,int *)

- ea: `0x180025140`
- end: `0x1800252c4`
- name: `?MatchesRequiredForDeleteKeySetOnDefaultContainer@@YAKPEAU_CARD_STATE@@PEAEPEAPEAGPEAH@Z`
- size: `388`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned __int8 *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180024b90`

## callees

- `0x18000a772`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x1800196ac`
- `0x180020070`
- `0x180025140`
- `0x180025fe0`
- `0x18002cfa0`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800251e9`
- `msvcrt!wcsnlen` at `0x1800251e9`

## pseudocode

```c
__int64 __fastcall MatchesRequiredForDeleteKeySetOnDefaultContainer(
        struct _CARD_STATE *a1,
        unsigned __int8 *a2,
        unsigned __int16 **a3,
        int *a4)
{
  __int64 v8; // rcx
  PVOID v9; // rcx
  unsigned int DefaultContainer; // ebx
  unsigned __int64 v11; // rdi
  unsigned __int16 *v12; // rax
  __int64 v13; // rcx
  wchar_t Source[48]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(Source, 0, 0x56u);
  WppTraceIndent(v8, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  DefaultContainer = ContainerMapGetDefaultContainer(a1, Source, a2);
  if ( DefaultContainer )
  {
    DefaultContainer = -2146435024;
  }
  else
  {
    v11 = (unsigned int)wcsnlen(Source, 0x28u) + 1;
    v12 = (unsigned __int16 *)MIDL_user_allocate(2 * v11);
    *a3 = v12;
    if ( v12 )
    {
      StringCchCopyNW(v12, v11, Source, 0x28u);
      *a4 = 1;
    }
    else
    {
      WppTraceIndent(v13, 2u);
      DefaultContainer = 8;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          WPP_pszIndent);
      }
    }
  }
  WppTraceIndent((__int64)v9, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      DefaultContainer);
  }
  return DefaultContainer;
}

```

## disassembly

```asm
0x180025140  push    rbx
0x180025142  push    rsi
0x180025143  push    rdi
0x180025144  push    r13
0x180025146  push    r14
0x180025148  sub     rsp, 0A0h
0x18002514f  mov     rax, cs:__security_cookie
0x180025156  xor     rax, rsp
0x180025159  mov     [rsp+0C8h+var_38], rax
0x180025161  mov     rdi, rdx
0x180025164  mov     r14, r8
0x180025167  xor     edx, edx; Val
0x180025169  mov     rbx, rcx
0x18002516c  lea     rcx, [rsp+0C8h+Source]; void *
0x180025171  mov     rsi, r9
0x180025174  lea     r8d, [rdx+56h]; Size
0x180025178  call    memset_0
0x18002517d  xor     edx, edx
0x18002517f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025184  mov     rcx, cs:WPP_GLOBAL_Control
0x18002518b  lea     r13, WPP_GLOBAL_Control
0x180025192  cmp     rcx, r13
0x180025195  jz      short loc_1800251BF
0x180025197  test    byte ptr [rcx+1Ch], 2
0x18002519b  jz      short loc_1800251BF
0x18002519d  cmp     byte ptr [rcx+19h], 5
0x1800251a1  jb      short loc_1800251BF
0x1800251a3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800251aa  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800251b1  mov     rcx, [rcx+10h]
0x1800251b5  mov     edx, 2Bh ; '+'
0x1800251ba  call    WPP_SF_s
0x1800251bf  mov     r8, rdi
0x1800251c2  lea     rdx, [rsp+0C8h+Source]
0x1800251c7  mov     rcx, rbx
0x1800251ca  call    ContainerMapGetDefaultContainer
0x1800251cf  mov     ebx, eax
0x1800251d1  test    eax, eax
0x1800251d3  jz      short loc_1800251DF
0x1800251d5  mov     ebx, 80100030h
0x1800251da  jmp     loc_180025261
0x1800251df  mov     edx, 28h ; '('; MaxCount
0x1800251e4  lea     rcx, [rsp+0C8h+Source]; Source
0x1800251e9  call    cs:__imp_wcsnlen
0x1800251ef  inc     eax
0x1800251f1  mov     edi, eax
0x1800251f3  lea     rcx, [rax+rax]; size
0x1800251f7  call    MIDL_user_allocate
0x1800251fc  mov     [r14], rax
0x1800251ff  test    rax, rax
0x180025202  jnz     short loc_180025245
0x180025204  lea     edx, [rax+2]
0x180025207  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002520c  mov     ebx, 8
0x180025211  mov     rcx, cs:WPP_GLOBAL_Control
0x180025218  cmp     rcx, r13
0x18002521b  jz      short loc_180025261
0x18002521d  test    byte ptr [rcx+1Ch], 1
0x180025221  jz      short loc_180025261
0x180025223  cmp     byte ptr [rcx+19h], 2
0x180025227  jb      short loc_180025261
0x180025229  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025230  lea     edx, [rbx+24h]
0x180025233  mov     rcx, [rcx+10h]
0x180025237  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18002523e  call    WPP_SF_s
0x180025243  jmp     short loc_180025261
0x180025245  mov     r9d, 28h ; '('; unsigned __int64
0x18002524b  lea     r8, [rsp+0C8h+Source]; unsigned __int16 *
0x180025250  mov     rdx, rdi; unsigned __int64
0x180025253  mov     rcx, rax; unsigned __int16 *
0x180025256  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002525b  mov     dword ptr [rsi], 1
0x180025261  mov     edx, 1
0x180025266  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002526b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025272  cmp     rcx, r13
0x180025275  jz      short loc_1800252A3
0x180025277  test    byte ptr [rcx+1Ch], 2
0x18002527b  jz      short loc_1800252A3
0x18002527d  cmp     byte ptr [rcx+19h], 5
0x180025281  jb      short loc_1800252A3
0x180025283  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002528a  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025291  mov     rcx, [rcx+10h]
0x180025295  mov     edx, 2Dh ; '-'
0x18002529a  mov     [rsp+0C8h+var_A8], ebx
0x18002529e  call    WPP_SF_sD
0x1800252a3  mov     eax, ebx
0x1800252a5  mov     rcx, [rsp+0C8h+var_38]
0x1800252ad  xor     rcx, rsp; StackCookie
0x1800252b0  call    __security_check_cookie
0x1800252b5  add     rsp, 0A0h
0x1800252bc  pop     r14
0x1800252be  pop     r13
0x1800252c0  pop     rdi
0x1800252c1  pop     rsi
0x1800252c2  pop     rbx
0x1800252c3  retn
```
