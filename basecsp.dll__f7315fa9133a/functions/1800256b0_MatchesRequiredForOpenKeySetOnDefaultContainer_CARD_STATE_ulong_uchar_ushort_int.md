# MatchesRequiredForOpenKeySetOnDefaultContainer(_CARD_STATE *,ulong,uchar *,ushort * *,int *)

- ea: `0x1800256b0`
- end: `0x180025878`
- name: `?MatchesRequiredForOpenKeySetOnDefaultContainer@@YAKPEAU_CARD_STATE@@KPEAEPEAPEAGPEAH@Z`
- size: `456`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned int, unsigned __int8 *, unsigned __int16 **, int *)`
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
- `0x1800256b0`
- `0x180025fe0`
- `0x18002cfa0`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180025793`
- `msvcrt!wcsnlen` at `0x180025793`

## pseudocode

```c
__int64 __fastcall MatchesRequiredForOpenKeySetOnDefaultContainer(
        struct _CARD_STATE *a1,
        int a2,
        unsigned __int8 *a3,
        unsigned __int16 **a4,
        int *a5)
{
  __int64 v9; // rcx
  unsigned int DefaultContainer; // ebx
  __int64 v11; // rcx
  unsigned __int64 v12; // rdi
  unsigned __int16 *v13; // rax
  __int64 v14; // rcx
  wchar_t Source[48]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(Source, 0, 0x56u);
  WppTraceIndent(v9, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  DefaultContainer = ContainerMapGetDefaultContainer(a1, Source, a3);
  if ( DefaultContainer )
  {
    v11 = 4026531840LL;
    LOBYTE(v11) = (a2 & 0xF0000000) != -268435456;
    if ( ((unsigned __int8)v11 & ((a2 & 0x80u) == 0)) != 0 )
    {
      DefaultContainer = -2146435024;
    }
    else
    {
      *a3 = -1;
      DefaultContainer = 0;
      *a5 = 0;
      *a4 = 0;
    }
  }
  else
  {
    v12 = (unsigned int)wcsnlen(Source, 0x28u) + 1;
    v13 = (unsigned __int16 *)MIDL_user_allocate(2 * v12);
    *a4 = v13;
    if ( v13 )
    {
      StringCchCopyNW(v13, v12, Source, 0x28u);
      *a5 = 1;
    }
    else
    {
      WppTraceIndent(v14, 2u);
      DefaultContainer = 8;
      v11 = (__int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          WPP_pszIndent);
      }
    }
  }
  WppTraceIndent(v11, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      DefaultContainer);
  }
  return DefaultContainer;
}

```

## disassembly

```asm
0x1800256b0  push    rbx
0x1800256b2  push    rsi
0x1800256b3  push    rdi
0x1800256b4  push    r14
0x1800256b6  push    r15
0x1800256b8  sub     rsp, 0A0h
0x1800256bf  mov     rax, cs:__security_cookie
0x1800256c6  xor     rax, rsp
0x1800256c9  mov     [rsp+0C8h+var_38], rax
0x1800256d1  mov     r14, [rsp+0C8h+arg_20]
0x1800256d9  mov     esi, edx
0x1800256db  xor     edx, edx; Val
0x1800256dd  mov     rdi, r8
0x1800256e0  mov     rbx, rcx
0x1800256e3  mov     r15, r9
0x1800256e6  lea     rcx, [rsp+0C8h+Source]; void *
0x1800256eb  lea     r8d, [rdx+56h]; Size
0x1800256ef  call    memset_0
0x1800256f4  xor     edx, edx
0x1800256f6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800256fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180025702  lea     rax, WPP_GLOBAL_Control
0x180025709  cmp     rcx, rax
0x18002570c  jz      short loc_180025736
0x18002570e  test    byte ptr [rcx+1Ch], 2
0x180025712  jz      short loc_180025736
0x180025714  cmp     byte ptr [rcx+19h], 5
0x180025718  jb      short loc_180025736
0x18002571a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025721  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025728  mov     rcx, [rcx+10h]
0x18002572c  mov     edx, 23h ; '#'
0x180025731  call    WPP_SF_s
0x180025736  mov     r8, rdi
0x180025739  lea     rdx, [rsp+0C8h+Source]
0x18002573e  mov     rcx, rbx
0x180025741  call    ContainerMapGetDefaultContainer
0x180025746  mov     ebx, eax
0x180025748  test    eax, eax
0x18002574a  jz      short loc_180025787
0x18002574c  mov     ecx, 0F0000000h
0x180025751  mov     eax, esi
0x180025753  and     eax, ecx
0x180025755  cmp     eax, ecx
0x180025757  setnz   cl
0x18002575a  test    sil, 80h
0x18002575e  setz    al
0x180025761  test    al, cl
0x180025763  jz      short loc_18002576F
0x180025765  mov     ebx, 80100030h
0x18002576a  jmp     loc_18002580E
0x18002576f  mov     byte ptr [rdi], 0FFh
0x180025772  xor     ebx, ebx
0x180025774  mov     dword ptr [r14], 0
0x18002577b  mov     qword ptr [r15], 0
0x180025782  jmp     loc_18002580E
0x180025787  mov     esi, 28h ; '('
0x18002578c  lea     rcx, [rsp+0C8h+Source]; Source
0x180025791  mov     edx, esi; MaxCount
0x180025793  call    cs:__imp_wcsnlen
0x180025799  inc     eax
0x18002579b  mov     edi, eax
0x18002579d  lea     rcx, [rax+rax]; size
0x1800257a1  call    MIDL_user_allocate
0x1800257a6  mov     [r15], rax
0x1800257a9  test    rax, rax
0x1800257ac  jnz     short loc_1800257F4
0x1800257ae  lea     edx, [rsi-26h]
0x1800257b1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800257b6  lea     ebx, [rsi-20h]
0x1800257b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257c0  lea     rdi, WPP_GLOBAL_Control
0x1800257c7  cmp     rcx, rdi
0x1800257ca  jz      short loc_180025815
0x1800257cc  test    byte ptr [rcx+1Ch], 1
0x1800257d0  jz      short loc_180025815
0x1800257d2  cmp     byte ptr [rcx+19h], 2
0x1800257d6  jb      short loc_180025815
0x1800257d8  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800257df  lea     edx, [rsi-4]
0x1800257e2  mov     rcx, [rcx+10h]
0x1800257e6  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800257ed  call    WPP_SF_s
0x1800257f2  jmp     short loc_180025815
0x1800257f4  mov     r9, rsi; unsigned __int64
0x1800257f7  lea     r8, [rsp+0C8h+Source]; unsigned __int16 *
0x1800257fc  mov     rdx, rdi; unsigned __int64
0x1800257ff  mov     rcx, rax; unsigned __int16 *
0x180025802  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180025807  mov     dword ptr [r14], 1
0x18002580e  lea     rdi, WPP_GLOBAL_Control
0x180025815  mov     edx, 1
0x18002581a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002581f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025826  cmp     rcx, rdi
0x180025829  jz      short loc_180025857
0x18002582b  test    byte ptr [rcx+1Ch], 2
0x18002582f  jz      short loc_180025857
0x180025831  cmp     byte ptr [rcx+19h], 5
0x180025835  jb      short loc_180025857
0x180025837  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002583e  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025845  mov     rcx, [rcx+10h]
0x180025849  mov     edx, 25h ; '%'
0x18002584e  mov     [rsp+0C8h+var_A8], ebx
0x180025852  call    WPP_SF_sD
0x180025857  mov     eax, ebx
0x180025859  mov     rcx, [rsp+0C8h+var_38]
0x180025861  xor     rcx, rsp; StackCookie
0x180025864  call    __security_check_cookie
0x180025869  add     rsp, 0A0h
0x180025870  pop     r15
0x180025872  pop     r14
0x180025874  pop     rdi
0x180025875  pop     rsi
0x180025876  pop     rbx
0x180025877  retn
```
