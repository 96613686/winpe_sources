# CspGetContainerInfo

- ea: `0x18001ded8`
- end: `0x18001e269`
- name: `CspGetContainerInfo`
- size: `913`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800101d8`
- `0x18001d9a4`

## callees

- `0x18000a766`
- `0x18000de80`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x18001c71c`
- `0x18001ded8`
- `0x18001f3a4`
- `0x180021928`
- `0x18002217c`
- `0x18002cfa0`
- `0x18002e010`

## string_xrefs

- `0x18001df24`: `Cached_ContainerInfo`

## pseudocode

```c
__int64 __fastcall CspGetContainerInfo(__int64 a1, unsigned __int8 a2, __int64 a3, __int64 a4)
{
  _DWORD *v4; // rsi
  unsigned int CachedCardData; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  _DWORD *v11; // r14
  unsigned int v12; // edi
  __int64 v13; // rax
  int v14; // r9d
  _DWORD *v15; // rax
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  int v19; // edi
  const void *v20; // rdx
  const void *v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rax
  void *v24; // rax
  __int64 v25; // rcx
  void *v26; // rax
  unsigned int v28; // [rsp+40h] [rbp-268h] BYREF
  _DWORD *v29; // [rsp+48h] [rbp-260h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-258h] BYREF

  v4 = 0;
  *(_DWORD *)(a4 + 8) = 0;
  *(_DWORD *)(a4 + 24) = 0;
  *(_QWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 32) = 0;
  v29 = 0;
  v28 = 0;
  StringCbPrintfW(pszDest, 0x104u, L"%s_%02x", L"Cached_ContainerInfo", a2);
  CachedCardData = GetCachedCardData(a1, pszDest, 2, 1, &v29, &v28, 0);
  v11 = v29;
  v12 = CachedCardData;
  if ( CachedCardData )
  {
    if ( CachedCardData != 1168 )
      goto LABEL_40;
    v13 = *(_QWORD *)(a1 + 8);
    if ( !v13 )
    {
      v12 = 87;
      WppTraceIndent(v10, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
          v14,
          (__int64)"pCardState->pCardData");
      }
      goto LABEL_40;
    }
    LOBYTE(v9) = a2;
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(v13 + 152))(*(_QWORD *)(a1 + 8), v9, 0, a4);
    if ( v12 )
      goto LABEL_40;
    if ( *(_DWORD *)(a4 + 24) > 0x10000u || *(_DWORD *)(a4 + 8) > 0x10000u )
    {
      v12 = -2147024809;
      goto LABEL_40;
    }
    v15 = MIDL_user_allocate(*(unsigned int *)(a4 + 24) + 16LL + *(unsigned int *)(a4 + 8));
    v4 = v15;
    if ( !v15 )
    {
      WppTraceIndent(v16, 2);
      v12 = 8;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v18 = 17;
      goto LABEL_31;
    }
    v19 = *(_DWORD *)(a4 + 24) + *(_DWORD *)(a4 + 8) + 16;
    *v15 = *(_DWORD *)a4;
    v15[1] = *(_DWORD *)(a4 + 4);
    v15[3] = *(_DWORD *)(a4 + 24);
    v15[2] = *(_DWORD *)(a4 + 8);
    v20 = *(const void **)(a4 + 32);
    if ( v20 )
      memcpy_0(v15 + 4, v20, *(unsigned int *)(a4 + 24));
    v21 = *(const void **)(a4 + 16);
    if ( v21 )
      memcpy_0((char *)v4 + *(unsigned int *)(a4 + 24) + 16, v21, *(unsigned int *)(a4 + 8));
    v12 = AddCachedCardData(a1, pszDest, 2, 1, v4, v19, 0);
  }
  else
  {
    if ( v28 < 0x10 )
      goto LABEL_23;
    *(_DWORD *)a4 = *v29;
    *(_DWORD *)(a4 + 4) = v11[1];
    v22 = (unsigned int)v11[3];
    *(_DWORD *)(a4 + 24) = v22;
    v23 = (unsigned int)v11[2];
    *(_DWORD *)(a4 + 8) = v23;
    *(_QWORD *)(a4 + 16) = 0;
    *(_QWORD *)(a4 + 32) = 0;
    if ( v22 + v23 + 16 != v28 )
    {
LABEL_23:
      v12 = -2146893820;
      goto LABEL_40;
    }
    if ( (_DWORD)v22 )
    {
      v24 = MIDL_user_allocate((unsigned int)v22);
      *(_QWORD *)(a4 + 32) = v24;
      if ( !v24 )
      {
        WppTraceIndent(v25, 2);
        v12 = 8;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_40;
        }
        v18 = 14;
LABEL_31:
        WPP_SF_s(v17[2], v18, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids, WPP_pszIndent);
        goto LABEL_40;
      }
      memcpy_0(v24, v11 + 4, *(unsigned int *)(a4 + 24));
    }
    if ( !*(_DWORD *)(a4 + 8) )
      goto LABEL_40;
    v26 = MIDL_user_allocate(*(unsigned int *)(a4 + 8));
    *(_QWORD *)(a4 + 16) = v26;
    if ( v26 )
    {
      memcpy_0(v26, (char *)v11 + *(unsigned int *)(a4 + 24) + 16, *(unsigned int *)(a4 + 8));
      goto LABEL_40;
    }
    WppTraceIndent(0, 2);
    v12 = 8;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 15;
      goto LABEL_31;
    }
  }
LABEL_40:
  if ( v11 )
    CspFreeH(v11);
  if ( v4 )
    CspFreeH(v4);
  return v12;
}

```

## disassembly

```asm
0x18001ded8  push    rbx
0x18001deda  push    rbp
0x18001dedb  push    rsi
0x18001dedc  push    rdi
0x18001dedd  push    r13
0x18001dedf  push    r14
0x18001dee1  push    r15
0x18001dee3  sub     rsp, 270h
0x18001deea  mov     rax, cs:__security_cookie
0x18001def1  xor     rax, rsp
0x18001def4  mov     [rsp+2A8h+var_48], rax
0x18001defc  xor     esi, esi
0x18001defe  movzx   r15d, dl
0x18001df02  mov     [r9+8], esi
0x18001df06  lea     r8, aS02x; "%s_%02x"
0x18001df0d  mov     [r9+18h], esi
0x18001df11  mov     rbx, r9
0x18001df14  mov     [r9+10h], rsi
0x18001df18  mov     rbp, rcx
0x18001df1b  mov     [r9+20h], rsi
0x18001df1f  lea     rcx, [rsp+2A8h+pszDest]; pszDest
0x18001df24  lea     r9, aCachedContaine_0; "Cached_ContainerInfo"
0x18001df2b  mov     [rsp+2A8h+var_260], 0
0x18001df34  mov     edx, 104h; cbDest
0x18001df39  mov     [rsp+2A8h+var_268], 0
0x18001df41  mov     dword ptr [rsp+2A8h+var_288], r15d
0x18001df46  call    StringCbPrintfW
0x18001df4b  lea     rax, [rsp+2A8h+var_268]
0x18001df50  mov     [rsp+2A8h+var_278], rsi
0x18001df55  mov     [rsp+2A8h+var_280], rax
0x18001df5a  lea     r13d, [rsi+2]
0x18001df5e  lea     rax, [rsp+2A8h+var_260]
0x18001df63  mov     r8d, r13d
0x18001df66  lea     r9d, [rsi+1]
0x18001df6a  mov     [rsp+2A8h+var_288], rax
0x18001df6f  lea     rdx, [rsp+2A8h+pszDest]
0x18001df74  mov     rcx, rbp
0x18001df77  call    GetCachedCardData
0x18001df7c  mov     r14, [rsp+2A8h+var_260]
0x18001df81  mov     edi, eax
0x18001df83  test    eax, eax
0x18001df85  jz      loc_18001E113
0x18001df8b  cmp     eax, 490h
0x18001df90  jnz     loc_18001E22B
0x18001df96  mov     rax, [rbp+8]
0x18001df9a  test    rax, rax
0x18001df9d  jnz     short loc_18001DFF9
0x18001df9f  mov     edx, r13d
0x18001dfa2  lea     edi, [rsi+57h]
0x18001dfa5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001dfaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfb1  lea     rax, WPP_GLOBAL_Control
0x18001dfb8  cmp     rcx, rax
0x18001dfbb  jz      loc_18001E22B
0x18001dfc1  test    byte ptr [rcx+1Ch], 1
0x18001dfc5  jz      loc_18001E22B
0x18001dfcb  cmp     [rcx+19h], r13b
0x18001dfcf  jb      loc_18001E22B
0x18001dfd5  mov     rcx, [rcx+10h]
0x18001dfd9  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001dfe0  lea     edx, [rsi+10h]
0x18001dfe3  mov     [rsp+2A8h+var_288], rax
0x18001dfe8  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001dfef  call    WPP_SF_ss
0x18001dff4  jmp     loc_18001E22B
0x18001dff9  mov     rcx, rax
0x18001dffc  mov     r9, rbx
0x18001dfff  mov     rax, [rax+98h]
0x18001e006  xor     r8d, r8d
0x18001e009  mov     dl, r15b
0x18001e00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e011  mov     edi, eax
0x18001e013  test    eax, eax
0x18001e015  jnz     loc_18001E22B
0x18001e01b  mov     eax, 10000h
0x18001e020  cmp     [rbx+18h], eax
0x18001e023  ja      loc_18001E109
0x18001e029  cmp     [rbx+8], eax
0x18001e02c  ja      loc_18001E109
0x18001e032  mov     eax, [rbx+18h]
0x18001e035  mov     ecx, [rbx+8]
0x18001e038  add     rax, 10h
0x18001e03c  add     rcx, rax; size
0x18001e03f  call    MIDL_user_allocate
0x18001e044  mov     rsi, rax
0x18001e047  test    rax, rax
0x18001e04a  jnz     short loc_18001E08A
0x18001e04c  mov     edx, r13d
0x18001e04f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e054  lea     edi, [rsi+8]
0x18001e057  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e05e  lea     rax, WPP_GLOBAL_Control
0x18001e065  cmp     rcx, rax
0x18001e068  jz      loc_18001E22B
0x18001e06e  test    byte ptr [rcx+1Ch], 1
0x18001e072  jz      loc_18001E22B
0x18001e078  cmp     [rcx+19h], r13b
0x18001e07c  jb      loc_18001E22B
0x18001e082  lea     edx, [rsi+11h]
0x18001e085  jmp     loc_18001E1A5
0x18001e08a  mov     edi, [rbx+8]
0x18001e08d  mov     eax, [rbx]
0x18001e08f  add     edi, 10h
0x18001e092  add     edi, [rbx+18h]
0x18001e095  mov     [rsi], eax
0x18001e097  mov     eax, [rbx+4]
0x18001e09a  mov     [rsi+4], eax
0x18001e09d  mov     eax, [rbx+18h]
0x18001e0a0  mov     [rsi+0Ch], eax
0x18001e0a3  mov     eax, [rbx+8]
0x18001e0a6  mov     [rsi+8], eax
0x18001e0a9  mov     rdx, [rbx+20h]; Src
0x18001e0ad  test    rdx, rdx
0x18001e0b0  jz      short loc_18001E0BF
0x18001e0b2  mov     r8d, [rbx+18h]; Size
0x18001e0b6  lea     rcx, [rsi+10h]; void *
0x18001e0ba  call    memcpy_0
0x18001e0bf  mov     rdx, [rbx+10h]; Src
0x18001e0c3  test    rdx, rdx
0x18001e0c6  jz      short loc_18001E0DB
0x18001e0c8  mov     ecx, [rbx+18h]
0x18001e0cb  mov     r8d, [rbx+8]; Size
0x18001e0cf  add     rcx, 10h
0x18001e0d3  add     rcx, rsi; void *
0x18001e0d6  call    memcpy_0
0x18001e0db  mov     dword ptr [rsp+2A8h+var_278], 0
0x18001e0e3  lea     rdx, [rsp+2A8h+pszDest]
0x18001e0e8  mov     dword ptr [rsp+2A8h+var_280], edi
0x18001e0ec  mov     r9d, 1
0x18001e0f2  mov     r8d, r13d
0x18001e0f5  mov     [rsp+2A8h+var_288], rsi
0x18001e0fa  mov     rcx, rbp
0x18001e0fd  call    AddCachedCardData
0x18001e102  mov     edi, eax
0x18001e104  jmp     loc_18001E22B
0x18001e109  mov     edi, 80070057h
0x18001e10e  jmp     loc_18001E22B
0x18001e113  cmp     [rsp+2A8h+var_268], 10h
0x18001e118  jnb     short loc_18001E124
0x18001e11a  mov     edi, 80090004h
0x18001e11f  jmp     loc_18001E22B
0x18001e124  mov     eax, [r14]
0x18001e127  mov     [rbx], eax
0x18001e129  mov     eax, [r14+4]
0x18001e12d  mov     [rbx+4], eax
0x18001e130  mov     edx, [r14+0Ch]
0x18001e134  mov     [rbx+18h], edx
0x18001e137  mov     eax, [r14+8]
0x18001e13b  mov     [rbx+8], eax
0x18001e13e  mov     [rbx+10h], rsi
0x18001e142  mov     [rbx+20h], rsi
0x18001e146  lea     rcx, [rax+10h]
0x18001e14a  mov     eax, [rsp+2A8h+var_268]
0x18001e14e  add     rcx, rdx
0x18001e151  cmp     rcx, rax
0x18001e154  jnz     short loc_18001E11A
0x18001e156  test    edx, edx
0x18001e158  jz      short loc_18001E1CE
0x18001e15a  mov     ecx, edx; size
0x18001e15c  call    MIDL_user_allocate
0x18001e161  mov     [rbx+20h], rax
0x18001e165  test    rax, rax
0x18001e168  jnz     short loc_18001E1BE
0x18001e16a  mov     edx, r13d
0x18001e16d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e172  mov     edi, 8
0x18001e177  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e17e  lea     rax, WPP_GLOBAL_Control
0x18001e185  cmp     rcx, rax
0x18001e188  jz      loc_18001E22B
0x18001e18e  test    byte ptr [rcx+1Ch], 1
0x18001e192  jz      loc_18001E22B
0x18001e198  cmp     [rcx+19h], r13b
0x18001e19c  jb      loc_18001E22B
0x18001e1a2  lea     edx, [rdi+6]
0x18001e1a5  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001e1ac  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001e1b3  mov     rcx, [rcx+10h]
0x18001e1b7  call    WPP_SF_s
0x18001e1bc  jmp     short loc_18001E22B
0x18001e1be  mov     r8d, [rbx+18h]; Size
0x18001e1c2  lea     rdx, [r14+10h]; Src
0x18001e1c6  mov     rcx, rax; void *
0x18001e1c9  call    memcpy_0
0x18001e1ce  cmp     [rbx+8], esi
0x18001e1d1  jz      short loc_18001E22B
0x18001e1d3  mov     ecx, [rbx+8]; size
0x18001e1d6  call    MIDL_user_allocate
0x18001e1db  mov     [rbx+10h], rax
0x18001e1df  mov     rcx, rax; void *
0x18001e1e2  test    rax, rax
0x18001e1e5  jnz     short loc_18001E218
0x18001e1e7  mov     edx, r13d
0x18001e1ea  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e1ef  mov     edi, 8
0x18001e1f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1fb  lea     rax, WPP_GLOBAL_Control
0x18001e202  cmp     rcx, rax
0x18001e205  jz      short loc_18001E22B
0x18001e207  test    byte ptr [rcx+1Ch], 1
0x18001e20b  jz      short loc_18001E22B
0x18001e20d  cmp     [rcx+19h], r13b
0x18001e211  jb      short loc_18001E22B
0x18001e213  lea     edx, [rdi+7]
0x18001e216  jmp     short loc_18001E1A5
0x18001e218  mov     edx, [rbx+18h]
0x18001e21b  mov     r8d, [rbx+8]; Size
0x18001e21f  add     rdx, 10h
0x18001e223  add     rdx, r14; Src
0x18001e226  call    memcpy_0
0x18001e22b  test    r14, r14
0x18001e22e  jz      short loc_18001E238
0x18001e230  mov     rcx, r14
0x18001e233  call    CspFreeH
0x18001e238  test    rsi, rsi
0x18001e23b  jz      short loc_18001E245
0x18001e23d  mov     rcx, rsi
0x18001e240  call    CspFreeH
0x18001e245  mov     eax, edi
0x18001e247  mov     rcx, [rsp+2A8h+var_48]
0x18001e24f  xor     rcx, rsp; StackCookie
0x18001e252  call    __security_check_cookie
0x18001e257  add     rsp, 270h
0x18001e25e  pop     r15
0x18001e260  pop     r14
0x18001e262  pop     r13
0x18001e264  pop     rdi
0x18001e265  pop     rsi
0x18001e266  pop     rbp
0x18001e267  pop     rbx
0x18001e268  retn
```
