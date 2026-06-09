# GetCachedCardData

- ea: `0x18002217c`
- end: `0x1800222fd`
- name: `GetCachedCardData`
- size: `385`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x18001cd44`
- `0x18001ced4`
- `0x18001d064`
- `0x18001ded8`
- `0x18001e66c`

## callees

- `0x18000a766`
- `0x18000a772`
- `0x18000de80`
- `0x180016e0c`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x180021bc8`
- `0x18002217c`
- `0x18002cfa0`

## pseudocode

```c
__int64 __fastcall GetCachedCardData(
        __int64 a1,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        _QWORD *a5,
        _DWORD *a6,
        _DWORD *a7)
{
  unsigned int CardCacheForItem; // esi
  size_t v12; // rbx
  void *v13; // rax
  __int64 v14; // rcx
  void *v15; // rdi
  __int64 v17; // [rsp+20h] [rbp-288h] BYREF
  int v18; // [rsp+28h] [rbp-280h]
  int v19; // [rsp+2Ch] [rbp-27Ch]
  _BYTE v20[4]; // [rsp+30h] [rbp-278h] BYREF
  unsigned __int16 v21[266]; // [rsp+34h] [rbp-274h] BYREF
  _DWORD *v22; // [rsp+248h] [rbp-60h]

  memset_0(v20, 0, 0x228u);
  if ( !a5 || !a6 )
    return 2148532228LL;
  *a5 = 0;
  *a6 = 0;
  v18 = a3;
  v19 = a4;
  v17 = a1;
  StringCbCopyW(v21, 0x208u, a2);
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v17);
  if ( CardCacheForItem )
  {
    v15 = 0;
    LODWORD(v12) = 0;
  }
  else
  {
    v12 = (unsigned int)v22[3];
    v13 = MIDL_user_allocate(v12);
    v15 = v13;
    if ( !v13 )
    {
      WppTraceIndent(v14, 2u);
      CardCacheForItem = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_13;
    }
    memcpy_0(v13, v22 + 4, v12);
    if ( a7 )
      *a7 = v22[2];
  }
  *a5 = v15;
  *a6 = v12;
LABEL_13:
  if ( v22 )
    CspFreeH(v22);
  return CardCacheForItem;
}

```

## disassembly

```asm
0x18002217c  push    rbx
0x18002217e  push    rbp
0x18002217f  push    rsi
0x180022180  push    rdi
0x180022181  push    r12
0x180022183  push    r14
0x180022185  push    r15
0x180022187  sub     rsp, 270h
0x18002218e  mov     rax, cs:__security_cookie
0x180022195  xor     rax, rsp
0x180022198  mov     [rsp+2A8h+var_48], rax
0x1800221a0  mov     r15, [rsp+2A8h+arg_20]
0x1800221a8  mov     esi, r8d
0x1800221ab  mov     r14, [rsp+2A8h+arg_28]
0x1800221b3  mov     rdi, rdx
0x1800221b6  mov     rbp, [rsp+2A8h+arg_30]
0x1800221be  mov     rbx, rcx
0x1800221c1  xor     edx, edx; Val
0x1800221c3  lea     rcx, [rsp+2A8h+var_278]; void *
0x1800221c8  mov     r8d, 228h; Size
0x1800221ce  mov     r12d, r9d
0x1800221d1  call    memset_0
0x1800221d6  test    r15, r15
0x1800221d9  jz      loc_1800222D6
0x1800221df  test    r14, r14
0x1800221e2  jz      loc_1800222D6
0x1800221e8  mov     qword ptr [r15], 0
0x1800221ef  lea     rcx, [rsp+2A8h+var_274]; unsigned __int16 *
0x1800221f4  mov     r8, rdi; unsigned __int16 *
0x1800221f7  mov     dword ptr [r14], 0
0x1800221fe  mov     edx, 208h; unsigned __int64
0x180022203  mov     [rsp+2A8h+var_280], esi
0x180022207  mov     [rsp+2A8h+var_27C], r12d
0x18002220c  mov     [rsp+2A8h+var_288], rbx
0x180022211  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180022216  lea     rcx, [rsp+2A8h+var_288]; struct _CARD_CACHE_QUERY_INFO *
0x18002221b  call    CspQueryCardCacheForItem
0x180022220  mov     esi, eax
0x180022222  test    eax, eax
0x180022224  jnz     loc_1800222B6
0x18002222a  mov     rcx, [rsp+2A8h+var_60]
0x180022232  mov     ebx, [rcx+0Ch]
0x180022235  mov     ecx, ebx; size
0x180022237  call    MIDL_user_allocate
0x18002223c  mov     rdi, rax
0x18002223f  test    rax, rax
0x180022242  jnz     short loc_18002228A
0x180022244  lea     edx, [rsi+2]
0x180022247  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002224c  lea     esi, [rdi+8]
0x18002224f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022256  lea     rax, WPP_GLOBAL_Control
0x18002225d  cmp     rcx, rax
0x180022260  jz      short loc_1800222C0
0x180022262  test    byte ptr [rcx+1Ch], 1
0x180022266  jz      short loc_1800222C0
0x180022268  cmp     byte ptr [rcx+19h], 2
0x18002226c  jb      short loc_1800222C0
0x18002226e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180022275  lea     edx, [rdi+16h]
0x180022278  mov     rcx, [rcx+10h]
0x18002227c  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180022283  call    WPP_SF_s
0x180022288  jmp     short loc_1800222C0
0x18002228a  mov     rdx, [rsp+2A8h+var_60]
0x180022292  mov     r8, rbx; Size
0x180022295  add     rdx, 10h; Src
0x180022299  mov     rcx, rax; void *
0x18002229c  call    memcpy_0
0x1800222a1  test    rbp, rbp
0x1800222a4  jz      short loc_1800222BA
0x1800222a6  mov     rax, [rsp+2A8h+var_60]
0x1800222ae  mov     ecx, [rax+8]
0x1800222b1  mov     [rbp+0], ecx
0x1800222b4  jmp     short loc_1800222BA
0x1800222b6  xor     edi, edi
0x1800222b8  xor     ebx, ebx
0x1800222ba  mov     [r15], rdi
0x1800222bd  mov     [r14], ebx
0x1800222c0  mov     rcx, [rsp+2A8h+var_60]
0x1800222c8  test    rcx, rcx
0x1800222cb  jz      short loc_1800222D2
0x1800222cd  call    CspFreeH
0x1800222d2  mov     eax, esi
0x1800222d4  jmp     short loc_1800222DB
0x1800222d6  mov     eax, 80100004h
0x1800222db  mov     rcx, [rsp+2A8h+var_48]
0x1800222e3  xor     rcx, rsp; StackCookie
0x1800222e6  call    __security_check_cookie
0x1800222eb  add     rsp, 270h
0x1800222f2  pop     r15
0x1800222f4  pop     r14
0x1800222f6  pop     r12
0x1800222f8  pop     rdi
0x1800222f9  pop     rsi
0x1800222fa  pop     rbp
0x1800222fb  pop     rbx
0x1800222fc  retn
```
