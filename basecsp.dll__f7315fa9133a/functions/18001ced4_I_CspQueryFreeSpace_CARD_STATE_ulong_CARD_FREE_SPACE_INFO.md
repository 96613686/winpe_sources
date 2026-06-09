# I_CspQueryFreeSpace(_CARD_STATE *,ulong,_CARD_FREE_SPACE_INFO *)

- ea: `0x18001ced4`
- end: `0x18001d05e`
- name: `?I_CspQueryFreeSpace@@YAKPEAU_CARD_STATE@@KPEAU_CARD_FREE_SPACE_INFO@@@Z`
- size: `394`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned int, struct _CARD_FREE_SPACE_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001e480`

## callees

- `0x18000de80`
- `0x180017bac`
- `0x18001c71c`
- `0x18001ced4`
- `0x18001f3a4`
- `0x180021928`
- `0x18002217c`
- `0x18002cfa0`
- `0x18002e010`

## string_xrefs

- `0x18001cf1d`: `Cached_FreeSpace`

## pseudocode

```c
__int64 __fastcall I_CspQueryFreeSpace(struct _CARD_STATE *a1, __int64 a2, struct _CARD_FREE_SPACE_INFO *a3)
{
  unsigned int CachedCardData; // eax
  __int64 v6; // rcx
  _OWORD *v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rax
  int v10; // r9d
  int v12; // [rsp+40h] [rbp-248h] BYREF
  _OWORD *v13; // [rsp+48h] [rbp-240h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-238h] BYREF

  v13 = 0;
  v12 = 0;
  StringCbPrintfW(pszDest, 0x104u, L"%s", L"Cached_FreeSpace");
  CachedCardData = GetCachedCardData(a1, pszDest, 6, 1, &v13, &v12, 0);
  v7 = v13;
  v8 = CachedCardData;
  if ( CachedCardData )
  {
    if ( CachedCardData == 1168 )
    {
      v9 = *((_QWORD *)a1 + 1);
      if ( v9 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _CARD_FREE_SPACE_INFO *))(v9 + 288))(
               *((_QWORD *)a1 + 1),
               0,
               a3);
        if ( !v8 )
          v8 = AddCachedCardData(a1, pszDest, 6, 1, a3, 16, 0);
      }
      else
      {
        v8 = 87;
        WppTraceIndent(v6, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
            v10,
            (__int64)"pCardState->pCardData");
        }
      }
    }
  }
  else if ( v12 == 16 )
  {
    *(_OWORD *)a3 = *v13;
  }
  else
  {
    v8 = -2146893820;
  }
  if ( v7 )
    CspFreeH(v7);
  return v8;
}

```

## disassembly

```asm
0x18001ced4  mov     [rsp+arg_8], rbx
0x18001ced9  push    rbp
0x18001ceda  push    rsi
0x18001cedb  push    rdi
0x18001cedc  sub     rsp, 270h
0x18001cee3  mov     rax, cs:__security_cookie
0x18001ceea  xor     rax, rsp
0x18001ceed  mov     [rsp+288h+var_28], rax
0x18001cef5  mov     rsi, r8
0x18001cef8  mov     [rsp+288h+var_240], 0
0x18001cf01  mov     rbp, rcx
0x18001cf04  mov     [rsp+288h+var_248], 0
0x18001cf0c  lea     r8, aS; "%s"
0x18001cf13  mov     edx, 104h; cbDest
0x18001cf18  lea     rcx, [rsp+288h+pszDest]; pszDest
0x18001cf1d  lea     r9, aCachedFreespac; "Cached_FreeSpace"
0x18001cf24  call    StringCbPrintfW
0x18001cf29  mov     r9d, 1
0x18001cf2f  mov     [rsp+288h+var_258], 0
0x18001cf38  lea     rax, [rsp+288h+var_248]
0x18001cf3d  mov     rcx, rbp
0x18001cf40  mov     [rsp+288h+var_260], rax
0x18001cf45  lea     rdx, [rsp+288h+pszDest]
0x18001cf4a  lea     rax, [rsp+288h+var_240]
0x18001cf4f  lea     r8d, [r9+5]
0x18001cf53  mov     [rsp+288h+var_268], rax
0x18001cf58  call    GetCachedCardData
0x18001cf5d  mov     rdi, [rsp+288h+var_240]
0x18001cf62  mov     ebx, eax
0x18001cf64  test    eax, eax
0x18001cf66  jz      loc_18001D017
0x18001cf6c  cmp     eax, 490h
0x18001cf71  jnz     loc_18001D02C
0x18001cf77  mov     rax, [rbp+8]
0x18001cf7b  test    rax, rax
0x18001cf7e  jnz     short loc_18001CFD3
0x18001cf80  lea     edx, [rax+2]
0x18001cf83  lea     ebx, [rax+57h]
0x18001cf86  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001cf8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf92  lea     rax, WPP_GLOBAL_Control
0x18001cf99  cmp     rcx, rax
0x18001cf9c  jz      loc_18001D02C
0x18001cfa2  test    byte ptr [rcx+1Ch], 1
0x18001cfa6  jz      loc_18001D02C
0x18001cfac  cmp     byte ptr [rcx+19h], 2
0x18001cfb0  jb      short loc_18001D02C
0x18001cfb2  mov     rcx, [rcx+10h]
0x18001cfb6  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001cfbd  lea     edx, [rbx-38h]
0x18001cfc0  mov     [rsp+288h+var_268], rax
0x18001cfc5  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001cfcc  call    WPP_SF_ss
0x18001cfd1  jmp     short loc_18001D02C
0x18001cfd3  mov     rcx, rax
0x18001cfd6  mov     r8, rsi
0x18001cfd9  mov     rax, [rax+120h]
0x18001cfe0  xor     edx, edx
0x18001cfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfe7  mov     ebx, eax
0x18001cfe9  test    eax, eax
0x18001cfeb  jnz     short loc_18001D02C
0x18001cfed  mov     dword ptr [rsp+288h+var_258], eax
0x18001cff1  lea     r9d, [rax+1]
0x18001cff5  mov     dword ptr [rsp+288h+var_260], 10h
0x18001cffd  lea     r8d, [rax+6]
0x18001d001  lea     rdx, [rsp+288h+pszDest]
0x18001d006  mov     [rsp+288h+var_268], rsi
0x18001d00b  mov     rcx, rbp
0x18001d00e  call    AddCachedCardData
0x18001d013  mov     ebx, eax
0x18001d015  jmp     short loc_18001D02C
0x18001d017  cmp     [rsp+288h+var_248], 10h
0x18001d01c  jz      short loc_18001D025
0x18001d01e  mov     ebx, 80090004h
0x18001d023  jmp     short loc_18001D02C
0x18001d025  movups  xmm0, xmmword ptr [rdi]
0x18001d028  movdqu  xmmword ptr [rsi], xmm0
0x18001d02c  test    rdi, rdi
0x18001d02f  jz      short loc_18001D039
0x18001d031  mov     rcx, rdi
0x18001d034  call    CspFreeH
0x18001d039  mov     eax, ebx
0x18001d03b  mov     rcx, [rsp+288h+var_28]
0x18001d043  xor     rcx, rsp; StackCookie
0x18001d046  call    __security_check_cookie
0x18001d04b  mov     rbx, [rsp+288h+arg_8]
0x18001d053  add     rsp, 270h
0x18001d05a  pop     rdi
0x18001d05b  pop     rsi
0x18001d05c  pop     rbp
0x18001d05d  retn
```
