# I_UpdateCardState(_CARD_STATE *,ushort *,int)

- ea: `0x18001d1fc`
- end: `0x18001d3b9`
- name: `?I_UpdateCardState@@YAKPEAU_CARD_STATE@@PEAGH@Z`
- size: `445`
- prototype: `unsigned int(struct _CARD_STATE *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18001efd8`

## callees

- `0x180016e0c`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18001d1fc`
- `0x18001ee94`
- `0x18001f3a4`
- `0x1800225d4`
- `0x1800282ac`

## pseudocode

```c
__int64 __fastcall I_UpdateCardState(struct _CARD_STATE *a1, unsigned __int16 *a2, int a3)
{
  __int64 v3; // r14
  PVOID v7; // rcx
  unsigned int CardActivityCount; // edi
  int v9; // r9d
  _DWORD *v10; // rcx
  SCARDCONTEXT v11; // rcx
  int v12; // esi
  bool v13; // zf
  __int64 v14; // rcx

  v3 = *((_QWORD *)a1 + 1);
  WppTraceIndent((__int64)a1, 0);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids, WPP_pszIndent);
  }
  if ( *((_QWORD *)a1 + 1) )
  {
    v11 = *(_QWORD *)(v3 + 96);
    CardActivityCount = 0;
    v12 = 0;
    if ( v11 )
    {
      CardActivityCount = GetCardActivityCount(v11);
      if ( !CardActivityCount )
      {
        v13 = *((_DWORD *)a1 + 176) == 0;
        *((_DWORD *)a1 + 176) = 0;
        LOBYTE(v12) = !v13;
      }
    }
    v10 = (_DWORD *)*((_QWORD *)a1 + 1);
    if ( *v10 >= 6u && *((_DWORD *)a1 + 174) == 2 )
    {
      if ( !a3 && !CardActivityCount && !v12 )
        goto LABEL_20;
      ScCacheDeleteCache(*((_QWORD *)a1 + 84));
      v14 = *((_QWORD *)a1 + 85);
      *((_QWORD *)a1 + 84) = 0;
      ScCacheDeleteCache(v14);
      *((_QWORD *)a1 + 85) = 0;
      InitializeCacheHandles(a1);
    }
    if ( a3 )
      goto LABEL_21;
LABEL_20:
    StringCbCopyW((unsigned __int16 *)a1 + 16, 0x208u, a2);
    goto LABEL_21;
  }
  CardActivityCount = 87;
  WppTraceIndent((__int64)v7, 2u);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_ss(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
      v9,
      (__int64)"pCardState->pCardData");
  }
LABEL_21:
  WppTraceIndent((__int64)v10, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardActivityCount);
  }
  return CardActivityCount;
}

```

## disassembly

```asm
0x18001d1fc  push    rbx
0x18001d1fe  push    rbp
0x18001d1ff  push    rsi
0x18001d200  push    rdi
0x18001d201  push    r14
0x18001d203  push    r15
0x18001d205  sub     rsp, 38h
0x18001d209  mov     r14, [rcx+8]
0x18001d20d  mov     r15, rdx
0x18001d210  xor     edx, edx
0x18001d212  mov     [rsp+68h+arg_0], 0
0x18001d21a  mov     ebp, r8d
0x18001d21d  mov     rbx, rcx
0x18001d220  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d225  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d22c  lea     rax, WPP_GLOBAL_Control
0x18001d233  cmp     rcx, rax
0x18001d236  jz      short loc_18001D260
0x18001d238  test    byte ptr [rcx+1Ch], 2
0x18001d23c  jz      short loc_18001D260
0x18001d23e  cmp     byte ptr [rcx+19h], 5
0x18001d242  jb      short loc_18001D260
0x18001d244  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001d24b  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001d252  mov     rcx, [rcx+10h]
0x18001d256  mov     edx, 28h ; '('
0x18001d25b  call    WPP_SF_s
0x18001d260  cmp     qword ptr [rbx+8], 0
0x18001d265  jnz     short loc_18001D2C3
0x18001d267  mov     edi, 57h ; 'W'
0x18001d26c  lea     edx, [rdi-55h]
0x18001d26f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d274  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d27b  lea     rbx, WPP_GLOBAL_Control
0x18001d282  cmp     rcx, rbx
0x18001d285  jz      loc_18001D368
0x18001d28b  test    byte ptr [rcx+1Ch], 1
0x18001d28f  jz      loc_18001D368
0x18001d295  cmp     byte ptr [rcx+19h], 2
0x18001d299  jb      loc_18001D368
0x18001d29f  mov     rcx, [rcx+10h]
0x18001d2a3  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001d2aa  lea     edx, [rdi-2Eh]
0x18001d2ad  mov     [rsp+68h+var_48], rax
0x18001d2b2  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001d2b9  call    WPP_SF_ss
0x18001d2be  jmp     loc_18001D368
0x18001d2c3  mov     rcx, [r14+60h]; hContext
0x18001d2c7  xor     edi, edi
0x18001d2c9  xor     esi, esi
0x18001d2cb  test    rcx, rcx
0x18001d2ce  jz      short loc_18001D2F8
0x18001d2d0  lea     rdx, [rbx+20h]
0x18001d2d4  lea     r8, [rsp+68h+arg_0]
0x18001d2d9  call    GetCardActivityCount
0x18001d2de  mov     edi, eax
0x18001d2e0  test    eax, eax
0x18001d2e2  jnz     short loc_18001D2F8
0x18001d2e4  mov     ecx, [rsp+68h+arg_0]
0x18001d2e8  cmp     [rbx+2C0h], ecx
0x18001d2ee  mov     [rbx+2C0h], ecx
0x18001d2f4  setnz   sil
0x18001d2f8  mov     rcx, [rbx+8]
0x18001d2fc  cmp     dword ptr [rcx], 6
0x18001d2ff  jb      short loc_18001D34C
0x18001d301  cmp     dword ptr [rbx+2B8h], 2
0x18001d308  jnz     short loc_18001D34C
0x18001d30a  test    ebp, ebp
0x18001d30c  jnz     short loc_18001D316
0x18001d30e  test    edi, edi
0x18001d310  jnz     short loc_18001D316
0x18001d312  test    esi, esi
0x18001d314  jz      short loc_18001D350
0x18001d316  mov     rcx, [rbx+2A0h]
0x18001d31d  call    ScCacheDeleteCache
0x18001d322  mov     rcx, [rbx+2A8h]
0x18001d329  mov     qword ptr [rbx+2A0h], 0
0x18001d334  call    ScCacheDeleteCache
0x18001d339  mov     rcx, rbx
0x18001d33c  mov     qword ptr [rbx+2A8h], 0
0x18001d347  call    InitializeCacheHandles
0x18001d34c  test    ebp, ebp
0x18001d34e  jnz     short loc_18001D361
0x18001d350  lea     rcx, [rbx+20h]; unsigned __int16 *
0x18001d354  mov     r8, r15; unsigned __int16 *
0x18001d357  mov     edx, 208h; unsigned __int64
0x18001d35c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d361  lea     rbx, WPP_GLOBAL_Control
0x18001d368  mov     edx, 1
0x18001d36d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d372  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d379  cmp     rcx, rbx
0x18001d37c  jz      short loc_18001D3AA
0x18001d37e  test    byte ptr [rcx+1Ch], 2
0x18001d382  jz      short loc_18001D3AA
0x18001d384  cmp     byte ptr [rcx+19h], 5
0x18001d388  jb      short loc_18001D3AA
0x18001d38a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001d391  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001d398  mov     rcx, [rcx+10h]
0x18001d39c  mov     edx, 2Ah ; '*'
0x18001d3a1  mov     dword ptr [rsp+68h+var_48], edi
0x18001d3a5  call    WPP_SF_sD
0x18001d3aa  mov     eax, edi
0x18001d3ac  add     rsp, 38h
0x18001d3b0  pop     r15
0x18001d3b2  pop     r14
0x18001d3b4  pop     rdi
0x18001d3b5  pop     rsi
0x18001d3b6  pop     rbp
0x18001d3b7  pop     rbx
0x18001d3b8  retn
```
